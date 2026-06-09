# GetPolicyTask(IRegisteredTask * *,int)

- ea: `0x18000f090`
- end: `0x18000f5db`
- name: `?GetPolicyTask@@YAJPEAPEAUIRegisteredTask@@H@Z`
- size: `1355`
- prototype: `__int64 __fastcall(struct IRegisteredTask **, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000f5f0`

## callees

- `0x1800044bf`
- `0x1800054c4`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000efc4`
- `0x18000f090`
- `0x18000ff00`
- `0x180042fd0`
- `0x180043df8`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000f123`
- `ole32!CoCreateInstance` at `0x18000f123`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1a4`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1ba`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1d1`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1e7`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1a4`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1ba`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1d1`
- `OLEAUT32!__imp_VariantInit` at `0x18000f1e7`

## string_xrefs

- `0x18000f163`: `CoCreateInstance failed for ITaskService`
- `0x18000f2b1`: `ITaskService::Connect failed`
- `0x18000f30e`: `GetPersonalTaskFolder failed`
- `0x18000f4f4`: `MasterCreateTask failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall GetPolicyTask(struct IRegisteredTask **a1, int a2)
{
  HRESULT Instance; // ebx
  unsigned int v5; // eax
  int v6; // edx
  const char *v7; // rcx
  struct ITaskService *v8; // rdi
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rbx
  __int128 v10; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v12; // xmm8
  IRecordInfo *v13; // xmm9_8
  __int128 v14; // xmm6
  __int64 v15; // xmm7_8
  struct ITaskFolder *v16; // rbx
  HRESULT (__stdcall *GetTask)(ITaskFolder *, BSTR, IRegisteredTask **); // rdi
  _QWORD *v18; // rdx
  int v19; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 *v28; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v29; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v30; // [rsp+48h] [rbp-C0h] BYREF
  __int64 *v31; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v32; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v33; // [rsp+70h] [rbp-98h] BYREF
  __int64 v34; // [rsp+88h] [rbp-80h]
  VARIANTARG v35; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v37; // [rsp+C8h] [rbp-40h] BYREF
  int v38; // [rsp+D0h] [rbp-38h]
  int v39; // [rsp+D4h] [rbp-34h]
  __int64 v40; // [rsp+D8h] [rbp-30h]
  int v41; // [rsp+E4h] [rbp-24h]
  __int64 v42; // [rsp+E8h] [rbp-20h]
  int v43; // [rsp+F0h] [rbp-18h]
  int v44; // [rsp+F4h] [rbp-14h]
  __int64 v45; // [rsp+F8h] [rbp-10h]
  int v46; // [rsp+110h] [rbp+8h]
  __int64 v47; // [rsp+118h] [rbp+10h]
  __int64 v48; // [rsp+128h] [rbp+20h]
  __int128 v49; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v50; // [rsp+148h] [rbp+40h]
  __int128 v51; // [rsp+158h] [rbp+50h] BYREF
  IRecordInfo *v52; // [rsp+168h] [rbp+60h]
  __int128 v53; // [rsp+178h] [rbp+70h] BYREF
  __int64 v54; // [rsp+188h] [rbp+80h]
  __int128 v55; // [rsp+198h] [rbp+90h] BYREF
  __int64 v56; // [rsp+1A8h] [rbp+A0h]
  struct ITaskService *ppv; // [rsp+258h] [rbp+150h] BYREF
  struct ITaskFolder *v58; // [rsp+260h] [rbp+158h] BYREF

  v48 = -2;
  memset_0(&v37, 0, 0x60u);
  ppv = 0;
  v58 = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v8 = ppv;
    Connect = ppv->lpVtbl->Connect;
    VariantInit(&pvarg);
    v10 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v35);
    v12 = *(_OWORD *)&v35.vt;
    v13 = v35.pRecInfo;
    VariantInit((VARIANTARG *)&v33.decVal.8);
    v14 = *(_OWORD *)&v33.decVal.Lo32;
    v15 = v34;
    VariantInit((VARIANTARG *)&v32.decVal.8);
    v49 = v10;
    v50 = pRecInfo;
    v51 = v12;
    v52 = v13;
    v53 = v14;
    v54 = v15;
    v55 = *(_OWORD *)&v32.decVal.Lo32;
    v56 = *(_QWORD *)&v33.vt;
    Instance = ((__int64 (__fastcall *)(struct ITaskService *, __int128 *, __int128 *, __int128 *, __int128 *))Connect)(
                 v8,
                 &v55,
                 &v53,
                 &v51,
                 &v49);
    _variant_t::~_variant_t((_variant_t *)&v32.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v33.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v35);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( Instance >= 0 )
    {
      Instance = GetPersonalTaskFolder(ppv, &v58, 1);
      if ( Instance >= 0 )
      {
        v16 = v58;
        GetTask = v58->lpVtbl->GetTask;
        v18 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v28, L"Process policy");
        if ( v18 )
          v18 = (_QWORD *)*v18;
        v19 = ((__int64 (__fastcall *)(struct ITaskFolder *, _QWORD *, struct IRegisteredTask **))GetTask)(v16, v18, a1);
        _bstr_t::_Free((_bstr_t *)&v28);
        if ( v19 < 0 && a2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
              CurrentThreadActivityIdPrefix,
              v19);
          }
          _bstr_t::_bstr_t((_bstr_t *)&v28, L"Process policy");
          _bstr_t::_bstr_t((_bstr_t *)&v32, L"PT22H");
          _bstr_t::_bstr_t((_bstr_t *)&v31, L"{E444E1B9-502C-44f9-B714-30DA330D0E8E}");
          _bstr_t::_bstr_t((_bstr_t *)&v30, L"PT0S");
          _bstr_t::_bstr_t((_bstr_t *)&v29, L"PT10M");
          memset_0(&v37, 0, 0x60u);
          if ( v28 )
            v21 = *v28;
          else
            v21 = 0;
          v37 = v21;
          v38 = 15604;
          v43 = 1;
          v39 = 1;
          if ( *(_QWORD *)&v32.vt )
            v22 = **(_QWORD **)&v32.vt;
          else
            v22 = 0;
          v40 = v22;
          v46 = 1;
          if ( v31 )
            v23 = *v31;
          else
            v23 = 0;
          v47 = v23;
          v44 = 2;
          if ( v30 )
            v24 = *v30;
          else
            v24 = 0;
          v45 = v24;
          v41 = 255;
          if ( v29 )
            v25 = *v29;
          else
            v25 = 0;
          v42 = v25;
          Instance = MasterCreateTask(ppv, v58, a1, (const struct TaskParams *)&v37);
          if ( Instance < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v26 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                (unsigned int)WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
                v26,
                (__int64)"MasterCreateTask failed",
                Instance);
            }
            _bstr_t::_Free((_bstr_t *)&v29);
            _bstr_t::_Free((_bstr_t *)&v30);
            _bstr_t::_Free((_bstr_t *)&v31);
            _bstr_t::_Free((_bstr_t *)&v32);
            _bstr_t::_Free((_bstr_t *)&v28);
            goto LABEL_48;
          }
          _bstr_t::_Free((_bstr_t *)&v29);
          _bstr_t::_Free((_bstr_t *)&v30);
          _bstr_t::_Free((_bstr_t *)&v31);
          _bstr_t::_Free((_bstr_t *)&v32);
          _bstr_t::_Free((_bstr_t *)&v28);
        }
        Instance = 0;
        goto LABEL_48;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 28;
        v7 = "GetPersonalTaskFolder failed";
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 27;
      v7 = "ITaskService::Connect failed";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 26;
    v7 = "CoCreateInstance failed for ITaskService";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids,
      v5,
      (__int64)v7,
      Instance);
  }
