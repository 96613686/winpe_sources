# CBackstackManager::GetBackstack(IObjectArray * *,int)

- ea: `0x18004a4f0`
- end: `0x18004aad3`
- name: `?GetBackstack@CBackstackManager@@UEAAJPEAPEAUIObjectArray@@H@Z`
- size: `1507`
- prototype: `__int64 __fastcall(CBackstackManager *__hidden this, struct IObjectArray **, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009dd0`
- `0x18000aa70`
- `0x1800187cc`
- `0x180018c80`
- `0x1800254a0`
- `0x180025710`
- `0x1800378dc`
- `0x18004a4f0`
- `0x18004aae0`
- `0x180062060`
- `0x18009873c`
- `0x1800bdf34`
- `0x180142e10`
- `0x18019acfc`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004a89e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004a89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a63e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a7cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a94a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a63e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a7cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a94a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa78`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004a580`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004a580`

## pseudocode

```c
__int64 __fastcall CBackstackManager::GetBackstack(IUnknown **this, struct IObjectArray **a2, __int64 a3)
{
  unsigned __int64 v5; // r14
  __int64 v6; // r8
  IUnknown *v7; // rcx
  int v8; // r15d
  int Instance; // ebx
  int v10; // eax
  unsigned int v11; // edi
  char *v12; // rcx
  unsigned __int64 i; // rbx
  unsigned int v15; // esi
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, _QWORD, GUID *, struct IImmersiveApplication **); // rbx
  const struct _GUID *v18; // r8
  unsigned __int64 v19; // rcx
  FILETIME *v20; // rdx
  unsigned int v21; // edx
  void *v22; // rcx
  void **v23; // rax
  const struct _GUID *v24; // rdx
  int v25; // ecx
  unsigned __int64 v26; // r13
  unsigned __int64 v27; // r12
  __int64 v28; // rsi
  int (__fastcall *v29)(__int64, GUID *, __int64 *); // rbx
  __int64 v30; // rdi
  int (__fastcall *v31)(__int64, LPVOID *); // rbx
  __int64 v32; // r9
  __int64 v33; // rcx
  struct IImmersiveApplication *v34; // rcx
  __int64 v35; // rcx
  char *v36; // rcx
  unsigned __int64 j; // rdi
  void *v38; // rcx
  int v39; // [rsp+20h] [rbp-79h]
  __int64 v40; // [rsp+30h] [rbp-69h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-61h] BYREF
  __int64 v42; // [rsp+40h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int64 v44; // [rsp+50h] [rbp-49h]
  LPVOID v45; // [rsp+58h] [rbp-41h] BYREF
  __int64 v46; // [rsp+60h] [rbp-39h]
  char v47[8]; // [rsp+68h] [rbp-31h] BYREF
  LPVOID v48; // [rsp+70h] [rbp-29h] BYREF
  void *ppvOut; // [rsp+78h] [rbp-21h] BYREF
  int v50; // [rsp+80h] [rbp-19h]
  IUnknown **v51; // [rsp+88h] [rbp-11h]
  struct IImmersiveApplication *v52[2]; // [rsp+90h] [rbp-9h] BYREF
  struct IObjectArray **v53; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v50 = a3;
  v53 = a2;
  v51 = this;
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      BackstackManager_GetBackstack_Start,
      a3,
      1,
      v52);
  v5 = 0;
  *a2 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
  IUnknown_QueryService(*(this - 9), &IID_IProjectionManager, &GUID_d9cd01a5_a926_412d_a6cd_c3b51c2a9bc8, &ppvOut);
  pv = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v42 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
  v7 = this[5];
  v42 = 0;
  if ( v7 )
  {
    v8 = 0;
    Instance = ((__int64 (__fastcall *)(IUnknown *, __int64 *))v7->lpVtbl[1].QueryInterface)(v7, &v42);
    if ( Instance >= 0 )
    {
      LODWORD(v40) = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 24LL))(v42, &v40);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"shell\\twinui\\backstackmanager\\lib\\backstackmanager.cpp",
          (const char *)(unsigned int)v10,
          v39);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
        v12 = (char *)pv;
        if ( pv )
        {
          for ( i = 0; i < v44; ++i )
          {
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v12[8 * i]);
            v12 = (char *)pv;
          }
          CoTaskMemFree(v12);
          pv = 0;
        }
        v44 = 0;
        v46 = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
        return v11;
      }
      v15 = 0;
      if ( (_DWORD)v40 )
      {
        while ( 1 )
        {
          v16 = v42;
          v52[0] = 0;
          v17 = *(int (__fastcall **)(__int64, _QWORD, GUID *, struct IImmersiveApplication **))(*(_QWORD *)v42 + 32LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v52);
          if ( v17(v16, v15, &GUID_8b14e88b_5663_4caf_b196_c31479262831, v52) >= 0 )
            break;
LABEL_25:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v52);
          if ( ++v15 >= (unsigned int)v40 )
            goto LABEL_28;
        }
        LODWORD(v48) = 0;
        if ( ppvOut )
          (*(void (__fastcall **)(void *, struct IImmersiveApplication *, LPVOID *))(*(_QWORD *)ppvOut + 48LL))(
            ppvOut,
            v52[0],
            &v48);
        FileTime1 = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&FileTime1);
        if ( (int)CBackstackApp::CreateInstance(v52[0], (_DWORD)v48 != 0, v18, (void **)&FileTime1) < 0 )
        {
LABEL_24:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&FileTime1);
          goto LABEL_25;
        }
        v19 = v44;
        if ( v44 == v46 )
        {
          if ( (int)CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(
                      &pv,
                      v44 + 1) < 0 )
          {
LABEL_22:
            if ( (_DWORD)v48 )
              ++v8;
            goto LABEL_24;
          }
          v19 = v44;
        }
        v44 = v19 + 1;
        v20 = (FILETIME *)((char *)pv + 8 * v19);
        if ( v20 )
        {
          *v20 = FileTime1;
          if ( FileTime1 )
            (*(void (__fastcall **)(FILETIME))(**(_QWORD **)&FileTime1 + 8LL))(FileTime1);
        }
        goto LABEL_22;
      }
    }
    if ( Instance >= 0 )
    {
LABEL_28:
      if ( v44 > 1 )
      {
        v45 = 0;
        v52[0] = 0;
        if ( (int)ULongLongMult(v44 >> 1, 8u, (unsigned __int64 *)v52) >= 0
          && CTCoAllocPolicy::Realloc(v22, v21, 0, (unsigned __int64)v52[0], &v45) >= 0 )
        {
          CTSimpleArray<Microsoft::WRL::ComPtr<IBackstackApp>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IBackstackApp>>>::_MergeSort<CBackstackAppSort>(
            &pv,
            v47,
            0,
            v44);
          CoTaskMemFree(v45);
          v45 = 0;
        }
      }
      v52[0] = 0;
      v23 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(v52);
      Instance = CEnumerableObjectCollection::CreateInstance(v25, v24, v23);
      if ( Instance >= 0 )
      {
        v26 = v44;
        v27 = 0;
        if ( v44 )
        {
          do
          {
            v28 = *((_QWORD *)pv + v5);
            if ( v28 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28 + 8LL))(*((_QWORD *)pv + v5));
            FileTime1 = 0;
            (*(void (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v28 + 24LL))(v28, &FileTime1);
            v40 = 0;
            v29 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v28 + 32LL);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
            if ( v29(v28, &GUID_8b14e88b_5663_4caf_b196_c31479262831, &v40) >= 0
              && ((*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28)
               || v27 < (unsigned int)-v8 && CompareFileTime(&FileTime1, &BackstackHelpers::s_FILETIME_MIN))
              && (*(int (__fastcall **)(struct IImmersiveApplication *, __int64))(*(_QWORD *)v52[0] + 40LL))(
                   v52[0],
                   v40) >= 0 )
            {
              ++v27;
              if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28) )
                --v8;
              if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
              {
                v48 = 0;
                v30 = v40;
                v31 = *(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 32LL);
                CoTaskMemFree(0);
                if ( v31(v30, &v48) >= 0 && (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(
                    &MICROSOFT_TWINUI_PUBLISHER_Context,
                    BackstackManager_GetBackstack_Info,
                    v48);
                CoTaskMemFree(v48);
              }
            }
            else if ( v50 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 40LL))(v28);
              if ( v40 )
              {
                LOBYTE(v32) = FileTime1.dwLowDateTime + ((unsigned __int64)FileTime1.dwHighDateTime << 32) != 0;
                CBackstackManager::_CleanupAppStateOnRemoval(v51 - 11, v40, 2, v32);
              }
            }
            v33 = v40;
            if ( v40 )
            {
              v40 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            ++v5;
          }
          while ( v5 < v26 );
        }
        Instance = (**(__int64 (__fastcall ***)(struct IImmersiveApplication *, GUID *, struct IObjectArray **))v52[0])(
                     v52[0],
                     &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                     v53);
      }
      v34 = v52[0];
      if ( v52[0] )
      {
        v52[0] = 0;
        (*(void (__fastcall **)(struct IImmersiveApplication *))(*(_QWORD *)v34 + 16LL))(v34);
      }
    }
  }
  else
  {
    Instance = -2147019873;
  }
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      BackstackManager_GetBackstack_Stop,
      v6,
      1,
      &v53);
  v35 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = (char *)pv;
  if ( pv )
  {
    for ( j = 0; j < v44; ++j )
    {
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v36[8 * j]);
      v36 = (char *)pv;
    }
    CoTaskMemFree(v36);
    pv = 0;
  }
  v38 = ppvOut;
  v44 = 0;
  v46 = 0;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004a4f0  mov     [rsp-8+arg_10], rbx
