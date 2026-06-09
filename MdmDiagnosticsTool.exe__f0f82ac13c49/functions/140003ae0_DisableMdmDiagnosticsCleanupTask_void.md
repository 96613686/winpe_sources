# DisableMdmDiagnosticsCleanupTask(void)

- ea: `0x140003ae0`
- end: `0x140003e8c`
- name: `?DisableMdmDiagnosticsCleanupTask@@YAXXZ`
- size: `940`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140008130`

## callees

- `0x1400030e8`
- `0x140003568`
- `0x140003ae0`
- `0x1400052b4`
- `0x140007184`
- `0x14000a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x140003d2e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003dea`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003d2e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003dea`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003d3f`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003dfb`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003d3f`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003dfb`
- `OLEAUT32!__imp_SysFreeString` at `0x140003d18`
- `OLEAUT32!__imp_SysFreeString` at `0x140003dd4`
- `OLEAUT32!__imp_SysFreeString` at `0x140003d18`
- `OLEAUT32!__imp_SysFreeString` at `0x140003dd4`
- `OLEAUT32!__imp_VariantInit` at `0x140003baa`
- `OLEAUT32!__imp_VariantInit` at `0x140003bc1`
- `OLEAUT32!__imp_VariantInit` at `0x140003bd9`
- `OLEAUT32!__imp_VariantInit` at `0x140003bf0`
- `OLEAUT32!__imp_VariantInit` at `0x140003baa`
- `OLEAUT32!__imp_VariantInit` at `0x140003bc1`
- `OLEAUT32!__imp_VariantInit` at `0x140003bd9`
- `OLEAUT32!__imp_VariantInit` at `0x140003bf0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003b1a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003b1a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003e58`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003e58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003b79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003b79`

## pseudocode

```c
void DisableMdmDiagnosticsCleanupTask(void)
{
  HRESULT v0; // eax
  unsigned int v1; // r8d
  BOOL v2; // ebx
  HRESULT v3; // eax
  unsigned int v4; // r8d
  LPVOID v5; // rsi
  __int64 (__fastcall *v6)(LPVOID, __int128 *, __int128 *, __int128 *); // rdi
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  __int64 v10; // xmm9_8
  __int128 v11; // xmm6
  __int64 v12; // xmm7_8
  int v13; // eax
  unsigned int v14; // r8d
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, _QWORD *, __int64 *); // rsi
  _QWORD *v17; // rdx
  int v18; // eax
  unsigned int v19; // r8d
  __int64 v20; // rdi
  void *v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD *, __int64 *); // rsi
  _QWORD *v24; // rdx
  int v25; // eax
  unsigned int v26; // r8d
  __int64 v27; // rdi
  void *v28; // rcx
  int v29; // eax
  unsigned int v30; // r8d
  int ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  __int64 v33; // [rsp+38h] [rbp-D0h] BYREF
  VARIANTARG v34; // [rsp+40h] [rbp-C8h] BYREF
  VARIANTARG v35; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v36; // [rsp+70h] [rbp-98h] BYREF
  __int64 v37; // [rsp+88h] [rbp-80h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-78h] BYREF
  int v39[4]; // [rsp+A8h] [rbp-60h] BYREF
  IRecordInfo *v40; // [rsp+B8h] [rbp-50h]
  __int128 v41; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v42; // [rsp+D8h] [rbp-30h]
  __int128 v43; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-10h]
  __int128 v45; // [rsp+108h] [rbp+0h] BYREF
  __int64 v46; // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+1B0h] [rbp+A8h]
  LPVOID v48; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v49; // [rsp+1D0h] [rbp+C8h] BYREF

  v0 = CoInitializeEx(0, 0);
  v2 = v0 >= 0;
  if ( v0 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x33, v1, (const char *)(unsigned int)v0, ppv);
  v48 = 0;
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v48);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v48);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x36, v4, (const char *)(unsigned int)v3, ppva);
  v5 = v48;
  v6 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v48 + 80LL);
  VariantInit(&pvarg);
  v7 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit((VARIANTARG *)&v36.decVal.8);
  v9 = *(_OWORD *)&v36.decVal.Lo32;
  v10 = v37;
  VariantInit((VARIANTARG *)&v35.decVal.8);
  v11 = *(_OWORD *)&v35.decVal.Lo32;
  v12 = *(_QWORD *)&v36.vt;
  VariantInit((VARIANTARG *)&v34.decVal.8);
  *(_OWORD *)v39 = v7;
  v40 = pRecInfo;
  v41 = v9;
  v42 = v10;
  v43 = v11;
  v44 = v12;
  v45 = *(_OWORD *)&v34.decVal.Lo32;
  v46 = *(_QWORD *)&v35.vt;
  v13 = v6(v5, &v45, &v43, &v41);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x38, v14, (const char *)(unsigned int)v13, (int)v39);
  _variant_t::~_variant_t((_variant_t *)&v34.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v35.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&v36.decVal.8);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  v33 = 0;
  v15 = v48;
  v16 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)v48 + 56LL);
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v33);
  v17 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v34, L"\\Microsoft\\Windows\\Management\\Provisioning");
  if ( v17 )
    v17 = (_QWORD *)*v17;
  v18 = v16(v15, v17, &v33);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x3C, v19, (const char *)(unsigned int)v18, (int)v39);
  v20 = *(_QWORD *)&v34.vt;
  if ( *(_QWORD *)&v34.vt
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v34.vt + 16LL), 0xFFFFFFFF) == 1
    && v20 )
  {
    if ( *(_QWORD *)v20 )
    {
      SysFreeString(*(BSTR *)v20);
      *(_QWORD *)v20 = 0;
    }
    v21 = *(void **)(v20 + 8);
    if ( v21 )
    {
      operator delete[](v21);
      *(_QWORD *)(v20 + 8) = 0;
    }
    operator delete((void *)v20);
  }
  v49 = 0;
  v22 = v33;
  v23 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v33 + 104LL);
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v49);
  v24 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v34, L"MdmDiagnosticsCleanup");
  if ( v24 )
    v24 = (_QWORD *)*v24;
  v25 = v23(v22, v24, &v49);
  if ( v25 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x3F, v26, (const char *)(unsigned int)v25, (int)v39);
  v27 = *(_QWORD *)&v34.vt;
  if ( *(_QWORD *)&v34.vt
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v34.vt + 16LL), 0xFFFFFFFF) == 1
    && v27 )
  {
    if ( *(_QWORD *)v27 )
    {
      SysFreeString(*(BSTR *)v27);
      *(_QWORD *)v27 = 0;
    }
    v28 = *(void **)(v27 + 8);
    if ( v28 )
    {
      operator delete[](v28);
      *(_QWORD *)(v27 + 8) = 0;
    }
    operator delete((void *)v27);
  }
  v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 88LL))(v49, 0);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x41, v30, (const char *)(unsigned int)v29, (int)v39);
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(&v48);
  if ( v2 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140003ae0  mov     rax, rsp
0x140003ae3  push    rbp
0x140003ae4  push    rbx
0x140003ae5  push    rsi
0x140003ae6  push    rdi
0x140003ae7  lea     rbp, [rax-0A8h]
0x140003aee  sub     rsp, 188h
0x140003af5  movaps  xmmword ptr [rax-38h], xmm6
0x140003af9  movaps  xmmword ptr [rax-48h], xmm7
0x140003afd  movaps  xmmword ptr [rax-58h], xmm8
0x140003b02  movaps  xmmword ptr [rax-68h], xmm9
0x140003b07  movaps  xmmword ptr [rax-78h], xmm10
0x140003b0c  movaps  xmmword ptr [rax-88h], xmm11
0x140003b14  xor     ebx, ebx
0x140003b16  xor     edx, edx; dwCoInit
0x140003b18  xor     ecx, ecx; pvReserved
0x140003b1a  call    cs:__imp_CoInitializeEx
0x140003b20  lea     edi, [rbx+1]
0x140003b23  test    eax, eax
0x140003b25  cmovns  ebx, edi
0x140003b28  mov     [rbp+0A0h+arg_0], ebx
0x140003b2e  mov     rcx, [rbp+0A8h]; this
0x140003b35  jns     short loc_140003B43
0x140003b37  mov     r9d, eax; char *
0x140003b3a  lea     edx, [rdi+32h]; void *
0x140003b3d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003b43  mov     [rbp+0A0h+arg_10], 0
0x140003b4e  lea     rcx, [rbp+0A0h+arg_10]
0x140003b55  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003b5a  lea     rax, [rbp+0A0h+arg_10]
0x140003b61  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x140003b66  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140003b6d  mov     r8d, edi; dwClsContext
0x140003b70  xor     edx, edx; pUnkOuter
0x140003b72  lea     rcx, CLSID_TaskScheduler; rclsid
0x140003b79  call    cs:__imp_CoCreateInstance
0x140003b7f  mov     rcx, [rbp+0A8h]; this
0x140003b86  test    eax, eax
0x140003b88  jns     short loc_140003B98
0x140003b8a  mov     r9d, eax; char *
0x140003b8d  mov     edx, 36h ; '6'; void *
0x140003b92  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003b98  mov     rsi, [rbp+0A0h+arg_10]
0x140003b9f  mov     rax, [rsi]
0x140003ba2  mov     rdi, [rax+50h]
0x140003ba6  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x140003baa  call    cs:__imp_VariantInit
0x140003bb0  nop
0x140003bb1  movups  xmm10, xmmword ptr [rbp+0A0h+pvarg]
0x140003bb6  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x140003bbc  lea     rcx, [rsp+1A0h+var_138+8]; pvarg
0x140003bc1  call    cs:__imp_VariantInit
0x140003bc7  nop
0x140003bc8  movups  xmm8, xmmword ptr [rsp+1A0h+var_138+8]
0x140003bce  movsd   xmm9, [rbp+0A0h+var_120]
0x140003bd4  lea     rcx, [rsp+1A0h+var_150+8]; pvarg
0x140003bd9  call    cs:__imp_VariantInit
0x140003bdf  nop
0x140003be0  movups  xmm6, xmmword ptr [rsp+1A0h+var_150+8]
0x140003be5  movsd   xmm7, qword ptr [rsp+1A0h+var_138]
0x140003beb  lea     rcx, [rsp+1A0h+var_168+8]; pvarg
0x140003bf0  call    cs:__imp_VariantInit
0x140003bf6  nop
0x140003bf7  movups  xmm0, xmmword ptr [rsp+1A0h+var_168+8]
0x140003bfc  movsd   xmm1, qword ptr [rsp+1A0h+var_150]
0x140003c02  movaps  xmmword ptr [rbp+0A0h+var_100], xmm10
0x140003c07  movsd   [rbp+0A0h+var_F0], xmm11
0x140003c0d  movaps  [rbp+0A0h+var_E0], xmm8
0x140003c12  movsd   [rbp+0A0h+var_D0], xmm9
0x140003c18  movaps  [rbp+0A0h+var_C0], xmm6
0x140003c1c  movsd   [rbp+0A0h+var_B0], xmm7
0x140003c21  movaps  [rbp+0A0h+var_A0], xmm0
0x140003c25  movsd   [rbp+0A0h+var_90], xmm1
0x140003c2a  lea     rax, [rbp+0A0h+var_100]
0x140003c2e  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x140003c33  lea     r9, [rbp+0A0h+var_E0]
0x140003c37  lea     r8, [rbp+0A0h+var_C0]
0x140003c3b  lea     rdx, [rbp+0A0h+var_A0]
0x140003c3f  mov     rcx, rsi
0x140003c42  mov     rax, rdi
0x140003c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c4a  mov     rcx, [rbp+0A8h]; this
0x140003c51  test    eax, eax
0x140003c53  jns     short loc_140003C63
0x140003c55  mov     r9d, eax; char *
0x140003c58  mov     edx, 38h ; '8'; void *
0x140003c5d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003c63  lea     rcx, [rsp+1A0h+var_168+8]; this
0x140003c68  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003c6d  nop
0x140003c6e  lea     rcx, [rsp+1A0h+var_150+8]; this
0x140003c73  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003c78  nop
0x140003c79  lea     rcx, [rsp+1A0h+var_138+8]; this
0x140003c7e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003c83  nop
0x140003c84  lea     rcx, [rbp+0A0h+pvarg]; this
0x140003c88  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003c8d  mov     [rsp+1A0h+var_170], 0
0x140003c96  mov     rdi, [rbp+0A0h+arg_10]
0x140003c9d  mov     rax, [rdi]
0x140003ca0  mov     rsi, [rax+38h]
0x140003ca4  lea     rcx, [rsp+1A0h+var_170]
0x140003ca9  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003cae  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Management\\Provi"...
0x140003cb5  lea     rcx, [rsp+1A0h+var_168]; this
0x140003cba  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140003cbf  nop
0x140003cc0  mov     rdx, [rax]
0x140003cc3  test    rdx, rdx
0x140003cc6  jz      short loc_140003CCB
0x140003cc8  mov     rdx, [rdx]
0x140003ccb  lea     r8, [rsp+1A0h+var_170]
0x140003cd0  mov     rcx, rdi
0x140003cd3  mov     rax, rsi
0x140003cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cdb  mov     rcx, [rbp+0A8h]; this
0x140003ce2  test    eax, eax
0x140003ce4  jns     short loc_140003CF4
0x140003ce6  mov     r9d, eax; char *
0x140003ce9  mov     edx, 3Ch ; '<'; void *
0x140003cee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003cf4  mov     rdi, qword ptr [rsp+1A0h+var_168]
0x140003cf9  test    rdi, rdi
0x140003cfc  jz      short loc_140003D45
0x140003cfe  or      eax, 0FFFFFFFFh
0x140003d01  lock xadd [rdi+10h], eax
0x140003d06  cmp     eax, 1
0x140003d09  jnz     short loc_140003D45
0x140003d0b  test    rdi, rdi
0x140003d0e  jz      short loc_140003D45
0x140003d10  mov     rcx, [rdi]; bstrString
0x140003d13  test    rcx, rcx
0x140003d16  jz      short loc_140003D25
0x140003d18  call    cs:__imp_SysFreeString
0x140003d1e  mov     qword ptr [rdi], 0
0x140003d25  mov     rcx, [rdi+8]
0x140003d29  test    rcx, rcx
0x140003d2c  jz      short loc_140003D3C
0x140003d2e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140003d34  mov     qword ptr [rdi+8], 0
0x140003d3c  mov     rcx, rdi
0x140003d3f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003d45  mov     [rbp+0A0h+arg_18], 0
0x140003d50  mov     rdi, [rsp+1A0h+var_170]
0x140003d55  mov     rax, [rdi]
0x140003d58  mov     rsi, [rax+68h]
0x140003d5c  lea     rcx, [rbp+0A0h+arg_18]
0x140003d63  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003d68  lea     rdx, aMdmdiagnostics_0; "MdmDiagnosticsCleanup"
0x140003d6f  lea     rcx, [rsp+1A0h+var_168]; this
0x140003d74  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140003d79  nop
0x140003d7a  mov     rdx, [rax]
0x140003d7d  test    rdx, rdx
0x140003d80  jz      short loc_140003D85
0x140003d82  mov     rdx, [rdx]
0x140003d85  lea     r8, [rbp+0A0h+arg_18]
0x140003d8c  mov     rcx, rdi
0x140003d8f  mov     rax, rsi
0x140003d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d97  mov     rcx, [rbp+0A8h]; this
0x140003d9e  test    eax, eax
0x140003da0  jns     short loc_140003DB0
0x140003da2  mov     r9d, eax; char *
0x140003da5  mov     edx, 3Fh ; '?'; void *
0x140003daa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003db0  mov     rdi, qword ptr [rsp+1A0h+var_168]
0x140003db5  test    rdi, rdi
0x140003db8  jz      short loc_140003E01
0x140003dba  or      eax, 0FFFFFFFFh
0x140003dbd  lock xadd [rdi+10h], eax
0x140003dc2  cmp     eax, 1
0x140003dc5  jnz     short loc_140003E01
0x140003dc7  test    rdi, rdi
0x140003dca  jz      short loc_140003E01
0x140003dcc  mov     rcx, [rdi]; bstrString
0x140003dcf  test    rcx, rcx
0x140003dd2  jz      short loc_140003DE1
0x140003dd4  call    cs:__imp_SysFreeString
0x140003dda  mov     qword ptr [rdi], 0
0x140003de1  mov     rcx, [rdi+8]
0x140003de5  test    rcx, rcx
0x140003de8  jz      short loc_140003DF8
0x140003dea  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140003df0  mov     qword ptr [rdi+8], 0
0x140003df8  mov     rcx, rdi
0x140003dfb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003e01  mov     rcx, [rbp+0A0h+arg_18]
0x140003e08  mov     rax, [rcx]
0x140003e0b  xor     edx, edx
0x140003e0d  mov     rax, [rax+58h]
0x140003e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e16  mov     rcx, [rbp+0A8h]; this
0x140003e1d  test    eax, eax
0x140003e1f  jns     short loc_140003E2F
0x140003e21  mov     r9d, eax; char *
0x140003e24  mov     edx, 41h ; 'A'; void *
0x140003e29  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003e2f  lea     rcx, [rbp+0A0h+arg_18]
0x140003e36  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003e3b  nop
0x140003e3c  lea     rcx, [rsp+1A0h+var_170]
0x140003e41  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003e46  nop
0x140003e47  lea     rcx, [rbp+0A0h+arg_10]
0x140003e4e  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003e53  nop
0x140003e54  test    ebx, ebx
0x140003e56  jz      short loc_140003E5E
0x140003e58  call    cs:__imp_CoUninitialize
0x140003e5e  lea     r11, [rsp+1A0h+var_18]
0x140003e66  movaps  xmm6, xmmword ptr [r11-18h]
0x140003e6b  movaps  xmm7, xmmword ptr [r11-28h]
0x140003e70  movaps  xmm8, xmmword ptr [r11-38h]
0x140003e75  movaps  xmm9, xmmword ptr [r11-48h]
0x140003e7a  movaps  xmm10, xmmword ptr [r11-58h]
0x140003e7f  movaps  xmm11, xmmword ptr [r11-68h]
0x140003e84  mov     rsp, r11
0x140003e87  pop     rdi
0x140003e88  pop     rsi
0x140003e89  pop     rbx
0x140003e8a  pop     rbp
0x140003e8b  retn
```
