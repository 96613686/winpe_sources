# OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute(Windows::Internal::String const &,Windows::Internal::String const &)

- ea: `0x18003efc0`
- end: `0x18003f4ad`
- name: `?AddAttribute@CExtensionRegistration@Internal@DEH@OSIntegration@@UEAA_NAEBVString@2Windows@@0@Z`
- size: `1261`
- prototype: `bool __fastcall(OSIntegration::DEH::Internal::CExtensionRegistration *__hidden this, const struct Windows::Internal::String *, const struct Windows::Internal::String *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callees

- `0x18003efc0`
- `0x180073fc4`
- `0x180074000`
- `0x180074248`
- `0x180074504`
- `0x18008a740`
- `0x1800d7ad0`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003efed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003f0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003efed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18003f0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003f081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003f0bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003f081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003f0bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003f06e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003f06e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f34b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f34b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f375`

## string_xrefs

- `0x18003f01f`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18003f0c8`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\extensioncatalogcollector.cpp`
- `0x18003f018`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18003f0ef`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18003f3ac`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18003f3dc`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18003f42f`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18003f480`: `OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute`
- `0x18003f3a0`: `_spAttributesCollisionMap->Insert(keyName, keyName, &fReplaced)`
- `0x18003f474`: `_spAttributesCollisionMap->Remove(keyName)`
- `0x18003f423`: `_spPropertyValueFactory->CreateString(value, &spPropertyValue)`
- `0x18003f2f7`: `OSIntegration::DEH::Internal::CExtensionRegistration::CheckAttributeNameDoesNotCollide`
- `0x18003f329`: `OSIntegration::DEH::Internal::CExtensionRegistration::CheckAttributeNameDoesNotCollide`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute(
        OSIntegration::DEH::Internal::CExtensionRegistration *this,
        HSTRING *a2,
        HSTRING *a3)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, _QWORD *); // r12
  __int64 v7; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // r13d
  unsigned int v17; // r13d
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // rbx
  int v19; // eax
  int v20; // edi
  __int64 v21; // rcx
  int v22; // eax
  char v23; // di
  int v24; // eax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rcx
  wil::details *v30; // [rsp+28h] [rbp-38h]
  int v31; // [rsp+30h] [rbp-30h]
  __int64 *v32; // [rsp+30h] [rbp-30h]
  __int64 v33; // [rsp+38h] [rbp-28h] BYREF
  int v34; // [rsp+40h] [rbp-20h]
  __int64 *v35; // [rsp+48h] [rbp-18h]
  __int64 (__fastcall ***v36)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 (__fastcall ***hasEmbedNull)(_QWORD, GUID *, _QWORD *); // [rsp+A8h] [rbp+48h] BYREF
  char v40; // [rsp+B8h] [rbp+58h] BYREF

  v6 = 0;
  LODWORD(hasEmbedNull) = 0;
  WindowsStringHasEmbeddedNull(*a2, (BOOL *)&hasEmbedNull);
  if ( (_DWORD)hasEmbedNull
    || WindowsIsStringEmpty(*a2)
    || WindowsGetStringLen(*a2) > 0x7FFF
    || (LODWORD(hasEmbedNull) = 0, WindowsStringHasEmbeddedNull(*a3, (BOOL *)&hasEmbedNull), (_DWORD)hasEmbedNull) )
  {
    LODWORD(v30) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
      "((HRESULT)0x80080204L)",
      v30,
      v31);
    if ( (byte_180245605 & 0x20) != 0 )
      McTemplateU0d_EventWriteTransfer(v7, &AttributeNameInvalid, 2148008452LL);
    LODWORD(hasEmbedNull) = -2146958844;
    SetAppXErrorFromLogMessage(
      -2146958844,
      &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
      &AttributeNameInvalid,
      1u,
      &hasEmbedNull);
    return 0;
  }
  if ( WindowsGetStringLen(*a2) > 0x3FFF )
  {
    LODWORD(v30) = -2146958844;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
      "((HRESULT)0x80080204L)",
      v30,
      v31);
    if ( (byte_180245605 & 0x20) != 0 )
      McTemplateU0d_EventWriteTransfer(v10, &AttributeNameInvalidLength, 2148008452LL);
    details::appxLog<long>(-2146958844, v9, &AttributeNameInvalidLength, -2146958844);
  }
  LOBYTE(hasEmbedNull) = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _QWORD *))(**((_QWORD **)this + 8) + 64LL))(
          *((_QWORD *)this + 8),
          *a2,
          &hasEmbedNull);
  if ( v11 < 0 )
  {
    LODWORD(v30) = v11;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::CheckAttributeNameDoesNotCollide",
      "_spAttributesCollisionMap->HasKey(keyName, &fHasKey)",
      v30,
      v31);
  }
  if ( (_BYTE)hasEmbedNull )
  {
    LODWORD(v30) = -2147024809;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::CheckAttributeNameDoesNotCollide",
      "((HRESULT)0x80070057L)",
      v30,
      v31);
    if ( (byte_180245605 & 0x20) != 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*a2, 0);
      McTemplateU0dz_EventWriteTransfer(
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context,
        CollidingAttributeNames,
        2147942487LL,
        StringRawBuffer);
    }
    v26 = WindowsGetStringRawBuffer(*a2, 0);
    details::appxLog<long,unsigned short const *>(
      -2147024809,
      v27,
      (const struct _EVENT_DESCRIPTOR *)CollidingAttributeNames,
      -2147024809,
      v26);
    return 0;
  }
  v40 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, HSTRING, char *))(**((_QWORD **)this + 8) + 80LL))(
          *((_QWORD *)this + 8),
          *a2,
          *a2,
          &v40);
  if ( v12 < 0 )
  {
    LODWORD(v30) = v12;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
      "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
      "_spAttributesCollisionMap->Insert(keyName, keyName, &fReplaced)",
      v30,
      v31);
    v23 = 0;
  }
  else
  {
    v33 = 0;
    v34 = 0;
    v13 = (__int64 *)*((_QWORD *)this + 9);
    v14 = *v13;
    v35 = &v33;
    v36 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v14 + 144))(v13, *a3, &v36);
    v16 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v30) = v15;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
        "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
        "_spPropertyValueFactory->CreateString(value, &spPropertyValue)",
        v30,
        v31);
    }
    v17 = v16 >> 31;
    v32 = v35;
    v18 = v36;
    if ( v36 )
    {
      hasEmbedNull = 0;
      v19 = (**v36)(v36, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &hasEmbedNull);
      v20 = v19;
      if ( v19 < 0 )
      {
        if ( v19 == -2147467262 )
        {
          v6 = v18;
          v20 = 3;
        }
        else
        {
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v18)[2])(v18);
        }
      }
      else
      {
        v6 = hasEmbedNull;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v18)[2])(v18);
        v20 = 7;
      }
    }
    else
    {
      v20 = 0;
    }
    v21 = *v32;
    *v32 = (__int64)v6;
    v22 = *((_DWORD *)v32 + 2);
    *((_DWORD *)v32 + 2) = v20;
    if ( v21 && ((v22 - 3) & 0xFFFFFFFB) == 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( (_BYTE)v17
      || (v23 = 1,
          (*(int (__fastcall **)(_QWORD, HSTRING, __int64, char *))(**((_QWORD **)this + 7) + 80LL))(
            *((_QWORD *)this + 7),
            *a2,
            v33,
            &v40) < 0) )
    {
      v23 = 0;
      v24 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8), *a2);
      if ( v24 < 0 )
      {
        LODWORD(v30) = v24;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0xE3,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
          "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
          "_spAttributesCollisionMap->Remove(keyName)",
          v30,
          (int)v32);
      }
    }
    if ( v33 && ((v34 - 3) & 0xFFFFFFFB) == 0 )
      (*(void (**)(void))(*(_QWORD *)v33 + 16LL))();
    if ( v23 )
      return v23;
  }
  LODWORD(v30) = -2147024882;
  wil::details::in1diag5::_Log_Hr(
    retaddr,
    (void *)0xEC,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\extensioncatalogcollector.cpp",
    "OSIntegration::DEH::Internal::CExtensionRegistration::AddAttribute",
    "((HRESULT)0x8007000EL)",
    v30,
    (int)v32);
  if ( (byte_180245605 & 0x20) != 0 )
    McTemplateU0d_EventWriteTransfer(v29, &CollectorIsOutOfMemory, 2147942414LL);
  details::appxLog<long>(-2147024882, v28, &CollectorIsOutOfMemory, -2147024882);
  return v23;
}

```

