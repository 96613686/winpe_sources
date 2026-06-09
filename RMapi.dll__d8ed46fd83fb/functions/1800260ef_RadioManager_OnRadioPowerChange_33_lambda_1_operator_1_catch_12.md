# __RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()_::_1_::catch$12

- ea: `0x1800260ef`
- end: `0x18002617b`
- name: `__RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()_::_1_::catch$12`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006a2c`
- `0x18000b814`
- `0x180015764`
- `0x1800260ef`

## string_xrefs

- `0x18002612b`: `Exception thrown accessing the SystemRadioStateIgnored registry key to set state`

## pseudocode

```c
__int64 __fastcall _RadioManager::OnRadioPowerChange_::_33_::_lambda_1_::operator()_::_1_::catch_12(
        wil *a1,
        __int64 a2)
{
  int v3; // ecx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 224) = v3;
  if ( (unsigned int)dword_180037050 > 2 )
  {
    *(_DWORD *)(a2 + 216) = v3;
    *(_QWORD *)(a2 + 88) = RmGuidToMediaTypeString(*(const struct _GUID **)(a2 + 112));
    *(_QWORD *)(a2 + 104) = v4;
    *(_QWORD *)(a2 + 96) = "Exception thrown accessing the SystemRadioStateIgnored registry key to set state";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned __int8 *)byte_18002F93D,
      v5,
      v6,
      (const wchar_t **)(a2 + 96),
      (__int64 *)(a2 + 104),
      (const wchar_t **)(a2 + 88),
      a2 + 216);
  }
  return 0;
}

```

## disassembly

```asm
0x1800260ef  mov     [rsp+arg_8], rdx
0x1800260f4  push    rbp
0x1800260f5  sub     rsp, 50h
0x1800260f9  mov     rbp, rdx
0x1800260fc  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180026101  mov     ecx, eax
0x180026103  mov     [rbp+0E0h], eax
0x180026109  mov     eax, cs:dword_180037050
0x18002610f  cmp     eax, 2
0x180026112  jbe     short loc_18002616A
0x180026114  mov     [rbp+0D8h], ecx
0x18002611a  mov     rcx, [rbp+70h]; struct _GUID *
0x18002611e  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180026123  mov     [rbp+58h], rax
0x180026127  mov     [rbp+68h], rcx
0x18002612b  lea     rax, aExceptionThrow_7; "Exception thrown accessing the SystemRa"...
0x180026132  mov     [rbp+60h], rax
0x180026136  lea     rax, [rbp+0D8h]
0x18002613d  mov     [rsp+58h+var_20], rax
0x180026142  lea     rax, [rbp+58h]
0x180026146  mov     [rsp+58h+var_28], rax
0x18002614b  lea     rax, [rbp+68h]
0x18002614f  mov     [rsp+58h+var_30], rax
0x180026154  lea     rax, [rbp+60h]
0x180026158  mov     [rsp+58h+var_38], rax
0x18002615d  lea     rdx, byte_18002F93D
0x180026164  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180026169  nop
0x18002616a  mov     rax, 0
0x180026174  add     rsp, 50h
0x180026178  pop     rbp
0x180026179  retn
```
