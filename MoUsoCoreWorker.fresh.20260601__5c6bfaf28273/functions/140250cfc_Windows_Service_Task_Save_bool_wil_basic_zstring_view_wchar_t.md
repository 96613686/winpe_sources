# Windows::Service::Task::Save(bool,wil::basic_zstring_view<wchar_t>)

- ea: `0x140250cfc`
- end: `0x1402512ce`
- name: `?Save@Task@Service@Windows@@QEAAX_NV?$basic_zstring_view@_W@wil@@@Z`
- size: `1490`
- prototype: `int __fastcall(__int64 **this, char, _OWORD *)`
- caller_count: `6`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1402531c0`
- `0x1402533d0`
- `0x140253510`
- `0x140253680`
- `0x1402539f0`
- `0x140254b20`

## callees

- `0x14003fee4`
- `0x14003ff28`
- `0x1400413a8`
- `0x1400a5368`
- `0x1402500f8`
- `0x1402502a4`
- `0x140250cfc`
- `0x1402512d4`
- `0x1402541b4`
- `0x140254ca4`
- `0x140254e24`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140250d8a`
- `OLEAUT32!__imp_SysAllocString` at `0x140250e60`
- `OLEAUT32!__imp_SysAllocString` at `0x140250f0f`
- `OLEAUT32!__imp_SysAllocString` at `0x140250d8a`
- `OLEAUT32!__imp_SysAllocString` at `0x140250e60`
- `OLEAUT32!__imp_SysAllocString` at `0x140250f0f`
- `OLEAUT32!__imp_SysFreeString` at `0x140250fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x140251119`
- `OLEAUT32!__imp_SysFreeString` at `0x1402511cf`
- `OLEAUT32!__imp_SysFreeString` at `0x140250fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x140251119`
- `OLEAUT32!__imp_SysFreeString` at `0x1402511cf`
- `OLEAUT32!__imp_VariantInit` at `0x140250d7c`
- `OLEAUT32!__imp_VariantInit` at `0x140250e52`
- `OLEAUT32!__imp_VariantInit` at `0x140250ed7`
- `OLEAUT32!__imp_VariantInit` at `0x140250d7c`
- `OLEAUT32!__imp_VariantInit` at `0x140250e52`
- `OLEAUT32!__imp_VariantInit` at `0x140250ed7`
- `OLEAUT32!__imp_VariantClear` at `0x140250fe7`
- `OLEAUT32!__imp_VariantClear` at `0x1402511a1`
- `OLEAUT32!__imp_VariantClear` at `0x1402511f8`
- `OLEAUT32!__imp_VariantClear` at `0x140250fe7`
- `OLEAUT32!__imp_VariantClear` at `0x1402511a1`
- `OLEAUT32!__imp_VariantClear` at `0x1402511f8`

## string_xrefs

