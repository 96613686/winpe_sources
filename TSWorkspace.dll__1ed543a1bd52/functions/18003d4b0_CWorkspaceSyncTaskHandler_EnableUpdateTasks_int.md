# CWorkspaceSyncTaskHandler::EnableUpdateTasks(int)

- ea: `0x18003d4b0`
- end: `0x18003da05`
- name: `?EnableUpdateTasks@CWorkspaceSyncTaskHandler@@SAJH@Z`
- size: `1365`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002eae0`
- `0x180033330`

## callees

- `0x1800054c4`
- `0x180005524`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ee9c`
- `0x18000efc4`
- `0x18000eff0`
- `0x18003d4b0`
- `0x18003da0c`
- `0x18003dcf0`
- `0x18003e03c`
- `0x180042fd0`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003d5c5`
- `ole32!CoCreateInstance` at `0x18003d5c5`
- `OLEAUT32!__imp_VariantInit` at `0x18003d61d`
- `OLEAUT32!__imp_VariantInit` at `0x18003d634`
- `OLEAUT32!__imp_VariantInit` at `0x18003d64c`
- `OLEAUT32!__imp_VariantInit` at `0x18003d663`
- `OLEAUT32!__imp_VariantInit` at `0x18003d61d`
- `OLEAUT32!__imp_VariantInit` at `0x18003d634`
- `OLEAUT32!__imp_VariantInit` at `0x18003d64c`
- `OLEAUT32!__imp_VariantInit` at `0x18003d663`

## string_xrefs

- `0x18003d5ff`: `CoCreateInstance failed for ITaskService`
- `0x18003d71b`: `ITaskService::Connect failed`
- `0x18003d771`: `GetPersonalTaskFolder failed`
- `0x18003d7cc`: `GetDailyUpdateTask failed`
- `0x18003d827`: `GetNotificationTask failed`
- `0x18003d884`: `GetWorkspaceReconnectTask failed`
- `0x18003d8d8`: `DailyTask put_Enabled failed`
- `0x18003d924`: `NotifyTask put_Enabled failed`
- `0x18003d96b`: `Reconnect Task put_Enabled failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWorkspaceSyncTaskHandler::EnableUpdateTasks(int a1)
{
  unsigned __int16 v2; // si
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT Instance; // ebx
  unsigned int v5; // eax
  int v6; // edx
  const char *v7; // rcx
  struct ITaskService *v8; // rdi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  __int64 v13; // xmm9_8
  __int128 v14; // xmm6
  __int64 v15; // xmm7_8
  HRESULT v17; // [rsp+30h] [rbp-D8h]
  struct IRegisteredTask *v18; // [rsp+38h] [rbp-D0h] BYREF
  VARIANTARG pvarSrc; // [rsp+40h] [rbp-C8h] BYREF
  VARIANTARG v20; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v21; // [rsp+70h] [rbp-98h] BYREF
  __int64 v22; // [rsp+88h] [rbp-80h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-78h] BYREF
  __int64 v24; // [rsp+A8h] [rbp-60h]
  __int128 v25; // [rsp+B8h] [rbp-50h] BYREF
  IRecordInfo *v26; // [rsp+C8h] [rbp-40h]
  __int128 v27; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v28; // [rsp+E8h] [rbp-20h]
  __int128 v29; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v30; // [rsp+108h] [rbp+0h]
  __int128 v31; // [rsp+118h] [rbp+10h] BYREF
  __int64 v32; // [rsp+128h] [rbp+20h]
  struct ITaskService *ppv; // [rsp+1D0h] [rbp+C8h] BYREF
  struct ITaskFolder *v34; // [rsp+1D8h] [rbp+D0h] BYREF
  struct IRegisteredTask *v35; // [rsp+1E0h] [rbp+D8h] BYREF

  v24 = -2;
  ppv = 0;
  v34 = 0;
  ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(&pvarSrc);
  ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(&v18);
  ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(&v35);
  pvarSrc.iVal = 11;
  *((_WORD *)&pvarSrc.decVal + 8) = -(a1 != 0);
  v2 = _variant_t::operator short((VARIANTARG *)&pvarSrc.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&pvarSrc.decVal.8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids,
      CurrentThreadActivityIdPrefix,
      a1);
  }
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v8 = ppv;
    Connect = ppv->lpVtbl->Connect;
    VariantInit(&pvarg);
    v10 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit((VARIANTARG *)&v21.decVal.8);
    v12 = *(_OWORD *)&v21.decVal.Lo32;
    v13 = v22;
    VariantInit((VARIANTARG *)&v20.decVal.8);
    v14 = *(_OWORD *)&v20.decVal.Lo32;
    v15 = *(_QWORD *)&v21.vt;
    VariantInit((VARIANTARG *)&pvarSrc.decVal.8);
    v25 = v10;
    v26 = pRecInfo;
    v27 = v12;
    v28 = v13;
    v29 = v14;
    v30 = v15;
    v31 = *(_OWORD *)&pvarSrc.decVal.Lo32;
    v32 = *(_QWORD *)&v20.vt;
    Instance = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *, __int128 *))Connect)(
                 v8,
                 &v31,
                 &v29,
                 &v27,
                 &v25);
    _variant_t::~_variant_t((_variant_t *)&pvarSrc.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v20.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v21.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( Instance >= 0 )
    {
      Instance = GetPersonalTaskFolder(ppv, &v34, 0);
      if ( Instance >= 0 )
      {
        Instance = CWorkspaceSyncTaskHandler::GetDailyUpdateTask(ppv, v34, (struct IRegisteredTask **)&pvarSrc, 0);
        if ( Instance >= 0 )
        {
          Instance = CWorkspaceSyncTaskHandler::GetNotificationTask(ppv, v34, &v18, 0);
          if ( Instance >= 0 )
          {
            Instance = CWorkspaceSyncTaskHandler::GetWorkspaceReconnectTask(ppv, v34, &v35, 0);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&pvarSrc.vt + 88LL))(
                           *(_QWORD *)&pvarSrc.vt,
                           v2);
              if ( Instance >= 0 )
              {
                Instance = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v18->lpVtbl->put_Enabled)(v18, v2);
                if ( Instance >= 0 )
                {
                  Instance = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v35->lpVtbl->put_Enabled)(
                               v35,
                               v2);
                  if ( Instance < 0
                    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
                    v6 = 31;
                    v7 = "Reconnect Task put_Enabled failed";
                    goto LABEL_50;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v5 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v6 = 30;
                  v7 = "NotifyTask put_Enabled failed";
                  goto LABEL_50;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v5 = RdpWppGetCurrentThreadActivityIdPrefix();
                v6 = 29;
                v7 = "DailyTask put_Enabled failed";
                goto LABEL_50;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v5 = RdpWppGetCurrentThreadActivityIdPrefix();
              v6 = 28;
              v7 = "GetWorkspaceReconnectTask failed";
              goto LABEL_50;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v5 = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 27;
            v7 = "GetNotificationTask failed";
            goto LABEL_50;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = RdpWppGetCurrentThreadActivityIdPrefix();
          v6 = 26;
          v7 = "GetDailyUpdateTask failed";
          goto LABEL_50;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 25;
        v7 = "GetPersonalTaskFolder failed";
        goto LABEL_50;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 24;
      v7 = "ITaskService::Connect failed";
      goto LABEL_50;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 23;
    v7 = "CoCreateInstance failed for ITaskService";
LABEL_50:
    v17 = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids,
      v5,
      (__int64)v7,
      v17);
  }
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v35);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v18);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&pvarSrc);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v34);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003d4b0  mov     rax, rsp
0x18003d4b3  push    rbp
0x18003d4b4  push    rsi
0x18003d4b5  push    rdi
0x18003d4b6  push    r14
0x18003d4b8  push    r15
0x18003d4ba  lea     rbp, [rax-0B8h]
0x18003d4c1  sub     rsp, 190h
0x18003d4c8  mov     [rbp+0B0h+var_110], 0FFFFFFFFFFFFFFFEh
0x18003d4d0  mov     [rax+8], rbx
0x18003d4d4  movaps  xmmword ptr [rax-38h], xmm6
0x18003d4d8  movaps  xmmword ptr [rax-48h], xmm7
0x18003d4dc  movaps  xmmword ptr [rax-58h], xmm8
0x18003d4e1  movaps  xmmword ptr [rax-68h], xmm9
0x18003d4e6  movaps  xmmword ptr [rax-78h], xmm10
0x18003d4eb  movaps  xmmword ptr [rax-88h], xmm11
0x18003d4f3  mov     ebx, ecx
0x18003d4f5  mov     [rbp+0B0h+arg_8], 0
0x18003d500  mov     [rbp+0B0h+arg_10], 0
0x18003d50b  lea     rcx, [rsp+1B0h+pvarSrc]
0x18003d510  call    ??0?$ComPlainSmartPtr@UIRegisteredTask@@@@QEAA@PEAUIRegisteredTask@@@Z; ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(IRegisteredTask *)
0x18003d515  nop
0x18003d516  lea     rcx, [rsp+1B0h+var_180]
0x18003d51b  call    ??0?$ComPlainSmartPtr@UIRegisteredTask@@@@QEAA@PEAUIRegisteredTask@@@Z; ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(IRegisteredTask *)
0x18003d520  nop
0x18003d521  lea     rcx, [rbp+0B0h+arg_18]
0x18003d528  call    ??0?$ComPlainSmartPtr@UIRegisteredTask@@@@QEAA@PEAUIRegisteredTask@@@Z; ComPlainSmartPtr<IRegisteredTask>::ComPlainSmartPtr<IRegisteredTask>(IRegisteredTask *)
0x18003d52d  nop
0x18003d52e  mov     eax, 0Bh
0x18003d533  mov     word ptr [rsp+1B0h+pvarSrc+8], ax
0x18003d538  mov     eax, ebx
0x18003d53a  neg     eax
0x18003d53c  sbb     cx, cx
0x18003d53f  mov     word ptr [rsp+1B0h+pvarSrc+10h], cx
0x18003d544  lea     rcx, [rsp+1B0h+pvarSrc+8]; pvarSrc
0x18003d549  call    ??B_variant_t@@QEBAFXZ; _variant_t::operator short(void)
0x18003d54e  movzx   esi, ax
0x18003d551  lea     rcx, [rsp+1B0h+pvarSrc+8]; this
0x18003d556  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d55b  lea     r14, WPP_GLOBAL_Control
0x18003d562  lea     r15, WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids
0x18003d569  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d570  cmp     rcx, r14
0x18003d573  jz      short loc_18003D5A5
0x18003d575  test    byte ptr [rcx+1Ch], 1
0x18003d579  jz      short loc_18003D5A5
0x18003d57b  cmp     byte ptr [rcx+19h], 4
0x18003d57f  jb      short loc_18003D5A5
0x18003d581  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d586  mov     edx, 16h
0x18003d58b  mov     dword ptr [rsp+1B0h+ppv], ebx
0x18003d58f  mov     r9d, eax
0x18003d592  mov     r8, r15
0x18003d595  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d59c  mov     rcx, [rcx+10h]
0x18003d5a0  call    WPP_SF_Dd
0x18003d5a5  lea     rax, [rbp+0B0h+arg_8]
0x18003d5ac  mov     [rsp+1B0h+ppv], rax; ppv
0x18003d5b1  lea     r9, IID_ITaskService; riid
0x18003d5b8  xor     edx, edx; pUnkOuter
0x18003d5ba  lea     r8d, [rdx+1]; dwClsContext
0x18003d5be  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003d5c5  call    cs:__imp_CoCreateInstance
0x18003d5cb  mov     ebx, eax
0x18003d5cd  test    eax, eax
0x18003d5cf  jns     short loc_18003D60B
0x18003d5d1  mov     rax, cs:WPP_GLOBAL_Control
0x18003d5d8  cmp     rax, r14
0x18003d5db  jz      loc_18003D992
0x18003d5e1  test    byte ptr [rax+1Ch], 8
0x18003d5e5  jz      loc_18003D992
0x18003d5eb  cmp     byte ptr [rax+19h], 2
0x18003d5ef  jb      loc_18003D992
0x18003d5f5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d5fa  mov     edx, 17h
0x18003d5ff  lea     rcx, aCocreateinstan_3; "CoCreateInstance failed for ITaskServic"...
0x18003d606  jmp     loc_18003D972
0x18003d60b  mov     rdi, [rbp+0B0h+arg_8]
0x18003d612  mov     rax, [rdi]
0x18003d615  mov     rbx, [rax+50h]
0x18003d619  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x18003d61d  call    cs:__imp_VariantInit
0x18003d623  nop
0x18003d624  movups  xmm10, xmmword ptr [rbp+0B0h+pvarg]
0x18003d629  movsd   xmm11, qword ptr [rbp+0B0h+pvarg+10h]
0x18003d62f  lea     rcx, [rsp+1B0h+var_148+8]; pvarg
0x18003d634  call    cs:__imp_VariantInit
0x18003d63a  nop
0x18003d63b  movups  xmm8, xmmword ptr [rsp+1B0h+var_148+8]
0x18003d641  movsd   xmm9, [rbp+0B0h+var_130]
0x18003d647  lea     rcx, [rsp+1B0h+var_160+8]; pvarg
0x18003d64c  call    cs:__imp_VariantInit
0x18003d652  nop
0x18003d653  movups  xmm6, xmmword ptr [rsp+1B0h+var_160+8]
0x18003d658  movsd   xmm7, qword ptr [rsp+1B0h+var_148]
0x18003d65e  lea     rcx, [rsp+1B0h+pvarSrc+8]; pvarg
0x18003d663  call    cs:__imp_VariantInit
0x18003d669  nop
0x18003d66a  movups  xmm0, xmmword ptr [rsp+1B0h+pvarSrc+8]
0x18003d66f  movsd   xmm1, qword ptr [rsp+1B0h+var_160]
0x18003d675  movaps  [rbp+0B0h+var_100], xmm10
0x18003d67a  movsd   [rbp+0B0h+var_F0], xmm11
0x18003d680  movaps  [rbp+0B0h+var_E0], xmm8
0x18003d685  movsd   [rbp+0B0h+var_D0], xmm9
0x18003d68b  movaps  [rbp+0B0h+var_C0], xmm6
0x18003d68f  movsd   [rbp+0B0h+var_B0], xmm7
0x18003d694  movaps  [rbp+0B0h+var_A0], xmm0
0x18003d698  movsd   [rbp+0B0h+var_90], xmm1
0x18003d69d  lea     rax, [rbp+0B0h+var_100]
0x18003d6a1  mov     [rsp+1B0h+ppv], rax
0x18003d6a6  lea     r9, [rbp+0B0h+var_E0]
0x18003d6aa  lea     r8, [rbp+0B0h+var_C0]
0x18003d6ae  lea     rdx, [rbp+0B0h+var_A0]
0x18003d6b2  mov     rcx, rdi
0x18003d6b5  mov     rax, rbx
0x18003d6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6bd  mov     ebx, eax
0x18003d6bf  lea     rcx, [rsp+1B0h+pvarSrc+8]; this
0x18003d6c4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d6c9  nop
0x18003d6ca  lea     rcx, [rsp+1B0h+var_160+8]; this
0x18003d6cf  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d6d4  nop
0x18003d6d5  lea     rcx, [rsp+1B0h+var_148+8]; this
0x18003d6da  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d6df  nop
0x18003d6e0  lea     rcx, [rbp+0B0h+pvarg]; this
0x18003d6e4  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d6e9  test    ebx, ebx
0x18003d6eb  jns     short loc_18003D727
0x18003d6ed  mov     rax, cs:WPP_GLOBAL_Control
0x18003d6f4  cmp     rax, r14
0x18003d6f7  jz      loc_18003D992
0x18003d6fd  test    byte ptr [rax+1Ch], 8
0x18003d701  jz      loc_18003D992
0x18003d707  cmp     byte ptr [rax+19h], 2
0x18003d70b  jb      loc_18003D992
0x18003d711  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d716  mov     edx, 18h
0x18003d71b  lea     rcx, aItaskserviceCo; "ITaskService::Connect failed"
0x18003d722  jmp     loc_18003D972
0x18003d727  xor     r8d, r8d; int
0x18003d72a  lea     rdx, [rbp+0B0h+arg_10]; struct ITaskFolder **
0x18003d731  mov     rcx, [rbp+0B0h+arg_8]; struct ITaskService *
0x18003d738  call    ?GetPersonalTaskFolder@@YAJPEAUITaskService@@PEAPEAUITaskFolder@@H@Z; GetPersonalTaskFolder(ITaskService *,ITaskFolder * *,int)
0x18003d73d  mov     ebx, eax
0x18003d73f  test    eax, eax
0x18003d741  jns     short loc_18003D77D
0x18003d743  mov     rax, cs:WPP_GLOBAL_Control
0x18003d74a  cmp     rax, r14
0x18003d74d  jz      loc_18003D992
0x18003d753  test    byte ptr [rax+1Ch], 8
0x18003d757  jz      loc_18003D992
0x18003d75d  cmp     byte ptr [rax+19h], 2
0x18003d761  jb      loc_18003D992
0x18003d767  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d76c  mov     edx, 19h
0x18003d771  lea     rcx, aGetpersonaltas_0; "GetPersonalTaskFolder failed"
0x18003d778  jmp     loc_18003D972
0x18003d77d  xor     r9d, r9d; int
0x18003d780  lea     r8, [rsp+1B0h+pvarSrc]; struct IRegisteredTask **
0x18003d785  mov     rdx, [rbp+0B0h+arg_10]; struct ITaskFolder *
0x18003d78c  mov     rcx, [rbp+0B0h+arg_8]; struct ITaskService *
0x18003d793  call    ?GetDailyUpdateTask@CWorkspaceSyncTaskHandler@@KAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@H@Z; CWorkspaceSyncTaskHandler::GetDailyUpdateTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,int)
0x18003d798  mov     ebx, eax
0x18003d79a  test    eax, eax
0x18003d79c  jns     short loc_18003D7D8
0x18003d79e  mov     rax, cs:WPP_GLOBAL_Control
0x18003d7a5  cmp     rax, r14
0x18003d7a8  jz      loc_18003D992
0x18003d7ae  test    byte ptr [rax+1Ch], 8
0x18003d7b2  jz      loc_18003D992
0x18003d7b8  cmp     byte ptr [rax+19h], 2
0x18003d7bc  jb      loc_18003D992
0x18003d7c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d7c7  mov     edx, 1Ah
0x18003d7cc  lea     rcx, aGetdailyupdate; "GetDailyUpdateTask failed"
0x18003d7d3  jmp     loc_18003D972
0x18003d7d8  xor     r9d, r9d; int
0x18003d7db  lea     r8, [rsp+1B0h+var_180]; struct IRegisteredTask **
0x18003d7e0  mov     rdx, [rbp+0B0h+arg_10]; struct ITaskFolder *
0x18003d7e7  mov     rcx, [rbp+0B0h+arg_8]; struct ITaskService *
0x18003d7ee  call    ?GetNotificationTask@CWorkspaceSyncTaskHandler@@KAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@H@Z; CWorkspaceSyncTaskHandler::GetNotificationTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,int)
0x18003d7f3  mov     ebx, eax
0x18003d7f5  test    eax, eax
0x18003d7f7  jns     short loc_18003D833
0x18003d7f9  mov     rax, cs:WPP_GLOBAL_Control
0x18003d800  cmp     rax, r14
0x18003d803  jz      loc_18003D992
0x18003d809  test    byte ptr [rax+1Ch], 8
0x18003d80d  jz      loc_18003D992
0x18003d813  cmp     byte ptr [rax+19h], 2
0x18003d817  jb      loc_18003D992
0x18003d81d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d822  mov     edx, 1Bh
0x18003d827  lea     rcx, aGetnotificatio; "GetNotificationTask failed"
0x18003d82e  jmp     loc_18003D972
0x18003d833  xor     r9d, r9d; int
0x18003d836  lea     r8, [rbp+0B0h+arg_18]; struct IRegisteredTask **
0x18003d83d  mov     rdx, [rbp+0B0h+arg_10]; struct ITaskFolder *
0x18003d844  mov     rcx, [rbp+0B0h+arg_8]; struct ITaskService *
0x18003d84b  call    ?GetWorkspaceReconnectTask@CWorkspaceSyncTaskHandler@@KAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@H@Z; CWorkspaceSyncTaskHandler::GetWorkspaceReconnectTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,int)
0x18003d850  mov     ebx, eax
0x18003d852  test    eax, eax
0x18003d854  jns     short loc_18003D890
0x18003d856  mov     rax, cs:WPP_GLOBAL_Control
0x18003d85d  cmp     rax, r14
0x18003d860  jz      loc_18003D992
0x18003d866  test    byte ptr [rax+1Ch], 8
0x18003d86a  jz      loc_18003D992
0x18003d870  cmp     byte ptr [rax+19h], 2
0x18003d874  jb      loc_18003D992
0x18003d87a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d87f  mov     edx, 1Ch
0x18003d884  lea     rcx, aGetworkspacere; "GetWorkspaceReconnectTask failed"
0x18003d88b  jmp     loc_18003D972
0x18003d890  mov     rcx, qword ptr [rsp+1B0h+pvarSrc]
0x18003d895  mov     rax, [rcx]
0x18003d898  movzx   edx, si
0x18003d89b  mov     rax, [rax+58h]
0x18003d89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8a4  mov     ebx, eax
0x18003d8a6  test    eax, eax
0x18003d8a8  jns     short loc_18003D8E4
0x18003d8aa  mov     rax, cs:WPP_GLOBAL_Control
0x18003d8b1  cmp     rax, r14
0x18003d8b4  jz      loc_18003D992
0x18003d8ba  test    byte ptr [rax+1Ch], 8
0x18003d8be  jz      loc_18003D992
0x18003d8c4  cmp     byte ptr [rax+19h], 2
0x18003d8c8  jb      loc_18003D992
0x18003d8ce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d8d3  mov     edx, 1Dh
0x18003d8d8  lea     rcx, aDailytaskPutEn; "DailyTask put_Enabled failed"
0x18003d8df  jmp     loc_18003D972
0x18003d8e4  mov     rcx, [rsp+1B0h+var_180]
0x18003d8e9  mov     rax, [rcx]
0x18003d8ec  movzx   edx, si
0x18003d8ef  mov     rax, [rax+58h]
0x18003d8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8f8  mov     ebx, eax
0x18003d8fa  test    eax, eax
0x18003d8fc  jns     short loc_18003D92D
0x18003d8fe  mov     rax, cs:WPP_GLOBAL_Control
0x18003d905  cmp     rax, r14
0x18003d908  jz      loc_18003D992
0x18003d90e  test    byte ptr [rax+1Ch], 8
0x18003d912  jz      short loc_18003D992
0x18003d914  cmp     byte ptr [rax+19h], 2
0x18003d918  jb      short loc_18003D992
0x18003d91a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d91f  mov     edx, 1Eh
0x18003d924  lea     rcx, aNotifytaskPutE; "NotifyTask put_Enabled failed"
0x18003d92b  jmp     short loc_18003D972
0x18003d92d  mov     rcx, [rbp+0B0h+arg_18]
0x18003d934  mov     rax, [rcx]
0x18003d937  movzx   edx, si
0x18003d93a  mov     rax, [rax+58h]
0x18003d93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d943  mov     ebx, eax
0x18003d945  test    eax, eax
0x18003d947  jns     short loc_18003D992
0x18003d949  mov     rax, cs:WPP_GLOBAL_Control
0x18003d950  cmp     rax, r14
0x18003d953  jz      short loc_18003D992
0x18003d955  test    byte ptr [rax+1Ch], 8
0x18003d959  jz      short loc_18003D992
0x18003d95b  cmp     byte ptr [rax+19h], 2
0x18003d95f  jb      short loc_18003D992
0x18003d961  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d966  mov     edx, 1Fh
0x18003d96b  lea     rcx, aReconnectTaskP; "Reconnect Task put_Enabled failed"
0x18003d972  mov     dword ptr [rsp+1B0h+var_188], ebx
0x18003d976  mov     [rsp+1B0h+ppv], rcx
0x18003d97b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d982  mov     r9d, eax
0x18003d985  mov     r8, r15
0x18003d988  mov     rcx, [rcx+10h]
0x18003d98c  call    WPP_SF_DsD
0x18003d991  nop
0x18003d992  lea     rcx, [rbp+0B0h+arg_18]
0x18003d999  call    ??1?$ComPlainSmartPtr@UIRADCWorkspaceManager@@@@QEAA@XZ; ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(void)
0x18003d99e  nop
0x18003d99f  lea     rcx, [rsp+1B0h+var_180]
0x18003d9a4  call    ??1?$ComPlainSmartPtr@UIRADCWorkspaceManager@@@@QEAA@XZ; ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(void)
0x18003d9a9  nop
0x18003d9aa  lea     rcx, [rsp+1B0h+pvarSrc]
0x18003d9af  call    ??1?$ComPlainSmartPtr@UIRADCWorkspaceManager@@@@QEAA@XZ; ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(void)
0x18003d9b4  nop
0x18003d9b5  lea     rcx, [rbp+0B0h+arg_10]
0x18003d9bc  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18003d9c1  nop
0x18003d9c2  lea     rcx, [rbp+0B0h+arg_8]
0x18003d9c9  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18003d9ce  mov     eax, ebx
0x18003d9d0  lea     r11, [rsp+1B0h+var_20]
0x18003d9d8  mov     rbx, [r11+30h]
0x18003d9dc  movaps  xmm6, xmmword ptr [r11-10h]
0x18003d9e1  movaps  xmm7, xmmword ptr [r11-20h]
0x18003d9e6  movaps  xmm8, xmmword ptr [r11-30h]
  ... truncated ...
```
