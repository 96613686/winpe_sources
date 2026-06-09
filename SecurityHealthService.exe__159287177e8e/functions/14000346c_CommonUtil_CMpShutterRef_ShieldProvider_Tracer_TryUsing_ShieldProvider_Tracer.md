# CommonUtil::CMpShutterRef<ShieldProvider::Tracer>::TryUsing(ShieldProvider::Tracer * *)

- ea: `0x14000346c`
- end: `0x140003523`
- name: `?TryUsing@?$CMpShutterRef@VTracer@ShieldProvider@@@CommonUtil@@QEBAJPEAPEAVTracer@ShieldProvider@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000329c`

## callees

- `0x14000346c`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::CMpShutterRef<ShieldProvider::Tracer>::TryUsing(__int64 a1, _QWORD *a2)
{
  int v2; // r8d
  __int64 v4; // rcx

  do
  {
    v2 = dword_14001B7C0;
    if ( dword_14001B7C0 < 0 )
      return 2147500036LL;
  }
  while ( v2 != _InterlockedCompareExchange(&dword_14001B7C0, dword_14001B7C0 + 1, dword_14001B7C0) );
  if ( *(_DWORD *)(qword_14001B7C8 + 8) )
    _InterlockedIncrement((volatile signed __int32 *)(qword_14001B7C8 + 8));
  else
    *(_DWORD *)(qword_14001B7C8 + 8) = 1;
  *a2 = qword_14001B7C8;
  if ( _InterlockedDecrement(&dword_14001B7C0) == 0x80000000 )
  {
    v4 = qword_14001B7C8;
    qword_14001B7C8 = 0;
    if ( *(_DWORD *)(v4 + 8) == 1 )
    {
      *(_DWORD *)(v4 + 8) = 0;
      goto LABEL_12;
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)(v4 + 8)) <= 0 )
    {
LABEL_12:
      if ( v4 )
        (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000346c  sub     rsp, 28h
0x140003470  jmp     short loc_140003486
0x140003472  lea     ecx, [r8+1]
0x140003476  mov     eax, r8d
0x140003479  lock cmpxchg cs:dword_14001B7C0, ecx
0x140003481  cmp     r8d, eax
0x140003484  jz      short loc_14000349C
0x140003486  mov     r8d, cs:dword_14001B7C0
0x14000348d  test    r8d, r8d
0x140003490  jns     short loc_140003472
0x140003492  mov     eax, 80004004h
0x140003497  add     rsp, 28h
0x14000349b  retn
0x14000349c  mov     rcx, cs:qword_14001B7C8
0x1400034a3  mov     eax, [rcx+8]
0x1400034a6  test    eax, eax
0x1400034a8  jnz     short loc_1400034B3
0x1400034aa  mov     dword ptr [rcx+8], 1
0x1400034b1  jmp     short loc_1400034B7
0x1400034b3  lock inc dword ptr [rcx+8]
0x1400034b7  mov     rax, cs:qword_14001B7C8
0x1400034be  mov     [rdx], rax
0x1400034c1  or      edx, 0FFFFFFFFh
0x1400034c4  mov     eax, edx
0x1400034c6  lock xadd cs:dword_14001B7C0, eax
0x1400034ce  add     eax, edx
0x1400034d0  cmp     eax, 80000000h
0x1400034d5  jnz     short loc_14000351C
0x1400034d7  mov     rcx, cs:qword_14001B7C8
0x1400034de  mov     cs:qword_14001B7C8, 0
0x1400034e9  mov     eax, [rcx+8]
0x1400034ec  cmp     eax, 1
0x1400034ef  jnz     short loc_1400034FA
0x1400034f1  mov     dword ptr [rcx+8], 0
0x1400034f8  jmp     short loc_140003507
0x1400034fa  mov     eax, edx
0x1400034fc  lock xadd [rcx+8], eax
0x140003501  add     eax, edx
0x140003503  test    eax, eax
0x140003505  jg      short loc_14000351C
0x140003507  test    rcx, rcx
0x14000350a  jz      short loc_14000351C
0x14000350c  mov     rax, [rcx]
0x14000350f  mov     edx, 1
0x140003514  mov     rax, [rax]
0x140003517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000351c  xor     eax, eax
0x14000351e  jmp     loc_140003497
```
