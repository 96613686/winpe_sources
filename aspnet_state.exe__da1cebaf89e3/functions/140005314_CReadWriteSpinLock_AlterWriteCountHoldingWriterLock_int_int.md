# CReadWriteSpinLock::AlterWriteCountHoldingWriterLock(int,int)

- ea: `0x140005314`
- end: `0x14000536e`
- name: `?AlterWriteCountHoldingWriterLock@CReadWriteSpinLock@@AEAAXHH@Z`
- size: `90`
- prototype: `void __fastcall(CReadWriteSpinLock *this, signed __int32, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005374`
- `0x1400054f8`

## callees

- `0x140005314`

## pseudocode

```c
void __fastcall CReadWriteSpinLock::AlterWriteCountHoldingWriterLock(
        CReadWriteSpinLock *this,
        signed __int32 a2,
        int a3)
{
  int v3; // r11d
  int v4; // r9d
  unsigned __int32 v5; // eax
  unsigned __int32 v6; // edx

  v3 = (unsigned __int16)a2;
  v4 = a3 + ((a2 >> 16) & 0x3FFF);
  v5 = _InterlockedCompareExchange(
         (volatile signed __int32 *)this,
         (unsigned __int16)a2 | ((v4 | ((((unsigned int)a2 >> 30) & 1) << 14)) << 16),
         a2);
  if ( a2 != v5 )
  {
    do
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange(
             (volatile signed __int32 *)this,
             v3 | ((v4 | (((v5 >> 30) & 1) << 14)) << 16),
             v5);
    }
    while ( v5 != v6 );
  }
}

```

## disassembly

```asm
0x140005314  mov     r9d, edx
0x140005317  movzx   r11d, dx
0x14000531b  sar     r9d, 10h
0x14000531f  mov     r10, rcx
0x140005322  and     r9d, 3FFFh
0x140005329  mov     eax, edx
0x14000532b  add     r9d, r8d
0x14000532e  mov     r8d, edx
0x140005331  shr     r8d, 1Eh
0x140005335  and     r8d, 1
0x140005339  shl     r8d, 0Eh
0x14000533d  or      r8d, r9d
0x140005340  shl     r8d, 10h
0x140005344  or      r8d, r11d
0x140005347  lock cmpxchg [rcx], r8d
0x14000534c  jz      short locret_14000536D
0x14000534e  mov     ecx, eax
0x140005350  mov     edx, eax
0x140005352  shr     ecx, 1Eh
0x140005355  and     ecx, 1
0x140005358  shl     ecx, 0Eh
0x14000535b  or      ecx, r9d
0x14000535e  shl     ecx, 10h
0x140005361  or      ecx, r11d
0x140005364  lock cmpxchg [r10], ecx
0x140005369  cmp     eax, edx
0x14000536b  jnz     short loc_14000534E
0x14000536d  retn
```
