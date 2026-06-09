# CUpdateDeploymentJob::DeployUpdates(void)

- ea: `0x18002cdd4`
- end: `0x18002cfb8`
- name: `?DeployUpdates@CUpdateDeploymentJob@@AEAAJXZ`
- size: `484`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002cd70`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x180007b9c`
- `0x1800110fc`
- `0x180011b44`
- `0x180018400`
- `0x180029e8c`
- `0x180029fac`
- `0x18002a1c0`
- `0x18002cdd4`
- `0x18002cfc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002cf98`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002cf98`

## string_xrefs

- `0x18002ce9b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x18002ce73`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002ceea`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002cf7e`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002ce12`: `Deployment job Id %ws : Beginning deployment of updates, CallerId = %ws.`
- `0x18002cf42`: `Deployment job Id %ws : Ending deployment for updates, CallerId = %ws, Exit code = 0x%08lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUpdateDeploymentJob::DeployUpdates(struct _GUID *this)
{
  unsigned int v2; // edx
  int v3; // edi
  __int64 v4; // rdx
  int v5; // eax
  int v6; // eax
  int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  int v12; // [rsp+20h] [rbp-98h]
  _BYTE v13[80]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v15; // [rsp+C0h] [rbp+8h] BYREF

  v15 = 0;
  Trace::GuidToString::GuidToString((Trace::GuidToString *)v13, this + 1);
  WUTrace(0, 0, 0x1000000, 4, 0, L"Deployment job Id %ws : Beginning deployment of updates, CallerId = %ws.");
  v3 = CCoInit::Initialize((CCoInit *)&v15, v2, 1);
  if ( v3 < 0 )
  {
    v4 = 2371;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v3,
      v12);
    goto LABEL_24;
  }
  v5 = CUpdateDeploymentJob::DeployUpdatesInternal((CUpdateDeploymentJob *)this);
  v3 = v5;
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x947,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v5,
      v12);
  v6 = *(_DWORD *)&this[25].Data4[4];
  if ( !v6 )
  {
    v7 = -2145120257;
    v8 = 2149847039LL;
    v9 = 903;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)v8,
      v12);
    goto LABEL_13;
  }
  if ( v6 != 3 )
  {
    v10 = CUHHandlerManager::ReleaseRemoteProcess((CUHHandlerManager *)&this[3]);
    v7 = v10;
    if ( v10 < 0 )
    {
      v8 = (unsigned int)v10;
      v9 = 905;
      goto LABEL_7;
    }
    *(_DWORD *)&this[25].Data4[4] = 3;
  }
  v7 = 0;
LABEL_13:
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x948,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v7,
      v12);
  if ( v3 < 0 )
  {
    if ( v3 == -2145124341 )
      CUpdateDeploymentJob::OnJobAborted((CUpdateDeploymentJob *)this);
    else
      CUpdateDeploymentJob::OnJobFailure((CUpdateDeploymentJob *)this, v3);
  }
  else
  {
    CUpdateDeploymentJob::OnJobComplete((CUpdateDeploymentJob *)this);
  }
  Trace::GuidToString::GuidToString((Trace::GuidToString *)v13, this + 1);
  WUTrace(
    0,
    0,
    0x1000000,
    4,
    0,
    L"Deployment job Id %ws : Ending deployment for updates, CallerId = %ws, Exit code = 0x%08lX");
  if ( v3 < 0 )
  {
    v4 = 2398;
    goto LABEL_22;
  }
  v3 = 0;
LABEL_24:
  if ( v15 )
    CoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002cdd4  mov     rax, rsp
0x18002cdd7  mov     [rax+10h], rbx
0x18002cddb  mov     [rax+18h], rbp
0x18002cddf  push    rsi
0x18002cde0  push    rdi
0x18002cde1  push    r14
0x18002cde3  sub     rsp, 0A0h
0x18002cdea  mov     rsi, rcx
0x18002cded  mov     dword ptr [rax+8], 0
0x18002cdf4  mov     rbx, [rcx+2A8h]
0x18002cdfb  lea     rdx, [rcx+10h]; struct _GUID *
0x18002cdff  lea     rcx, [rax-68h]; this
0x18002ce03  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002ce08  mov     [rsp+0B8h+var_80], rbx
0x18002ce0d  mov     [rsp+0B8h+var_88], rax
0x18002ce12  lea     rax, aDeploymentJobI_22; "Deployment job Id %ws : Beginning deplo"...
0x18002ce19  mov     [rsp+0B8h+var_90], rax
0x18002ce1e  mov     qword ptr [rsp+0B8h+var_98], 0; int
0x18002ce27  xor     edx, edx
0x18002ce29  xor     ecx, ecx
0x18002ce2b  lea     r9d, [rdx+4]
0x18002ce2f  mov     r8d, 1000000h
0x18002ce35  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002ce3a  mov     r8b, 1; bool
0x18002ce3d  lea     rcx, [rsp+0B8h+arg_0]; this
0x18002ce45  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x18002ce4a  mov     edi, eax
0x18002ce4c  test    eax, eax
0x18002ce4e  jns     short loc_18002CE5A
0x18002ce50  mov     edx, 943h
0x18002ce55  jmp     loc_18002CF73
0x18002ce5a  mov     rcx, rsi; this
0x18002ce5d  call    ?DeployUpdatesInternal@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::DeployUpdatesInternal(void)
0x18002ce62  mov     edi, eax
0x18002ce64  mov     rcx, [rsp+0B8h]; this
0x18002ce6c  test    eax, eax
0x18002ce6e  jns     short loc_18002CE84
0x18002ce70  mov     r9d, eax; char *
0x18002ce73  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002ce7a  mov     edx, 947h; void *
0x18002ce7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ce84  mov     eax, [rsi+19Ch]
0x18002ce8a  test    eax, eax
0x18002ce8c  jnz     short loc_18002CEB1
0x18002ce8e  mov     ebx, 80240FFFh
0x18002ce93  mov     r9d, ebx; char *
0x18002ce96  mov     edx, 387h; void *
0x18002ce9b  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002cea2  mov     rcx, [rsp+0B8h]; this
0x18002ceaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ceaf  jmp     short loc_18002CEDB
0x18002ceb1  cmp     eax, 3
0x18002ceb4  jz      short loc_18002CED9
0x18002ceb6  lea     rcx, [rsi+30h]; this
0x18002ceba  call    ?ReleaseRemoteProcess@CUHHandlerManager@@AEAAJXZ; CUHHandlerManager::ReleaseRemoteProcess(void)
0x18002cebf  mov     ebx, eax
0x18002cec1  test    eax, eax
0x18002cec3  jns     short loc_18002CECF
0x18002cec5  mov     r9d, eax
0x18002cec8  mov     edx, 389h
0x18002cecd  jmp     short loc_18002CE9B
0x18002cecf  mov     dword ptr [rsi+19Ch], 3
0x18002ced9  xor     ebx, ebx
0x18002cedb  mov     rcx, [rsp+0B8h]; this
0x18002cee3  test    ebx, ebx
0x18002cee5  jns     short loc_18002CEFB
0x18002cee7  mov     r9d, ebx; char *
0x18002ceea  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002cef1  mov     edx, 948h; void *
0x18002cef6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cefb  mov     rcx, rsi; this
0x18002cefe  test    edi, edi
0x18002cf00  js      short loc_18002CF09
0x18002cf02  call    ?OnJobComplete@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::OnJobComplete(void)
0x18002cf07  jmp     short loc_18002CF1F
0x18002cf09  cmp     edi, 8024000Bh
0x18002cf0f  jnz     short loc_18002CF18
0x18002cf11  call    ?OnJobAborted@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::OnJobAborted(void)
0x18002cf16  jmp     short loc_18002CF1F
0x18002cf18  mov     edx, edi; int
0x18002cf1a  call    ?OnJobFailure@CUpdateDeploymentJob@@AEAAJJ@Z; CUpdateDeploymentJob::OnJobFailure(long)
0x18002cf1f  mov     rbx, [rsi+2A8h]
0x18002cf26  lea     rdx, [rsi+10h]; struct _GUID *
0x18002cf2a  lea     rcx, [rsp+0B8h+var_68]; this
0x18002cf2f  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002cf34  mov     [rsp+0B8h+var_78], edi
0x18002cf38  mov     [rsp+0B8h+var_80], rbx
0x18002cf3d  mov     [rsp+0B8h+var_88], rax
0x18002cf42  lea     rax, aDeploymentJobI_77; "Deployment job Id %ws : Ending deployme"...
0x18002cf49  mov     [rsp+0B8h+var_90], rax
0x18002cf4e  mov     qword ptr [rsp+0B8h+var_98], 0; int
0x18002cf57  xor     edx, edx
0x18002cf59  xor     ecx, ecx
0x18002cf5b  lea     r9d, [rdx+4]
0x18002cf5f  mov     r8d, 1000000h
0x18002cf65  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002cf6a  test    edi, edi
0x18002cf6c  jns     short loc_18002CF8C
0x18002cf6e  mov     edx, 95Eh; void *
0x18002cf73  mov     rcx, [rsp+0B8h]; this
0x18002cf7b  mov     r9d, edi; char *
0x18002cf7e  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002cf85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cf8a  jmp     short loc_18002CF8E
0x18002cf8c  xor     edi, edi
0x18002cf8e  cmp     [rsp+0B8h+arg_0], 0
0x18002cf96  jz      short loc_18002CF9E
0x18002cf98  call    cs:__imp_CoUninitialize
0x18002cf9e  mov     eax, edi
0x18002cfa0  lea     r11, [rsp+0B8h+var_18]
0x18002cfa8  mov     rbx, [r11+28h]
0x18002cfac  mov     rbp, [r11+30h]
0x18002cfb0  mov     rsp, r11
0x18002cfb3  pop     r14
0x18002cfb5  pop     rdi
0x18002cfb6  pop     rsi
0x18002cfb7  retn
```
