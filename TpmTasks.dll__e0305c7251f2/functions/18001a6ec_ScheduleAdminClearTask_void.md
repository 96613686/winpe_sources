# ScheduleAdminClearTask(void)

- ea: `0x18001a6ec`
- end: `0x18001aa15`
- name: `?ScheduleAdminClearTask@@YAJXZ`
- size: `809`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f8ac`

## callees

- `0x18000de18`
- `0x18001a6ec`
- `0x18005e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001a729`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a739`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a729`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a739`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a9a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a9b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a9a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a9b6`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7b9`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7d0`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7e9`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7ff`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8d0`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8e9`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8ff`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7b9`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7d0`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7e9`
- `OLEAUT32!__imp_VariantInit` at `0x18001a7ff`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8d0`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8e9`
- `OLEAUT32!__imp_VariantInit` at `0x18001a8ff`
- `OLEAUT32!__imp_VariantClear` at `0x18001a862`
- `OLEAUT32!__imp_VariantClear` at `0x18001a86e`
- `OLEAUT32!__imp_VariantClear` at `0x18001a87a`
- `OLEAUT32!__imp_VariantClear` at `0x18001a885`
- `OLEAUT32!__imp_VariantClear` at `0x18001a97c`
- `OLEAUT32!__imp_VariantClear` at `0x18001a988`
- `OLEAUT32!__imp_VariantClear` at `0x18001a994`
- `OLEAUT32!__imp_VariantClear` at `0x18001a862`
- `OLEAUT32!__imp_VariantClear` at `0x18001a86e`
- `OLEAUT32!__imp_VariantClear` at `0x18001a87a`
- `OLEAUT32!__imp_VariantClear` at `0x18001a885`
- `OLEAUT32!__imp_VariantClear` at `0x18001a97c`
- `OLEAUT32!__imp_VariantClear` at `0x18001a988`
- `OLEAUT32!__imp_VariantClear` at `0x18001a994`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a767`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001a767`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a797`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a797`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001a99a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001a99a`

## string_xrefs

