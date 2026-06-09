# CFileActivatedEventArgs::get_NeighboringFilesQuery(Windows::Storage::Search::IStorageFileQueryResult * *)

- ea: `0x180022c60`
- end: `0x18002332d`
- name: `?get_NeighboringFilesQuery@CFileActivatedEventArgs@@UEAAJPEAPEAUIStorageFileQueryResult@Search@Storage@Windows@@@Z`
- size: `1741`
- prototype: `__int64 __fastcall(CFileActivatedEventArgs *this, struct Windows::Storage::Search::IStorageFileQueryResult **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180010a34`
- `0x180011328`
- `0x180022c60`
- `0x1800234f8`
- `0x180023620`
- `0x18003de5c`
- `0x18003eed0`
- `0x18003f284`
- `0x180048324`
- `0x18004b874`
- `0x18004df14`
- `0x18004eec8`
- `0x18004ef68`
- `0x18004f570`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002327e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002327e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022cd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002321c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002328f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022cd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002321c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002328f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022fbe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022fbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ec6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ec6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002301f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002301f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fa8`

## pseudocode

```c
__int64 __fastcall CFileActivatedEventArgs::get_NeighboringFilesQuery(
        CFileActivatedEventArgs *this,
        struct Windows::Storage::Search::IStorageFileQueryResult **a2)
{
  Microsoft::WRL::AgileRef *v3; // rcx
  unsigned int v5; // ebx
  char v6; // bl
  __int64 v7; // r9
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD); // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rdi
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, GUID *, __int64 *); // rbx
  int v19; // eax
  int CallingProcessHandle; // eax
  unsigned __int16 **v21; // r8
  char *v22; // rcx
  bool v23; // cc
  int PackageFamilyNameFromProcess; // eax
  bool *v25; // r8
  __int64 v26; // rdx
  void *v27; // rdx
  void **v28; // r9
  unsigned __int8 v29; // r15
  char v30; // bl
  void *v31; // rdx
  bool *v32; // r9
  char *v33; // rcx
  HRESULT v34; // eax
  int v35; // eax
  __int64 v36; // rcx
  char *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v41)(_QWORD, GUID *, __int64 *); // rdi
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64, LPVOID, _QWORD); // rbx
  __int64 v45; // rax
  int v46; // eax
  char *v47; // rcx
  int v48; // eax
  GUID *v50; // [rsp+20h] [rbp-99h]
  unsigned __int16 v51; // [rsp+40h] [rbp-79h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-71h] BYREF
  __int64 v53; // [rsp+50h] [rbp-69h] BYREF
  __int64 v54; // [rsp+58h] [rbp-61h] BYREF
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-59h] BYREF
  __int64 v56; // [rsp+68h] [rbp-51h] BYREF
  __int64 v57; // [rsp+70h] [rbp-49h] BYREF
  __int64 v58; // [rsp+78h] [rbp-41h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-39h] BYREF
  HANDLE v60; // [rsp+88h] [rbp-31h] BYREF
  int v61; // [rsp+90h] [rbp-29h] BYREF
  LPVOID pv[3]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v63; // [rsp+B0h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-1h] BYREF
  HSTRING string; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v3 = (CFileActivatedEventArgs *)((char *)this + 360);
  *a2 = 0;
  v63 = 0;
  if ( *(_QWORD *)v3 )
  {
    v5 = Microsoft::WRL::AgileRef::InternalResolve(v3, &GUID_52fda447_2baa_412c_b29f_d4b1778efa1e, (void **)a2);
LABEL_74:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
    return v5;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  v6 = *((_BYTE *)this + 432);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  if ( !v6 )
  {
    v53 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
    v7 = *((_QWORD *)this + 44);
    v8 = 0;
    v53 = 0;
    if ( v7 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v7 + 24LL))(
             v7,
             &GUID_85575a41_06cb_58d0_b98a_7c8f06e6e9d7,
             &v53);
      v5 = v9;
      if ( v9 < 0 )
      {
        v10 = 61;
LABEL_7:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)v9,
          (int)v50);
LABEL_8:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
        goto LABEL_74;
      }
      v8 = v53;
    }
    v61 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 56LL))(v8, &v61);
    v5 = v9;
    if ( v9 < 0 )
    {
      v10 = 64;
      goto LABEL_7;
    }
    if ( v61 == 1 )
    {
      v11 = v53;
      v55 = 0;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v53 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      v13 = v12(v11, 0, &v55);
      v5 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)v13,
          (int)v50);
