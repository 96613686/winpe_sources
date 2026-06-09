# CARPFolderEnum::Next(ulong,_ITEMID_CHILD * *,ulong *)

- ea: `0x1800153d0`
- end: `0x1800156b2`
- name: `?Next@CARPFolderEnum@@UEAAJKPEAPEAU_ITEMID_CHILD@@PEAK@Z`
- size: `738`
- prototype: `__int64 __fastcall(CARPFolderEnum *__hidden this, unsigned int, struct _ITEMID_CHILD **, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008cf8`
- `0x18000b340`
- `0x1800153d0`
- `0x180019340`
- `0x1800198bc`
- `0x180019adc`
- `0x180019b2c`
- `0x180019bec`
- `0x18001a1f8`
- `0x18001a3a4`
- `0x18001a474`
- `0x18001b5b8`
- `0x180044ca0`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x18001541c`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180015434`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001544e`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001541c`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180015434`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001544e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015647`

## pseudocode

```c
__int64 __fastcall CARPFolderEnum::Next(CARPFolderEnum *this, __int64 a2, struct _ITEMID_CHILD **a3, unsigned int *a4)
{
  __int64 v4; // rax
  unsigned int *v6; // r13
  int v8; // r14d
  int v9; // r15d
  int NextVUE; // ebx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int NextCBSPackage; // eax
  void *v17; // r14
  struct IUnknown *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v20; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h]
  __int128 v22; // [rsp+58h] [rbp-A8h]
  LPVOID pv[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v24[264]; // [rsp+80h] [rbp-80h] BYREF

  v4 = *((_QWORD *)this + 4);
  pv[0] = a4;
  v6 = a4;
  v8 = *(_DWORD *)(v4 + 128);
  v9 = 0;
  if ( (unsigned int)SHWindowsPolicy(POLID_NoProgramsCPL)
    || (unsigned int)SHWindowsPolicy(POLID_NoInstalledUpdates) && v8
    || (unsigned int)SHWindowsPolicy(POLID_NoProgramsAndFeatures) && !v8 )
  {
    NextVUE = 1;
  }
  else
  {
    if ( v8 )
    {
      NextVUE = CARPFolderEnum::_EnsureVUE((HKEY *)this);
      if ( !NextVUE )
      {
        v19 = 0;
        NextVUE = CARPFolderEnum::_GetNextVUE(this, &v19, v24);
        if ( !NextVUE )
          NextVUE = CARPFolderEnum::_CreateItemIDFromCBSPackage(this, (struct ICbsPackage *)v19, a3, 1, v24);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      }
      if ( NextVUE != 1 )
        goto LABEL_45;
      v19 = 0;
      NextVUE = CARPFolderEnum::_GetNextSystemMsp(this, (struct IInstalledApp **)&v19);
      if ( !NextVUE )
        NextVUE = CARPFolderEnum::_CreateItemIDFromInstalledApp(this, v19, a3);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      if ( NextVUE != 1 )
        goto LABEL_45;
    }
    v11 = CARPFolderEnum::_EnsureInstalledApps(this);
    NextVUE = v11;
    if ( !*((_DWORD *)this + 32) && v11 >= 0 )
    {
      do
      {
        v12 = *((_QWORD *)this + 5);
        v19 = 0;
        NextVUE = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v12 + 24LL))(v12, &v19);
        if ( NextVUE )
        {
          *((_DWORD *)this + 32) = 1;
        }
        else
        {
          v9 = 0;
          v20 = 0x200000030uLL;
          v21 = 0;
          v22 = 0;
          if ( (int)IAppUpdate_GetAppUpdateInfo(v19, (struct APPUPDATEINFO *)&v20) >= 0 )
          {
            if ( (_QWORD)v21 && *(_WORD *)v21 )
              v9 = NextVUE + 1;
            ClearAppUpdateInfo((LPVOID *)&v20);
          }
          if ( v9 == v8 )
            NextVUE = CARPFolderEnum::_CreateItemIDFromInstalledApp(this, v19, a3);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      }
      while ( !NextVUE && v9 != v8 );
      v6 = (unsigned int *)pv[0];
    }
    if ( v8 )
    {
LABEL_45:
      if ( *((_DWORD *)this + 32) )
      {
        NextVUE = CARPFolderEnum::_EnsureCBS(this);
        if ( NextVUE >= 0 )
        {
          v19 = 0;
          pv[0] = 0;
          NextCBSPackage = CARPFolderEnum::_GetNextCBSPackage(this, (struct ICbsPackage **)&v19, pv);
          NextVUE = NextCBSPackage;
          if ( NextCBSPackage >= 0 )
          {
            v17 = pv[0];
            if ( !NextCBSPackage )
              NextVUE = CARPFolderEnum::_CreateItemIDFromCBSPackage(
                          this,
                          (struct ICbsPackage *)v19,
                          a3,
                          0,
                          (unsigned __int16 *)pv[0]);
            CoTaskMemFree(v17);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        }
        if ( (Microsoft_Windows_Shell_AppWizCplEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            v13,
            (const EVENT_DESCRIPTOR *)&AppWizCpl_SoftwareExplorer_InstalledProgramsView_Stop,
            v14,
            v15,
            (PEVENT_DATA_DESCRIPTOR)pv);
      }
    }
  }
  if ( v6 )
    *v6 = NextVUE == 0;
  return (unsigned int)NextVUE;
}

```