- `0x140251243`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x14025126a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x14025127c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140251258`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140251291`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402512a6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402512bb`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140250df1`: `Microsoft\Windows\UpdateOrchestrator`
- `0x14025100b`: `Refreshing cached task definition after Registering newly created task`
- `0x1402510e4`: `Task definition refreshed: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
int __fastcall Windows::Service::Task::Save(__int64 **this, char a2, _OWORD *a3)
{
  wil::details::in1diag3 **v3; // rax
  _OWORD *v4; // r12
  char v5; // r14
  __int64 **v6; // rsi
  BSTR v7; // rax
  const char *v8; // r9
  struct ITaskServiceVtbl *lpVtbl; // rax
  int v10; // eax
  BSTR v11; // rax
  const char *v12; // r9
  __int64 v13; // rbx
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v16; // xmm8
  IRecordInfo *v17; // xmm9_8
  __int128 v18; // xmm10
  IRecordInfo *v19; // xmm11_8
  __int64 *v20; // r13
  const OLECHAR *v21; // rcx
  BSTR v22; // rax
  const char *v23; // r9
  OLECHAR *v24; // r15
  int v25; // eax
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  __int64 *v29; // rbx
  __int64 *v30; // rcx
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const char *v34; // r9
  int v36; // [rsp+20h] [rbp-1E8h]
  _QWORD v37[2]; // [rsp+50h] [rbp-1B8h] BYREF
  VARIANTARG v38; // [rsp+60h] [rbp-1A8h] BYREF
  Windows::Service::Task *v39; // [rsp+80h] [rbp-188h]
  _OWORD *v40; // [rsp+90h] [rbp-178h]
  __int128 v41; // [rsp+A0h] [rbp-168h]
  IRecordInfo *v42; // [rsp+B0h] [rbp-158h]
  __int128 v43; // [rsp+C0h] [rbp-148h]
  IRecordInfo *v44; // [rsp+D0h] [rbp-138h]
  int v45[4]; // [rsp+E0h] [rbp-128h] BYREF
  IRecordInfo *v46; // [rsp+F0h] [rbp-118h]
  VARIANTARG v47; // [rsp+100h] [rbp-108h] BYREF
  VARIANTARG pvarg; // [rsp+118h] [rbp-F0h] BYREF
  BSTR bstrString; // [rsp+130h] [rbp-D8h] BYREF
  __int64 *v50; // [rsp+138h] [rbp-D0h] BYREF
  __int64 *v51; // [rsp+140h] [rbp-C8h]
  __int64 v52; // [rsp+148h] [rbp-C0h] BYREF
  struct ITaskService *v53; // [rsp+150h] [rbp-B8h] BYREF
  BSTR v54; // [rsp+158h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h] BYREF

  v3 = &retaddr;
  v4 = a3;
  v5 = a2;
  v6 = this;
  v39 = (Windows::Service::Task *)this;
  v40 = a3;
  LODWORD(bstrString) = 0;
  if ( *((_BYTE *)this + 40) )
  {
    VariantInit(&pvarg);
    v7 = SysAllocString(L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)");
    v37[0] = v7;
    LODWORD(bstrString) = 1;
    if ( !v7 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    pvarg.llVal = (LONGLONG)v7;
    pvarg.vt = 8;
    v53 = 0;
    Windows::Service::Task::TaskService((int)&v53);
    Windows::Service::Task::EnsureTaskFolderExists(v53);
    v54 = 0;
    wil::make_bstr(&v54, L"Microsoft\\Windows\\UpdateOrchestrator");
    v52 = 0;
    lpVtbl = v53->lpVtbl;
    v52 = 0;
    v10 = ((__int64 (__fastcall *)(struct ITaskService *, BSTR, __int64 *))lpVtbl->GetFolder)(v53, v54, &v52);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v10,
        v36);
    VariantInit(&v47);
    v11 = SysAllocString(L"S-1-5-18");
    v37[0] = v11;
    LODWORD(bstrString) = 4;
    if ( !v11 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v12);
    v47.llVal = (LONGLONG)v11;
    v47.vt = 8;
    v51 = 0;
    v13 = v52;
    v50 = *(__int64 **)(*(_QWORD *)v52 + 136LL);
    v51 = 0;
    v14 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v38);
    v16 = *(_OWORD *)&v38.vt;
    v17 = v38.pRecInfo;
    v18 = *(_OWORD *)&v47.vt;
    v19 = v47.pRecInfo;
    v20 = *v6;
    v21 = (const OLECHAR *)(v6 + 1);
    if ( (unsigned __int64)v6[4] > 7 )
      v21 = *(const OLECHAR **)v21;
    v22 = SysAllocString(v21);
    v24 = v22;
    v37[0] = v22;
    LODWORD(bstrString) = 8;
    if ( !v22 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    v41 = v14;
    v42 = pRecInfo;
    v43 = v16;
    v44 = v17;
    *(_OWORD *)v45 = v18;
    v46 = v19;
    v25 = ((__int64 (__fastcall *)(__int64, BSTR, __int64 *, __int64))v50)(v13, v22, v20, 6);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v25,
        (int)v45);
    SysFreeString(v24);
    VariantClear(&v38);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::GetImpl'::`2'::impl)
      && *((_BYTE *)v6 + 41) )
    {
      try
      {
        v37[0] = L"Refreshing cached task definition after Registering newly created task";
        v37[1] = 70;
        SystemInterface::Log<>(v37);
        v50 = 0;
        v27 = *v51;
        v50 = 0;
        v28 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v27 + 152))(v51, &v50);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v28,
            (int)v45);
        v29 = *v6;
        v30 = v50;
        *v6 = v50;
        if ( v30 )
          (*(void (__fastcall **)(__int64 *))(*v30 + 8))(v30);
        if ( v29 )
          (*(void (__fastcall **)(__int64 *))(*v29 + 16))(v29);
        bstrString = 0;
        v31 = *v6;
        v32 = **v6;
        bstrString = 0;
        v33 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v32 + 152))(v31, &bstrString);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF7,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v33,
            (int)v45);
        v37[0] = bstrString;
        *(_QWORD *)&v38.vt = L"Task definition refreshed: {}";
        v38.llVal = 29;
        SystemInterface::Log<wchar_t *>(&v38, v37);
        *((_BYTE *)v6 + 41) = 0;
        if ( bstrString )
          SysFreeString(bstrString);
        v26 = v50;
        if ( v50 )
          (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xFB,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
          v34);
        v5 = a2;
        v6 = (__int64 **)v39;
        v4 = v40;
      }
    }
    if ( v5 )
      Windows::Service::Task::Protect(v6);
    *(_OWORD *)&v38.vt = *v4;
    Windows::Service::Task::LogTaskModified(v26, v51, &v38);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    VariantClear(&v47);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v54 )
      SysFreeString(v54);
    if ( v53 )
      ((void (__fastcall *)(struct ITaskService *))v53->lpVtbl->Release)(v53);
    LODWORD(v3) = VariantClear(&pvarg);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x140250cfc  mov     rax, rsp
