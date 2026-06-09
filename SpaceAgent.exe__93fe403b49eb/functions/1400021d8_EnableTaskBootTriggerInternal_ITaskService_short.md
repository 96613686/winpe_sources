# EnableTaskBootTriggerInternal(ITaskService *,short)

- ea: `0x1400021d8`
- end: `0x140002663`
- name: `?EnableTaskBootTriggerInternal@@YAXPEAUITaskService@@F@Z`
- size: `1163`
- prototype: `void __fastcall(struct ITaskService *, unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1400020b8`

## callees

- `0x140001200`
- `0x14000120c`
- `0x14000124c`
- `0x140001f5c`
- `0x140002000`
- `0x1400021d8`
- `0x140003624`
- `0x140020010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140002245`
- `OLEAUT32!__imp_SysAllocString` at `0x140002245`
- `OLEAUT32!__imp_SysFreeString` at `0x140002600`
- `OLEAUT32!__imp_SysFreeString` at `0x140002600`
- `OLEAUT32!__imp_VariantInit` at `0x140002295`
- `OLEAUT32!__imp_VariantInit` at `0x1400022aa`
- `OLEAUT32!__imp_VariantInit` at `0x1400022bf`
- `OLEAUT32!__imp_VariantInit` at `0x1400022d2`
- `OLEAUT32!__imp_VariantInit` at `0x1400024f4`
- `OLEAUT32!__imp_VariantInit` at `0x14000250d`
- `OLEAUT32!__imp_VariantInit` at `0x140002520`
- `OLEAUT32!__imp_VariantInit` at `0x140002295`
- `OLEAUT32!__imp_VariantInit` at `0x1400022aa`
- `OLEAUT32!__imp_VariantInit` at `0x1400022bf`
- `OLEAUT32!__imp_VariantInit` at `0x1400022d2`
- `OLEAUT32!__imp_VariantInit` at `0x1400024f4`
- `OLEAUT32!__imp_VariantInit` at `0x14000250d`
- `OLEAUT32!__imp_VariantInit` at `0x140002520`

## string_xrefs

- `0x140002233`: `\Microsoft\Windows\SpacePort\SpaceAgentTask`

## pseudocode

