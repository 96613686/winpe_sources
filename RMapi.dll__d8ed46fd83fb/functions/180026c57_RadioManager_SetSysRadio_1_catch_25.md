# _RadioManager::_SetSysRadio_::_1_::catch$25

- ea: `0x180026c57`
- end: `0x180026cfa`
- name: `_RadioManager::_SetSysRadio_::_1_::catch$25`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006a2c`
- `0x18000b814`
- `0x180015764`
- `0x180026c57`

## string_xrefs

- `0x180026ca7`: `Exception thrown accessing the SystemRadioStateIgnored registry key to check if RM GUID is ignored`

## pseudocode

```c
__int64 __fastcall RadioManager::_SetSysRadio_::_1_::catch_25(wil *a1, __int64 a2)
{
  wil *v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9

  if ( (unsigned int)wil::ResultFromCaughtException(a1) != -2147024894 )
  {
    v4 = wil::ResultFromCaughtException(v3);
    *(_DWORD *)(a2 + 80) = v4;
    if ( (unsigned int)dword_180037050 > 2 )
    {
      *(_DWORD *)(a2 + 192) = v4;
      *(_QWORD *)(a2 + 96) = RmGuidToMediaTypeString((const struct _GUID *)(a2 + 200));
      *(_QWORD *)(a2 + 136) = a2 + 200;
      *(_QWORD *)(a2 + 88) = "Exception thrown accessing the SystemRadioStateIgnored registry key to check if RM GUID is ignored";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned __int8 *)byte_18002ED2B,
        v6,
        v7,
        (const wchar_t **)(a2 + 88),
        (__int64 *)(a2 + 136),
        (const wchar_t **)(a2 + 96),
        a2 + 192);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180026c57  mov     [rsp+arg_8], rdx
0x180026c5c  push    rbp
0x180026c5d  sub     rsp, 50h
0x180026c61  mov     rbp, rdx
0x180026c64  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180026c69  cmp     eax, 80070002h
0x180026c6e  jz      short loc_180026CE9
0x180026c70  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180026c75  mov     [rbp+50h], eax
0x180026c78  mov     ecx, cs:dword_180037050
0x180026c7e  cmp     ecx, 2
0x180026c81  jbe     short loc_180026CE9
0x180026c83  mov     [rbp+0C0h], eax
0x180026c89  lea     rcx, [rbp+0C8h]; struct _GUID *
0x180026c90  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180026c95  mov     [rbp+60h], rax
0x180026c99  lea     rax, [rbp+0C8h]
0x180026ca0  mov     [rbp+88h], rax
0x180026ca7  lea     rax, aExceptionThrow_9; "Exception thrown accessing the SystemRa"...
0x180026cae  mov     [rbp+58h], rax
0x180026cb2  lea     rax, [rbp+0C0h]
0x180026cb9  mov     [rsp+58h+var_20], rax
0x180026cbe  lea     rax, [rbp+60h]
0x180026cc2  mov     [rsp+58h+var_28], rax
0x180026cc7  lea     rax, [rbp+88h]
0x180026cce  mov     [rsp+58h+var_30], rax
0x180026cd3  lea     rax, [rbp+58h]
0x180026cd7  mov     [rsp+58h+var_38], rax
0x180026cdc  lea     rdx, byte_18002ED2B
0x180026ce3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180026ce8  nop
0x180026ce9  mov     rax, 0
0x180026cf3  add     rsp, 50h
0x180026cf7  pop     rbp
0x180026cf8  retn
```
