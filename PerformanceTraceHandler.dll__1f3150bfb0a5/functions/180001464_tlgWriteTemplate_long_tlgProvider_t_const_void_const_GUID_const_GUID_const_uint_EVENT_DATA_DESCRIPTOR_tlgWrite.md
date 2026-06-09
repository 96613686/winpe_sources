# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001464`
- end: `0x180001753`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800170bc`

## callees

- `0x180001464`
- `0x1800018e8`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        _QWORD *a11,
        __int64 a12,
        _QWORD *a13,
        __int64 a14,
        _QWORD *a15,
        _QWORD *a16,
        __int64 a17,
        _QWORD *a18,
        _QWORD *a19,
        __int64 a20,
        __int64 a21,
        _QWORD *a22)
{
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax

  v23 = -1;
  if ( *a22 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_BYTE *)(*a22 + v24) );
  }
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*a19 + 2 * v25) );
  }
  if ( *a18 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a18 + v26) );
  }
  if ( *a16 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a16 + 2 * v27) );
  }
  if ( *a15 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a15 + v28) );
  }
  if ( *a13 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(*a13 + v29) );
  }
  if ( *a11 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_WORD *)(*a11 + 2 * v30) );
  }
  if ( *a9 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *(_BYTE *)(*a9 + v31) );
  }
  if ( *a7 )
  {
    do
      ++v23;
    while ( *(_BYTE *)(*a7 + v23) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x180001464  mov     [rsp-8+arg_10], rbx
0x180001469  push    rbp
0x18000146a  push    rdi
0x18000146b  push    r14
0x18000146d  lea     rbp, [rsp-80h]
0x180001472  sub     rsp, 180h
0x180001479  mov     rax, cs:__security_cookie
0x180001480  xor     rax, rsp
0x180001483  mov     [rbp+90h+var_20], rax
0x180001487  mov     rax, [rbp+90h+arg_A8]
0x18000148e  lea     rdi, byte_18001E1D0
0x180001495  mov     r11, rdx
0x180001498  mov     r10, rcx
0x18000149b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000149f  xor     ebx, ebx
0x1800014a1  mov     r8d, 1
0x1800014a7  mov     rcx, [rax]
0x1800014aa  test    rcx, rcx
0x1800014ad  jz      short loc_1800014BE
0x1800014af  mov     rax, rdx
0x1800014b2  inc     rax
0x1800014b5  cmp     [rcx+rax], bl
0x1800014b8  jnz     short loc_1800014B2
0x1800014ba  inc     eax
0x1800014bc  jmp     short loc_1800014C4
0x1800014be  mov     rcx, rdi
0x1800014c1  mov     eax, r8d
0x1800014c4  mov     [rbp+90h+var_28], eax
0x1800014c7  mov     r9d, 2
0x1800014cd  mov     rax, [rbp+90h+arg_A0]
0x1800014d4  mov     [rbp+90h+var_40], rax
0x1800014d8  mov     rax, [rbp+90h+arg_98]
0x1800014df  mov     [rbp+90h+var_50], rax
0x1800014e3  mov     rax, [rbp+90h+arg_90]
0x1800014ea  mov     [rbp+90h+var_30], rcx
0x1800014ee  mov     [rbp+90h+var_24], ebx
0x1800014f1  mov     [rbp+90h+var_38], 4
0x1800014f9  mov     rcx, [rax]
0x1800014fc  mov     [rbp+90h+var_48], 4
0x180001504  test    rcx, rcx
0x180001507  jz      short loc_18000151E
0x180001509  mov     rax, rdx
0x18000150c  inc     rax
0x18000150f  cmp     [rcx+rax*2], bx
0x180001513  jnz     short loc_18000150C
0x180001515  lea     eax, ds:2[rax*2]
0x18000151c  jmp     short loc_180001528
0x18000151e  lea     rcx, dword_18001E1D4
0x180001525  mov     eax, r9d
0x180001528  mov     [rbp+90h+var_58], eax
0x18000152b  mov     rax, [rbp+90h+arg_88]
0x180001532  mov     [rbp+90h+var_60], rcx
0x180001536  mov     [rbp+90h+var_54], ebx
0x180001539  mov     rcx, [rax]
0x18000153c  test    rcx, rcx
0x18000153f  jz      short loc_180001550
0x180001541  mov     rax, rdx
0x180001544  inc     rax
0x180001547  cmp     [rcx+rax], bl
0x18000154a  jnz     short loc_180001544
0x18000154c  inc     eax
0x18000154e  jmp     short loc_180001556
0x180001550  mov     rcx, rdi
0x180001553  mov     eax, r8d
0x180001556  mov     [rbp+90h+var_68], eax
0x180001559  mov     rax, [rbp+90h+arg_80]
0x180001560  mov     [rbp+90h+var_80], rax
0x180001564  mov     rax, [rbp+90h+arg_78]
0x18000156b  mov     [rbp+90h+var_70], rcx
0x18000156f  mov     [rbp+90h+var_64], ebx
0x180001572  mov     [rbp+90h+var_78], 4
0x18000157a  mov     rcx, [rax]
0x18000157d  test    rcx, rcx
0x180001580  jz      short loc_180001597
0x180001582  mov     rax, rdx
0x180001585  inc     rax
0x180001588  cmp     [rcx+rax*2], bx
0x18000158c  jnz     short loc_180001585
0x18000158e  lea     eax, ds:2[rax*2]
0x180001595  jmp     short loc_1800015A1
0x180001597  lea     rcx, dword_18001E1D4
0x18000159e  mov     eax, r9d
0x1800015a1  mov     [rbp+90h+var_88], eax
0x1800015a4  mov     rax, [rbp+90h+arg_70]
0x1800015ab  mov     [rbp+90h+var_90], rcx
0x1800015af  mov     [rbp+90h+var_84], ebx
0x1800015b2  mov     rcx, [rax]
0x1800015b5  test    rcx, rcx
0x1800015b8  jz      short loc_1800015C9
0x1800015ba  mov     rax, rdx
0x1800015bd  inc     rax
0x1800015c0  cmp     [rcx+rax], bl
0x1800015c3  jnz     short loc_1800015BD
0x1800015c5  inc     eax
0x1800015c7  jmp     short loc_1800015CF
0x1800015c9  mov     rcx, rdi
0x1800015cc  mov     eax, r8d
0x1800015cf  mov     [rbp+90h+var_98], eax
0x1800015d2  mov     rax, [rbp+90h+arg_68]
0x1800015d9  mov     [rbp+90h+var_B0], rax
0x1800015dd  mov     rax, [rbp+90h+arg_60]
0x1800015e4  mov     [rbp+90h+var_A0], rcx
0x1800015e8  mov     [rbp+90h+var_94], ebx
0x1800015eb  mov     [rbp+90h+var_A8], 4
0x1800015f3  mov     rcx, [rax]
0x1800015f6  test    rcx, rcx
0x1800015f9  jz      short loc_18000160A
0x1800015fb  mov     rax, rdx
0x1800015fe  inc     rax
0x180001601  cmp     [rcx+rax], bl
0x180001604  jnz     short loc_1800015FE
0x180001606  inc     eax
0x180001608  jmp     short loc_180001610
0x18000160a  mov     rcx, rdi
0x18000160d  mov     eax, r8d
0x180001610  mov     [rbp+90h+var_B8], eax
0x180001613  mov     rax, [rbp+90h+arg_58]
0x18000161a  mov     [rbp+90h+var_D0], rax
0x18000161e  mov     rax, [rbp+90h+arg_50]
0x180001625  mov     [rbp+90h+var_C0], rcx
0x180001629  mov     [rbp+90h+var_B4], ebx
0x18000162c  mov     [rbp+90h+var_C8], 4
0x180001634  mov     rcx, [rax]
0x180001637  test    rcx, rcx
0x18000163a  jz      short loc_180001652
0x18000163c  mov     rax, rdx
0x18000163f  inc     rax
0x180001642  cmp     [rcx+rax*2], bx
0x180001646  jnz     short loc_18000163F
0x180001648  lea     r9d, ds:2[rax*2]
0x180001650  jmp     short loc_180001659
0x180001652  lea     rcx, dword_18001E1D4
0x180001659  mov     rax, [rbp+90h+arg_48]
0x180001660  mov     [rbp+90h+var_F0], rax
0x180001664  mov     rax, [rbp+90h+arg_40]
0x18000166b  mov     [rbp+90h+var_E0], rcx
0x18000166f  mov     [rbp+90h+var_D8], r9d
0x180001673  mov     [rbp+90h+var_D4], ebx
0x180001676  mov     rcx, [rax]
0x180001679  mov     [rbp+90h+var_E8], 4
0x180001681  test    rcx, rcx
0x180001684  jz      short loc_180001695
0x180001686  mov     rax, rdx
0x180001689  inc     rax
0x18000168c  cmp     [rcx+rax], bl
0x18000168f  jnz     short loc_180001689
0x180001691  inc     eax
0x180001693  jmp     short loc_18000169B
0x180001695  mov     rcx, rdi
0x180001698  mov     eax, r8d
0x18000169b  mov     [rbp+90h+var_F8], eax
0x18000169e  mov     rax, [rbp+90h+arg_38]
0x1800016a5  mov     [rbp+90h+var_110], rax
0x1800016a9  mov     rax, [rbp+90h+arg_30]
0x1800016b0  mov     [rbp+90h+var_100], rcx
0x1800016b4  mov     [rbp+90h+var_F4], ebx
0x1800016b7  mov     [rbp+90h+var_108], 4
0x1800016bf  mov     rcx, [rax]
0x1800016c2  test    rcx, rcx
0x1800016c5  jz      short loc_1800016D5
0x1800016c7  inc     rdx
0x1800016ca  cmp     [rcx+rdx], bl
0x1800016cd  jnz     short loc_1800016C7
0x1800016cf  lea     r8d, [rdx+1]
0x1800016d3  jmp     short loc_1800016D8
0x1800016d5  mov     rcx, rdi
0x1800016d8  mov     rax, [rbp+90h+arg_28]
0x1800016df  xor     r9d, r9d
0x1800016e2  mov     [rsp+190h+var_130], rax
0x1800016e7  mov     rdx, r11
0x1800016ea  mov     rax, [rbp+90h+arg_20]
0x1800016f1  mov     [rsp+190h+var_140], rax
0x1800016f6  lea     rax, [rsp+190h+var_160]
0x1800016fb  mov     [rsp+190h+var_120], rcx
0x180001700  mov     rcx, r10
0x180001703  mov     [rsp+190h+var_118], r8d
0x180001708  xor     r8d, r8d
0x18000170b  mov     [rsp+190h+var_168], rax
0x180001710  mov     [rsp+190h+var_170], 14h
0x180001718  mov     [rsp+190h+var_114], ebx
0x18000171c  mov     [rsp+190h+var_128], 4
0x180001725  mov     [rsp+190h+var_138], 8
0x18000172e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001733  mov     rcx, [rbp+90h+var_20]
0x180001737  xor     rcx, rsp; StackCookie
0x18000173a  call    __security_check_cookie
0x18000173f  mov     rbx, [rsp+190h+arg_10]
0x180001747  add     rsp, 180h
0x18000174e  pop     r14
0x180001750  pop     rdi
0x180001751  pop     rbp
0x180001752  retn
```