LABEL_48:
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v58);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000f090  mov     rax, rsp
0x18000f093  push    rbp
0x18000f094  push    rsi
0x18000f095  push    rdi
0x18000f096  push    r14
0x18000f098  push    r15
0x18000f09a  lea     rbp, [rax-138h]
0x18000f0a1  sub     rsp, 210h
0x18000f0a8  mov     [rbp+130h+var_110], 0FFFFFFFFFFFFFFFEh
0x18000f0b0  mov     [rax+8], rbx
0x18000f0b4  movaps  xmmword ptr [rax-38h], xmm6
0x18000f0b8  movaps  xmmword ptr [rax-48h], xmm7
0x18000f0bc  movaps  xmmword ptr [rax-58h], xmm8
0x18000f0c1  movaps  xmmword ptr [rax-68h], xmm9
0x18000f0c6  movaps  xmmword ptr [rax-78h], xmm10
0x18000f0cb  movaps  xmmword ptr [rax-88h], xmm11
0x18000f0d3  mov     r14d, edx
0x18000f0d6  mov     rsi, rcx
0x18000f0d9  xor     edx, edx; Val
0x18000f0db  lea     r8d, [rdx+60h]; Size
0x18000f0df  lea     rcx, [rbp+130h+var_170]; void *
0x18000f0e3  call    memset_0
0x18000f0e8  mov     [rbp+130h+arg_10], 0
0x18000f0f3  mov     [rbp+130h+arg_18], 0
0x18000f0fe  lea     rax, [rbp+130h+arg_10]
0x18000f105  mov     [rsp+230h+ppv], rax; ppv
0x18000f10a  lea     r9, IID_ITaskService; riid
0x18000f111  mov     r15d, 1
0x18000f117  mov     r8d, r15d; dwClsContext
0x18000f11a  xor     edx, edx; pUnkOuter
0x18000f11c  lea     rcx, CLSID_TaskScheduler; rclsid
0x18000f123  call    cs:__imp_CoCreateInstance
0x18000f129  mov     ebx, eax
0x18000f12b  test    eax, eax
0x18000f12d  jns     short loc_18000F192
0x18000f12f  lea     rdi, WPP_GLOBAL_Control
0x18000f136  mov     rax, cs:WPP_GLOBAL_Control
0x18000f13d  cmp     rax, rdi
0x18000f140  jz      loc_18000F58B
0x18000f146  test    byte ptr [rax+1Ch], 8
0x18000f14a  jz      loc_18000F58B
0x18000f150  cmp     byte ptr [rax+19h], 2
0x18000f154  jb      loc_18000F58B
0x18000f15a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f15f  lea     edx, [r15+19h]
0x18000f163  lea     rcx, aCocreateinstan_3; "CoCreateInstance failed for ITaskServic"...
0x18000f16a  mov     dword ptr [rsp+230h+var_208], ebx
0x18000f16e  mov     [rsp+230h+ppv], rcx
0x18000f173  mov     r9d, eax
0x18000f176  lea     r8, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids
0x18000f17d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f184  mov     rcx, [rcx+10h]
0x18000f188  call    WPP_SF_DsD
0x18000f18d  jmp     loc_18000F58B
0x18000f192  mov     rdi, [rbp+130h+arg_10]
0x18000f199  mov     rax, [rdi]
0x18000f19c  mov     rbx, [rax+50h]
0x18000f1a0  lea     rcx, [rbp+130h+pvarg]; pvarg
0x18000f1a4  call    cs:__imp_VariantInit
0x18000f1aa  nop
0x18000f1ab  movups  xmm10, xmmword ptr [rbp+130h+pvarg]
0x18000f1b0  movsd   xmm11, qword ptr [rbp+130h+pvarg+10h]
0x18000f1b6  lea     rcx, [rbp+130h+var_1A8]; pvarg
0x18000f1ba  call    cs:__imp_VariantInit
0x18000f1c0  nop
0x18000f1c1  movups  xmm8, xmmword ptr [rbp+130h+var_1A8]
0x18000f1c6  movsd   xmm9, qword ptr [rbp+130h+var_1A8+10h]
0x18000f1cc  lea     rcx, [rsp+230h+var_1C8+8]; pvarg
0x18000f1d1  call    cs:__imp_VariantInit
0x18000f1d7  nop
0x18000f1d8  movups  xmm6, xmmword ptr [rsp+230h+var_1C8+8]
0x18000f1dd  movsd   xmm7, [rbp+130h+var_1B0]
0x18000f1e2  lea     rcx, [rsp+230h+var_1E0+8]; pvarg
0x18000f1e7  call    cs:__imp_VariantInit
0x18000f1ed  nop
0x18000f1ee  movups  xmm0, xmmword ptr [rsp+230h+var_1E0+8]
0x18000f1f3  movsd   xmm1, qword ptr [rsp+230h+var_1C8]
0x18000f1f9  movaps  [rbp+130h+var_100], xmm10
0x18000f1fe  movsd   [rbp+130h+var_F0], xmm11
0x18000f204  movaps  [rbp+130h+var_E0], xmm8
0x18000f209  movsd   [rbp+130h+var_D0], xmm9
0x18000f20f  movaps  [rbp+130h+var_C0], xmm6
0x18000f213  movsd   [rbp+130h+var_B0], xmm7
0x18000f21b  movaps  [rbp+130h+var_A0], xmm0
0x18000f222  movsd   [rbp+130h+var_90], xmm1
0x18000f22a  lea     rax, [rbp+130h+var_100]
0x18000f22e  mov     [rsp+230h+ppv], rax
0x18000f233  lea     r9, [rbp+130h+var_E0]
0x18000f237  lea     r8, [rbp+130h+var_C0]
0x18000f23b  lea     rdx, [rbp+130h+var_A0]
0x18000f242  mov     rcx, rdi
0x18000f245  mov     rax, rbx
0x18000f248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f24d  mov     ebx, eax
0x18000f24f  lea     rcx, [rsp+230h+var_1E0+8]; this
0x18000f254  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000f259  nop
0x18000f25a  lea     rcx, [rsp+230h+var_1C8+8]; this
0x18000f25f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000f264  nop
0x18000f265  lea     rcx, [rbp+130h+var_1A8]; this
0x18000f269  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000f26e  nop
0x18000f26f  lea     rcx, [rbp+130h+pvarg]; this
0x18000f273  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18000f278  test    ebx, ebx
0x18000f27a  jns     short loc_18000F2BD
0x18000f27c  lea     rdi, WPP_GLOBAL_Control
0x18000f283  mov     rax, cs:WPP_GLOBAL_Control
0x18000f28a  cmp     rax, rdi
0x18000f28d  jz      loc_18000F58B
0x18000f293  test    byte ptr [rax+1Ch], 8
0x18000f297  jz      loc_18000F58B
0x18000f29d  cmp     byte ptr [rax+19h], 2
0x18000f2a1  jb      loc_18000F58B
0x18000f2a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f2ac  mov     edx, 1Bh
0x18000f2b1  lea     rcx, aItaskserviceCo; "ITaskService::Connect failed"
0x18000f2b8  jmp     loc_18000F16A
0x18000f2bd  mov     r8d, r15d; int
0x18000f2c0  lea     rdx, [rbp+130h+arg_18]; struct ITaskFolder **
0x18000f2c7  mov     rcx, [rbp+130h+arg_10]; struct ITaskService *
0x18000f2ce  call    ?GetPersonalTaskFolder@@YAJPEAUITaskService@@PEAPEAUITaskFolder@@H@Z; GetPersonalTaskFolder(ITaskService *,ITaskFolder * *,int)
0x18000f2d3  mov     ebx, eax
0x18000f2d5  test    eax, eax
0x18000f2d7  jns     short loc_18000F31A
0x18000f2d9  lea     rdi, WPP_GLOBAL_Control
0x18000f2e0  mov     rax, cs:WPP_GLOBAL_Control
0x18000f2e7  cmp     rax, rdi
0x18000f2ea  jz      loc_18000F58B
0x18000f2f0  test    byte ptr [rax+1Ch], 8
0x18000f2f4  jz      loc_18000F58B
0x18000f2fa  cmp     byte ptr [rax+19h], 2
0x18000f2fe  jb      loc_18000F58B
0x18000f304  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f309  mov     edx, 1Ch
0x18000f30e  lea     rcx, aGetpersonaltas_0; "GetPersonalTaskFolder failed"
0x18000f315  jmp     loc_18000F16A
0x18000f31a  mov     rbx, [rbp+130h+arg_18]
0x18000f321  mov     rax, [rbx]
0x18000f324  mov     rdi, [rax+68h]
0x18000f328  lea     rdx, aProcessPolicy; "Process policy"
0x18000f32f  lea     rcx, [rsp+230h+var_200]; this
0x18000f334  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f339  nop
0x18000f33a  mov     rdx, [rax]
0x18000f33d  test    rdx, rdx
0x18000f340  jz      short loc_18000F345
0x18000f342  mov     rdx, [rdx]
0x18000f345  mov     r8, rsi
0x18000f348  mov     rcx, rbx
0x18000f34b  mov     rax, rdi
0x18000f34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f353  mov     ebx, eax
0x18000f355  lea     rcx, [rsp+230h+var_200]; this
0x18000f35a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f35f  test    ebx, ebx
0x18000f361  jns     loc_18000F589
0x18000f367  test    r14d, r14d
0x18000f36a  jz      loc_18000F589
0x18000f370  lea     rdi, WPP_GLOBAL_Control
0x18000f377  mov     rax, cs:WPP_GLOBAL_Control
0x18000f37e  cmp     rax, rdi
0x18000f381  jz      short loc_18000F3B7
0x18000f383  test    [rax+1Ch], r15b
0x18000f387  jz      short loc_18000F3B7
0x18000f389  cmp     byte ptr [rax+19h], 2
0x18000f38d  jb      short loc_18000F3B7
0x18000f38f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f394  mov     edx, 1Dh
0x18000f399  mov     dword ptr [rsp+230h+ppv], ebx
0x18000f39d  mov     r9d, eax
0x18000f3a0  lea     r8, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids
0x18000f3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3ae  mov     rcx, [rcx+10h]
0x18000f3b2  call    WPP_SF_Dd
0x18000f3b7  lea     rdx, aProcessPolicy; "Process policy"
0x18000f3be  lea     rcx, [rsp+230h+var_200]; this
0x18000f3c3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f3c8  nop
0x18000f3c9  lea     rdx, aPt22h; "PT22H"
0x18000f3d0  lea     rcx, [rsp+230h+var_1E0]; this
0x18000f3d5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f3da  nop
0x18000f3db  lea     rdx, aE444e1b9502c44; "{E444E1B9-502C-44f9-B714-30DA330D0E8E}"
0x18000f3e2  lea     rcx, [rsp+230h+var_1E8]; this
0x18000f3e7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f3ec  nop
0x18000f3ed  lea     rdx, aPt0s; "PT0S"
0x18000f3f4  lea     rcx, [rsp+230h+var_1F0]; this
0x18000f3f9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f3fe  nop
0x18000f3ff  lea     rdx, aPt10m; "PT10M"
0x18000f406  lea     rcx, [rsp+230h+var_1F8]; this
0x18000f40b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000f410  nop
0x18000f411  xor     edx, edx; Val
0x18000f413  lea     r8d, [rdx+60h]; Size
0x18000f417  lea     rcx, [rbp+130h+var_170]; void *
0x18000f41b  call    memset_0
0x18000f420  mov     rax, [rsp+230h+var_200]
0x18000f425  test    rax, rax
0x18000f428  jz      short loc_18000F42F
0x18000f42a  mov     rcx, [rax]
0x18000f42d  jmp     short loc_18000F431
0x18000f42f  xor     ecx, ecx
0x18000f431  mov     [rbp+130h+var_170], rcx
0x18000f435  mov     [rbp+130h+var_168], 3CF4h
0x18000f43c  mov     [rbp+130h+var_148], r15d
0x18000f440  mov     [rbp+130h+var_164], r15d
0x18000f444  mov     rax, qword ptr [rsp+230h+var_1E0]
0x18000f449  test    rax, rax
0x18000f44c  jz      short loc_18000F453
0x18000f44e  mov     rcx, [rax]
0x18000f451  jmp     short loc_18000F455
0x18000f453  xor     ecx, ecx
0x18000f455  mov     [rbp+130h+var_160], rcx
0x18000f459  mov     [rbp+130h+var_128], r15d
0x18000f45d  mov     rax, [rsp+230h+var_1E8]
0x18000f462  test    rax, rax
0x18000f465  jz      short loc_18000F46C
0x18000f467  mov     rcx, [rax]
0x18000f46a  jmp     short loc_18000F46E
0x18000f46c  xor     ecx, ecx
0x18000f46e  mov     [rbp+130h+var_120], rcx
0x18000f472  mov     [rbp+130h+var_144], 2
0x18000f479  mov     rax, [rsp+230h+var_1F0]
0x18000f47e  test    rax, rax
0x18000f481  jz      short loc_18000F488
0x18000f483  mov     rcx, [rax]
0x18000f486  jmp     short loc_18000F48A
0x18000f488  xor     ecx, ecx
0x18000f48a  mov     [rbp+130h+var_140], rcx
0x18000f48e  mov     [rbp+130h+var_154], 0FFh
0x18000f495  mov     rax, [rsp+230h+var_1F8]
0x18000f49a  test    rax, rax
0x18000f49d  jz      short loc_18000F4A4
0x18000f49f  mov     rcx, [rax]
0x18000f4a2  jmp     short loc_18000F4A6
0x18000f4a4  xor     ecx, ecx
0x18000f4a6  mov     [rbp+130h+var_150], rcx
0x18000f4aa  lea     r9, [rbp+130h+var_170]; struct TaskParams *
0x18000f4ae  mov     r8, rsi; struct IRegisteredTask **
0x18000f4b1  mov     rdx, [rbp+130h+arg_18]; struct ITaskFolder *
0x18000f4b8  mov     rcx, [rbp+130h+arg_10]; struct ITaskService *
0x18000f4bf  call    ?MasterCreateTask@@YAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@AEBUTaskParams@@@Z; MasterCreateTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,TaskParams const &)
0x18000f4c4  mov     ebx, eax
0x18000f4c6  test    eax, eax
0x18000f4c8  jns     loc_18000F553
0x18000f4ce  mov     rax, cs:WPP_GLOBAL_Control
0x18000f4d5  cmp     rax, rdi
0x18000f4d8  jz      short loc_18000F51B
0x18000f4da  test    byte ptr [rax+1Ch], 8
0x18000f4de  jz      short loc_18000F51B
0x18000f4e0  cmp     byte ptr [rax+19h], 2
0x18000f4e4  jb      short loc_18000F51B
0x18000f4e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f4eb  mov     edx, 1Eh
0x18000f4f0  mov     dword ptr [rsp+230h+var_208], ebx
0x18000f4f4  lea     rcx, aMastercreateta; "MasterCreateTask failed"
0x18000f4fb  mov     [rsp+230h+ppv], rcx
0x18000f500  mov     r9d, eax
0x18000f503  lea     r8, WPP_0c67c371c06c33770c4a1ca283377c32_Traceguids
0x18000f50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f511  mov     rcx, [rcx+10h]
0x18000f515  call    WPP_SF_DsD
0x18000f51a  nop
0x18000f51b  lea     rcx, [rsp+230h+var_1F8]; this
0x18000f520  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f525  nop
0x18000f526  lea     rcx, [rsp+230h+var_1F0]; this
0x18000f52b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f530  nop
0x18000f531  lea     rcx, [rsp+230h+var_1E8]; this
0x18000f536  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f53b  nop
0x18000f53c  lea     rcx, [rsp+230h+var_1E0]; this
0x18000f541  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f546  nop
0x18000f547  lea     rcx, [rsp+230h+var_200]; this
0x18000f54c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f551  jmp     short loc_18000F58B
0x18000f553  lea     rcx, [rsp+230h+var_1F8]; this
0x18000f558  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f55d  nop
0x18000f55e  lea     rcx, [rsp+230h+var_1F0]; this
0x18000f563  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f568  nop
0x18000f569  lea     rcx, [rsp+230h+var_1E8]; this
0x18000f56e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f573  nop
0x18000f574  lea     rcx, [rsp+230h+var_1E0]; this
0x18000f579  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f57e  nop
0x18000f57f  lea     rcx, [rsp+230h+var_200]; this
0x18000f584  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000f589  xor     ebx, ebx
0x18000f58b  lea     rcx, [rbp+130h+arg_18]
0x18000f592  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18000f597  nop
  ... truncated ...
```
