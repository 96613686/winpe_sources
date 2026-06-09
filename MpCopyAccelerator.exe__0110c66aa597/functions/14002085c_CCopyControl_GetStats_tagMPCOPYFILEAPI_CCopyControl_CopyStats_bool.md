# CCopyControl::GetStats(tagMPCOPYFILEAPI,CCopyControl::CopyStats &,bool)

- ea: `0x14002085c`
- end: `0x1400208f1`
- name: `?GetStats@CCopyControl@@QEAAXW4tagMPCOPYFILEAPI@@AEAUCopyStats@1@_N@Z`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001efa4`

## callees

- `0x14002085c`

## pseudocode

```c
void __fastcall CCopyControl::GetStats(__int64 a1, int a2, volatile __int32 *a3)
{
  int v4; // edx
  int v5; // edx
  __int64 v6; // rax
  volatile signed __int32 *v7; // r10
  signed __int32 v8; // ecx
  signed __int32 v9; // edx
  signed __int32 v10; // r8d
  signed __int32 v11; // r9d
  signed __int32 v12; // eax
  signed __int32 v13; // eax
  signed __int32 v14; // eax
  signed __int32 v15; // eax

  if ( a2 )
  {
    v4 = a2 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 != 1 )
          return;
        v6 = 80;
      }
      else
      {
        v6 = 48;
      }
    }
    else
    {
      v6 = 64;
    }
  }
  else
  {
    v6 = 32;
  }
  v7 = (volatile signed __int32 *)(v6 + a1);
  if ( v6 + a1 )
  {
    v8 = *((_DWORD *)v7 + 1);
    v9 = *((_DWORD *)v7 + 2);
    v10 = *v7;
    v11 = *((_DWORD *)v7 + 3);
    v12 = _InterlockedCompareExchange(v7 + 1, 0, v8);
    if ( v8 != v12 )
      v8 = v12;
    v13 = _InterlockedCompareExchange(v7 + 2, 0, v9);
    if ( v9 != v13 )
      v9 = v13;
    v14 = _InterlockedCompareExchange(v7, 0, v10);
    if ( v10 != v14 )
      v10 = v14;
    v15 = _InterlockedCompareExchange(v7 + 3, 0, v11);
    _InterlockedExchange(a3 + 1, v8);
    _InterlockedExchange(a3 + 2, v9);
    _InterlockedExchange(a3, v10);
    if ( v11 != v15 )
      v11 = v15;
    _InterlockedExchange(a3 + 3, v11);
  }
}

```

## disassembly

```asm
0x14002085c  mov     [rsp+arg_8], rbx
0x140020861  xor     ebx, ebx
0x140020863  mov     r11, r8
0x140020866  test    edx, edx
0x140020868  jz      short loc_14002088C
0x14002086a  sub     edx, 1
0x14002086d  jz      short loc_140020885
0x14002086f  sub     edx, 1
0x140020872  jz      short loc_14002087E
0x140020874  cmp     edx, 1
0x140020877  jnz     short loc_1400208EB
0x140020879  lea     eax, [rbx+50h]
0x14002087c  jmp     short loc_140020891
0x14002087e  mov     eax, 30h ; '0'
0x140020883  jmp     short loc_140020891
0x140020885  mov     eax, 40h ; '@'
0x14002088a  jmp     short loc_140020891
0x14002088c  mov     eax, 20h ; ' '
0x140020891  lea     r10, [rax+rcx]
0x140020895  test    r10, r10
0x140020898  jz      short loc_1400208EB
0x14002089a  mov     ecx, [r10+4]
0x14002089e  nop
0x14002089f  mov     edx, [r10+8]
0x1400208a3  mov     eax, ecx
0x1400208a5  nop
0x1400208a6  mov     r8d, [r10]
0x1400208a9  nop
0x1400208aa  mov     r9d, [r10+0Ch]
0x1400208ae  nop
0x1400208af  lock cmpxchg [r10+4], ebx
0x1400208b5  cmovnz  ecx, eax
0x1400208b8  mov     eax, edx
0x1400208ba  lock cmpxchg [r10+8], ebx
0x1400208c0  cmovnz  edx, eax
0x1400208c3  mov     eax, r8d
0x1400208c6  lock cmpxchg [r10], ebx
0x1400208cb  cmovnz  r8d, eax
0x1400208cf  mov     eax, r9d
0x1400208d2  lock cmpxchg [r10+0Ch], ebx
0x1400208d8  xchg    ecx, [r11+4]
0x1400208dc  xchg    edx, [r11+8]
0x1400208e0  xchg    r8d, [r11]
0x1400208e3  cmovnz  r9d, eax
0x1400208e7  xchg    r9d, [r11+0Ch]
0x1400208eb  mov     rbx, [rsp+arg_8]
0x1400208f0  retn
```
