# _RadioManager::_LoadRadioManagers_::_1_::catch$31

- ea: `0x1800269ce`
- end: `0x180026a29`
- name: `_RadioManager::_LoadRadioManagers_::_1_::catch$31`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800042b0`
- `0x180015764`
- `0x1800269ce`

## string_xrefs

- `0x1800269ee`: `Exception thrown accessing the RadioManager registry key to find radio managers`

## pseudocode

```c
__int64 __fastcall RadioManager::_LoadRadioManagers_::_1_::catch_31(wil *a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9

  if ( (unsigned int)dword_180037050 > 2 )
  {
    *(_DWORD *)(a2 + 64) = wil::ResultFromCaughtException(a1);
    *(_QWORD *)(a2 + 104) = "Exception thrown accessing the RadioManager registry key to find radio managers";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned __int8 *)&word_18002FCDE,
      v4,
      v5,
      (const wchar_t **)(a2 + 104),
      a2 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x1800269ce  mov     [rsp+arg_8], rdx
0x1800269d3  push    rbp
0x1800269d4  sub     rsp, 40h
0x1800269d8  mov     rbp, rdx
0x1800269db  mov     eax, cs:dword_180037050
0x1800269e1  cmp     eax, 2
0x1800269e4  jbe     short loc_180026A18
0x1800269e6  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x1800269eb  mov     [rbp+40h], eax
0x1800269ee  lea     rax, aExceptionThrow_13; "Exception thrown accessing the RadioMan"...
0x1800269f5  mov     [rbp+68h], rax
0x1800269f9  lea     rax, [rbp+40h]
0x1800269fd  mov     [rsp+48h+var_20], rax
0x180026a02  lea     rax, [rbp+68h]
0x180026a06  mov     [rsp+48h+var_28], rax
0x180026a0b  lea     rdx, word_18002FCDE
0x180026a12  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180026a17  nop
0x180026a18  mov     rax, 0
0x180026a22  add     rsp, 40h
0x180026a26  pop     rbp
0x180026a27  retn
```
