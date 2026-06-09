# MsixPackage::Provisioning::Library::MsixProvisioningManager::AddAllUserAppxLooseFiles(ushort *,ushort *,short)

- ea: `0x180035f40`
- end: `0x180036611`
- name: `?AddAllUserAppxLooseFiles@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEAG0F@Z`
- size: `1745`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningManager *__hidden this, unsigned __int16 *, unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180036618`

## callees

- `0x18000d3dc`
- `0x180034f30`
- `0x180035998`
- `0x180035f40`
- `0x18003d4ec`
- `0x18003d52c`
- `0x18003ead0`
- `0x18003f6f8`
- `0x18003ff14`
- `0x18004462c`
- `0x180053b30`
- `0x180056068`
- `0x1800681d0`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800363c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800363c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180036364`
- `OLEAUT32!__imp_SysFreeString` at `0x18003640a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800364ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800364c5`
- `OLEAUT32!__imp_SysFreeString` at `0x180036511`
- `OLEAUT32!__imp_SysFreeString` at `0x18003652a`
- `OLEAUT32!__imp_SysFreeString` at `0x180036364`
- `OLEAUT32!__imp_SysFreeString` at `0x18003640a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800364ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800364c5`
- `OLEAUT32!__imp_SysFreeString` at `0x180036511`
- `OLEAUT32!__imp_SysFreeString` at `0x18003652a`

## string_xrefs