- `0x18001a732`: `ClearTPMIfNotReady`
- `0x18001a961`: `<?xml version="1.0" encoding="UTF-16"?><Task version="1.2" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">  <RegistrationInfo>    <Date>2017-05-16T18:14:10.8490227</Date>    <Author>$(@%SystemRoot%\system32\TpmTasks.dll,-600)</Author>    <Source>$(@%SystemRoot%\system32\TpmTasks.dll,-601)</Source>    <URI>\Microsoft\Windows\TPM\ClearTPMIfNotReady</URI>  </RegistrationInfo>  <Triggers>    <LogonTrigger>      <Enabled>true</Enabled>      <Delay>PT1M</Delay>    </LogonTrigger>  </Tri`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 ScheduleAdminClearTask(void)
{
  OLECHAR *v0; // rsi
  OLECHAR *v1; // r14
  HRESULT v2; // edi
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, VARIANTARG *, __int128 *, VARIANTARG *, __int128 *); // rbx
  __int128 v5; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v7; // xmm8
  IRecordInfo *v8; // xmm9_8
  __int128 v9; // xmm6
  IRecordInfo *v10; // xmm7_8
  __int64 v11; // rdi
  __int64 (*v12)(__int64, OLECHAR *, const wchar_t *, ...); // rbx
  __int128 v13; // xmm8
  IRecordInfo *v14; // xmm9_8
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  VARIANTARG v18; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v19; // [rsp+68h] [rbp-A0h] BYREF
  IRecordInfo *v20; // [rsp+80h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v22; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v23; // [rsp+C8h] [rbp-40h] BYREF
  IRecordInfo *v24; // [rsp+D8h] [rbp-30h]
  VARIANTARG v25; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG v26; // [rsp+108h] [rbp+0h] BYREF
  __int128 v27; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v28; // [rsp+138h] [rbp+30h]
  LPVOID ppv; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v30; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v31; // [rsp+1E8h] [rbp+E0h] BYREF

  v0 = SysAllocString(L"\\Microsoft\\Windows\\TPM");
  v1 = SysAllocString(L"ClearTPMIfNotReady");
  ppv = 0;
  v30 = 0;
  v31 = 0;
  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    if ( v2 >= 0 )
    {
      v3 = ppv;
      v4 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, VARIANTARG *, __int128 *))(*(_QWORD *)ppv + 80LL);
      VariantInit(&pvarg);
      v5 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit((VARIANTARG *)&v19.decVal.8);
      v7 = *(_OWORD *)&v19.decVal.Lo32;
      v8 = v20;
      VariantInit((VARIANTARG *)&v18.decVal.8);
      v9 = *(_OWORD *)&v18.decVal.Lo32;
      v10 = *(IRecordInfo **)&v19.vt;
      VariantInit(&v26);
      v27 = v5;
      v28 = pRecInfo;
      *(_OWORD *)&v22.vt = v7;
      v22.pRecInfo = v8;
      v23 = v9;
      v24 = v10;
      v25 = v26;
      v2 = v4(v3, &v25, &v23, &v22, &v27);
      VariantClear(&v26);
      VariantClear((VARIANTARG *)&v18.decVal.8);
      VariantClear((VARIANTARG *)&v19.decVal.8);
      VariantClear(&pvarg);
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v0, &v30);
        if ( v2 >= 0 )
        {
          v11 = v30;
          v12 = *(__int64 (**)(__int64, OLECHAR *, const wchar_t *, ...))(*(_QWORD *)v30 + 128LL);
          VariantInit((VARIANTARG *)&v18.decVal.8);
          v13 = *(_OWORD *)&v18.decVal.Lo32;
          v14 = *(IRecordInfo **)&v19.vt;
          VariantInit((VARIANTARG *)&v19.decVal.8);
          v15 = *(_OWORD *)&v19.decVal.Lo32;
          v16 = v20;
          VariantInit(&pvarg);
          *(_OWORD *)&v25.vt = v13;
          v25.pRecInfo = v14;
          v23 = v15;
          v24 = v16;
          v22 = pvarg;
          v2 = v12(
                 v11,
                 v1,
                 L"<?xml version=\"1.0\" encoding=\"UTF-16\"?><Task version=\"1.2\" xmlns=\"http://schemas.microsoft.com/w"
                  "indows/2004/02/mit/task\">  <RegistrationInfo>    <Date>2017-05-16T18:14:10.8490227</Date>    <Author>"
                  "$(@%SystemRoot%\\system32\\TpmTasks.dll,-600)</Author>    <Source>$(@%SystemRoot%\\system32\\TpmTasks."
                  "dll,-601)</Source>    <URI>\\Microsoft\\Windows\\TPM\\ClearTPMIfNotReady</URI>  </RegistrationInfo>  <"
                  "Triggers>    <LogonTrigger>      <Enabled>true</Enabled>      <Delay>PT1M</Delay>    </LogonTrigger>  "
                  "</Triggers>  <Principals>    <Principal id=\"Author\">      <GroupId>S-1-5-32-544</GroupId>      <RunL"
                  "evel>HighestAvailable</RunLevel>    </Principal>  </Principals>  <Settings>    <IdleSettings>      <St"
                  "opOnIdleEnd>false</StopOnIdleEnd>    </IdleSettings>    <MultipleInstancesPolicy>IgnoreNew</MultipleIn"
                  "stancesPolicy>    <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>    <StopIfGoingOnBatt"
                  "eries>false</StopIfGoingOnBatteries>    <AllowHardTerminate>true</AllowHardTerminate>    <StartWhenAva"
                  "ilable>true</StartWhenAvailable>    <AllowStartOnDemand>false</AllowStartOnDemand>    <Enabled>true</E"
                  "nabled>    <Hidden>true</Hidden>    <RunOnlyIfIdle>false</RunOnlyIfIdle>    <WakeToRun>false</WakeToRu"
                  "n>    <ExecutionTimeLimit>PT72H</ExecutionTimeLimit>    <Priority>7</Priority>  </Settings>  <Actions "
                  "Context=\"Author\">    <Exec>      <Command>tpminit.exe</Command>      <Arguments>/cleartpmbypolicy</A"
                  "rguments>    </Exec>    <Exec>      <Command>schtasks.exe</Command>      <Arguments>/delete /f /tn \\M"
                  "icrosoft\\Windows\\TPM\\ClearTPMIfNotReady</Arguments>    </Exec>  </Actions></Task>",
                 6,
                 &v22,
                 &v23,
                 3,
                 &v25,
                 &v31);
          VariantClear(&pvarg);
          VariantClear((VARIANTARG *)&v19.decVal.8);
          VariantClear((VARIANTARG *)&v18.decVal.8);
        }
      }
    }
    CoUninitialize();
  }
  if ( v0 )
    SysFreeString(v0);
  if ( v1 )
    SysFreeString(v1);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v31);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v30);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001a6ec  mov     rax, rsp
