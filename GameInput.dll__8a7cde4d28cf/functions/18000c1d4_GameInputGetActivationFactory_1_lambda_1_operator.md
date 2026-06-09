# _GameInputGetActivationFactory_::_1_::_lambda_1_::operator()

- ea: `0x18000c1d4`
- end: `0x18000c252`
- name: `_GameInputGetActivationFactory_::_1_::_lambda_1_::operator()`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c69c`

## callees

- `0x180001304`
- `0x18000c1d4`

## string_xrefs

- `0x18000c20b`: `onecore\xbox\gameinput\common\WinrtResourceWrappers.cpp`

## pseudocode

```c
char __fastcall GameInputGetActivationFactory_::_1_::_lambda_1_::operator()(__int64 a1, int a2, __int64 a3, __int64 a4)
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
    LODWORD(v5) = 102;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)&dword_18005A0AC,
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
0x18000c1d4  mov     r11, rsp
0x18000c1d7  mov     [r11+8], rcx
0x18000c1db  sub     rsp, 48h
0x18000c1df  test    edx, edx
0x18000c1e1  jns     short loc_18000C24A
0x18000c1e3  mov     eax, cs:dword_180069000
0x18000c1e9  cmp     eax, 2
0x18000c1ec  jbe     short loc_18000C246
0x18000c1ee  mov     rcx, cs:qword_180069018
0x18000c1f5  mov     rax, cs:qword_180069010
0x18000c1fc  test    al, 2
0x18000c1fe  jz      short loc_18000C246
0x18000c200  mov     rax, rcx
0x18000c203  and     eax, 2
0x18000c206  cmp     rax, rcx
0x18000c209  jnz     short loc_18000C246
0x18000c20b  lea     rax, aOnecoreXboxGam_7; "onecore\\xbox\\gameinput\\common\\Winrt"...
0x18000c212  mov     [rsp+48h+arg_8], edx
0x18000c216  mov     [r11+18h], rax
0x18000c21a  lea     rdx, dword_18005A0AC
0x18000c221  lea     rax, [r11+10h]
0x18000c225  mov     dword ptr [rsp+48h+arg_0], 66h ; 'f'
0x18000c22d  mov     [r11-18h], rax
0x18000c231  lea     rax, [r11+8]
0x18000c235  mov     [r11-20h], rax
0x18000c239  lea     rax, [r11+18h]
0x18000c23d  mov     [r11-28h], rax
0x18000c241  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c246  mov     al, 1
0x18000c248  jmp     short loc_18000C24C
0x18000c24a  xor     al, al
0x18000c24c  add     rsp, 48h
0x18000c250  retn
```
