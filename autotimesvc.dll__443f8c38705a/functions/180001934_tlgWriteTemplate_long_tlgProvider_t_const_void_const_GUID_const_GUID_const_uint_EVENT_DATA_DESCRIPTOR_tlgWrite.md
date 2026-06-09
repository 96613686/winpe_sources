# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001934`
- end: `0x180001c3a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `774`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d720`

## callees

- `0x180001054`
- `0x180001934`
- `0x180002a70`

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
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001934  mov     [rsp-8+arg_0], rbx
0x180001939  mov     [rsp-8+arg_10], rsi
0x18000193e  push    rbp
0x18000193f  lea     rbp, [rsp-80h]
0x180001944  sub     rsp, 180h
0x18000194b  mov     rax, cs:__security_cookie
0x180001952  xor     rax, rsp
0x180001955  mov     [rbp+80h+var_10], rax
0x180001959  mov     rax, [rbp+80h+arg_A8]
0x180001960  lea     rbx, byte_1800150A8
0x180001967  mov     r10, rdx
0x18000196a  xor     r11d, r11d
0x18000196d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001971  mov     r8d, 1
0x180001977  mov     rcx, [rax]
0x18000197a  test    rcx, rcx
0x18000197d  jz      short loc_18000198F
0x18000197f  mov     rax, rdx
0x180001982  inc     rax
0x180001985  cmp     [rcx+rax], r11b
0x180001989  jnz     short loc_180001982
0x18000198b  inc     eax
0x18000198d  jmp     short loc_180001995
0x18000198f  mov     rcx, rbx
0x180001992  mov     eax, r8d
0x180001995  mov     [rbp+80h+var_18], eax
0x180001998  mov     r9d, 2
0x18000199e  mov     rax, [rbp+80h+arg_A0]
0x1800019a5  mov     [rbp+80h+var_30], rax
0x1800019a9  mov     rax, [rbp+80h+arg_98]
0x1800019b0  mov     [rbp+80h+var_40], rax
0x1800019b4  mov     rax, [rbp+80h+arg_90]
0x1800019bb  mov     [rbp+80h+var_20], rcx
0x1800019bf  mov     [rbp+80h+var_14], r11d
0x1800019c3  mov     [rbp+80h+var_28], 4
0x1800019cb  mov     rcx, [rax]
0x1800019ce  mov     [rbp+80h+var_38], 4
0x1800019d6  test    rcx, rcx
0x1800019d9  jz      short loc_1800019F1
0x1800019db  mov     rax, rdx
0x1800019de  inc     rax
0x1800019e1  cmp     [rcx+rax*2], r11w
0x1800019e6  jnz     short loc_1800019DE
0x1800019e8  lea     eax, ds:2[rax*2]
0x1800019ef  jmp     short loc_1800019FB
0x1800019f1  lea     rcx, dword_1800150AC
0x1800019f8  mov     eax, r9d
0x1800019fb  mov     [rbp+80h+var_48], eax
0x1800019fe  mov     rax, [rbp+80h+arg_88]
0x180001a05  mov     [rbp+80h+var_50], rcx
0x180001a09  mov     [rbp+80h+var_44], r11d
0x180001a0d  mov     rcx, [rax]
0x180001a10  test    rcx, rcx
0x180001a13  jz      short loc_180001A25
0x180001a15  mov     rax, rdx
0x180001a18  inc     rax
0x180001a1b  cmp     [rcx+rax], r11b
0x180001a1f  jnz     short loc_180001A18
0x180001a21  inc     eax
0x180001a23  jmp     short loc_180001A2B
0x180001a25  mov     rcx, rbx
0x180001a28  mov     eax, r8d
0x180001a2b  mov     [rbp+80h+var_58], eax
0x180001a2e  mov     rax, [rbp+80h+arg_80]
0x180001a35  mov     [rbp+80h+var_70], rax
0x180001a39  mov     rax, [rbp+80h+arg_78]
0x180001a40  mov     [rbp+80h+var_60], rcx
0x180001a44  mov     [rbp+80h+var_54], r11d
0x180001a48  mov     [rbp+80h+var_68], 4
0x180001a50  mov     rcx, [rax]
0x180001a53  test    rcx, rcx
0x180001a56  jz      short loc_180001A6E
0x180001a58  mov     rax, rdx
0x180001a5b  inc     rax
0x180001a5e  cmp     [rcx+rax*2], r11w
0x180001a63  jnz     short loc_180001A5B
0x180001a65  lea     eax, ds:2[rax*2]
0x180001a6c  jmp     short loc_180001A78
0x180001a6e  lea     rcx, dword_1800150AC
0x180001a75  mov     eax, r9d
0x180001a78  mov     [rbp+80h+var_78], eax
0x180001a7b  mov     rax, [rbp+80h+arg_70]
0x180001a82  mov     [rbp+80h+var_80], rcx
0x180001a86  mov     [rbp+80h+var_74], r11d
0x180001a8a  mov     rcx, [rax]
0x180001a8d  test    rcx, rcx
0x180001a90  jz      short loc_180001AA2
0x180001a92  mov     rax, rdx
0x180001a95  inc     rax
0x180001a98  cmp     [rcx+rax], r11b
0x180001a9c  jnz     short loc_180001A95
0x180001a9e  inc     eax
0x180001aa0  jmp     short loc_180001AA8
0x180001aa2  mov     rcx, rbx
0x180001aa5  mov     eax, r8d
0x180001aa8  mov     [rbp+80h+var_88], eax
0x180001aab  mov     rax, [rbp+80h+arg_68]
0x180001ab2  mov     [rbp+80h+var_A0], rax
0x180001ab6  mov     rax, [rbp+80h+arg_60]
0x180001abd  mov     [rbp+80h+var_90], rcx
0x180001ac1  mov     [rbp+80h+var_84], r11d
0x180001ac5  mov     [rbp+80h+var_98], 4
0x180001acd  mov     rcx, [rax]
0x180001ad0  test    rcx, rcx
0x180001ad3  jz      short loc_180001AE5
0x180001ad5  mov     rax, rdx
0x180001ad8  inc     rax
0x180001adb  cmp     [rcx+rax], r11b
0x180001adf  jnz     short loc_180001AD8
0x180001ae1  inc     eax
0x180001ae3  jmp     short loc_180001AEB
0x180001ae5  mov     rcx, rbx
0x180001ae8  mov     eax, r8d
0x180001aeb  mov     [rbp+80h+var_A8], eax
0x180001aee  mov     rax, [rbp+80h+arg_58]
0x180001af5  mov     [rbp+80h+var_C0], rax
0x180001af9  mov     rax, [rbp+80h+arg_50]
0x180001b00  mov     [rbp+80h+var_B0], rcx
0x180001b04  mov     [rbp+80h+var_A4], r11d
0x180001b08  mov     [rbp+80h+var_B8], 4
0x180001b10  mov     rcx, [rax]
0x180001b13  test    rcx, rcx
0x180001b16  jz      short loc_180001B2F
0x180001b18  mov     rax, rdx
0x180001b1b  inc     rax
0x180001b1e  cmp     [rcx+rax*2], r11w
0x180001b23  jnz     short loc_180001B1B
0x180001b25  lea     r9d, ds:2[rax*2]
0x180001b2d  jmp     short loc_180001B36
0x180001b2f  lea     rcx, dword_1800150AC
0x180001b36  mov     rax, [rbp+80h+arg_48]
0x180001b3d  mov     [rbp+80h+var_E0], rax
0x180001b41  mov     rax, [rbp+80h+arg_40]
0x180001b48  mov     [rbp+80h+var_D0], rcx
0x180001b4c  mov     [rbp+80h+var_C8], r9d
0x180001b50  mov     [rbp+80h+var_C4], r11d
0x180001b54  mov     rcx, [rax]
0x180001b57  mov     [rbp+80h+var_D8], 4
0x180001b5f  test    rcx, rcx
0x180001b62  jz      short loc_180001B74
0x180001b64  mov     rax, rdx
0x180001b67  inc     rax
0x180001b6a  cmp     [rcx+rax], r11b
0x180001b6e  jnz     short loc_180001B67
0x180001b70  inc     eax
0x180001b72  jmp     short loc_180001B7A
0x180001b74  mov     rcx, rbx
0x180001b77  mov     eax, r8d
0x180001b7a  mov     [rbp+80h+var_E8], eax
0x180001b7d  mov     rax, [rbp+80h+arg_38]
0x180001b84  mov     [rbp+80h+var_100], rax
0x180001b88  mov     rax, [rbp+80h+arg_30]
0x180001b8f  mov     [rbp+80h+var_F0], rcx
0x180001b93  mov     [rbp+80h+var_E4], r11d
0x180001b97  mov     [rbp+80h+var_F8], 4
0x180001b9f  mov     rcx, [rax]
0x180001ba2  test    rcx, rcx
0x180001ba5  jz      short loc_180001BB6
0x180001ba7  inc     rdx
0x180001baa  cmp     [rcx+rdx], r11b
0x180001bae  jnz     short loc_180001BA7
0x180001bb0  lea     r8d, [rdx+1]
0x180001bb4  jmp     short loc_180001BB9
0x180001bb6  mov     rcx, rbx
0x180001bb9  mov     rax, [rbp+80h+arg_28]
0x180001bc0  xor     r9d, r9d
0x180001bc3  mov     [rsp+180h+var_120], rax
0x180001bc8  mov     rdx, r10
0x180001bcb  mov     rax, [rbp+80h+arg_20]
0x180001bd2  mov     [rsp+180h+var_130], rax
0x180001bd7  lea     rax, [rsp+180h+var_150]
0x180001bdc  mov     [rsp+180h+var_110], rcx
0x180001be1  lea     rcx, dword_18001C010
0x180001be8  mov     [rsp+180h+var_108], r8d
0x180001bed  xor     r8d, r8d
0x180001bf0  mov     [rsp+180h+var_158], rax
0x180001bf5  mov     [rsp+180h+var_160], 14h
0x180001bfd  mov     [rsp+180h+var_104], r11d
0x180001c02  mov     [rsp+180h+var_118], 4
0x180001c0b  mov     [rsp+180h+var_128], 8
0x180001c14  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c19  mov     rcx, [rbp+80h+var_10]
0x180001c1d  xor     rcx, rsp; StackCookie
0x180001c20  call    __security_check_cookie
0x180001c25  lea     r11, [rsp+180h+var_s0]
0x180001c2d  mov     rbx, [r11+10h]
0x180001c31  mov     rsi, [r11+20h]
0x180001c35  mov     rsp, r11
0x180001c38  pop     rbp
0x180001c39  retn
```