- `0x1800360c5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003616f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180036202`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003627a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180036346`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800363ec`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180036498`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180036558`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180036549`: `Failed while notifying all user install agent scheduler.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::AddAllUserAppxLooseFiles(
        MsixPackage::Provisioning::Library::MsixProvisioningManager *this,
        unsigned __int16 *a2,
        char *a3,
        __int16 a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdx
  _QWORD *v9; // r8
  _QWORD *v10; // r9
  char *v11; // rbx
  char *v12; // r10
  int v13; // r11d
  int v14; // esi
  __int64 v15; // r14
  __int64 v16; // r15
  _QWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // esi
  int AppxDataFileTarget; // esi
  unsigned __int16 *v22; // rax
  OLECHAR *v23; // rbx
  int v24; // edi
  int v25; // ebx
  int v26; // [rsp+20h] [rbp-468h]
  int v27; // [rsp+20h] [rbp-468h]
  char *v28; // [rsp+28h] [rbp-460h]
  char *v29; // [rsp+28h] [rbp-460h]
  char *v30; // [rsp+30h] [rbp-458h]
  _QWORD *v31; // [rsp+38h] [rbp-450h]
  _QWORD *v32; // [rsp+40h] [rbp-448h]
  _QWORD *v33; // [rsp+48h] [rbp-440h]
  _QWORD *v34; // [rsp+50h] [rbp-438h]
  struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *v35; // [rsp+80h] [rbp-408h] BYREF
  int v36; // [rsp+88h] [rbp-400h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-3F8h] BYREF
  _QWORD v38[3]; // [rsp+A0h] [rbp-3E8h] BYREF
  __int16 v39; // [rsp+B8h] [rbp-3D0h]
  __int64 v40; // [rsp+C8h] [rbp-3C0h]
  __int64 v41; // [rsp+D0h] [rbp-3B8h]
  __int16 v42; // [rsp+D8h] [rbp-3B0h]
  __int64 v43; // [rsp+E8h] [rbp-3A0h]
  __int64 v44; // [rsp+F0h] [rbp-398h]
  __int64 v45; // [rsp+F8h] [rbp-390h]
  __int128 v46; // [rsp+100h] [rbp-388h]
  __int64 v47; // [rsp+110h] [rbp-378h]
  struct _RTL_AVL_TABLE Table; // [rsp+120h] [rbp-368h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  v7 = (_QWORD *)((char *)this + 168);
  if ( *((_QWORD *)this + 24) >= 8u )
    v7 = (_QWORD *)*v7;
  v8 = (_QWORD *)((char *)this + 72);
  if ( *((_QWORD *)this + 12) >= 8u )
    v8 = (_QWORD *)*v8;
  v9 = (_QWORD *)((char *)this + 136);
  if ( *((_QWORD *)this + 20) >= 8u )
    v9 = (_QWORD *)*v9;
  v10 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 16) >= 8u )
    v10 = (_QWORD *)*v10;
  v11 = (char *)this + 40;
  if ( *((_QWORD *)this + 8) < 8u )
    v12 = (char *)this + 40;
  else
    v12 = *(char **)v11;
  v13 = *((unsigned __int8 *)this + 8);
  v14 = *((_DWORD *)this + 8);
  v15 = *((_QWORD *)this + 3);
  v16 = *((_QWORD *)this + 2);
  v17 = (_QWORD *)((char *)this + 200);
  if ( v17[3] >= 8u )
    v17 = (_QWORD *)*v17;
  v34 = v7;
  v33 = v8;
  v32 = v9;
  v31 = v10;
  v30 = v12;
  LODWORD(v28) = v13;
  v26 = v14;
  MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(&Table, v17, v16, v15);
  v38[0] = &Table;
  v38[1] = a2;
  v38[2] = 0;
  v41 = 7;
  v40 = 0;
  v39 = 0;
  v44 = 7;
  v43 = 0;
  v42 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v35 = 0;
  if ( a3 )
  {
    if ( *(_WORD *)a3 )
    {
      v18 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::VerifyCustomDataPathExists(a3);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x396,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)v18,
          v26);
        MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v38);
        MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
        return v19;
      }
    }
  }
  v35 = 0;
  AppxDataFileTarget = MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(
                         (struct MsixPackage::Provisioning::Library::PackageSource *)v38,
                         (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table,
                         &v35);
  if ( AppxDataFileTarget < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)AppxDataFileTarget,
      (int)"Failed to initialize package set",
      v28,
      v30,
      v31,
      v32,
      v33,
      v34);
    if ( v35 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
LABEL_37:
    MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v38);
    MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
    return (unsigned int)AppxDataFileTarget;
  }
  AppxDataFileTarget = MsixPackage::Provisioning::Library::MsixProvisioningRequest::ProvisionPackagesOnline(
                         v35,
                         0,
                         a4 == -1,
                         1,
                         0,
                         0);
  if ( AppxDataFileTarget < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)AppxDataFileTarget,
      (int)"Failed to provision packages.",
      v29);
    if ( v35 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_37;
  }
  AppxDataFileTarget = MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges((MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table);
  if ( AppxDataFileTarget < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3A6,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)AppxDataFileTarget,
      (int)"Encountered failure while finalizing package provision list.",
      v29);
    if ( v35 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_37;
  }
  if ( a3 && *(_WORD *)a3 )
  {
    bstrString = 0;
    v36 = 0;
    AppxDataFileTarget = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetAppxDataFileTarget(
                           (OLECHAR *)&Table,
                           *((char **)v35 + 8),
                           &v36,
                           &bstrString);
    if ( AppxDataFileTarget < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3B1,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)AppxDataFileTarget,
        (int)"Failed to get appropriate data file target for package %ws",
        *((const char **)v35 + 8),
        v30,
        v31,
        v32,
        v33,
        v34);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v35 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
      goto LABEL_37;
    }
    if ( v36 )
    {
      if ( *((_QWORD *)v11 + 3) >= 8u )
        v11 = *(char **)v11;
      v22 = SysAllocString((const OLECHAR *)v11);
      v23 = v22;
      if ( !v22 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B6,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)0x8007000ELL,
          v27);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v35 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
        MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v38);
        MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
        return 2147942414LL;
      }
      v24 = MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile(
              (unsigned __int16 *)a3,
              bstrString,
              v22);
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x3BD,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)v24,
          (int)"Failed to add custom data to provisioned request for package %ws",
          *((const char **)v35 + 8),
          v30,
          v31,
          v32,
          v33,
          v34);
        SysFreeString(v23);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v35 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
        MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v38);
        MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
        return (unsigned int)v24;
      }
      SysFreeString(v23);
    }
    if ( bstrString )
      SysFreeString(bstrString);
  }
  v25 = RDSAppXOnlineNotifyPackageChanges();
  if ( v25 >= 0 )
  {
    if ( v35 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
    MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v38);
    MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3C2,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v25,
      (int)"Failed while notifying all user install agent scheduler.",
      v29);
    if ( v35 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v35 + 16LL))(v35);
    MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v38);
    MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
    return (unsigned int)v25;
  }
}

