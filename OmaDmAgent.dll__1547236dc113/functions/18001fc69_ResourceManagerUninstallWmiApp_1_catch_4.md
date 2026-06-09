# _ResourceManagerUninstallWmiApp_::_1_::catch$4

- ea: `0x18001fc69`
- end: `0x18001fcb5`
- name: `_ResourceManagerUninstallWmiApp_::_1_::catch$4`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000121c`
- `0x180005214`
- `0x18001fc69`

## pseudocode

```c
__int64 __fastcall ResourceManagerUninstallWmiApp_::_1_::catch_4(wil *a1, __int64 a2)
{
  unsigned int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 64) = v3;
  if ( (unsigned int)dword_18002B000 > 5 )
  {
    *(_DWORD *)(a2 + 52) = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v3,
      (unsigned __int8 *)&dword_180024BCC,
      v4,
      v5,
      a2 + 52);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fc69  mov     [rsp+arg_8], rdx
0x18001fc6e  push    rbp
0x18001fc6f  sub     rsp, 30h
0x18001fc73  mov     rbp, rdx
0x18001fc76  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18001fc7b  mov     ecx, eax
0x18001fc7d  mov     [rbp+40h], eax
0x18001fc80  mov     eax, cs:dword_18002B000
0x18001fc86  cmp     eax, 5
0x18001fc89  jbe     short loc_18001FCA4
0x18001fc8b  mov     [rbp+34h], ecx
0x18001fc8e  lea     rax, [rbp+34h]
0x18001fc92  mov     [rsp+38h+var_18], rax
0x18001fc97  lea     rdx, dword_180024BCC
0x18001fc9e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001fca3  nop
0x18001fca4  mov     rax, 0
0x18001fcae  add     rsp, 30h
0x18001fcb2  pop     rbp
0x18001fcb3  retn
```
