# CActivationBrokerManager::ActivateApplication(ulong,ulong,_GUID,ulong,ushort const *,ushort const * *,ulong,ACTIVATEOPTIONS,unsigned __int64,IInspectable *,ulong *,void * *)

- ea: `0x180014610`
- end: `0x180014f17`
- name: `?ActivateApplication@CActivationBrokerManager@@UEAAJKKU_GUID@@KPEBGPEAPEBGKW4ACTIVATEOPTIONS@@_KPEAUIInspectable@@PEAKPEAPEAX@Z`
- size: `2311`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, unsigned int, unsigned int, struct _GUID *, __int64, unsigned __int16 *, __int64 *, unsigned int, int, __int64, __int64, _DWORD *, RTL_SRWLOCK *)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180011328`
- `0x180014610`
- `0x180015e90`
- `0x18003f3f0`
- `0x1800483cc`
- `0x18004ada0`
- `0x18004b200`
- `0x18004bc98`
- `0x18004c650`
- `0x18004c6c8`
- `0x1800550f4`
- `0x180057d14`
- `0x180058830`
- `0x18005ae90`
- `0x18005ba40`
- `0x18005d02c`
- `0x18005d094`
- `0x18005ed94`
- `0x18005ede8`
- `0x180062f30`
- `0x1800634cc`
- `0x1800636a8`
- `0x180066fa0`
- `0x180067464`
- `0x180067ac8`
- `0x180068424`
- `0x1800684d4`
- `0x1800685ac`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800147bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014e4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800147bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014e4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014769`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001489b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014769`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001489b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014edc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014edc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014eef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014eef`
- `ext-ms-win-desktopappx-l1-1-6!DoesPluginSupportCentennial` at `0x1800149cd`
- `ext-ms-win-desktopappx-l1-1-6!DoesPluginSupportCentennial` at `0x1800149cd`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x180014a8c`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x180014a8c`

## pseudocode

