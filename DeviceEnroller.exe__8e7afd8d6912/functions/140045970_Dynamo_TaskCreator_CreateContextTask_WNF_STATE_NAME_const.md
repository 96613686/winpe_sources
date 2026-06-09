# Dynamo::TaskCreator::CreateContextTask(_WNF_STATE_NAME const *)

- ea: `0x140045970`
- end: `0x140045d79`
- name: `?CreateContextTask@TaskCreator@Dynamo@@UEAAXPEBU_WNF_STATE_NAME@@@Z`
- size: `1033`
- prototype: `void __fastcall(void **this, const struct _WNF_STATE_NAME *)`
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
- `0x140045754`
- `0x140045970`
- `0x140046bd8`
- `0x14005890c`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140045b8a`
- `OLEAUT32!__imp_SysAllocString` at `0x140045b8a`
- `OLEAUT32!__imp_SysFreeString` at `0x140045bd3`
- `OLEAUT32!__imp_SysFreeString` at `0x140045bd3`
- `OLEAUT32!__imp_VariantInit` at `0x140045a51`
- `OLEAUT32!__imp_VariantInit` at `0x140045a68`
- `OLEAUT32!__imp_VariantInit` at `0x140045a80`
- `OLEAUT32!__imp_VariantInit` at `0x140045a97`
- `OLEAUT32!__imp_VariantInit` at `0x140045a51`
- `OLEAUT32!__imp_VariantInit` at `0x140045a68`
- `OLEAUT32!__imp_VariantInit` at `0x140045a80`
- `OLEAUT32!__imp_VariantInit` at `0x140045a97`
- `OLEAUT32!__imp_VariantClear` at `0x140045b05`
- `OLEAUT32!__imp_VariantClear` at `0x140045b18`
- `OLEAUT32!__imp_VariantClear` at `0x140045b2b`
- `OLEAUT32!__imp_VariantClear` at `0x140045b3d`
- `OLEAUT32!__imp_VariantClear` at `0x140045b05`
- `OLEAUT32!__imp_VariantClear` at `0x140045b18`
- `OLEAUT32!__imp_VariantClear` at `0x140045b2b`
- `OLEAUT32!__imp_VariantClear` at `0x140045b3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045a2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045a2c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140045c7a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140045c7a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400459e2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400459e2`

## string_xrefs

- `0x140045d67`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140045b83`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">\n    <RegistrationInfo>\n        <Author>$(@%systemRoot%\system32\deviceenroller.exe,-101)</Author>\n        <Description>$(@%systemRoot%\system32\deviceenroller.exe,-104)</Description>\n        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>\n    </RegistrationInfo>\n    <Principals>\n        <Principal id="LocalSystem">\n            <UserId>S-1-5-18</UserId`
- `0x140045c1c`: `ContextTask`
- `0x140045cc9`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045ce1`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045cf6`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045d0b`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045d20`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x140045d55`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Dynamo::TaskCreator::CreateContextTask(void **this, const struct _WNF_STATE_NAME *a2)
{
  HRESULT v4; // eax
  ULONG v5; // ebx
  __int64 *v6; // rax
  HRESULT Instance; // eax
  struct ITaskService *v8; // rsi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rdi
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  __int64 v13; // xmm9_8
  __int128 v14; // xmm6
  __int64 v15; // xmm7_8
  int v16; // eax
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  int v21; // eax
  struct ITaskDefinition *v22; // rsi
  struct ITaskDefinitionVtbl *lpVtbl; // r13
  BSTR v24; // rax
  const char *v25; // r9
  OLECHAR *v26; // rdi
  int v27; // eax
  _QWORD *v28; // rax
  struct ITaskDefinition *v29; // rcx
  struct ITaskService *v30; // rcx
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  struct ITaskDefinition *v33; // [rsp+38h] [rbp-D0h] BYREF
  struct ITaskService *v34; // [rsp+40h] [rbp-C8h] BYREF
  VARIANTARG v35; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG v36; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG v37; // [rsp+78h] [rbp-90h] BYREF
  __int64 v38; // [rsp+90h] [rbp-78h]
  VARIANTARG pvarg; // [rsp+98h] [rbp-70h] BYREF
  BSTR v40; // [rsp+B0h] [rbp-58h]
  int v41[4]; // [rsp+B8h] [rbp-50h] BYREF
  IRecordInfo *v42; // [rsp+C8h] [rbp-40h]
  __int128 v43; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v44; // [rsp+E8h] [rbp-20h]
  __int128 v45; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v46; // [rsp+108h] [rbp+0h]
  __int128 Src; // [rsp+118h] [rbp+10h] BYREF
  __int64 v48; // [rsp+128h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  *(_DWORD *)&v35.vt = 0;
  if ( !a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x85,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)0x80070057LL,
      ppv);
  v4 = CoInitializeEx(0, 0);
  v5 = v4 >= 0;
  v35.decVal.Hi32 = v5;
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x87,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v34 = 0;
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>((__int64 *)&v34);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)v6);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8A,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
  v8 = v34;
  Connect = v34->lpVtbl->Connect;
  VariantInit(&pvarg);
  v10 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit((VARIANTARG *)&v37.decVal.8);
  v12 = *(_OWORD *)&v37.decVal.Lo32;
  v13 = v38;
  VariantInit((VARIANTARG *)&v36.decVal.8);
  v14 = *(_OWORD *)&v36.decVal.Lo32;
  v15 = *(_QWORD *)&v37.vt;
  VariantInit((VARIANTARG *)&v35.decVal.8);
  *(_OWORD *)v41 = v10;
  v42 = pRecInfo;
  v43 = v12;
  v44 = v13;
  v45 = v14;
  v46 = v15;
  Src = *(_OWORD *)&v35.decVal.Lo32;
  v48 = *(_QWORD *)&v36.vt;
  v16 = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *))Connect)(
          v8,
          &Src,
          &v45,
          &v43);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8B,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v16,
      (int)v41);
  v17 = VariantClear((VARIANTARG *)&v35.decVal.8);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v18 = VariantClear((VARIANTARG *)&v36.decVal.8);
  if ( v18 < 0 )
    _com_issue_error(v18);
  v19 = VariantClear((VARIANTARG *)&v37.decVal.8);
  if ( v19 < 0 )
    _com_issue_error(v19);
  v20 = VariantClear(&pvarg);
  if ( v20 < 0 )
    _com_issue_error(v20);
  v33 = 0;
  v21 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))v34->lpVtbl->NewTask)(
          v34,
          0,
          &v33);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8E,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v21,
      (int)v41);
  v22 = v33;
  lpVtbl = v33->lpVtbl;
  v24 = SysAllocString(
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
  v26 = v24;
  v40 = v24;
  *(_DWORD *)&v35.vt = 1;
  if ( !v24 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  v27 = ((__int64 (__fastcall *)(struct ITaskDefinition *, BSTR))lpVtbl->put_XmlText)(v22, v24);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8F,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v27,
      (int)v41);
  SysFreeString(v26);
  anonymous_namespace_::AddWnfTrigger(v33, a2);
  v28 = (_QWORD *)anonymous_namespace_::CreateCommandLine(&Src, this[1], this[2], 0);
  if ( v28[3] > 7u )
    v28 = (_QWORD *)*v28;
  anonymous_namespace_::AddCommandLine(v33, v28);
  std::wstring::~wstring((char **)&Src);
  Dynamo::TaskCreator::RegisterTask((Dynamo::TaskCreator *)this, v34, v33, L"ContextTask");
  v29 = v33;
  if ( v33 )
  {
    v33 = 0;
    ((void (__fastcall *)(struct ITaskDefinition *))v29->lpVtbl->Release)(v29);
  }
  v30 = v34;
  if ( v34 )
  {
    v34 = 0;
    ((void (__fastcall *)(struct ITaskService *))v30->lpVtbl->Release)(v30);
  }
  if ( v5 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140045970  mov     rax, rsp
0x140045973  mov     [rax+18h], rbx
0x140045977  mov     [rax+20h], rsi
0x14004597b  push    rbp
0x14004597c  push    rdi
0x14004597d  push    r13
0x14004597f  push    r14
0x140045981  push    r15
0x140045983  lea     rbp, [rax-0C8h]
0x14004598a  sub     rsp, 1A0h
0x140045991  movaps  xmmword ptr [rax-38h], xmm6
0x140045995  movaps  xmmword ptr [rax-48h], xmm7
0x140045999  movaps  xmmword ptr [rax-58h], xmm8
0x14004599e  movaps  xmmword ptr [rax-68h], xmm9
0x1400459a3  movaps  xmmword ptr [rax-78h], xmm10
0x1400459a8  movaps  xmmword ptr [rax-88h], xmm11
0x1400459b0  mov     rax, cs:__security_cookie
0x1400459b7  xor     rax, rsp
0x1400459ba  mov     [rbp+0C0h+var_90], rax
0x1400459be  mov     r15, rdx
0x1400459c1  mov     r14, rcx
0x1400459c4  mov     dword ptr [rsp+1C0h+var_180], 0
0x1400459cc  mov     rcx, [rbp+0C8h]; this
0x1400459d3  test    rdx, rdx
0x1400459d6  jz      loc_140045CDB
0x1400459dc  xor     ebx, ebx
0x1400459de  xor     edx, edx; dwCoInit
0x1400459e0  xor     ecx, ecx; pvReserved
0x1400459e2  call    cs:__imp_CoInitializeEx
0x1400459e8  lea     edi, [rbx+1]
0x1400459eb  test    eax, eax
0x1400459ed  cmovns  ebx, edi
0x1400459f0  mov     dword ptr [rsp+1C0h+var_180+4], ebx
0x1400459f4  mov     rcx, [rbp+0C8h]; this
0x1400459fb  js      loc_140045CF3
0x140045a01  mov     [rsp+1C0h+var_188], 0
0x140045a0a  lea     rcx, [rsp+1C0h+var_188]
0x140045a0f  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UITaskService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ITaskService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITaskService>>)
0x140045a14  mov     qword ptr [rsp+1C0h+ppv], rax; int
0x140045a19  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140045a20  mov     r8d, edi; dwClsContext
0x140045a23  xor     edx, edx; pUnkOuter
0x140045a25  lea     rcx, CLSID_TaskScheduler; rclsid
0x140045a2c  call    cs:__imp_CoCreateInstance
0x140045a32  mov     rcx, [rbp+0C8h]; this
0x140045a39  test    eax, eax
0x140045a3b  js      loc_140045D08
0x140045a41  mov     rsi, [rsp+1C0h+var_188]
0x140045a46  mov     rax, [rsi]
0x140045a49  mov     rdi, [rax+50h]
0x140045a4d  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x140045a51  call    cs:__imp_VariantInit
0x140045a57  nop
0x140045a58  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x140045a5d  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x140045a63  lea     rcx, [rsp+1C0h+var_150+8]; pvarg
0x140045a68  call    cs:__imp_VariantInit
0x140045a6e  nop
0x140045a6f  movups  xmm8, xmmword ptr [rsp+1C0h+var_150+8]
0x140045a75  movsd   xmm9, [rbp+0C0h+var_138]
0x140045a7b  lea     rcx, [rsp+1C0h+var_168+8]; pvarg
0x140045a80  call    cs:__imp_VariantInit
0x140045a86  nop
0x140045a87  movups  xmm6, xmmword ptr [rsp+1C0h+var_168+8]
0x140045a8c  movsd   xmm7, qword ptr [rsp+1C0h+var_150]
0x140045a92  lea     rcx, [rsp+1C0h+var_180+8]; pvarg
0x140045a97  call    cs:__imp_VariantInit
0x140045a9d  nop
0x140045a9e  movups  xmm0, xmmword ptr [rsp+1C0h+var_180+8]
0x140045aa3  movsd   xmm1, qword ptr [rsp+1C0h+var_168]
0x140045aa9  movaps  xmmword ptr [rbp+0C0h+var_110], xmm10
0x140045aae  movsd   [rbp+0C0h+var_100], xmm11
0x140045ab4  movaps  [rbp+0C0h+var_F0], xmm8
0x140045ab9  movsd   [rbp+0C0h+var_E0], xmm9
0x140045abf  movaps  [rbp+0C0h+var_D0], xmm6
0x140045ac3  movsd   [rbp+0C0h+var_C0], xmm7
0x140045ac8  movaps  [rbp+0C0h+Src], xmm0
0x140045acc  movsd   [rbp+0C0h+var_A0], xmm1
0x140045ad1  lea     rax, [rbp+0C0h+var_110]
0x140045ad5  mov     qword ptr [rsp+1C0h+ppv], rax; int
0x140045ada  lea     r9, [rbp+0C0h+var_F0]
0x140045ade  lea     r8, [rbp+0C0h+var_D0]
0x140045ae2  lea     rdx, [rbp+0C0h+Src]
0x140045ae6  mov     rcx, rsi
0x140045ae9  mov     rax, rdi
0x140045aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045af1  mov     rcx, [rbp+0C8h]; this
0x140045af8  test    eax, eax
0x140045afa  js      loc_140045D1D
0x140045b00  lea     rcx, [rsp+1C0h+var_180+8]; pvarg
0x140045b05  call    cs:__imp_VariantClear
0x140045b0b  test    eax, eax
0x140045b0d  js      loc_140045D32
0x140045b13  lea     rcx, [rsp+1C0h+var_168+8]; pvarg
0x140045b18  call    cs:__imp_VariantClear
0x140045b1e  test    eax, eax
0x140045b20  js      loc_140045D3A
0x140045b26  lea     rcx, [rsp+1C0h+var_150+8]; pvarg
0x140045b2b  call    cs:__imp_VariantClear
0x140045b31  test    eax, eax
0x140045b33  js      loc_140045D42
0x140045b39  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x140045b3d  call    cs:__imp_VariantClear
0x140045b43  test    eax, eax
0x140045b45  js      loc_140045D4A
0x140045b4b  mov     [rsp+1C0h+var_190], 0
0x140045b54  mov     rcx, [rsp+1C0h+var_188]
0x140045b59  mov     rax, [rcx]
0x140045b5c  lea     r8, [rsp+1C0h+var_190]
0x140045b61  xor     edx, edx
0x140045b63  mov     rax, [rax+48h]
0x140045b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045b6c  mov     rcx, [rbp+0C8h]; this
0x140045b73  test    eax, eax
0x140045b75  js      loc_140045D52
0x140045b7b  mov     rsi, [rsp+1C0h+var_190]
0x140045b80  mov     r13, [rsi]
0x140045b83  lea     rcx, aTaskXmlnsHttpS_0; "<Task xmlns=\"http://schemas.microsoft."...
0x140045b8a  call    cs:__imp_SysAllocString
0x140045b90  mov     rdi, rax
0x140045b93  mov     [rbp+0C0h+var_118], rax
0x140045b97  mov     dword ptr [rsp+1C0h+var_180], 1
0x140045b9f  mov     rcx, [rbp+0C8h]; this
0x140045ba6  test    rax, rax
0x140045ba9  jz      loc_140045D67
0x140045baf  mov     rdx, rax
0x140045bb2  mov     rcx, rsi
0x140045bb5  mov     rax, [r13+0A0h]
0x140045bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045bc1  mov     rcx, [rbp+0C8h]; this
0x140045bc8  test    eax, eax
0x140045bca  js      loc_140045CC6
0x140045bd0  mov     rcx, rdi; bstrString
0x140045bd3  call    cs:__imp_SysFreeString
0x140045bd9  mov     rdx, r15
0x140045bdc  mov     rcx, [rsp+1C0h+var_190]
0x140045be1  call    _anonymous_namespace___AddWnfTrigger
0x140045be6  xor     r9d, r9d; void *
0x140045be9  mov     r8, [r14+10h]; void *
0x140045bed  mov     rdx, [r14+8]; void *
0x140045bf1  lea     rcx, [rbp+0C0h+Src]; Src
0x140045bf5  call    _anonymous_namespace___CreateCommandLine
0x140045bfa  nop
0x140045bfb  cmp     qword ptr [rax+18h], 7
0x140045c00  jbe     short loc_140045C05
0x140045c02  mov     rax, [rax]
0x140045c05  mov     rdx, rax
0x140045c08  mov     rcx, [rsp+1C0h+var_190]
0x140045c0d  call    _anonymous_namespace___AddCommandLine
0x140045c12  nop
0x140045c13  lea     rcx, [rbp+0C0h+Src]
0x140045c17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045c1c  lea     r9, aContexttask; "ContextTask"
0x140045c23  mov     r8, [rsp+1C0h+var_190]; struct ITaskDefinition *
0x140045c28  mov     rdx, [rsp+1C0h+var_188]; struct ITaskService *
0x140045c2d  mov     rcx, r14; this
0x140045c30  call    ?RegisterTask@TaskCreator@Dynamo@@AEAAXPEAUITaskService@@PEAUITaskDefinition@@PEBG@Z; Dynamo::TaskCreator::RegisterTask(ITaskService *,ITaskDefinition *,ushort const *)
0x140045c35  nop
0x140045c36  mov     rcx, [rsp+1C0h+var_190]
0x140045c3b  test    rcx, rcx
0x140045c3e  jz      short loc_140045C56
0x140045c40  mov     [rsp+1C0h+var_190], 0
0x140045c49  mov     rax, [rcx]
0x140045c4c  mov     rax, [rax+10h]
0x140045c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045c55  nop
0x140045c56  mov     rcx, [rsp+1C0h+var_188]
0x140045c5b  test    rcx, rcx
0x140045c5e  jz      short loc_140045C76
0x140045c60  mov     [rsp+1C0h+var_188], 0
0x140045c69  mov     rax, [rcx]
0x140045c6c  mov     rax, [rax+10h]
0x140045c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045c75  nop
0x140045c76  test    ebx, ebx
0x140045c78  jz      short loc_140045C80
0x140045c7a  call    cs:__imp_CoUninitialize
0x140045c80  mov     rcx, [rbp+0C0h+var_90]
0x140045c84  xor     rcx, rsp; StackCookie
0x140045c87  call    __security_check_cookie
0x140045c8c  lea     r11, [rsp+1C0h+var_20]
0x140045c94  mov     rbx, [r11+40h]
0x140045c98  mov     rsi, [r11+48h]
0x140045c9c  movaps  xmm6, xmmword ptr [r11-10h]
0x140045ca1  movaps  xmm7, xmmword ptr [r11-20h]
0x140045ca6  movaps  xmm8, xmmword ptr [r11-30h]
0x140045cab  movaps  xmm9, xmmword ptr [r11-40h]
0x140045cb0  movaps  xmm10, xmmword ptr [r11-50h]
0x140045cb5  movaps  xmm11, xmmword ptr [r11-60h]
0x140045cba  mov     rsp, r11
0x140045cbd  pop     r15
0x140045cbf  pop     r14
0x140045cc1  pop     r13
0x140045cc3  pop     rdi
0x140045cc4  pop     rbp
0x140045cc5  retn
0x140045cc6  mov     r9d, eax; char *
0x140045cc9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045cd0  mov     edx, 8Fh; void *
0x140045cd5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045cdb  mov     r9d, 80070057h; char *
0x140045ce1  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045ce8  mov     edx, 85h; void *
0x140045ced  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045cf3  mov     r9d, eax; char *
0x140045cf6  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045cfd  mov     edx, 87h; void *
0x140045d02  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045d08  mov     r9d, eax; char *
0x140045d0b  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045d12  mov     edx, 8Ah; void *
0x140045d17  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045d1d  mov     r9d, eax; char *
0x140045d20  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045d27  mov     edx, 8Bh; void *
0x140045d2c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045d32  mov     ecx, eax; int
0x140045d34  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140045d3a  mov     ecx, eax; int
0x140045d3c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140045d42  mov     ecx, eax; int
0x140045d44  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140045d4a  mov     ecx, eax; int
0x140045d4c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140045d52  mov     r9d, eax; char *
0x140045d55  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140045d5c  mov     edx, 8Eh; void *
0x140045d61  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140045d67  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140045d6e  mov     edx, 15F3h; void *
0x140045d73  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
