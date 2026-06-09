# _RadioInstance::GetSystemRadioStateIgnored_::_1_::catch$7

- ea: `0x180025b66`
- end: `0x180025c03`
- name: `_RadioInstance::GetSystemRadioStateIgnored_::_1_::catch$7`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006a2c`
- `0x18000b814`
- `0x180015764`
- `0x180025b66`

## string_xrefs

- `0x180025bb3`: `Exception thrown accessing the SystemRadioStateIgnored registry key to check if RM GUID is ignored`

## pseudocode

```c
__int64 __fastcall RadioInstance::GetSystemRadioStateIgnored_::_1_::catch_7(wil *a1, __int64 a2)
{
  wil *v3; // rcx
  int v4; // ecx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9

  if ( (unsigned int)wil::ResultFromCaughtException(a1) != -2147024894 )
  {
    v4 = wil::ResultFromCaughtException(v3);
    *(_DWORD *)(a2 + 64) = v4;
    if ( (unsigned int)dword_180037050 > 2 )
    {
      *(_DWORD *)(a2 + 136) = v4;
      *(_QWORD *)(a2 + 88) = RmGuidToMediaTypeString((const struct _GUID *)(*(_QWORD *)(a2 + 88) + 120LL));
      *(_QWORD *)(a2 + 80) = v5 + 120;
      *(_QWORD *)(a2 + 72) = "Exception thrown accessing the SystemRadioStateIgnored registry key to check if RM GUID is ignored";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned __int8 *)byte_18002E419,
        v7,
        v8,
        (const wchar_t **)(a2 + 72),
        (__int64 *)(a2 + 80),
        (const wchar_t **)(a2 + 88),
        a2 + 136);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025b66  mov     [rsp+arg_8], rdx
0x180025b6b  push    rbp
0x180025b6c  sub     rsp, 40h
0x180025b70  mov     rbp, rdx
0x180025b73  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180025b78  cmp     eax, 80070002h
0x180025b7d  jz      short loc_180025BF2
0x180025b7f  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180025b84  mov     ecx, eax
0x180025b86  mov     [rbp+40h], eax
0x180025b89  mov     eax, cs:dword_180037050
0x180025b8f  cmp     eax, 2
0x180025b92  jbe     short loc_180025BF2
0x180025b94  mov     [rbp+88h], ecx
0x180025b9a  mov     rdx, [rbp+58h]
0x180025b9e  lea     rcx, [rdx+78h]; struct _GUID *
0x180025ba2  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180025ba7  mov     [rbp+58h], rax
0x180025bab  lea     rax, [rdx+78h]
0x180025baf  mov     [rbp+50h], rax
0x180025bb3  lea     rax, aExceptionThrow_9; "Exception thrown accessing the SystemRa"...
0x180025bba  mov     [rbp+48h], rax
0x180025bbe  lea     rax, [rbp+88h]
0x180025bc5  mov     [rsp+48h+var_10], rax
0x180025bca  lea     rax, [rbp+58h]
0x180025bce  mov     [rsp+48h+var_18], rax
0x180025bd3  lea     rax, [rbp+50h]
0x180025bd7  mov     [rsp+48h+var_20], rax
0x180025bdc  lea     rax, [rbp+48h]
0x180025be0  mov     [rsp+48h+var_28], rax
0x180025be5  lea     rdx, byte_18002E419
0x180025bec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180025bf1  nop
0x180025bf2  mov     rax, 0
0x180025bfc  add     rsp, 40h
0x180025c00  pop     rbp
0x180025c01  retn
```
