# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013c4`
- end: `0x18000153a`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43AEBU?$_tlgWrapSz@G@@@Z`
- size: `374`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b994`

## callees

- `0x1800011d0`
- `0x1800013c4`
- `0x180001e20`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        _QWORD *a11)
{
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax

  v11 = -1;
  if ( *a11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(*a11 + 2 * v12) );
  }
  if ( *a10 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_BYTE *)(*a10 + v13) );
  }
  if ( *a7 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(*a7 + v14) );
  }
  if ( *a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_BYTE *)(*a6 + v15) );
  }
  if ( *a5 )
  {
    do
      ++v11;
    while ( *(_BYTE *)(*a5 + v11) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001D000, a2, 0);
}

```

## disassembly

```asm
0x1800013c4  push    rbp
0x1800013c6  lea     rbp, [rsp-1Fh]
0x1800013cb  sub     rsp, 0D0h
0x1800013d2  mov     rax, cs:__security_cookie
0x1800013d9  xor     rax, rsp
0x1800013dc  mov     [rbp+1Fh+var_10], rax
0x1800013e0  mov     rax, [rbp+1Fh+arg_50]
0x1800013e4  mov     r10, rdx
0x1800013e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800013eb  xor     r9d, r9d
0x1800013ee  mov     rdx, [rax]
0x1800013f1  test    rdx, rdx
0x1800013f4  jz      short loc_18000140C
0x1800013f6  mov     rax, rcx
0x1800013f9  inc     rax
0x1800013fc  cmp     [rdx+rax*2], r9w
0x180001401  jnz     short loc_1800013F9
0x180001403  lea     eax, ds:2[rax*2]
0x18000140a  jmp     short loc_180001418
0x18000140c  lea     rdx, byte_180017140
0x180001413  mov     eax, 2
0x180001418  mov     [rbp+1Fh+var_18], eax
0x18000141b  lea     r11, qword_1800150F8
0x180001422  mov     rax, [rbp+1Fh+arg_48]
0x180001426  mov     r8d, 1
0x18000142c  mov     [rbp+1Fh+var_20], rdx
0x180001430  mov     [rbp+1Fh+var_14], r9d
0x180001434  mov     rdx, [rax]
0x180001437  test    rdx, rdx
0x18000143a  jz      short loc_18000144C
0x18000143c  mov     rax, rcx
0x18000143f  inc     rax
0x180001442  cmp     [rdx+rax], r9b
0x180001446  jnz     short loc_18000143F
0x180001448  inc     eax
0x18000144a  jmp     short loc_180001452
0x18000144c  mov     rdx, r11
0x18000144f  mov     eax, r8d
0x180001452  mov     [rbp+1Fh+var_28], eax
0x180001455  mov     rax, [rbp+1Fh+arg_40]
0x180001459  mov     [rbp+1Fh+var_40], rax
0x18000145d  mov     rax, [rbp+1Fh+arg_38]
0x180001461  mov     [rbp+1Fh+var_50], rax
0x180001465  mov     rax, [rbp+1Fh+arg_30]
0x180001469  mov     [rbp+1Fh+var_30], rdx
0x18000146d  mov     [rbp+1Fh+var_24], r9d
0x180001471  mov     [rbp+1Fh+var_38], 4
0x180001479  mov     rdx, [rax]
0x18000147c  mov     [rbp+1Fh+var_48], 4
0x180001484  test    rdx, rdx
0x180001487  jz      short loc_180001499
0x180001489  mov     rax, rcx
0x18000148c  inc     rax
0x18000148f  cmp     [rdx+rax], r9b
0x180001493  jnz     short loc_18000148C
0x180001495  inc     eax
0x180001497  jmp     short loc_18000149F
0x180001499  mov     rdx, r11
0x18000149c  mov     eax, r8d
0x18000149f  mov     [rbp+1Fh+var_58], eax
0x1800014a2  mov     rax, [rbp+1Fh+arg_28]
0x1800014a6  mov     [rbp+1Fh+var_60], rdx
0x1800014aa  mov     [rbp+1Fh+var_54], r9d
0x1800014ae  mov     rdx, [rax]
0x1800014b1  test    rdx, rdx
0x1800014b4  jz      short loc_1800014C6
0x1800014b6  mov     rax, rcx
0x1800014b9  inc     rax
0x1800014bc  cmp     [rdx+rax], r9b
0x1800014c0  jnz     short loc_1800014B9
0x1800014c2  inc     eax
0x1800014c4  jmp     short loc_1800014CC
0x1800014c6  mov     rdx, r11
0x1800014c9  mov     eax, r8d
0x1800014cc  mov     [rbp+1Fh+var_68], eax
0x1800014cf  mov     rax, [rbp+1Fh+arg_20]
0x1800014d3  mov     [rbp+1Fh+var_70], rdx
0x1800014d7  mov     [rbp+1Fh+var_64], r9d
0x1800014db  mov     rdx, [rax]
0x1800014de  test    rdx, rdx
0x1800014e1  jz      short loc_1800014F2
0x1800014e3  inc     rcx
0x1800014e6  cmp     [rdx+rcx], r9b
0x1800014ea  jnz     short loc_1800014E3
0x1800014ec  lea     r8d, [rcx+1]
0x1800014f0  jmp     short loc_1800014F5
0x1800014f2  mov     rdx, r11
0x1800014f5  lea     rax, [rsp+0D0h+var_A0]
0x1800014fa  mov     [rbp+1Fh+var_80], rdx
0x1800014fe  mov     [rbp+1Fh+var_78], r8d
0x180001502  lea     rcx, dword_18001D000
0x180001509  mov     [rsp+0D0h+var_A8], rax
0x18000150e  xor     r8d, r8d
0x180001511  mov     rdx, r10
0x180001514  mov     [rsp+0D0h+var_B0], 9
0x18000151c  mov     [rbp+1Fh+var_74], r9d
0x180001520  call    _tlgWriteTransfer_EventWriteTransfer
0x180001525  mov     rcx, [rbp+1Fh+var_10]
0x180001529  xor     rcx, rsp; StackCookie
0x18000152c  call    __security_check_cookie
0x180001531  add     rsp, 0D0h
0x180001538  pop     rbp
0x180001539  retn
```
