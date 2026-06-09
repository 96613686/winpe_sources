# _RadioManager::NotifySinkListeners_::_6_::_lambda_1_::operator()

- ea: `0x18001ca54`
- end: `0x18001cd43`
- name: `_RadioManager::NotifySinkListeners_::_6_::_lambda_1_::operator()`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020cd0`

## callees

- `0x1800042b0`
- `0x18000559c`
- `0x180005c00`
- `0x1800060b0`
- `0x180006a0c`
- `0x1800076b0`
- `0x18000be90`
- `0x18001ca54`
- `0x180028010`

## string_xrefs

- `0x18001ccb9`: `RM_NOTIFY::INSTANCE_REMOVE event`

## pseudocode

```c
int __fastcall RadioManager::NotifySinkListeners_::_6_::_lambda_1_::operator()(__int64 a1, _QWORD *a2)
{
  int v2; // r8d
  int v4; // r8d
  int v5; // r8d
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int result; // eax
  __int64 *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  bool v13; // zf
  const char *v14; // rax
  const char *v15; // rax
  __int64 v16; // rax
  __int64 v17; // r11
  __int64 *v18; // rax
  const char *v19; // rax
  const char *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned __int8 *v29; // rdx
  const char *v30; // rax
  __int64 v31; // rax
  __int64 v32; // r10
  const char *v33; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v34; // [rsp+58h] [rbp-18h] BYREF
  const wchar_t *v35; // [rsp+60h] [rbp-10h] BYREF
  int v36; // [rsp+90h] [rbp+20h] BYREF
  const char *v37; // [rsp+A0h] [rbp+30h] BYREF
  const wchar_t *v38; // [rsp+A8h] [rbp+38h] BYREF

  v2 = *(_DWORD *)(a1 + 44);
  if ( !v2 )
  {
    v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v32 + 24LL))(v32, *(_QWORD *)a1, v31);
    if ( (unsigned int)dword_180037050 <= 4 )
      return result;
    v36 = result;
    v37 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
    v29 = (unsigned __int8 *)byte_18002F6F5;
    v30 = "RM_NOTIFY::INSTANCE_ADD event";
    goto LABEL_23;
  }
  v4 = v2 - 1;
  if ( !v4 )
  {
    v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, v24);
    if ( (unsigned int)dword_180037050 <= 4 )
      return result;
    v36 = result;
    v37 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
    v29 = (unsigned __int8 *)word_18002F6A2;
    v30 = "RM_NOTIFY::INSTANCE_REMOVE event";
LABEL_23:
    v38 = (const wchar_t *)v30;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
             v26,
             v29,
             v27,
             v28,
             &v38,
             (__int64 **)&v37,
             (__int64)&v36);
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 40LL))(
                 *a2,
                 *(unsigned __int8 *)(a1 + 48),
                 *(unsigned __int8 *)(a1 + 49),
                 *(unsigned int *)(a1 + 40));
      if ( (unsigned int)dword_180037050 > 4 )
      {
        v36 = result;
        v10 = (__int64 *)RMToString((const enum _RADIO_CHANGE_REASON *)(a1 + 40));
        v13 = *(_BYTE *)(a1 + 49) == 0;
        v37 = (const char *)v10;
        v14 = "Enabled";
        if ( v13 )
          v14 = "Disabled";
        v13 = *(_BYTE *)(a1 + 48) == 0;
        v38 = (const wchar_t *)v14;
        v15 = "On";
        if ( v13 )
          v15 = "Off";
        v33 = v15;
        v34 = (const wchar_t *)"RM_NOTIFY::SYSTEM_RADIO_CHANGE event";
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 (__int64)"Off",
                 (unsigned __int8 *)&word_18002F5BE,
                 v11,
                 v12,
                 &v34,
                 (const wchar_t **)&v33,
                 &v38,
                 (const wchar_t **)&v37,
                 (__int64)&v36);
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      result = dword_180037050;
      if ( (unsigned int)dword_180037050 > 2 )
      {
        v36 = -2147024809;
        v37 = "Invalid event type";
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 v6,
                 (unsigned __int8 *)byte_18002F577,
                 v7,
                 v8,
                 (const wchar_t **)&v37,
                 (__int64)&v36);
      }
    }
  }
  else
  {
    v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
    result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v17 + 48LL))(
               v17,
               v16,
               *(unsigned __int8 *)(a1 + 48),
               *(unsigned __int8 *)(a1 + 49),
               *(_DWORD *)(a1 + 40));
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v36 = result;
      v18 = (__int64 *)RMToString((const enum _RADIO_CHANGE_REASON *)(a1 + 40));
      v13 = *(_BYTE *)(a1 + 49) == 0;
      v37 = (const char *)v18;
      v19 = "Enabled";
      if ( v13 )
        v19 = "Disabled";
      v13 = *(_BYTE *)(a1 + 48) == 0;
      v38 = (const wchar_t *)v19;
      v20 = "On";
      if ( v13 )
        v20 = "Off";
      v34 = (const wchar_t *)v20;
      v33 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
      v35 = (const wchar_t *)"RM_NOTIFY::INSTANCE_RADIO_CHANGE event";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
               v21,
               (unsigned __int8 *)word_18002F62A,
               v22,
               v23,
               &v35,
               (__int64 **)&v33,
               &v34,
               &v38,
               (const wchar_t **)&v37,
               (__int64)&v36);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ca54  mov     [rsp-18h+arg_8], rbx
