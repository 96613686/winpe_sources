# MsixPackage::Provisioning::Library::MsixProvisioningManager::AddAllUserAppxLooseFiles(ushort *,ushort *,short)

- ea: `0x180032f28`
- end: `0x1800335cf`
- name: `?AddAllUserAppxLooseFiles@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEAG0F@Z`
- size: `1703`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningManager *this, unsigned __int16 *, char *, __int16)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800335d8`

## callees

- `0x18000cfe8`
- `0x180032058`
- `0x1800329f4`
- `0x180032f28`
- `0x180039e9c`
- `0x180039edc`
- `0x18003b3f8`
- `0x18003bf94`
- `0x18003c740`
- `0x180040a04`
- `0x18004f76c`
- `0x180051c7c`
- `0x180062b68`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800333aa`
- `OLEAUT32!__imp_SysAllocString` at `0x1800333aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18003334c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800333e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180033482`
- `OLEAUT32!__imp_SysFreeString` at `0x180033495`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18003334c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800333e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180033482`
- `OLEAUT32!__imp_SysFreeString` at `0x180033495`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334ee`

## string_xrefs

- `0x1800330ad`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180033157`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800331ea`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180033262`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003332e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800333c8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003346e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180033516`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180033507`: `Failed while notifying all user install agent scheduler.`

## pseudocode

```c
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
  struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *v30; // [rsp+80h] [rbp-408h] BYREF
  int v31; // [rsp+88h] [rbp-400h]
  BSTR bstrString; // [rsp+90h] [rbp-3F8h]
  _QWORD v33[3]; // [rsp+A0h] [rbp-3E8h] BYREF
  __int16 v34; // [rsp+B8h] [rbp-3D0h]
  __int64 v35; // [rsp+C8h] [rbp-3C0h]
  __int64 v36; // [rsp+D0h] [rbp-3B8h]
  __int16 v37; // [rsp+D8h] [rbp-3B0h]
  __int64 v38; // [rsp+E8h] [rbp-3A0h]
  __int64 v39; // [rsp+F0h] [rbp-398h]
  __int64 v40; // [rsp+F8h] [rbp-390h]
  __int128 v41; // [rsp+100h] [rbp-388h]
  __int64 v42; // [rsp+110h] [rbp-378h]
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
  MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(
    (__int64)&Table,
    (__int64)v17,
    v16,
    v15,
    v14,
    v13,
    (__int64)v12,
    (__int64)v10,
    (__int64)v9,
    (__int64)v8,
    (__int64)v7);
  v33[0] = &Table;
  v33[1] = a2;
  v33[2] = 0;
  v36 = 7;
  v35 = 0;
  v34 = 0;
  v39 = 7;
  v38 = 0;
  v37 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v30 = 0;
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
        MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v33);
        MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
        return v19;
      }
    }
  }
  v30 = 0;
  AppxDataFileTarget = MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(
                         (struct MsixPackage::Provisioning::Library::PackageSource *)v33,
                         (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table,
                         &v30);
  if ( AppxDataFileTarget < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)AppxDataFileTarget,
      (int)"Failed to initialize package set",
      v28);
    if ( v30 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
LABEL_37:
    MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v33);
    MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
    return (unsigned int)AppxDataFileTarget;
  }
  AppxDataFileTarget = MsixPackage::Provisioning::Library::MsixProvisioningRequest::ProvisionPackagesOnline(
                         v30,
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
    if ( v30 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
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
    if ( v30 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
    goto LABEL_37;
  }
  if ( a3 && *(_WORD *)a3 )
  {
    bstrString = 0;
    v31 = 0;
    AppxDataFileTarget = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetAppxDataFileTarget(
                           (MsixPackage::Provisioning::Library::MsixProvisioningContext *)&Table,
                           *((char **)v30 + 8));
    if ( AppxDataFileTarget < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3B1,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)AppxDataFileTarget,
        (int)"Failed to get appropriate data file target for package %ws",
        *((const char **)v30 + 8));
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v30 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
      goto LABEL_37;
    }
    if ( v31 )
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
        if ( v30 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
        MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v33);
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
          *((const char **)v30 + 8));
        SysFreeString(v23);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v30 )
          (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
        MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v33);
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
    if ( v30 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
    MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v33);
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
    if ( v30 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixProvisioningRequest *))(*(_QWORD *)v30 + 16LL))(v30);
    MsixPackage::Provisioning::Library::PackageSource::~PackageSource((MsixPackage::Provisioning::Library::PackageSource *)v33);
    MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(&Table);
    return (unsigned int)v25;
  }
}