## disassembly

```asm
0x1800153d0  push    rbp
0x1800153d2  push    rbx
0x1800153d3  push    rdi
0x1800153d4  push    r12
0x1800153d6  push    r13
0x1800153d8  push    r14
0x1800153da  push    r15
0x1800153dc  lea     rbp, [rsp-1A0h]
0x1800153e4  sub     rsp, 2A0h
0x1800153eb  mov     rax, cs:__security_cookie
0x1800153f2  xor     rax, rsp
0x1800153f5  mov     [rbp+1D0h+var_40], rax
0x1800153fc  mov     rax, [rcx+20h]
0x180015400  mov     rdi, rcx
0x180015403  lea     rcx, POLID_NoProgramsCPL
0x18001540a  mov     [rsp+2D0h+pv], r9
0x18001540f  mov     r13, r9
0x180015412  mov     r12, r8
0x180015415  mov     r14d, [rax+80h]
0x18001541c  call    cs:__imp_SHWindowsPolicy
0x180015422  xor     r15d, r15d
0x180015425  test    eax, eax
0x180015427  jnz     loc_180015678
0x18001542d  lea     rcx, POLID_NoInstalledUpdates
0x180015434  call    cs:__imp_SHWindowsPolicy
0x18001543a  test    eax, eax
0x18001543c  jz      short loc_180015447
0x18001543e  test    r14d, r14d
0x180015441  jnz     loc_180015678
0x180015447  lea     rcx, POLID_NoProgramsAndFeatures
0x18001544e  call    cs:__imp_SHWindowsPolicy
0x180015454  test    eax, eax
0x180015456  jz      short loc_180015461
0x180015458  test    r14d, r14d
0x18001545b  jz      loc_180015678
0x180015461  test    r14d, r14d
0x180015464  jz      loc_180015503
0x18001546a  mov     rcx, rdi; this
0x18001546d  call    ?_EnsureVUE@CARPFolderEnum@@AEAAJXZ; CARPFolderEnum::_EnsureVUE(void)
0x180015472  mov     ebx, eax
0x180015474  test    eax, eax
0x180015476  jnz     short loc_1800154BD
0x180015478  lea     r8, [rbp+1D0h+var_250]; unsigned __int16 *
0x18001547c  mov     [rsp+2D0h+var_2A0], r15
0x180015481  lea     rdx, [rsp+2D0h+var_2A0]; struct ICbsPackage **
0x180015486  mov     rcx, rdi; this
0x180015489  call    ?_GetNextVUE@CARPFolderEnum@@AEAAJPEAPEAUICbsPackage@@PEAG_K@Z; CARPFolderEnum::_GetNextVUE(ICbsPackage * *,ushort *,unsigned __int64)
0x18001548e  mov     ebx, eax
0x180015490  test    eax, eax
0x180015492  jnz     short loc_1800154B3
0x180015494  mov     rdx, [rsp+2D0h+var_2A0]; struct ICbsPackage *
0x180015499  lea     rax, [rbp+1D0h+var_250]
0x18001549d  lea     r9d, [rbx+1]; int
0x1800154a1  mov     [rsp+2D0h+var_2B0], rax; unsigned __int16 *
0x1800154a6  mov     r8, r12; struct _ITEMID_CHILD **
0x1800154a9  mov     rcx, rdi; this
0x1800154ac  call    ?_CreateItemIDFromCBSPackage@CARPFolderEnum@@AEAAJPEAUICbsPackage@@PEAPEAU_ITEMID_CHILD@@HPEBG@Z; CARPFolderEnum::_CreateItemIDFromCBSPackage(ICbsPackage *,_ITEMID_CHILD * *,int,ushort const *)
0x1800154b1  mov     ebx, eax
0x1800154b3  lea     rcx, [rsp+2D0h+var_2A0]
0x1800154b8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800154bd  cmp     ebx, 1
0x1800154c0  jnz     loc_1800155E6
0x1800154c6  lea     rdx, [rsp+2D0h+var_2A0]; struct IInstalledApp **
0x1800154cb  mov     [rsp+2D0h+var_2A0], r15
0x1800154d0  mov     rcx, rdi; this
0x1800154d3  call    ?_GetNextSystemMsp@CARPFolderEnum@@AEAAJPEAPEAUIInstalledApp@@@Z; CARPFolderEnum::_GetNextSystemMsp(IInstalledApp * *)
0x1800154d8  mov     ebx, eax
0x1800154da  test    eax, eax
0x1800154dc  jnz     short loc_1800154F0
0x1800154de  mov     rdx, [rsp+2D0h+var_2A0]; struct IUnknown *
0x1800154e3  mov     r8, r12; struct _ITEMID_CHILD **
0x1800154e6  mov     rcx, rdi; this
0x1800154e9  call    ?_CreateItemIDFromInstalledApp@CARPFolderEnum@@AEAAJPEAUIInstalledApp@@PEAPEAU_ITEMID_CHILD@@@Z; CARPFolderEnum::_CreateItemIDFromInstalledApp(IInstalledApp *,_ITEMID_CHILD * *)
0x1800154ee  mov     ebx, eax
0x1800154f0  lea     rcx, [rsp+2D0h+var_2A0]
0x1800154f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800154fa  cmp     ebx, 1
0x1800154fd  jnz     loc_1800155E6
0x180015503  mov     rcx, rdi; this
0x180015506  call    ?_EnsureInstalledApps@CARPFolderEnum@@AEAAJXZ; CARPFolderEnum::_EnsureInstalledApps(void)
0x18001550b  mov     ebx, eax
0x18001550d  cmp     [rdi+80h], r15d
0x180015514  jnz     loc_1800155DD
0x18001551a  test    eax, eax
0x18001551c  js      loc_1800155DD
0x180015522  xor     r13d, r13d
0x180015525  mov     rcx, [rdi+28h]
0x180015529  lea     rdx, [rsp+2D0h+var_2A0]
0x18001552e  mov     [rsp+2D0h+var_2A0], r13
0x180015533  mov     rax, [rcx]
0x180015536  mov     rax, [rax+18h]
0x18001553a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001553f  mov     ebx, eax
0x180015541  test    eax, eax
0x180015543  jnz     short loc_1800155B4
0x180015545  mov     rcx, [rsp+2D0h+var_2A0]; struct IUnknown *
0x18001554a  lea     rdx, [rsp+2D0h+var_298]; struct APPUPDATEINFO *
0x18001554f  xorps   xmm0, xmm0
0x180015552  mov     r15d, r13d
0x180015555  movups  [rsp+2D0h+var_298], xmm0
0x18001555a  mov     dword ptr [rsp+2D0h+var_298], 30h ; '0'
0x180015562  mov     dword ptr [rsp+2D0h+var_298+4], 2
0x18001556a  movups  [rsp+2D0h+var_288], xmm0
0x18001556f  movups  [rsp+2D0h+var_278], xmm0
0x180015574  call    ?IAppUpdate_GetAppUpdateInfo@@YAJPEAUIUnknown@@PEAUAPPUPDATEINFO@@@Z; IAppUpdate_GetAppUpdateInfo(IUnknown *,APPUPDATEINFO *)
0x180015579  test    eax, eax
0x18001557b  js      short loc_18001559B
0x18001557d  mov     rax, qword ptr [rsp+2D0h+var_288]
0x180015582  test    rax, rax
0x180015585  jz      short loc_180015591
0x180015587  cmp     [rax], r13w
0x18001558b  jz      short loc_180015591
0x18001558d  lea     r15d, [rbx+1]
0x180015591  lea     rcx, [rsp+2D0h+var_298]; struct APPUPDATEINFO *
0x180015596  call    ?ClearAppUpdateInfo@@YAXPEAUAPPUPDATEINFO@@@Z; ClearAppUpdateInfo(APPUPDATEINFO *)
0x18001559b  cmp     r15d, r14d
0x18001559e  jnz     short loc_1800155BE
0x1800155a0  mov     rdx, [rsp+2D0h+var_2A0]; struct IUnknown *
0x1800155a5  mov     r8, r12; struct _ITEMID_CHILD **
0x1800155a8  mov     rcx, rdi; this
0x1800155ab  call    ?_CreateItemIDFromInstalledApp@CARPFolderEnum@@AEAAJPEAUIInstalledApp@@PEAPEAU_ITEMID_CHILD@@@Z; CARPFolderEnum::_CreateItemIDFromInstalledApp(IInstalledApp *,_ITEMID_CHILD * *)
0x1800155b0  mov     ebx, eax
0x1800155b2  jmp     short loc_1800155BE
0x1800155b4  mov     dword ptr [rdi+80h], 1
0x1800155be  lea     rcx, [rsp+2D0h+var_2A0]
0x1800155c3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800155c8  test    ebx, ebx
0x1800155ca  jnz     short loc_1800155D5
0x1800155cc  cmp     r15d, r14d
0x1800155cf  jnz     loc_180015525
0x1800155d5  mov     r13, [rsp+2D0h+pv]
0x1800155da  xor     r15d, r15d
0x1800155dd  test    r14d, r14d
0x1800155e0  jz      loc_18001567D
0x1800155e6  cmp     [rdi+80h], r15d
0x1800155ed  jz      loc_18001567D
0x1800155f3  mov     rcx, rdi; this
0x1800155f6  call    ?_EnsureCBS@CARPFolderEnum@@AEAAJXZ; CARPFolderEnum::_EnsureCBS(void)
0x1800155fb  mov     ebx, eax
0x1800155fd  test    eax, eax
0x1800155ff  js      short loc_180015657
0x180015601  lea     r8, [rsp+2D0h+pv]; unsigned __int16 **
0x180015606  mov     [rsp+2D0h+var_2A0], r15
0x18001560b  lea     rdx, [rsp+2D0h+var_2A0]; struct ICbsPackage **
0x180015610  mov     [rsp+2D0h+pv], r15
0x180015615  mov     rcx, rdi; this
0x180015618  call    ?_GetNextCBSPackage@CARPFolderEnum@@AEAAJPEAPEAUICbsPackage@@PEAPEAG@Z; CARPFolderEnum::_GetNextCBSPackage(ICbsPackage * *,ushort * *)
0x18001561d  mov     ebx, eax
0x18001561f  test    eax, eax
0x180015621  js      short loc_18001564D
0x180015623  mov     r14, [rsp+2D0h+pv]
0x180015628  jnz     short loc_180015644
0x18001562a  mov     rdx, [rsp+2D0h+var_2A0]; struct ICbsPackage *
0x18001562f  xor     r9d, r9d; int
0x180015632  mov     r8, r12; struct _ITEMID_CHILD **
0x180015635  mov     [rsp+2D0h+var_2B0], r14; unsigned __int16 *
0x18001563a  mov     rcx, rdi; this
0x18001563d  call    ?_CreateItemIDFromCBSPackage@CARPFolderEnum@@AEAAJPEAUICbsPackage@@PEAPEAU_ITEMID_CHILD@@HPEBG@Z; CARPFolderEnum::_CreateItemIDFromCBSPackage(ICbsPackage *,_ITEMID_CHILD * *,int,ushort const *)
0x180015642  mov     ebx, eax
0x180015644  mov     rcx, r14; pv
0x180015647  call    cs:__imp_CoTaskMemFree
0x18001564d  lea     rcx, [rsp+2D0h+var_2A0]
0x180015652  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015657  test    cs:Microsoft_Windows_Shell_AppWizCplEnableBits, 1
0x18001565e  jz      short loc_18001567D
0x180015660  lea     rax, [rsp+2D0h+pv]
0x180015665  lea     rdx, AppWizCpl_SoftwareExplorer_InstalledProgramsView_Stop; int
0x18001566c  mov     [rsp+2D0h+var_2B0], rax; PEVENT_DATA_DESCRIPTOR
0x180015671  call    McGenEventWrite_EventWriteTransfer
0x180015676  jmp     short loc_18001567D
0x180015678  mov     ebx, 1
0x18001567d  test    r13, r13
0x180015680  jz      short loc_18001568E
0x180015682  mov     eax, r15d
0x180015685  test    ebx, ebx
0x180015687  setz    al
0x18001568a  mov     [r13+0], eax
0x18001568e  mov     eax, ebx
0x180015690  mov     rcx, [rbp+1D0h+var_40]
0x180015697  xor     rcx, rsp; StackCookie
0x18001569a  call    __security_check_cookie
0x18001569f  add     rsp, 2A0h
0x1800156a6  pop     r15
0x1800156a8  pop     r14
0x1800156aa  pop     r13
0x1800156ac  pop     r12
0x1800156ae  pop     rdi
0x1800156af  pop     rbx
0x1800156b0  pop     rbp
0x1800156b1  retn
```
