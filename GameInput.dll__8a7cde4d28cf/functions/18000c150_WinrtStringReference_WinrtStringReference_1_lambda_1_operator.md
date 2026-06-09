# _WinrtStringReference::WinrtStringReference_::_1_::_lambda_1_::operator()

- ea: `0x18000c150`
- end: `0x18000c1ce`
- name: `_WinrtStringReference::WinrtStringReference_::_1_::_lambda_1_::operator()`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c04c`

## callees

- `0x180001304`
- `0x18000c150`

## string_xrefs

- `0x18000c187`: `onecore\xbox\gameinput\common\WinrtResourceWrappers.cpp`

## pseudocode

```c
char __fastcall WinrtStringReference::WinrtStringReference_::_1_::_lambda_1_::operator()(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF
  const char *v7; // [rsp+60h] [rbp+18h] BYREF

  v5 = a1;
  if ( a2 >= 0 )
    return 0;
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
  {
    v6 = a2;
    v7 = "onecore\\xbox\\gameinput\\common\\WinrtResourceWrappers.cpp";
    LODWORD(v5) = 150;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)byte_180059ED9,
      a3,
      a4,
      (__int64 **)&v7,
      (__int64)&v5,
      (__int64)&v6);
  }
  return 1;
}

```

## disassembly

```asm
0x18000c150  mov     r11, rsp
0x18000c153  mov     [r11+8], rcx
0x18000c157  sub     rsp, 48h
0x18000c15b  test    edx, edx
0x18000c15d  jns     short loc_18000C1C6
0x18000c15f  mov     eax, cs:dword_180069000
0x18000c165  cmp     eax, 2
0x18000c168  jbe     short loc_18000C1C2
0x18000c16a  mov     rcx, cs:qword_180069018
0x18000c171  mov     rax, cs:qword_180069010
0x18000c178  test    al, 2
0x18000c17a  jz      short loc_18000C1C2
0x18000c17c  mov     rax, rcx
0x18000c17f  and     eax, 2
0x18000c182  cmp     rax, rcx
0x18000c185  jnz     short loc_18000C1C2
0x18000c187  lea     rax, aOnecoreXboxGam_7; "onecore\\xbox\\gameinput\\common\\Winrt"...
0x18000c18e  mov     [rsp+48h+arg_8], edx
0x18000c192  mov     [r11+18h], rax
0x18000c196  lea     rdx, byte_180059ED9
0x18000c19d  lea     rax, [r11+10h]
0x18000c1a1  mov     dword ptr [rsp+48h+arg_0], 96h
0x18000c1a9  mov     [r11-18h], rax
0x18000c1ad  lea     rax, [r11+8]
0x18000c1b1  mov     [r11-20h], rax
0x18000c1b5  lea     rax, [r11+18h]
0x18000c1b9  mov     [r11-28h], rax
0x18000c1bd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c1c2  mov     al, 1
0x18000c1c4  jmp     short loc_18000C1C8
0x18000c1c6  xor     al, al
0x18000c1c8  add     rsp, 48h
0x18000c1cc  retn
```