0x140250cff  mov     [rax+10h], dl
0x140250d02  push    rbx
0x140250d03  push    rsi
0x140250d04  push    rdi
0x140250d05  push    r12
0x140250d07  push    r13
0x140250d09  push    r14
0x140250d0b  push    r15
0x140250d0d  sub     rsp, 1D0h
0x140250d14  movaps  xmmword ptr [rax-48h], xmm6
0x140250d18  movaps  xmmword ptr [rax-58h], xmm7
0x140250d1c  movaps  xmmword ptr [rax-68h], xmm8
0x140250d21  movaps  xmmword ptr [rax-78h], xmm9
0x140250d26  movaps  xmmword ptr [rax-88h], xmm10
0x140250d2e  movaps  xmmword ptr [rax-98h], xmm11
0x140250d36  mov     rax, cs:__security_cookie
0x140250d3d  xor     rax, rsp
0x140250d40  mov     [rsp+208h+var_A8], rax
0x140250d48  mov     r12, r8
0x140250d4b  mov     r14b, dl
0x140250d4e  mov     rsi, rcx
0x140250d51  mov     [rsp+208h+var_188], rcx
0x140250d59  mov     [rsp+208h+var_178], r8
0x140250d61  xor     edi, edi
0x140250d63  mov     dword ptr [rsp+208h+bstrString], edi
0x140250d6a  cmp     [rcx+28h], dil
0x140250d6e  jz      loc_1402511FE
0x140250d74  lea     rcx, [rsp+208h+pvarg]; pvarg
0x140250d7c  call    cs:__imp_VariantInit
0x140250d82  nop
0x140250d83  lea     rcx, aDPAFaSyAFrfxLs; "D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;"...
0x140250d8a  call    cs:__imp_SysAllocString
0x140250d90  mov     [rsp+208h+var_1B8], rax
0x140250d95  mov     dword ptr [rsp+208h+bstrString], 1
0x140250da0  mov     rcx, [rsp+208h]; this
0x140250da8  test    rax, rax
0x140250dab  jz      loc_140251243
0x140250db1  mov     qword ptr [rsp+208h+pvarg+8], rax
0x140250db9  mov     ebx, 8
0x140250dbe  mov     word ptr [rsp+208h+pvarg], bx
0x140250dc6  mov     [rsp+208h+var_B8], rdi
0x140250dce  lea     rcx, [rsp+208h+var_B8]; int
0x140250dd6  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x140250ddb  nop
0x140250ddc  mov     rcx, [rsp+208h+var_B8]; struct ITaskService *
0x140250de4  call    ?EnsureTaskFolderExists@Task@Service@Windows@@CAXPEAUITaskService@@@Z; Windows::Service::Task::EnsureTaskFolderExists(ITaskService *)
0x140250de9  mov     [rsp+208h+var_B0], rdi
0x140250df1  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x140250df8  lea     rcx, [rsp+208h+var_B0]
0x140250e00  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x140250e05  nop
0x140250e06  mov     [rsp+208h+var_C0], rdi
0x140250e0e  mov     rcx, [rsp+208h+var_B8]
0x140250e16  mov     rax, [rcx]
0x140250e19  mov     [rsp+208h+var_C0], rdi
0x140250e21  lea     r8, [rsp+208h+var_C0]
0x140250e29  mov     rdx, [rsp+208h+var_B0]
0x140250e31  mov     rax, [rax+38h]
0x140250e35  call    _guard_dispatch_icall
0x140250e3a  mov     rcx, [rsp+208h]; this
0x140250e42  test    eax, eax
0x140250e44  js      loc_140251255
0x140250e4a  lea     rcx, [rsp+208h+var_108]; pvarg
0x140250e52  call    cs:__imp_VariantInit
0x140250e58  nop
0x140250e59  lea     rcx, aS1518; "S-1-5-18"
0x140250e60  call    cs:__imp_SysAllocString
0x140250e66  mov     [rsp+208h+var_1B8], rax
0x140250e6b  mov     dword ptr [rsp+208h+bstrString], 4
0x140250e76  mov     rcx, [rsp+208h]; this
0x140250e7e  test    rax, rax
0x140250e81  jz      loc_14025126A
0x140250e87  mov     qword ptr [rsp+208h+var_108+8], rax
0x140250e8f  mov     word ptr [rsp+208h+var_108], bx
0x140250e97  mov     [rsp+208h+var_C8], rdi
0x140250e9f  mov     rbx, [rsp+208h+var_C0]
0x140250ea7  mov     rax, [rbx]
0x140250eaa  mov     rax, [rax+88h]
0x140250eb1  mov     [rsp+208h+var_D0], rax
0x140250eb9  mov     [rsp+208h+var_C8], rdi
0x140250ec1  movups  xmm6, xmmword ptr [rsp+208h+pvarg]
0x140250ec9  movsd   xmm7, qword ptr [rsp+208h+pvarg+10h]
0x140250ed2  lea     rcx, [rsp+208h+var_1A8]; pvarg
0x140250ed7  call    cs:__imp_VariantInit
0x140250edd  nop
0x140250ede  movups  xmm8, xmmword ptr [rsp+208h+var_1A8]
0x140250ee4  movsd   xmm9, qword ptr [rsp+208h+var_1A8+10h]
0x140250eeb  movups  xmm10, xmmword ptr [rsp+208h+var_108]
0x140250ef4  movsd   xmm11, qword ptr [rsp+208h+var_108+10h]
0x140250efe  mov     r13, [rsi]
0x140250f01  lea     rcx, [rsi+8]
0x140250f05  cmp     qword ptr [rcx+18h], 7
0x140250f0a  jbe     short loc_140250F0F
0x140250f0c  mov     rcx, [rcx]; psz
0x140250f0f  call    cs:__imp_SysAllocString
0x140250f15  mov     r15, rax
0x140250f18  mov     [rsp+208h+var_1B8], rax
0x140250f1d  mov     dword ptr [rsp+208h+bstrString], 8
0x140250f28  mov     rcx, [rsp+208h]; this
0x140250f30  test    rax, rax
0x140250f33  jz      loc_14025127C
0x140250f39  movaps  [rsp+208h+var_168], xmm6
0x140250f41  movsd   [rsp+208h+var_158], xmm7
0x140250f4a  movaps  [rsp+208h+var_148], xmm8
0x140250f53  movsd   [rsp+208h+var_138], xmm9
0x140250f5d  movaps  xmmword ptr [rsp+208h+var_128], xmm10
0x140250f66  movsd   [rsp+208h+var_118], xmm11
0x140250f70  lea     rax, [rsp+208h+var_C8]
0x140250f78  mov     [rsp+208h+var_1C8], rax
0x140250f7d  lea     rax, [rsp+208h+var_168]
0x140250f85  mov     [rsp+208h+var_1D0], rax
0x140250f8a  mov     [rsp+208h+var_1D8], 5
0x140250f92  lea     rax, [rsp+208h+var_148]
0x140250f9a  mov     [rsp+208h+var_1E0], rax
0x140250f9f  lea     rax, [rsp+208h+var_128]
0x140250fa7  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x140250fac  mov     r9d, 6
0x140250fb2  mov     r8, r13
0x140250fb5  mov     rdx, r15
0x140250fb8  mov     rcx, rbx
0x140250fbb  mov     rax, [rsp+208h+var_D0]
0x140250fc3  call    _guard_dispatch_icall
0x140250fc8  mov     rcx, [rsp+208h]; this
0x140250fd0  test    eax, eax
0x140250fd2  js      loc_14025128E
0x140250fd8  mov     rcx, r15; bstrString
0x140250fdb  call    cs:__imp_SysFreeString
0x140250fe1  nop
0x140250fe2  lea     rcx, [rsp+208h+var_1A8]; pvarg
0x140250fe7  call    cs:__imp_VariantClear
0x140250fed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect> `wil::Feature<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::GetImpl(void)'::`2'::impl
0x140250ff4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_SchedulerRefreshTaskBeforeProtect>::__private_IsEnabled(void)
0x140250ff9  test    al, al
0x140250ffb  jz      loc_140251154
0x140251001  cmp     [rsi+29h], dil
0x140251005  jz      loc_140251154
0x14025100b  lea     rax, aRefreshingCach; "Refreshing cached task definition after"...
0x140251012  mov     [rsp+208h+var_1B8], rax
0x140251017  mov     [rsp+208h+var_1B0], 46h ; 'F'
0x140251020  lea     rcx, [rsp+208h+var_1B8]
0x140251025  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x14025102a  mov     [rsp+208h+var_D0], rdi
0x140251032  mov     rcx, [rsp+208h+var_C8]
0x14025103a  mov     rax, [rcx]
0x14025103d  mov     [rsp+208h+var_D0], rdi
0x140251045  lea     rdx, [rsp+208h+var_D0]
0x14025104d  mov     rax, [rax+98h]
0x140251054  call    _guard_dispatch_icall
0x140251059  mov     rcx, [rsp+208h]; this
0x140251061  test    eax, eax
0x140251063  js      loc_1402512A3
0x140251069  mov     rbx, [rsi]
0x14025106c  mov     rcx, [rsp+208h+var_D0]
0x140251074  mov     [rsi], rcx
0x140251077  test    rcx, rcx
0x14025107a  jz      short loc_140251088
0x14025107c  mov     rax, [rcx]
0x14025107f  mov     rax, [rax+8]
0x140251083  call    _guard_dispatch_icall
0x140251088  test    rbx, rbx
0x14025108b  jz      short loc_14025109D
0x14025108d  mov     rax, [rbx]
0x140251090  mov     rcx, rbx
0x140251093  mov     rax, [rax+10h]
0x140251097  call    _guard_dispatch_icall
0x14025109c  nop
0x14025109d  mov     [rsp+208h+bstrString], rdi
0x1402510a5  mov     rcx, [rsi]
0x1402510a8  mov     rax, [rcx]
0x1402510ab  mov     [rsp+208h+bstrString], rdi
0x1402510b3  lea     rdx, [rsp+208h+bstrString]
0x1402510bb  mov     rax, [rax+98h]
0x1402510c2  call    _guard_dispatch_icall
0x1402510c7  mov     rcx, [rsp+208h]; this
0x1402510cf  test    eax, eax
0x1402510d1  js      loc_1402512B8
0x1402510d7  mov     rax, [rsp+208h+bstrString]
0x1402510df  mov     [rsp+208h+var_1B8], rax
0x1402510e4  lea     rax, aTaskDefinition; "Task definition refreshed: {}"
0x1402510eb  mov     qword ptr [rsp+208h+var_1A8], rax
0x1402510f0  mov     qword ptr [rsp+208h+var_1A8+8], 1Dh
0x1402510f9  lea     rdx, [rsp+208h+var_1B8]
0x1402510fe  lea     rcx, [rsp+208h+var_1A8]
0x140251103  call    ??$Log@PEA_W@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAPEA_W@Z; SystemInterface::Log<wchar_t *>(std::wstring_view,wchar_t * &&)
0x140251108  mov     [rsi+29h], dil
0x14025110c  mov     rcx, [rsp+208h+bstrString]; bstrString
0x140251114  test    rcx, rcx
0x140251117  jz      short loc_140251120
0x140251119  call    cs:__imp_SysFreeString
0x14025111f  nop
0x140251120  mov     rcx, [rsp+208h+var_D0]
0x140251128  test    rcx, rcx
0x14025112b  jz      short loc_14025113A
0x14025112d  mov     rax, [rcx]
0x140251130  mov     rax, [rax+10h]
0x140251134  call    _guard_dispatch_icall
0x140251139  nop
0x14025113a  jmp     short loc_140251154
0x14025113c  mov     r14b, [rsp+208h+arg_8]
0x140251144  mov     rsi, [rsp+208h+var_188]
0x14025114c  mov     r12, [rsp+208h+var_178]
0x140251154  test    r14b, r14b
0x140251157  jz      short loc_140251161
0x140251159  mov     rcx, rsi; this
0x14025115c  call    ?Protect@Task@Service@Windows@@AEAAXXZ; Windows::Service::Task::Protect(void)
0x140251161  movaps  xmm0, xmmword ptr [r12]
0x140251166  movdqa  xmmword ptr [rsp+208h+var_1A8], xmm0
0x14025116c  lea     r8, [rsp+208h+var_1A8]
0x140251171  mov     rdx, [rsp+208h+var_C8]
0x140251179  call    ?LogTaskModified@Task@Service@Windows@@AEAAXPEAUIRegisteredTask@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Service::Task::LogTaskModified(IRegisteredTask *,wil::basic_zstring_view<wchar_t>)
0x14025117e  nop
0x14025117f  mov     rcx, [rsp+208h+var_C8]
0x140251187  test    rcx, rcx
0x14025118a  jz      short loc_140251199
0x14025118c  mov     rax, [rcx]
0x14025118f  mov     rax, [rax+10h]
0x140251193  call    _guard_dispatch_icall
0x140251198  nop
0x140251199  lea     rcx, [rsp+208h+var_108]; pvarg
0x1402511a1  call    cs:__imp_VariantClear
0x1402511a7  nop
0x1402511a8  mov     rcx, [rsp+208h+var_C0]
0x1402511b0  test    rcx, rcx
0x1402511b3  jz      short loc_1402511C2
0x1402511b5  mov     rax, [rcx]
0x1402511b8  mov     rax, [rax+10h]
0x1402511bc  call    _guard_dispatch_icall
0x1402511c1  nop
0x1402511c2  mov     rcx, [rsp+208h+var_B0]; bstrString
0x1402511ca  test    rcx, rcx
0x1402511cd  jz      short loc_1402511D6
0x1402511cf  call    cs:__imp_SysFreeString
0x1402511d5  nop
0x1402511d6  mov     rcx, [rsp+208h+var_B8]
0x1402511de  test    rcx, rcx
0x1402511e1  jz      short loc_1402511F0
0x1402511e3  mov     rax, [rcx]
0x1402511e6  mov     rax, [rax+10h]
0x1402511ea  call    _guard_dispatch_icall
0x1402511ef  nop
0x1402511f0  lea     rcx, [rsp+208h+pvarg]; pvarg
0x1402511f8  call    cs:__imp_VariantClear
0x1402511fe  mov     rcx, [rsp+208h+var_A8]
0x140251206  xor     rcx, rsp; StackCookie
0x140251209  call    __security_check_cookie
0x14025120e  lea     r11, [rsp+208h+var_38]
0x140251216  movaps  xmm6, xmmword ptr [r11-10h]
0x14025121b  movaps  xmm7, xmmword ptr [r11-20h]
0x140251220  movaps  xmm8, xmmword ptr [r11-30h]
0x140251225  movaps  xmm9, xmmword ptr [r11-40h]
0x14025122a  movaps  xmm10, xmmword ptr [r11-50h]
0x14025122f  movaps  xmm11, xmmword ptr [r11-60h]
0x140251234  mov     rsp, r11
0x140251237  pop     r15
0x140251239  pop     r14
0x14025123b  pop     r13
0x14025123d  pop     r12
0x14025123f  pop     rdi
0x140251240  pop     rsi
0x140251241  pop     rbx
0x140251242  retn
0x140251243  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14025124a  mov     edx, 138Dh; void *
0x14025124f  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140251255  mov     r9d, eax; char *
0x140251258  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14025125f  mov     edx, 0D9h; void *
0x140251264  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14025126a  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140251271  mov     edx, 138Dh; void *
0x140251276  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14025127c  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140251283  mov     edx, 138Dh; void *
0x140251288  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14025128e  mov     r9d, eax; char *
0x140251291  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140251298  mov     edx, 0E8h; void *
0x14025129d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402512a3  mov     r9d, eax; char *
0x1402512a6  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402512ad  mov     edx, 0F4h; void *
0x1402512b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402512b8  mov     r9d, eax; char *
0x1402512bb  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402512c2  mov     edx, 0F7h; void *
0x1402512c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