0x18001ca59  push    rbp
0x18001ca5a  push    rsi
0x18001ca5b  push    rdi
0x18001ca5c  mov     rbp, rsp
0x18001ca5f  sub     rsp, 70h
0x18001ca63  mov     r8d, [rcx+2Ch]
0x18001ca67  mov     rbx, rcx
0x18001ca6a  test    r8d, r8d
0x18001ca6d  jz      loc_18001CCC2
0x18001ca73  sub     r8d, 1
0x18001ca77  jz      loc_18001CC72
0x18001ca7d  sub     r8d, 1
0x18001ca81  jz      loc_18001CB8E
0x18001ca87  cmp     r8d, 1
0x18001ca8b  jz      short loc_18001CAD6
0x18001ca8d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ca92  mov     eax, cs:dword_180037050
0x18001ca98  cmp     eax, 2
0x18001ca9b  jbe     loc_18001CD33
0x18001caa1  lea     rax, aInvalidEventTy; "Invalid event type"
0x18001caa8  mov     [rbp+arg_0], 80070057h
0x18001caaf  mov     [rbp+arg_10], rax
0x18001cab3  lea     rdx, byte_18002F577
0x18001caba  lea     rax, [rbp+arg_0]
0x18001cabe  mov     [rsp+70h+var_48], rax
0x18001cac3  lea     rax, [rbp+arg_10]
0x18001cac7  mov     [rsp+70h+var_50], rax
0x18001cacc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001cad1  jmp     loc_18001CD33
0x18001cad6  mov     rcx, [rdx]
0x18001cad9  movzx   r8d, byte ptr [rbx+31h]
0x18001cade  movzx   edx, byte ptr [rbx+30h]
0x18001cae2  mov     r9d, [rbx+28h]
0x18001cae6  mov     rax, [rcx]
0x18001cae9  mov     rax, [rax+28h]
0x18001caed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caf2  mov     edx, cs:dword_180037050
0x18001caf8  cmp     edx, 4
0x18001cafb  jbe     loc_18001CD33
0x18001cb01  lea     rcx, [rbx+28h]; enum _RADIO_CHANGE_REASON *
0x18001cb05  mov     [rbp+arg_0], eax
0x18001cb08  call    ?RMToString@@YAPEBDAEBW4_RADIO_CHANGE_REASON@@@Z; RMToString(_RADIO_CHANGE_REASON const &)
0x18001cb0d  cmp     byte ptr [rbx+31h], 0
0x18001cb11  lea     rcx, aDisabled; "Disabled"
0x18001cb18  mov     [rbp+arg_10], rax
0x18001cb1c  lea     rdx, word_18002F5BE
0x18001cb23  lea     rax, aEnabled_0; "Enabled"
0x18001cb2a  cmovz   rax, rcx
0x18001cb2e  cmp     byte ptr [rbx+30h], 0
0x18001cb32  mov     [rbp+arg_18], rax
0x18001cb36  lea     rcx, aOff; "Off"
0x18001cb3d  lea     rax, aOn; "On"
0x18001cb44  cmovz   rax, rcx
0x18001cb48  mov     [rbp+var_20], rax
0x18001cb4c  lea     rax, aRmNotifySystem; "RM_NOTIFY::SYSTEM_RADIO_CHANGE event"
0x18001cb53  mov     [rbp+var_18], rax
0x18001cb57  lea     rax, [rbp+arg_0]
0x18001cb5b  mov     [rsp+70h+var_30], rax
0x18001cb60  lea     rax, [rbp+arg_10]
0x18001cb64  mov     [rsp+70h+var_38], rax
0x18001cb69  lea     rax, [rbp+arg_18]
0x18001cb6d  mov     [rsp+70h+var_40], rax
0x18001cb72  lea     rax, [rbp+var_20]
0x18001cb76  mov     [rsp+70h+var_48], rax
0x18001cb7b  lea     rax, [rbp+var_18]
0x18001cb7f  mov     [rsp+70h+var_50], rax
0x18001cb84  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@333AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001cb89  jmp     loc_18001CD33
0x18001cb8e  mov     r11, [rdx]
0x18001cb91  add     rcx, 8
0x18001cb95  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cb9a  mov     rdx, [r11]
0x18001cb9d  mov     r10, rax
0x18001cba0  movzx   r9d, byte ptr [rbx+31h]
0x18001cba5  mov     rcx, r11
0x18001cba8  movzx   r8d, byte ptr [rbx+30h]
0x18001cbad  mov     rax, [rdx+30h]
0x18001cbb1  mov     edx, [rbx+28h]
0x18001cbb4  mov     dword ptr [rsp+70h+var_50], edx
0x18001cbb8  mov     rdx, r10
0x18001cbbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc0  mov     edx, cs:dword_180037050
0x18001cbc6  cmp     edx, 4
0x18001cbc9  jbe     loc_18001CD33
0x18001cbcf  lea     rcx, [rbx+28h]; enum _RADIO_CHANGE_REASON *
0x18001cbd3  mov     [rbp+arg_0], eax
0x18001cbd6  call    ?RMToString@@YAPEBDAEBW4_RADIO_CHANGE_REASON@@@Z; RMToString(_RADIO_CHANGE_REASON const &)
0x18001cbdb  cmp     byte ptr [rbx+31h], 0
0x18001cbdf  lea     rcx, aDisabled; "Disabled"
0x18001cbe6  mov     [rbp+arg_10], rax
0x18001cbea  lea     rax, aEnabled_0; "Enabled"
0x18001cbf1  cmovz   rax, rcx
0x18001cbf5  cmp     byte ptr [rbx+30h], 0
0x18001cbf9  mov     [rbp+arg_18], rax
0x18001cbfd  lea     rcx, aOff; "Off"
0x18001cc04  lea     rax, aOn; "On"
0x18001cc0b  cmovz   rax, rcx
0x18001cc0f  lea     rcx, [rbx+8]
0x18001cc13  mov     [rbp+var_18], rax
0x18001cc17  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cc1c  mov     [rbp+var_20], rax
0x18001cc20  lea     rdx, word_18002F62A
0x18001cc27  lea     rax, aRmNotifyInstan_1; "RM_NOTIFY::INSTANCE_RADIO_CHANGE event"
0x18001cc2e  mov     [rbp+var_10], rax
0x18001cc32  lea     rax, [rbp+arg_0]
0x18001cc36  mov     [rsp+70h+var_28], rax
0x18001cc3b  lea     rax, [rbp+arg_10]
0x18001cc3f  mov     [rsp+70h+var_30], rax
0x18001cc44  lea     rax, [rbp+arg_18]
0x18001cc48  mov     [rsp+70h+var_38], rax
0x18001cc4d  lea     rax, [rbp+var_18]
0x18001cc51  mov     [rsp+70h+var_40], rax
0x18001cc56  lea     rax, [rbp+var_20]
0x18001cc5a  mov     [rsp+70h+var_48], rax
0x18001cc5f  lea     rax, [rbp+var_10]
0x18001cc63  mov     [rsp+70h+var_50], rax
0x18001cc68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@333AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001cc6d  jmp     loc_18001CD33
0x18001cc72  mov     r9, [rdx]
0x18001cc75  add     rcx, 8
0x18001cc79  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cc7e  mov     rdx, [r9]
0x18001cc81  mov     rcx, r9
0x18001cc84  mov     r8, [rdx+20h]
0x18001cc88  mov     rdx, rax
0x18001cc8b  mov     rax, r8
0x18001cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc93  mov     edx, cs:dword_180037050
0x18001cc99  cmp     edx, 4
0x18001cc9c  jbe     loc_18001CD33
0x18001cca2  lea     rcx, [rbx+8]
0x18001cca6  mov     [rbp+arg_0], eax
0x18001cca9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ccae  mov     [rbp+arg_10], rax
0x18001ccb2  lea     rdx, word_18002F6A2
0x18001ccb9  lea     rax, aRmNotifyInstan; "RM_NOTIFY::INSTANCE_REMOVE event"
0x18001ccc0  jmp     short loc_18001CD0F
0x18001ccc2  mov     r10, [rdx]
0x18001ccc5  add     rcx, 8
0x18001ccc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ccce  mov     rdx, [r10]
0x18001ccd1  mov     r8, rax
0x18001ccd4  mov     rcx, r10
0x18001ccd7  mov     r9, [rdx+18h]
0x18001ccdb  mov     rdx, [rbx]
0x18001ccde  mov     rax, r9
0x18001cce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cce6  mov     edx, cs:dword_180037050
0x18001ccec  cmp     edx, 4
0x18001ccef  jbe     short loc_18001CD33
0x18001ccf1  lea     rcx, [rbx+8]
0x18001ccf5  mov     [rbp+arg_0], eax
0x18001ccf8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ccfd  mov     [rbp+arg_10], rax
0x18001cd01  lea     rdx, byte_18002F6F5
0x18001cd08  lea     rax, aRmNotifyInstan_0; "RM_NOTIFY::INSTANCE_ADD event"
0x18001cd0f  mov     [rbp+arg_18], rax
0x18001cd13  lea     rax, [rbp+arg_0]
0x18001cd17  mov     [rsp+70h+var_40], rax
0x18001cd1c  lea     rax, [rbp+arg_10]
0x18001cd20  mov     [rsp+70h+var_48], rax
0x18001cd25  lea     rax, [rbp+arg_18]
0x18001cd29  mov     [rsp+70h+var_50], rax
0x18001cd2e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18001cd33  mov     rbx, [rsp+70h+arg_8]
0x18001cd3b  add     rsp, 70h
0x18001cd3f  pop     rdi
0x18001cd40  pop     rsi
0x18001cd41  pop     rbp
0x18001cd42  retn
```
