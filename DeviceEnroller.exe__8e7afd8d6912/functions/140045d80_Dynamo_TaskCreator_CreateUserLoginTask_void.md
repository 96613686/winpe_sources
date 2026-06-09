# Dynamo::TaskCreator::CreateUserLoginTask(void)

- ea: `0x140045d80`
- end: `0x1400462e7`
- name: `?CreateUserLoginTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `1383`
- prototype: `void __fastcall(Dynamo::TaskCreator *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1400042f0`
- `0x140005ea8`
- `0x14000a6e4`
- `0x14001ed14`
- `0x14003d008`
- `0x1400449e4`
- `0x140045754`
- `0x140045d80`
- `0x140046bd8`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140045f87`
- `OLEAUT32!__imp_SysAllocString` at `0x14004606a`
- `OLEAUT32!__imp_SysAllocString` at `0x140045f87`
- `OLEAUT32!__imp_SysAllocString` at `0x14004606a`
- `OLEAUT32!__imp_SysFreeString` at `0x140045fce`
- `OLEAUT32!__imp_SysFreeString` at `0x1400460b4`
- `OLEAUT32!__imp_SysFreeString` at `0x140045fce`
- `OLEAUT32!__imp_SysFreeString` at `0x1400460b4`
- `OLEAUT32!__imp_VariantInit` at `0x140045e5a`
- `OLEAUT32!__imp_VariantInit` at `0x140045e70`
- `OLEAUT32!__imp_VariantInit` at `0x140045e86`
- `OLEAUT32!__imp_VariantInit` at `0x140045e9b`
- `OLEAUT32!__imp_VariantInit` at `0x140045e5a`
- `OLEAUT32!__imp_VariantInit` at `0x140045e70`
- `OLEAUT32!__imp_VariantInit` at `0x140045e86`
- `OLEAUT32!__imp_VariantInit` at `0x140045e9b`
- `OLEAUT32!__imp_VariantClear` at `0x140045f08`
- `OLEAUT32!__imp_VariantClear` at `0x140045f1a`
- `OLEAUT32!__imp_VariantClear` at `0x140045f2c`
- `OLEAUT32!__imp_VariantClear` at `0x140045f3e`
- `OLEAUT32!__imp_VariantClear` at `0x140045f08`
- `OLEAUT32!__imp_VariantClear` at `0x140045f1a`
- `OLEAUT32!__imp_VariantClear` at `0x140045f2c`
- `OLEAUT32!__imp_VariantClear` at `0x140045f3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045e35`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045e35`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004619e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004619e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140045dec`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140045dec`

## string_xrefs

- `0x14004626f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400462d5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140045f80`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x1400460f4`: `LoginTask`
- `0x1400461e9`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400461fe`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046213`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046228`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x14004625d`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046284`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140046299`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400462ae`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400462c3`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
void __fastcall Dynamo::TaskCreator::CreateUserLoginTask(Dynamo::TaskCreator *this)
{
  HRESULT v2; // eax
  BOOL v3; // ebx
  __int64 *v4; // rax
  HRESULT Instance; // eax
  struct ITaskService *v6; // rsi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rdi
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  IRecordInfo *v11; // xmm9_8
  __int128 v12; // xmm6
  IRecordInfo *v13; // xmm7_8
  int v14; // eax
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  int v19; // eax
  struct ITaskDefinition *v20; // rsi
  struct ITaskDefinitionVtbl *lpVtbl; // r15
  BSTR v22; // rax
  const char *v23; // r9
  OLECHAR *v24; // rdi
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  _QWORD *v29; // rsi
  __int64 v30; // r15
  BSTR v31; // rax
  const char *v32; // r9
  OLECHAR *v33; // rdi
  int v34; // eax
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  __int64 (__fastcall ***v37)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v38; // rcx
  struct ITaskDefinition *v39; // rcx
  struct ITaskService *v40; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v43; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v44; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+48h] [rbp-C0h]
  _QWORD *v46; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, _QWORD **); // [rsp+58h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+68h] [rbp-A0h]
  VARIANTARG v50; // [rsp+70h] [rbp-98h] BYREF
  __int64 v51; // [rsp+88h] [rbp-80h]
  VARIANTARG v52; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v53; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-48h] BYREF
  int v55[4]; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v56; // [rsp+E8h] [rbp-20h]
  __int128 v57; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v58; // [rsp+108h] [rbp+0h]
  __int128 v59; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v60; // [rsp+128h] [rbp+20h]
  __int128 Src; // [rsp+138h] [rbp+30h] BYREF
  __int64 v62; // [rsp+148h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+210h] [rbp+108h]

  LODWORD(v45) = 0;
  if ( *((_QWORD *)this + 2) )
  {
    v2 = CoInitializeEx(0, 0);
    v3 = v2 >= 0;
    LODWORD(v49) = v3;
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xC9,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v2,
        ppv);
    v44 = 0;
    v4 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>((__int64 *)&v44);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v4);
    if ( Instance < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCC,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
    v6 = v44;
    Connect = v44->lpVtbl->Connect;
    VariantInit(&pvarg);
    v8 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v53);
    v10 = *(_OWORD *)&v53.vt;
    v11 = v53.pRecInfo;
    VariantInit(&v52);
    v12 = *(_OWORD *)&v52.vt;
    v13 = v52.pRecInfo;
    VariantInit((VARIANTARG *)&v50.decVal.8);
    *(_OWORD *)v55 = v8;
    v56 = pRecInfo;
    v57 = v10;
    v58 = v11;
    v59 = v12;
    v60 = v13;
    Src = *(_OWORD *)&v50.decVal.Lo32;
    v62 = v51;
    v14 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
            v6,
            &Src,
            &v59,
            &v57);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCD,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v14,
        (int)v55);
    v15 = VariantClear((VARIANTARG *)&v50.decVal.8);
    if ( v15 < 0 )
      _com_issue_error(v15);
    v16 = VariantClear(&v52);
    if ( v16 < 0 )
      _com_issue_error(v16);
    v17 = VariantClear(&v53);
    if ( v17 < 0 )
      _com_issue_error(v17);
    v18 = VariantClear(&pvarg);
    if ( v18 < 0 )
      _com_issue_error(v18);
    v43 = 0;
    v19 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))v44->lpVtbl->NewTask)(
            v44,
            0,
            &v43);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD0,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v19,
        (int)v55);
    v20 = v43;
    lpVtbl = v43->lpVtbl;
    v22 = SysAllocString(
            L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsoft"
             "-com:asm.v3\">\n"
             "    <RegistrationInfo>\n"
             "        <Author>$(@%systemRoot%\\system32\\deviceenroller.exe,-101)</Author>\n"
             "        <Description>$(@%systemRoot%\\system32\\deviceenroller.exe,-104)</Description>\n"
             "        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n"
             "    </RegistrationInfo>\n"
             "    <Principals>\n"
             "        <Principal id=\"LocalSystem\">\n"
             "            <UserId>S-1-5-18</UserId>\n"
             "            <RunLevel>HighestAvailable</RunLevel>\n"
             "        </Principal>\n"
             "    </Principals>\n"
             "    <Settings>\n"
             "        <MultipleInstancesPolicy>Queue</MultipleInstancesPolicy>\n"
             "        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
             "        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
             "        <AllowHardTerminate>false</AllowHardTerminate>\n"
             "        <StartWhenAvailable>true</StartWhenAvailable>\n"
             "        <AllowStartOnDemand>true</AllowStartOnDemand>\n"
             "        <Hidden>true</Hidden>\n"
             "        <RunOnlyIfIdle>false</RunOnlyIfIdle>\n"
             "        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
             "        <ExecutionTimeLimit>PT1H</ExecutionTimeLimit>\n"
             "    </Settings>\n"
             "    <Actions Context=\"LocalSystem\">\n"
             "        <Exec>\n"
             "            <Command>%windir%\\system32\\deviceenroller.exe</Command>\n"
             "        </Exec>\n"
             "    </Actions>\n"
             "</Task>");
    v24 = v22;
    *(_QWORD *)&v50.vt = v22;
    LODWORD(v45) = 1;
    if ( !v22 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    v25 = ((__int64 (__fastcall *)(struct ITaskDefinition *, BSTR))lpVtbl->put_XmlText)(v20, v22);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD1,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v25,
        (int)v55);
    SysFreeString(v24);
    v48 = 0;
    v26 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v43->lpVtbl->get_Triggers)(v43, &v48);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD4,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v26,
        (int)v55);
    v47 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v48 + 80LL))(v48, 9, &v47);
    if ( v27 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD7,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v27,
        (int)v55);
    v46 = 0;
    v28 = (**v47)(v47, &GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c, &v46);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xDA,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v28,
        (int)v55);
    v29 = v46;
    v30 = *v46;
    v31 = SysAllocString(*((const OLECHAR **)this + 2));
    v33 = v31;
    *(_QWORD *)&v50.vt = v31;
    LODWORD(v45) = 2;
    if ( !v31 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15F3,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v32);
    v34 = (*(__int64 (__fastcall **)(_QWORD *, BSTR))(v30 + 184))(v29, v31);
    if ( v34 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xDC,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v34,
        (int)v55);
    SysFreeString(v33);
    v35 = (_QWORD *)anonymous_namespace_::CreateCommandLine(&Src, *((void **)this + 1), *((void **)this + 2), L"Login");
    if ( v35[3] > 7u )
      v35 = (_QWORD *)*v35;
    anonymous_namespace_::AddCommandLine(v43, v35);
    std::wstring::~wstring((char **)&Src);
    Dynamo::TaskCreator::RegisterTask(this, v44, v43, L"LoginTask");
    v36 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    }
    v37 = v47;
    if ( v47 )
    {
      v47 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v37)[2])(v37);
    }
    v38 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v43;
    if ( v43 )
    {
      v43 = 0;
      ((void (__fastcall *)(struct ITaskDefinition *))v39->lpVtbl->Release)(v39);
    }
    v40 = v44;
    if ( v44 )
    {
      v44 = 0;
      ((void (__fastcall *)(struct ITaskService *))v40->lpVtbl->Release)(v40);
    }
    if ( v3 )
      CoUninitialize();
  }
}

