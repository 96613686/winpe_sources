# Dynamo::TaskCreator::CreateAlertTask(void)

- ea: `0x140044e50`
- end: `0x140045224`
- name: `?CreateAlertTask@TaskCreator@Dynamo@@UEAAXXZ`
- size: `980`
- prototype: `void __fastcall(void **this)`
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
- `0x140044e50`
- `0x140045754`
- `0x140046bd8`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140045059`
- `OLEAUT32!__imp_SysAllocString` at `0x140045059`
- `OLEAUT32!__imp_SysFreeString` at `0x14004509f`
- `OLEAUT32!__imp_SysFreeString` at `0x14004509f`
- `OLEAUT32!__imp_VariantInit` at `0x140044f20`
- `OLEAUT32!__imp_VariantInit` at `0x140044f37`
- `OLEAUT32!__imp_VariantInit` at `0x140044f4f`
- `OLEAUT32!__imp_VariantInit` at `0x140044f66`
- `OLEAUT32!__imp_VariantInit` at `0x140044f20`
- `OLEAUT32!__imp_VariantInit` at `0x140044f37`
- `OLEAUT32!__imp_VariantInit` at `0x140044f4f`
- `OLEAUT32!__imp_VariantInit` at `0x140044f66`
- `OLEAUT32!__imp_VariantClear` at `0x140044fd4`
- `OLEAUT32!__imp_VariantClear` at `0x140044fe7`
- `OLEAUT32!__imp_VariantClear` at `0x140044ffa`
- `OLEAUT32!__imp_VariantClear` at `0x14004500c`
- `OLEAUT32!__imp_VariantClear` at `0x140044fd4`
- `OLEAUT32!__imp_VariantClear` at `0x140044fe7`
- `OLEAUT32!__imp_VariantClear` at `0x140044ffa`
- `OLEAUT32!__imp_VariantClear` at `0x14004500c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140044efb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140044efb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004513d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004513d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140044eaf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140044eaf`

## string_xrefs

- `0x140045212`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140045052`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x1400450df`: `AlertTask`
- `0x14004518c`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400451a1`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400451b6`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1400451cb`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045200`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dynamo::TaskCreator::CreateAlertTask(void **this)
{
  HRESULT v2; // eax
  ULONG v3; // ebx
  __int64 *v4; // rax
  HRESULT Instance; // eax
  struct ITaskService *v6; // rsi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rdi
  __int128 v8; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v10; // xmm8
  __int64 v11; // xmm9_8
  __int128 v12; // xmm6
  __int64 v13; // xmm7_8
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
  _QWORD *v26; // rax
  struct ITaskDefinition *v27; // rcx
  struct ITaskService *v28; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v31; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v32; // [rsp+40h] [rbp-C8h] BYREF
  VARIANTARG v33; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG v34; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v35; // [rsp+78h] [rbp-90h] BYREF
  __int64 v36; // [rsp+90h] [rbp-78h]
  VARIANTARG pvarg; // [rsp+98h] [rbp-70h] BYREF
  BSTR v38; // [rsp+B0h] [rbp-58h]
  int v39[4]; // [rsp+B8h] [rbp-50h] BYREF
  IRecordInfo *v40; // [rsp+C8h] [rbp-40h]
  __int128 v41; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v42; // [rsp+E8h] [rbp-20h]
  __int128 v43; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v44; // [rsp+108h] [rbp+0h]
  __int128 Src; // [rsp+118h] [rbp+10h] BYREF
  __int64 v46; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  *(_DWORD *)&v33.vt = 0;
  v2 = CoInitializeEx(0, 0);
  v3 = v2 >= 0;
  v33.decVal.Hi32 = v3;
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF0,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  v32 = 0;
  v4 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>((__int64 *)&v32);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v4);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF3,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v6 = v32;
  Connect = v32->lpVtbl->Connect;
  VariantInit(&pvarg);
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit((VARIANTARG *)&v35.decVal.8);
  v10 = *(_OWORD *)&v35.decVal.Lo32;
  v11 = v36;
  VariantInit((VARIANTARG *)&v34.decVal.8);
  v12 = *(_OWORD *)&v34.decVal.Lo32;
  v13 = *(_QWORD *)&v35.vt;
  VariantInit((VARIANTARG *)&v33.decVal.8);
  *(_OWORD *)v39 = v8;
  v40 = pRecInfo;
  v41 = v10;
  v42 = v11;
  v43 = v12;
  v44 = v13;
  Src = *(_OWORD *)&v33.decVal.Lo32;
  v46 = *(_QWORD *)&v34.vt;
  v14 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
          v6,
          &Src,
          &v43,
          &v41);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF4,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v14,
      (int)v39);
  v15 = VariantClear((VARIANTARG *)&v33.decVal.8);
  if ( v15 < 0 )
    _com_issue_error(v15);
  v16 = VariantClear((VARIANTARG *)&v34.decVal.8);
  if ( v16 < 0 )
    _com_issue_error(v16);
  v17 = VariantClear((VARIANTARG *)&v35.decVal.8);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear(&pvarg);
  if ( v18 < 0 )
    _com_issue_error(v18);
  v31 = 0;
  v19 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))v32->lpVtbl->NewTask)(
          v32,
          0,
          &v31);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF7,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v19,
      (int)v39);
  v20 = v31;
  lpVtbl = v31->lpVtbl;
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
  v38 = v22;
  *(_DWORD *)&v33.vt = 1;
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
      (void *)0xF8,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v25,
      (int)v39);
  SysFreeString(v24);
  v26 = (_QWORD *)anonymous_namespace_::CreateCommandLine(&Src, this[1], this[2], L"Alert");
  if ( v26[3] > 7u )
    v26 = (_QWORD *)*v26;
  anonymous_namespace_::AddCommandLine(v31, v26);
  std::wstring::~wstring((char **)&Src);
  Dynamo::TaskCreator::RegisterTask((Dynamo::TaskCreator *)this, v32, v31, L"AlertTask");
  v27 = v31;
  if ( v31 )
  {
    v31 = 0;
    ((void (__fastcall *)(struct ITaskDefinition *))v27->lpVtbl->Release)(v27);
  }
  v28 = v32;
  if ( v32 )
  {
    v32 = 0;
    ((void (__fastcall *)(struct ITaskService *))v28->lpVtbl->Release)(v28);
  }
  if ( v3 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140044e50  mov     rax, rsp
0x140044e53  mov     [rax+10h], rbx
0x140044e57  mov     [rax+18h], rsi
0x140044e5b  push    rbp
0x140044e5c  push    rdi
0x140044e5d  push    r13
0x140044e5f  push    r14
0x140044e61  push    r15
0x140044e63  lea     rbp, [rax-0C8h]
0x140044e6a  sub     rsp, 1A0h
0x140044e71  movaps  xmmword ptr [rax-38h], xmm6
0x140044e75  movaps  xmmword ptr [rax-48h], xmm7
0x140044e79  movaps  xmmword ptr [rax-58h], xmm8
0x140044e7e  movaps  xmmword ptr [rax-68h], xmm9
0x140044e83  movaps  xmmword ptr [rax-78h], xmm10
0x140044e88  movaps  xmmword ptr [rax-88h], xmm11
0x140044e90  mov     rax, cs:__security_cookie
0x140044e97  xor     rax, rsp
0x140044e9a  mov     [rbp+0C0h+var_90], rax
0x140044e9e  mov     r14, rcx
0x140044ea1  mov     dword ptr [rsp+1C0h+var_180], 0
0x140044ea9  xor     ebx, ebx
0x140044eab  xor     edx, edx; dwCoInit
0x140044ead  xor     ecx, ecx; pvReserved
0x140044eaf  call    cs:__imp_CoInitializeEx
0x140044eb5  lea     r13d, [rbx+1]
0x140044eb9  test    eax, eax
0x140044ebb  cmovns  ebx, r13d
0x140044ebf  mov     dword ptr [rsp+1C0h+var_180+4], ebx
0x140044ec3  mov     rcx, [rbp+0C8h]; this
0x140044eca  js      loc_14004519E
0x140044ed0  mov     [rsp+1C0h+var_188], 0
0x140044ed9  lea     rcx, [rsp+1C0h+var_188]
0x140044ede  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x140044ee3  mov     qword ptr [rsp+1C0h+ppv], rax; int
0x140044ee8  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140044eef  mov     r8d, r13d; dwClsContext
0x140044ef2  xor     edx, edx; pUnkOuter
0x140044ef4  lea     rcx, CLSID_TaskScheduler; rclsid
0x140044efb  call    cs:__imp_CoCreateInstance
0x140044f01  mov     rcx, [rbp+0C8h]; this
0x140044f08  test    eax, eax
0x140044f0a  js      loc_1400451B3
0x140044f10  mov     rsi, [rsp+1C0h+var_188]
0x140044f15  mov     rax, [rsi]
0x140044f18  mov     rdi, [rax+50h]
0x140044f1c  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x140044f20  call    cs:__imp_VariantInit
0x140044f26  nop
0x140044f27  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x140044f2c  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x140044f32  lea     rcx, [rsp+1C0h+var_150+8]; pvarg
0x140044f37  call    cs:__imp_VariantInit
0x140044f3d  nop
0x140044f3e  movups  xmm8, xmmword ptr [rsp+1C0h+var_150+8]
0x140044f44  movsd   xmm9, [rbp+0C0h+var_138]
0x140044f4a  lea     rcx, [rsp+1C0h+var_168+8]; pvarg
0x140044f4f  call    cs:__imp_VariantInit
0x140044f55  nop
0x140044f56  movups  xmm6, xmmword ptr [rsp+1C0h+var_168+8]
0x140044f5b  movsd   xmm7, qword ptr [rsp+1C0h+var_150]
0x140044f61  lea     rcx, [rsp+1C0h+var_180+8]; pvarg
0x140044f66  call    cs:__imp_VariantInit
0x140044f6c  nop
0x140044f6d  movups  xmm0, xmmword ptr [rsp+1C0h+var_180+8]
0x140044f72  movsd   xmm1, qword ptr [rsp+1C0h+var_168]
0x140044f78  movaps  xmmword ptr [rbp+0C0h+var_110], xmm10
0x140044f7d  movsd   [rbp+0C0h+var_100], xmm11
0x140044f83  movaps  [rbp+0C0h+var_F0], xmm8
0x140044f88  movsd   [rbp+0C0h+var_E0], xmm9
0x140044f8e  movaps  [rbp+0C0h+var_D0], xmm6
0x140044f92  movsd   [rbp+0C0h+var_C0], xmm7
0x140044f97  movaps  [rbp+0C0h+Src], xmm0
0x140044f9b  movsd   [rbp+0C0h+var_A0], xmm1
0x140044fa0  lea     rax, [rbp+0C0h+var_110]
0x140044fa4  mov     qword ptr [rsp+1C0h+ppv], rax; int
0x140044fa9  lea     r9, [rbp+0C0h+var_F0]
0x140044fad  lea     r8, [rbp+0C0h+var_D0]
0x140044fb1  lea     rdx, [rbp+0C0h+Src]
0x140044fb5  mov     rcx, rsi
0x140044fb8  mov     rax, rdi
0x140044fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044fc0  mov     rcx, [rbp+0C8h]; this
0x140044fc7  test    eax, eax
0x140044fc9  js      loc_1400451C8
0x140044fcf  lea     rcx, [rsp+1C0h+var_180+8]; pvarg
0x140044fd4  call    cs:__imp_VariantClear
0x140044fda  test    eax, eax
0x140044fdc  js      loc_1400451DD
0x140044fe2  lea     rcx, [rsp+1C0h+var_168+8]; pvarg
0x140044fe7  call    cs:__imp_VariantClear
0x140044fed  test    eax, eax
0x140044fef  js      loc_1400451E5
0x140044ff5  lea     rcx, [rsp+1C0h+var_150+8]; pvarg
0x140044ffa  call    cs:__imp_VariantClear
0x140045000  test    eax, eax
0x140045002  js      loc_1400451ED
0x140045008  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x14004500c  call    cs:__imp_VariantClear
0x140045012  test    eax, eax
0x140045014  js      loc_1400451F5
0x14004501a  mov     [rsp+1C0h+var_190], 0
0x140045023  mov     rcx, [rsp+1C0h+var_188]
0x140045028  mov     rax, [rcx]
0x14004502b  lea     r8, [rsp+1C0h+var_190]
0x140045030  xor     edx, edx
0x140045032  mov     rax, [rax+48h]
0x140045036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004503b  mov     rcx, [rbp+0C8h]; this
0x140045042  test    eax, eax
0x140045044  js      loc_1400451FD
0x14004504a  mov     rsi, [rsp+1C0h+var_190]
0x14004504f  mov     r15, [rsi]
0x140045052  lea     rcx, aTaskXmlnsHttpS_0; "<Task xmlns=\"http://schemas.microsoft."...
0x140045059  call    cs:__imp_SysAllocString
0x14004505f  mov     rdi, rax
0x140045062  mov     [rbp+0C0h+var_118], rax
0x140045066  mov     dword ptr [rsp+1C0h+var_180], r13d
0x14004506b  mov     rcx, [rbp+0C8h]; this
0x140045072  test    rax, rax
0x140045075  jz      loc_140045212
0x14004507b  mov     rdx, rax
0x14004507e  mov     rcx, rsi
0x140045081  mov     rax, [r15+0A0h]
0x140045088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004508d  mov     rcx, [rbp+0C8h]; this
0x140045094  test    eax, eax
0x140045096  js      loc_140045189
0x14004509c  mov     rcx, rdi; bstrString
0x14004509f  call    cs:__imp_SysFreeString
0x1400450a5  lea     r9, aAlert; "Alert"
0x1400450ac  mov     r8, [r14+10h]; void *
0x1400450b0  mov     rdx, [r14+8]; void *
0x1400450b4  lea     rcx, [rbp+0C0h+Src]; Src
0x1400450b8  call    _anonymous_namespace___CreateCommandLine
0x1400450bd  nop
0x1400450be  cmp     qword ptr [rax+18h], 7
0x1400450c3  jbe     short loc_1400450C8
0x1400450c5  mov     rax, [rax]
0x1400450c8  mov     rdx, rax
0x1400450cb  mov     rcx, [rsp+1C0h+var_190]
0x1400450d0  call    _anonymous_namespace___AddCommandLine
0x1400450d5  nop
0x1400450d6  lea     rcx, [rbp+0C0h+Src]
0x1400450da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400450df  lea     r9, aAlerttask; "AlertTask"
0x1400450e6  mov     r8, [rsp+1C0h+var_190]; struct ITaskDefinition *
0x1400450eb  mov     rdx, [rsp+1C0h+var_188]; struct ITaskService *
0x1400450f0  mov     rcx, r14; this
0x1400450f3  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x1400450f8  nop
0x1400450f9  mov     rcx, [rsp+1C0h+var_190]
0x1400450fe  test    rcx, rcx
0x140045101  jz      short loc_140045119
0x140045103  mov     [rsp+1C0h+var_190], 0
0x14004510c  mov     rax, [rcx]
0x14004510f  mov     rax, [rax+10h]
0x140045113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045118  nop
0x140045119  mov     rcx, [rsp+1C0h+var_188]
0x14004511e  test    rcx, rcx
0x140045121  jz      short loc_140045139
0x140045123  mov     [rsp+1C0h+var_188], 0
0x14004512c  mov     rax, [rcx]
0x14004512f  mov     rax, [rax+10h]
0x140045133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045138  nop
0x140045139  test    ebx, ebx
0x14004513b  jz      short loc_140045143
0x14004513d  call    cs:__imp_CoUninitialize
0x140045143  mov     rcx, [rbp+0C0h+var_90]
0x140045147  xor     rcx, rsp; StackCookie
0x14004514a  call    __security_check_cookie
0x14004514f  lea     r11, [rsp+1C0h+var_20]
0x140045157  mov     rbx, [r11+38h]
0x14004515b  mov     rsi, [r11+40h]
0x14004515f  movaps  xmm6, xmmword ptr [r11-10h]
0x140045164  movaps  xmm7, xmmword ptr [r11-20h]
0x140045169  movaps  xmm8, xmmword ptr [r11-30h]
0x14004516e  movaps  xmm9, xmmword ptr [r11-40h]
0x140045173  movaps  xmm10, xmmword ptr [r11-50h]
0x140045178  movaps  xmm11, xmmword ptr [r11-60h]
0x14004517d  mov     rsp, r11
0x140045180  pop     r15
0x140045182  pop     r14
0x140045184  pop     r13
0x140045186  pop     rdi
0x140045187  pop     rbp
0x140045188  retn
0x140045189  mov     r9d, eax; char *
0x14004518c  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045193  mov     edx, 0F8h; void *
0x140045198  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14004519e  mov     r9d, eax; char *
0x1400451a1  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400451a8  mov     edx, 0F0h; void *
0x1400451ad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400451b3  mov     r9d, eax; char *
0x1400451b6  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400451bd  mov     edx, 0F3h; void *
0x1400451c2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400451c8  mov     r9d, eax; char *
0x1400451cb  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400451d2  mov     edx, 0F4h; void *
0x1400451d7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400451dd  mov     ecx, eax; int
0x1400451df  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400451e5  mov     ecx, eax; int
0x1400451e7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400451ed  mov     ecx, eax; int
0x1400451ef  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400451f5  mov     ecx, eax; int
0x1400451f7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400451fd  mov     r9d, eax; char *
0x140045200  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045207  mov     edx, 0F7h; void *
0x14004520c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045212  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140045219  mov     edx, 15F3h; void *
0x14004521e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
