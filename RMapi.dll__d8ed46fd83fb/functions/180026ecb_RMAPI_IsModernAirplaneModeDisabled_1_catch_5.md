# _RMAPI::IsModernAirplaneModeDisabled_::_1_::catch$5

- ea: `0x180026ecb`
- end: `0x180026f2d`
- name: `_RMAPI::IsModernAirplaneModeDisabled_::_1_::catch$5`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800042b0`
- `0x180015764`
- `0x180026ecb`

## string_xrefs

- `0x180026ef2`: `Exception accessing DisableModernAPM reg key!`

## pseudocode

```c
__int64 __fastcall RMAPI::IsModernAirplaneModeDisabled_::_1_::catch_5(wil *a1, __int64 a2)
{
  int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx

  v3 = wil::ResultFromCaughtException(a1);
  if ( v3 != -2147024894 )
  {
    v6 = (unsigned int)dword_180037050;
    if ( (unsigned int)dword_180037050 > 2 )
    {
      *(_DWORD *)(a2 + 96) = v3;
      *(_QWORD *)(a2 + 56) = "Exception accessing DisableModernAPM reg key!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned __int8 *)word_1800302AA,
        v4,
        v5,
        (const wchar_t **)(a2 + 56),
        a2 + 96);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180026ecb  mov     [rsp+arg_8], rdx
0x180026ed0  push    rbp
0x180026ed1  sub     rsp, 30h
0x180026ed5  mov     rbp, rdx
0x180026ed8  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180026edd  cmp     eax, 80070002h
0x180026ee2  jz      short loc_180026F1C
0x180026ee4  mov     ecx, cs:dword_180037050
0x180026eea  cmp     ecx, 2
0x180026eed  jbe     short loc_180026F1C
0x180026eef  mov     [rbp+60h], eax
0x180026ef2  lea     rax, aExceptionAcces; "Exception accessing DisableModernAPM re"...
0x180026ef9  mov     [rbp+38h], rax
0x180026efd  lea     rax, [rbp+60h]
0x180026f01  mov     [rsp+38h+var_10], rax
0x180026f06  lea     rax, [rbp+38h]
0x180026f0a  mov     [rsp+38h+var_18], rax
0x180026f0f  lea     rdx, word_1800302AA
0x180026f16  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180026f1b  nop
0x180026f1c  mov     rax, 0
0x180026f26  add     rsp, 30h
0x180026f2a  pop     rbp
0x180026f2b  retn
```
