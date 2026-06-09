# CWorkspaceSyncTaskHandler::ScheduleUpdateTasks(void)

- ea: `0x18003e334`
- end: `0x18003e764`
- name: `?ScheduleUpdateTasks@CWorkspaceSyncTaskHandler@@SAJXZ`
- size: `1072`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c650`
- `0x18000c7c0`
- `0x18000d3d0`
- `0x180033330`

## callees

- `0x1800054c4`
- `0x180005524`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ece0`
- `0x18000ee9c`
- `0x18000efc4`
- `0x18003da0c`
- `0x18003dcf0`
- `0x18003e03c`
- `0x18003e334`
- `0x180042fd0`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003e41c`
- `ole32!CoCreateInstance` at `0x18003e41c`
- `OLEAUT32!__imp_VariantInit` at `0x18003e474`
- `OLEAUT32!__imp_VariantInit` at `0x18003e48b`
- `OLEAUT32!__imp_VariantInit` at `0x18003e4a4`
- `OLEAUT32!__imp_VariantInit` at `0x18003e4bb`
- `OLEAUT32!__imp_VariantInit` at `0x18003e474`
- `OLEAUT32!__imp_VariantInit` at `0x18003e48b`
- `OLEAUT32!__imp_VariantInit` at `0x18003e4a4`
- `OLEAUT32!__imp_VariantInit` at `0x18003e4bb`

## string_xrefs

- `0x18003e456`: `CoCreateInstance failed for ITaskService`
- `0x18003e573`: `ITaskService::Connect failed`
- `0x18003e5c9`: `GetPersonalTaskFolder failed`
- `0x18003e624`: `GetDailyUpdateTask failed`
- `0x18003e67d`: `GetNotificationTask failed`
- `0x18003e6cb`: `GetWorkspaceReconnectTask failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 CWorkspaceSyncTaskHandler::ScheduleUpdateTasks(void)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT Instance; // ebx
  unsigned int v2; // eax
  int v3; // edx
  const char *v4; // rcx
  struct ITaskService *v5; // rdi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rbx
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  __int64 v10; // xmm9_8
  __int128 v11; // xmm6
  __int64 v12; // xmm7_8
  HRESULT v14; // [rsp+30h] [rbp-D8h]
  VARIANTARG v15; // [rsp+38h] [rbp-D0h] BYREF
  VARIANTARG v16; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v17; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+80h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-68h]
  __int128 v21; // [rsp+A8h] [rbp-60h] BYREF
  IRecordInfo *v22; // [rsp+B8h] [rbp-50h]
  __int128 v23; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-30h]
  __int128 v25; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-10h]
  __int128 v27; // [rsp+108h] [rbp+0h] BYREF
  __int64 v28; // [rsp+118h] [rbp+10h]
  struct ITaskService *ppv; // [rsp+1C8h] [rbp+C0h] BYREF
  struct ITaskFolder *v30; // [rsp+1D0h] [rbp+C8h] BYREF
  struct IRegisteredTask *v31; // [rsp+1D8h] [rbp+D0h] BYREF
  struct IRegisteredTask *v32; // [rsp+1E0h] [rbp+D8h] BYREF

  v20 = -2;
  ppv = 0;
  v30 = 0;
  ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(&v15);
  ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(&v32);
  ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(&v31);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v5 = ppv;
    Connect = ppv->lpVtbl->Connect;
    VariantInit(&pvarg);
    v7 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit((VARIANTARG *)&v17.decVal.8);
    v9 = *(_OWORD *)&v17.decVal.Lo32;
    v10 = v18;
    VariantInit((VARIANTARG *)&v16.decVal.8);
    v11 = *(_OWORD *)&v16.decVal.Lo32;
    v12 = *(_QWORD *)&v17.vt;
    VariantInit((VARIANTARG *)&v15.decVal.8);
    v21 = v7;
    v22 = pRecInfo;
    v23 = v9;
    v24 = v10;
    v25 = v11;
    v26 = v12;
    v27 = *(_OWORD *)&v15.decVal.Lo32;
    v28 = *(_QWORD *)&v16.vt;
    Instance = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *, __int128 *))Connect)(
                 v5,
                 &v27,
                 &v25,
                 &v23,
                 &v21);
    _variant_t::~_variant_t((_variant_t *)&v15.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v16.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v17.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( Instance >= 0 )
    {
      Instance = GetPersonalTaskFolder(ppv, &v30, 1);
      if ( Instance >= 0 )
      {
        Instance = CWorkspaceSyncTaskHandler::GetDailyUpdateTask(ppv, v30, (struct IRegisteredTask **)&v15, 1);
        if ( Instance >= 0 )
        {
          Instance = CWorkspaceSyncTaskHandler::GetNotificationTask(ppv, v30, &v32, 1);
          if ( Instance >= 0 )
          {
            Instance = CWorkspaceSyncTaskHandler::GetWorkspaceReconnectTask(ppv, v30, &v31, 1);
            if ( Instance < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v2 = RdpWppGetCurrentThreadActivityIdPrefix();
              v3 = 21;
              v4 = "GetWorkspaceReconnectTask failed";
              goto LABEL_35;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v2 = RdpWppGetCurrentThreadActivityIdPrefix();
            v3 = 20;
            v4 = "GetNotificationTask failed";
            goto LABEL_35;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v2 = RdpWppGetCurrentThreadActivityIdPrefix();
          v3 = 19;
          v4 = "GetDailyUpdateTask failed";
          goto LABEL_35;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v2 = RdpWppGetCurrentThreadActivityIdPrefix();
        v3 = 18;
        v4 = "GetPersonalTaskFolder failed";
        goto LABEL_35;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = RdpWppGetCurrentThreadActivityIdPrefix();
      v3 = 17;
      v4 = "ITaskService::Connect failed";
      goto LABEL_35;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v2 = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 16;
    v4 = "CoCreateInstance failed for ITaskService";
LABEL_35:
    v14 = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids,
      v2,
      (__int64)v4,
      v14);
  }
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v31);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v32);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v15);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v30);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003e334  mov     rax, rsp
0x18003e337  push    rbp
0x18003e338  push    rbx
0x18003e339  push    rsi
0x18003e33a  push    rdi
0x18003e33b  push    r14
0x18003e33d  push    r15
0x18003e33f  lea     rbp, [rax-0B8h]
0x18003e346  sub     rsp, 188h
0x18003e34d  mov     [rbp+0B0h+var_118], 0FFFFFFFFFFFFFFFEh
0x18003e355  movaps  xmmword ptr [rax-48h], xmm6
0x18003e359  movaps  xmmword ptr [rax-58h], xmm7
0x18003e35d  movaps  xmmword ptr [rax-68h], xmm8
0x18003e362  movaps  xmmword ptr [rax-78h], xmm9
0x18003e367  movaps  xmmword ptr [rax-88h], xmm10
0x18003e36f  movaps  xmmword ptr [rax-98h], xmm11
0x18003e377  mov     [rbp+0B0h+arg_0], 0
0x18003e382  mov     [rbp+0B0h+arg_8], 0
0x18003e38d  lea     rcx, [rsp+1B0h+var_180]
0x18003e392  call    ??0?$ComPlainSmartPtr@UIRegisteredTask@@@@QEAA@PEAUIRegisteredTask@@@Z; ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(IRegisteredTask *)
0x18003e397  nop
0x18003e398  lea     rcx, [rbp+0B0h+arg_18]
0x18003e39f  call    ??0?$ComPlainSmartPtr@UIRegisteredTask@@@@QEAA@PEAUIRegisteredTask@@@Z; ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(IRegisteredTask *)
0x18003e3a4  nop
0x18003e3a5  lea     rcx, [rbp+0B0h+arg_10]
0x18003e3ac  call    ??0?$ComPlainSmartPtr@UIRegisteredTask@@@@QEAA@PEAUIRegisteredTask@@@Z; ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(IRegisteredTask *)
0x18003e3b1  nop
0x18003e3b2  lea     rsi, WPP_GLOBAL_Control
0x18003e3b9  lea     r14, WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids
0x18003e3c0  mov     r15d, 1
0x18003e3c6  mov     rax, cs:WPP_GLOBAL_Control
0x18003e3cd  cmp     rax, rsi
0x18003e3d0  jz      short loc_18003E3FD
0x18003e3d2  test    [rax+1Ch], r15b
0x18003e3d6  jz      short loc_18003E3FD
0x18003e3d8  cmp     byte ptr [rax+19h], 4
0x18003e3dc  jb      short loc_18003E3FD
0x18003e3de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003e3e3  lea     edx, [r15+0Eh]
0x18003e3e7  mov     r9d, eax
0x18003e3ea  mov     r8, r14
0x18003e3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3f4  mov     rcx, [rcx+10h]
0x18003e3f8  call    WPP_SF_D
0x18003e3fd  lea     rax, [rbp+0B0h+arg_0]
0x18003e404  mov     [rsp+1B0h+ppv], rax; ppv
0x18003e409  lea     r9, IID_ITaskService; riid
0x18003e410  mov     r8d, r15d; dwClsContext
0x18003e413  xor     edx, edx; pUnkOuter
0x18003e415  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003e41c  call    cs:__imp_CoCreateInstance
0x18003e422  mov     ebx, eax
0x18003e424  test    eax, eax
0x18003e426  jns     short loc_18003E462
0x18003e428  mov     rax, cs:WPP_GLOBAL_Control
0x18003e42f  cmp     rax, rsi
0x18003e432  jz      loc_18003E6F2
0x18003e438  test    byte ptr [rax+1Ch], 8
0x18003e43c  jz      loc_18003E6F2
0x18003e442  cmp     byte ptr [rax+19h], 2
0x18003e446  jb      loc_18003E6F2
0x18003e44c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003e451  mov     edx, 10h
0x18003e456  lea     rcx, aCocreateinstan_3; "CoCreateInstance failed for ITaskServic"...
0x18003e45d  jmp     loc_18003E6D2
0x18003e462  mov     rdi, [rbp+0B0h+arg_0]
0x18003e469  mov     rax, [rdi]
0x18003e46c  mov     rbx, [rax+50h]
0x18003e470  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x18003e474  call    cs:__imp_VariantInit
0x18003e47a  nop
0x18003e47b  movups  xmm10, xmmword ptr [rbp+0B0h+pvarg]
0x18003e480  movsd   xmm11, qword ptr [rbp+0B0h+pvarg+10h]
0x18003e486  lea     rcx, [rsp+1B0h+var_150+8]; pvarg
0x18003e48b  call    cs:__imp_VariantInit
0x18003e491  nop
0x18003e492  movups  xmm8, xmmword ptr [rsp+1B0h+var_150+8]
0x18003e498  movsd   xmm9, [rsp+1B0h+var_138]
0x18003e49f  lea     rcx, [rsp+1B0h+var_168+8]; pvarg
0x18003e4a4  call    cs:__imp_VariantInit
0x18003e4aa  nop
0x18003e4ab  movups  xmm6, xmmword ptr [rsp+1B0h+var_168+8]
0x18003e4b0  movsd   xmm7, qword ptr [rsp+1B0h+var_150]
0x18003e4b6  lea     rcx, [rsp+1B0h+var_180+8]; pvarg
0x18003e4bb  call    cs:__imp_VariantInit
0x18003e4c1  nop
0x18003e4c2  movups  xmm0, xmmword ptr [rsp+1B0h+var_180+8]
0x18003e4c7  movsd   xmm1, qword ptr [rsp+1B0h+var_168]
0x18003e4cd  movaps  [rbp+0B0h+var_110], xmm10
0x18003e4d2  movsd   [rbp+0B0h+var_100], xmm11
0x18003e4d8  movaps  [rbp+0B0h+var_F0], xmm8
0x18003e4dd  movsd   [rbp+0B0h+var_E0], xmm9
0x18003e4e3  movaps  [rbp+0B0h+var_D0], xmm6
0x18003e4e7  movsd   [rbp+0B0h+var_C0], xmm7
0x18003e4ec  movaps  [rbp+0B0h+var_B0], xmm0
0x18003e4f0  movsd   [rbp+0B0h+var_A0], xmm1
0x18003e4f5  lea     rax, [rbp+0B0h+var_110]
0x18003e4f9  mov     [rsp+1B0h+ppv], rax
0x18003e4fe  lea     r9, [rbp+0B0h+var_F0]
0x18003e502  lea     r8, [rbp+0B0h+var_D0]
0x18003e506  lea     rdx, [rbp+0B0h+var_B0]
0x18003e50a  mov     rcx, rdi
0x18003e50d  mov     rax, rbx
0x18003e510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e515  mov     ebx, eax
0x18003e517  lea     rcx, [rsp+1B0h+var_180+8]; this
0x18003e51c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003e521  nop
0x18003e522  lea     rcx, [rsp+1B0h+var_168+8]; this
0x18003e527  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003e52c  nop
0x18003e52d  lea     rcx, [rsp+1B0h+var_150+8]; this
0x18003e532  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003e537  nop
0x18003e538  lea     rcx, [rbp+0B0h+pvarg]; this
0x18003e53c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003e541  test    ebx, ebx
0x18003e543  jns     short loc_18003E57F
0x18003e545  mov     rax, cs:WPP_GLOBAL_Control
0x18003e54c  cmp     rax, rsi
0x18003e54f  jz      loc_18003E6F2
0x18003e555  test    byte ptr [rax+1Ch], 8
0x18003e559  jz      loc_18003E6F2
0x18003e55f  cmp     byte ptr [rax+19h], 2
0x18003e563  jb      loc_18003E6F2
0x18003e569  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003e56e  mov     edx, 11h
0x18003e573  lea     rcx, aItaskserviceCo; "ITaskService::Connect failed"
0x18003e57a  jmp     loc_18003E6D2
0x18003e57f  mov     r8d, r15d; int
0x18003e582  lea     rdx, [rbp+0B0h+arg_8]; struct ITaskFolder **
0x18003e589  mov     rcx, [rbp+0B0h+arg_0]; struct ITaskService *
0x18003e590  call    ?GetPersonalTaskFolder@@YAJPEAUITaskService@@PEAPEAUITaskFolder@@H@Z; GetPersonalTaskFolder(ITaskService *,ITaskFolder * *,int)
0x18003e595  mov     ebx, eax
0x18003e597  test    eax, eax
0x18003e599  jns     short loc_18003E5D5
0x18003e59b  mov     rax, cs:WPP_GLOBAL_Control
0x18003e5a2  cmp     rax, rsi
0x18003e5a5  jz      loc_18003E6F2
0x18003e5ab  test    byte ptr [rax+1Ch], 8
0x18003e5af  jz      loc_18003E6F2
0x18003e5b5  cmp     byte ptr [rax+19h], 2
0x18003e5b9  jb      loc_18003E6F2
0x18003e5bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003e5c4  mov     edx, 12h
0x18003e5c9  lea     rcx, aGetpersonaltas_0; "GetPersonalTaskFolder failed"
0x18003e5d0  jmp     loc_18003E6D2
0x18003e5d5  mov     r9d, r15d; int
0x18003e5d8  lea     r8, [rsp+1B0h+var_180]; struct IRegisteredTask **
0x18003e5dd  mov     rdx, [rbp+0B0h+arg_8]; struct ITaskFolder *
0x18003e5e4  mov     rcx, [rbp+0B0h+arg_0]; struct ITaskService *
0x18003e5eb  call    ?GetDailyUpdateTask@CWorkspaceSyncTaskHandler@@KAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@H@Z; CWorkspaceSyncTaskHandler::GetDailyUpdateTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,int)
0x18003e5f0  mov     ebx, eax
0x18003e5f2  test    eax, eax
0x18003e5f4  jns     short loc_18003E630
0x18003e5f6  mov     rax, cs:WPP_GLOBAL_Control
0x18003e5fd  cmp     rax, rsi
0x18003e600  jz      loc_18003E6F2
0x18003e606  test    byte ptr [rax+1Ch], 8
0x18003e60a  jz      loc_18003E6F2
0x18003e610  cmp     byte ptr [rax+19h], 2
0x18003e614  jb      loc_18003E6F2
0x18003e61a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003e61f  mov     edx, 13h
0x18003e624  lea     rcx, aGetdailyupdate; "GetDailyUpdateTask failed"
0x18003e62b  jmp     loc_18003E6D2
0x18003e630  mov     r9d, r15d; int
0x18003e633  lea     r8, [rbp+0B0h+arg_18]; struct IRegisteredTask **
0x18003e63a  mov     rdx, [rbp+0B0h+arg_8]; struct ITaskFolder *
0x18003e641  mov     rcx, [rbp+0B0h+arg_0]; struct ITaskService *
0x18003e648  call    ?GetNotificationTask@CWorkspaceSyncTaskHandler@@KAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@H@Z; CWorkspaceSyncTaskHandler::GetNotificationTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,int)
0x18003e64d  mov     ebx, eax
0x18003e64f  test    eax, eax
0x18003e651  jns     short loc_18003E686
0x18003e653  mov     rax, cs:WPP_GLOBAL_Control
0x18003e65a  cmp     rax, rsi
0x18003e65d  jz      loc_18003E6F2
0x18003e663  test    byte ptr [rax+1Ch], 8
0x18003e667  jz      loc_18003E6F2
0x18003e66d  cmp     byte ptr [rax+19h], 2
0x18003e671  jb      short loc_18003E6F2
0x18003e673  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003e678  mov     edx, 14h
0x18003e67d  lea     rcx, aGetnotificatio; "GetNotificationTask failed"
0x18003e684  jmp     short loc_18003E6D2
0x18003e686  mov     r9d, r15d; int
0x18003e689  lea     r8, [rbp+0B0h+arg_10]; struct IRegisteredTask **
0x18003e690  mov     rdx, [rbp+0B0h+arg_8]; struct ITaskFolder *
0x18003e697  mov     rcx, [rbp+0B0h+arg_0]; struct ITaskService *
0x18003e69e  call    ?GetWorkspaceReconnectTask@CWorkspaceSyncTaskHandler@@KAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@H@Z; CWorkspaceSyncTaskHandler::GetWorkspaceReconnectTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,int)
0x18003e6a3  mov     ebx, eax
0x18003e6a5  test    eax, eax
0x18003e6a7  jns     short loc_18003E6F2
0x18003e6a9  mov     rax, cs:WPP_GLOBAL_Control
0x18003e6b0  cmp     rax, rsi
0x18003e6b3  jz      short loc_18003E6F2
0x18003e6b5  test    byte ptr [rax+1Ch], 8
0x18003e6b9  jz      short loc_18003E6F2
0x18003e6bb  cmp     byte ptr [rax+19h], 2
0x18003e6bf  jb      short loc_18003E6F2
0x18003e6c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003e6c6  mov     edx, 15h
0x18003e6cb  lea     rcx, aGetworkspacere; "GetWorkspaceReconnectTask failed"
0x18003e6d2  mov     dword ptr [rsp+1B0h+var_188], ebx
0x18003e6d6  mov     [rsp+1B0h+ppv], rcx
0x18003e6db  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6e2  mov     r9d, eax
0x18003e6e5  mov     r8, r14
0x18003e6e8  mov     rcx, [rcx+10h]
0x18003e6ec  call    WPP_SF_DsD
0x18003e6f1  nop
0x18003e6f2  lea     rcx, [rbp+0B0h+arg_10]
0x18003e6f9  call    ??1?$ComPlainSmartPtr@UIRADCWorkspaceManager@@@@QEAA@XZ; ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(void)
0x18003e6fe  nop
0x18003e6ff  lea     rcx, [rbp+0B0h+arg_18]
0x18003e706  call    ??1?$ComPlainSmartPtr@UIRADCWorkspaceManager@@@@QEAA@XZ; ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(void)
0x18003e70b  nop
0x18003e70c  lea     rcx, [rsp+1B0h+var_180]
0x18003e711  call    ??1?$ComPlainSmartPtr@UIRADCWorkspaceManager@@@@QEAA@XZ; ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(void)
0x18003e716  nop
0x18003e717  lea     rcx, [rbp+0B0h+arg_8]
0x18003e71e  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18003e723  nop
0x18003e724  lea     rcx, [rbp+0B0h+arg_0]
0x18003e72b  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18003e730  mov     eax, ebx
0x18003e732  lea     r11, [rsp+1B0h+var_28]
0x18003e73a  movaps  xmm6, xmmword ptr [r11-18h]
0x18003e73f  movaps  xmm7, xmmword ptr [r11-28h]
0x18003e744  movaps  xmm8, xmmword ptr [r11-38h]
0x18003e749  movaps  xmm9, xmmword ptr [r11-48h]
0x18003e74e  movaps  xmm10, xmmword ptr [r11-58h]
0x18003e753  movaps  xmm11, xmmword ptr [r11-68h]
0x18003e758  mov     rsp, r11
0x18003e75b  pop     r15
0x18003e75d  pop     r14
0x18003e75f  pop     rdi
0x18003e760  pop     rsi
0x18003e761  pop     rbx
0x18003e762  pop     rbp
0x18003e763  retn
```