```c
__int64 __fastcall CActivationBrokerManager::ActivateApplication(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        struct _GUID *a4,
        __int64 a5,
        unsigned __int16 *a6,
        __int64 *a7,
        unsigned int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        _DWORD *a12,
        RTL_SRWLOCK *a13)
{
  __int64 *v15; // r13
  __int64 v16; // rdi
  unsigned int v17; // r15d
  int v18; // edx
  RTL_SRWLOCK *v19; // rsi
  int v20; // edx
  CActivationBrokerManager *v21; // r12
  int v22; // eax
  int v23; // ecx
  unsigned int i; // ebx
  int v25; // edx
  int Plugin; // ebx
  unsigned int v27; // r14d
  _DWORD *v28; // rcx
  HANDLE v29; // rax
  RTL_SRWLOCK *v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // rcx
  struct IActivationBrokerPlugin *v33; // rbx
  void (__fastcall *v34)(struct IActivationBrokerPlugin *, GUID *, __int64 *); // r14
  __int64 v35; // r12
  unsigned __int64 v36; // r14
  const unsigned __int16 *v37; // r8
  HLOCAL v38; // r12
  struct IActivationBrokerPlugin *v39; // r14
  __int64 (__fastcall *v40)(struct IActivationBrokerPlugin *, unsigned __int16 *, __int64 *, _QWORD, __int64 *); // rbx
  struct IActivationBrokerPlugin *v41; // r14
  __int64 (__fastcall *v42)(struct IActivationBrokerPlugin *, unsigned __int16 *, __int64 *, _QWORD, __int64 *); // rbx
  int v43; // edx
  int v44; // ecx
  void **v45; // r14
  void **v46; // rbx
  void **v47; // rax
  CActivationBrokerManager *v48; // rcx
  __int64 v49; // r14
  __int64 (__fastcall *v50)(__int64, unsigned __int16 *, __int64 *, _QWORD, __int64, __int64 *); // rbx
  __int64 *v51; // rax
  __int64 v52; // r14
  __int64 v53; // rbx
  __int64 v54; // r12
  __int64 (__fastcall *v55)(__int64, unsigned __int16 *, _QWORD, __int64, __int64, int, __int64, _DWORD *); // r15
  __int64 v56; // r14
  __int64 v57; // rbx
  __int64 v58; // rcx
  struct IActivationBrokerPlugin *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  char v64; // [rsp+60h] [rbp-A0h]
  CActivationBrokerManager *v65; // [rsp+68h] [rbp-98h]
  __int64 v66; // [rsp+70h] [rbp-90h] BYREF
  __int64 v67; // [rsp+78h] [rbp-88h] BYREF
  __int64 v68; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v69; // [rsp+88h] [rbp-78h] BYREF
  struct IActivationBrokerPlugin *v70; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v71; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v72; // [rsp+A0h] [rbp-60h]
  __int64 v73; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v75; // [rsp+B8h] [rbp-48h]
  HANDLE hObject; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v77; // [rsp+C8h] [rbp-38h]
  int v78; // [rsp+CCh] [rbp-34h]
  __int64 v79; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v80; // [rsp+D8h] [rbp-28h]
  RTL_SRWLOCK *v81; // [rsp+E0h] [rbp-20h]
  RTL_SRWLOCK *v82; // [rsp+E8h] [rbp-18h]
  HLOCAL hMem; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v84; // [rsp+F8h] [rbp-8h]
  __int64 v85; // [rsp+100h] [rbp+0h]
  __int64 v86; // [rsp+108h] [rbp+8h]
  struct _GUID v87; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v88; // [rsp+130h] [rbp+30h] BYREF
  int v89; // [rsp+138h] [rbp+38h]
  HLOCAL v90; // [rsp+140h] [rbp+40h]
  __int64 v91; // [rsp+148h] [rbp+48h]
  unsigned int v92; // [rsp+15Ch] [rbp+5Ch]
  __int64 v93; // [rsp+160h] [rbp+60h]
  __int64 v94; // [rsp+168h] [rbp+68h]

  v75 = a3;
  v81 = a1;
  v72 = a6;
  v15 = a7;
  v80 = a11;
  v82 = a13;
  v64 = 0;
  hMem = 0;
  v84 = 0;
  v85 = 0;
  v69 = -1;
  v71 = -1;
  hObject = 0;
  v68 = 0;
  v74 = 0;
  v70 = 0;
  v73 = 0;
  v16 = 0;
  v86 = 0;
  if ( dword_1800D2728 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800D2728);
    if ( dword_1800D2728 == -1 )
    {
      qword_1800D2200 = (__int64)&Src;
      Init_thread_footer(&dword_1800D2728);
    }
  }
  *a12 = 0;
  a13->Ptr = 0;
  if ( a7 && (v17 = a8) != 0 )
  {
    if ( !*a7 )
      *a7 = (__int64)&Src;
  }
  else
  {
    v15 = &qword_1800D2200;
    v17 = 1;
  }
  v18 = a9 | 0x1000000;
  if ( (a9 & 0x2000000) == 0 )
    v18 = a9;
  v78 = v18;
  v19 = a1 + 9;
  AcquireSRWLockExclusive(a1 + 9);
  v21 = (CActivationBrokerManager *)&a1[-17];
  v65 = v21;
  v22 = *((_DWORD *)v21 + 61) + 1;
  v23 = (int)v81;
  HIDWORD(v81[13].Ptr) = v22;
  if ( (byte_1800D1F03 & 2) != 0 )
    McTemplateU0zzqjqq_EventWriteTransfer(v23, a2, (_DWORD)a6, *v15, v17, (__int64)a4, a2, v22);
  if ( v19 )
    ReleaseSRWLockExclusive(v19);
  for ( i = 1; i < v17; ++i )
  {
    if ( byte_1800D1F02 < 0 )
      McTemplateU0zzq_EventWriteTransfer(v23, v20, (_DWORD)v72, v15[i], i);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v70);
  v87 = *a4;
  Plugin = CActivationBrokerManager::_GetPlugin(v21, &v87, &v70);
  if ( Plugin < 0 )
    goto LABEL_22;
  if ( !v70 )
  {
    Plugin = -2147024882;
LABEL_22:
    LOBYTE(v27) = a2;
LABEL_23:
    v28 = a12;
    goto LABEL_24;
  }
  v31 = (_QWORD *)(*(__int64 (__fastcall **)(struct IActivationBrokerPlugin *, struct _GUID *))(*(_QWORD *)v70 + 24LL))(
                    v70,
                    &v87);
  v32 = *v31 - *(_QWORD *)&a4->Data1;
  if ( *v31 == *(_QWORD *)&a4->Data1 )
    v32 = v31[1] - *(_QWORD *)a4->Data4;
  if ( v32 )
  {
    Plugin = -2147024809;
    goto LABEL_22;
  }
  v33 = v70;
  v34 = **(void (__fastcall ***)(struct IActivationBrokerPlugin *, GUID *, __int64 *))v70;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
  v34(v33, &GUID_b98dd1e5_633a_4266_9610_0f82ef69856e, &v73);
  v77 = (*(__int64 (__fastcall **)(struct IActivationBrokerPlugin *))(*(_QWORD *)v70 + 40LL))(v70);
  v35 = (*(__int64 (__fastcall **)(struct IActivationBrokerPlugin *))(*(_QWORD *)v70 + 32LL))(v70);
  if ( !v35 )
  {
    Plugin = -2147467259;
    goto LABEL_84;
  }
  v36 = -1;
  do
    ++v36;
  while ( *(_WORD *)(v35 + 2 * v36) );
  Plugin = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCapacity(
             &hMem,
             v36);
  if ( Plugin < 0 )
    goto LABEL_84;
  v37 = (const unsigned __int16 *)v35;
  v38 = hMem;
  StringCchCopyNW((unsigned __int16 *)hMem, v36 + 1, v37, v36);
  v84 = v36;
  if ( !(unsigned __int8)IsDoesPluginSupportCentennialPresent()
    || !(unsigned __int8)IsTryActivateDesktopAppXApplicationPresent() )
  {
    goto LABEL_49;
  }
  (*(void (__fastcall **)(struct IActivationBrokerPlugin *, struct _GUID *))(*(_QWORD *)v70 + 24LL))(v70, &v87);
  LODWORD(v67) = 0;
  Plugin = DoesPluginSupportCentennial(&v87, &v67);
  if ( Plugin < 0 )
  {
LABEL_84:
    v21 = v65;
    goto LABEL_22;
  }
  if ( !(_DWORD)v67 )
  {
LABEL_49:
    v27 = a2;
    goto LABEL_50;
  }
  memset_0(&v88, 0, 0x40u);
  v66 = 0;
  v88 = v72;
  v93 = a10;
  v89 = 1;
  v39 = v70;
  v40 = *(__int64 (__fastcall **)(struct IActivationBrokerPlugin *, unsigned __int16 *, __int64 *, _QWORD, __int64 *))(*(_QWORD *)v70 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
  Plugin = v40(v39, v72, v15, v17, &v68);
  if ( Plugin < 0 )
    goto LABEL_84;
  v27 = a2;
  if ( !v68 )
  {
    Plugin = -2147024882;
    v21 = v65;
    goto LABEL_23;
  }
  v91 = v68;
  v90 = v38;
  v92 = a2;
  v94 = v80;
  Plugin = TryActivateDesktopAppXApplication(&v88, &v66);
  v25 = 0;
  v28 = a12;
  if ( Plugin >= 0 )
  {
    *a12 = HIDWORD(v66);
    if ( (_DWORD)v66 )
    {
LABEL_50:
      if ( !v73 )
      {
        v41 = v70;
        v42 = *(__int64 (__fastcall **)(struct IActivationBrokerPlugin *, unsigned __int16 *, __int64 *, _QWORD, __int64 *))(*(_QWORD *)v70 + 48LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
        Plugin = v42(v41, v72, v15, v17, &v68);
        v21 = v65;
        if ( Plugin < 0 )
        {
LABEL_54:
          LOBYTE(v27) = a2;
          goto LABEL_23;
        }
        if ( !v68 )
        {
          Plugin = -2147024882;
          goto LABEL_54;
        }
LABEL_75:
        Plugin = Microsoft::WRL::Details::MakeAndInitialize<Execution::ActivationManagerShim,IApplicationActivationManagerPriv,>(&v74);
        LOBYTE(v27) = a2;
        if ( Plugin < 0 )
          goto LABEL_23;
        Plugin = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v74 + 136LL))(
                   v74,
                   v75,
                   a2,
                   v77,
                   v80);
        if ( Plugin < 0 )
          goto LABEL_23;
        v54 = v74;
        v55 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64, __int64, int, __int64, _DWORD *))(*(_QWORD *)v74 + 64LL);
        v56 = v68;
        Windows::Internal::StringReference::_ConstructorHelper(
          (Windows::Internal::StringReference *)&v87,
          (const unsigned __int16 *)hMem);
        v57 = *(_QWORD *)&v87.Data1;
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&v88, v72);
        Plugin = v55(v54, v88, 0, v57, v56, v78, a10, a12);
        if ( Plugin >= 0
          && v16
          && (Plugin = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v74 + 152LL))(v74, &v71),
              Plugin >= 0) )
        {
          *(_DWORD *)(v16 + 8) = v71;
          v21 = v65;
          if ( *(_DWORD *)(v16 + 12) )
            CActivationBrokerManager::_CloseTask(v65, v71);
        }
        else
        {
          v21 = v65;
        }
        goto LABEL_54;
      }
      v66 = 0;
      v67 = 0;
      v21 = v65;
      Plugin = CActivationBrokerManager::_GetTaskId(v65, v27, v75, &v69);
      if ( Plugin >= 0 )
      {
        if ( (byte_1800D1F03 & 2) != 0 )
          McTemplateU0zqq_EventWriteTransfer(v44, v43, (_DWORD)v72, v27, v69);
        if ( (unsigned int)CActivationBrokerManager::_GetTaskWithResult(v65, v69, 0) == -2147319765 )
        {
          v45 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&hObject);
          v46 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&v67);
          v47 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&v66);
          CActivationBrokerManager::_CreateCompletedEvent(v48, a2, v47, v46, v45);
          v49 = v73;
          v50 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 *, _QWORD, __int64, __int64 *))(*(_QWORD *)v73 + 24LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
          Plugin = v50(v49, v72, v15, v17, v66, &v68);
          if ( Plugin >= 0 )
          {
            if ( !v68 )
              goto LABEL_63;
            v66 = 0;
            v51 = (__int64 *)CreateRefCountedObj<CActivationBrokerManager::TaskWithResult,>(&v87);
            v16 = 0;
            if ( &v79 != v51 )
            {
              v16 = *v51;
              *v51 = 0;
            }
            v79 = 0;
            v86 = v16;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v79);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
            if ( v16 )
            {
              v52 = v67;
              v67 = 0;
              if ( v52 != *(_QWORD *)(v16 + 24) )
              {
                tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v16 + 24);
                *(_QWORD *)(v16 + 24) = v52;
              }
              Microsoft::WRL::ComPtr<IInspectable>::operator=(v16 + 32, v68);
              v53 = v73;
              if ( *(_QWORD *)(v16 + 40) != v73 )
              {
                if ( v73 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 8LL))(v73);
                *(_QWORD *)&v87.Data1 = *(_QWORD *)(v16 + 40);
                *(_QWORD *)(v16 + 40) = v53;
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
              }
              Plugin = CActivationBrokerManager::_AddTaskWithResult(v65, v69, v16);
              if ( Plugin >= 0 )
              {
                v64 = 1;
                tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v67);
                tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v66);
                goto LABEL_75;
              }
            }
            else
            {
LABEL_63:
              Plugin = -2147024882;
            }
          }
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v67);
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v66);
          goto LABEL_54;
        }
        Plugin = -2147019873;
      }
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v67);
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v66);
      goto LABEL_23;
    }
  }
  v21 = v65;
LABEL_24:
  if ( (byte_1800D1F03 & 2) != 0 )
    McTemplateU0zqqqq_EventWriteTransfer((_DWORD)v28, v25, (_DWORD)v72, *v28, v71, Plugin, v27);
  v29 = hObject;
  hObject = 0;
  v82->Ptr = v29;
  if ( v15 != &qword_1800D2200 && (const WCHAR *)*v15 == &Src )
    *v15 = 0;
  v82 = v19;
  AcquireSRWLockExclusive(v19);
  v30 = v81;
  --HIDWORD(v81[13].Ptr);
  if ( Plugin < 0 && v64 )
  {
    CActivationBrokerManager::_RemoveTaskWithResult(v21, v69);
  }
  else if ( !LODWORD(v30[10].Ptr) )
  {
    CActivationBrokerManager::_ReleaseBrokerSessionMgr(v21, 0, 0);
  }
  if ( v19 )
    ReleaseSRWLockExclusive(v19);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v58 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  }
  v59 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(struct IActivationBrokerPlugin *))(*(_QWORD *)v59 + 16LL))(v59);
  }
  v60 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  }
  v61 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)Plugin;
}

```