```c
void __fastcall EnableTaskBootTriggerInternal(struct ITaskService *a1, unsigned __int16 a2)
{
  volatile signed __int32 *v4; // rax
  volatile signed __int32 *v5; // rbx
  BSTR v6; // rax
  struct ITaskServiceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *Connect)(ITaskService *, VARIANT, VARIANT, VARIANT, VARIANT); // rdi
  __int128 v9; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *v14; // xmm7_8
  int i; // edi
  __int64 v16; // rcx
  __int64 v17; // r14
  void (__fastcall *v18)(__int64, __int64, __int64, __int64, VARIANTARG *, __int128 *, int, VARIANTARG *, __int64 *); // rsi
  __int128 v19; // xmm8
  int v20; // edi
  IRecordInfo *v21; // xmm9_8
  __int128 v22; // xmm6
  IRecordInfo *v23; // xmm7_8
  __int64 v24; // rdx
  void *v25; // rcx
  __int64 v26; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+70h] [rbp-98h] BYREF
  __int64 v30; // [rsp+78h] [rbp-90h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h] BYREF
  __int64 v32; // [rsp+88h] [rbp-80h] BYREF
  __int64 v33; // [rsp+90h] [rbp-78h] BYREF
  __int64 v34; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v35; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v36; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v38; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v39; // [rsp+108h] [rbp+0h] BYREF
  IRecordInfo *v40; // [rsp+118h] [rbp+10h]
  VARIANTARG v41; // [rsp+128h] [rbp+20h] BYREF
  VARIANTARG v42; // [rsp+148h] [rbp+40h] BYREF
  __int128 v43; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v44; // [rsp+178h] [rbp+70h]
  int v45; // [rsp+228h] [rbp+120h] BYREF
  int v46; // [rsp+230h] [rbp+128h] BYREF

  v4 = (volatile signed __int32 *)operator new(0x18u);
  v5 = v4;
  if ( !v4
    || (*((_QWORD *)v4 + 1) = 0,
        *((_DWORD *)v4 + 4) = 1,
        v6 = SysAllocString(L"\\Microsoft\\Windows\\SpacePort\\SpaceAgentTask"),
        (*(_QWORD *)v5 = v6) == 0) )
  {
    _com_issue_error(-2147024882);
  }
  lpVtbl = a1->lpVtbl;
  v46 = 0;
  LODWORD(v26) = 0;
  v45 = 0;
  Connect = lpVtbl->Connect;
  v31 = 0;
  v33 = 0;
  v28 = 0;
  v32 = 0;
  v34 = 0;
  v30 = 0;
  v29 = 0;
  VariantInit(&pvarg);
  v9 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v36);
  v11 = *(_OWORD *)&v36.vt;
  v12 = v36.pRecInfo;
  VariantInit(&v35);
  v13 = *(_OWORD *)&v35.vt;
  v14 = v35.pRecInfo;
  VariantInit(&v42);
  v41 = v42;
  v43 = v9;
  v44 = pRecInfo;
  *(_OWORD *)&v38.vt = v11;
  v38.pRecInfo = v12;
  v39 = v13;
  v40 = v14;
  LODWORD(Connect) = ((__int64 (__fastcall *)(struct ITaskService *, VARIANTARG *, __int128 *, VARIANTARG *, __int128 *))Connect)(
                       a1,
                       &v41,
                       &v39,
                       &v38,
                       &v43);
  _variant_t::~_variant_t((_variant_t *)&v42);
  _variant_t::~_variant_t((_variant_t *)&v35);
  _variant_t::~_variant_t((_variant_t *)&v36);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  if ( (int)Connect >= 0
    && ((int (__fastcall *)(struct ITaskService *, _QWORD, __int64 *))a1->lpVtbl->GetFolder)(a1, 0, &v31) >= 0
    && (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 104LL))(v31, *(_QWORD *)v5, &v33) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 152LL))(v33, &v28) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 120LL))(v28, &v32) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 104LL))(v32, &v26) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 72LL))(v28, &v30) >= 0
    && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 56LL))(v30, &v45) >= 0 )
  {
    for ( i = 1; i <= v45; ++i )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 64LL))(v30, (unsigned int)i, &v29);
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 56LL))(v29, &v46) < 0 )
        goto LABEL_22;
      if ( v46 == 8 )
      {
        v16 = 0;
        v27 = 0;
        if ( v29 )
        {
          (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v29)(
            v29,
            &GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb,
            &v27);
          v16 = v27;
        }
        if ( (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 152LL))(v16, a2) < 0 )
        {
          ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v27);
          goto LABEL_22;
        }
        ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v27);
      }
    }
    v17 = v31;
    v18 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, VARIANTARG *, __int128 *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v31 + 136LL);
    VariantInit(&v35);
    v19 = *(_OWORD *)&v35.vt;
    v20 = v26;
    v21 = v35.pRecInfo;
    VariantInit(&v36);
    v22 = *(_OWORD *)&v36.vt;
    v23 = v36.pRecInfo;
    VariantInit(&pvarg);
    v24 = *(_QWORD *)v5;
    *(_OWORD *)&v41.vt = v19;
    v41.pRecInfo = v21;
    v39 = v22;
    v40 = v23;
    v38 = pvarg;
    v18(v17, v24, v28, 4, &v38, &v39, v20, &v41, &v34);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    _variant_t::~_variant_t((_variant_t *)&v36);
    _variant_t::~_variant_t((_variant_t *)&v35);
  }
LABEL_22:
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v29);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v30);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v34);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v32);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v28);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v33);
  ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(&v31);
  if ( _InterlockedExchangeAdd(v5 + 4, 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v5 )
    {
      SysFreeString(*(BSTR *)v5);
      *(_QWORD *)v5 = 0;
    }
    v25 = (void *)*((_QWORD *)v5 + 1);
    if ( v25 )
    {
      operator delete[](v25);
      *((_QWORD *)v5 + 1) = 0;
    }
    operator delete((void *)v5);
  }
}

```

## disassembly