```

## disassembly

```asm
0x180032f28  mov     [rsp+arg_8], rbx
0x180032f2d  mov     [rsp+arg_18], rsi
0x180032f32  push    rdi
0x180032f33  push    r12
0x180032f35  push    r13
0x180032f37  push    r14
0x180032f39  push    r15
0x180032f3b  sub     rsp, 460h
0x180032f42  mov     rax, cs:__security_cookie
0x180032f49  xor     rax, rsp
0x180032f4c  mov     [rsp+488h+var_38], rax
0x180032f54  movzx   r13d, r9w
0x180032f58  mov     rdi, r8
0x180032f5b  mov     r12, rdx
0x180032f5e  lea     rax, [rcx+0A8h]
0x180032f65  cmp     qword ptr [rax+18h], 8
0x180032f6a  jb      short loc_180032F6F
0x180032f6c  mov     rax, [rax]
0x180032f6f  lea     rdx, [rcx+48h]
0x180032f73  cmp     qword ptr [rdx+18h], 8
0x180032f78  jb      short loc_180032F7D
0x180032f7a  mov     rdx, [rdx]
0x180032f7d  lea     r8, [rcx+88h]
0x180032f84  cmp     qword ptr [r8+18h], 8
0x180032f89  jb      short loc_180032F8E
0x180032f8b  mov     r8, [r8]
0x180032f8e  lea     r9, [rcx+68h]
0x180032f92  cmp     qword ptr [r9+18h], 8
0x180032f97  jb      short loc_180032F9C
0x180032f99  mov     r9, [r9]
0x180032f9c  lea     rbx, [rcx+28h]
0x180032fa0  cmp     qword ptr [rbx+18h], 8
0x180032fa5  jb      short loc_180032FAC
0x180032fa7  mov     r10, [rbx]
0x180032faa  jmp     short loc_180032FAF
0x180032fac  mov     r10, rbx
0x180032faf  movzx   r11d, byte ptr [rcx+8]
0x180032fb4  mov     esi, [rcx+20h]
0x180032fb7  mov     r14, [rcx+18h]
0x180032fbb  mov     r15, [rcx+10h]
0x180032fbf  add     rcx, 0C8h
0x180032fc6  cmp     qword ptr [rcx+18h], 8
0x180032fcb  jb      short loc_180032FD0
0x180032fcd  mov     rcx, [rcx]
0x180032fd0  mov     [rsp+488h+var_438], rax
0x180032fd5  mov     [rsp+488h+var_440], rdx
0x180032fda  mov     [rsp+488h+var_448], r8
0x180032fdf  mov     [rsp+488h+var_450], r9
0x180032fe4  mov     [rsp+488h+var_458], r10
0x180032fe9  mov     dword ptr [rsp+488h+var_460], r11d; char *
0x180032fee  mov     dword ptr [rsp+488h+var_468], esi; int
0x180032ff2  mov     r9, r14
0x180032ff5  mov     r8, r15
0x180032ff8  mov     rdx, rcx
0x180032ffb  lea     rcx, [rsp+488h+Table]
0x180033003  call    ??0MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@PEBGPEAUHKEY__@@1JH00000W4StubPackageOption@@IH0@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::MsixProvisioningContext(ushort const *,HKEY__ *,HKEY__ *,long,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,StubPackageOption,uint,int,ushort const *)
0x180033008  nop
0x180033009  lea     rax, [rsp+488h+Table]
0x180033011  mov     [rsp+488h+var_3E8], rax
0x180033019  mov     [rsp+488h+var_3E0], r12
0x180033021  xor     r14d, r14d
0x180033024  mov     [rsp+488h+var_3D8], r14
0x18003302c  lea     ecx, [r14+7]
0x180033030  mov     [rsp+488h+var_3B8], rcx
0x180033038  mov     [rsp+488h+var_3C0], r14
0x180033040  mov     [rsp+488h+var_3D0], r14w
0x180033049  mov     [rsp+488h+var_398], rcx
0x180033051  mov     [rsp+488h+var_3A0], r14
0x180033059  mov     [rsp+488h+var_3B0], r14w
0x180033062  mov     [rsp+488h+var_390], r14
0x18003306a  xorps   xmm0, xmm0
0x18003306d  movdqa  [rsp+488h+var_388], xmm0
0x180033076  mov     [rsp+488h+var_378], r14
0x18003307e  mov     ecx, r14d
0x180033081  mov     [rsp+488h+var_408], rcx
0x180033089  test    rdi, rdi
0x18003308c  jz      short loc_180033103
0x18003308e  cmp     [rdi], r14w
0x180033092  jz      short loc_180033103
0x180033094  mov     rcx, rdi; char *
0x180033097  call    ?VerifyCustomDataPathExists@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEAG@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::VerifyCustomDataPathExists(ushort *)
0x18003309c  mov     esi, eax
0x18003309e  test    eax, eax
0x1800330a0  jns     short loc_1800330FB
0x1800330a2  mov     rcx, [rsp+488h]; this
0x1800330aa  mov     r9d, eax; char *
0x1800330ad  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800330b4  mov     edx, 396h; void *
0x1800330b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800330be  nop
0x1800330bf  mov     rcx, [rsp+488h+var_408]
0x1800330c7  test    rcx, rcx
0x1800330ca  jz      short loc_1800330D9
0x1800330cc  mov     rax, [rcx]
0x1800330cf  mov     rax, [rax+10h]
0x1800330d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330d8  nop
0x1800330d9  lea     rcx, [rsp+488h+var_3E8]; this
0x1800330e1  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x1800330e6  nop
0x1800330e7  lea     rcx, [rsp+488h+Table]; Table
0x1800330ef  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x1800330f4  mov     eax, esi
0x1800330f6  jmp     loc_1800335A1
0x1800330fb  mov     rcx, [rsp+488h+var_408]
0x180033103  mov     [rsp+488h+var_408], r14
0x18003310b  test    rcx, rcx
0x18003310e  jz      short loc_18003311D
0x180033110  mov     rax, [rcx]
0x180033113  mov     rax, [rax+10h]
0x180033117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003311c  nop
0x18003311d  lea     r8, [rsp+488h+var_408]; struct MsixPackage::Provisioning::Library::MsixProvisioningRequest **
0x180033125  lea     rdx, [rsp+488h+Table]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18003312d  lea     rcx, [rsp+488h+var_3E8]; struct MsixPackage::Provisioning::Library::PackageSource *
0x180033135  call    ?CreateFromPackageSource@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@SAJPEAVPackageSource@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::CreateFromPackageSource(MsixPackage::Provisioning::Library::PackageSource *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixProvisioningRequest * *)
0x18003313a  mov     esi, eax
0x18003313c  test    eax, eax
0x18003313e  jns     short loc_1800331A5
0x180033140  mov     rcx, [rsp+488h]; this
0x180033148  lea     rax, aFailedToInitia_0; "Failed to initialize package set"
0x18003314f  mov     qword ptr [rsp+488h+var_468], rax; int
0x180033154  mov     r9d, esi; char *
0x180033157  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003315e  mov     edx, 39Dh; void *
0x180033163  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033168  nop
0x180033169  mov     rcx, [rsp+488h+var_408]
0x180033171  test    rcx, rcx
0x180033174  jz      short loc_180033183
0x180033176  mov     rax, [rcx]
0x180033179  mov     rax, [rax+10h]
0x18003317d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033182  nop
0x180033183  lea     rcx, [rsp+488h+var_3E8]; this
0x18003318b  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x180033190  nop
0x180033191  lea     rcx, [rsp+488h+Table]; Table
0x180033199  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x18003319e  mov     eax, esi
0x1800331a0  jmp     loc_1800335A1
0x1800331a5  mov     r8d, r14d
0x1800331a8  cmp     r13w, 0FFFFh
0x1800331ad  setz    r8b; int
0x1800331b1  mov     [rsp+488h+var_460], r14; char *
0x1800331b6  mov     [rsp+488h+var_468], r14b; int
0x1800331bb  mov     r9b, 1; bool
0x1800331be  xor     edx, edx; unsigned __int16 *
0x1800331c0  mov     rcx, [rsp+488h+var_408]; this
0x1800331c8  call    ?ProvisionPackagesOnline@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEAGH_N1PEBG@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::ProvisionPackagesOnline(ushort *,int,bool,bool,ushort const *)
0x1800331cd  mov     esi, eax
0x1800331cf  test    eax, eax
0x1800331d1  jns     short loc_180033238
0x1800331d3  mov     rcx, [rsp+488h]; this
0x1800331db  lea     rax, aFailedToProvis_1; "Failed to provision packages."
0x1800331e2  mov     qword ptr [rsp+488h+var_468], rax; int
0x1800331e7  mov     r9d, esi; char *
0x1800331ea  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800331f1  mov     edx, 3A4h; void *
0x1800331f6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800331fb  nop
0x1800331fc  mov     rcx, [rsp+488h+var_408]
0x180033204  test    rcx, rcx
0x180033207  jz      short loc_180033216
0x180033209  mov     rax, [rcx]
0x18003320c  mov     rax, [rax+10h]
0x180033210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033215  nop
0x180033216  lea     rcx, [rsp+488h+var_3E8]; this
0x18003321e  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x180033223  nop
0x180033224  lea     rcx, [rsp+488h+Table]; Table
0x18003322c  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x180033231  mov     eax, esi
0x180033233  jmp     loc_1800335A1
0x180033238  lea     rcx, [rsp+488h+Table]; this
0x180033240  call    ?FinalizeChanges@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(void)
0x180033245  mov     esi, eax
0x180033247  test    eax, eax
0x180033249  jns     short loc_1800332B0
0x18003324b  mov     rcx, [rsp+488h]; this
0x180033253  lea     rax, aEncounteredFai_0; "Encountered failure while finalizing pa"...
0x18003325a  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003325f  mov     r9d, esi; char *
0x180033262  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180033269  mov     edx, 3A6h; void *
0x18003326e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033273  nop
0x180033274  mov     rcx, [rsp+488h+var_408]
0x18003327c  test    rcx, rcx
0x18003327f  jz      short loc_18003328E
0x180033281  mov     rax, [rcx]
0x180033284  mov     rax, [rax+10h]
0x180033288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003328d  nop
0x18003328e  lea     rcx, [rsp+488h+var_3E8]; this
0x180033296  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x18003329b  nop
0x18003329c  lea     rcx, [rsp+488h+Table]; Table
0x1800332a4  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x1800332a9  mov     eax, esi
0x1800332ab  jmp     loc_1800335A1
0x1800332b0  test    rdi, rdi
0x1800332b3  jz      loc_1800334F4
0x1800332b9  cmp     [rdi], r14w
0x1800332bd  jz      loc_1800334F4
0x1800332c3  mov     [rsp+488h+bstrString], r14
0x1800332cb  mov     [rsp+488h+var_400], r14d
0x1800332d3  lea     r9, [rsp+488h+bstrString]
0x1800332db  lea     r8, [rsp+488h+var_400]
0x1800332e3  mov     rdx, [rsp+488h+var_408]
0x1800332eb  mov     rdx, [rdx+40h]
0x1800332ef  lea     rcx, [rsp+488h+Table]
0x1800332f7  call    ?GetAppxDataFileTarget@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetAppxDataFileTarget(ushort const *,int &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800332fc  mov     esi, eax
0x1800332fe  test    eax, eax
0x180033300  jns     loc_18003338F
0x180033306  mov     rcx, [rsp+488h]; this
0x18003330e  mov     rdx, [rsp+488h+var_408]
0x180033316  mov     r8, [rdx+40h]
0x18003331a  mov     [rsp+488h+var_460], r8; char *
0x18003331f  lea     rax, aFailedToGetApp_0; "Failed to get appropriate data file tar"...
0x180033326  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003332b  mov     r9d, esi; char *
0x18003332e  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180033335  mov     edx, 3B1h; void *
0x18003333a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003333f  mov     rcx, [rsp+488h+bstrString]; bstrString
0x180033347  test    rcx, rcx
0x18003334a  jz      short loc_180033353
0x18003334c  call    cs:__imp_SysFreeString
0x180033352  nop
0x180033353  mov     rcx, [rsp+488h+var_408]
0x18003335b  test    rcx, rcx
0x18003335e  jz      short loc_18003336D
0x180033360  mov     rax, [rcx]
0x180033363  mov     rax, [rax+10h]
0x180033367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003336c  nop
0x18003336d  lea     rcx, [rsp+488h+var_3E8]; this
0x180033375  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x18003337a  nop
0x18003337b  lea     rcx, [rsp+488h+Table]; Table
0x180033383  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x180033388  mov     eax, esi
0x18003338a  jmp     loc_1800335A1
0x18003338f  cmp     [rsp+488h+var_400], r14d
0x180033397  jz      loc_1800334E1
0x18003339d  cmp     qword ptr [rbx+18h], 8
0x1800333a2  jb      short loc_1800333A7
0x1800333a4  mov     rbx, [rbx]
0x1800333a7  mov     rcx, rbx; psz
0x1800333aa  call    cs:__imp_SysAllocString
0x1800333b0  mov     rbx, rax
0x1800333b3  test    rax, rax
0x1800333b6  jnz     short loc_180033429
0x1800333b8  mov     rcx, [rsp+488h]; this
0x1800333c0  mov     ebx, 8007000Eh
0x1800333c5  mov     r9d, ebx; char *
0x1800333c8  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800333cf  mov     edx, 3B6h; void *
0x1800333d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800333d9  mov     rcx, [rsp+488h+bstrString]; bstrString
0x1800333e1  test    rcx, rcx
0x1800333e4  jz      short loc_1800333ED
0x1800333e6  call    cs:__imp_SysFreeString
0x1800333ec  nop
0x1800333ed  mov     rcx, [rsp+488h+var_408]
0x1800333f5  test    rcx, rcx
0x1800333f8  jz      short loc_180033407
0x1800333fa  mov     rdx, [rcx]
0x1800333fd  mov     rax, [rdx+10h]
0x180033401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033406  nop
0x180033407  lea     rcx, [rsp+488h+var_3E8]; this
0x18003340f  call    ??1PackageSource@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::PackageSource::~PackageSource(void)
0x180033414  nop
0x180033415  lea     rcx, [rsp+488h+Table]; Table
0x18003341d  call    ??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)
0x180033422  mov     eax, ebx
0x180033424  jmp     loc_1800335A1
0x180033429  mov     r8, rbx; unsigned __int16 *
0x18003342c  mov     rdx, [rsp+488h+bstrString]; unsigned __int16 *
0x180033434  mov     rcx, rdi; unsigned __int16 *
0x180033437  call    ?SetProvisionedAppxDataFile@MsixProvisioningManager@Library@Provisioning@MsixPackage@@SAJPEAG00@Z; MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile(ushort *,ushort *,ushort *)
0x18003343c  mov     edi, eax
0x18003343e  test    eax, eax
0x180033440  jns     loc_1800334D8
0x180033446  mov     rcx, [rsp+488h]; this
0x18003344e  mov     rdx, [rsp+488h+var_408]
0x180033456  mov     r8, [rdx+40h]
0x18003345a  mov     [rsp+488h+var_460], r8; char *
0x18003345f  lea     rax, aFailedToAddCus; "Failed to add custom data to provisione"...
0x180033466  mov     qword ptr [rsp+488h+var_468], rax; int
0x18003346b  mov     r9d, edi; char *
0x18003346e  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180033475  mov     edx, 3BDh; void *
0x18003347a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003347f  mov     rcx, rbx; bstrString
0x180033482  call    cs:__imp_SysFreeString
  ... truncated ...
```