LABEL_15:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
        goto LABEL_8;
      }
      v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v55;
      v54 = 0;
      v15 = **v55;
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v54);
      v16 = v15(v14, &GUID_d75c13bb_3883_4bd2_9b7a_334ff6d83066, &v54);
      v5 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)v16,
          (int)v50);
LABEL_18:
        Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v54);
        goto LABEL_15;
      }
      v17 = v54;
      v56 = 0;
      v18 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v54 + 24LL);
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v56);
      v19 = v18(v17, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v56);
      v5 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)v19,
          (int)v50);
LABEL_21:
        Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v56);
        goto LABEL_18;
      }
      hObject = 0;
      CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(4096, 0, &hObject);
      v5 = CallingProcessHandle;
      if ( CallingProcessHandle < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)CallingProcessHandle,
          (int)v50);
LABEL_24:
        v22 = (char *)hObject;
        hObject = 0;
        v23 = (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_25;
      }
      pv[0] = 0;
      pv[1] = (LPVOID)-1LL;
      pv[2] = (LPVOID)-1LL;
      PackageFamilyNameFromProcess = CallerIdentity::GetPackageFamilyNameFromProcess(hObject, pv, v21);
      v5 = PackageFamilyNameFromProcess;
      if ( PackageFamilyNameFromProcess < 0 )
      {
        v26 = 82;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)PackageFamilyNameFromProcess,
          (int)v50);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
        goto LABEL_24;
      }
      LOBYTE(v51) = 0;
      PackageFamilyNameFromProcess = CallerIdentity::IsProcessAppContainer(hObject, &v51, v25);
      v5 = PackageFamilyNameFromProcess;
      if ( PackageFamilyNameFromProcess < 0 )
      {
        v26 = 85;
        goto LABEL_29;
      }
      v29 = v51;
      if ( (_BYTE)v51 )
      {
        v30 = 0;
        v60 = 0;
        if ( CallerIdentity::GetImpersonationTokenFromProcess((CallerIdentity *)hObject, v27, (unsigned int)&v60, v28) >= 0 )
        {
          LOBYTE(v51) = 0;
          CapabilityCheckHelpers::CapabilityCheck((CapabilityCheckHelpers *)v60, v31, &v51, v32);
          v30 = v51;
        }
        v33 = (char *)v60;
        v60 = 0;
        if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v33);
        if ( v30 )
          v29 = 0;
      }
      v59 = 0;
      v57 = 0;
      string = 0;
      v34 = WindowsCreateStringReference(
              L"Windows.Storage.NeighboringFilesQueryFactory",
              0x2Cu,
              &hstringHeader,
              &string);
      if ( v34 < 0 )
      {
        RaiseException(v34, 1u, 0, 0);
        __debugbreak();
      }
      v35 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IInspectable>>(string, &v59);
      v5 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)v35,
          (int)v50);
        v36 = v57;
        if ( v57 )
        {
          v57 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
        v37 = (char *)hObject;
        hObject = 0;
        if ( (unsigned __int64)(v37 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v37);
        v38 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        }
        v39 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        }
        goto LABEL_15;
      }
      v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
      v41 = **v59;
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v57);
      v42 = v41(v40, &GUID_a9c88282_c261_4c26_ae97_21a4c8a3e19b, &v57);
      v5 = v42;
      if ( v42 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)(unsigned int)v42,
          (int)v50);
LABEL_54:
        Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v57);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
        v22 = (char *)hObject;
        hObject = 0;
