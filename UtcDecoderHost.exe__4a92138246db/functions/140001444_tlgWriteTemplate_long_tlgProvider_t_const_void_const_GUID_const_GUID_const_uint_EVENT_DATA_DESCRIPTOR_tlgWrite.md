# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x140001444`
- end: `0x1400016ef`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400157bc`

## callees

- `0x140001008`
- `0x140001444`
- `0x140008660`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        _QWORD *a14,
        __int64 a15,
        _QWORD *a16,
        _QWORD *a17,
        __int64 a18,
        _QWORD *a19,
        _QWORD *a20)
{
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax

  v21 = -1;
  if ( *a20 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*a20 + 2 * v22) );
  }
  if ( *a19 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(*a19 + v23) );
  }
  if ( *a17 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a17 + 2 * v24) );
  }
  if ( *a16 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(*a16 + v25) );
  }
  if ( *a14 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a14 + v26) );
  }
  if ( *a12 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a12 + 2 * v27) );
  }
  if ( *a10 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a10 + v28) );
  }
  if ( *a8 )
  {
    do
      ++v21;
    while ( *(_BYTE *)(*a8 + v21) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x140001444  mov     [rsp-8+arg_10], rbx
0x140001449  push    rbp
0x14000144a  push    rsi
0x14000144b  push    rdi
0x14000144c  lea     rbp, [rsp-60h]
0x140001451  sub     rsp, 160h
0x140001458  mov     rax, cs:__security_cookie
0x14000145f  xor     rax, rsp
0x140001462  mov     [rbp+70h+var_20], rax
0x140001466  mov     rax, [rbp+70h+arg_98]
0x14000146d  mov     r11, rdx
0x140001470  mov     r10, rcx
0x140001473  xor     ebx, ebx
0x140001475  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001479  mov     r9d, 2
0x14000147f  mov     rdx, [rax]
0x140001482  test    rdx, rdx
0x140001485  jz      short loc_14000149C
0x140001487  mov     rax, rcx
0x14000148a  inc     rax
0x14000148d  cmp     [rdx+rax*2], bx
0x140001491  jnz     short loc_14000148A
0x140001493  lea     eax, ds:2[rax*2]
0x14000149a  jmp     short loc_1400014A6
0x14000149c  lea     rdx, qword_14001C468
0x1400014a3  mov     eax, r9d
0x1400014a6  mov     [rbp+70h+var_28], eax
0x1400014a9  lea     rdi, byte_14001C467
0x1400014b0  mov     rax, [rbp+70h+arg_90]
0x1400014b7  mov     r8d, 1
0x1400014bd  mov     [rbp+70h+var_30], rdx
0x1400014c1  mov     [rbp+70h+var_24], ebx
0x1400014c4  mov     rdx, [rax]
0x1400014c7  test    rdx, rdx
0x1400014ca  jz      short loc_1400014DB
0x1400014cc  mov     rax, rcx
0x1400014cf  inc     rax
0x1400014d2  cmp     [rdx+rax], bl
0x1400014d5  jnz     short loc_1400014CF
0x1400014d7  inc     eax
0x1400014d9  jmp     short loc_1400014E1
0x1400014db  mov     rdx, rdi
0x1400014de  mov     eax, r8d
0x1400014e1  mov     [rbp+70h+var_38], eax
0x1400014e4  mov     rax, [rbp+70h+arg_88]
0x1400014eb  mov     [rbp+70h+var_50], rax
0x1400014ef  mov     rax, [rbp+70h+arg_80]
0x1400014f6  mov     [rbp+70h+var_40], rdx
0x1400014fa  mov     [rbp+70h+var_34], ebx
0x1400014fd  mov     [rbp+70h+var_48], 4
0x140001505  mov     rdx, [rax]
0x140001508  test    rdx, rdx
0x14000150b  jz      short loc_140001522
0x14000150d  mov     rax, rcx
0x140001510  inc     rax
0x140001513  cmp     [rdx+rax*2], bx
0x140001517  jnz     short loc_140001510
0x140001519  lea     eax, ds:2[rax*2]
0x140001520  jmp     short loc_14000152C
0x140001522  lea     rdx, qword_14001C468
0x140001529  mov     eax, r9d
0x14000152c  mov     [rbp+70h+var_58], eax
0x14000152f  mov     rax, [rbp+70h+arg_78]
0x140001536  mov     [rbp+70h+var_60], rdx
0x14000153a  mov     [rbp+70h+var_54], ebx
0x14000153d  mov     rdx, [rax]
0x140001540  test    rdx, rdx
0x140001543  jz      short loc_140001554
0x140001545  mov     rax, rcx
0x140001548  inc     rax
0x14000154b  cmp     [rdx+rax], bl
0x14000154e  jnz     short loc_140001548
0x140001550  inc     eax
0x140001552  jmp     short loc_14000155A
0x140001554  mov     rdx, rdi
0x140001557  mov     eax, r8d
0x14000155a  mov     [rbp+70h+var_68], eax
0x14000155d  mov     rax, [rbp+70h+arg_70]
0x140001564  mov     [rbp+70h+var_80], rax
0x140001568  mov     rax, [rbp+70h+arg_68]
0x14000156f  mov     [rbp+70h+var_70], rdx
0x140001573  mov     [rbp+70h+var_64], ebx
0x140001576  mov     [rbp+70h+var_78], 4
0x14000157e  mov     rdx, [rax]
0x140001581  test    rdx, rdx
0x140001584  jz      short loc_140001595
0x140001586  mov     rax, rcx
0x140001589  inc     rax
0x14000158c  cmp     [rdx+rax], bl
0x14000158f  jnz     short loc_140001589
0x140001591  inc     eax
0x140001593  jmp     short loc_14000159B
0x140001595  mov     rdx, rdi
0x140001598  mov     eax, r8d
0x14000159b  mov     [rbp+70h+var_88], eax
0x14000159e  mov     rax, [rbp+70h+arg_60]
0x1400015a5  mov     [rbp+70h+var_A0], rax
0x1400015a9  mov     rax, [rbp+70h+arg_58]
0x1400015b0  mov     [rbp+70h+var_90], rdx
0x1400015b4  mov     [rbp+70h+var_84], ebx
0x1400015b7  mov     [rbp+70h+var_98], 4
0x1400015bf  mov     rdx, [rax]
0x1400015c2  test    rdx, rdx
0x1400015c5  jz      short loc_1400015DD
0x1400015c7  mov     rax, rcx
0x1400015ca  inc     rax
0x1400015cd  cmp     [rdx+rax*2], bx
0x1400015d1  jnz     short loc_1400015CA
0x1400015d3  lea     r9d, ds:2[rax*2]
0x1400015db  jmp     short loc_1400015E4
0x1400015dd  lea     rdx, qword_14001C468
0x1400015e4  mov     rax, [rbp+70h+arg_50]
0x1400015eb  mov     [rbp+70h+var_C0], rax
0x1400015ef  mov     rax, [rbp+70h+arg_48]
0x1400015f6  mov     [rbp+70h+var_B0], rdx
0x1400015fa  mov     [rbp+70h+var_A8], r9d
0x1400015fe  mov     [rbp+70h+var_A4], ebx
0x140001601  mov     rdx, [rax]
0x140001604  mov     [rbp+70h+var_B8], 4
0x14000160c  test    rdx, rdx
0x14000160f  jz      short loc_140001620
0x140001611  mov     rax, rcx
0x140001614  inc     rax
0x140001617  cmp     [rdx+rax], bl
0x14000161a  jnz     short loc_140001614
0x14000161c  inc     eax
0x14000161e  jmp     short loc_140001626
0x140001620  mov     rdx, rdi
0x140001623  mov     eax, r8d
0x140001626  mov     [rbp+70h+var_C8], eax
0x140001629  mov     rax, [rbp+70h+arg_40]
0x140001630  mov     [rbp+70h+var_E0], rax
0x140001634  mov     rax, [rbp+70h+arg_38]
0x14000163b  mov     [rbp+70h+var_D0], rdx
0x14000163f  mov     [rbp+70h+var_C4], ebx
0x140001642  mov     [rbp+70h+var_D8], 4
0x14000164a  mov     rdx, [rax]
0x14000164d  test    rdx, rdx
0x140001650  jz      short loc_140001660
0x140001652  inc     rcx
0x140001655  cmp     [rdx+rcx], bl
0x140001658  jnz     short loc_140001652
0x14000165a  lea     r8d, [rcx+1]
0x14000165e  jmp     short loc_140001663
0x140001660  mov     rdx, rdi
0x140001663  mov     rax, [rbp+70h+arg_30]
0x14000166a  xor     r9d, r9d
0x14000166d  mov     [rsp+170h+var_100], rax
0x140001672  mov     rcx, r10
0x140001675  mov     rax, [rbp+70h+arg_28]
0x14000167c  mov     [rsp+170h+var_110], rax
0x140001681  mov     rax, [rbp+70h+arg_20]
0x140001688  mov     [rsp+170h+var_120], rax
0x14000168d  lea     rax, [rsp+170h+var_140]
0x140001692  mov     [rbp+70h+var_F0], rdx
0x140001696  mov     rdx, r11
0x140001699  mov     [rbp+70h+var_E8], r8d
0x14000169d  xor     r8d, r8d
0x1400016a0  mov     [rsp+170h+var_148], rax
0x1400016a5  mov     [rsp+170h+var_150], 12h
0x1400016ad  mov     [rbp+70h+var_E4], ebx
0x1400016b0  mov     [rsp+170h+var_F8], 4
0x1400016b9  mov     [rsp+170h+var_108], 8
0x1400016c2  mov     [rsp+170h+var_118], 8
0x1400016cb  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016d0  mov     rcx, [rbp+70h+var_20]
0x1400016d4  xor     rcx, rsp; StackCookie
0x1400016d7  call    __security_check_cookie
0x1400016dc  mov     rbx, [rsp+170h+arg_10]
0x1400016e4  add     rsp, 160h
0x1400016eb  pop     rdi
0x1400016ec  pop     rsi
0x1400016ed  pop     rbp
0x1400016ee  retn
```