```

## disassembly

```asm
0x180035f40  mov     [rsp+arg_8], rbx
0x180035f45  mov     [rsp+arg_18], rsi
0x180035f4a  push    rdi
0x180035f4b  push    r12
0x180035f4d  push    r13
0x180035f4f  push    r14
0x180035f51  push    r15
0x180035f53  sub     rsp, 460h
0x180035f5a  mov     rax, cs:__security_cookie
0x180035f61  xor     rax, rsp
0x180035f64  mov     [rsp+488h+var_38], rax
0x180035f6c  movzx   r13d, r9w
0x180035f70  mov     rdi, r8
0x180035f73  mov     r12, rdx
0x180035f76  lea     rax, [rcx+0A8h]
0x180035f7d  cmp     qword ptr [rax+18h], 8
0x180035f82  jb      short loc_180035F87
0x180035f84  mov     rax, [rax]
0x180035f87  lea     rdx, [rcx+48h]
0x180035f8b  cmp     qword ptr [rdx+18h], 8
0x180035f90  jb      short loc_180035F95
0x180035f92  mov     rdx, [rdx]
0x180035f95  lea     r8, [rcx+88h]
0x180035f9c  cmp     qword ptr [r8+18h], 8
0x180035fa1  jb      short loc_180035FA6
0x180035fa3  mov     r8, [r8]
0x180035fa6  lea     r9, [rcx+68h]
0x180035faa  cmp     qword ptr [r9+18h], 8
0x180035faf  jb      short loc_180035FB4
0x180035fb1  mov     r9, [r9]
0x180035fb4  lea     rbx, [rcx+28h]
0x180035fb8  cmp     qword ptr [rbx+18h], 8
0x180035fbd  jb      short loc_180035FC4
0x180035fbf  mov     r10, [rbx]
0x180035fc2  jmp     short loc_180035FC7
0x180035fc4  mov     r10, rbx
0x180035fc7  movzx   r11d, byte ptr [rcx+8]
0x180035fcc  mov     esi, [rcx+20h]
0x180035fcf  mov     r14, [rcx+18h]
0x180035fd3  mov     r15, [rcx+10h]
0x180035fd7  add     rcx, 0C8h
0x180035fde  cmp     qword ptr [rcx+18h], 8
0x180035fe3  jb      short loc_180035FE8
0x180035fe5  mov     rcx, [rcx]
0x180035fe8  mov     [rsp+488h+var_438], rax
0x180035fed  mov     [rsp+488h+var_440], rdx
0x180035ff2  mov     [rsp+488h+var_448], r8
0x180035ff7  mov     [rsp+488h+var_450], r9
0x180035ffc  mov     [rsp+488h+var_458], r10
0x180036001  mov     dword ptr [rsp+488h+var_460], r11d; char *
0x180036006  mov     dword ptr [rsp+488h+var_468], esi; int
0x18003600a  mov     r9, r14
0x18003600d  mov     r8, r15
0x180036010  mov     rdx, rcx
0x180036013  lea     rcx, [rsp+488h+Table]
0x18003601b  call    ??0MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@PEBGPEAUHKEY__@@1JH00000W4StubPackageOption@@IH0@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(ushort const *,HKEY__ *,HKEY__ *,long,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,StubPackageOption,uint,int,ushort const *)
0x180036020  nop
0x180036021  lea     rax, [rsp+488h+Table]
0x180036029  mov     [rsp+488h+var_3E8], rax
0x180036031  mov     [rsp+488h+var_3E0], r12
0x180036039  xor     r14d, r14d
0x18003603c  mov     [rsp+488h+var_3D8], r14
0x180036044  lea     ecx, [r14+7]
0x180036048  mov     [rsp+488h+var_3B8], rcx
0x180036050  mov     [rsp+488h+var_3C0], r14
0x180036058  mov     [rsp+488h+var_3D0], r14w
0x180036061  mov     [rsp+488h+var_398], rcx
0x180036069  mov     [rsp+488h+var_3A0], r14
0x180036071  mov     [rsp+488h+var_3B0], r14w
0x18003607a  mov     [rsp+488h+var_390], r14
0x180036082  xorps   xmm0, xmm0
0x180036085  movdqa  [rsp+488h+var_388], xmm0
0x18003608e  mov     [rsp+488h+var_378], r14
0x180036096  mov     ecx, r14d
0x180036099  mov     [rsp+488h+var_408], rcx
0x1800360a1  test    rdi, rdi
0x1800360a4  jz      short loc_18003611B
0x1800360a6  cmp     [rdi], r14w
0x1800360aa  jz      short loc_18003611B
0x1800360ac  mov     rcx, rdi; char *
0x1800360af  call    ?VerifyCustomDataPathExists@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEAG@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::VerifyCustomDataPathExists(ushort *)
0x1800360b4  mov     esi, eax
0x1800360b6  test    eax, eax
0x1800360b8  jns     short loc_180036113
0x1800360ba  mov     rcx, [rsp+488h]; this
0x1800360c2  mov     r9d, eax; char *
0x1800360c5  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800360cc  mov     edx, 396h; void *
0x1800360d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800360d6  nop
0x1800360d7  mov     rcx, [rsp+488h+var_408]
0x1800360df  test    rcx, rcx
0x1800360e2  jz      short loc_1800360F1
0x1800360e4  mov     rax, [rcx]
0x1800360e7  mov     rax, [rax+10h]
0x1800360eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360f0  nop
0x1800360f1  lea     rcx, [rsp+488h+var_3E8]; this
0x1800360f9  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x1800360fe  nop
0x1800360ff  lea     rcx, [rsp+488h+Table]; Table
0x180036107  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x18003610c  mov     eax, esi
0x18003610e  jmp     loc_1800365E3
0x180036113  mov     rcx, [rsp+488h+var_408]
0x18003611b  mov     [rsp+488h+var_408], r14
0x180036123  test    rcx, rcx
0x180036126  jz      short loc_180036135
0x180036128  mov     rax, [rcx]
0x18003612b  mov     rax, [rax+10h]
0x18003612f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036134  nop
0x180036135  lea     r8, [rsp+488h+var_408]; struct MsixPackage::Provisioning::Library::MsixProvisioningRequest **
0x18003613d  lea     rdx, [rsp+488h+Table]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x180036145  lea     rcx, [rsp+488h+var_3E8]; struct MsixPackage::Provisioning::Library::PackageSource *
0x18003614d  call    ?CreateFromPackageSource@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@SAJPEAVPackageSource@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(MsixPackage::Provisioning::Library::PackageSource *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixProvisioningRequest * *)
0x180036152  mov     esi, eax
0x180036154  test    eax, eax
0x180036156  jns     short loc_1800361BD
0x180036158  mov     rcx, [rsp+488h]; this
0x180036160  lea     rax, aFailedToInitia_0; "Failed to initialize package set"
0x180036167  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003616c  mov     r9d, esi; char *
0x18003616f  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180036176  mov     edx, 39Dh; void *
0x18003617b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036180  nop
0x180036181  mov     rcx, [rsp+488h+var_408]
0x180036189  test    rcx, rcx
0x18003618c  jz      short loc_18003619B
0x18003618e  mov     rax, [rcx]
0x180036191  mov     rax, [rax+10h]
0x180036195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003619a  nop
0x18003619b  lea     rcx, [rsp+488h+var_3E8]; this
0x1800361a3  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x1800361a8  nop
0x1800361a9  lea     rcx, [rsp+488h+Table]; Table
0x1800361b1  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x1800361b6  mov     eax, esi
0x1800361b8  jmp     loc_1800365E3
0x1800361bd  mov     r8d, r14d
0x1800361c0  cmp     r13w, 0FFFFh
0x1800361c5  setz    r8b; int
0x1800361c9  mov     [rsp+488h+var_460], r14; char *
0x1800361ce  mov     [rsp+488h+var_468], r14b; int
0x1800361d3  mov     r9b, 1; bool
0x1800361d6  xor     edx, edx; unsigned __int16 *
0x1800361d8  mov     rcx, [rsp+488h+var_408]; this
0x1800361e0  call    ?ProvisionPackagesOnline@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEAGH_N1PEBG@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::ProvisionPackagesOnline(ushort *,int,bool,bool,ushort const *)
0x1800361e5  mov     esi, eax
0x1800361e7  test    eax, eax
0x1800361e9  jns     short loc_180036250
0x1800361eb  mov     rcx, [rsp+488h]; this
0x1800361f3  lea     rax, aFailedToProvis_1; "Failed to provision packages."
0x1800361fa  mov     qword ptr [rsp+488h+var_468], rax; int
0x1800361ff  mov     r9d, esi; char *
0x180036202  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180036209  mov     edx, 3A4h; void *
0x18003620e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036213  nop
0x180036214  mov     rcx, [rsp+488h+var_408]
0x18003621c  test    rcx, rcx
0x18003621f  jz      short loc_18003622E
0x180036221  mov     rax, [rcx]
0x180036224  mov     rax, [rax+10h]
0x180036228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003622d  nop
0x18003622e  lea     rcx, [rsp+488h+var_3E8]; this
0x180036236  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x18003623b  nop
0x18003623c  lea     rcx, [rsp+488h+Table]; Table
0x180036244  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x180036249  mov     eax, esi
0x18003624b  jmp     loc_1800365E3
0x180036250  lea     rcx, [rsp+488h+Table]; this
0x180036258  call    ?FinalizeChanges@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(void)
0x18003625d  mov     esi, eax
0x18003625f  test    eax, eax
0x180036261  jns     short loc_1800362C8
0x180036263  mov     rcx, [rsp+488h]; this
0x18003626b  lea     rax, aEncounteredFai_0; "Encountered failure while finalizing pa"...
0x180036272  mov     qword ptr [rsp+488h+var_468], rax; int
0x180036277  mov     r9d, esi; char *
0x18003627a  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180036281  mov     edx, 3A6h; void *
0x180036286  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003628b  nop
0x18003628c  mov     rcx, [rsp+488h+var_408]
0x180036294  test    rcx, rcx
0x180036297  jz      short loc_1800362A6
0x180036299  mov     rax, [rcx]
0x18003629c  mov     rax, [rax+10h]
0x1800362a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362a5  nop
0x1800362a6  lea     rcx, [rsp+488h+var_3E8]; this
0x1800362ae  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x1800362b3  nop
0x1800362b4  lea     rcx, [rsp+488h+Table]; Table
0x1800362bc  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x1800362c1  mov     eax, esi
0x1800362c3  jmp     loc_1800365E3
0x1800362c8  test    rdi, rdi
0x1800362cb  jz      loc_180036536
0x1800362d1  cmp     [rdi], r14w
0x1800362d5  jz      loc_180036536
0x1800362db  mov     [rsp+488h+bstrString], r14
0x1800362e3  mov     [rsp+488h+var_400], r14d
0x1800362eb  lea     r9, [rsp+488h+bstrString]
0x1800362f3  lea     r8, [rsp+488h+var_400]
0x1800362fb  mov     rdx, [rsp+488h+var_408]
0x180036303  mov     rdx, [rdx+40h]
0x180036307  lea     rcx, [rsp+488h+Table]
0x18003630f  call    ?GetAppxDataFileTarget@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetAppxDataFileTarget(ushort const *,int &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180036314  mov     esi, eax
0x180036316  test    eax, eax
0x180036318  jns     loc_1800363AD
0x18003631e  mov     rcx, [rsp+488h]; this
0x180036326  mov     rdx, [rsp+488h+var_408]
0x18003632e  mov     r8, [rdx+40h]
0x180036332  mov     [rsp+488h+var_460], r8; char *
0x180036337  lea     rax, aFailedToGetApp_0; "Failed to get appropriate data file tar"...
0x18003633e  mov     qword ptr [rsp+488h+var_468], rax; int
0x180036343  mov     r9d, esi; char *
0x180036346  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003634d  mov     edx, 3B1h; void *
0x180036352  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036357  mov     rcx, [rsp+488h+bstrString]; bstrString
0x18003635f  test    rcx, rcx
0x180036362  jz      short loc_180036371
0x180036364  call    cs:__imp_SysFreeString
0x18003636b  nop     dword ptr [rax+rax+00h]
0x180036370  nop
0x180036371  mov     rcx, [rsp+488h+var_408]
0x180036379  test    rcx, rcx
0x18003637c  jz      short loc_18003638B
0x18003637e  mov     rax, [rcx]
0x180036381  mov     rax, [rax+10h]
0x180036385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003638a  nop
0x18003638b  lea     rcx, [rsp+488h+var_3E8]; this
0x180036393  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x180036398  nop
0x180036399  lea     rcx, [rsp+488h+Table]; Table
0x1800363a1  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x1800363a6  mov     eax, esi
0x1800363a8  jmp     loc_1800365E3
0x1800363ad  cmp     [rsp+488h+var_400], r14d
0x1800363b5  jz      loc_18003651D
0x1800363bb  cmp     qword ptr [rbx+18h], 8
0x1800363c0  jb      short loc_1800363C5
0x1800363c2  mov     rbx, [rbx]
0x1800363c5  mov     rcx, rbx; psz
0x1800363c8  call    cs:__imp_SysAllocString
0x1800363cf  nop     dword ptr [rax+rax+00h]
0x1800363d4  mov     rbx, rax
0x1800363d7  test    rax, rax
0x1800363da  jnz     short loc_180036453
0x1800363dc  mov     rcx, [rsp+488h]; this
0x1800363e4  mov     ebx, 8007000Eh
0x1800363e9  mov     r9d, ebx; char *
0x1800363ec  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800363f3  mov     edx, 3B6h; void *
0x1800363f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800363fd  mov     rcx, [rsp+488h+bstrString]; bstrString
0x180036405  test    rcx, rcx
0x180036408  jz      short loc_180036417
0x18003640a  call    cs:__imp_SysFreeString
0x180036411  nop     dword ptr [rax+rax+00h]
0x180036416  nop
0x180036417  mov     rcx, [rsp+488h+var_408]
0x18003641f  test    rcx, rcx
0x180036422  jz      short loc_180036431
0x180036424  mov     rdx, [rcx]
0x180036427  mov     rax, [rdx+10h]
0x18003642b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036430  nop
0x180036431  lea     rcx, [rsp+488h+var_3E8]; this
0x180036439  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x18003643e  nop
0x18003643f  lea     rcx, [rsp+488h+Table]; Table
0x180036447  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x18003644c  mov     eax, ebx
0x18003644e  jmp     loc_1800365E3
0x180036453  mov     r8, rbx; unsigned __int16 *
0x180036456  mov     rdx, [rsp+488h+bstrString]; unsigned __int16 *
0x18003645e  mov     rcx, rdi; unsigned __int16 *
0x180036461  call    ?SetProvisionedAppxDataFile@MsixProvisioningManager@Library@Provisioning@MsixPackage@@SAJPEAG00@Z; MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile(ushort *,ushort *,ushort *)
0x180036466  mov     edi, eax
0x180036468  test    eax, eax
0x18003646a  jns     loc_18003650E
0x180036470  mov     rcx, [rsp+488h]; this
0x180036478  mov     rdx, [rsp+488h+var_408]
0x180036480  mov     r8, [rdx+40h]
0x180036484  mov     [rsp+488h+var_460], r8; char *
0x180036489  lea     rax, aFailedToAddCus; "Failed to add custom data to provisione"...
0x180036490  mov     qword ptr [rsp+488h+var_468], rax; int
0x180036495  mov     r9d, edi; char *
0x180036498  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003649f  mov     edx, 3BDh; void *
  ... truncated ...
```