LABEL_55:
        v23 = (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_25:
        if ( v23 )
          CloseHandle(v22);
        goto LABEL_21;
      }
      v43 = v57;
      v58 = 0;
      v44 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID, _QWORD))(*(_QWORD *)v57 + 24LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
      v50 = &GUID_52fda447_2baa_412c_b29f_d4b1778efa1e;
      v5 = v44(v43, v56, pv[0], v29);
      if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147023728 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
          (const char *)v5,
          (int)&GUID_52fda447_2baa_412c_b29f_d4b1778efa1e);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
        goto LABEL_54;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
      if ( !*((_BYTE *)this + 432) )
      {
        if ( *((_QWORD *)this + 53) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( v58 )
        {
          v60 = (char *)this + 424;
          v45 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v60);
          v46 = Microsoft::WRL::AsAgile<Windows::Storage::Search::IStorageFileQueryResult>(v58, v45);
          v5 = v46;
          if ( v46 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6F,
              (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
              (const char *)(unsigned int)v46,
              (int)&GUID_52fda447_2baa_412c_b29f_d4b1778efa1e);
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
            Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v57);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
            v22 = (char *)hObject;
            hObject = 0;
            goto LABEL_55;
          }
        }
        *((_BYTE *)this + 432) = 1;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pv);
      v47 = (char *)hObject;
      hObject = 0;
      if ( (unsigned __int64)(v47 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v47);
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v54);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
      *((_BYTE *)this + 432) = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  if ( *((_QWORD *)this + 53) )
  {
    v48 = Microsoft::WRL::AgileRef::InternalResolve(
            (CFileActivatedEventArgs *)((char *)this + 424),
            &GUID_52fda447_2baa_412c_b29f_d4b1778efa1e,
            (void **)a2);
    v5 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\fileactivated.cpp",
        (const char *)(unsigned int)v48,
        (int)v50);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
      goto LABEL_74;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
  return 0;
}