0x18001a6ef  push    rbp
0x18001a6f0  push    rbx
0x18001a6f1  push    rsi
0x18001a6f2  push    rdi
0x18001a6f3  push    r14
0x18001a6f5  lea     rbp, [rax-0C8h]
0x18001a6fc  sub     rsp, 1A0h
0x18001a703  movaps  xmmword ptr [rax-38h], xmm6
0x18001a707  movaps  xmmword ptr [rax-48h], xmm7
0x18001a70b  movaps  xmmword ptr [rax-58h], xmm8
0x18001a710  movaps  xmmword ptr [rax-68h], xmm9
0x18001a715  movaps  xmmword ptr [rax-78h], xmm10
0x18001a71a  movaps  xmmword ptr [rax-88h], xmm11
0x18001a722  lea     rcx, psz; "\\Microsoft\\Windows\\TPM"
0x18001a729  call    cs:__imp_SysAllocString
0x18001a72f  mov     rsi, rax
0x18001a732  lea     rcx, aCleartpmifnotr; "ClearTPMIfNotReady"
0x18001a739  call    cs:__imp_SysAllocString
0x18001a73f  mov     r14, rax
0x18001a742  mov     [rbp+0C0h+arg_0], 0
0x18001a74d  mov     [rbp+0C0h+arg_8], 0
0x18001a758  mov     [rbp+0C0h+arg_10], 0
0x18001a763  xor     edx, edx; dwCoInit
0x18001a765  xor     ecx, ecx; pvReserved
0x18001a767  call    cs:__imp_CoInitializeEx
0x18001a76d  mov     edi, eax
0x18001a76f  test    eax, eax
0x18001a771  js      loc_18001A9A0
0x18001a777  lea     rax, [rbp+0C0h+arg_0]
0x18001a77e  mov     [rsp+1C0h+ppv], rax; ppv
0x18001a783  lea     r9, IID_ITaskService; riid
0x18001a78a  xor     edx, edx; pUnkOuter
0x18001a78c  lea     r8d, [rdx+1]; dwClsContext
0x18001a790  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001a797  call    cs:__imp_CoCreateInstance
0x18001a79d  mov     edi, eax
0x18001a79f  test    eax, eax
0x18001a7a1  js      loc_18001A99A
0x18001a7a7  mov     rdi, [rbp+0C0h+arg_0]
0x18001a7ae  mov     rax, [rdi]
0x18001a7b1  mov     rbx, [rax+50h]
0x18001a7b5  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x18001a7b9  call    cs:__imp_VariantInit
0x18001a7bf  nop
0x18001a7c0  movups  xmm10, xmmword ptr [rbp+0C0h+pvarg]
0x18001a7c5  movsd   xmm11, qword ptr [rbp+0C0h+pvarg+10h]
0x18001a7cb  lea     rcx, [rsp+1C0h+var_160+8]; pvarg
0x18001a7d0  call    cs:__imp_VariantInit
0x18001a7d6  nop
0x18001a7d7  movups  xmm8, xmmword ptr [rsp+1C0h+var_160+8]
0x18001a7dd  movsd   xmm9, [rsp+1C0h+var_148]
0x18001a7e4  lea     rcx, [rsp+1C0h+var_178+8]; pvarg
0x18001a7e9  call    cs:__imp_VariantInit
0x18001a7ef  nop
0x18001a7f0  movups  xmm6, xmmword ptr [rsp+1C0h+var_178+8]
0x18001a7f5  movsd   xmm7, qword ptr [rsp+1C0h+var_160]
0x18001a7fb  lea     rcx, [rbp+0C0h+var_C0]; pvarg
0x18001a7ff  call    cs:__imp_VariantInit
0x18001a805  nop
0x18001a806  movups  xmm0, xmmword ptr [rbp+0C0h+var_C0]
0x18001a80a  movsd   xmm1, qword ptr [rbp+0C0h+var_C0+10h]
0x18001a80f  movaps  [rbp+0C0h+var_A0], xmm10
0x18001a814  movsd   [rbp+0C0h+var_90], xmm11
0x18001a81a  movaps  [rbp+0C0h+var_120], xmm8
0x18001a81f  movsd   [rbp+0C0h+var_110], xmm9
0x18001a825  movaps  [rbp+0C0h+var_100], xmm6
0x18001a829  movsd   [rbp+0C0h+var_F0], xmm7
0x18001a82e  movaps  [rbp+0C0h+var_E0], xmm0
0x18001a832  movsd   [rbp+0C0h+var_D0], xmm1
0x18001a837  lea     rax, [rbp+0C0h+var_A0]
0x18001a83b  mov     [rsp+1C0h+ppv], rax
0x18001a840  lea     r9, [rbp+0C0h+var_120]
0x18001a844  lea     r8, [rbp+0C0h+var_100]
0x18001a848  lea     rdx, [rbp+0C0h+var_E0]
0x18001a84c  mov     rcx, rdi
0x18001a84f  mov     rax, rbx
0x18001a852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a857  mov     edi, eax
0x18001a859  mov     ebx, eax
0x18001a85b  shr     ebx, 1Fh
0x18001a85e  lea     rcx, [rbp+0C0h+var_C0]; pvarg
0x18001a862  call    cs:__imp_VariantClear
0x18001a868  nop
0x18001a869  lea     rcx, [rsp+1C0h+var_178+8]; pvarg
0x18001a86e  call    cs:__imp_VariantClear
0x18001a874  nop
0x18001a875  lea     rcx, [rsp+1C0h+var_160+8]; pvarg
0x18001a87a  call    cs:__imp_VariantClear
0x18001a880  nop
0x18001a881  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x18001a885  call    cs:__imp_VariantClear
0x18001a88b  test    bl, bl
0x18001a88d  jnz     loc_18001A99A
0x18001a893  mov     rcx, [rbp+0C0h+arg_0]
0x18001a89a  mov     rax, [rcx]
0x18001a89d  lea     r8, [rbp+0C0h+arg_8]
0x18001a8a4  mov     rdx, rsi
0x18001a8a7  mov     rax, [rax+38h]
0x18001a8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8b0  mov     edi, eax
0x18001a8b2  test    eax, eax
0x18001a8b4  js      loc_18001A99A
0x18001a8ba  mov     rdi, [rbp+0C0h+arg_8]
0x18001a8c1  mov     rax, [rdi]
0x18001a8c4  mov     rbx, [rax+80h]
0x18001a8cb  lea     rcx, [rsp+1C0h+var_178+8]; pvarg
0x18001a8d0  call    cs:__imp_VariantInit
0x18001a8d6  nop
0x18001a8d7  movups  xmm8, xmmword ptr [rsp+1C0h+var_178+8]
0x18001a8dd  movsd   xmm9, qword ptr [rsp+1C0h+var_160]
0x18001a8e4  lea     rcx, [rsp+1C0h+var_160+8]; pvarg
0x18001a8e9  call    cs:__imp_VariantInit
0x18001a8ef  nop
0x18001a8f0  movups  xmm6, xmmword ptr [rsp+1C0h+var_160+8]
0x18001a8f5  movsd   xmm7, [rsp+1C0h+var_148]
0x18001a8fb  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x18001a8ff  call    cs:__imp_VariantInit
0x18001a905  nop
0x18001a906  movups  xmm0, xmmword ptr [rbp+0C0h+pvarg]
0x18001a90a  movsd   xmm1, qword ptr [rbp+0C0h+pvarg+10h]
0x18001a90f  movaps  [rbp+0C0h+var_E0], xmm8
0x18001a914  movsd   [rbp+0C0h+var_D0], xmm9
0x18001a91a  movaps  [rbp+0C0h+var_100], xmm6
0x18001a91e  movsd   [rbp+0C0h+var_F0], xmm7
0x18001a923  movaps  [rbp+0C0h+var_120], xmm0
0x18001a927  movsd   [rbp+0C0h+var_110], xmm1
0x18001a92c  lea     rax, [rbp+0C0h+arg_10]
0x18001a933  mov     [rsp+1C0h+var_180], rax
0x18001a938  lea     rax, [rbp+0C0h+var_E0]
0x18001a93c  mov     [rsp+1C0h+var_188], rax
0x18001a941  mov     dword ptr [rsp+1C0h+var_190], 3
0x18001a949  lea     rax, [rbp+0C0h+var_100]
0x18001a94d  mov     qword ptr [rsp+1C0h+var_198], rax
0x18001a952  lea     rax, [rbp+0C0h+var_120]
0x18001a956  mov     [rsp+1C0h+ppv], rax
0x18001a95b  mov     r9d, 6
0x18001a961  lea     r8, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x18001a968  mov     rdx, r14
0x18001a96b  mov     rcx, rdi
0x18001a96e  mov     rax, rbx
0x18001a971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a976  mov     edi, eax
0x18001a978  lea     rcx, [rbp+0C0h+pvarg]; pvarg
0x18001a97c  call    cs:__imp_VariantClear
0x18001a982  nop
0x18001a983  lea     rcx, [rsp+1C0h+var_160+8]; pvarg
0x18001a988  call    cs:__imp_VariantClear
0x18001a98e  nop
0x18001a98f  lea     rcx, [rsp+1C0h+var_178+8]; pvarg
0x18001a994  call    cs:__imp_VariantClear
0x18001a99a  call    cs:__imp_CoUninitialize
0x18001a9a0  test    rsi, rsi
0x18001a9a3  jz      short loc_18001A9AE
0x18001a9a5  mov     rcx, rsi; bstrString
0x18001a9a8  call    cs:__imp_SysFreeString
0x18001a9ae  test    r14, r14
0x18001a9b1  jz      short loc_18001A9BD
0x18001a9b3  mov     rcx, r14; bstrString
0x18001a9b6  call    cs:__imp_SysFreeString
0x18001a9bc  nop
0x18001a9bd  lea     rcx, [rbp+0C0h+arg_10]
0x18001a9c4  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x18001a9c9  nop
0x18001a9ca  lea     rcx, [rbp+0C0h+arg_8]
0x18001a9d1  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x18001a9d6  nop
0x18001a9d7  lea     rcx, [rbp+0C0h+arg_0]
0x18001a9de  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x18001a9e3  mov     eax, edi
0x18001a9e5  lea     r11, [rsp+1C0h+var_20]
0x18001a9ed  movaps  xmm6, xmmword ptr [r11-10h]
0x18001a9f2  movaps  xmm7, xmmword ptr [r11-20h]
0x18001a9f7  movaps  xmm8, xmmword ptr [r11-30h]
0x18001a9fc  movaps  xmm9, xmmword ptr [r11-40h]
0x18001aa01  movaps  xmm10, xmmword ptr [r11-50h]
0x18001aa06  movaps  xmm11, xmmword ptr [r11-60h]
0x18001aa0b  mov     rsp, r11
0x18001aa0e  pop     r14
0x18001aa10  pop     rdi
0x18001aa11  pop     rsi
0x18001aa12  pop     rbx
0x18001aa13  pop     rbp
0x18001aa14  retn
```
