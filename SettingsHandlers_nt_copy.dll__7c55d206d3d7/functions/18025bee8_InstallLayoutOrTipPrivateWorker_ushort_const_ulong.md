# InstallLayoutOrTipPrivateWorker(ushort const *,ulong)

- ea: `0x18025bee8`
- end: `0x18025c7fb`
- name: `?InstallLayoutOrTipPrivateWorker@@YAHPEBGK@Z`
- size: `2323`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180256ba8`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x18001a64c`
- `0x1800234c4`
- `0x18003eaec`
- `0x18025649c`
- `0x180257054`
- `0x180259f60`
- `0x18025a060`
- `0x18025a0b8`
- `0x18025a20c`
- `0x18025a29c`
- `0x18025a35c`
- `0x18025a5c8`
- `0x18025a9b8`
- `0x18025ab48`
- `0x18025ac48`
- `0x18025b068`
- `0x18025b42c`
- `0x18025b64c`
- `0x18025bb78`
- `0x18025bd18`
- `0x18025bee8`
- `0x18025cde4`
- `0x18025d330`
- `0x18025d530`
- `0x18025da98`
- `0x18025dba8`
- `0x18025dc44`
- `0x18025dff8`
- `0x18025e154`
- `0x18025e49c`
- `0x180260cdc`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18025c687`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18025c687`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025c6a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18025c6a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18025c1a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18025c1a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025c6f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025c730`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025c741`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025c6f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025c730`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025c741`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18025c651`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18025c651`

## string_xrefs

