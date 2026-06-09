# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001658`
- end: `0x180001947`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a678`

## callees

- `0x180001658`
- `0x180001a8c`
- `0x18000b640`

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
0x180001658  mov     [rsp-8+arg_10], rbx
0x18000165d  push    rbp
0x18000165e  push    rdi
0x18000165f  push    r14
0x180001661  lea     rbp, [rsp-80h]
0x180001666  sub     rsp, 180h
0x18000166d  mov     rax, cs:__security_cookie
0x180001674  xor     rax, rsp
0x180001677  mov     [rbp+90h+var_20], rax
0x18000167b  mov     rax, [rbp+90h+arg_A8]
0x180001682  lea     rdi, qword_18000F030
0x180001689  mov     r11, rdx
0x18000168c  mov     r10, rcx
0x18000168f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001693  xor     ebx, ebx
0x180001695  mov     r8d, 1
0x18000169b  mov     rcx, [rax]
0x18000169e  test    rcx, rcx
0x1800016a1  jz      short loc_1800016B2
0x1800016a3  mov     rax, rdx
0x1800016a6  inc     rax
0x1800016a9  cmp     [rcx+rax], bl
0x1800016ac  jnz     short loc_1800016A6
0x1800016ae  inc     eax
0x1800016b0  jmp     short loc_1800016B8
0x1800016b2  mov     rcx, rdi
0x1800016b5  mov     eax, r8d
0x1800016b8  mov     [rbp+90h+var_28], eax
0x1800016bb  mov     r9d, 2
0x1800016c1  mov     rax, [rbp+90h+arg_A0]
0x1800016c8  mov     [rbp+90h+var_40], rax
0x1800016cc  mov     rax, [rbp+90h+arg_98]
0x1800016d3  mov     [rbp+90h+var_50], rax
0x1800016d7  mov     rax, [rbp+90h+arg_90]
0x1800016de  mov     [rbp+90h+var_30], rcx
0x1800016e2  mov     [rbp+90h+var_24], ebx
0x1800016e5  mov     [rbp+90h+var_38], 4
0x1800016ed  mov     rcx, [rax]
0x1800016f0  mov     [rbp+90h+var_48], 4
0x1800016f8  test    rcx, rcx
0x1800016fb  jz      short loc_180001712
0x1800016fd  mov     rax, rdx
0x180001700  inc     rax
0x180001703  cmp     [rcx+rax*2], bx
0x180001707  jnz     short loc_180001700
0x180001709  lea     eax, ds:2[rax*2]
0x180001710  jmp     short loc_18000171C
0x180001712  lea     rcx, qword_18000F3D0
0x180001719  mov     eax, r9d
0x18000171c  mov     [rbp+90h+var_58], eax
0x18000171f  mov     rax, [rbp+90h+arg_88]
0x180001726  mov     [rbp+90h+var_60], rcx
0x18000172a  mov     [rbp+90h+var_54], ebx
0x18000172d  mov     rcx, [rax]
0x180001730  test    rcx, rcx
0x180001733  jz      short loc_180001744
0x180001735  mov     rax, rdx
0x180001738  inc     rax
0x18000173b  cmp     [rcx+rax], bl
0x18000173e  jnz     short loc_180001738
0x180001740  inc     eax
0x180001742  jmp     short loc_18000174A
0x180001744  mov     rcx, rdi
0x180001747  mov     eax, r8d
0x18000174a  mov     [rbp+90h+var_68], eax
0x18000174d  mov     rax, [rbp+90h+arg_80]
0x180001754  mov     [rbp+90h+var_80], rax
0x180001758  mov     rax, [rbp+90h+arg_78]
0x18000175f  mov     [rbp+90h+var_70], rcx
0x180001763  mov     [rbp+90h+var_64], ebx
0x180001766  mov     [rbp+90h+var_78], 4
0x18000176e  mov     rcx, [rax]
0x180001771  test    rcx, rcx
0x180001774  jz      short loc_18000178B
0x180001776  mov     rax, rdx
0x180001779  inc     rax
0x18000177c  cmp     [rcx+rax*2], bx
0x180001780  jnz     short loc_180001779
0x180001782  lea     eax, ds:2[rax*2]
0x180001789  jmp     short loc_180001795
0x18000178b  lea     rcx, qword_18000F3D0
0x180001792  mov     eax, r9d
0x180001795  mov     [rbp+90h+var_88], eax
0x180001798  mov     rax, [rbp+90h+arg_70]
0x18000179f  mov     [rbp+90h+var_90], rcx
0x1800017a3  mov     [rbp+90h+var_84], ebx
0x1800017a6  mov     rcx, [rax]
0x1800017a9  test    rcx, rcx
0x1800017ac  jz      short loc_1800017BD
0x1800017ae  mov     rax, rdx
0x1800017b1  inc     rax
0x1800017b4  cmp     [rcx+rax], bl
0x1800017b7  jnz     short loc_1800017B1
0x1800017b9  inc     eax
0x1800017bb  jmp     short loc_1800017C3
0x1800017bd  mov     rcx, rdi
0x1800017c0  mov     eax, r8d
0x1800017c3  mov     [rbp+90h+var_98], eax
0x1800017c6  mov     rax, [rbp+90h+arg_68]
0x1800017cd  mov     [rbp+90h+var_B0], rax
0x1800017d1  mov     rax, [rbp+90h+arg_60]
0x1800017d8  mov     [rbp+90h+var_A0], rcx
0x1800017dc  mov     [rbp+90h+var_94], ebx
0x1800017df  mov     [rbp+90h+var_A8], 4
0x1800017e7  mov     rcx, [rax]
0x1800017ea  test    rcx, rcx
0x1800017ed  jz      short loc_1800017FE
0x1800017ef  mov     rax, rdx
0x1800017f2  inc     rax
0x1800017f5  cmp     [rcx+rax], bl
0x1800017f8  jnz     short loc_1800017F2
0x1800017fa  inc     eax
0x1800017fc  jmp     short loc_180001804
0x1800017fe  mov     rcx, rdi
0x180001801  mov     eax, r8d
0x180001804  mov     [rbp+90h+var_B8], eax
0x180001807  mov     rax, [rbp+90h+arg_58]
0x18000180e  mov     [rbp+90h+var_D0], rax
0x180001812  mov     rax, [rbp+90h+arg_50]
0x180001819  mov     [rbp+90h+var_C0], rcx
0x18000181d  mov     [rbp+90h+var_B4], ebx
0x180001820  mov     [rbp+90h+var_C8], 4
0x180001828  mov     rcx, [rax]
0x18000182b  test    rcx, rcx
0x18000182e  jz      short loc_180001846
0x180001830  mov     rax, rdx
0x180001833  inc     rax
0x180001836  cmp     [rcx+rax*2], bx
0x18000183a  jnz     short loc_180001833
0x18000183c  lea     r9d, ds:2[rax*2]
0x180001844  jmp     short loc_18000184D
0x180001846  lea     rcx, qword_18000F3D0
0x18000184d  mov     rax, [rbp+90h+arg_48]
0x180001854  mov     [rbp+90h+var_F0], rax
0x180001858  mov     rax, [rbp+90h+arg_40]
0x18000185f  mov     [rbp+90h+var_E0], rcx
0x180001863  mov     [rbp+90h+var_D8], r9d
0x180001867  mov     [rbp+90h+var_D4], ebx
0x18000186a  mov     rcx, [rax]
0x18000186d  mov     [rbp+90h+var_E8], 4
0x180001875  test    rcx, rcx
0x180001878  jz      short loc_180001889
0x18000187a  mov     rax, rdx
0x18000187d  inc     rax
0x180001880  cmp     [rcx+rax], bl
0x180001883  jnz     short loc_18000187D
0x180001885  inc     eax
0x180001887  jmp     short loc_18000188F
0x180001889  mov     rcx, rdi
0x18000188c  mov     eax, r8d
0x18000188f  mov     [rbp+90h+var_F8], eax
0x180001892  mov     rax, [rbp+90h+arg_38]
0x180001899  mov     [rbp+90h+var_110], rax
0x18000189d  mov     rax, [rbp+90h+arg_30]
0x1800018a4  mov     [rbp+90h+var_100], rcx
0x1800018a8  mov     [rbp+90h+var_F4], ebx
0x1800018ab  mov     [rbp+90h+var_108], 4
0x1800018b3  mov     rcx, [rax]
0x1800018b6  test    rcx, rcx
0x1800018b9  jz      short loc_1800018C9
0x1800018bb  inc     rdx
0x1800018be  cmp     [rcx+rdx], bl
0x1800018c1  jnz     short loc_1800018BB
0x1800018c3  lea     r8d, [rdx+1]
0x1800018c7  jmp     short loc_1800018CC
0x1800018c9  mov     rcx, rdi
0x1800018cc  mov     rax, [rbp+90h+arg_28]
0x1800018d3  xor     r9d, r9d
0x1800018d6  mov     [rsp+190h+var_130], rax
0x1800018db  mov     rdx, r11
0x1800018de  mov     rax, [rbp+90h+arg_20]
0x1800018e5  mov     [rsp+190h+var_140], rax
0x1800018ea  lea     rax, [rsp+190h+var_160]
0x1800018ef  mov     [rsp+190h+var_120], rcx
0x1800018f4  mov     rcx, r10
0x1800018f7  mov     [rsp+190h+var_118], r8d
0x1800018fc  xor     r8d, r8d
0x1800018ff  mov     [rsp+190h+var_168], rax
0x180001904  mov     [rsp+190h+var_170], 14h
0x18000190c  mov     [rsp+190h+var_114], ebx
0x180001910  mov     [rsp+190h+var_128], 4
0x180001919  mov     [rsp+190h+var_138], 8
0x180001922  call    _tlgWriteTransfer_EventWriteTransfer
0x180001927  mov     rcx, [rbp+90h+var_20]
0x18000192b  xor     rcx, rsp; StackCookie
0x18000192e  call    __security_check_cookie
0x180001933  mov     rbx, [rsp+190h+arg_10]
0x18000193b  add     rsp, 180h
0x180001942  pop     r14
0x180001944  pop     rdi
0x180001945  pop     rbp
0x180001946  retn
```