```

## disassembly

```asm
0x180022c60  mov     [rsp-8+arg_10], rbx
0x180022c65  push    rbp
0x180022c66  push    rsi
0x180022c67  push    rdi
0x180022c68  push    r12
0x180022c6a  push    r13
0x180022c6c  push    r14
0x180022c6e  push    r15
0x180022c70  lea     rbp, [rsp-27h]
0x180022c75  sub     rsp, 0E0h
0x180022c7c  mov     rax, cs:__security_cookie
0x180022c83  xor     rax, rsp
0x180022c86  mov     [rbp+57h+var_38], rax
0x180022c8a  xor     r15d, r15d
0x180022c8d  mov     r14, rcx
0x180022c90  add     rcx, 168h; this
0x180022c97  mov     [rdx], r15
0x180022c9a  mov     r13, rdx
0x180022c9d  mov     [rbp+57h+var_60], r15
0x180022ca1  cmp     [rcx], r15
0x180022ca4  jz      short loc_180022CBC
0x180022ca6  mov     r8, rdx; void **
0x180022ca9  lea     rdx, _GUID_52fda447_2baa_412c_b29f_d4b1778efa1e; struct _GUID *
0x180022cb0  call    ?InternalResolve@AgileRef@WRL@Microsoft@@IEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::AgileRef::InternalResolve(_GUID const &,void * *)
0x180022cb5  mov     ebx, eax
0x180022cb7  jmp     loc_1800232E5
0x180022cbc  lea     rsi, [r14+180h]
0x180022cc3  mov     rcx, rsi; lpCriticalSection
0x180022cc6  call    cs:__imp_EnterCriticalSection
0x180022ccc  mov     bl, [r14+1B0h]
0x180022cd3  mov     rcx, rsi; lpCriticalSection
0x180022cd6  call    cs:__imp_LeaveCriticalSection
0x180022cdc  lea     r12, _GUID_52fda447_2baa_412c_b29f_d4b1778efa1e
0x180022ce3  test    bl, bl
0x180022ce5  jnz     loc_18002329E
0x180022ceb  lea     rcx, [rbp+57h+var_C0]
0x180022cef  mov     [rbp+57h+var_C0], r15
0x180022cf3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022cf8  mov     r9, [r14+160h]
0x180022cff  mov     rcx, r15
0x180022d02  mov     [rbp+57h+var_C0], rcx
0x180022d06  test    r9, r9
0x180022d09  jz      short loc_180022D55
0x180022d0b  mov     rax, [r9]
0x180022d0e  lea     r8, [rbp+57h+var_C0]
0x180022d12  lea     rdx, _GUID_85575a41_06cb_58d0_b98a_7c8f06e6e9d7
0x180022d19  mov     rcx, r9
0x180022d1c  mov     rax, [rax+18h]
0x180022d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d25  mov     ebx, eax
0x180022d27  test    eax, eax
0x180022d29  jns     short loc_180022D51
0x180022d2b  mov     edx, 3Dh ; '='; void *
0x180022d30  mov     rcx, [rbp+5Fh]; this
0x180022d34  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x180022d3b  mov     r9d, eax; char *
0x180022d3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d43  lea     rcx, [rbp+57h+var_C0]
0x180022d47  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022d4c  jmp     loc_1800232E5
0x180022d51  mov     rcx, [rbp+57h+var_C0]
0x180022d55  mov     [rbp+57h+var_80], r15d
0x180022d59  lea     rdx, [rbp+57h+var_80]
0x180022d5d  mov     rax, [rcx]
0x180022d60  mov     rax, [rax+38h]
0x180022d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d69  mov     ebx, eax
0x180022d6b  test    eax, eax
0x180022d6d  jns     short loc_180022D76
0x180022d6f  mov     edx, 40h ; '@'
0x180022d74  jmp     short loc_180022D30
0x180022d76  cmp     [rbp+57h+var_80], 1
0x180022d7a  jnz     loc_18002327B
0x180022d80  mov     rdi, [rbp+57h+var_C0]
0x180022d84  lea     rcx, [rbp+57h+var_B0]
0x180022d88  mov     [rbp+57h+var_B0], r15
0x180022d8c  mov     rax, [rdi]
0x180022d8f  mov     rbx, [rax+30h]
0x180022d93  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022d98  lea     r8, [rbp+57h+var_B0]
0x180022d9c  xor     edx, edx
0x180022d9e  mov     rcx, rdi
0x180022da1  mov     rax, rbx
0x180022da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022da9  mov     ebx, eax
0x180022dab  test    eax, eax
0x180022dad  jns     short loc_180022DD5
0x180022daf  mov     rcx, [rbp+5Fh]; this
0x180022db3  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x180022dba  mov     r9d, eax; char *
0x180022dbd  mov     edx, 45h ; 'E'; void *
0x180022dc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022dc7  lea     rcx, [rbp+57h+var_B0]
0x180022dcb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180022dd0  jmp     loc_180022D43
0x180022dd5  mov     rbx, [rbp+57h+var_B0]
0x180022dd9  lea     rcx, [rbp+57h+var_B8]
0x180022ddd  mov     [rbp+57h+var_B8], r15
0x180022de1  mov     rax, [rbx]
0x180022de4  mov     rdi, [rax]
0x180022de7  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x180022dec  lea     r8, [rbp+57h+var_B8]
0x180022df0  mov     rcx, rbx
0x180022df3  lea     rdx, _GUID_d75c13bb_3883_4bd2_9b7a_334ff6d83066
0x180022dfa  mov     rax, rdi
0x180022dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e02  mov     ebx, eax
0x180022e04  test    eax, eax
0x180022e06  jns     short loc_180022E2B
0x180022e08  mov     rcx, [rbp+5Fh]; this
0x180022e0c  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x180022e13  mov     r9d, eax; char *
0x180022e16  mov     edx, 48h ; 'H'; void *
0x180022e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e20  lea     rcx, [rbp+57h+var_B8]
0x180022e24  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x180022e29  jmp     short loc_180022DC7
0x180022e2b  mov     rdi, [rbp+57h+var_B8]
0x180022e2f  lea     rcx, [rbp+57h+var_A8]
0x180022e33  mov     [rbp+57h+var_A8], r15
0x180022e37  mov     rax, [rdi]
0x180022e3a  mov     rbx, [rax+18h]
0x180022e3e  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x180022e43  lea     r8, [rbp+57h+var_A8]
0x180022e47  mov     rcx, rdi
0x180022e4a  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180022e51  mov     rax, rbx
0x180022e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e59  mov     ebx, eax
0x180022e5b  test    eax, eax
0x180022e5d  jns     short loc_180022E82
0x180022e5f  mov     rcx, [rbp+5Fh]; this
0x180022e63  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x180022e6a  mov     r9d, eax; char *
0x180022e6d  mov     edx, 4Ch ; 'L'; void *
0x180022e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e77  lea     rcx, [rbp+57h+var_A8]
0x180022e7b  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x180022e80  jmp     short loc_180022E20
0x180022e82  lea     r8, [rbp+57h+hObject]
0x180022e86  mov     [rbp+57h+hObject], r15
0x180022e8a  xor     edx, edx
0x180022e8c  mov     ecx, 1000h
0x180022e91  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180022e96  mov     ebx, eax
0x180022e98  test    eax, eax
0x180022e9a  jns     short loc_180022ECE
0x180022e9c  mov     rcx, [rbp+5Fh]; this
0x180022ea0  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x180022ea7  mov     r9d, eax; char *
0x180022eaa  mov     edx, 4Fh ; 'O'; void *
0x180022eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022eb4  mov     rcx, [rbp+57h+hObject]; hObject
0x180022eb8  mov     [rbp+57h+hObject], r15
0x180022ebc  lea     rdx, [rcx-1]
0x180022ec0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180022ec4  ja      short loc_180022E77
0x180022ec6  call    cs:__imp_CloseHandle
0x180022ecc  jmp     short loc_180022E77
0x180022ece  mov     rcx, [rbp+57h+hObject]; hProcess
0x180022ed2  lea     rdx, [rbp+57h+pv]; void *
0x180022ed6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022eda  mov     [rbp+57h+pv], r15
0x180022ede  mov     [rbp+57h+var_70], rax
0x180022ee2  mov     [rbp+57h+var_68], rax
0x180022ee6  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x180022eeb  mov     ebx, eax
0x180022eed  test    eax, eax
0x180022eef  jns     short loc_180022F14
0x180022ef1  mov     edx, 52h ; 'R'; void *
0x180022ef6  mov     rcx, [rbp+5Fh]; this
0x180022efa  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x180022f01  mov     r9d, eax; char *
0x180022f04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f09  lea     rcx, [rbp+57h+pv]
0x180022f0d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180022f12  jmp     short loc_180022EB4
0x180022f14  mov     rcx, [rbp+57h+hObject]; ProcessHandle
0x180022f18  lea     rdx, [rbp+57h+var_D0]; void *
0x180022f1c  mov     byte ptr [rbp+57h+var_D0], r15b
0x180022f20  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x180022f25  mov     ebx, eax
0x180022f27  test    eax, eax
0x180022f29  jns     short loc_180022F32
0x180022f2b  mov     edx, 55h ; 'U'
0x180022f30  jmp     short loc_180022EF6
0x180022f32  movzx   r15d, byte ptr [rbp+57h+var_D0]
0x180022f37  xor     edi, edi
0x180022f39  test    r15b, r15b
0x180022f3c  jz      short loc_180022F88
0x180022f3e  mov     rcx, [rbp+57h+hObject]; this
0x180022f42  lea     r8, [rbp+57h+var_88]; unsigned int
0x180022f46  mov     bl, dil
0x180022f49  mov     [rbp+57h+var_88], rdi
0x180022f4d  call    ?GetImpersonationTokenFromProcess@CallerIdentity@@YAJPEAXKPEAPEAX@Z; CallerIdentity::GetImpersonationTokenFromProcess(void *,ulong,void * *)
0x180022f52  test    eax, eax
0x180022f54  js      short loc_180022F6A
0x180022f56  mov     rcx, [rbp+57h+var_88]; this
0x180022f5a  lea     r8, [rbp+57h+var_D0]; unsigned __int16 *
0x180022f5e  mov     byte ptr [rbp+57h+var_D0], dil
0x180022f62  call    ?CapabilityCheck@CapabilityCheckHelpers@@YAJPEAXPEBGPEA_N@Z; CapabilityCheckHelpers::CapabilityCheck(void *,ushort const *,bool *)
0x180022f67  mov     bl, byte ptr [rbp+57h+var_D0]
0x180022f6a  mov     rcx, [rbp+57h+var_88]; hObject
0x180022f6e  mov     [rbp+57h+var_88], rdi
0x180022f72  lea     rax, [rcx-1]
0x180022f76  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022f7a  ja      short loc_180022F82
0x180022f7c  call    cs:__imp_CloseHandle
0x180022f82  test    bl, bl
0x180022f84  cmovnz  r15d, edi
0x180022f88  lea     r9, [rbp+57h+string]; string
0x180022f8c  mov     [rbp+57h+var_90], rdi
0x180022f90  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180022f94  mov     [rbp+57h+var_A0], rdi
0x180022f98  mov     edx, 2Ch ; ','; length
0x180022f9d  mov     [rbp+57h+string], rdi
0x180022fa1  lea     rcx, aWindowsStorage; "Windows.Storage.NeighboringFilesQueryFa"...
0x180022fa8  call    cs:__imp_WindowsCreateStringReference
0x180022fae  test    eax, eax
0x180022fb0  jns     short loc_180022FC5
0x180022fb2  xor     r9d, r9d; lpArguments
0x180022fb5  xor     r8d, r8d; nNumberOfArguments
0x180022fb8  mov     ecx, eax; dwExceptionCode
0x180022fba  lea     edx, [r9+1]; dwExceptionFlags
0x180022fbe  call    cs:__imp_RaiseException
0x180022fc4  int     3; Trap to Debugger
0x180022fc5  mov     rcx, [rbp+57h+string]
0x180022fc9  lea     rdx, [rbp+57h+var_90]
0x180022fcd  call    ??$ActivateInstance@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IInspectable>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x180022fd2  mov     ebx, eax
0x180022fd4  test    eax, eax
0x180022fd6  jns     loc_180023078
0x180022fdc  mov     rcx, [rbp+5Fh]; this
0x180022fe0  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x180022fe7  mov     r9d, eax; char *
0x180022fea  mov     edx, 5Fh ; '_'; void *
0x180022fef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ff4  mov     rcx, [rbp+57h+var_A0]
0x180022ff8  test    rcx, rcx
0x180022ffb  jz      short loc_18002300D
0x180022ffd  mov     [rbp+57h+var_A0], rdi
0x180023001  mov     rax, [rcx]
0x180023004  mov     rax, [rax+10h]
0x180023008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002300d  lea     rcx, [rbp+57h+var_90]
0x180023011  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180023016  mov     rcx, [rbp+57h+pv]; pv
0x18002301a  test    rcx, rcx
0x18002301d  jz      short loc_180023025
0x18002301f  call    cs:__imp_CoTaskMemFree
0x180023025  mov     rcx, [rbp+57h+hObject]; hObject
0x180023029  mov     [rbp+57h+hObject], rdi
0x18002302d  lea     rax, [rcx-1]
0x180023031  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023035  ja      short loc_18002303D
0x180023037  call    cs:__imp_CloseHandle
0x18002303d  mov     rcx, [rbp+57h+var_A8]
0x180023041  test    rcx, rcx
0x180023044  jz      short loc_180023056
0x180023046  mov     [rbp+57h+var_A8], rdi
0x18002304a  mov     rax, [rcx]
0x18002304d  mov     rax, [rax+10h]
0x180023051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023056  mov     rcx, [rbp+57h+var_B8]
0x18002305a  test    rcx, rcx
0x18002305d  jz      loc_180022DC7
0x180023063  mov     [rbp+57h+var_B8], rdi
0x180023067  mov     rax, [rcx]
0x18002306a  mov     rax, [rax+10h]
0x18002306e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023073  jmp     loc_180022DC7
0x180023078  mov     rbx, [rbp+57h+var_90]
0x18002307c  lea     rcx, [rbp+57h+var_A0]
0x180023080  mov     rax, [rbx]
0x180023083  mov     rdi, [rax]
0x180023086  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x18002308b  lea     r8, [rbp+57h+var_A0]
0x18002308f  mov     rcx, rbx
0x180023092  lea     rdx, _GUID_a9c88282_c261_4c26_ae97_21a4c8a3e19b
0x180023099  mov     rax, rdi
0x18002309c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230a1  mov     ebx, eax
0x1800230a3  test    eax, eax
0x1800230a5  jns     short loc_1800230F3
0x1800230a7  mov     rcx, [rbp+5Fh]; this
0x1800230ab  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\lib\\activationevent"...
0x1800230b2  mov     r9d, eax; char *
0x1800230b5  mov     edx, 61h ; 'a'; void *
0x1800230ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800230bf  lea     rcx, [rbp+57h+var_A0]
0x1800230c3  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x1800230c8  lea     rcx, [rbp+57h+var_90]
0x1800230cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800230d1  lea     rcx, [rbp+57h+pv]
0x1800230d5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800230da  mov     rcx, [rbp+57h+hObject]
0x1800230de  mov     [rbp+57h+hObject], 0
0x1800230e6  lea     rax, [rcx-1]
0x1800230ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800230ee  jmp     loc_180022EC4
  ... truncated ...
```
