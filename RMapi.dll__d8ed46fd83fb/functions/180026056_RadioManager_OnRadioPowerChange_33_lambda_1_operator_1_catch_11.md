# __RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()_::_1_::catch$11

- ea: `0x180026056`
- end: `0x1800260e9`
- name: `__RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()_::_1_::catch$11`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006a2c`
- `0x18000b814`
- `0x180015764`
- `0x180026056`

## string_xrefs

- `0x180026099`: `Exception thrown accessing the SystemRadioStateIgnored registry key to read state`

## pseudocode

```c
__int64 __fastcall _RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()_::_1_::catch_11(
        wil *a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9

  if ( (unsigned int)wil::ResultFromCaughtException(a1) != -2147024894 )
  {
    *(_BYTE *)(a2 + 82) = 1;
    if ( (unsigned int)dword_180037050 > 2 )
    {
      *(_DWORD *)(a2 + 216) = 0;
      *(_QWORD *)(a2 + 96) = RmGuidToMediaTypeString(*(const struct _GUID **)(a2 + 112));
      *(_QWORD *)(a2 + 104) = v3;
      *(_QWORD *)(a2 + 88) = "Exception thrown accessing the SystemRadioStateIgnored registry key to read state";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v3,
        (unsigned __int8 *)word_18002FA12,
        v4,
        v5,
        (const wchar_t **)(a2 + 88),
        (__int64 *)(a2 + 104),
        (const wchar_t **)(a2 + 96),
        a2 + 216);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180026056  mov     [rsp+arg_8], rdx
0x18002605b  push    rbp
0x18002605c  sub     rsp, 50h
0x180026060  mov     rbp, rdx
0x180026063  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180026068  cmp     eax, 80070002h
0x18002606d  jz      short loc_1800260D8
0x18002606f  mov     byte ptr [rbp+52h], 1
0x180026073  mov     eax, cs:dword_180037050
0x180026079  cmp     eax, 2
0x18002607c  jbe     short loc_1800260D8
0x18002607e  mov     dword ptr [rbp+0D8h], 0
0x180026088  mov     rcx, [rbp+70h]; struct _GUID *
0x18002608c  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180026091  mov     [rbp+60h], rax
0x180026095  mov     [rbp+68h], rcx
0x180026099  lea     rax, aExceptionThrow; "Exception thrown accessing the SystemRa"...
0x1800260a0  mov     [rbp+58h], rax
0x1800260a4  lea     rax, [rbp+0D8h]
0x1800260ab  mov     [rsp+58h+var_20], rax
0x1800260b0  lea     rax, [rbp+60h]
0x1800260b4  mov     [rsp+58h+var_28], rax
0x1800260b9  lea     rax, [rbp+68h]
0x1800260bd  mov     [rsp+58h+var_30], rax
0x1800260c2  lea     rax, [rbp+58h]
0x1800260c6  mov     [rsp+58h+var_38], rax
0x1800260cb  lea     rdx, word_18002FA12
0x1800260d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800260d7  nop
0x1800260d8  mov     rax, 0
0x1800260e2  add     rsp, 50h
0x1800260e6  pop     rbp
0x1800260e7  retn
```
