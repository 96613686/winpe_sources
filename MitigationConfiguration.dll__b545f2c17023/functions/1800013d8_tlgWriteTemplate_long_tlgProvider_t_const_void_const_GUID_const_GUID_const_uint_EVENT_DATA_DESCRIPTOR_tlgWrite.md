# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013d8`
- end: `0x18000150b`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013528`
- `0x180013720`

## callees

- `0x18000113c`
- `0x1800013d8`
- `0x180001c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax

  v8 = -1;
  if ( *a8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*a8 + 2 * v9) );
  }
  if ( *a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(*a7 + 2 * v10) );
  }
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(*a6 + 2 * v11) );
  }
  if ( *a5 )
  {
    do
      ++v8;
    while ( *(_WORD *)(*a5 + 2 * v8) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0);
}

```

## disassembly

```asm
0x1800013d8  push    rbp
0x1800013da  lea     rbp, [rsp-37h]
0x1800013df  sub     rsp, 0A0h
0x1800013e6  mov     rax, cs:__security_cookie
0x1800013ed  xor     rax, rsp
0x1800013f0  mov     [rbp+37h+var_10], rax
0x1800013f4  mov     rax, [rbp+37h+arg_38]
0x1800013f8  lea     r11, qword_180018390
0x1800013ff  mov     r10, rdx
0x180001402  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001406  xor     r9d, r9d
0x180001409  mov     r8d, 2
0x18000140f  mov     rdx, [rax]
0x180001412  test    rdx, rdx
0x180001415  jz      short loc_18000142D
0x180001417  mov     rax, rcx
0x18000141a  inc     rax
0x18000141d  cmp     [rdx+rax*2], r9w
0x180001422  jnz     short loc_18000141A
0x180001424  lea     eax, ds:2[rax*2]
0x18000142b  jmp     short loc_180001433
0x18000142d  mov     rdx, r11
0x180001430  mov     eax, r8d
0x180001433  mov     [rbp+37h+var_18], eax
0x180001436  mov     rax, [rbp+37h+arg_30]
0x18000143a  mov     [rbp+37h+var_20], rdx
0x18000143e  mov     [rbp+37h+var_14], r9d
0x180001442  mov     rdx, [rax]
0x180001445  test    rdx, rdx
0x180001448  jz      short loc_180001460
0x18000144a  mov     rax, rcx
0x18000144d  inc     rax
0x180001450  cmp     [rdx+rax*2], r9w
0x180001455  jnz     short loc_18000144D
0x180001457  lea     eax, ds:2[rax*2]
0x18000145e  jmp     short loc_180001466
0x180001460  mov     rdx, r11
0x180001463  mov     eax, r8d
0x180001466  mov     [rbp+37h+var_28], eax
0x180001469  mov     rax, [rbp+37h+arg_28]
0x18000146d  mov     [rbp+37h+var_30], rdx
0x180001471  mov     [rbp+37h+var_24], r9d
0x180001475  mov     rdx, [rax]
0x180001478  test    rdx, rdx
0x18000147b  jz      short loc_180001493
0x18000147d  mov     rax, rcx
0x180001480  inc     rax
0x180001483  cmp     [rdx+rax*2], r9w
0x180001488  jnz     short loc_180001480
0x18000148a  lea     eax, ds:2[rax*2]
0x180001491  jmp     short loc_180001499
0x180001493  mov     rdx, r11
0x180001496  mov     eax, r8d
0x180001499  mov     [rbp+37h+var_38], eax
0x18000149c  mov     rax, [rbp+37h+arg_20]
0x1800014a0  mov     [rbp+37h+var_40], rdx
0x1800014a4  mov     [rbp+37h+var_34], r9d
0x1800014a8  mov     rdx, [rax]
0x1800014ab  test    rdx, rdx
0x1800014ae  jz      short loc_1800014C4
0x1800014b0  inc     rcx
0x1800014b3  cmp     [rdx+rcx*2], r9w
0x1800014b8  jnz     short loc_1800014B0
0x1800014ba  lea     r8d, ds:2[rcx*2]
0x1800014c2  jmp     short loc_1800014C7
0x1800014c4  mov     rdx, r11
0x1800014c7  lea     rax, [rbp+37h+var_70]
0x1800014cb  mov     [rbp+37h+var_50], rdx
0x1800014cf  mov     [rbp+37h+var_48], r8d
0x1800014d3  lea     rcx, dword_18001C038
0x1800014da  mov     [rsp+0A0h+var_78], rax
0x1800014df  xor     r8d, r8d
0x1800014e2  mov     rdx, r10
0x1800014e5  mov     [rsp+0A0h+var_80], 6
0x1800014ed  mov     [rbp+37h+var_44], r9d
0x1800014f1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800014f6  mov     rcx, [rbp+37h+var_10]
0x1800014fa  xor     rcx, rsp; StackCookie
0x1800014fd  call    __security_check_cookie
0x180001502  add     rsp, 0A0h
0x180001509  pop     rbp
0x18000150a  retn
```