```

## disassembly

```asm
0x140045d80  mov     rax, rsp
0x140045d83  push    rbp
0x140045d84  push    rbx
0x140045d85  push    rsi
0x140045d86  push    rdi
0x140045d87  push    r12
0x140045d89  push    r13
0x140045d8b  push    r14
0x140045d8d  push    r15
0x140045d8f  lea     rbp, [rax-108h]
0x140045d96  sub     rsp, 1C8h
0x140045d9d  movaps  xmmword ptr [rax-58h], xmm6
0x140045da1  movaps  xmmword ptr [rax-68h], xmm7
0x140045da5  movaps  xmmword ptr [rax-78h], xmm8
0x140045daa  movaps  xmmword ptr [rax-88h], xmm9
0x140045db2  movaps  xmmword ptr [rax-98h], xmm10
0x140045dba  movaps  xmmword ptr [rax-0A8h], xmm11
0x140045dc2  mov     rax, cs:__security_cookie
0x140045dc9  xor     rax, rsp
0x140045dcc  mov     [rbp+100h+var_B0], rax
0x140045dd0  mov     r14, rcx
0x140045dd3  xor     r12d, r12d
0x140045dd6  mov     dword ptr [rsp+200h+var_1C0], r12d
0x140045ddb  cmp     [rcx+10h], r12
0x140045ddf  jz      loc_1400461A4
0x140045de5  mov     ebx, r12d
0x140045de8  xor     edx, edx; dwCoInit
0x140045dea  xor     ecx, ecx; pvReserved
0x140045dec  call    cs:__imp_CoInitializeEx
0x140045df2  lea     r13d, [r12+1]
0x140045df7  test    eax, eax
0x140045df9  cmovns  ebx, r13d
0x140045dfd  mov     dword ptr [rsp+200h+var_1A0], ebx
0x140045e01  mov     rcx, [rbp+108h]; this
0x140045e08  js      loc_1400461FB
0x140045e0e  mov     [rsp+200h+var_1C8], r12
0x140045e13  lea     rcx, [rsp+200h+var_1C8]
0x140045e18  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x140045e1d  mov     qword ptr [rsp+200h+ppv], rax; int
0x140045e22  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140045e29  mov     r8d, r13d; dwClsContext
0x140045e2c  xor     edx, edx; pUnkOuter
0x140045e2e  lea     rcx, CLSID_TaskScheduler; rclsid
0x140045e35  call    cs:__imp_CoCreateInstance
0x140045e3b  mov     rcx, [rbp+108h]; this
0x140045e42  test    eax, eax
0x140045e44  js      loc_140046210
0x140045e4a  mov     rsi, [rsp+200h+var_1C8]
0x140045e4f  mov     rax, [rsi]
0x140045e52  mov     rdi, [rax+50h]
0x140045e56  lea     rcx, [rbp+100h+pvarg]; pvarg
0x140045e5a  call    cs:__imp_VariantInit
0x140045e60  nop
0x140045e61  movups  xmm10, xmmword ptr [rbp+100h+pvarg]
0x140045e66  movsd   xmm11, qword ptr [rbp+100h+pvarg+10h]
0x140045e6c  lea     rcx, [rbp+100h+var_160]; pvarg
0x140045e70  call    cs:__imp_VariantInit
0x140045e76  nop
0x140045e77  movups  xmm8, xmmword ptr [rbp+100h+var_160]
0x140045e7c  movsd   xmm9, qword ptr [rbp+100h+var_160+10h]
0x140045e82  lea     rcx, [rbp+100h+var_178]; pvarg
0x140045e86  call    cs:__imp_VariantInit
0x140045e8c  nop
0x140045e8d  movups  xmm6, xmmword ptr [rbp+100h+var_178]
0x140045e91  movsd   xmm7, qword ptr [rbp+100h+var_178+10h]
0x140045e96  lea     rcx, [rsp+200h+var_198+8]; pvarg
0x140045e9b  call    cs:__imp_VariantInit
0x140045ea1  nop
0x140045ea2  movups  xmm0, xmmword ptr [rsp+200h+var_198+8]
0x140045ea7  movsd   xmm1, [rbp+100h+var_180]
0x140045eac  movaps  xmmword ptr [rbp+100h+var_130], xmm10
0x140045eb1  movsd   [rbp+100h+var_120], xmm11
0x140045eb7  movaps  [rbp+100h+var_110], xmm8
0x140045ebc  movsd   [rbp+100h+var_100], xmm9
0x140045ec2  movaps  [rbp+100h+var_F0], xmm6
0x140045ec6  movsd   [rbp+100h+var_E0], xmm7
0x140045ecb  movaps  [rbp+100h+Src], xmm0
0x140045ecf  movsd   [rbp+100h+var_C0], xmm1
0x140045ed4  lea     rax, [rbp+100h+var_130]
0x140045ed8  mov     qword ptr [rsp+200h+ppv], rax; int
0x140045edd  lea     r9, [rbp+100h+var_110]
0x140045ee1  lea     r8, [rbp+100h+var_F0]
0x140045ee5  lea     rdx, [rbp+100h+Src]
0x140045ee9  mov     rcx, rsi
0x140045eec  mov     rax, rdi
0x140045eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ef4  mov     rcx, [rbp+108h]; this
0x140045efb  test    eax, eax
0x140045efd  js      loc_140046225
0x140045f03  lea     rcx, [rsp+200h+var_198+8]; pvarg
0x140045f08  call    cs:__imp_VariantClear
0x140045f0e  test    eax, eax
0x140045f10  js      loc_14004623A
0x140045f16  lea     rcx, [rbp+100h+var_178]; pvarg
0x140045f1a  call    cs:__imp_VariantClear
0x140045f20  test    eax, eax
0x140045f22  js      loc_140046242
0x140045f28  lea     rcx, [rbp+100h+var_160]; pvarg
0x140045f2c  call    cs:__imp_VariantClear
0x140045f32  test    eax, eax
0x140045f34  js      loc_14004624A
0x140045f3a  lea     rcx, [rbp+100h+pvarg]; pvarg
0x140045f3e  call    cs:__imp_VariantClear
0x140045f44  test    eax, eax
0x140045f46  js      loc_140046252
0x140045f4c  mov     [rsp+200h+var_1D0], r12
0x140045f51  mov     rcx, [rsp+200h+var_1C8]
0x140045f56  mov     rax, [rcx]
0x140045f59  lea     r8, [rsp+200h+var_1D0]
0x140045f5e  xor     edx, edx
0x140045f60  mov     rax, [rax+48h]
0x140045f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045f69  mov     rcx, [rbp+108h]; this
0x140045f70  test    eax, eax
0x140045f72  js      loc_14004625A
0x140045f78  mov     rsi, [rsp+200h+var_1D0]
0x140045f7d  mov     r15, [rsi]
0x140045f80  lea     rcx, aTaskXmlnsHttpS_0; "<Task xmlns=\"http://schemas.microsoft."...
0x140045f87  call    cs:__imp_SysAllocString
0x140045f8d  mov     rdi, rax
0x140045f90  mov     qword ptr [rsp+200h+var_198], rax
0x140045f95  mov     dword ptr [rsp+200h+var_1C0], r13d
0x140045f9a  mov     rcx, [rbp+108h]; this
0x140045fa1  test    rax, rax
0x140045fa4  jz      loc_14004626F
0x140045faa  mov     rdx, rax
0x140045fad  mov     rcx, rsi
0x140045fb0  mov     rax, [r15+0A0h]
0x140045fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045fbc  mov     rcx, [rbp+108h]; this
0x140045fc3  test    eax, eax
0x140045fc5  js      loc_140046281
0x140045fcb  mov     rcx, rdi; bstrString
0x140045fce  call    cs:__imp_SysFreeString
0x140045fd4  mov     [rsp+200h+var_1A8], r12
0x140045fd9  mov     rcx, [rsp+200h+var_1D0]
0x140045fde  mov     rax, [rcx]
0x140045fe1  lea     rdx, [rsp+200h+var_1A8]
0x140045fe6  mov     rax, [rax+48h]
0x140045fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045fef  mov     rcx, [rbp+108h]; this
0x140045ff6  test    eax, eax
0x140045ff8  js      loc_140046296
0x140045ffe  mov     [rsp+200h+var_1B0], r12
0x140046003  mov     rcx, [rsp+200h+var_1A8]
0x140046008  mov     rax, [rcx]
0x14004600b  lea     r8, [rsp+200h+var_1B0]
0x140046010  lea     edx, [r12+9]
0x140046015  mov     rax, [rax+50h]
0x140046019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004601e  mov     rcx, [rbp+108h]; this
0x140046025  test    eax, eax
0x140046027  js      loc_1400462AB
0x14004602d  mov     [rsp+200h+var_1B8], r12
0x140046032  mov     rcx, [rsp+200h+var_1B0]
0x140046037  mov     rax, [rcx]
0x14004603a  lea     r8, [rsp+200h+var_1B8]
0x14004603f  lea     rdx, _GUID_72dade38_fae4_4b3e_baf4_5d009af02b1c
0x140046046  mov     rax, [rax]
0x140046049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004604e  nop
0x14004604f  mov     rcx, [rbp+108h]; this
0x140046056  test    eax, eax
0x140046058  js      loc_1400462C0
0x14004605e  mov     rsi, [rsp+200h+var_1B8]
0x140046063  mov     r15, [rsi]
0x140046066  mov     rcx, [r14+10h]; psz
0x14004606a  call    cs:__imp_SysAllocString
0x140046070  mov     rdi, rax
0x140046073  mov     qword ptr [rsp+200h+var_198], rax
0x140046078  mov     dword ptr [rsp+200h+var_1C0], 2
0x140046080  mov     rcx, [rbp+108h]; this
0x140046087  test    rax, rax
0x14004608a  jz      loc_1400462D5
0x140046090  mov     rdx, rax
0x140046093  mov     rcx, rsi
0x140046096  mov     rax, [r15+0B8h]
0x14004609d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400460a2  mov     rcx, [rbp+108h]; this
0x1400460a9  test    eax, eax
0x1400460ab  js      loc_1400461E6
0x1400460b1  mov     rcx, rdi; bstrString
0x1400460b4  call    cs:__imp_SysFreeString
0x1400460ba  lea     r9, aLogin; "Login"
0x1400460c1  mov     r8, [r14+10h]; void *
0x1400460c5  mov     rdx, [r14+8]; void *
0x1400460c9  lea     rcx, [rbp+100h+Src]; Src
0x1400460cd  call    _anonymous_namespace___CreateCommandLine
0x1400460d2  nop
0x1400460d3  cmp     qword ptr [rax+18h], 7
0x1400460d8  jbe     short loc_1400460DD
0x1400460da  mov     rax, [rax]
0x1400460dd  mov     rdx, rax
0x1400460e0  mov     rcx, [rsp+200h+var_1D0]
0x1400460e5  call    _anonymous_namespace___AddCommandLine
0x1400460ea  nop
0x1400460eb  lea     rcx, [rbp+100h+Src]
0x1400460ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400460f4  lea     r9, aLogintask; "LoginTask"
0x1400460fb  mov     r8, [rsp+200h+var_1D0]; struct ITaskDefinition *
0x140046100  mov     rdx, [rsp+200h+var_1C8]; struct ITaskService *
0x140046105  mov     rcx, r14; this
0x140046108  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x14004610d  nop
0x14004610e  mov     rcx, [rsp+200h+var_1B8]
0x140046113  test    rcx, rcx
0x140046116  jz      short loc_14004612A
0x140046118  mov     [rsp+200h+var_1B8], r12
0x14004611d  mov     rax, [rcx]
0x140046120  mov     rax, [rax+10h]
0x140046124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046129  nop
0x14004612a  mov     rcx, [rsp+200h+var_1B0]
0x14004612f  test    rcx, rcx
0x140046132  jz      short loc_140046146
0x140046134  mov     [rsp+200h+var_1B0], r12
0x140046139  mov     rax, [rcx]
0x14004613c  mov     rax, [rax+10h]
0x140046140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046145  nop
0x140046146  mov     rcx, [rsp+200h+var_1A8]
0x14004614b  test    rcx, rcx
0x14004614e  jz      short loc_140046162
0x140046150  mov     [rsp+200h+var_1A8], r12
0x140046155  mov     rax, [rcx]
0x140046158  mov     rax, [rax+10h]
0x14004615c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046161  nop
0x140046162  mov     rcx, [rsp+200h+var_1D0]
0x140046167  test    rcx, rcx
0x14004616a  jz      short loc_14004617E
0x14004616c  mov     [rsp+200h+var_1D0], r12
0x140046171  mov     rax, [rcx]
0x140046174  mov     rax, [rax+10h]
0x140046178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004617d  nop
0x14004617e  mov     rcx, [rsp+200h+var_1C8]
0x140046183  test    rcx, rcx
0x140046186  jz      short loc_14004619A
0x140046188  mov     [rsp+200h+var_1C8], r12
0x14004618d  mov     rax, [rcx]
0x140046190  mov     rax, [rax+10h]
0x140046194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046199  nop
0x14004619a  test    ebx, ebx
0x14004619c  jz      short loc_1400461A4
0x14004619e  call    cs:__imp_CoUninitialize
0x1400461a4  mov     rcx, [rbp+100h+var_B0]
0x1400461a8  xor     rcx, rsp; StackCookie
0x1400461ab  call    __security_check_cookie
0x1400461b0  lea     r11, [rsp+200h+var_38]
0x1400461b8  movaps  xmm6, xmmword ptr [r11-18h]
0x1400461bd  movaps  xmm7, xmmword ptr [r11-28h]
0x1400461c2  movaps  xmm8, xmmword ptr [r11-38h]
0x1400461c7  movaps  xmm9, xmmword ptr [r11-48h]
0x1400461cc  movaps  xmm10, xmmword ptr [r11-58h]
0x1400461d1  movaps  xmm11, xmmword ptr [r11-68h]
0x1400461d6  mov     rsp, r11
0x1400461d9  pop     r15
0x1400461db  pop     r14
0x1400461dd  pop     r13
0x1400461df  pop     r12
0x1400461e1  pop     rdi
0x1400461e2  pop     rsi
0x1400461e3  pop     rbx
0x1400461e4  pop     rbp
0x1400461e5  retn
0x1400461e6  mov     r9d, eax; char *
0x1400461e9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400461f0  mov     edx, 0DCh; void *
0x1400461f5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400461fb  mov     r9d, eax; char *
0x1400461fe  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140046205  mov     edx, 0C9h; void *
0x14004620a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140046210  mov     r9d, eax; char *
0x140046213  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004621a  mov     edx, 0CCh; void *
0x14004621f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140046225  mov     r9d, eax; char *
0x140046228  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004622f  mov     edx, 0CDh; void *
0x140046234  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14004623a  mov     ecx, eax; int
0x14004623c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140046242  mov     ecx, eax; int
0x140046244  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004624a  mov     ecx, eax; int
0x14004624c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140046252  mov     ecx, eax; int
0x140046254  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004625a  mov     r9d, eax; char *
0x14004625d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140046264  mov     edx, 0D0h; void *
0x140046269  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14004626f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140046276  mov     edx, 15F3h; void *
0x14004627b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140046281  mov     r9d, eax; char *
0x140046284  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
  ... truncated ...
```
