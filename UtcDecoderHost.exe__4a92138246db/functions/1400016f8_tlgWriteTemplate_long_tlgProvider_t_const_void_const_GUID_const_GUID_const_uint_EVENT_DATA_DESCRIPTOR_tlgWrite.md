# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400016f8`
- end: `0x1400019e7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015924`

## callees

- `0x140001008`
- `0x1400016f8`
- `0x140008660`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
0x1400016f8  mov     [rsp-8+arg_10], rbx
0x1400016fd  push    rbp
0x1400016fe  push    rdi
0x1400016ff  push    r14
0x140001701  lea     rbp, [rsp-80h]
0x140001706  sub     rsp, 180h
0x14000170d  mov     rax, cs:__security_cookie
0x140001714  xor     rax, rsp
0x140001717  mov     [rbp+90h+var_20], rax
0x14000171b  mov     rax, [rbp+90h+arg_A8]
0x140001722  lea     rdi, byte_14001C467
0x140001729  mov     r11, rdx
0x14000172c  mov     r10, rcx
0x14000172f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001733  xor     ebx, ebx
0x140001735  mov     r8d, 1
0x14000173b  mov     rcx, [rax]
0x14000173e  test    rcx, rcx
0x140001741  jz      short loc_140001752
0x140001743  mov     rax, rdx
0x140001746  inc     rax
0x140001749  cmp     [rcx+rax], bl
0x14000174c  jnz     short loc_140001746
0x14000174e  inc     eax
0x140001750  jmp     short loc_140001758
0x140001752  mov     rcx, rdi
0x140001755  mov     eax, r8d
0x140001758  mov     [rbp+90h+var_28], eax
0x14000175b  mov     r9d, 2
0x140001761  mov     rax, [rbp+90h+arg_A0]
0x140001768  mov     [rbp+90h+var_40], rax
0x14000176c  mov     rax, [rbp+90h+arg_98]
0x140001773  mov     [rbp+90h+var_50], rax
0x140001777  mov     rax, [rbp+90h+arg_90]
0x14000177e  mov     [rbp+90h+var_30], rcx
0x140001782  mov     [rbp+90h+var_24], ebx
0x140001785  mov     [rbp+90h+var_38], 4
0x14000178d  mov     rcx, [rax]
0x140001790  mov     [rbp+90h+var_48], 4
0x140001798  test    rcx, rcx
0x14000179b  jz      short loc_1400017B2
0x14000179d  mov     rax, rdx
0x1400017a0  inc     rax
0x1400017a3  cmp     [rcx+rax*2], bx
0x1400017a7  jnz     short loc_1400017A0
0x1400017a9  lea     eax, ds:2[rax*2]
0x1400017b0  jmp     short loc_1400017BC
0x1400017b2  lea     rcx, qword_14001C468
0x1400017b9  mov     eax, r9d
0x1400017bc  mov     [rbp+90h+var_58], eax
0x1400017bf  mov     rax, [rbp+90h+arg_88]
0x1400017c6  mov     [rbp+90h+var_60], rcx
0x1400017ca  mov     [rbp+90h+var_54], ebx
0x1400017cd  mov     rcx, [rax]
0x1400017d0  test    rcx, rcx
0x1400017d3  jz      short loc_1400017E4
0x1400017d5  mov     rax, rdx
0x1400017d8  inc     rax
0x1400017db  cmp     [rcx+rax], bl
0x1400017de  jnz     short loc_1400017D8
0x1400017e0  inc     eax
0x1400017e2  jmp     short loc_1400017EA
0x1400017e4  mov     rcx, rdi
0x1400017e7  mov     eax, r8d
0x1400017ea  mov     [rbp+90h+var_68], eax
0x1400017ed  mov     rax, [rbp+90h+arg_80]
0x1400017f4  mov     [rbp+90h+var_80], rax
0x1400017f8  mov     rax, [rbp+90h+arg_78]
0x1400017ff  mov     [rbp+90h+var_70], rcx
0x140001803  mov     [rbp+90h+var_64], ebx
0x140001806  mov     [rbp+90h+var_78], 4
0x14000180e  mov     rcx, [rax]
0x140001811  test    rcx, rcx
0x140001814  jz      short loc_14000182B
0x140001816  mov     rax, rdx
0x140001819  inc     rax
0x14000181c  cmp     [rcx+rax*2], bx
0x140001820  jnz     short loc_140001819
0x140001822  lea     eax, ds:2[rax*2]
0x140001829  jmp     short loc_140001835
0x14000182b  lea     rcx, qword_14001C468
0x140001832  mov     eax, r9d
0x140001835  mov     [rbp+90h+var_88], eax
0x140001838  mov     rax, [rbp+90h+arg_70]
0x14000183f  mov     [rbp+90h+var_90], rcx
0x140001843  mov     [rbp+90h+var_84], ebx
0x140001846  mov     rcx, [rax]
0x140001849  test    rcx, rcx
0x14000184c  jz      short loc_14000185D
0x14000184e  mov     rax, rdx
0x140001851  inc     rax
0x140001854  cmp     [rcx+rax], bl
0x140001857  jnz     short loc_140001851
0x140001859  inc     eax
0x14000185b  jmp     short loc_140001863
0x14000185d  mov     rcx, rdi
0x140001860  mov     eax, r8d
0x140001863  mov     [rbp+90h+var_98], eax
0x140001866  mov     rax, [rbp+90h+arg_68]
0x14000186d  mov     [rbp+90h+var_B0], rax
0x140001871  mov     rax, [rbp+90h+arg_60]
0x140001878  mov     [rbp+90h+var_A0], rcx
0x14000187c  mov     [rbp+90h+var_94], ebx
0x14000187f  mov     [rbp+90h+var_A8], 4
0x140001887  mov     rcx, [rax]
0x14000188a  test    rcx, rcx
0x14000188d  jz      short loc_14000189E
0x14000188f  mov     rax, rdx
0x140001892  inc     rax
0x140001895  cmp     [rcx+rax], bl
0x140001898  jnz     short loc_140001892
0x14000189a  inc     eax
0x14000189c  jmp     short loc_1400018A4
0x14000189e  mov     rcx, rdi
0x1400018a1  mov     eax, r8d
0x1400018a4  mov     [rbp+90h+var_B8], eax
0x1400018a7  mov     rax, [rbp+90h+arg_58]
0x1400018ae  mov     [rbp+90h+var_D0], rax
0x1400018b2  mov     rax, [rbp+90h+arg_50]
0x1400018b9  mov     [rbp+90h+var_C0], rcx
0x1400018bd  mov     [rbp+90h+var_B4], ebx
0x1400018c0  mov     [rbp+90h+var_C8], 4
0x1400018c8  mov     rcx, [rax]
0x1400018cb  test    rcx, rcx
0x1400018ce  jz      short loc_1400018E6
0x1400018d0  mov     rax, rdx
0x1400018d3  inc     rax
0x1400018d6  cmp     [rcx+rax*2], bx
0x1400018da  jnz     short loc_1400018D3
0x1400018dc  lea     r9d, ds:2[rax*2]
0x1400018e4  jmp     short loc_1400018ED
0x1400018e6  lea     rcx, qword_14001C468
0x1400018ed  mov     rax, [rbp+90h+arg_48]
0x1400018f4  mov     [rbp+90h+var_F0], rax
0x1400018f8  mov     rax, [rbp+90h+arg_40]
0x1400018ff  mov     [rbp+90h+var_E0], rcx
0x140001903  mov     [rbp+90h+var_D8], r9d
0x140001907  mov     [rbp+90h+var_D4], ebx
0x14000190a  mov     rcx, [rax]
0x14000190d  mov     [rbp+90h+var_E8], 4
0x140001915  test    rcx, rcx
0x140001918  jz      short loc_140001929
0x14000191a  mov     rax, rdx
0x14000191d  inc     rax
0x140001920  cmp     [rcx+rax], bl
0x140001923  jnz     short loc_14000191D
0x140001925  inc     eax
0x140001927  jmp     short loc_14000192F
0x140001929  mov     rcx, rdi
0x14000192c  mov     eax, r8d
0x14000192f  mov     [rbp+90h+var_F8], eax
0x140001932  mov     rax, [rbp+90h+arg_38]
0x140001939  mov     [rbp+90h+var_110], rax
0x14000193d  mov     rax, [rbp+90h+arg_30]
0x140001944  mov     [rbp+90h+var_100], rcx
0x140001948  mov     [rbp+90h+var_F4], ebx
0x14000194b  mov     [rbp+90h+var_108], 4
0x140001953  mov     rcx, [rax]
0x140001956  test    rcx, rcx
0x140001959  jz      short loc_140001969
0x14000195b  inc     rdx
0x14000195e  cmp     [rcx+rdx], bl
0x140001961  jnz     short loc_14000195B
0x140001963  lea     r8d, [rdx+1]
0x140001967  jmp     short loc_14000196C
0x140001969  mov     rcx, rdi
0x14000196c  mov     rax, [rbp+90h+arg_28]
0x140001973  xor     r9d, r9d
0x140001976  mov     [rsp+190h+var_130], rax
0x14000197b  mov     rdx, r11
0x14000197e  mov     rax, [rbp+90h+arg_20]
0x140001985  mov     [rsp+190h+var_140], rax
0x14000198a  lea     rax, [rsp+190h+var_160]
0x14000198f  mov     [rsp+190h+var_120], rcx
0x140001994  mov     rcx, r10
0x140001997  mov     [rsp+190h+var_118], r8d
0x14000199c  xor     r8d, r8d
0x14000199f  mov     [rsp+190h+var_168], rax
0x1400019a4  mov     [rsp+190h+var_170], 14h
0x1400019ac  mov     [rsp+190h+var_114], ebx
0x1400019b0  mov     [rsp+190h+var_128], 4
0x1400019b9  mov     [rsp+190h+var_138], 8
0x1400019c2  call    _tlgWriteTransfer_EventWriteTransfer
0x1400019c7  mov     rcx, [rbp+90h+var_20]
0x1400019cb  xor     rcx, rsp; StackCookie
0x1400019ce  call    __security_check_cookie
0x1400019d3  mov     rbx, [rsp+190h+arg_10]
0x1400019db  add     rsp, 180h
0x1400019e2  pop     r14
0x1400019e4  pop     rdi
0x1400019e5  pop     rbp
0x1400019e6  retn
```
