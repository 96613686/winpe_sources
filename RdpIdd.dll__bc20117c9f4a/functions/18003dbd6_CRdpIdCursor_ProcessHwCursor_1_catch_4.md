# _CRdpIdCursor::ProcessHwCursor_::_1_::catch$4

- ea: `0x18003dbd6`
- end: `0x18003dde3`
- name: `_CRdpIdCursor::ProcessHwCursor_::_1_::catch$4`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001bc4`
- `0x180004fa8`
- `0x18000d614`
- `0x18000f0b8`
- `0x18001d368`
- `0x180030420`
- `0x18003dbd6`

## string_xrefs

- `0x18003dc37`: `Setting up H/W cursor failed during connection shutdown. Fallback to S/W mode cannot be done at this point`

## pseudocode

```c
__int64 __fastcall CRdpIdCursor::ProcessHwCursor_::_1_::catch_4(wil *a1, __int64 a2)
{
  int v3; // ebx
  const char *v4; // r9
  _DWORD *v5; // r8
  int v6; // r9d
  _DWORD *v7; // r8
  int v8; // r9d
  CRdpIdCursor *v9; // rbx

  v3 = wil::ResultFromCaughtException(a1);
  if ( v3 == -2147467260 )
  {
    v5 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v5 > 3u )
    {
      *(_DWORD *)(a2 + 136) = *(_DWORD *)(*(_QWORD *)(a2 + 176) + 516LL);
      *(_DWORD *)(a2 + 152) = *(_DWORD *)(**(_QWORD **)(a2 + 192) + 280LL);
      *(_QWORD *)(a2 + 168) = "Setting up H/W cursor failed during connection shutdown. Fallback to S/W mode cannot be do"
                              "ne at this point";
      *(_QWORD *)(a2 + 160) = "CRdpIdCursor::ProcessHwCursor";
      *(_DWORD *)(a2 + 128) = 432;
      *(_QWORD *)(a2 + 144) = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v5,
        (unsigned int)&word_18004F99E,
        (_DWORD)v5,
        v6,
        a2 + 144,
        a2 + 128,
        a2 + 160,
        a2 + 168,
        a2 + 152,
        a2 + 136);
    }
  }
  else
  {
    wil::details::in1diag3::Log_CaughtException(
      *(wil::details::in1diag3 **)(a2 + 376),
      (void *)0x1B4,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp",
      v4);
    v7 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v7 <= 3u )
    {
      v9 = *(CRdpIdCursor **)(a2 + 192);
    }
    else
    {
      *(_DWORD *)(a2 + 136) = v3;
      *(_DWORD *)(a2 + 152) = *(_DWORD *)(*(_QWORD *)(a2 + 176) + 516LL);
      v9 = *(CRdpIdCursor **)(a2 + 192);
      *(_DWORD *)(a2 + 128) = *(_DWORD *)(*(_QWORD *)v9 + 280LL);
      *(_QWORD *)(a2 + 168) = "Non-fatal. Falling back to S/W cursor mode";
      *(_QWORD *)(a2 + 160) = "CRdpIdCursor::ProcessHwCursor";
      *(_DWORD *)(a2 + 192) = 445;
      *(_QWORD *)(a2 + 144) = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\cursor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v7,
        (unsigned int)&byte_18004F947,
        (_DWORD)v7,
        v8,
        a2 + 144,
        a2 + 192,
        a2 + 160,
        a2 + 168,
        a2 + 128,
        a2 + 152,
        a2 + 136);
    }
    CRdpIdCursor::EnableHwCursorInternal(v9, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18003dbd6  mov     [rsp+arg_8], rdx
0x18003dbdb  push    rbx
0x18003dbdc  push    rbp
0x18003dbdd  sub     rsp, 88h
0x18003dbe4  mov     rbp, rdx
0x18003dbe7  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18003dbec  mov     ebx, eax
0x18003dbee  cmp     eax, 80004004h
0x18003dbf3  jnz     loc_18003DCC7
0x18003dbf9  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18003dbfe  mov     r8, [rax+8]
0x18003dc02  mov     eax, [r8]
0x18003dc05  cmp     eax, 3
0x18003dc08  jbe     loc_18003DDCE
0x18003dc0e  mov     rax, [rbp+0B0h]
0x18003dc15  mov     ecx, [rax+204h]
0x18003dc1b  mov     [rbp+88h], ecx
0x18003dc21  mov     rax, [rbp+0C0h]
0x18003dc28  mov     rcx, [rax]
0x18003dc2b  mov     eax, [rcx+118h]
0x18003dc31  mov     [rbp+98h], eax
0x18003dc37  lea     rax, aSettingUpHWCur; "Setting up H/W cursor failed during con"...
0x18003dc3e  mov     [rbp+0A8h], rax
0x18003dc45  lea     rax, aCrdpidcursorPr; "CRdpIdCursor::ProcessHwCursor"
0x18003dc4c  mov     [rbp+0A0h], rax
0x18003dc53  mov     dword ptr [rbp+80h], 1B0h
0x18003dc5d  lea     rax, aOnecoreuapTerm_16; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003dc64  mov     [rbp+90h], rax
0x18003dc6b  lea     rax, [rbp+88h]
0x18003dc72  mov     [rsp+98h+var_50], rax
0x18003dc77  lea     rax, [rbp+98h]
0x18003dc7e  mov     [rsp+98h+var_58], rax
0x18003dc83  lea     rax, [rbp+0A8h]
0x18003dc8a  mov     [rsp+98h+var_60], rax
0x18003dc8f  lea     rax, [rbp+0A0h]
0x18003dc96  mov     [rsp+98h+var_68], rax
0x18003dc9b  lea     rax, [rbp+80h]
0x18003dca2  mov     [rsp+98h+var_70], rax
0x18003dca7  lea     rax, [rbp+90h]
0x18003dcae  mov     [rsp+98h+var_78], rax
0x18003dcb3  lea     rdx, word_18004F99E
0x18003dcba  mov     rcx, r8
0x18003dcbd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003dcc2  jmp     loc_18003DDCE
0x18003dcc7  mov     rcx, [rbp+178h]; this
0x18003dcce  lea     r8, aOnecoreuapTerm_16; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003dcd5  mov     edx, 1B4h; void *
0x18003dcda  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003dcdf  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18003dce4  mov     r8, [rax+8]
0x18003dce8  mov     eax, [r8]
0x18003dceb  cmp     eax, 3
0x18003dcee  jbe     loc_18003DDBC
0x18003dcf4  mov     [rbp+88h], ebx
0x18003dcfa  mov     rax, [rbp+0B0h]
0x18003dd01  mov     ecx, [rax+204h]
0x18003dd07  mov     [rbp+98h], ecx
0x18003dd0d  mov     rbx, [rbp+0C0h]
0x18003dd14  mov     rax, [rbx]
0x18003dd17  mov     ecx, [rax+118h]
0x18003dd1d  mov     [rbp+80h], ecx
0x18003dd23  lea     rax, aNonFatalFallin; "Non-fatal. Falling back to S/W cursor m"...
0x18003dd2a  mov     [rbp+0A8h], rax
0x18003dd31  lea     rax, aCrdpidcursorPr; "CRdpIdCursor::ProcessHwCursor"
0x18003dd38  mov     [rbp+0A0h], rax
0x18003dd3f  mov     dword ptr [rbp+0C0h], 1BDh
0x18003dd49  lea     rax, aOnecoreuapTerm_16; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003dd50  mov     [rbp+90h], rax
0x18003dd57  lea     rax, [rbp+88h]
0x18003dd5e  mov     [rsp+98h+var_48], rax
0x18003dd63  lea     rax, [rbp+98h]
0x18003dd6a  mov     [rsp+98h+var_50], rax
0x18003dd6f  lea     rax, [rbp+80h]
0x18003dd76  mov     [rsp+98h+var_58], rax
0x18003dd7b  lea     rax, [rbp+0A8h]
0x18003dd82  mov     [rsp+98h+var_60], rax
0x18003dd87  lea     rax, [rbp+0A0h]
0x18003dd8e  mov     [rsp+98h+var_68], rax
0x18003dd93  lea     rax, [rbp+0C0h]
0x18003dd9a  mov     [rsp+98h+var_70], rax
0x18003dd9f  lea     rax, [rbp+90h]
0x18003dda6  mov     [rsp+98h+var_78], rax
0x18003ddab  lea     rdx, byte_18004F947
0x18003ddb2  mov     rcx, r8
0x18003ddb5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003ddba  jmp     short loc_18003DDC3
0x18003ddbc  mov     rbx, [rbp+0C0h]
0x18003ddc3  xor     edx, edx; bool
0x18003ddc5  mov     rcx, rbx; this
0x18003ddc8  call    ?EnableHwCursorInternal@CRdpIdCursor@@AEAAX_N@Z; CRdpIdCursor::EnableHwCursorInternal(bool)
0x18003ddcd  nop
0x18003ddce  mov     rax, 0
0x18003ddd8  add     rsp, 88h
0x18003dddf  pop     rbp
0x18003dde0  pop     rbx
0x18003dde1  retn
```
