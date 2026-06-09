# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400010a8`
- end: `0x14000137a`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013cd0`

## callees

- `0x140001008`
- `0x1400010a8`
- `0x140008660`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14,
        __int64 a15,
        _QWORD *a16,
        _QWORD *a17,
        _QWORD *a18,
        _QWORD *a19,
        __int64 a20,
        _QWORD *a21)
{
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax

  v22 = -1;
  if ( *a21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(*a21 + v23) );
  }
  if ( *a19 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_BYTE *)(*a19 + v24) );
  }
  if ( *a18 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(*a18 + v25) );
  }
  if ( *a17 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a17 + v26) );
  }
  if ( *a16 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_BYTE *)(*a16 + v27) );
  }
  if ( *a14 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a14 + v28) );
  }
  if ( *a13 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(*a13 + v29) );
  }
  if ( *a12 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_BYTE *)(*a12 + v30) );
  }
  if ( *a10 )
  {
    do
      ++v22;
    while ( *(_BYTE *)(*a10 + v22) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1400010a8  mov     [rsp-8+arg_10], rbx
0x1400010ad  mov     [rsp-8+arg_18], rsi
0x1400010b2  push    rbp
0x1400010b3  lea     rbp, [rsp-80h]
0x1400010b8  sub     rsp, 180h
0x1400010bf  mov     rax, cs:__security_cookie
0x1400010c6  xor     rax, rsp
0x1400010c9  mov     [rbp+80h+var_10], rax
0x1400010cd  mov     rax, [rbp+80h+arg_A8]
0x1400010d4  lea     rbx, byte_14001C467
0x1400010db  xor     r9d, r9d
0x1400010de  mov     [rbp+80h+var_20], rax
0x1400010e2  mov     rax, [rbp+80h+arg_A0]
0x1400010e9  mov     r10, rcx
0x1400010ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400010f0  mov     [rbp+80h+var_18], 4
0x1400010f8  mov     r11, rdx
0x1400010fb  lea     edx, [r9+1]
0x1400010ff  mov     r8, [rax]
0x140001102  test    r8, r8
0x140001105  jz      short loc_140001117
0x140001107  mov     rax, rcx
0x14000110a  inc     rax
0x14000110d  cmp     [r8+rax], r9b
0x140001111  jnz     short loc_14000110A
0x140001113  inc     eax
0x140001115  jmp     short loc_14000111C
0x140001117  mov     r8, rbx
0x14000111a  mov     eax, edx
0x14000111c  mov     [rbp+80h+var_28], eax
0x14000111f  mov     rax, [rbp+80h+arg_98]
0x140001126  mov     [rbp+80h+var_40], rax
0x14000112a  mov     rax, [rbp+80h+arg_90]
0x140001131  mov     [rbp+80h+var_30], r8
0x140001135  mov     [rbp+80h+var_24], r9d
0x140001139  mov     [rbp+80h+var_38], 4
0x140001141  mov     r8, [rax]
0x140001144  test    r8, r8
0x140001147  jz      short loc_140001159
0x140001149  mov     rax, rcx
0x14000114c  inc     rax
0x14000114f  cmp     [r8+rax], r9b
0x140001153  jnz     short loc_14000114C
0x140001155  inc     eax
0x140001157  jmp     short loc_14000115E
0x140001159  mov     r8, rbx
0x14000115c  mov     eax, edx
0x14000115e  mov     [rbp+80h+var_48], eax
0x140001161  mov     rax, [rbp+80h+arg_88]
0x140001168  mov     [rbp+80h+var_50], r8
0x14000116c  mov     [rbp+80h+var_44], r9d
0x140001170  mov     r8, [rax]
0x140001173  test    r8, r8
0x140001176  jz      short loc_140001188
0x140001178  mov     rax, rcx
0x14000117b  inc     rax
0x14000117e  cmp     [r8+rax], r9b
0x140001182  jnz     short loc_14000117B
0x140001184  inc     eax
0x140001186  jmp     short loc_14000118D
0x140001188  mov     r8, rbx
0x14000118b  mov     eax, edx
0x14000118d  mov     [rbp+80h+var_58], eax
0x140001190  mov     rax, [rbp+80h+arg_80]
0x140001197  mov     [rbp+80h+var_60], r8
0x14000119b  mov     [rbp+80h+var_54], r9d
0x14000119f  mov     r8, [rax]
0x1400011a2  test    r8, r8
0x1400011a5  jz      short loc_1400011B7
0x1400011a7  mov     rax, rcx
0x1400011aa  inc     rax
0x1400011ad  cmp     [r8+rax], r9b
0x1400011b1  jnz     short loc_1400011AA
0x1400011b3  inc     eax
0x1400011b5  jmp     short loc_1400011BC
0x1400011b7  mov     r8, rbx
0x1400011ba  mov     eax, edx
0x1400011bc  mov     [rbp+80h+var_68], eax
0x1400011bf  mov     rax, [rbp+80h+arg_78]
0x1400011c6  mov     [rbp+80h+var_70], r8
0x1400011ca  mov     [rbp+80h+var_64], r9d
0x1400011ce  mov     r8, [rax]
0x1400011d1  test    r8, r8
0x1400011d4  jz      short loc_1400011E6
0x1400011d6  mov     rax, rcx
0x1400011d9  inc     rax
0x1400011dc  cmp     [r8+rax], r9b
0x1400011e0  jnz     short loc_1400011D9
0x1400011e2  inc     eax
0x1400011e4  jmp     short loc_1400011EB
0x1400011e6  mov     r8, rbx
0x1400011e9  mov     eax, edx
0x1400011eb  mov     [rbp+80h+var_78], eax
0x1400011ee  mov     rax, [rbp+80h+arg_70]
0x1400011f5  mov     [rbp+80h+var_90], rax
0x1400011f9  mov     rax, [rbp+80h+arg_68]
0x140001200  mov     [rbp+80h+var_80], r8
0x140001204  mov     [rbp+80h+var_74], r9d
0x140001208  mov     [rbp+80h+var_88], 2
0x140001210  mov     r8, [rax]
0x140001213  test    r8, r8
0x140001216  jz      short loc_140001228
0x140001218  mov     rax, rcx
0x14000121b  inc     rax
0x14000121e  cmp     [r8+rax], r9b
0x140001222  jnz     short loc_14000121B
0x140001224  inc     eax
0x140001226  jmp     short loc_14000122D
0x140001228  mov     r8, rbx
0x14000122b  mov     eax, edx
0x14000122d  mov     [rbp+80h+var_98], eax
0x140001230  mov     rax, [rbp+80h+arg_60]
0x140001237  mov     [rbp+80h+var_A0], r8
0x14000123b  mov     [rbp+80h+var_94], r9d
0x14000123f  mov     r8, [rax]
0x140001242  test    r8, r8
0x140001245  jz      short loc_140001257
0x140001247  mov     rax, rcx
0x14000124a  inc     rax
0x14000124d  cmp     [r8+rax], r9b
0x140001251  jnz     short loc_14000124A
0x140001253  inc     eax
0x140001255  jmp     short loc_14000125C
0x140001257  mov     r8, rbx
0x14000125a  mov     eax, edx
0x14000125c  mov     [rbp+80h+var_A8], eax
0x14000125f  mov     rax, [rbp+80h+arg_58]
0x140001266  mov     [rbp+80h+var_B0], r8
0x14000126a  mov     [rbp+80h+var_A4], r9d
0x14000126e  mov     r8, [rax]
0x140001271  test    r8, r8
0x140001274  jz      short loc_140001286
0x140001276  mov     rax, rcx
0x140001279  inc     rax
0x14000127c  cmp     [r8+rax], r9b
0x140001280  jnz     short loc_140001279
0x140001282  inc     eax
0x140001284  jmp     short loc_14000128B
0x140001286  mov     r8, rbx
0x140001289  mov     eax, edx
0x14000128b  mov     [rbp+80h+var_B8], eax
0x14000128e  mov     rax, [rbp+80h+arg_50]
0x140001295  mov     [rbp+80h+var_D0], rax
0x140001299  mov     rax, [rbp+80h+arg_48]
0x1400012a0  mov     [rbp+80h+var_C0], r8
0x1400012a4  mov     [rbp+80h+var_B4], r9d
0x1400012a8  mov     [rbp+80h+var_C8], 2
0x1400012b0  mov     r8, [rax]
0x1400012b3  test    r8, r8
0x1400012b6  jz      short loc_1400012C6
0x1400012b8  inc     rcx
0x1400012bb  cmp     [r8+rcx], r9b
0x1400012bf  jnz     short loc_1400012B8
0x1400012c1  lea     edx, [rcx+1]
0x1400012c4  jmp     short loc_1400012C9
0x1400012c6  mov     r8, rbx
0x1400012c9  mov     rax, [rbp+80h+arg_40]
0x1400012d0  mov     rcx, r10
0x1400012d3  mov     [rbp+80h+var_F0], rax
0x1400012d7  mov     rax, [rbp+80h+arg_38]
0x1400012de  mov     [rbp+80h+var_100], rax
0x1400012e2  mov     rax, [rbp+80h+arg_30]
0x1400012e9  mov     [rsp+180h+var_110], rax
0x1400012ee  mov     rax, [rbp+80h+arg_28]
0x1400012f5  mov     [rsp+180h+var_120], rax
0x1400012fa  mov     rax, [rbp+80h+arg_20]
0x140001301  mov     [rsp+180h+var_130], rax
0x140001306  lea     rax, [rsp+180h+var_150]
0x14000130b  mov     [rbp+80h+var_E0], r8
0x14000130f  xor     r8d, r8d
0x140001312  mov     [rbp+80h+var_D8], edx
0x140001315  mov     rdx, r11
0x140001318  mov     [rsp+180h+var_158], rax
0x14000131d  mov     [rsp+180h+var_160], 14h
0x140001325  mov     [rbp+80h+var_D4], r9d
0x140001329  mov     [rbp+80h+var_E8], 4
0x140001331  mov     [rbp+80h+var_F8], 2
0x140001339  mov     [rsp+180h+var_108], 4
0x140001342  mov     [rsp+180h+var_118], 4
0x14000134b  mov     [rsp+180h+var_128], 4
0x140001354  call    _tlgWriteTransfer_EventWriteTransfer
0x140001359  mov     rcx, [rbp+80h+var_10]
0x14000135d  xor     rcx, rsp; StackCookie
0x140001360  call    __security_check_cookie
0x140001365  lea     r11, [rsp+180h+var_s0]
0x14000136d  mov     rbx, [r11+20h]
0x140001371  mov     rsi, [r11+28h]
0x140001375  mov     rsp, r11
0x140001378  pop     rbp
0x140001379  retn
```
