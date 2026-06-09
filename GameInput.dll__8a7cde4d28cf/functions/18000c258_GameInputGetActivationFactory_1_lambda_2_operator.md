# _GameInputGetActivationFactory_::_1_::_lambda_2_::operator()

- ea: `0x18000c258`
- end: `0x18000c2d6`
- name: `_GameInputGetActivationFactory_::_1_::_lambda_2_::operator()`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c69c`

## callees

- `0x180001304`
- `0x18000c258`

## string_xrefs

- `0x18000c28f`: `onecore\xbox\gameinput\common\WinrtResourceWrappers.cpp`

## pseudocode

```c
char __fastcall GameInputGetActivationFactory_::_1_::_lambda_2_::operator()(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF
  const char *v7; // [rsp+60h] [rbp+18h] BYREF

  v5 = a1;
  if ( a2 >= 0 )
    return 1;
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
  {
    v6 = a2;
    v7 = "onecore\\xbox\\gameinput\\common\\WinrtResourceWrappers.cpp";
    LODWORD(v5) = 126;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)&dword_180059E9C,
      a3,
      a4,
      (__int64 **)&v7,
      (__int64)&v5,
      (__int64)&v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c258  mov     r11, rsp
0x18000c25b  mov     [r11+8], rcx
0x18000c25f  sub     rsp, 48h
0x18000c263  test    edx, edx
0x18000c265  jns     short loc_18000C2CE
0x18000c267  mov     eax, cs:dword_180069000
0x18000c26d  cmp     eax, 2
0x18000c270  jbe     short loc_18000C2CA
0x18000c272  mov     rcx, cs:qword_180069018
0x18000c279  mov     rax, cs:qword_180069010
0x18000c280  test    al, 2
0x18000c282  jz      short loc_18000C2CA
0x18000c284  mov     rax, rcx
0x18000c287  and     eax, 2
0x18000c28a  cmp     rax, rcx
0x18000c28d  jnz     short loc_18000C2CA
0x18000c28f  lea     rax, aOnecoreXboxGam_7; "onecore\\xbox\\gameinput\\common\\Winrt"...
0x18000c296  mov     [rsp+48h+arg_8], edx
0x18000c29a  mov     [r11+18h], rax
0x18000c29e  lea     rdx, dword_180059E9C
0x18000c2a5  lea     rax, [r11+10h]
0x18000c2a9  mov     dword ptr [rsp+48h+arg_0], 7Eh ; '~'
0x18000c2b1  mov     [r11-18h], rax
0x18000c2b5  lea     rax, [r11+8]
0x18000c2b9  mov     [r11-20h], rax
0x18000c2bd  lea     rax, [r11+18h]
0x18000c2c1  mov     [r11-28h], rax
0x18000c2c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c2ca  xor     al, al
0x18000c2cc  jmp     short loc_18000C2D0
0x18000c2ce  mov     al, 1
0x18000c2d0  add     rsp, 48h
0x18000c2d4  retn
```
