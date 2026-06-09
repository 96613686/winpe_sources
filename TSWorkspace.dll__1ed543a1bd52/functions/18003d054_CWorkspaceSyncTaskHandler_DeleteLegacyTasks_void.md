# CWorkspaceSyncTaskHandler::DeleteLegacyTasks(void)

- ea: `0x18003d054`
- end: `0x18003d4a8`
- name: `?DeleteLegacyTasks@CWorkspaceSyncTaskHandler@@SAJXZ`
- size: `1108`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c650`
- `0x18000c7c0`
- `0x18000d3d0`
- `0x180033330`

## callees

- `0x1800054c4`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000efc4`
- `0x18000ff00`
- `0x18003d054`
- `0x1800426dc`
- `0x180042fd0`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003d10c`
- `ole32!CoCreateInstance` at `0x18003d10c`
- `OLEAUT32!__imp_VariantInit` at `0x18003d165`
- `OLEAUT32!__imp_VariantInit` at `0x18003d17d`
- `OLEAUT32!__imp_VariantInit` at `0x18003d196`
- `OLEAUT32!__imp_VariantInit` at `0x18003d1ad`
- `OLEAUT32!__imp_VariantInit` at `0x18003d165`
- `OLEAUT32!__imp_VariantInit` at `0x18003d17d`
- `OLEAUT32!__imp_VariantInit` at `0x18003d196`
- `OLEAUT32!__imp_VariantInit` at `0x18003d1ad`

## string_xrefs

- `0x18003d146`: `CoCreateInstance failed for ITaskService`
- `0x18003d266`: `ITaskService::Connect failed`
- `0x18003d2bc`: `GetPersonalTaskFolder failed`
- `0x18003d2c8`: `Update connections (daily)`
- `0x18003d330`: `DeleteTask failed for the daily update legacy task`
- `0x18003d352`: `Update connections (at login, if needed)`
- `0x18003d3b5`: `DeleteTask failed for the login update legacy task`
- `0x18003d436`: `DeleteTask failed for the notification legacy task`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 CWorkspaceSyncTaskHandler::DeleteLegacyTasks(void)
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
  IRecordInfo *v10; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  struct ITaskService *v13; // rcx
  unsigned __int16 *lpVtbl; // r8
  int v15; // ebx
  unsigned int v16; // eax
  struct ITaskService *v17; // rcx
  unsigned __int16 *v18; // r8
  int v19; // ebx
  unsigned int v20; // eax
  struct ITaskService *v21; // rcx
  unsigned __int16 *v22; // r8
  __int64 v24; // [rsp+28h] [rbp-D8h]
  VARIANTARG v25; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v26; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v27; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h]
  __int128 v30; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *v31; // [rsp+B0h] [rbp-50h]
  __int128 v32; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *v33; // [rsp+D0h] [rbp-30h]
  __int128 v34; // [rsp+E0h] [rbp-20h] BYREF
  IRecordInfo *v35; // [rsp+F0h] [rbp-10h]
  VARIANTARG v36; // [rsp+100h] [rbp+0h] BYREF
  struct ITaskFolder *v37; // [rsp+1B0h] [rbp+B0h] BYREF
  struct ITaskService *ppv; // [rsp+1B8h] [rbp+B8h] BYREF
  char v39; // [rsp+1C0h] [rbp+C0h] BYREF

  v29 = -2;
  ppv = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
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
    VariantInit(&v27);
    v9 = *(_OWORD *)&v27.vt;
    v10 = v27.pRecInfo;
    VariantInit(&v26);
    v11 = *(_OWORD *)&v26.vt;
    v12 = v26.pRecInfo;
    VariantInit(&v25);
    v30 = v7;
    v31 = pRecInfo;
    v32 = v9;
    v33 = v10;
    v34 = v11;
    v35 = v12;
    v36 = v25;
    Instance = ((__int64 (__fastcall *)(struct ITaskService *, VARIANTARG *, __int128 *, __int128 *, __int128 *))Connect)(
                 v5,
                 &v36,
                 &v34,
                 &v32,
                 &v30);
    _variant_t::~_variant_t((_variant_t *)&v25);
    _variant_t::~_variant_t((_variant_t *)&v26);
    _variant_t::~_variant_t((_variant_t *)&v27);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( Instance >= 0 )
    {
      Instance = GetPersonalTaskFolder(ppv, &v37, 0);
      if ( Instance >= 0 )
      {
        v13 = *(struct ITaskService **)_bstr_t::_bstr_t((_bstr_t *)&v39, L"Update connections (daily)");
        if ( v13 )
          lpVtbl = (unsigned __int16 *)v13->lpVtbl;
        else
          lpVtbl = 0;
        v15 = DeleteTask(v13, v37, lpVtbl);
        _bstr_t::_Free((_bstr_t *)&v39);
        if ( v15 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids,
            v16,
            (__int64)"DeleteTask failed for the daily update legacy task",
            v15);
        }
        v18 = *(unsigned __int16 **)_bstr_t::_bstr_t((_bstr_t *)&v39, L"Update connections (at login, if needed)");
        if ( v18 )
          v18 = *(unsigned __int16 **)v18;
        v19 = DeleteTask(v17, v37, v18);
        _bstr_t::_Free((_bstr_t *)&v39);
        if ( v19 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v24) = v19;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            (unsigned int)WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids,
            v20,
            (__int64)"DeleteTask failed for the login update legacy task",
            v24);
        }
        v22 = *(unsigned __int16 **)_bstr_t::_bstr_t((_bstr_t *)&v39, L"Report connection status");
        if ( v22 )
          v22 = *(unsigned __int16 **)v22;
        Instance = DeleteTask(v21, v37, v22);
        _bstr_t::_Free((_bstr_t *)&v39);
        if ( Instance < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v2 = RdpWppGetCurrentThreadActivityIdPrefix();
          v3 = 38;
          v4 = "DeleteTask failed for the notification legacy task";
          goto LABEL_42;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v2 = RdpWppGetCurrentThreadActivityIdPrefix();
        v3 = 35;
        v4 = "GetPersonalTaskFolder failed";
        goto LABEL_42;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = RdpWppGetCurrentThreadActivityIdPrefix();
      v3 = 34;
      v4 = "ITaskService::Connect failed";
      goto LABEL_42;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v2 = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 33;
    v4 = "CoCreateInstance failed for ITaskService";
LABEL_42:
    LODWORD(v24) = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids,
      v2,
      (__int64)v4,
      v24);
  }
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v37);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003d054  mov     rax, rsp
0x18003d057  push    rbp
0x18003d058  push    rbx
0x18003d059  push    rsi
0x18003d05a  push    rdi
0x18003d05b  push    r14
0x18003d05d  lea     rbp, [rsp-80h]
0x18003d062  sub     rsp, 180h
0x18003d069  mov     [rbp+0A0h+var_110], 0FFFFFFFFFFFFFFFEh
0x18003d071  movaps  xmmword ptr [rax-38h], xmm6
0x18003d075  movaps  xmmword ptr [rax-48h], xmm7
0x18003d079  movaps  xmmword ptr [rax-58h], xmm8
0x18003d07e  movaps  xmmword ptr [rax-68h], xmm9
0x18003d083  movaps  xmmword ptr [rax-78h], xmm10
0x18003d088  movaps  xmmword ptr [rax-88h], xmm11
0x18003d090  mov     [rbp+0A0h+arg_8], 0
0x18003d09b  mov     [rbp+0A0h+arg_0], 0
0x18003d0a6  lea     rsi, WPP_GLOBAL_Control
0x18003d0ad  lea     r14, WPP_7e49a335a0ee34cca2bcd4eab7b89c05_Traceguids
0x18003d0b4  mov     rax, cs:WPP_GLOBAL_Control
0x18003d0bb  cmp     rax, rsi
0x18003d0be  jz      short loc_18003D0EC
0x18003d0c0  test    byte ptr [rax+1Ch], 1
0x18003d0c4  jz      short loc_18003D0EC
0x18003d0c6  cmp     byte ptr [rax+19h], 4
0x18003d0ca  jb      short loc_18003D0EC
0x18003d0cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d0d1  mov     edx, 20h ; ' '
0x18003d0d6  mov     r9d, eax
0x18003d0d9  mov     r8, r14
0x18003d0dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0e3  mov     rcx, [rcx+10h]
0x18003d0e7  call    WPP_SF_D
0x18003d0ec  lea     rax, [rbp+0A0h+arg_8]
0x18003d0f3  mov     [rsp+1A0h+ppv], rax; ppv
0x18003d0f8  lea     r9, IID_ITaskService; riid
0x18003d0ff  xor     edx, edx; pUnkOuter
0x18003d101  lea     r8d, [rdx+1]; dwClsContext
0x18003d105  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003d10c  call    cs:__imp_CoCreateInstance
0x18003d112  mov     ebx, eax
0x18003d114  test    eax, eax
0x18003d116  jns     short loc_18003D152
0x18003d118  mov     rax, cs:WPP_GLOBAL_Control
0x18003d11f  cmp     rax, rsi
0x18003d122  jz      loc_18003D45D
0x18003d128  test    byte ptr [rax+1Ch], 8
0x18003d12c  jz      loc_18003D45D
0x18003d132  cmp     byte ptr [rax+19h], 2
0x18003d136  jb      loc_18003D45D
0x18003d13c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d141  mov     edx, 21h ; '!'
0x18003d146  lea     rcx, aCocreateinstan_3; "CoCreateInstance failed for ITaskServic"...
0x18003d14d  jmp     loc_18003D43D
0x18003d152  mov     rdi, [rbp+0A0h+arg_8]
0x18003d159  mov     rax, [rdi]
0x18003d15c  mov     rbx, [rax+50h]
0x18003d160  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x18003d165  call    cs:__imp_VariantInit
0x18003d16b  nop
0x18003d16c  movups  xmm10, xmmword ptr [rsp+1A0h+pvarg]
0x18003d172  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x18003d178  lea     rcx, [rsp+1A0h+var_140]; pvarg
0x18003d17d  call    cs:__imp_VariantInit
0x18003d183  nop
0x18003d184  movups  xmm8, xmmword ptr [rsp+1A0h+var_140]
0x18003d18a  movsd   xmm9, qword ptr [rsp+1A0h+var_140+10h]
0x18003d191  lea     rcx, [rsp+1A0h+var_158]; pvarg
0x18003d196  call    cs:__imp_VariantInit
0x18003d19c  nop
0x18003d19d  movups  xmm6, xmmword ptr [rsp+1A0h+var_158]
0x18003d1a2  movsd   xmm7, qword ptr [rsp+1A0h+var_158+10h]
0x18003d1a8  lea     rcx, [rsp+1A0h+var_170]; pvarg
0x18003d1ad  call    cs:__imp_VariantInit
0x18003d1b3  nop
0x18003d1b4  movups  xmm0, xmmword ptr [rsp+1A0h+var_170]
0x18003d1b9  movsd   xmm1, qword ptr [rsp+1A0h+var_170+10h]
0x18003d1bf  movaps  [rbp+0A0h+var_100], xmm10
0x18003d1c4  movsd   [rbp+0A0h+var_F0], xmm11
0x18003d1ca  movaps  [rbp+0A0h+var_E0], xmm8
0x18003d1cf  movsd   [rbp+0A0h+var_D0], xmm9
0x18003d1d5  movaps  [rbp+0A0h+var_C0], xmm6
0x18003d1d9  movsd   [rbp+0A0h+var_B0], xmm7
0x18003d1de  movaps  [rbp+0A0h+var_A0], xmm0
0x18003d1e2  movsd   [rbp+0A0h+var_90], xmm1
0x18003d1e7  lea     rax, [rbp+0A0h+var_100]
0x18003d1eb  mov     [rsp+1A0h+ppv], rax
0x18003d1f0  lea     r9, [rbp+0A0h+var_E0]
0x18003d1f4  lea     r8, [rbp+0A0h+var_C0]
0x18003d1f8  lea     rdx, [rbp+0A0h+var_A0]
0x18003d1fc  mov     rcx, rdi
0x18003d1ff  mov     rax, rbx
0x18003d202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d207  mov     ebx, eax
0x18003d209  lea     rcx, [rsp+1A0h+var_170]; this
0x18003d20e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d213  nop
0x18003d214  lea     rcx, [rsp+1A0h+var_158]; this
0x18003d219  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d21e  nop
0x18003d21f  lea     rcx, [rsp+1A0h+var_140]; this
0x18003d224  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d229  nop
0x18003d22a  lea     rcx, [rsp+1A0h+pvarg]; this
0x18003d22f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003d234  test    ebx, ebx
0x18003d236  jns     short loc_18003D272
0x18003d238  mov     rax, cs:WPP_GLOBAL_Control
0x18003d23f  cmp     rax, rsi
0x18003d242  jz      loc_18003D45D
0x18003d248  test    byte ptr [rax+1Ch], 8
0x18003d24c  jz      loc_18003D45D
0x18003d252  cmp     byte ptr [rax+19h], 2
0x18003d256  jb      loc_18003D45D
0x18003d25c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d261  mov     edx, 22h ; '"'
0x18003d266  lea     rcx, aItaskserviceCo; "ITaskService::Connect failed"
0x18003d26d  jmp     loc_18003D43D
0x18003d272  xor     r8d, r8d; int
0x18003d275  lea     rdx, [rbp+0A0h+arg_0]; struct ITaskFolder **
0x18003d27c  mov     rcx, [rbp+0A0h+arg_8]; struct ITaskService *
0x18003d283  call    ?GetPersonalTaskFolder@@YAJPEAUITaskService@@PEAPEAUITaskFolder@@H@Z; GetPersonalTaskFolder(ITaskService *,ITaskFolder * *,int)
0x18003d288  mov     ebx, eax
0x18003d28a  test    eax, eax
0x18003d28c  jns     short loc_18003D2C8
0x18003d28e  mov     rax, cs:WPP_GLOBAL_Control
0x18003d295  cmp     rax, rsi
0x18003d298  jz      loc_18003D45D
0x18003d29e  test    byte ptr [rax+1Ch], 8
0x18003d2a2  jz      loc_18003D45D
0x18003d2a8  cmp     byte ptr [rax+19h], 2
0x18003d2ac  jb      loc_18003D45D
0x18003d2b2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d2b7  mov     edx, 23h ; '#'
0x18003d2bc  lea     rcx, aGetpersonaltas_0; "GetPersonalTaskFolder failed"
0x18003d2c3  jmp     loc_18003D43D
0x18003d2c8  lea     rdx, aUpdateConnecti_1; "Update connections (daily)"
0x18003d2cf  lea     rcx, [rbp+0A0h+arg_10]; this
0x18003d2d6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003d2db  nop
0x18003d2dc  mov     rcx, [rax]; struct ITaskService *
0x18003d2df  test    rcx, rcx
0x18003d2e2  jz      short loc_18003D2E9
0x18003d2e4  mov     r8, [rcx]
0x18003d2e7  jmp     short loc_18003D2EC
0x18003d2e9  xor     r8d, r8d; unsigned __int16 *
0x18003d2ec  mov     rdx, [rbp+0A0h+arg_0]; struct ITaskFolder *
0x18003d2f3  call    ?DeleteTask@@YAJPEAUITaskService@@PEAUITaskFolder@@PEAG@Z; DeleteTask(ITaskService *,ITaskFolder *,ushort *)
0x18003d2f8  mov     ebx, eax
0x18003d2fa  lea     rcx, [rbp+0A0h+arg_10]; this
0x18003d301  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d306  test    ebx, ebx
0x18003d308  jns     short loc_18003D352
0x18003d30a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d311  cmp     rcx, rsi
0x18003d314  jz      short loc_18003D352
0x18003d316  test    byte ptr [rcx+1Ch], 8
0x18003d31a  jz      short loc_18003D352
0x18003d31c  cmp     byte ptr [rcx+19h], 2
0x18003d320  jb      short loc_18003D352
0x18003d322  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d327  mov     edx, 24h ; '$'
0x18003d32c  mov     dword ptr [rsp+1A0h+var_178], ebx
0x18003d330  lea     rcx, aDeletetaskFail; "DeleteTask failed for the daily update "...
0x18003d337  mov     [rsp+1A0h+ppv], rcx
0x18003d33c  mov     r9d, eax
0x18003d33f  mov     r8, r14
0x18003d342  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d349  mov     rcx, [rcx+10h]
0x18003d34d  call    WPP_SF_DsD
0x18003d352  lea     rdx, aUpdateConnecti; "Update connections (at login, if needed"...
0x18003d359  lea     rcx, [rbp+0A0h+arg_10]; this
0x18003d360  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003d365  nop
0x18003d366  mov     r8, [rax]
0x18003d369  test    r8, r8
0x18003d36c  jz      short loc_18003D371
0x18003d36e  mov     r8, [r8]; unsigned __int16 *
0x18003d371  mov     rdx, [rbp+0A0h+arg_0]; struct ITaskFolder *
0x18003d378  call    ?DeleteTask@@YAJPEAUITaskService@@PEAUITaskFolder@@PEAG@Z; DeleteTask(ITaskService *,ITaskFolder *,ushort *)
0x18003d37d  mov     ebx, eax
0x18003d37f  lea     rcx, [rbp+0A0h+arg_10]; this
0x18003d386  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d38b  test    ebx, ebx
0x18003d38d  jns     short loc_18003D3D7
0x18003d38f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d396  cmp     rcx, rsi
0x18003d399  jz      short loc_18003D3D7
0x18003d39b  test    byte ptr [rcx+1Ch], 8
0x18003d39f  jz      short loc_18003D3D7
0x18003d3a1  cmp     byte ptr [rcx+19h], 2
0x18003d3a5  jb      short loc_18003D3D7
0x18003d3a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d3ac  mov     edx, 25h ; '%'
0x18003d3b1  mov     dword ptr [rsp+1A0h+var_178], ebx
0x18003d3b5  lea     rcx, aDeletetaskFail_1; "DeleteTask failed for the login update "...
0x18003d3bc  mov     [rsp+1A0h+ppv], rcx
0x18003d3c1  mov     r9d, eax
0x18003d3c4  mov     r8, r14
0x18003d3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3ce  mov     rcx, [rcx+10h]
0x18003d3d2  call    WPP_SF_DsD
0x18003d3d7  lea     rdx, aReportConnecti; "Report connection status"
0x18003d3de  lea     rcx, [rbp+0A0h+arg_10]; this
0x18003d3e5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003d3ea  nop
0x18003d3eb  mov     r8, [rax]
0x18003d3ee  test    r8, r8
0x18003d3f1  jz      short loc_18003D3F6
0x18003d3f3  mov     r8, [r8]; unsigned __int16 *
0x18003d3f6  mov     rdx, [rbp+0A0h+arg_0]; struct ITaskFolder *
0x18003d3fd  call    ?DeleteTask@@YAJPEAUITaskService@@PEAUITaskFolder@@PEAG@Z; DeleteTask(ITaskService *,ITaskFolder *,ushort *)
0x18003d402  mov     ebx, eax
0x18003d404  lea     rcx, [rbp+0A0h+arg_10]; this
0x18003d40b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003d410  test    ebx, ebx
0x18003d412  jns     short loc_18003D45D
0x18003d414  mov     rax, cs:WPP_GLOBAL_Control
0x18003d41b  cmp     rax, rsi
0x18003d41e  jz      short loc_18003D45D
0x18003d420  test    byte ptr [rax+1Ch], 8
0x18003d424  jz      short loc_18003D45D
0x18003d426  cmp     byte ptr [rax+19h], 2
0x18003d42a  jb      short loc_18003D45D
0x18003d42c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003d431  mov     edx, 26h ; '&'
0x18003d436  lea     rcx, aDeletetaskFail_2; "DeleteTask failed for the notification "...
0x18003d43d  mov     dword ptr [rsp+1A0h+var_178], ebx
0x18003d441  mov     [rsp+1A0h+ppv], rcx
0x18003d446  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d44d  mov     r9d, eax
0x18003d450  mov     r8, r14
0x18003d453  mov     rcx, [rcx+10h]
0x18003d457  call    WPP_SF_DsD
0x18003d45c  nop
0x18003d45d  lea     rcx, [rbp+0A0h+arg_0]
0x18003d464  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18003d469  nop
0x18003d46a  lea     rcx, [rbp+0A0h+arg_8]
0x18003d471  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18003d476  mov     eax, ebx
0x18003d478  lea     r11, [rsp+1A0h+var_20]
0x18003d480  movaps  xmm6, xmmword ptr [r11-10h]
0x18003d485  movaps  xmm7, xmmword ptr [r11-20h]
0x18003d48a  movaps  xmm8, xmmword ptr [r11-30h]
0x18003d48f  movaps  xmm9, xmmword ptr [r11-40h]
0x18003d494  movaps  xmm10, xmmword ptr [r11-50h]
0x18003d499  movaps  xmm11, xmmword ptr [r11-60h]
0x18003d49e  mov     rsp, r11
0x18003d4a1  pop     r14
0x18003d4a3  pop     rdi
0x18003d4a4  pop     rsi
0x18003d4a5  pop     rbx
0x18003d4a6  pop     rbp
0x18003d4a7  retn
```