0x18004a4f5  push    rbp
0x18004a4f6  push    rsi
0x18004a4f7  push    rdi
0x18004a4f8  push    r12
0x18004a4fa  push    r13
0x18004a4fc  push    r14
0x18004a4fe  push    r15
0x18004a500  lea     rbp, [rsp-27h]
0x18004a505  sub     rsp, 0C0h
0x18004a50c  mov     rax, cs:__security_cookie
0x18004a513  xor     rax, rsp
0x18004a516  mov     [rbp+57h+var_40], rax
0x18004a51a  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18004a521  mov     rdi, rdx
0x18004a524  mov     [rbp+57h+var_70], r8d
0x18004a528  mov     rbx, rcx
0x18004a52b  mov     [rbp+57h+var_50], rdx
0x18004a52f  mov     [rbp+57h+var_68], rcx
0x18004a533  jz      short loc_18004A557
0x18004a535  lea     rax, [rbp+57h+var_60]
0x18004a539  mov     r9d, 1
0x18004a53f  lea     rdx, BackstackManager_GetBackstack_Start
0x18004a546  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18004a54b  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18004a552  call    McGenEventWrite_EventWriteTransfer
0x18004a557  xor     r14d, r14d
0x18004a55a  lea     rcx, [rbp+57h+ppvOut]
0x18004a55e  mov     [rdi], r14
0x18004a561  mov     [rbp+57h+ppvOut], r14
0x18004a565  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a56a  mov     rcx, [rbx-48h]; punk
0x18004a56e  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18004a572  lea     r8, _GUID_d9cd01a5_a926_412d_a6cd_c3b51c2a9bc8; riid
0x18004a579  lea     rdx, IID_IProjectionManager; guidService
0x18004a580  call    cs:__imp_IUnknown_QueryService
0x18004a587  nop     dword ptr [rax+rax+00h]
0x18004a58c  lea     rcx, [rbp+57h+var_B0]
0x18004a590  mov     [rbp+57h+pv], r14
0x18004a594  mov     [rbp+57h+var_A0], r14
0x18004a598  mov     [rbp+57h+var_98], r14
0x18004a59c  mov     [rbp+57h+var_90], r14
0x18004a5a0  mov     [rbp+57h+var_B0], r14
0x18004a5a4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a5a9  mov     rcx, [rbx+28h]
0x18004a5ad  mov     [rbp+57h+var_B0], r14
0x18004a5b1  test    rcx, rcx
0x18004a5b4  jz      loc_18004AA07
0x18004a5ba  mov     rax, [rcx]
0x18004a5bd  lea     rdx, [rbp+57h+var_B0]
0x18004a5c1  mov     r15d, r14d
0x18004a5c4  mov     rax, [rax+18h]
0x18004a5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5cd  mov     ebx, eax
0x18004a5cf  test    eax, eax
0x18004a5d1  js      loc_18004A76C
0x18004a5d7  mov     rcx, [rbp+57h+var_B0]
0x18004a5db  lea     rdx, [rbp+57h+var_C0]
0x18004a5df  mov     dword ptr [rbp+57h+var_C0], r14d
0x18004a5e3  mov     rax, [rcx]
0x18004a5e6  mov     rax, [rax+18h]
0x18004a5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5ef  mov     edi, eax
0x18004a5f1  test    eax, eax
0x18004a5f3  jns     short loc_18004A666
0x18004a5f5  mov     rcx, [rbp+5Fh]; this
0x18004a5f9  lea     r8, aShellTwinuiBac; "shell\\twinui\\backstackmanager\\lib\\b"...
0x18004a600  mov     r9d, eax; char *
0x18004a603  mov     edx, 0C0h; void *
0x18004a608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a60d  lea     rcx, [rbp+57h+var_B0]
0x18004a611  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a616  mov     rcx, [rbp+57h+pv]
0x18004a61a  test    rcx, rcx
0x18004a61d  jz      short loc_18004A64E
0x18004a61f  mov     ebx, r14d
0x18004a622  cmp     [rbp+57h+var_A0], r14
0x18004a626  jbe     short loc_18004A63E
0x18004a628  lea     rcx, [rcx+rbx*8]
0x18004a62c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a631  mov     rcx, [rbp+57h+pv]; pv
0x18004a635  inc     rbx
0x18004a638  cmp     rbx, [rbp+57h+var_A0]
0x18004a63c  jb      short loc_18004A628
0x18004a63e  call    cs:__imp_CoTaskMemFree
0x18004a645  nop     dword ptr [rax+rax+00h]
0x18004a64a  mov     [rbp+57h+pv], r14
0x18004a64e  lea     rcx, [rbp+57h+ppvOut]
0x18004a652  mov     [rbp+57h+var_A0], r14
0x18004a656  mov     [rbp+57h+var_90], r14
0x18004a65a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a65f  mov     eax, edi
0x18004a661  jmp     loc_18004AAAB
0x18004a666  mov     esi, r14d
0x18004a669  cmp     dword ptr [rbp+57h+var_C0], r14d
0x18004a66d  jbe     loc_18004A76C
0x18004a673  mov     rdi, [rbp+57h+var_B0]
0x18004a677  lea     rcx, [rbp+57h+var_60]
0x18004a67b  mov     [rbp+57h+var_60], r14
0x18004a67f  mov     rax, [rdi]
0x18004a682  mov     rbx, [rax+20h]
0x18004a686  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a68b  lea     r9, [rbp+57h+var_60]
0x18004a68f  mov     edx, esi
0x18004a691  lea     r8, _GUID_8b14e88b_5663_4caf_b196_c31479262831
0x18004a698  mov     rcx, rdi
0x18004a69b  mov     rax, rbx
0x18004a69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6a3  test    eax, eax
0x18004a6a5  js      loc_18004A756
0x18004a6ab  mov     rcx, [rbp+57h+ppvOut]
0x18004a6af  mov     dword ptr [rbp+57h+var_80], r14d
0x18004a6b3  test    rcx, rcx
0x18004a6b6  jz      short loc_18004A6CC
0x18004a6b8  mov     rax, [rcx]
0x18004a6bb  lea     r8, [rbp+57h+var_80]
0x18004a6bf  mov     rdx, [rbp+57h+var_60]
0x18004a6c3  mov     rax, [rax+30h]
0x18004a6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6cc  lea     rcx, [rbp+57h+FileTime1]
0x18004a6d0  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x18004a6d4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a6d9  cmp     dword ptr [rbp+57h+var_80], r14d
0x18004a6dd  lea     r9, [rbp+57h+FileTime1]; void **
0x18004a6e1  mov     rcx, [rbp+57h+var_60]; struct IImmersiveApplication *
0x18004a6e5  setnz   dl; bool
0x18004a6e8  call    ?CreateInstance@CBackstackApp@@SAJPEAUIImmersiveApplication@@_NAEBU_GUID@@PEAPEAX@Z; CBackstackApp::CreateInstance(IImmersiveApplication *,bool,_GUID const &,void * *)
0x18004a6ed  test    eax, eax
0x18004a6ef  js      short loc_18004A74D
0x18004a6f1  mov     rcx, [rbp+57h+var_A0]
0x18004a6f5  cmp     rcx, [rbp+57h+var_90]
0x18004a6f9  jnz     short loc_18004A710
0x18004a6fb  lea     rdx, [rcx+1]
0x18004a6ff  lea     rcx, [rbp+57h+pv]
0x18004a703  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIGestureClient@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIGestureClient@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIGestureClient@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIGestureClient@@@@@@QEAAJ_K0@Z; CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18004a708  test    eax, eax
0x18004a70a  js      short loc_18004A744
0x18004a70c  mov     rcx, [rbp+57h+var_A0]
0x18004a710  mov     rdx, [rbp+57h+pv]
0x18004a714  inc     rcx
0x18004a717  add     rdx, 0FFFFFFFFFFFFFFF8h
0x18004a71b  mov     [rbp+57h+var_A0], rcx
0x18004a71f  lea     rdx, [rdx+rcx*8]
0x18004a723  test    rdx, rdx
0x18004a726  jz      short loc_18004A744
0x18004a728  mov     rax, qword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x18004a72c  mov     [rdx], rax
0x18004a72f  mov     rcx, qword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x18004a733  test    rcx, rcx
0x18004a736  jz      short loc_18004A744
0x18004a738  mov     rax, [rcx]
0x18004a73b  mov     rax, [rax+8]
0x18004a73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a744  cmp     dword ptr [rbp+57h+var_80], r14d
0x18004a748  jz      short loc_18004A74D
0x18004a74a  inc     r15d
0x18004a74d  lea     rcx, [rbp+57h+FileTime1]
0x18004a751  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a756  lea     rcx, [rbp+57h+var_60]
0x18004a75a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a75f  inc     esi
0x18004a761  cmp     esi, dword ptr [rbp+57h+var_C0]
0x18004a764  jb      loc_18004A673
0x18004a76a  jmp     short loc_18004A774
0x18004a76c  test    ebx, ebx
0x18004a76e  js      loc_18004AA0C
0x18004a774  mov     rcx, [rbp+57h+var_A0]
0x18004a778  cmp     rcx, 1
0x18004a77c  jbe     short loc_18004A7DC
0x18004a77e  shr     rcx, 1; unsigned __int64
0x18004a781  lea     r8, [rbp+57h+var_60]; unsigned __int64 *
0x18004a785  mov     edx, 8; unsigned __int64
0x18004a78a  mov     [rbp+57h+var_98], r14
0x18004a78e  mov     [rbp+57h+var_60], r14
0x18004a792  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004a797  test    eax, eax
0x18004a799  js      short loc_18004A7DC
0x18004a79b  mov     r9, [rbp+57h+var_60]; unsigned __int64
0x18004a79f  lea     rax, [rbp+57h+var_98]
0x18004a7a3  xor     r8d, r8d; void *
0x18004a7a6  mov     qword ptr [rsp+0F0h+var_D0], rax; void **
0x18004a7ab  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18004a7b0  test    eax, eax
0x18004a7b2  js      short loc_18004A7DC
0x18004a7b4  mov     r9, [rbp+57h+var_A0]
0x18004a7b8  lea     rdx, [rbp+57h+var_88]
0x18004a7bc  xor     r8d, r8d
0x18004a7bf  lea     rcx, [rbp+57h+pv]
0x18004a7c3  call    ??$_MergeSort@VCBackstackAppSort@@@?$CTSimpleArray@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@@@@@QEAAXAEBVCBackstackAppSort@@_K1@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IBackstackApp>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IBackstackApp>>>::_MergeSort<CBackstackAppSort>(CBackstackAppSort const &,unsigned __int64,unsigned __int64)
0x18004a7c8  mov     rcx, [rbp+57h+var_98]; pv
0x18004a7cc  call    cs:__imp_CoTaskMemFree
0x18004a7d3  nop     dword ptr [rax+rax+00h]
0x18004a7d8  mov     [rbp+57h+var_98], r14
0x18004a7dc  lea     rcx, [rbp+57h+var_60]
0x18004a7e0  mov     [rbp+57h+var_60], r14
0x18004a7e4  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18004a7e9  mov     r8, rax; void **
0x18004a7ec  call    ?CreateInstance@CEnumerableObjectCollection@@SAJHAEBU_GUID@@PEAPEAX@Z; CEnumerableObjectCollection::CreateInstance(int,_GUID const &,void * *)
0x18004a7f1  mov     ebx, eax
0x18004a7f3  test    eax, eax
0x18004a7f5  js      loc_18004A9EC
0x18004a7fb  mov     r13, [rbp+57h+var_A0]
0x18004a7ff  xor     edi, edi
0x18004a801  mov     r12, r14
0x18004a804  test    r13, r13
0x18004a807  jz      loc_18004A9CD
0x18004a80d  mov     rax, [rbp+57h+pv]
0x18004a811  mov     rsi, [rax+r14*8]
0x18004a815  test    rsi, rsi
0x18004a818  jz      short loc_18004A829
0x18004a81a  mov     rax, [rsi]
0x18004a81d  mov     rcx, rsi
0x18004a820  mov     rax, [rax+8]
0x18004a824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a829  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rdi
0x18004a82d  lea     rdx, [rbp+57h+FileTime1]
0x18004a831  mov     rax, [rsi]
0x18004a834  mov     rcx, rsi
0x18004a837  mov     rax, [rax+18h]
0x18004a83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a840  mov     [rbp+57h+var_C0], rdi
0x18004a844  lea     rcx, [rbp+57h+var_C0]
0x18004a848  mov     rax, [rsi]
0x18004a84b  mov     rbx, [rax+20h]
0x18004a84f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004a854  lea     r8, [rbp+57h+var_C0]
0x18004a858  mov     rcx, rsi
0x18004a85b  lea     rdx, _GUID_8b14e88b_5663_4caf_b196_c31479262831
0x18004a862  mov     rax, rbx
0x18004a865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a86a  test    eax, eax
0x18004a86c  js      loc_18004A958
0x18004a872  mov     rax, [rsi]
0x18004a875  mov     rcx, rsi
0x18004a878  mov     rax, [rax+30h]
0x18004a87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a881  test    al, al
0x18004a883  jnz     short loc_18004A8B2
0x18004a885  mov     eax, r15d
0x18004a888  neg     eax
0x18004a88a  cmp     r12, rax
0x18004a88d  jnb     loc_18004A958
0x18004a893  lea     rdx, ?s_FILETIME_MIN@BackstackHelpers@@3U_FILETIME@@B; lpFileTime2
0x18004a89a  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x18004a89e  call    cs:__imp_CompareFileTime
0x18004a8a5  nop     dword ptr [rax+rax+00h]
0x18004a8aa  test    eax, eax
0x18004a8ac  jz      loc_18004A958
0x18004a8b2  mov     rcx, [rbp+57h+var_60]
0x18004a8b6  mov     rdx, [rbp+57h+var_C0]
0x18004a8ba  mov     rax, [rcx]
0x18004a8bd  mov     rax, [rax+28h]
0x18004a8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8c6  test    eax, eax
0x18004a8c8  js      loc_18004A958
0x18004a8ce  mov     rax, [rsi]
0x18004a8d1  mov     rcx, rsi
0x18004a8d4  inc     r12
0x18004a8d7  mov     rax, [rax+30h]
0x18004a8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8e0  test    al, al
0x18004a8e2  jz      short loc_18004A8E7
0x18004a8e4  dec     r15d
0x18004a8e7  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18004a8ee  jz      loc_18004A999
0x18004a8f4  mov     [rbp+57h+var_80], rdi
0x18004a8f8  xor     ecx, ecx; pv
0x18004a8fa  mov     rdi, [rbp+57h+var_C0]
0x18004a8fe  mov     rax, [rdi]
0x18004a901  mov     rbx, [rax+20h]
0x18004a905  call    cs:__imp_CoTaskMemFree
0x18004a90c  nop     dword ptr [rax+rax+00h]
0x18004a911  lea     rdx, [rbp+57h+var_80]
0x18004a915  mov     rcx, rdi
0x18004a918  mov     rax, rbx
0x18004a91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a920  xor     edi, edi
0x18004a922  test    eax, eax
0x18004a924  js      short loc_18004A946
0x18004a926  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18004a92d  jz      short loc_18004A946
0x18004a92f  mov     r8, [rbp+57h+var_80]
0x18004a933  lea     rdx, BackstackManager_GetBackstack_Info
0x18004a93a  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18004a941  call    McTemplateU0z_EventWriteTransfer
0x18004a946  mov     rcx, [rbp+57h+var_80]; pv
0x18004a94a  call    cs:__imp_CoTaskMemFree
0x18004a951  nop     dword ptr [rax+rax+00h]
0x18004a956  jmp     short loc_18004A999
0x18004a958  cmp     [rbp+57h+var_70], edi
0x18004a95b  jz      short loc_18004A999
0x18004a95d  mov     rax, [rsi]
0x18004a960  mov     rcx, rsi
0x18004a963  mov     rax, [rax+28h]
0x18004a967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a96c  mov     rdx, [rbp+57h+var_C0]
0x18004a970  test    rdx, rdx
0x18004a973  jz      short loc_18004A999
0x18004a975  mov     ecx, [rbp+57h+FileTime1.dwHighDateTime]
0x18004a978  mov     r8d, 2
  ... truncated ...
```