```asm
0x1400021d8  mov     rax, rsp
0x1400021db  mov     [rax+8], rbx
0x1400021df  push    rbp
0x1400021e0  push    rsi
0x1400021e1  push    rdi
0x1400021e2  push    r14
0x1400021e4  push    r15
0x1400021e6  lea     rbp, [rax-108h]
0x1400021ed  sub     rsp, 1E0h
0x1400021f4  movaps  xmmword ptr [rax-38h], xmm6
0x1400021f8  mov     rsi, rcx
0x1400021fb  movaps  xmmword ptr [rax-48h], xmm7
0x1400021ff  mov     ecx, 18h; Size
0x140002204  movaps  xmmword ptr [rax-58h], xmm8
0x140002209  movzx   r14d, dx
0x14000220d  movaps  xmmword ptr [rax-68h], xmm9
0x140002212  movaps  xmmword ptr [rax-78h], xmm10
0x140002217  movaps  xmmword ptr [rax-88h], xmm11
0x14000221f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002224  xor     r15d, r15d
0x140002227  mov     rbx, rax
0x14000222a  test    rax, rax
0x14000222d  jz      loc_140002658
0x140002233  lea     rcx, psz; "\\Microsoft\\Windows\\SpacePort\\SpaceA"...
0x14000223a  mov     [rax+8], r15
0x14000223e  mov     dword ptr [rax+10h], 1
0x140002245  call    cs:__imp_SysAllocString
0x14000224b  mov     [rbx], rax
0x14000224e  test    rax, rax
0x140002251  jz      loc_140002658
0x140002257  mov     rax, [rsi]
0x14000225a  lea     rcx, [rbp+100h+pvarg]; pvarg
0x14000225e  mov     [rbp+100h+arg_18], r15d
0x140002265  mov     dword ptr [rsp+200h+var_1B0], r15d
0x14000226a  mov     [rbp+100h+arg_10], r15d
0x140002271  mov     rdi, [rax+50h]
0x140002275  mov     [rsp+200h+var_188], r15
0x14000227a  mov     [rbp+100h+var_178], r15
0x14000227e  mov     [rsp+200h+var_1A0], r15
0x140002283  mov     [rbp+100h+var_180], r15
0x140002287  mov     [rbp+100h+var_170], r15
0x14000228b  mov     [rsp+200h+var_190], r15
0x140002290  mov     [rsp+200h+var_198], r15
0x140002295  call    cs:__imp_VariantInit
0x14000229b  movups  xmm10, xmmword ptr [rbp+100h+pvarg]
0x1400022a0  lea     rcx, [rbp+100h+var_150]; pvarg
0x1400022a4  movsd   xmm11, qword ptr [rbp+100h+pvarg+10h]
0x1400022aa  call    cs:__imp_VariantInit
0x1400022b0  movups  xmm8, xmmword ptr [rbp+100h+var_150]
0x1400022b5  lea     rcx, [rbp+100h+var_168]; pvarg
0x1400022b9  movsd   xmm9, qword ptr [rbp+100h+var_150+10h]
0x1400022bf  call    cs:__imp_VariantInit
0x1400022c5  movups  xmm6, xmmword ptr [rbp+100h+var_168]
0x1400022c9  lea     rcx, [rbp+100h+var_C0]; pvarg
0x1400022cd  movsd   xmm7, qword ptr [rbp+100h+var_168+10h]
0x1400022d2  call    cs:__imp_VariantInit
0x1400022d8  movups  xmm0, xmmword ptr [rbp+100h+var_C0]
0x1400022dc  lea     rax, [rbp+100h+var_A0]
0x1400022e0  mov     rcx, rsi
0x1400022e3  movsd   xmm1, qword ptr [rbp+100h+var_C0+10h]
0x1400022e8  lea     r9, [rbp+100h+var_120]
0x1400022ec  mov     [rsp+200h+var_1E0], rax
0x1400022f1  lea     r8, [rbp+100h+var_100]
0x1400022f5  mov     rax, rdi
0x1400022f8  movaps  [rbp+100h+var_E0], xmm0
0x1400022fc  lea     rdx, [rbp+100h+var_E0]
0x140002300  movaps  [rbp+100h+var_A0], xmm10
0x140002305  movsd   [rbp+100h+var_90], xmm11
0x14000230b  movaps  [rbp+100h+var_120], xmm8
0x140002310  movsd   [rbp+100h+var_110], xmm9
0x140002316  movaps  [rbp+100h+var_100], xmm6
0x14000231a  movsd   [rbp+100h+var_F0], xmm7
0x14000231f  movsd   [rbp+100h+var_D0], xmm1
0x140002324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002329  lea     rcx, [rbp+100h+var_C0]; this
0x14000232d  mov     edi, eax
0x14000232f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140002334  lea     rcx, [rbp+100h+var_168]; this
0x140002338  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14000233d  lea     rcx, [rbp+100h+var_150]; this
0x140002341  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140002346  lea     rcx, [rbp+100h+pvarg]; this
0x14000234a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14000234f  test    edi, edi
0x140002351  js      loc_1400025A8
0x140002357  mov     rax, [rsi]
0x14000235a  lea     r8, [rsp+200h+var_188]
0x14000235f  xor     edx, edx
0x140002361  mov     rcx, rsi
0x140002364  mov     rax, [rax+38h]
0x140002368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000236d  test    eax, eax
0x14000236f  js      loc_1400025A8
0x140002375  mov     rcx, [rsp+200h+var_188]
0x14000237a  lea     r8, [rbp+100h+var_178]
0x14000237e  mov     rdx, [rbx]
0x140002381  mov     rax, [rcx]
0x140002384  mov     rax, [rax+68h]
0x140002388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000238d  test    eax, eax
0x14000238f  js      loc_1400025A8
0x140002395  mov     rcx, [rbp+100h+var_178]
0x140002399  lea     rdx, [rsp+200h+var_1A0]
0x14000239e  mov     rax, [rcx]
0x1400023a1  mov     rax, [rax+98h]
0x1400023a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023ad  test    eax, eax
0x1400023af  js      loc_1400025A8
0x1400023b5  mov     rcx, [rsp+200h+var_1A0]
0x1400023ba  lea     rdx, [rbp+100h+var_180]
0x1400023be  mov     rax, [rcx]
0x1400023c1  mov     rax, [rax+78h]
0x1400023c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023ca  test    eax, eax
0x1400023cc  js      loc_1400025A8
0x1400023d2  mov     rcx, [rbp+100h+var_180]
0x1400023d6  lea     rdx, [rsp+200h+var_1B0]
0x1400023db  mov     rax, [rcx]
0x1400023de  mov     rax, [rax+68h]
0x1400023e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023e7  test    eax, eax
0x1400023e9  js      loc_1400025A8
0x1400023ef  mov     rcx, [rsp+200h+var_1A0]
0x1400023f4  lea     rdx, [rsp+200h+var_190]
0x1400023f9  mov     rax, [rcx]
0x1400023fc  mov     rax, [rax+48h]
0x140002400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002405  test    eax, eax
0x140002407  js      loc_1400025A8
0x14000240d  mov     rcx, [rsp+200h+var_190]
0x140002412  lea     rdx, [rbp+100h+arg_10]
0x140002419  mov     rax, [rcx]
0x14000241c  mov     rax, [rax+38h]
0x140002420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002425  test    eax, eax
0x140002427  js      loc_1400025A8
0x14000242d  lea     edi, [r15+1]
0x140002431  cmp     edi, [rbp+100h+arg_10]
0x140002437  jg      loc_1400024E1
0x14000243d  mov     rcx, [rsp+200h+var_190]
0x140002442  lea     r8, [rsp+200h+var_198]
0x140002447  mov     edx, edi
0x140002449  mov     rax, [rcx]
0x14000244c  mov     rax, [rax+40h]
0x140002450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002455  mov     rcx, [rsp+200h+var_198]
0x14000245a  lea     rdx, [rbp+100h+arg_18]
0x140002461  mov     rax, [rcx]
0x140002464  mov     rax, [rax+38h]
0x140002468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000246d  test    eax, eax
0x14000246f  js      loc_1400025A8
0x140002475  cmp     [rbp+100h+arg_18], 8
0x14000247c  jnz     short loc_1400024D0
0x14000247e  mov     r9, [rsp+200h+var_198]
0x140002483  mov     rcx, r15
0x140002486  mov     [rsp+200h+var_1A8], rcx
0x14000248b  test    r9, r9
0x14000248e  jz      short loc_1400024AF
0x140002490  mov     rax, [r9]
0x140002493  lea     r8, [rsp+200h+var_1A8]
0x140002498  lea     rdx, _GUID_2a9c35da_d357_41f4_bbc1_207ac1b1f3cb
0x14000249f  mov     rcx, r9
0x1400024a2  mov     rax, [rax]
0x1400024a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024aa  mov     rcx, [rsp+200h+var_1A8]
0x1400024af  mov     rax, [rcx]
0x1400024b2  movzx   edx, r14w
0x1400024b6  mov     rax, [rax+98h]
0x1400024bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024c2  lea     rcx, [rsp+200h+var_1A8]
0x1400024c7  test    eax, eax
0x1400024c9  js      short loc_1400024D7
0x1400024cb  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400024d0  inc     edi
0x1400024d2  jmp     loc_140002431
0x1400024d7  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400024dc  jmp     loc_1400025A8
0x1400024e1  mov     r14, [rsp+200h+var_188]
0x1400024e6  lea     rcx, [rbp+100h+var_168]; pvarg
0x1400024ea  mov     rax, [r14]
0x1400024ed  mov     rsi, [rax+88h]
0x1400024f4  call    cs:__imp_VariantInit
0x1400024fa  movups  xmm8, xmmword ptr [rbp+100h+var_168]
0x1400024ff  lea     rcx, [rbp+100h+var_150]; pvarg
0x140002503  mov     edi, dword ptr [rsp+200h+var_1B0]
0x140002507  movsd   xmm9, qword ptr [rbp+100h+var_168+10h]
0x14000250d  call    cs:__imp_VariantInit
0x140002513  movups  xmm6, xmmword ptr [rbp+100h+var_150]
0x140002517  lea     rcx, [rbp+100h+pvarg]; pvarg
0x14000251b  movsd   xmm7, qword ptr [rbp+100h+var_150+10h]
0x140002520  call    cs:__imp_VariantInit
0x140002526  movups  xmm0, xmmword ptr [rbp+100h+pvarg]
0x14000252a  lea     rax, [rbp+100h+var_170]
0x14000252e  mov     r8, [rsp+200h+var_1A0]
0x140002533  movsd   xmm1, qword ptr [rbp+100h+pvarg+10h]
0x140002538  mov     r9d, 4
0x14000253e  mov     rdx, [rbx]
0x140002541  mov     rcx, r14
0x140002544  mov     [rsp+200h+var_1C0], rax
0x140002549  lea     rax, [rbp+100h+var_E0]
0x14000254d  mov     [rsp+200h+var_1C8], rax
0x140002552  lea     rax, [rbp+100h+var_100]
0x140002556  mov     dword ptr [rsp+200h+var_1D0], edi
0x14000255a  mov     qword ptr [rsp+200h+var_1D8], rax
0x14000255f  lea     rax, [rbp+100h+var_120]
0x140002563  mov     [rsp+200h+var_1E0], rax
0x140002568  mov     rax, rsi
0x14000256b  movaps  [rbp+100h+var_E0], xmm8
0x140002570  movsd   [rbp+100h+var_D0], xmm9
0x140002576  movaps  [rbp+100h+var_100], xmm6
0x14000257a  movsd   [rbp+100h+var_F0], xmm7
0x14000257f  movaps  [rbp+100h+var_120], xmm0
0x140002583  movsd   [rbp+100h+var_110], xmm1
0x140002588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000258d  lea     rcx, [rbp+100h+pvarg]; this
0x140002591  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140002596  lea     rcx, [rbp+100h+var_150]; this
0x14000259a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14000259f  lea     rcx, [rbp+100h+var_168]; this
0x1400025a3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1400025a8  lea     rcx, [rsp+200h+var_198]
0x1400025ad  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400025b2  lea     rcx, [rsp+200h+var_190]
0x1400025b7  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400025bc  lea     rcx, [rbp+100h+var_170]
0x1400025c0  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400025c5  lea     rcx, [rbp+100h+var_180]
0x1400025c9  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400025ce  lea     rcx, [rsp+200h+var_1A0]
0x1400025d3  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400025d8  lea     rcx, [rbp+100h+var_178]
0x1400025dc  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400025e1  lea     rcx, [rsp+200h+var_188]
0x1400025e6  call    ??1?$CComPtrBase@UITriggerCollection@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITriggerCollection>::~CComPtrBase<ITriggerCollection>(void)
0x1400025eb  or      eax, 0FFFFFFFFh
0x1400025ee  lock xadd [rbx+10h], eax
0x1400025f3  cmp     eax, 1
0x1400025f6  jnz     short loc_140002623
0x1400025f8  mov     rcx, [rbx]; bstrString
0x1400025fb  test    rcx, rcx
0x1400025fe  jz      short loc_140002609
0x140002600  call    cs:__imp_SysFreeString
0x140002606  mov     [rbx], r15
0x140002609  mov     rcx, [rbx+8]; Block
0x14000260d  test    rcx, rcx
0x140002610  jz      short loc_14000261B
0x140002612  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140002617  mov     [rbx+8], r15
0x14000261b  mov     rcx, rbx; Block
0x14000261e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002623  lea     r11, [rsp+200h+var_20]
0x14000262b  mov     rbx, [r11+30h]
0x14000262f  movaps  xmm6, xmmword ptr [r11-10h]
0x140002634  movaps  xmm7, xmmword ptr [r11-20h]
0x140002639  movaps  xmm8, xmmword ptr [r11-30h]
0x14000263e  movaps  xmm9, xmmword ptr [r11-40h]
0x140002643  movaps  xmm10, xmmword ptr [r11-50h]
0x140002648  movaps  xmm11, xmmword ptr [r11-60h]
0x14000264d  mov     rsp, r11
0x140002650  pop     r15
0x140002652  pop     r14
0x140002654  pop     rdi
0x140002655  pop     rsi
0x140002656  pop     rbp
0x140002657  retn
0x140002658  mov     ecx, 8007000Eh; int
0x14000265d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
