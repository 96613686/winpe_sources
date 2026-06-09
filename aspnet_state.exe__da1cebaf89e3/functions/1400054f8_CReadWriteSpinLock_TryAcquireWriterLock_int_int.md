# CReadWriteSpinLock::_TryAcquireWriterLock(int,int)

- ea: `0x1400054f8`
- end: `0x14000556c`
- name: `?_TryAcquireWriterLock@CReadWriteSpinLock@@AEAAHHH@Z`
- size: `116`
- prototype: `__int64 __fastcall(CReadWriteSpinLock *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400052d0`
- `0x1400053dc`

## callees

- `0x140005314`
- `0x1400054f8`

## pseudocode

```c
__int64 __fastcall CReadWriteSpinLock::_TryAcquireWriterLock(CReadWriteSpinLock *this, int a2, int a3)
{
  int v3; // eax
  int v5; // ett
  signed __int32 v6; // eax
  int v7; // ett
  signed __int32 v8; // edx

  v3 = *(_DWORD *)this;
  if ( *((_DWORD *)this + 1) == a2 )
  {
    CReadWriteSpinLock::AlterWriteCountHoldingWriterLock(this, v3, 1);
    return 1;
  }
  if ( !*((_DWORD *)this + 1) && (v3 & 0xBFFFFFFF) == 0 )
  {
    v5 = *(_DWORD *)this;
    v3 = _InterlockedCompareExchange((volatile signed __int32 *)this, 0x10000, v3);
    if ( v5 == v3 )
    {
      *((_DWORD *)this + 1) = a2;
      return 1;
    }
  }
  if ( a3 )
  {
    if ( (v3 & 0x40000000) == 0 )
    {
      v7 = v3;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)this, v3 | 0x40000000, v3);
      if ( v7 != v6 )
      {
        do
        {
          v8 = v6;
          v6 = _InterlockedCompareExchange((volatile signed __int32 *)this, v6 | 0x40000000, v6);
        }
        while ( v6 != v8 );
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400054f8  sub     rsp, 28h
0x1400054fc  mov     r9, rcx
0x1400054ff  mov     eax, [rcx]
0x140005501  cmp     [rcx+4], edx
0x140005504  jnz     short loc_14000551A
0x140005506  mov     r8d, 1; int
0x14000550c  mov     edx, eax; int
0x14000550e  call    ?AlterWriteCountHoldingWriterLock@CReadWriteSpinLock@@AEAAXHH@Z; CReadWriteSpinLock::AlterWriteCountHoldingWriterLock(int,int)
0x140005513  mov     eax, 1
0x140005518  jmp     short loc_140005567
0x14000551a  cmp     dword ptr [rcx+4], 0
0x14000551e  jnz     short loc_140005539
0x140005520  test    eax, 0BFFFFFFFh
0x140005525  jnz     short loc_140005539
0x140005527  mov     ecx, 10000h
0x14000552c  lock cmpxchg [r9], ecx
0x140005531  jnz     short loc_140005539
0x140005533  mov     [r9+4], edx
0x140005537  jmp     short loc_140005513
0x140005539  test    r8d, r8d
0x14000553c  jz      short loc_140005565
0x14000553e  mov     r8d, 40000000h
0x140005544  test    r8d, eax
0x140005547  jnz     short loc_140005565
0x140005549  mov     ecx, eax
0x14000554b  or      ecx, r8d
0x14000554e  lock cmpxchg [r9], ecx
0x140005553  jz      short loc_140005565
0x140005555  mov     ecx, eax
0x140005557  mov     edx, eax
0x140005559  or      ecx, r8d
0x14000555c  lock cmpxchg [r9], ecx
0x140005561  cmp     eax, edx
0x140005563  jnz     short loc_140005555
0x140005565  xor     eax, eax
0x140005567  add     rsp, 28h
0x14000556b  retn
```