## disassembly

```asm
0x180014610  push    rbp
0x180014612  push    rbx
0x180014613  push    rsi
0x180014614  push    rdi
0x180014615  push    r12
0x180014617  push    r13
0x180014619  push    r14
0x18001461b  push    r15
0x18001461d  lea     rbp, [rsp-88h]
0x180014625  sub     rsp, 188h
0x18001462c  mov     rax, cs:__security_cookie
0x180014633  xor     rax, rsp
0x180014636  mov     [rbp+0C0h+var_50], rax
0x18001463a  mov     r14, r9
0x18001463d  mov     [rbp+0C0h+var_108], r8d
0x180014641  mov     [rsp+1C0h+var_170], edx
0x180014645  mov     r12, rcx
0x180014648  mov     [rbp+0C0h+var_E0], rcx
0x18001464c  mov     rbx, [rbp+0C0h+arg_28]
0x180014653  mov     [rbp+0C0h+var_120], rbx
0x180014657  mov     r13, [rbp+0C0h+arg_30]
0x18001465e  mov     rax, [rbp+0C0h+arg_50]
0x180014665  mov     [rbp+0C0h+var_E8], rax
0x180014669  mov     rsi, [rbp+0C0h+arg_58]
0x180014670  mov     [rsp+1C0h+var_168], rsi
0x180014675  mov     r15, [rbp+0C0h+arg_60]
0x18001467c  mov     [rbp+0C0h+var_D8], r15
0x180014680  xor     r8d, r8d
0x180014683  mov     [rsp+1C0h+var_160], r8b
0x180014688  mov     [rbp+0C0h+hMem], r8
0x18001468c  mov     [rbp+0C0h+var_C8], r8
0x180014690  mov     [rbp+0C0h+var_C0], r8
0x180014694  or      eax, 0FFFFFFFFh
0x180014697  mov     [rbp+0C0h+var_138], eax
0x18001469a  mov     [rbp+0C0h+var_128], eax
0x18001469d  mov     [rbp+0C0h+hObject], r8
0x1800146a1  mov     [rbp+0C0h+var_140], r8
0x1800146a5  mov     [rbp+0C0h+var_110], r8
0x1800146a9  mov     [rbp+0C0h+var_130], r8
0x1800146ad  mov     [rbp+0C0h+var_118], r8
0x1800146b1  mov     edi, r8d
0x1800146b4  mov     [rbp+0C0h+var_B8], r8
0x1800146b8  mov     ecx, cs:_tls_index
0x1800146be  mov     rax, gs:58h
0x1800146c7  mov     edx, 4
0x1800146cc  mov     rax, [rax+rcx*8]
0x1800146d0  lea     rcx, Src
0x1800146d7  mov     eax, [rdx+rax]
0x1800146da  cmp     cs:dword_1800D2728, eax
0x1800146e0  jle     short loc_18001471B
0x1800146e2  lea     rcx, dword_1800D2728
0x1800146e9  call    _Init_thread_header
0x1800146ee  cmp     cs:dword_1800D2728, 0FFFFFFFFh
0x1800146f5  jnz     short loc_180014711
0x1800146f7  lea     rax, Src
0x1800146fe  mov     cs:qword_1800D2200, rax
0x180014705  lea     rcx, dword_1800D2728
0x18001470c  call    _Init_thread_footer
0x180014711  lea     rcx, Src
0x180014718  xor     r8d, r8d
0x18001471b  mov     [rsi], r8d
0x18001471e  mov     [r15], r8
0x180014721  test    r13, r13
0x180014724  jz      short loc_18001473E
0x180014726  mov     r15d, [rbp+0C0h+arg_38]
0x18001472d  test    r15d, r15d
0x180014730  jz      short loc_18001473E
0x180014732  cmp     [r13+0], r8
0x180014736  jnz     short loc_18001474B
0x180014738  mov     [r13+0], rcx
0x18001473c  jmp     short loc_18001474B
0x18001473e  lea     r13, qword_1800D2200
0x180014745  mov     r15d, 1
0x18001474b  mov     ecx, [rbp+0C0h+arg_40]
0x180014751  mov     edx, ecx
0x180014753  bts     edx, 18h
0x180014757  bt      ecx, 19h
0x18001475b  cmovnb  edx, ecx
0x18001475e  mov     [rbp+0C0h+var_F4], edx
0x180014761  lea     rsi, [r12+48h]
0x180014766  mov     rcx, rsi; SRWLock
0x180014769  call    cs:__imp_AcquireSRWLockExclusive
0x18001476f  add     r12, 0FFFFFFFFFFFFFF78h
0x180014776  mov     [rsp+1C0h+var_158], r12
0x18001477b  mov     eax, [r12+0F4h]
0x180014783  inc     eax
0x180014785  mov     rcx, [rbp+0C0h+var_E0]
0x180014789  mov     [rcx+6Ch], eax
0x18001478c  test    cs:byte_1800D1F03, 2
0x180014793  jz      short loc_1800147B7
0x180014795  mov     dword ptr [rsp+1C0h+var_188], eax
0x180014799  mov     edx, [rsp+1C0h+var_170]
0x18001479d  mov     dword ptr [rsp+1C0h+var_190], edx
0x1800147a1  mov     [rsp+1C0h+var_198], r14
0x1800147a6  mov     dword ptr [rsp+1C0h+var_1A0], r15d
0x1800147ab  mov     r9, [r13+0]
0x1800147af  mov     r8, rbx
0x1800147b2  call    McTemplateU0zzqjqq_EventWriteTransfer
0x1800147b7  test    rsi, rsi
0x1800147ba  jz      short loc_1800147C5
0x1800147bc  mov     rcx, rsi; SRWLock
0x1800147bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800147c5  mov     ebx, 1
0x1800147ca  cmp     r15d, ebx
0x1800147cd  jbe     short loc_1800147FC
0x1800147cf  mov     r12, [rbp+0C0h+var_120]
0x1800147d3  cmp     cs:byte_1800D1F02, 0
0x1800147da  jge     short loc_1800147F0
0x1800147dc  mov     r9d, ebx
0x1800147df  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x1800147e3  mov     r9, [r13+r9*8+0]
0x1800147e8  mov     r8, r12
0x1800147eb  call    McTemplateU0zzq_EventWriteTransfer
0x1800147f0  inc     ebx
0x1800147f2  cmp     ebx, r15d
0x1800147f5  jb      short loc_1800147D3
0x1800147f7  mov     r12, [rsp+1C0h+var_158]
0x1800147fc  lea     rcx, [rbp+0C0h+var_130]
0x180014800  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180014805  movups  xmm0, xmmword ptr [r14]
0x180014809  movdqu  xmmword ptr [rbp+0C0h+var_B0.Data1], xmm0
0x18001480e  lea     r8, [rbp+0C0h+var_130]; struct IActivationBrokerPlugin **
0x180014812  lea     rdx, [rbp+0C0h+var_B0]; struct _GUID
0x180014816  mov     rcx, r12; this
0x180014819  call    ?_GetPlugin@CActivationBrokerManager@@AEAAJU_GUID@@PEAPEAUIActivationBrokerPlugin@@@Z; CActivationBrokerManager::_GetPlugin(_GUID,IActivationBrokerPlugin * *)
0x18001481e  mov     ebx, eax
0x180014820  test    eax, eax
0x180014822  js      short loc_180014836
0x180014824  mov     rcx, [rbp+0C0h+var_130]
0x180014828  test    rcx, rcx
0x18001482b  jnz     loc_1800148CC
0x180014831  mov     ebx, 8007000Eh
0x180014836  mov     r14d, [rsp+1C0h+var_170]
0x18001483b  xor     r15d, r15d
0x18001483e  mov     rcx, [rsp+1C0h+var_168]
0x180014843  test    cs:byte_1800D1F03, 2
0x18001484a  jz      short loc_180014868
0x18001484c  mov     dword ptr [rsp+1C0h+var_190], r14d
0x180014851  mov     dword ptr [rsp+1C0h+var_198], ebx
0x180014855  mov     eax, [rbp+0C0h+var_128]
0x180014858  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x18001485c  mov     r9d, [rcx]
0x18001485f  mov     r8, [rbp+0C0h+var_120]
0x180014863  call    McTemplateU0zqqqq_EventWriteTransfer
0x180014868  mov     rax, [rbp+0C0h+hObject]
0x18001486c  mov     [rbp+0C0h+hObject], r15
0x180014870  mov     rcx, [rbp+0C0h+var_D8]
0x180014874  mov     [rcx], rax
0x180014877  lea     rax, qword_1800D2200
0x18001487e  cmp     r13, rax
0x180014881  jz      short loc_180014894
0x180014883  lea     rax, Src
0x18001488a  cmp     [r13+0], rax
0x18001488e  jnz     short loc_180014894
0x180014890  mov     [r13+0], r15
0x180014894  mov     [rbp+0C0h+var_D8], rsi
0x180014898  mov     rcx, rsi; SRWLock
0x18001489b  call    cs:__imp_AcquireSRWLockExclusive
0x1800148a1  nop
0x1800148a2  mov     rax, [rbp+0C0h+var_E0]
0x1800148a6  dec     dword ptr [rax+6Ch]
0x1800148a9  test    ebx, ebx
0x1800148ab  jns     loc_180014E33
0x1800148b1  cmp     [rsp+1C0h+var_160], r15b
0x1800148b6  jz      loc_180014E33
0x1800148bc  mov     edx, [rbp+0C0h+var_138]; unsigned int
0x1800148bf  mov     rcx, r12; this
0x1800148c2  call    ?_RemoveTaskWithResult@CActivationBrokerManager@@AEAAJK@Z; CActivationBrokerManager::_RemoveTaskWithResult(ulong)
0x1800148c7  jmp     loc_180014E47
0x1800148cc  mov     rax, [rcx]
0x1800148cf  lea     rdx, [rbp+0C0h+var_B0]
0x1800148d3  mov     rax, [rax+18h]
0x1800148d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148dc  mov     rcx, [rax]
0x1800148df  sub     rcx, [r14]
0x1800148e2  jnz     short loc_1800148EC
0x1800148e4  mov     rcx, [rax+8]
0x1800148e8  sub     rcx, [r14+8]
0x1800148ec  test    rcx, rcx
0x1800148ef  jnz     loc_180014E1F
0x1800148f5  mov     rbx, [rbp+0C0h+var_130]
0x1800148f9  mov     rax, [rbx]
0x1800148fc  mov     r14, [rax]
0x1800148ff  lea     rcx, [rbp+0C0h+var_118]
0x180014903  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180014908  lea     r8, [rbp+0C0h+var_118]
0x18001490c  lea     rdx, _GUID_b98dd1e5_633a_4266_9610_0f82ef69856e
0x180014913  mov     rcx, rbx
0x180014916  mov     rax, r14
0x180014919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001491e  nop
0x18001491f  mov     rcx, [rbp+0C0h+var_130]
0x180014923  mov     rax, [rcx]
0x180014926  mov     rax, [rax+28h]
0x18001492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001492f  mov     [rbp+0C0h+var_F8], eax
0x180014932  mov     rcx, [rbp+0C0h+var_130]
0x180014936  mov     rdx, [rcx]
0x180014939  mov     rax, [rdx+20h]
0x18001493d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014942  mov     r12, rax
0x180014945  xor     eax, eax
0x180014947  test    r12, r12
0x18001494a  jz      loc_180014E10
0x180014950  or      r14, 0FFFFFFFFFFFFFFFFh
0x180014954  inc     r14
0x180014957  cmp     [r12+r14*2], ax
0x18001495c  jnz     short loc_180014954
0x18001495e  mov     rdx, r14
0x180014961  lea     rcx, [rbp+0C0h+hMem]
0x180014965  call    ?_EnsureCapacity@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18001496a  mov     ebx, eax
0x18001496c  test    eax, eax
0x18001496e  js      loc_180014E15
0x180014974  lea     rdx, [r14+1]; unsigned __int64
0x180014978  mov     r9, r14; unsigned __int64
0x18001497b  mov     r8, r12; unsigned __int16 *
0x18001497e  mov     r12, [rbp+0C0h+hMem]
0x180014982  mov     rcx, r12; unsigned __int16 *
0x180014985  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001498a  mov     [rbp+0C0h+var_C8], r14
0x18001498e  call    IsDoesPluginSupportCentennialPresent
0x180014993  xor     r14d, r14d
0x180014996  test    al, al
0x180014998  jz      loc_180014AB8
0x18001499e  call    IsTryActivateDesktopAppXApplicationPresent
0x1800149a3  test    al, al
0x1800149a5  jz      loc_180014AB8
0x1800149ab  mov     rcx, [rbp+0C0h+var_130]
0x1800149af  mov     rax, [rcx]
0x1800149b2  lea     rdx, [rbp+0C0h+var_B0]
0x1800149b6  mov     rax, [rax+18h]
0x1800149ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149bf  mov     dword ptr [rsp+1C0h+var_148], r14d
0x1800149c4  lea     rdx, [rsp+1C0h+var_148]
0x1800149c9  lea     rcx, [rbp+0C0h+var_B0]
0x1800149cd  call    cs:__imp_DoesPluginSupportCentennial
0x1800149d3  mov     ebx, eax
0x1800149d5  test    eax, eax
0x1800149d7  js      loc_180014E15
0x1800149dd  cmp     dword ptr [rsp+1C0h+var_148], r14d
0x1800149e2  jz      loc_180014AB8
0x1800149e8  xor     edx, edx; Val
0x1800149ea  lea     r8d, [r14+40h]; Size
0x1800149ee  lea     rcx, [rbp+0C0h+var_90]; void *
0x1800149f2  call    memset_0
0x1800149f7  mov     [rsp+1C0h+var_150], r14
0x1800149fc  mov     rax, [rbp+0C0h+var_120]
0x180014a00  mov     [rbp+0C0h+var_90], rax
0x180014a04  mov     rax, [rbp+0C0h+arg_48]
0x180014a0b  mov     [rbp+0C0h+var_60], rax
0x180014a0f  mov     [rbp+0C0h+var_88], 1
0x180014a16  mov     r14, [rbp+0C0h+var_130]
0x180014a1a  mov     rax, [r14]
0x180014a1d  mov     rbx, [rax+30h]
0x180014a21  lea     rcx, [rbp+0C0h+var_140]
0x180014a25  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180014a2a  lea     rax, [rbp+0C0h+var_140]
0x180014a2e  mov     [rsp+1C0h+var_1A0], rax
0x180014a33  mov     r9d, r15d
0x180014a36  mov     r8, r13
0x180014a39  mov     rdx, [rbp+0C0h+var_120]
0x180014a3d  mov     rcx, r14
0x180014a40  mov     rax, rbx
0x180014a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a48  mov     ebx, eax
0x180014a4a  test    eax, eax
0x180014a4c  js      loc_180014E15
0x180014a52  mov     rax, [rbp+0C0h+var_140]
0x180014a56  mov     r14d, [rsp+1C0h+var_170]
0x180014a5b  test    rax, rax
0x180014a5e  jnz     short loc_180014A6F
0x180014a60  mov     ebx, 8007000Eh
0x180014a65  mov     r12, [rsp+1C0h+var_158]
0x180014a6a  jmp     loc_18001483B
0x180014a6f  mov     [rbp+0C0h+var_78], rax
0x180014a73  mov     [rbp+0C0h+var_80], r12
0x180014a77  mov     [rbp+0C0h+var_64], r14d
0x180014a7b  mov     rax, [rbp+0C0h+var_E8]
0x180014a7f  mov     [rbp+0C0h+var_58], rax
0x180014a83  lea     rdx, [rsp+1C0h+var_150]
0x180014a88  lea     rcx, [rbp+0C0h+var_90]
0x180014a8c  call    cs:__imp_TryActivateDesktopAppXApplication
0x180014a92  mov     ebx, eax
0x180014a94  xor     edx, edx
0x180014a96  mov     rcx, [rsp+1C0h+var_168]
0x180014a9b  test    eax, eax
0x180014a9d  js      short loc_180014AAB
0x180014a9f  mov     eax, dword ptr [rsp+1C0h+var_150+4]
0x180014aa3  mov     [rcx], eax
0x180014aa5  cmp     dword ptr [rsp+1C0h+var_150], edx
0x180014aa9  jnz     short loc_180014ABD
0x180014aab  mov     r12, [rsp+1C0h+var_158]
0x180014ab0  xor     r15d, r15d
0x180014ab3  jmp     loc_180014843
0x180014ab8  mov     r14d, [rsp+1C0h+var_170]
0x180014abd  xor     ecx, ecx
0x180014abf  cmp     [rbp+0C0h+var_118], rcx
0x180014ac3  jnz     short loc_180014B1E
0x180014ac5  mov     r14, [rbp+0C0h+var_130]
  ... truncated ...
```