- `0x18025c67e`: `Kernel32.dll`
- `0x18025bf8c`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x18025c06a`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x18025c12d`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x18025c2a4`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x18025c3af`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`

## pseudocode

```c
__int64 __fastcall InstallLayoutOrTipPrivateWorker(unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  int v6; // ebx
  int v7; // r12d
  unsigned int v8; // r14d
  bool IsLoaded; // r13
  __int64 v11; // rsi
  char v12; // r15
  unsigned __int16 *v13; // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // r9
  unsigned __int16 *v17; // rbx
  int v18; // esi
  int v19; // eax
  int v20; // r12d
  int *v21; // rbx
  int v22; // eax
  unsigned int v23; // edx
  __int64 v24; // rcx
  FARPROC ProcAddress; // rax
  int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  bool lpcSubKeysc; // [rsp+20h] [rbp-E0h]
  bool lpcSubKeysd; // [rsp+20h] [rbp-E0h]
  int lpcSubKeysb; // [rsp+20h] [rbp-E0h]
  _DWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v32; // [rsp+68h] [rbp-98h]
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  bool v37[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+98h] [rbp-68h]
  void **v39; // [rsp+A0h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-58h]
  _QWORD v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v42[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v43[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v44[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v45[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v46; // [rsp+F8h] [rbp-8h]
  _QWORD v47[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v48[2]; // [rsp+110h] [rbp+10h] BYREF
  int v49; // [rsp+120h] [rbp+20h]
  int v50; // [rsp+124h] [rbp+24h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  _BYTE v52[128]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v53[42]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v54[2]; // [rsp+300h] [rbp+200h] BYREF
  unsigned int HKLFromLayout; // [rsp+304h] [rbp+204h]
  int v56; // [rsp+30Ch] [rbp+20Ch]
  unsigned __int16 v57[39]; // [rsp+314h] [rbp+214h] BYREF
  unsigned __int16 v58[303]; // [rsp+362h] [rbp+262h] BYREF
  unsigned __int16 v59[40]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v60[40]; // [rsp+610h] [rbp+510h] BYREF
  unsigned __int16 v61[88]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v62[176]; // [rsp+710h] [rbp+610h] BYREF
  _BYTE v63[176]; // [rsp+7C0h] [rbp+6C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8C8h] [rbp+7C8h]

  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v53);
  v53[0] = &InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable';
  InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::StartActivity((InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker *)v53);
  v4 = 1;
  v5 = a2 >> 5;
  v6 = a2 & 0x40;
  LOBYTE(v5) = (a2 & 0x20) == 0;
  v49 = v6;
  LODWORD(pSid) = v5;
  v7 = a2 & 0x100;
  v8 = 0;
  IsLoaded = EnsureBcp47LangsLibraryIsLoaded();
  if ( (a2 & 0x40) != 0 && (a2 & 0x100) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4BD,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      lpcSubKeys);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 2147500037LL);
LABEL_4:
    InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::~InstallLayoutOrTipPrivateWorker((InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker *)v53);
    return 0;
  }
  v39 = &CInputDllEnumRegBase::`vftable';
  v48[0] = &CInputDllEnumRegBase::`vftable';
  *(_QWORD *)v37 = &CInputDllEnumRegBase::`vftable';
  v47[0] = &CInputDllEnumRegBase::`vftable';
  *(_QWORD *)v45 = &CInputDllEnumRegBase::`vftable';
  v44[0] = &CInputDllEnumRegBase::`vftable';
  v43[0] = &CInputDllEnumRegBase::`vftable';
  v42[0] = &CInputDllEnumRegBase::`vftable';
  v41[0] = &CInputDllEnumRegBase::`vftable';
  hKey = 0;
  v48[1] = 0;
  v38 = 0;
  v47[1] = 0;
  v46 = 0;
  v44[1] = 0;
  v43[1] = 0;
  v42[1] = 0;
  v41[1] = 0;
  if ( !InstallLayoutOrTipPrivateHelpers::OpenRegistryKeys(
          (struct CInputDllRegKey *)&v39,
          (struct CInputDllRegKey *)v48,
          (struct CInputDllRegKey *)v37,
          (struct CInputDllRegKey *)v47,
          (struct CInputDllRegKey *)v45,
          (struct CInputDllRegKey *)v44,
          (struct CInputDllRegKey *)v43,
          (struct CInputDllRegKey *)v42,
          (struct CInputDllRegKey *)v41,
          (a2 & 0x200) != 0) )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x4CE,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      lpcSubKeysa);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 2147500037LL);
    v41[0] = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v41);
    v42[0] = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v42);
    v43[0] = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v43);
    v44[0] = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v44);
    *(_QWORD *)v45 = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v45);
    v47[0] = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v47);
    *(_QWORD *)v37 = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v37);
    v48[0] = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v48);
    v39 = &CInputDllEnumRegBase::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v39);
    goto LABEL_4;
  }
  v51 = ParseItemString(a1);
  v11 = v51;
  if ( v51 )
  {
    v50 = a2 & 0x80;
    v12 = a2 & 1;
    cValues = 0;
    RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    CInputList::CInputList((CInputList *)v31, *(_DWORD *)(v11 + 16) + cValues);
    CInputList::CInputList((CInputList *)v35, *(_DWORD *)(v11 + 16) + 4);
    CSortOrder::CSortOrder((CSortOrder *)v52);
    InstallLayoutOrTipPrivateHelpers::ReadKeyboardRegistry(
      (struct CInputList *)v31,
      (struct CInputDllRegKey *)&v39,
      (struct CInputDllRegKey *)v48,
      (struct CInputDllRegKey *)v44,
      (struct CInputDllRegKey *)v37);
    InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
      (struct CInputList *)v35,
      (struct CInputDllRegKey *)v45,
      0,
      0,
      lpcSubKeysc);
    InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
      (struct CInputList *)v35,
      (struct CInputDllRegKey *)v43,
      1,
      1,
      lpcSubKeysd);
    InstallLayoutOrTipPrivateHelpers::ReadSortOrder(
      (struct CInputDllRegKey *)v42,
      (struct CInputDllRegKey *)v41,
      (struct CSortOrder *)v52);
    if ( v6 || v7 )
    {
      if ( v31[0] )
      {
        v13 = (unsigned __int16 *)v32;
        if ( v32 )
        {
          do
          {
            if ( v8 >= v31[1] )
              break;
            if ( *((_BYTE *)v13 + 16) )
            {
              *((_BYTE *)v13 + 16) = 0;
              if ( IsLoaded )
              {
                v14 = ((__int64 (__fastcall *)(_QWORD, _BYTE *, __int64))pfnBcp47BufferFromLcid)(*v13, v62, 85);
                if ( v14 >= 0 )
                {
                  v15 = *((_DWORD *)v13 + 1);
                  v16 = *v13;
                  v61[0] = 0;
                  lpcSubKeysb = v15;
                  StringCchPrintfW(v61, 0x57u, L"%04X:%08X", v16);
                  ((void (__fastcall *)(_BYTE *, __int64, unsigned __int16 *))pfnRemoveUserLanguageInputMethods)(
                    v62,
                    59,
                    v61);
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x4FF,
                    (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
                    (const char *)(unsigned int)v14,
                    lpcSubKeysb);
                }
              }
            }
            if ( ++v8 >= v31[0] )
              break;
            v13 = (unsigned __int16 *)((char *)v32 + 700 * v8);
          }
          while ( v13 );
          v8 = 0;
        }
      }
      if ( v35[0] )
      {
        v17 = (unsigned __int16 *)hMem;
        if ( hMem )
        {
          v18 = v49;
          do
          {
            if ( v8 >= v35[1] )
              break;
            if ( v17[10] && v17[49] && *((_BYTE *)v17 + 16) && (v7 && *((_BYTE *)v17 + 19) || v18) )
            {
              *((_BYTE *)v17 + 16) = 0;
              if ( IsLoaded )
              {
                v19 = ((__int64 (__fastcall *)(_QWORD, _BYTE *, __int64))pfnBcp47BufferFromLcid)(*v17, v63, 85);
                if ( v19 >= 0 )
                {
                  lpcSubKeysb = (_DWORD)v17 + 20;
                  StringCchPrintfW(v54, 0x57u, L"%04X:%s%s", *v17);
                  ((void (__fastcall *)(_BYTE *, __int64, unsigned __int16 *))pfnRemoveUserLanguageInputMethods)(
                    v63,
                    59,
                    v54);
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x518,
                    (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
                    (const char *)(unsigned int)v19,
                    lpcSubKeysb);
                }
              }
            }
            if ( ++v8 >= v35[0] )
              break;
            v17 = (unsigned __int16 *)((char *)hMem + 700 * v8);
          }
          while ( v17 );
          v11 = v51;
        }
        v8 = 0;
      }
      CSortOrder::Clear((CSortOrder *)v52);
    }
    if ( *(int *)(v11 + 16) > 0 )
    {
      v20 = v50;
      do
      {
        v21 = (int *)(*(_QWORD *)(v11 + 8) + (int)(*(_DWORD *)(v11 + 20) * v8));
        if ( v21 )
        {
          if ( *v21 == 1 )
          {
            if ( v12 || v20 )
              InstallLayoutOrTipPrivateHelpers::DisableKeyboard(
                *((_WORD *)v21 + 2),
                v21[2],
                (struct CInputList *)v31,
                IsLoaded);
            else
              InstallLayoutOrTipPrivateHelpers::EnableKeyboard(
                *((_WORD *)v21 + 2),
                v21[2],
                0,
                (struct CInputList *)v31,
                IsLoaded,
                (struct CInputDllRegKey *)v37,
                (struct CInputDllRegKey *)v47);
          }
          else if ( *v21 == 2 )
          {
            CLSIDToStringW((const struct _GUID *)(v21 + 3), v60);
            CLSIDToStringW((const struct _GUID *)(v21 + 7), v59);
            if ( v12 || v20 )
              InstallLayoutOrTipPrivateHelpers::DisableIme(
                *((_WORD *)v21 + 2),
                v60,
                v59,
                (struct CInputList *)v35,
                (struct CInputList *)v31,
                IsLoaded);
            else
              InstallLayoutOrTipPrivateHelpers::EnableIme(
                *((_WORD *)v21 + 2),
                v60,
                v59,
                (struct CInputList *)v35,
                (struct CInputList *)v31,
                IsLoaded,
                (struct CInputDllRegKey *)v43,
                (struct CInputDllRegKey *)v37,
                (struct CInputDllRegKey *)v47);
          }
          memset_0(v54, 0, 0x2BCu);
          v22 = *v21;
          v23 = v21[2];
          v54[0] = *((_WORD *)v21 + 2);
          v56 = v22;
          HKLFromLayout = (unsigned int)GetHKLFromLayout(v54[0], v23);
          CLSIDToStringW((const struct _GUID *)(v21 + 3), v57);
          CLSIDToStringW((const struct _GUID *)(v21 + 7), v58);
          if ( v12 || v20 )
            CSortOrder::RemoveAssemblyItem((CSortOrder *)v52, (struct InputContainer *)v54);
          else
            CSortOrder::AddAssemblyItem((CSortOrder *)v52, (struct InputContainer *)v54);
        }
        ++v8;
      }
      while ( (signed int)v8 < *(_DWORD *)(v11 + 16) );
    }
    InstallLayoutOrTipPrivateHelpers::WriteKeyboardRegistry(
      (struct CInputList *)v31,
      (bool)pSid,
      (struct CInputDllRegKey *)&v39,
      (struct CInputDllRegKey *)v48,
      (struct CInputDllRegKey *)v44);
    InstallLayoutOrTipPrivateHelpers::WriteImeRegistry((struct CInputList *)v35, (struct CInputDllRegKey *)v45);
    InstallLayoutOrTipPrivateHelpers::WriteSortOrder(
      (struct CInputDllRegKey *)v42,
      (struct CInputDllRegKey *)v41,
      (struct CSortOrder *)v52);
    pSid = 0;
    if ( !GetCurrentUserSid(&pSid) )
      goto LABEL_72;
    if ( !IsWellKnownSid(pSid, WinLocalSystemSid) && EnsureBcp47LangsLibraryIsLoaded() )
    {
      if ( hKernel32Dll )
      {
        ProcAddress = (FARPROC)pfnNotifyUiLanguageChange;
      }
      else
      {
        hKernel32Dll = (__int64)LoadLibraryExW(L"Kernel32.dll", 0, 0);
        v24 = hKernel32Dll;
        if ( hKernel32Dll )
        {
          ProcAddress = GetProcAddress((HMODULE)hKernel32Dll, "NotifyUILanguageChange");
          v24 = hKernel32Dll;
          pfnNotifyUiLanguageChange = (__int64)ProcAddress;
        }
        else
        {
          ProcAddress = (FARPROC)pfnNotifyUiLanguageChange;
        }
        if ( !v24 )
          goto LABEL_71;
      }
      if ( ProcAddress )
        ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(32, 0, 0, 0, 0);
    }
LABEL_71:
    LocalFree(pSid);
LABEL_72:
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
    (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
    CSortOrder::~CSortOrder((CSortOrder *)v52);
    LocalFree(hMem);
    LocalFree(v32);
    goto LABEL_73;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x4D4,
    (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
    (const char *)0x80004005LL,
    lpcSubKeysa);
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 2147500037LL);
  v4 = 0;
LABEL_73:
  v41[0] = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v41);
  v42[0] = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v42);
  v43[0] = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v43);
  v44[0] = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v44);
  *(_QWORD *)v45 = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v45);
  v47[0] = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v47);
  *(_QWORD *)v37 = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v37);
  v48[0] = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v48);
  v39 = &CInputDllEnumRegBase::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)&v39);
  InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::~InstallLayoutOrTipPrivateWorker((InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker *)v53);
  return v4;
}

```

## disassembly

```asm
0x18025bee8  push    rbp
0x18025beea  push    rbx
0x18025beeb  push    rsi
0x18025beec  push    rdi
0x18025beed  push    r12
0x18025beef  push    r13
0x18025bef1  push    r14
0x18025bef3  push    r15
0x18025bef5  lea     rbp, [rsp-788h]
0x18025befd  sub     rsp, 888h
0x18025bf04  mov     rax, cs:__security_cookie
0x18025bf0b  xor     rax, rsp
0x18025bf0e  mov     [rbp+7C0h+var_50], rax
0x18025bf15  mov     rsi, rcx
0x18025bf18  mov     r15d, edx
0x18025bf1b  lea     rcx, [rbp+7C0h+var_710]; struct wil::details::IFailureCallback *
0x18025bf22  call    ??0?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18025bf27  lea     rax, ??_7InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@6B@; const InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable'
0x18025bf2e  lea     rcx, [rbp+7C0h+var_710]; this
0x18025bf35  mov     [rbp+7C0h+var_710], rax
0x18025bf3c  call    ?StartActivity@InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@QEAAXXZ; InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::StartActivity(void)
0x18025bf41  mov     eax, r15d
0x18025bf44  mov     edi, 1
0x18025bf49  shr     eax, 5
0x18025bf4c  mov     ebx, r15d
0x18025bf4f  not     al
0x18025bf51  and     ebx, 40h
0x18025bf54  and     al, dil
0x18025bf57  mov     [rbp+7C0h+var_7A0], ebx
0x18025bf5a  mov     r12d, r15d
0x18025bf5d  mov     dword ptr [rsp+8C0h+pSid], eax
0x18025bf61  and     r12d, 100h
0x18025bf68  call    ?EnsureBcp47LangsLibraryIsLoaded@@YA_NXZ; EnsureBcp47LangsLibraryIsLoaded(void)
0x18025bf6d  mov     ecx, r15d
0x18025bf70  xor     r14d, r14d
0x18025bf73  shr     ecx, 9
0x18025bf76  mov     r13b, al
0x18025bf79  and     cl, dil
0x18025bf7c  test    ebx, ebx
0x18025bf7e  jz      short loc_18025BFC6
0x18025bf80  test    r12d, r12d
0x18025bf83  jz      short loc_18025BFC6
0x18025bf85  mov     rcx, [rbp+7C8h]; this
0x18025bf8c  lea     r8, aOnecoreWindows_0; "onecore\\windows\\advcore\\ctf\\inputse"...
0x18025bf93  mov     ebx, 80004005h
0x18025bf98  mov     edx, 4BDh; void *
0x18025bf9d  mov     r9d, ebx; char *
0x18025bfa0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18025bfa5  mov     edx, ebx
0x18025bfa7  lea     rcx, [rbp+7C0h+var_710]
0x18025bfae  call    ?Stop@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18025bfb3  lea     rcx, [rbp+7C0h+var_710]; this
0x18025bfba  call    ??1InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@QEAA@XZ; InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::~InstallLayoutOrTipPrivateWorker(void)
0x18025bfbf  xor     eax, eax
0x18025bfc1  jmp     loc_18025C7D7
0x18025bfc6  lea     rax, ??_7CInputDllEnumRegBase@@6B@; const CInputDllEnumRegBase::`vftable'
0x18025bfcd  mov     byte ptr [rsp+8C0h+lpcbMaxValueLen], cl; bool
0x18025bfd1  mov     [rbp+7C0h+var_820], rax
0x18025bfd5  lea     r9, [rbp+7C0h+var_7C0]; struct CInputDllRegKey *
0x18025bfd9  mov     [rbp+7C0h+var_7B0], rax
0x18025bfdd  lea     r8, [rbp+7C0h+var_830]; struct CInputDllRegKey *
0x18025bfe1  mov     qword ptr [rbp+7C0h+var_830], rax
0x18025bfe5  lea     rdx, [rbp+7C0h+var_7B0]; struct CInputDllRegKey *
0x18025bfe9  mov     [rbp+7C0h+var_7C0], rax
0x18025bfed  lea     rcx, [rbp+7C0h+var_820]; struct CInputDllRegKey *
0x18025bff1  mov     qword ptr [rbp+7C0h+var_7D0], rax
0x18025bff5  mov     [rbp+7C0h+var_7E0], rax
0x18025bff9  mov     [rbp+7C0h+var_7F0], rax
0x18025bffd  mov     [rbp+7C0h+var_800], rax
0x18025c001  mov     [rbp+7C0h+var_810], rax
0x18025c005  lea     rax, [rbp+7C0h+var_810]
0x18025c009  mov     [rsp+8C0h+lpcbMaxValueNameLen], rax; struct CInputDllRegKey *
0x18025c00e  lea     rax, [rbp+7C0h+var_800]
0x18025c012  mov     [rsp+8C0h+lpcValues], rax; struct CInputDllRegKey *
0x18025c017  lea     rax, [rbp+7C0h+var_7F0]
0x18025c01b  mov     [rsp+8C0h+lpcbMaxClassLen], rax; struct CInputDllRegKey *
0x18025c020  lea     rax, [rbp+7C0h+var_7E0]
0x18025c024  mov     [rsp+8C0h+lpcbMaxSubKeyLen], rax; struct CInputDllRegKey *
0x18025c029  lea     rax, [rbp+7C0h+var_7D0]
0x18025c02d  mov     [rsp+8C0h+lpcSubKeys], rax; int
0x18025c032  mov     [rbp+7C0h+hKey], r14
0x18025c036  mov     [rbp+7C0h+var_7A8], r14
0x18025c03a  mov     [rbp+7C0h+var_828], r14
0x18025c03e  mov     [rbp+7C0h+var_7B8], r14
0x18025c042  mov     [rbp+7C0h+var_7C8], r14
0x18025c046  mov     [rbp+7C0h+var_7D8], r14
0x18025c04a  mov     [rbp+7C0h+var_7E8], r14
0x18025c04e  mov     [rbp+7C0h+var_7F8], r14
0x18025c052  mov     [rbp+7C0h+var_808], r14
0x18025c056  call    ?OpenRegistryKeys@InstallLayoutOrTipPrivateHelpers@@SA_NAEAVCInputDllRegKey@@00000000_N@Z; InstallLayoutOrTipPrivateHelpers::OpenRegistryKeys(CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,bool)
0x18025c05b  test    al, al
0x18025c05d  jnz     loc_18025C112
0x18025c063  mov     rcx, [rbp+7C8h]; this
0x18025c06a  lea     r8, aOnecoreWindows_0; "onecore\\windows\\advcore\\ctf\\inputse"...
0x18025c071  mov     ebx, 80004005h
0x18025c076  mov     edx, 4CEh; void *
0x18025c07b  mov     r9d, ebx; char *
0x18025c07e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18025c083  mov     edx, ebx
0x18025c085  lea     rcx, [rbp+7C0h+var_710]
0x18025c08c  call    ?Stop@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18025c091  lea     rbx, ??_7CInputDllEnumRegBase@@6B@; const CInputDllEnumRegBase::`vftable'
0x18025c098  lea     rcx, [rbp+7C0h+var_810]; this
0x18025c09c  mov     [rbp+7C0h+var_810], rbx
0x18025c0a0  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c0a5  lea     rcx, [rbp+7C0h+var_800]; this
0x18025c0a9  mov     [rbp+7C0h+var_800], rbx
0x18025c0ad  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c0b2  lea     rcx, [rbp+7C0h+var_7F0]; this
0x18025c0b6  mov     [rbp+7C0h+var_7F0], rbx
0x18025c0ba  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c0bf  lea     rcx, [rbp+7C0h+var_7E0]; this
0x18025c0c3  mov     [rbp+7C0h+var_7E0], rbx
0x18025c0c7  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c0cc  lea     rcx, [rbp+7C0h+var_7D0]; this
0x18025c0d0  mov     qword ptr [rbp+7C0h+var_7D0], rbx
0x18025c0d4  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c0d9  lea     rcx, [rbp+7C0h+var_7C0]; this
0x18025c0dd  mov     [rbp+7C0h+var_7C0], rbx
0x18025c0e1  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c0e6  lea     rcx, [rbp+7C0h+var_830]; this
0x18025c0ea  mov     qword ptr [rbp+7C0h+var_830], rbx
0x18025c0ee  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c0f3  lea     rcx, [rbp+7C0h+var_7B0]; this
0x18025c0f7  mov     [rbp+7C0h+var_7B0], rbx
0x18025c0fb  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c100  lea     rcx, [rbp+7C0h+var_820]; this
0x18025c104  mov     [rbp+7C0h+var_820], rbx
0x18025c108  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18025c10d  jmp     loc_18025BFB3
0x18025c112  mov     rcx, rsi; unsigned __int16 *
0x18025c115  call    ?ParseItemString@@YAPEAV?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@PEBG@Z; ParseItemString(ushort const *)
0x18025c11a  mov     [rbp+7C0h+var_798], rax
0x18025c11e  mov     rsi, rax
0x18025c121  test    rax, rax
0x18025c124  jnz     short loc_18025C15C
0x18025c126  mov     rcx, [rbp+7C8h]; this
0x18025c12d  lea     r8, aOnecoreWindows_0; "onecore\\windows\\advcore\\ctf\\inputse"...
0x18025c134  mov     ebx, 80004005h
0x18025c139  mov     edx, 4D4h; void *
0x18025c13e  mov     r9d, ebx; char *
0x18025c141  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18025c146  mov     edx, ebx
0x18025c148  lea     rcx, [rbp+7C0h+var_710]
0x18025c14f  call    ?Stop@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18025c154  mov     edi, r14d
0x18025c157  jmp     loc_18025C74D
0x18025c15c  mov     rcx, [rbp+7C0h+hKey]; hKey
0x18025c160  mov     eax, r15d
0x18025c163  mov     [rsp+8C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18025c168  and     eax, 80h
0x18025c16d  mov     [rsp+8C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18025c172  xor     r9d, r9d; lpReserved
0x18025c175  mov     [rsp+8C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18025c17a  xor     r8d, r8d; lpcchClass
0x18025c17d  mov     [rsp+8C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18025c182  xor     edx, edx; lpClass
0x18025c184  mov     [rbp+7C0h+var_79C], eax
0x18025c187  and     r15b, dil
0x18025c18a  lea     rax, [rsp+8C0h+cValues]
0x18025c18f  mov     [rsp+8C0h+cValues], r14d
0x18025c194  mov     [rsp+8C0h+lpcValues], rax; lpcValues
0x18025c199  mov     [rsp+8C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18025c19e  mov     [rsp+8C0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18025c1a3  mov     [rsp+8C0h+lpcSubKeys], r14; lpcSubKeys
0x18025c1a8  call    cs:__imp_RegQueryInfoKeyW
0x18025c1af  nop     dword ptr [rax+rax+00h]
0x18025c1b4  mov     edx, [rsp+8C0h+cValues]
0x18025c1b8  lea     rcx, [rsp+8C0h+var_860]; this
0x18025c1bd  add     edx, [rsi+10h]; unsigned int
0x18025c1c0  call    ??0CInputList@@QEAA@I@Z; CInputList::CInputList(uint)
0x18025c1c5  mov     edx, [rsi+10h]
0x18025c1c8  lea     rcx, [rbp+7C0h+var_840]; this
0x18025c1cc  add     edx, 4; unsigned int
0x18025c1cf  call    ??0CInputList@@QEAA@I@Z; CInputList::CInputList(uint)
0x18025c1d4  lea     rcx, [rbp+7C0h+var_790]; this
0x18025c1d8  call    ??0CSortOrder@@QEAA@XZ; CSortOrder::CSortOrder(void)
0x18025c1dd  lea     rax, [rbp+7C0h+var_830]
0x18025c1e1  lea     r9, [rbp+7C0h+var_7E0]; struct CInputDllRegKey *
0x18025c1e5  mov     [rsp+8C0h+lpcSubKeys], rax; int
0x18025c1ea  lea     r8, [rbp+7C0h+var_7B0]; struct CInputDllRegKey *
0x18025c1ee  lea     rdx, [rbp+7C0h+var_820]; struct CInputDllRegKey *
0x18025c1f2  lea     rcx, [rsp+8C0h+var_860]; this
0x18025c1f7  call    ?ReadKeyboardRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@111@Z; InstallLayoutOrTipPrivateHelpers::ReadKeyboardRegistry(CInputList &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &)
0x18025c1fc  xor     r9d, r9d; bool
0x18025c1ff  lea     rdx, [rbp+7C0h+var_7D0]; struct CInputDllRegKey *
0x18025c203  xor     r8d, r8d; bool
0x18025c206  lea     rcx, [rbp+7C0h+var_840]; this
0x18025c20a  call    ?EnumCtfRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@_N22@Z; InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(CInputList &,CInputDllRegKey &,bool,bool,bool)
0x18025c20f  mov     r9b, dil; bool
0x18025c212  lea     rdx, [rbp+7C0h+var_7F0]; struct CInputDllRegKey *
0x18025c216  mov     r8b, dil; bool
0x18025c219  lea     rcx, [rbp+7C0h+var_840]; this
0x18025c21d  call    ?EnumCtfRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@_N22@Z; InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(CInputList &,CInputDllRegKey &,bool,bool,bool)
0x18025c222  lea     r8, [rbp+7C0h+var_790]; struct CSortOrder *
0x18025c226  lea     rdx, [rbp+7C0h+var_810]; struct CInputDllRegKey *
0x18025c22a  lea     rcx, [rbp+7C0h+var_800]; struct CInputDllRegKey *
0x18025c22e  call    ?ReadSortOrder@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputDllRegKey@@0AEAVCSortOrder@@@Z; InstallLayoutOrTipPrivateHelpers::ReadSortOrder(CInputDllRegKey &,CInputDllRegKey &,CSortOrder &)
0x18025c233  test    ebx, ebx
0x18025c235  jnz     short loc_18025C240
0x18025c237  test    r12d, r12d
0x18025c23a  jz      loc_18025C441
0x18025c240  cmp     [rsp+8C0h+var_860], r14d
0x18025c245  jbe     loc_18025C327
0x18025c24b  mov     rbx, [rsp+8C0h+var_858]
0x18025c250  xor     edx, edx
0x18025c252  test    rbx, rbx
0x18025c255  jz      loc_18025C327
0x18025c25b  cmp     r14d, [rsp+8C0h+var_85C]
0x18025c260  jnb     loc_18025C324
0x18025c266  cmp     [rbx+10h], dl
0x18025c269  jz      loc_18025C305
0x18025c26f  mov     [rbx+10h], dl
0x18025c272  test    r13b, r13b
0x18025c275  jz      loc_18025C305
0x18025c27b  movzx   ecx, word ptr [rbx]
0x18025c27e  lea     rdx, [rbp+7C0h+var_1B0]
0x18025c285  mov     rax, cs:pfnBcp47BufferFromLcid
0x18025c28c  mov     r8d, 55h ; 'U'
0x18025c292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c297  xor     ecx, ecx
0x18025c299  test    eax, eax
0x18025c29b  jns     short loc_18025C2BA
0x18025c29d  mov     rcx, [rbp+7C8h]; this
0x18025c2a4  lea     r8, aOnecoreWindows_0; "onecore\\windows\\advcore\\ctf\\inputse"...
0x18025c2ab  mov     r9d, eax; char *
0x18025c2ae  mov     edx, 4FFh; void *
0x18025c2b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18025c2b8  jmp     short loc_18025C303
0x18025c2ba  mov     eax, [rbx+4]
0x18025c2bd  lea     r8, a04x08x; "%04X:%08X"
0x18025c2c4  movzx   r9d, word ptr [rbx]
0x18025c2c8  mov     edx, 57h ; 'W'; unsigned __int64
0x18025c2cd  mov     [rbp+7C0h+var_260], cx
0x18025c2d4  lea     rcx, [rbp+7C0h+var_260]; unsigned __int16 *
0x18025c2db  mov     dword ptr [rsp+8C0h+lpcSubKeys], eax; int
0x18025c2df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18025c2e4  mov     rax, cs:pfnRemoveUserLanguageInputMethods
0x18025c2eb  lea     r8, [rbp+7C0h+var_260]
0x18025c2f2  mov     edx, 3Bh ; ';'
0x18025c2f7  lea     rcx, [rbp+7C0h+var_1B0]
0x18025c2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c303  xor     edx, edx
0x18025c305  add     r14d, edi
0x18025c308  cmp     r14d, [rsp+8C0h+var_860]
0x18025c30d  jnb     short loc_18025C324
0x18025c30f  mov     eax, r14d
0x18025c312  imul    rbx, rax, 2BCh
0x18025c319  add     rbx, [rsp+8C0h+var_858]
0x18025c31e  jnz     loc_18025C25B
0x18025c324  xor     r14d, r14d
0x18025c327  cmp     [rbp+7C0h+var_840], r14d
0x18025c32b  jbe     loc_18025C438
0x18025c331  mov     rbx, [rbp+7C0h+hMem]
0x18025c335  xor     edx, edx
0x18025c337  test    rbx, rbx
0x18025c33a  jz      loc_18025C435
0x18025c340  mov     esi, [rbp+7C0h+var_7A0]
0x18025c343  cmp     r14d, [rbp+7C0h+var_83C]
0x18025c347  jnb     loc_18025C431
0x18025c34d  cmp     [rbx+14h], dx
0x18025c351  jz      loc_18025C414
0x18025c357  cmp     [rbx+62h], dx
0x18025c35b  jz      loc_18025C414
0x18025c361  cmp     [rbx+10h], dl
0x18025c364  jz      loc_18025C414
0x18025c36a  test    r12d, r12d
0x18025c36d  jz      short loc_18025C374
0x18025c36f  cmp     [rbx+13h], dl
0x18025c372  jnz     short loc_18025C37C
0x18025c374  test    esi, esi
0x18025c376  jz      loc_18025C414
0x18025c37c  mov     [rbx+10h], dl
0x18025c37f  test    r13b, r13b
0x18025c382  jz      loc_18025C414
0x18025c388  movzx   ecx, word ptr [rbx]
0x18025c38b  lea     rdx, [rbp+7C0h+var_100]
0x18025c392  mov     rax, cs:pfnBcp47BufferFromLcid
0x18025c399  mov     r8d, 55h ; 'U'
0x18025c39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c3a4  test    eax, eax
0x18025c3a6  jns     short loc_18025C3C5
0x18025c3a8  mov     rcx, [rbp+7C8h]; this
0x18025c3af  lea     r8, aOnecoreWindows_0; "onecore\\windows\\advcore\\ctf\\inputse"...
0x18025c3b6  mov     r9d, eax; char *
0x18025c3b9  mov     edx, 518h; void *
0x18025c3be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18025c3c3  jmp     short loc_18025C412
0x18025c3c5  movzx   r9d, word ptr [rbx]
0x18025c3c9  lea     rax, [rbx+62h]
0x18025c3cd  mov     [rsp+8C0h+lpcbMaxSubKeyLen], rax
0x18025c3d2  lea     r8, a04xSS; "%04X:%s%s"
0x18025c3d9  lea     rax, [rbx+14h]
0x18025c3dd  mov     edx, 57h ; 'W'; unsigned __int64
0x18025c3e2  lea     rcx, [rbp+7C0h+var_5C0]; unsigned __int16 *
0x18025c3e9  mov     [rsp+8C0h+lpcSubKeys], rax
0x18025c3ee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18025c3f3  mov     rax, cs:pfnRemoveUserLanguageInputMethods
0x18025c3fa  lea     r8, [rbp+7C0h+var_5C0]
0x18025c401  mov     edx, 3Bh ; ';'
  ... truncated ...
```
