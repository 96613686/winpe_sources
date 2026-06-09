# _RadioManager::_SetInstanceRadio_::_3_::_lambda_1_::operator()

- ea: `0x18001c7e0`
- end: `0x18001ca4d`
- name: `_RadioManager::_SetInstanceRadio_::_3_::_lambda_1_::operator()`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020cc0`

## callees

- `0x180001954`
- `0x180002000`
- `0x1800042b0`
- `0x180006a2c`
- `0x180007568`
- `0x18000b814`
- `0x18000d2a0`
- `0x18001c7e0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c877`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c877`

## string_xrefs

- `0x18001c9f1`: `IRadioInstanceInternal::SetInstanceRadioComplete failed`

## pseudocode

```c
signed int __fastcall RadioManager::_SetInstanceRadio_::_3_::_lambda_1_::operator()(__int64 a1)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  BOOL v5; // r14d
  unsigned int v6; // esi
  int v7; // eax
  __int64 v8; // rdx
  int v9; // edi
  const wchar_t *v10; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // rcx
  __int64 *v13; // rcx
  __int64 v14; // rax
  signed int result; // eax
  const char *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  BOOL v20; // [rsp+50h] [rbp+7h] BYREF
  const wchar_t *v21; // [rsp+58h] [rbp+Fh] BYREF
  const wchar_t *v22; // [rsp+60h] [rbp+17h] BYREF
  const char *v23; // [rsp+68h] [rbp+1Fh] BYREF
  const wchar_t *v24[2]; // [rsp+70h] [rbp+27h] BYREF
  int v25; // [rsp+80h] [rbp+37h] BYREF

  v25 = 1;
  v2 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 24) + 48LL))(*(_QWORD *)(a1 + 24), &v25);
  if ( v2 < 0 && (unsigned int)dword_180037050 > 2 )
  {
    v20 = v2;
    v21 = (const wchar_t *)"IRadioInstance::GetRadioState failed. Will default to DRS_SW_RADIO_OFF";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180037050,
      (unsigned __int8 *)&word_18002EC8E,
      v3,
      v4,
      &v21,
      (__int64)&v20);
  }
  v5 = *(_BYTE *)a1 == 0;
  v6 = 0;
  v20 = v5;
  do
  {
    Sleep(200 * v6);
    v7 = (*(__int64 (__fastcall **)(_QWORD, BOOL, __int64))(**(_QWORD **)(a1 + 24) + 56LL))(*(_QWORD *)(a1 + 24), v5, 5);
    v9 = v7;
    if ( v7 < 0 && (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v21) = v7;
      v10 = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)(a1 + 4));
      v22 = v11;
      v24[1] = v10;
      v23 = RMToString((const enum _DEVICE_RADIO_STATE *)&v20);
      v24[0] = (const wchar_t *)"IRadioInstance::SetRadioState failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v12,
        byte_18002EC25);
    }
    if ( v9 != -2144075729 && v9 != -2147019873 )
      break;
    ++v6;
  }
  while ( v6 <= 6 );
  v13 = *(__int64 **)(a1 + 32);
  v14 = *v13;
  if ( v9 >= 0 )
  {
    result = (*(__int64 (**)(void))(v14 + 96))();
    if ( result < 0 && (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v21) = result;
      v24[0] = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)(a1 + 4));
      v23 = (const char *)v17;
      v22 = (const wchar_t *)"IRadioInstanceInternal::SetInstanceRadioComplete failed";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
               v17,
               (unsigned __int8 *)byte_18002EB5D,
               v18,
               v19,
               &v22,
               (__int64 *)&v23,
               v24,
               (__int64)&v21);
    }
  }
  else
  {
    LOBYTE(v8) = v25 == 0;
    result = (*(__int64 (__fastcall **)(__int64 *, __int64))(v14 + 88))(v13, v8);
    if ( result < 0 && (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v21) = result;
      v24[0] = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)(a1 + 4));
      v23 = v16;
      v20 = v25 == 0;
      v22 = (const wchar_t *)"IRadioInstanceInternal::ResetInstanceRadioState failed";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
               v16,
               word_18002EBBA);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001c7e0  mov     [rsp-8+arg_8], rbx
0x18001c7e5  mov     [rsp-8+arg_10], rsi
0x18001c7ea  push    rbp
0x18001c7eb  push    rdi
0x18001c7ec  push    r14
0x18001c7ee  lea     rbp, [rsp-47h]
0x18001c7f3  sub     rsp, 90h
0x18001c7fa  mov     rax, cs:__security_cookie
0x18001c801  xor     rax, rsp
0x18001c804  mov     [rbp+57h+var_18], rax
0x18001c808  mov     rbx, rcx
0x18001c80b  mov     [rbp+57h+var_20], 1
0x18001c812  mov     rcx, [rcx+18h]
0x18001c816  lea     rdx, [rbp+57h+var_20]
0x18001c81a  mov     rax, [rcx]
0x18001c81d  mov     rax, [rax+30h]
0x18001c821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c826  test    eax, eax
0x18001c828  jns     short loc_18001C861
0x18001c82a  mov     ecx, cs:dword_180037050
0x18001c830  cmp     ecx, 2
0x18001c833  jbe     short loc_18001C861
0x18001c835  mov     [rbp+57h+var_50], eax
0x18001c838  lea     rdx, word_18002EC8E
0x18001c83f  lea     rax, aIradioinstance_0; "IRadioInstance::GetRadioState failed. W"...
0x18001c846  mov     [rbp+57h+var_48], rax
0x18001c84a  lea     rax, [rbp+57h+var_50]
0x18001c84e  mov     [rsp+0A0h+var_78], rax
0x18001c853  lea     rax, [rbp+57h+var_48]
0x18001c857  mov     [rsp+0A0h+var_80], rax
0x18001c85c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001c861  xor     r14d, r14d
0x18001c864  cmp     [rbx], r14b
0x18001c867  setz    r14b
0x18001c86b  xor     esi, esi
0x18001c86d  mov     [rbp+57h+var_50], r14d
0x18001c871  imul    ecx, esi, 0C8h; dwMilliseconds
0x18001c877  call    cs:__imp_Sleep
0x18001c87d  mov     rcx, [rbx+18h]
0x18001c881  mov     r8d, 5
0x18001c887  mov     edx, r14d
0x18001c88a  mov     rax, [rcx]
0x18001c88d  mov     rax, [rax+38h]
0x18001c891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c896  mov     edi, eax
0x18001c898  test    eax, eax
0x18001c89a  jns     short loc_18001C90C
0x18001c89c  mov     ecx, cs:dword_180037050
0x18001c8a2  cmp     ecx, 2
0x18001c8a5  jbe     short loc_18001C90C
0x18001c8a7  lea     rcx, [rbx+4]; struct _GUID *
0x18001c8ab  mov     dword ptr [rbp+57h+var_48], eax
0x18001c8ae  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001c8b3  mov     [rbp+57h+var_40], rcx
0x18001c8b7  lea     rcx, [rbp+57h+var_50]; enum _DEVICE_RADIO_STATE *
0x18001c8bb  mov     [rbp+57h+var_28], rax
0x18001c8bf  call    ?RMToString@@YAPEBDAEBW4_DEVICE_RADIO_STATE@@@Z; RMToString(_DEVICE_RADIO_STATE const &)
0x18001c8c4  mov     [rbp+57h+var_38], rax
0x18001c8c8  lea     rdx, byte_18002EC25
0x18001c8cf  lea     rax, aIradioinstance_6; "IRadioInstance::SetRadioState failed"
0x18001c8d6  mov     [rbp+57h+var_30], rax
0x18001c8da  lea     rax, [rbp+57h+var_48]
0x18001c8de  mov     [rsp+0A0h+var_60], rax
0x18001c8e3  lea     rax, [rbp+57h+var_28]
0x18001c8e7  mov     [rsp+0A0h+var_68], rax
0x18001c8ec  lea     rax, [rbp+57h+var_40]
0x18001c8f0  mov     [rsp+0A0h+var_70], rax
0x18001c8f5  lea     rax, [rbp+57h+var_38]
0x18001c8f9  mov     [rsp+0A0h+var_78], rax
0x18001c8fe  lea     rax, [rbp+57h+var_30]
0x18001c902  mov     [rsp+0A0h+var_80], rax
0x18001c907  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001c90c  cmp     edi, 8034002Fh
0x18001c912  jz      short loc_18001C91C
0x18001c914  cmp     edi, 8007139Fh
0x18001c91a  jnz     short loc_18001C927
0x18001c91c  inc     esi
0x18001c91e  cmp     esi, 6
0x18001c921  jbe     loc_18001C871
0x18001c927  mov     rcx, [rbx+20h]
0x18001c92b  mov     rax, [rcx]
0x18001c92e  test    edi, edi
0x18001c930  jns     loc_18001C9C2
0x18001c936  cmp     [rbp+57h+var_20], 0
0x18001c93a  mov     rax, [rax+58h]
0x18001c93e  setz    dl
0x18001c941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c946  test    eax, eax
0x18001c948  jns     loc_18001CA29
0x18001c94e  mov     ecx, cs:dword_180037050
0x18001c954  cmp     ecx, 2
0x18001c957  jbe     loc_18001CA29
0x18001c95d  lea     rcx, [rbx+4]; struct _GUID *
0x18001c961  mov     dword ptr [rbp+57h+var_48], eax
0x18001c964  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001c969  mov     [rbp+57h+var_30], rax
0x18001c96d  lea     rdx, word_18002EBBA
0x18001c974  xor     eax, eax
0x18001c976  mov     [rbp+57h+var_38], rcx
0x18001c97a  cmp     [rbp+57h+var_20], eax
0x18001c97d  setz    al
0x18001c980  mov     [rbp+57h+var_50], eax
0x18001c983  lea     rax, aIradioinstance_1; "IRadioInstanceInternal::ResetInstanceRa"...
0x18001c98a  mov     [rbp+57h+var_40], rax
0x18001c98e  lea     rax, [rbp+57h+var_48]
0x18001c992  mov     [rsp+0A0h+var_60], rax
0x18001c997  lea     rax, [rbp+57h+var_30]
0x18001c99b  mov     [rsp+0A0h+var_68], rax
0x18001c9a0  lea     rax, [rbp+57h+var_38]
0x18001c9a4  mov     [rsp+0A0h+var_70], rax
0x18001c9a9  lea     rax, [rbp+57h+var_50]
0x18001c9ad  mov     [rsp+0A0h+var_78], rax
0x18001c9b2  lea     rax, [rbp+57h+var_40]
0x18001c9b6  mov     [rsp+0A0h+var_80], rax
0x18001c9bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001c9c0  jmp     short loc_18001CA29
0x18001c9c2  mov     rax, [rax+60h]
0x18001c9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9cb  test    eax, eax
0x18001c9cd  jns     short loc_18001CA29
0x18001c9cf  mov     ecx, cs:dword_180037050
0x18001c9d5  cmp     ecx, 2
0x18001c9d8  jbe     short loc_18001CA29
0x18001c9da  lea     rcx, [rbx+4]; struct _GUID *
0x18001c9de  mov     dword ptr [rbp+57h+var_48], eax
0x18001c9e1  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001c9e6  mov     [rbp+57h+var_30], rax
0x18001c9ea  lea     rdx, byte_18002EB5D
0x18001c9f1  lea     rax, aIradioinstance; "IRadioInstanceInternal::SetInstanceRadi"...
0x18001c9f8  mov     [rbp+57h+var_38], rcx
0x18001c9fc  mov     [rbp+57h+var_40], rax
0x18001ca00  lea     rax, [rbp+57h+var_48]
0x18001ca04  mov     [rsp+0A0h+var_68], rax
0x18001ca09  lea     rax, [rbp+57h+var_30]
0x18001ca0d  mov     [rsp+0A0h+var_70], rax
0x18001ca12  lea     rax, [rbp+57h+var_38]
0x18001ca16  mov     [rsp+0A0h+var_78], rax
0x18001ca1b  lea     rax, [rbp+57h+var_40]
0x18001ca1f  mov     [rsp+0A0h+var_80], rax
0x18001ca24  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ca29  mov     rcx, [rbp+57h+var_18]
0x18001ca2d  xor     rcx, rsp; StackCookie
0x18001ca30  call    __security_check_cookie
0x18001ca35  lea     r11, [rsp+0A0h+var_10]
0x18001ca3d  mov     rbx, [r11+28h]
0x18001ca41  mov     rsi, [r11+30h]
0x18001ca45  mov     rsp, r11
0x18001ca48  pop     r14
0x18001ca4a  pop     rdi
0x18001ca4b  pop     rbp
0x18001ca4c  retn
```
