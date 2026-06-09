# DisableMdmDiagnosticsCleanupTask(void)

- ea: `0x140003c44`
- end: `0x14000403f`
- name: `?DisableMdmDiagnosticsCleanupTask@@YAXXZ`
- size: `1019`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140008694`

## callees

- `0x140003184`
- `0x1400035f0`
- `0x140003c44`
- `0x140005588`
- `0x140007588`
- `0x14000b010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x140003ebc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003f8a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003ebc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140003f8a`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003ed3`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003fa1`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003ed3`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003fa1`
- `OLEAUT32!__imp_SysFreeString` at `0x140003ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x140003f6e`
- `OLEAUT32!__imp_SysFreeString` at `0x140003ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x140003f6e`
- `OLEAUT32!__imp_VariantInit` at `0x140003d1a`
- `OLEAUT32!__imp_VariantInit` at `0x140003d37`
- `OLEAUT32!__imp_VariantInit` at `0x140003d55`
- `OLEAUT32!__imp_VariantInit` at `0x140003d72`
- `OLEAUT32!__imp_VariantInit` at `0x140003d1a`
- `OLEAUT32!__imp_VariantInit` at `0x140003d37`
- `OLEAUT32!__imp_VariantInit` at `0x140003d55`
- `OLEAUT32!__imp_VariantInit` at `0x140003d72`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003c7e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003c7e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004004`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004004`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003ce3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003ce3`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
0x140003c44  mov     rax, rsp
0x140003c47  push    rbp
0x140003c48  push    rbx
0x140003c49  push    rsi
0x140003c4a  push    rdi
0x140003c4b  lea     rbp, [rax-0A8h]
0x140003c52  sub     rsp, 188h
0x140003c59  movaps  xmmword ptr [rax-38h], xmm6
0x140003c5d  movaps  xmmword ptr [rax-48h], xmm7
0x140003c61  movaps  xmmword ptr [rax-58h], xmm8
0x140003c66  movaps  xmmword ptr [rax-68h], xmm9
0x140003c6b  movaps  xmmword ptr [rax-78h], xmm10
0x140003c70  movaps  xmmword ptr [rax-88h], xmm11
0x140003c78  xor     ebx, ebx
0x140003c7a  xor     edx, edx; dwCoInit
0x140003c7c  xor     ecx, ecx; pvReserved
0x140003c7e  call    cs:__imp_CoInitializeEx
0x140003c85  nop     dword ptr [rax+rax+00h]
0x140003c8a  lea     edi, [rbx+1]
0x140003c8d  test    eax, eax
0x140003c8f  cmovns  ebx, edi
0x140003c92  mov     [rbp+0A0h+arg_0], ebx
0x140003c98  mov     rcx, [rbp+0A8h]; this
0x140003c9f  jns     short loc_140003CAD
0x140003ca1  mov     r9d, eax; char *
0x140003ca4  lea     edx, [rdi+32h]; void *
0x140003ca7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003cad  mov     [rbp+0A0h+arg_10], 0
0x140003cb8  lea     rcx, [rbp+0A0h+arg_10]
0x140003cbf  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003cc4  lea     rax, [rbp+0A0h+arg_10]
0x140003ccb  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x140003cd0  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140003cd7  mov     r8d, edi; dwClsContext
0x140003cda  xor     edx, edx; pUnkOuter
0x140003cdc  lea     rcx, CLSID_TaskScheduler; rclsid
0x140003ce3  call    cs:__imp_CoCreateInstance
0x140003cea  nop     dword ptr [rax+rax+00h]
0x140003cef  mov     rcx, [rbp+0A8h]; this
0x140003cf6  test    eax, eax
0x140003cf8  jns     short loc_140003D08
0x140003cfa  mov     r9d, eax; char *
0x140003cfd  mov     edx, 36h ; '6'; void *
0x140003d02  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003d08  mov     rsi, [rbp+0A0h+arg_10]
0x140003d0f  mov     rax, [rsi]
0x140003d12  mov     rdi, [rax+50h]
0x140003d16  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x140003d1a  call    cs:__imp_VariantInit
0x140003d21  nop     dword ptr [rax+rax+00h]
0x140003d26  nop
0x140003d27  movups  xmm10, xmmword ptr [rbp+0A0h+pvarg]
0x140003d2c  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x140003d32  lea     rcx, [rsp+1A0h+var_138+8]; pvarg
0x140003d37  call    cs:__imp_VariantInit
0x140003d3e  nop     dword ptr [rax+rax+00h]
0x140003d43  nop
0x140003d44  movups  xmm8, xmmword ptr [rsp+1A0h+var_138+8]
0x140003d4a  movsd   xmm9, [rbp+0A0h+var_120]
0x140003d50  lea     rcx, [rsp+1A0h+var_150+8]; pvarg
0x140003d55  call    cs:__imp_VariantInit
0x140003d5c  nop     dword ptr [rax+rax+00h]
0x140003d61  nop
0x140003d62  movups  xmm6, xmmword ptr [rsp+1A0h+var_150+8]
0x140003d67  movsd   xmm7, qword ptr [rsp+1A0h+var_138]
0x140003d6d  lea     rcx, [rsp+1A0h+var_168+8]; pvarg
0x140003d72  call    cs:__imp_VariantInit
0x140003d79  nop     dword ptr [rax+rax+00h]
0x140003d7e  nop
0x140003d7f  movups  xmm0, xmmword ptr [rsp+1A0h+var_168+8]
0x140003d84  movsd   xmm1, qword ptr [rsp+1A0h+var_150]
0x140003d8a  movaps  xmmword ptr [rbp+0A0h+var_100], xmm10
0x140003d8f  movsd   [rbp+0A0h+var_F0], xmm11
0x140003d95  movaps  [rbp+0A0h+var_E0], xmm8
0x140003d9a  movsd   [rbp+0A0h+var_D0], xmm9
0x140003da0  movaps  [rbp+0A0h+var_C0], xmm6
0x140003da4  movsd   [rbp+0A0h+var_B0], xmm7
0x140003da9  movaps  [rbp+0A0h+var_A0], xmm0
0x140003dad  movsd   [rbp+0A0h+var_90], xmm1
0x140003db2  lea     rax, [rbp+0A0h+var_100]
0x140003db6  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x140003dbb  lea     r9, [rbp+0A0h+var_E0]
0x140003dbf  lea     r8, [rbp+0A0h+var_C0]
0x140003dc3  lea     rdx, [rbp+0A0h+var_A0]
0x140003dc7  mov     rcx, rsi
0x140003dca  mov     rax, rdi
0x140003dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dd2  mov     rcx, [rbp+0A8h]; this
0x140003dd9  test    eax, eax
0x140003ddb  jns     short loc_140003DEB
0x140003ddd  mov     r9d, eax; char *
0x140003de0  mov     edx, 38h ; '8'; void *
0x140003de5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003deb  lea     rcx, [rsp+1A0h+var_168+8]; this
0x140003df0  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003df5  nop
0x140003df6  lea     rcx, [rsp+1A0h+var_150+8]; this
0x140003dfb  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003e00  nop
0x140003e01  lea     rcx, [rsp+1A0h+var_138+8]; this
0x140003e06  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003e0b  nop
0x140003e0c  lea     rcx, [rbp+0A0h+pvarg]; this
0x140003e10  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140003e15  mov     [rsp+1A0h+var_170], 0
0x140003e1e  mov     rdi, [rbp+0A0h+arg_10]
0x140003e25  mov     rax, [rdi]
0x140003e28  mov     rsi, [rax+38h]
0x140003e2c  lea     rcx, [rsp+1A0h+var_170]
0x140003e31  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003e36  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Management\\Provi"...
0x140003e3d  lea     rcx, [rsp+1A0h+var_168]; this
0x140003e42  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140003e47  nop
0x140003e48  mov     rdx, [rax]
0x140003e4b  test    rdx, rdx
0x140003e4e  jz      short loc_140003E53
0x140003e50  mov     rdx, [rdx]
0x140003e53  lea     r8, [rsp+1A0h+var_170]
0x140003e58  mov     rcx, rdi
0x140003e5b  mov     rax, rsi
0x140003e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e63  mov     rcx, [rbp+0A8h]; this
0x140003e6a  test    eax, eax
0x140003e6c  jns     short loc_140003E7C
0x140003e6e  mov     r9d, eax; char *
0x140003e71  mov     edx, 3Ch ; '<'; void *
0x140003e76  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003e7c  mov     rdi, qword ptr [rsp+1A0h+var_168]
0x140003e81  test    rdi, rdi
0x140003e84  jz      short loc_140003EDF
0x140003e86  or      eax, 0FFFFFFFFh
0x140003e89  lock xadd [rdi+10h], eax
0x140003e8e  cmp     eax, 1
0x140003e91  jnz     short loc_140003EDF
0x140003e93  test    rdi, rdi
0x140003e96  jz      short loc_140003EDF
0x140003e98  mov     rcx, [rdi]; bstrString
0x140003e9b  test    rcx, rcx
0x140003e9e  jz      short loc_140003EB3
0x140003ea0  call    cs:__imp_SysFreeString
0x140003ea7  nop     dword ptr [rax+rax+00h]
0x140003eac  mov     qword ptr [rdi], 0
0x140003eb3  mov     rcx, [rdi+8]
0x140003eb7  test    rcx, rcx
0x140003eba  jz      short loc_140003ED0
0x140003ebc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140003ec3  nop     dword ptr [rax+rax+00h]
0x140003ec8  mov     qword ptr [rdi+8], 0
0x140003ed0  mov     rcx, rdi
0x140003ed3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003eda  nop     dword ptr [rax+rax+00h]
0x140003edf  mov     [rbp+0A0h+arg_18], 0
0x140003eea  mov     rdi, [rsp+1A0h+var_170]
0x140003eef  mov     rax, [rdi]
0x140003ef2  mov     rsi, [rax+68h]
0x140003ef6  lea     rcx, [rbp+0A0h+arg_18]
0x140003efd  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003f02  lea     rdx, aMdmdiagnostics_0; "MdmDiagnosticsCleanup"
0x140003f09  lea     rcx, [rsp+1A0h+var_168]; this
0x140003f0e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x140003f13  nop
0x140003f14  mov     rdx, [rax]
0x140003f17  test    rdx, rdx
0x140003f1a  jz      short loc_140003F1F
0x140003f1c  mov     rdx, [rdx]
0x140003f1f  lea     r8, [rbp+0A0h+arg_18]
0x140003f26  mov     rcx, rdi
0x140003f29  mov     rax, rsi
0x140003f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f31  mov     rcx, [rbp+0A8h]; this
0x140003f38  test    eax, eax
0x140003f3a  jns     short loc_140003F4A
0x140003f3c  mov     r9d, eax; char *
0x140003f3f  mov     edx, 3Fh ; '?'; void *
0x140003f44  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003f4a  mov     rdi, qword ptr [rsp+1A0h+var_168]
0x140003f4f  test    rdi, rdi
0x140003f52  jz      short loc_140003FAD
0x140003f54  or      eax, 0FFFFFFFFh
0x140003f57  lock xadd [rdi+10h], eax
0x140003f5c  cmp     eax, 1
0x140003f5f  jnz     short loc_140003FAD
0x140003f61  test    rdi, rdi
0x140003f64  jz      short loc_140003FAD
0x140003f66  mov     rcx, [rdi]; bstrString
0x140003f69  test    rcx, rcx
0x140003f6c  jz      short loc_140003F81
0x140003f6e  call    cs:__imp_SysFreeString
0x140003f75  nop     dword ptr [rax+rax+00h]
0x140003f7a  mov     qword ptr [rdi], 0
0x140003f81  mov     rcx, [rdi+8]
0x140003f85  test    rcx, rcx
0x140003f88  jz      short loc_140003F9E
0x140003f8a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140003f91  nop     dword ptr [rax+rax+00h]
0x140003f96  mov     qword ptr [rdi+8], 0
0x140003f9e  mov     rcx, rdi
0x140003fa1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003fa8  nop     dword ptr [rax+rax+00h]
0x140003fad  mov     rcx, [rbp+0A0h+arg_18]
0x140003fb4  mov     rax, [rcx]
0x140003fb7  xor     edx, edx
0x140003fb9  mov     rax, [rax+58h]
0x140003fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fc2  mov     rcx, [rbp+0A8h]; this
0x140003fc9  test    eax, eax
0x140003fcb  jns     short loc_140003FDB
0x140003fcd  mov     r9d, eax; char *
0x140003fd0  mov     edx, 41h ; 'A'; void *
0x140003fd5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140003fdb  lea     rcx, [rbp+0A0h+arg_18]
0x140003fe2  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003fe7  nop
0x140003fe8  lea     rcx, [rsp+1A0h+var_170]
0x140003fed  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003ff2  nop
0x140003ff3  lea     rcx, [rbp+0A0h+arg_10]
0x140003ffa  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x140003fff  nop
0x140004000  test    ebx, ebx
0x140004002  jz      short loc_140004010
0x140004004  call    cs:__imp_CoUninitialize
0x14000400b  nop     dword ptr [rax+rax+00h]
0x140004010  lea     r11, [rsp+1A0h+var_18]
0x140004018  movaps  xmm6, xmmword ptr [r11-18h]
0x14000401d  movaps  xmm7, xmmword ptr [r11-28h]
0x140004022  movaps  xmm8, xmmword ptr [r11-38h]
0x140004027  movaps  xmm9, xmmword ptr [r11-48h]
0x14000402c  movaps  xmm10, xmmword ptr [r11-58h]
0x140004031  movaps  xmm11, xmmword ptr [r11-68h]
0x140004036  mov     rsp, r11
0x140004039  pop     rdi
0x14000403a  pop     rsi
0x14000403b  pop     rbx
0x14000403c  pop     rbp
0x14000403d  retn
```
