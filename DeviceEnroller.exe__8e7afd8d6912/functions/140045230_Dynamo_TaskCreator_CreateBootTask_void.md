# Dynamo::TaskCreator::CreateBootTask(void)

- ea: `0x140045230`
- end: `0x14004574c`
- name: `?CreateBootTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `1308`
- prototype: `void __fastcall(void **this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1400042f0`
- `0x140005ea8`
- `0x14000a6e4`
- `0x14001ed14`
- `0x14003d008`
- `0x1400449e4`
- `0x140044ba0`
- `0x140045230`
- `0x140045754`
- `0x140046bd8`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140045432`
- `OLEAUT32!__imp_SysAllocString` at `0x140045432`
- `OLEAUT32!__imp_SysFreeString` at `0x140045478`
- `OLEAUT32!__imp_SysFreeString` at `0x140045478`
- `OLEAUT32!__imp_VariantInit` at `0x140045300`
- `OLEAUT32!__imp_VariantInit` at `0x140045316`
- `OLEAUT32!__imp_VariantInit` at `0x14004532c`
- `OLEAUT32!__imp_VariantInit` at `0x140045341`
- `OLEAUT32!__imp_VariantInit` at `0x140045300`
- `OLEAUT32!__imp_VariantInit` at `0x140045316`
- `OLEAUT32!__imp_VariantInit` at `0x14004532c`
- `OLEAUT32!__imp_VariantInit` at `0x140045341`
- `OLEAUT32!__imp_VariantClear` at `0x1400453af`
- `OLEAUT32!__imp_VariantClear` at `0x1400453c1`
- `OLEAUT32!__imp_VariantClear` at `0x1400453d3`
- `OLEAUT32!__imp_VariantClear` at `0x1400453e5`
- `OLEAUT32!__imp_VariantClear` at `0x1400453af`
- `OLEAUT32!__imp_VariantClear` at `0x1400453c1`
- `OLEAUT32!__imp_VariantClear` at `0x1400453d3`
- `OLEAUT32!__imp_VariantClear` at `0x1400453e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400452db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400452db`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140045626`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140045626`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14004528f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14004528f`

## string_xrefs

- `0x1400456fb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140045568`: `BootTask`
- `0x14004542b`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x140045675`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x14004568a`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x14004569f`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400456b4`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400456e9`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045710`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045725`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x14004573a`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dynamo::TaskCreator::CreateBootTask(void **this)
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
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v32; // rcx
  struct ITaskDefinition *v33; // rcx
  struct ITaskService *v34; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v37; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v38; // [rsp+40h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v43; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+80h] [rbp-88h]
  VARIANTARG v45; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v46; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-50h] BYREF
  BSTR v48; // [rsp+D0h] [rbp-38h]
  int v49[4]; // [rsp+D8h] [rbp-30h] BYREF
  IRecordInfo *v50; // [rsp+E8h] [rbp-20h]
  __int128 v51; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v52; // [rsp+108h] [rbp+0h]
  __int128 v53; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v54; // [rsp+128h] [rbp+20h]
  __int128 Src; // [rsp+138h] [rbp+30h] BYREF
  __int64 v56; // [rsp+148h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  LODWORD(v41) = 0;
  v2 = CoInitializeEx(0, 0);
  v3 = v2 >= 0;
  *(_DWORD *)&v43.vt = v3;
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA0,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  v38 = 0;
  v4 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>((__int64 *)&v38);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v4);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA3,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v6 = v38;
  Connect = v38->lpVtbl->Connect;
  VariantInit(&pvarg);
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v46);
  v10 = *(_OWORD *)&v46.vt;
  v11 = v46.pRecInfo;
  VariantInit(&v45);
  v12 = *(_OWORD *)&v45.vt;
  v13 = v45.pRecInfo;
  VariantInit((VARIANTARG *)&v43.decVal.8);
  *(_OWORD *)v49 = v8;
  v50 = pRecInfo;
  v51 = v10;
  v52 = v11;
  v53 = v12;
  v54 = v13;
  Src = *(_OWORD *)&v43.decVal.Lo32;
  v56 = v44;
  v14 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
          v6,
          &Src,
          &v53,
          &v51);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA4,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v14,
      (int)v49);
  v15 = VariantClear((VARIANTARG *)&v43.decVal.8);
  if ( v15 < 0 )
    _com_issue_error(v15);
  v16 = VariantClear(&v45);
  if ( v16 < 0 )
    _com_issue_error(v16);
  v17 = VariantClear(&v46);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear(&pvarg);
  if ( v18 < 0 )
    _com_issue_error(v18);
  v37 = 0;
  v19 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))v38->lpVtbl->NewTask)(
          v38,
          0,
          &v37);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA7,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v19,
      (int)v49);
  v20 = v37;
  lpVtbl = v37->lpVtbl;
  v22 = SysAllocString(
          L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsoft-c"
           "om:asm.v3\">\n"
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
  v48 = v22;
  LODWORD(v41) = 1;
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
      (void *)0xA8,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v25,
      (int)v49);
  SysFreeString(v24);
  v40 = 0;
  v26 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v37->lpVtbl->get_Triggers)(v37, &v40);
  if ( v26 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xAB,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v26,
      (int)v49);
  v39 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v40 + 80LL))(v40, 8, &v39);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xAE,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v27,
      (int)v49);
  v42 = 0;
  v28 = (**v39)(v39, &GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb, &v42);
  if ( v28 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB1,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v28,
      (int)v49);
  v29 = (_QWORD *)anonymous_namespace_::CreateCommandLine(&Src, this[1], this[2], L"Boot");
  if ( v29[3] > 7u )
    v29 = (_QWORD *)*v29;
  anonymous_namespace_::AddCommandLine(v37, v29);
  std::wstring::~wstring((char **)&Src);
  v41 = WNF_NASV_SERVICE_RUNNING;
  anonymous_namespace_::AddWnfTrigger(v37, &v41);
  Dynamo::TaskCreator::RegisterTask((Dynamo::TaskCreator *)this, v38, v37, L"BootTask");
  v30 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v39;
  if ( v39 )
  {
    v39 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v31)[2])(v31);
  }
  v32 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v37;
  if ( v37 )
  {
    v37 = 0;
    ((void (__fastcall *)(struct ITaskDefinition *))v33->lpVtbl->Release)(v33);
  }
  v34 = v38;
  if ( v38 )
  {
    v38 = 0;
    ((void (__fastcall *)(struct ITaskService *))v34->lpVtbl->Release)(v34);
  }
  if ( v3 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140045230  mov     rax, rsp
0x140045233  mov     [rax+10h], rbx
0x140045237  mov     [rax+18h], rsi
0x14004523b  push    rbp
0x14004523c  push    rdi
0x14004523d  push    r13
0x14004523f  push    r14
0x140045241  push    r15
0x140045243  lea     rbp, [rax-0E8h]
0x14004524a  sub     rsp, 1C0h
0x140045251  movaps  xmmword ptr [rax-38h], xmm6
0x140045255  movaps  xmmword ptr [rax-48h], xmm7
0x140045259  movaps  xmmword ptr [rax-58h], xmm8
0x14004525e  movaps  xmmword ptr [rax-68h], xmm9
0x140045263  movaps  xmmword ptr [rax-78h], xmm10
0x140045268  movaps  xmmword ptr [rax-88h], xmm11
0x140045270  mov     rax, cs:__security_cookie
0x140045277  xor     rax, rsp
0x14004527a  mov     [rbp+0E0h+var_90], rax
0x14004527e  mov     r14, rcx
0x140045281  mov     dword ptr [rsp+1E0h+var_190], 0
0x140045289  xor     ebx, ebx
0x14004528b  xor     edx, edx; dwCoInit
0x14004528d  xor     ecx, ecx; pvReserved
0x14004528f  call    cs:__imp_CoInitializeEx
0x140045295  lea     r13d, [rbx+1]
0x140045299  test    eax, eax
0x14004529b  cmovns  ebx, r13d
0x14004529f  mov     dword ptr [rsp+1E0h+var_180], ebx
0x1400452a3  mov     rcx, [rbp+0E8h]; this
0x1400452aa  js      loc_140045687
0x1400452b0  mov     [rsp+1E0h+var_1A8], 0
0x1400452b9  lea     rcx, [rsp+1E0h+var_1A8]
0x1400452be  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x1400452c3  mov     qword ptr [rsp+1E0h+ppv], rax; int
0x1400452c8  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1400452cf  mov     r8d, r13d; dwClsContext
0x1400452d2  xor     edx, edx; pUnkOuter
0x1400452d4  lea     rcx, CLSID_TaskScheduler; rclsid
0x1400452db  call    cs:__imp_CoCreateInstance
0x1400452e1  mov     rcx, [rbp+0E8h]; this
0x1400452e8  test    eax, eax
0x1400452ea  js      loc_14004569C
0x1400452f0  mov     rsi, [rsp+1E0h+var_1A8]
0x1400452f5  mov     rax, [rsi]
0x1400452f8  mov     rdi, [rax+50h]
0x1400452fc  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x140045300  call    cs:__imp_VariantInit
0x140045306  nop
0x140045307  movups  xmm10, xmmword ptr [rbp+0E0h+pvarg]
0x14004530c  movsd   xmm11, qword ptr [rbp+0E0h+pvarg+10h]
0x140045312  lea     rcx, [rbp+0E0h+var_148]; pvarg
0x140045316  call    cs:__imp_VariantInit
0x14004531c  nop
0x14004531d  movups  xmm8, xmmword ptr [rbp+0E0h+var_148]
0x140045322  movsd   xmm9, qword ptr [rbp+0E0h+var_148+10h]
0x140045328  lea     rcx, [rbp+0E0h+var_160]; pvarg
0x14004532c  call    cs:__imp_VariantInit
0x140045332  nop
0x140045333  movups  xmm6, xmmword ptr [rbp+0E0h+var_160]
0x140045337  movsd   xmm7, qword ptr [rbp+0E0h+var_160+10h]
0x14004533c  lea     rcx, [rsp+1E0h+var_180+8]; pvarg
0x140045341  call    cs:__imp_VariantInit
0x140045347  nop
0x140045348  movups  xmm0, xmmword ptr [rsp+1E0h+var_180+8]
0x14004534d  movsd   xmm1, [rsp+1E0h+var_168]
0x140045353  movaps  xmmword ptr [rbp+0E0h+var_110], xmm10
0x140045358  movsd   [rbp+0E0h+var_100], xmm11
0x14004535e  movaps  [rbp+0E0h+var_F0], xmm8
0x140045363  movsd   [rbp+0E0h+var_E0], xmm9
0x140045369  movaps  [rbp+0E0h+var_D0], xmm6
0x14004536d  movsd   [rbp+0E0h+var_C0], xmm7
0x140045372  movaps  [rbp+0E0h+Src], xmm0
0x140045376  movsd   [rbp+0E0h+var_A0], xmm1
0x14004537b  lea     rax, [rbp+0E0h+var_110]
0x14004537f  mov     qword ptr [rsp+1E0h+ppv], rax; int
0x140045384  lea     r9, [rbp+0E0h+var_F0]
0x140045388  lea     r8, [rbp+0E0h+var_D0]
0x14004538c  lea     rdx, [rbp+0E0h+Src]
0x140045390  mov     rcx, rsi
0x140045393  mov     rax, rdi
0x140045396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004539b  mov     rcx, [rbp+0E8h]; this
0x1400453a2  test    eax, eax
0x1400453a4  js      loc_1400456B1
0x1400453aa  lea     rcx, [rsp+1E0h+var_180+8]; pvarg
0x1400453af  call    cs:__imp_VariantClear
0x1400453b5  test    eax, eax
0x1400453b7  js      loc_1400456C6
0x1400453bd  lea     rcx, [rbp+0E0h+var_160]; pvarg
0x1400453c1  call    cs:__imp_VariantClear
0x1400453c7  test    eax, eax
0x1400453c9  js      loc_1400456CE
0x1400453cf  lea     rcx, [rbp+0E0h+var_148]; pvarg
0x1400453d3  call    cs:__imp_VariantClear
0x1400453d9  test    eax, eax
0x1400453db  js      loc_1400456D6
0x1400453e1  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x1400453e5  call    cs:__imp_VariantClear
0x1400453eb  test    eax, eax
0x1400453ed  js      loc_1400456DE
0x1400453f3  mov     [rsp+1E0h+var_1B0], 0
0x1400453fc  mov     rcx, [rsp+1E0h+var_1A8]
0x140045401  mov     rax, [rcx]
0x140045404  lea     r8, [rsp+1E0h+var_1B0]
0x140045409  xor     edx, edx
0x14004540b  mov     rax, [rax+48h]
0x14004540f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045414  mov     rcx, [rbp+0E8h]; this
0x14004541b  test    eax, eax
0x14004541d  js      loc_1400456E6
0x140045423  mov     rsi, [rsp+1E0h+var_1B0]
0x140045428  mov     r15, [rsi]
0x14004542b  lea     rcx, aTaskXmlnsHttpS_0; "<Task xmlns=\"http://schemas.microsoft."...
0x140045432  call    cs:__imp_SysAllocString
0x140045438  mov     rdi, rax
0x14004543b  mov     [rbp+0E0h+var_118], rax
0x14004543f  mov     dword ptr [rsp+1E0h+var_190], r13d
0x140045444  mov     rcx, [rbp+0E8h]; this
0x14004544b  test    rax, rax
0x14004544e  jz      loc_1400456FB
0x140045454  mov     rdx, rax
0x140045457  mov     rcx, rsi
0x14004545a  mov     rax, [r15+0A0h]
0x140045461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045466  mov     rcx, [rbp+0E8h]; this
0x14004546d  test    eax, eax
0x14004546f  js      loc_14004570D
0x140045475  mov     rcx, rdi; bstrString
0x140045478  call    cs:__imp_SysFreeString
0x14004547e  mov     [rsp+1E0h+var_198], 0
0x140045487  mov     rcx, [rsp+1E0h+var_1B0]
0x14004548c  mov     rax, [rcx]
0x14004548f  lea     rdx, [rsp+1E0h+var_198]
0x140045494  mov     rax, [rax+48h]
0x140045498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004549d  mov     rcx, [rbp+0E8h]; this
0x1400454a4  test    eax, eax
0x1400454a6  js      loc_140045722
0x1400454ac  mov     [rsp+1E0h+var_1A0], 0
0x1400454b5  mov     rcx, [rsp+1E0h+var_198]
0x1400454ba  mov     rax, [rcx]
0x1400454bd  lea     r8, [rsp+1E0h+var_1A0]
0x1400454c2  lea     edx, [r13+7]
0x1400454c6  mov     rax, [rax+50h]
0x1400454ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400454cf  mov     rcx, [rbp+0E8h]; this
0x1400454d6  test    eax, eax
0x1400454d8  js      loc_140045737
0x1400454de  mov     [rsp+1E0h+var_188], 0
0x1400454e7  mov     rcx, [rsp+1E0h+var_1A0]
0x1400454ec  mov     rax, [rcx]
0x1400454ef  lea     r8, [rsp+1E0h+var_188]
0x1400454f4  lea     rdx, _GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb
0x1400454fb  mov     rax, [rax]
0x1400454fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045503  nop
0x140045504  mov     rcx, [rbp+0E8h]; this
0x14004550b  test    eax, eax
0x14004550d  js      loc_140045672
0x140045513  lea     r9, aBoot; "Boot"
0x14004551a  mov     r8, [r14+10h]; void *
0x14004551e  mov     rdx, [r14+8]; void *
0x140045522  lea     rcx, [rbp+0E0h+Src]; Src
0x140045526  call    _anonymous_namespace___CreateCommandLine
0x14004552b  nop
0x14004552c  cmp     qword ptr [rax+18h], 7
0x140045531  jbe     short loc_140045536
0x140045533  mov     rax, [rax]
0x140045536  mov     rdx, rax
0x140045539  mov     rcx, [rsp+1E0h+var_1B0]
0x14004553e  call    _anonymous_namespace___AddCommandLine
0x140045543  nop
0x140045544  lea     rcx, [rbp+0E0h+Src]
0x140045548  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004554d  mov     rax, cs:WNF_NASV_SERVICE_RUNNING
0x140045554  mov     [rsp+1E0h+var_190], rax
0x140045559  lea     rdx, [rsp+1E0h+var_190]
0x14004555e  mov     rcx, [rsp+1E0h+var_1B0]
0x140045563  call    _anonymous_namespace___AddWnfTrigger
0x140045568  lea     r9, aBoottask; "BootTask"
0x14004556f  mov     r8, [rsp+1E0h+var_1B0]; struct ITaskDefinition *
0x140045574  mov     rdx, [rsp+1E0h+var_1A8]; struct ITaskService *
0x140045579  mov     rcx, r14; this
0x14004557c  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x140045581  nop
0x140045582  mov     rcx, [rsp+1E0h+var_188]
0x140045587  test    rcx, rcx
0x14004558a  jz      short loc_1400455A2
0x14004558c  mov     [rsp+1E0h+var_188], 0
0x140045595  mov     rax, [rcx]
0x140045598  mov     rax, [rax+10h]
0x14004559c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400455a1  nop
0x1400455a2  mov     rcx, [rsp+1E0h+var_1A0]
0x1400455a7  test    rcx, rcx
0x1400455aa  jz      short loc_1400455C2
0x1400455ac  mov     [rsp+1E0h+var_1A0], 0
0x1400455b5  mov     rax, [rcx]
0x1400455b8  mov     rax, [rax+10h]
0x1400455bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400455c1  nop
0x1400455c2  mov     rcx, [rsp+1E0h+var_198]
0x1400455c7  test    rcx, rcx
0x1400455ca  jz      short loc_1400455E2
0x1400455cc  mov     [rsp+1E0h+var_198], 0
0x1400455d5  mov     rax, [rcx]
0x1400455d8  mov     rax, [rax+10h]
0x1400455dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400455e1  nop
0x1400455e2  mov     rcx, [rsp+1E0h+var_1B0]
0x1400455e7  test    rcx, rcx
0x1400455ea  jz      short loc_140045602
0x1400455ec  mov     [rsp+1E0h+var_1B0], 0
0x1400455f5  mov     rax, [rcx]
0x1400455f8  mov     rax, [rax+10h]
0x1400455fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045601  nop
0x140045602  mov     rcx, [rsp+1E0h+var_1A8]
0x140045607  test    rcx, rcx
0x14004560a  jz      short loc_140045622
0x14004560c  mov     [rsp+1E0h+var_1A8], 0
0x140045615  mov     rax, [rcx]
0x140045618  mov     rax, [rax+10h]
0x14004561c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045621  nop
0x140045622  test    ebx, ebx
0x140045624  jz      short loc_14004562C
0x140045626  call    cs:__imp_CoUninitialize
0x14004562c  mov     rcx, [rbp+0E0h+var_90]
0x140045630  xor     rcx, rsp; StackCookie
0x140045633  call    __security_check_cookie
0x140045638  lea     r11, [rsp+1E0h+var_20]
0x140045640  mov     rbx, [r11+38h]
0x140045644  mov     rsi, [r11+40h]
0x140045648  movaps  xmm6, xmmword ptr [r11-10h]
0x14004564d  movaps  xmm7, xmmword ptr [r11-20h]
0x140045652  movaps  xmm8, xmmword ptr [r11-30h]
0x140045657  movaps  xmm9, xmmword ptr [r11-40h]
0x14004565c  movaps  xmm10, xmmword ptr [r11-50h]
0x140045661  movaps  xmm11, xmmword ptr [r11-60h]
0x140045666  mov     rsp, r11
0x140045669  pop     r15
0x14004566b  pop     r14
0x14004566d  pop     r13
0x14004566f  pop     rdi
0x140045670  pop     rbp
0x140045671  retn
0x140045672  mov     r9d, eax; char *
0x140045675  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004567c  mov     edx, 0B1h; void *
0x140045681  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045687  mov     r9d, eax; char *
0x14004568a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045691  mov     edx, 0A0h; void *
0x140045696  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14004569c  mov     r9d, eax; char *
0x14004569f  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400456a6  mov     edx, 0A3h; void *
0x1400456ab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400456b1  mov     r9d, eax; char *
0x1400456b4  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400456bb  mov     edx, 0A4h; void *
0x1400456c0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400456c6  mov     ecx, eax; int
0x1400456c8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400456ce  mov     ecx, eax; int
0x1400456d0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400456d6  mov     ecx, eax; int
0x1400456d8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400456de  mov     ecx, eax; int
0x1400456e0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400456e6  mov     r9d, eax; char *
0x1400456e9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400456f0  mov     edx, 0A7h; void *
0x1400456f5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400456fb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140045702  mov     edx, 15F3h; void *
0x140045707  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14004570d  mov     r9d, eax; char *
0x140045710  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045717  mov     edx, 0A8h; void *
0x14004571c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045722  mov     r9d, eax; char *
0x140045725  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004572c  mov     edx, 0ABh; void *
0x140045731  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045737  mov     r9d, eax; char *
0x14004573a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045741  mov     edx, 0AEh; void *
0x140045746  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
