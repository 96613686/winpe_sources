# HidForceFeedbackBrokerFactory::LockServer(int)

- ea: `0x180017df0`
- end: `0x180017e69`
- name: `?LockServer@HidForceFeedbackBrokerFactory@@UEAAJH@Z`
- size: `121`
- prototype: `__int64 __fastcall(HidForceFeedbackBrokerFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001304`
- `0x180017df0`

## string_xrefs

- `0x180017e1f`: `onecore\xbox\gameinput\feedback\hid\HidForceFeedbackBrokerFactory.cpp`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackBrokerFactory::LockServer(
        HidForceFeedbackBrokerFactory *this,
        __int64 a2,
        int a3,
        int a4)
{
  const char *v5; // [rsp+40h] [rbp-18h] BYREF
  int v6; // [rsp+70h] [rbp+18h] BYREF
  int v7; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v6 = -2147467263;
    v5 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackBrokerFactory.cpp";
    v7 = 22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)byte_18005AA7B,
      a3,
      a4,
      (__int64)&v5,
      (__int64)&v7,
      (__int64)&v6);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180017df0  mov     r11, rsp
0x180017df3  sub     rsp, 58h
0x180017df7  mov     eax, cs:dword_180069000
0x180017dfd  cmp     eax, 2
0x180017e00  jbe     short loc_180017E5E
0x180017e02  mov     rcx, cs:qword_180069018
0x180017e09  mov     rax, cs:qword_180069010
0x180017e10  test    al, 8
0x180017e12  jz      short loc_180017E5E
0x180017e14  mov     rax, rcx
0x180017e17  and     eax, 8
0x180017e1a  cmp     rax, rcx
0x180017e1d  jnz     short loc_180017E5E
0x180017e1f  lea     rax, aOnecoreXboxGam_19; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180017e26  mov     [rsp+58h+arg_10], 80004001h
0x180017e2e  mov     [r11-18h], rax
0x180017e32  lea     rdx, byte_18005AA7B
0x180017e39  lea     rax, [r11+18h]
0x180017e3d  mov     [rsp+58h+arg_18], 16h
0x180017e45  mov     [r11-28h], rax
0x180017e49  lea     rax, [r11+20h]
0x180017e4d  mov     [r11-30h], rax
0x180017e51  lea     rax, [r11-18h]
0x180017e55  mov     [r11-38h], rax
0x180017e59  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017e5e  mov     eax, 80004001h
0x180017e63  add     rsp, 58h
0x180017e67  retn
```
