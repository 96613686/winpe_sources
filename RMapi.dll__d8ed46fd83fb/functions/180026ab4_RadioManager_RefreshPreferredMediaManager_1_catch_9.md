# _RadioManager::_RefreshPreferredMediaManager_::_1_::catch$9

- ea: `0x180026ab4`
- end: `0x180026b5a`
- name: `_RadioManager::_RefreshPreferredMediaManager_::_1_::catch$9`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006a2c`
- `0x18000b814`
- `0x180015764`
- `0x180026ab4`

## string_xrefs

- `0x180026afe`: `Exception thrown accessing the SystemRadioStateIgnored registry key - preferred media radio type might be an ignored media radio type`

## pseudocode

```c
__int64 __fastcall RadioManager::_RefreshPreferredMediaManager_::_1_::catch_9(wil *a1, __int64 a2)
{
  wil *v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9

  if ( (unsigned int)wil::ResultFromCaughtException(a1) == -2147024894 )
    return 1;
  v4 = wil::ResultFromCaughtException(v3);
  if ( (unsigned int)dword_180037050 > 2 )
  {
    *(_DWORD *)(a2 + 152) = v4;
    *(_QWORD *)(a2 + 88) = RmGuidToMediaTypeString((const struct _GUID *)(a2 + 160));
    *(_QWORD *)(a2 + 80) = a2 + 160;
    *(_QWORD *)(a2 + 72) = "Exception thrown accessing the SystemRadioStateIgnored registry key - preferred media radio t"
                           "ype might be an ignored media radio type";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned __int8 *)byte_18002F401,
      v6,
      v7,
      (const wchar_t **)(a2 + 72),
      (__int64 *)(a2 + 80),
      (const wchar_t **)(a2 + 88),
      a2 + 152);
  }
  return 0;
}

```

## disassembly

```asm
0x180026ab4  mov     [rsp+arg_8], rdx
0x180026ab9  push    rbp
0x180026aba  sub     rsp, 40h
0x180026abe  mov     rbp, rdx
0x180026ac1  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180026ac6  cmp     eax, 80070002h
0x180026acb  jz      short loc_180026B49
0x180026acd  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180026ad2  mov     ecx, cs:dword_180037050
0x180026ad8  cmp     ecx, 2
0x180026adb  jbe     short loc_180026B3D
0x180026add  mov     [rbp+98h], eax
0x180026ae3  lea     rcx, [rbp+0A0h]; struct _GUID *
0x180026aea  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180026aef  mov     [rbp+58h], rax
0x180026af3  lea     rax, [rbp+0A0h]
0x180026afa  mov     [rbp+50h], rax
0x180026afe  lea     rax, aExceptionThrow_0; "Exception thrown accessing the SystemRa"...
0x180026b05  mov     [rbp+48h], rax
0x180026b09  lea     rax, [rbp+98h]
0x180026b10  mov     [rsp+48h+var_10], rax
0x180026b15  lea     rax, [rbp+58h]
0x180026b19  mov     [rsp+48h+var_18], rax
0x180026b1e  lea     rax, [rbp+50h]
0x180026b22  mov     [rsp+48h+var_20], rax
0x180026b27  lea     rax, [rbp+48h]
0x180026b2b  mov     [rsp+48h+var_28], rax
0x180026b30  lea     rdx, byte_18002F401
0x180026b37  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180026b3c  nop
0x180026b3d  mov     rax, 0
0x180026b47  jmp     short loc_180026B53
0x180026b49  mov     rax, 1
0x180026b53  add     rsp, 40h
0x180026b57  pop     rbp
0x180026b58  retn
```