## disassembly

```asm
0x18003efc0  mov     [rsp-38h+arg_0], rcx
0x18003efc5  push    rbp
0x18003efc6  push    rbx
0x18003efc7  push    rsi
0x18003efc8  push    rdi
0x18003efc9  push    r12
0x18003efcb  push    r13
0x18003efcd  push    r14
0x18003efcf  mov     rbp, rsp
0x18003efd2  sub     rsp, 60h
0x18003efd6  mov     rdi, r8
0x18003efd9  mov     rsi, rdx
0x18003efdc  mov     r13, rcx
0x18003efdf  xor     r12d, r12d
0x18003efe2  mov     dword ptr [rbp+hasEmbedNull], r12d
0x18003efe6  lea     rdx, [rbp+hasEmbedNull]; hasEmbedNull
0x18003efea  mov     rcx, [rsi]; string
0x18003efed  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18003eff4  nop     dword ptr [rax+rax+00h]
0x18003eff9  cmp     dword ptr [rbp+hasEmbedNull], r12d
0x18003effd  jz      short loc_18003F06B
0x18003efff  mov     rcx, [rbp+38h]; this
0x18003f003  mov     ebx, 80080204h
0x18003f008  mov     dword ptr [rsp+60h+var_38], ebx; wil::details *
0x18003f00c  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18003f013  mov     [rsp+60h+var_40], rax; char *
0x18003f018  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f01f  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003f026  mov     edx, 0B5h; void *
0x18003f02b  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f030  test    cs:byte_180245605, 20h
0x18003f037  jnz     loc_18003F499
0x18003f03d  mov     dword ptr [rbp+hasEmbedNull], ebx
0x18003f040  lea     rax, [rbp+hasEmbedNull]
0x18003f044  mov     [rsp+60h+var_40], rax
0x18003f049  mov     r9d, 1; unsigned int
0x18003f04f  lea     r8, AttributeNameInvalid; struct _EVENT_DESCRIPTOR *
0x18003f056  lea     rdx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID; struct _GUID *
0x18003f05d  mov     ecx, ebx; int
0x18003f05f  call    ?SetAppXErrorFromLogMessage@@YAJJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@KZZ; SetAppXErrorFromLogMessage(long,_GUID const &,_EVENT_DESCRIPTOR const &,ulong,...)
0x18003f064  xor     al, al
0x18003f066  jmp     loc_18003F277
0x18003f06b  mov     rcx, [rsi]; string
0x18003f06e  call    cs:__imp_WindowsIsStringEmpty
0x18003f075  nop     dword ptr [rax+rax+00h]
0x18003f07a  test    eax, eax
0x18003f07c  jnz     short loc_18003EFFF
0x18003f07e  mov     rcx, [rsi]; string
0x18003f081  call    cs:__imp_WindowsGetStringLen
0x18003f088  nop     dword ptr [rax+rax+00h]
0x18003f08d  cmp     eax, 7FFFh
0x18003f092  ja      loc_18003EFFF
0x18003f098  mov     dword ptr [rbp+hasEmbedNull], r12d
0x18003f09c  lea     rdx, [rbp+hasEmbedNull]; hasEmbedNull
0x18003f0a0  mov     rcx, [rdi]; string
0x18003f0a3  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18003f0aa  nop     dword ptr [rax+rax+00h]
0x18003f0af  cmp     dword ptr [rbp+hasEmbedNull], r12d
0x18003f0b3  jnz     loc_18003EFFF
0x18003f0b9  mov     rcx, [rsi]; string
0x18003f0bc  call    cs:__imp_WindowsGetStringLen
0x18003f0c3  nop     dword ptr [rax+rax+00h]
0x18003f0c8  lea     r14, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003f0cf  cmp     eax, 3FFFh
0x18003f0d4  jbe     short loc_18003F12C
0x18003f0d6  mov     rcx, [rbp+38h]; this
0x18003f0da  mov     ebx, 80080204h
0x18003f0df  mov     dword ptr [rsp+60h+var_38], ebx; wil::details *
0x18003f0e3  lea     rax, aHresult0x80080; "((HRESULT)0x80080204L)"
0x18003f0ea  mov     [rsp+60h+var_40], rax; char *
0x18003f0ef  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f0f6  mov     r8, r14; unsigned int
0x18003f0f9  mov     edx, 0BFh; void *
0x18003f0fe  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f103  test    cs:byte_180245605, 20h
0x18003f10a  jz      short loc_18003F11B
0x18003f10c  mov     r8d, ebx
0x18003f10f  lea     rdx, AttributeNameInvalidLength
0x18003f116  call    McTemplateU0d_EventWriteTransfer
0x18003f11b  mov     r9d, ebx
0x18003f11e  lea     r8, AttributeNameInvalidLength
0x18003f125  mov     ecx, ebx
0x18003f127  call    ??$appxLog@J@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@J@Z; details::appxLog<long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long)
0x18003f12c  mov     byte ptr [rbp+hasEmbedNull], r12b
0x18003f130  mov     rcx, [r13+40h]
0x18003f134  mov     rax, [rcx]
0x18003f137  lea     r8, [rbp+hasEmbedNull]
0x18003f13b  mov     rdx, [rsi]
0x18003f13e  mov     rax, [rax+40h]
0x18003f142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f147  mov     rcx, [rbp+38h]; this
0x18003f14b  test    eax, eax
0x18003f14d  js      loc_18003F2E7
0x18003f153  cmp     byte ptr [rbp+hasEmbedNull], r12b
0x18003f157  jnz     loc_18003F310
0x18003f15d  mov     [rbp+arg_18], r12b
0x18003f161  mov     rcx, [r13+40h]
0x18003f165  mov     rax, [rcx]
0x18003f168  lea     r9, [rbp+arg_18]
0x18003f16c  mov     r8, [rsi]
0x18003f16f  mov     rdx, r8
0x18003f172  mov     rax, [rax+50h]
0x18003f176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f17b  mov     rcx, [rbp+38h]; this
0x18003f17f  test    eax, eax
0x18003f181  js      loc_18003F39C
0x18003f187  mov     [rbp+var_28], r12
0x18003f18b  mov     [rbp+var_20], r12d
0x18003f18f  mov     rcx, [r13+48h]
0x18003f193  mov     rax, [rcx]
0x18003f196  lea     rdx, [rbp+var_28]
0x18003f19a  mov     [rbp+var_18], rdx
0x18003f19e  mov     [rbp+var_10], r12
0x18003f1a2  lea     r8, [rbp+var_10]
0x18003f1a6  mov     rdx, [rdi]
0x18003f1a9  mov     rax, [rax+90h]
0x18003f1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1b5  mov     r13d, eax
0x18003f1b8  mov     rcx, [rbp+38h]; this
0x18003f1bc  test    eax, eax
0x18003f1be  js      loc_18003F41E
0x18003f1c4  shr     r13d, 1Fh
0x18003f1c8  mov     rax, [rbp+var_18]
0x18003f1cc  mov     [rbp+var_30], rax
0x18003f1d0  mov     rbx, [rbp+var_10]
0x18003f1d4  test    rbx, rbx
0x18003f1d7  jz      loc_18003F287
0x18003f1dd  mov     [rbp+hasEmbedNull], r12
0x18003f1e1  mov     rax, [rbx]
0x18003f1e4  lea     r8, [rbp+hasEmbedNull]
0x18003f1e8  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18003f1ef  mov     rcx, rbx
0x18003f1f2  mov     rax, [rax]
0x18003f1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1fa  mov     edi, eax
0x18003f1fc  test    eax, eax
0x18003f1fe  js      loc_18003F448
0x18003f204  mov     r12, [rbp+hasEmbedNull]
0x18003f208  mov     rax, [rbx]
0x18003f20b  mov     rcx, rbx
0x18003f20e  mov     rax, [rax+10h]
0x18003f212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f217  mov     edi, 7
0x18003f21c  mov     rbx, [rbp+var_30]
0x18003f220  mov     rcx, [rbx]
0x18003f223  mov     [rbx], r12
0x18003f226  mov     eax, [rbx+8]
0x18003f229  mov     [rbx+8], edi
0x18003f22c  mov     r12d, 0FFFFFFFBh
0x18003f232  test    rcx, rcx
0x18003f235  jnz     short loc_18003F28B
0x18003f237  mov     rbx, [rbp+arg_0]
0x18003f23b  test    r13b, r13b
0x18003f23e  jz      short loc_18003F2BA
0x18003f240  xor     dil, dil
0x18003f243  mov     rcx, [rbx+40h]
0x18003f247  mov     rax, [rcx]
0x18003f24a  mov     rdx, [rsi]
0x18003f24d  mov     rax, [rax+58h]
0x18003f251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f256  mov     rcx, [rbp+38h]; this
0x18003f25a  test    eax, eax
0x18003f25c  js      loc_18003F470
0x18003f262  mov     rcx, [rbp+var_28]
0x18003f266  test    rcx, rcx
0x18003f269  jnz     short loc_18003F2A1
0x18003f26b  test    dil, dil
0x18003f26e  jz      loc_18003F3C3
0x18003f274  mov     al, dil
0x18003f277  add     rsp, 60h
0x18003f27b  pop     r14
0x18003f27d  pop     r13
0x18003f27f  pop     r12
0x18003f281  pop     rdi
0x18003f282  pop     rsi
0x18003f283  pop     rbx
0x18003f284  pop     rbp
0x18003f285  retn
0x18003f287  xor     edi, edi
0x18003f289  jmp     short loc_18003F21C
0x18003f28b  add     eax, 0FFFFFFFDh
0x18003f28e  test    r12d, eax
0x18003f291  jnz     short loc_18003F237
0x18003f293  mov     rax, [rcx]
0x18003f296  mov     rax, [rax+10h]
0x18003f29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f29f  jmp     short loc_18003F237
0x18003f2a1  mov     eax, [rbp+var_20]
0x18003f2a4  add     eax, 0FFFFFFFDh
0x18003f2a7  test    r12d, eax
0x18003f2aa  jnz     short loc_18003F26B
0x18003f2ac  mov     rax, [rcx]
0x18003f2af  mov     rax, [rax+10h]
0x18003f2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2b8  jmp     short loc_18003F26B
0x18003f2ba  mov     edi, 1
0x18003f2bf  mov     rcx, [rbx+38h]
0x18003f2c3  mov     rax, [rcx]
0x18003f2c6  lea     r9, [rbp+arg_18]
0x18003f2ca  mov     r8, [rbp+var_28]
0x18003f2ce  mov     rdx, [rsi]
0x18003f2d1  mov     rax, [rax+50h]
0x18003f2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2da  test    eax, eax
0x18003f2dc  js      loc_18003F240
0x18003f2e2  jmp     loc_18003F262
0x18003f2e7  mov     dword ptr [rsp+60h+var_38], eax; wil::details *
0x18003f2eb  lea     rax, aSpattributesco; "_spAttributesCollisionMap->HasKey(keyNa"...
0x18003f2f2  mov     [rsp+60h+var_40], rax; char *
0x18003f2f7  lea     r9, aOsintegrationD_357; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f2fe  mov     r8, r14; unsigned int
0x18003f301  mov     edx, 181h; void *
0x18003f306  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f30b  jmp     loc_18003F153
0x18003f310  mov     rcx, [rbp+38h]; this
0x18003f314  mov     ebx, 80070057h
0x18003f319  mov     dword ptr [rsp+60h+var_38], ebx; wil::details *
0x18003f31d  lea     rax, aHresult0x80070; "((HRESULT)0x80070057L)"
0x18003f324  mov     [rsp+60h+var_40], rax; char *
0x18003f329  lea     r9, aOsintegrationD_357; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f330  mov     r8, r14; unsigned int
0x18003f333  mov     edx, 189h; void *
0x18003f338  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f33d  test    cs:byte_180245605, 20h
0x18003f344  jz      short loc_18003F370
0x18003f346  xor     edx, edx; length
0x18003f348  mov     rcx, [rsi]; string
0x18003f34b  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f352  nop     dword ptr [rax+rax+00h]
0x18003f357  mov     r9, rax
0x18003f35a  mov     r8d, ebx
0x18003f35d  lea     rdx, CollidingAttributeNames
0x18003f364  lea     rcx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID_Context
0x18003f36b  call    McTemplateU0dz_EventWriteTransfer
0x18003f370  xor     edx, edx; length
0x18003f372  mov     rcx, [rsi]; string
0x18003f375  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f37c  nop     dword ptr [rax+rax+00h]
0x18003f381  mov     [rsp+60h+var_40], rax
0x18003f386  mov     r9d, ebx
0x18003f389  lea     r8, CollidingAttributeNames
0x18003f390  mov     ecx, ebx
0x18003f392  call    ??$appxLog@JPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEBG@Z; details::appxLog<long,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort const *)
0x18003f397  jmp     loc_18003F064
0x18003f39c  mov     dword ptr [rsp+60h+var_38], eax; wil::details *
0x18003f3a0  lea     rax, aSpattributesco_0; "_spAttributesCollisionMap->Insert(keyNa"...
0x18003f3a7  mov     [rsp+60h+var_40], rax; char *
0x18003f3ac  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f3b3  mov     r8, r14; unsigned int
0x18003f3b6  mov     edx, 0CBh; void *
0x18003f3bb  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f3c0  mov     dil, r12b
0x18003f3c3  mov     rcx, [rbp+38h]; this
0x18003f3c7  mov     ebx, 8007000Eh
0x18003f3cc  mov     dword ptr [rsp+60h+var_38], ebx; wil::details *
0x18003f3d0  lea     rax, aHresult0x80070_0; "((HRESULT)0x8007000EL)"
0x18003f3d7  mov     [rsp+60h+var_40], rax; char *
0x18003f3dc  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f3e3  mov     r8, r14; unsigned int
0x18003f3e6  mov     edx, 0ECh; void *
0x18003f3eb  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f3f0  test    cs:byte_180245605, 20h
0x18003f3f7  jz      short loc_18003F408
0x18003f3f9  mov     r8d, ebx
0x18003f3fc  lea     rdx, CollectorIsOutOfMemory
0x18003f403  call    McTemplateU0d_EventWriteTransfer
0x18003f408  mov     r9d, ebx
0x18003f40b  lea     r8, CollectorIsOutOfMemory
0x18003f412  mov     ecx, ebx
0x18003f414  call    ??$appxLog@J@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@J@Z; details::appxLog<long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long)
0x18003f419  jmp     loc_18003F274
0x18003f41e  mov     dword ptr [rsp+60h+var_38], r13d; wil::details *
0x18003f423  lea     rax, aSppropertyvalu; "_spPropertyValueFactory->CreateString(v"...
0x18003f42a  mov     [rsp+60h+var_40], rax; char *
0x18003f42f  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f436  mov     r8, r14; unsigned int
0x18003f439  mov     edx, 0D6h; void *
0x18003f43e  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f443  jmp     loc_18003F1C4
0x18003f448  cmp     eax, 80004002h
0x18003f44d  jnz     short loc_18003F45C
0x18003f44f  mov     r12, rbx
0x18003f452  mov     edi, 3
0x18003f457  jmp     loc_18003F21C
0x18003f45c  mov     rax, [rbx]
0x18003f45f  mov     rcx, rbx
0x18003f462  mov     rax, [rax+10h]
0x18003f466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f46b  jmp     loc_18003F21C
0x18003f470  mov     dword ptr [rsp+60h+var_38], eax; wil::details *
0x18003f474  lea     rax, aSpattributesco_1; "_spAttributesCollisionMap->Remove(keyNa"...
0x18003f47b  mov     [rsp+60h+var_40], rax; char *
0x18003f480  lea     r9, aOsintegrationD_319; "OSIntegration::DEH::Internal::CExtensio"...
0x18003f487  mov     r8, r14; unsigned int
0x18003f48a  mov     edx, 0E3h; void *
0x18003f48f  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003f494  jmp     loc_18003F262
0x18003f499  mov     r8d, ebx
0x18003f49c  lea     rdx, AttributeNameInvalid
0x18003f4a3  call    McTemplateU0d_EventWriteTransfer
  ... truncated ...
```
