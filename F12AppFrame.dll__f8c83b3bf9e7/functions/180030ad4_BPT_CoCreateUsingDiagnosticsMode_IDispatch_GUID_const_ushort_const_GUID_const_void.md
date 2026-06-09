# BPT::CoCreateUsingDiagnosticsMode(IDispatch *,_GUID const &,ushort const *,_GUID const &,void * *)

- ea: `0x180030ad4`
- end: `0x180030f90`
- name: `?CoCreateUsingDiagnosticsMode@BPT@@YAJPEAUIDispatch@@AEBU_GUID@@PEBG1PEAPEAX@Z`
- size: `1212`
- prototype: `__int64 __fastcall(BPT *this, OLECHAR *, const OLECHAR *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180014210`
- `0x180014740`

## callees

- `0x180003858`
- `0x180030ad4`
- `0x180030f98`
- `0x180035010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180030b7a`
- `ole32!CoTaskMemFree` at `0x180030c90`
- `ole32!CoTaskMemFree` at `0x180030daa`
- `ole32!CoTaskMemFree` at `0x180030e0e`
- `ole32!CoTaskMemFree` at `0x180030e5b`
- `ole32!CoTaskMemFree` at `0x180030eeb`
- `ole32!CoTaskMemFree` at `0x180030f48`
- `ole32!CoTaskMemFree` at `0x180030b7a`
- `ole32!CoTaskMemFree` at `0x180030c90`
- `ole32!CoTaskMemFree` at `0x180030daa`
- `ole32!CoTaskMemFree` at `0x180030e0e`
- `ole32!CoTaskMemFree` at `0x180030e5b`
- `ole32!CoTaskMemFree` at `0x180030eeb`
- `ole32!CoTaskMemFree` at `0x180030f48`
- `ole32!StringFromCLSID` at `0x180030b5b`
- `ole32!StringFromCLSID` at `0x180030b5b`
- `OLEAUT32!__imp_SysAllocString` at `0x180030bdd`
- `OLEAUT32!__imp_SysAllocString` at `0x180030bf9`
- `OLEAUT32!__imp_SysAllocString` at `0x180030c1c`
- `OLEAUT32!__imp_SysAllocString` at `0x180030c3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180030bdd`
- `OLEAUT32!__imp_SysAllocString` at `0x180030bf9`
- `OLEAUT32!__imp_SysAllocString` at `0x180030c1c`
- `OLEAUT32!__imp_SysAllocString` at `0x180030c3f`
- `OLEAUT32!__imp_VariantInit` at `0x180030d26`
- `OLEAUT32!__imp_VariantInit` at `0x180030d26`
- `OLEAUT32!__imp_VariantClear` at `0x180030d73`
- `OLEAUT32!__imp_VariantClear` at `0x180030d7e`
- `OLEAUT32!__imp_VariantClear` at `0x180030dd7`
- `OLEAUT32!__imp_VariantClear` at `0x180030de2`
- `OLEAUT32!__imp_VariantClear` at `0x180030e24`
- `OLEAUT32!__imp_VariantClear` at `0x180030e2f`
- `OLEAUT32!__imp_VariantClear` at `0x180030eb4`
- `OLEAUT32!__imp_VariantClear` at `0x180030ebf`
- `OLEAUT32!__imp_VariantClear` at `0x180030f11`
- `OLEAUT32!__imp_VariantClear` at `0x180030f1c`
- `OLEAUT32!__imp_VariantClear` at `0x180030d73`
- `OLEAUT32!__imp_VariantClear` at `0x180030d7e`
- `OLEAUT32!__imp_VariantClear` at `0x180030dd7`
- `OLEAUT32!__imp_VariantClear` at `0x180030de2`
- `OLEAUT32!__imp_VariantClear` at `0x180030e24`
- `OLEAUT32!__imp_VariantClear` at `0x180030e2f`
- `OLEAUT32!__imp_VariantClear` at `0x180030eb4`
- `OLEAUT32!__imp_VariantClear` at `0x180030ebf`
- `OLEAUT32!__imp_VariantClear` at `0x180030f11`
- `OLEAUT32!__imp_VariantClear` at `0x180030f1c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180030bb2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180030bb2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030c80`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030d9a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030dfe`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030e4b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030edb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030f38`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030c80`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030d9a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030dfe`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030e4b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030edb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180030f38`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180030bcb`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180030bcb`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030c73`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030d8d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030df1`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030e3e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030ece`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030f2b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030c73`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030d8d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030df1`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030e3e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030ece`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180030f2b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180030cc3`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180030cc3`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180030ce3`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180030ce3`

## pseudocode

```c
__int64 __fastcall BPT::CoCreateUsingDiagnosticsMode(
        BPT *this,
        OLECHAR *a2,
        const OLECHAR *a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5)
{
  const struct _GUID *v7; // rsi
  HRESULT v8; // ebx
  SAFEARRAY *v9; // rax
  SAFEARRAY *v10; // rbx
  HRESULT v11; // eax
  int v12; // edi
  HRESULT v13; // eax
  HRESULT Vartype; // eax
  VARTYPE vt; // cx
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvt; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  SAFEARRAY *v19; // [rsp+A0h] [rbp+20h] BYREF
  LPOLESTR lpsz; // [rsp+A8h] [rbp+28h] BYREF
  const unsigned __int16 *v21; // [rsp+B8h] [rbp+38h] BYREF

  v21 = a4;
  lpsz = a2;
  if ( !this )
    return 2147942487LL;
  v7 = a5;
  if ( a5 )
    *(_QWORD *)&a5->Data1 = 0;
  v21 = 0;
  (**(void (__fastcall ***)(BPT *, GUID *, const unsigned __int16 **))this)(
    this,
    &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
    &v21);
  if ( !v21 )
    return 2147942487LL;
  lpsz = 0;
  v8 = StringFromCLSID(&GUID_28bccb9a_e66b_463c_82a4_09f320de94d7, &lpsz);
  if ( v8 )
  {
    if ( v8 >= 0 )
      v8 = -2147467259;
    if ( lpsz )
      CoTaskMemFree(lpsz);
    if ( v21 )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v21 + 16LL))(v21);
    return (unsigned int)v8;
  }
  rgsabound = (SAFEARRAYBOUND)4LL;
  v9 = SafeArrayCreate(8u, 1u, &rgsabound);
  v10 = v9;
  v19 = v9;
  if ( !v9 )
  {
    v11 = -2147024882;
LABEL_82:
    ATL::AtlThrowImpl(v11);
  }
  v11 = SafeArrayLock(v9);
  if ( v11 < 0 )
    goto LABEL_82;
  rgsabound = (SAFEARRAYBOUND)SysAllocString(lpsz);
  ATL::CComSafeArray<unsigned short *,8>::SetAt(&v19, 0, &rgsabound);
  rgsabound = (SAFEARRAYBOUND)SysAllocString(a3);
  ATL::CComSafeArray<unsigned short *,8>::SetAt(&v19, 1, &rgsabound);
  rgsabound = (SAFEARRAYBOUND)SysAllocString(&String);
  ATL::CComSafeArray<unsigned short *,8>::SetAt(&v19, 2, &rgsabound);
  rgsabound = (SAFEARRAYBOUND)SysAllocString(&String);
  v12 = ATL::CComSafeArray<unsigned short *,8>::SetAt(&v19, 3, &rgsabound);
  if ( v12 )
  {
    if ( v12 >= 0 )
      v12 = -2147467259;
    if ( v10 && SafeArrayUnlock(v10) >= 0 )
      SafeArrayDestroy(v10);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    if ( v21 )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v21 + 16LL))(v21);
    return (unsigned int)v12;
  }
  rgsabound = 0;
  v13 = SafeArrayCopy(v10, (SAFEARRAY **)&rgsabound);
  if ( v13 < 0 || !*(_QWORD *)&rgsabound )
  {
    pvt.vt = 10;
    pvt.lVal = v13;
    ATL::AtlThrowImpl(-2147024882);
  }
  Vartype = SafeArrayGetVartype(v10, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v10->fFeatures & 0x440) == 0x440 )
    vt = 9;
  pvt.vt = vt | 0x2000;
  pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
  VariantInit(&pvarg);
  v12 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const GUID *, __int64, _QWORD, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v21 + 32LL))(
          v21,
          &CGID_MSHTML,
          3802,
          0,
          &pvt,
          &pvarg);
  if ( v12 )
  {
    if ( v12 >= 0 )
      v12 = -2147467259;
    VariantClear(&pvarg);
    VariantClear(&pvt);
    if ( v10 && SafeArrayUnlock(v10) >= 0 )
      SafeArrayDestroy(v10);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    if ( v21 )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v21 + 16LL))(v21);
    return (unsigned int)v12;
  }
  if ( pvarg.vt != 13 )
  {
    VariantClear(&pvarg);
    VariantClear(&pvt);
    if ( v10 && SafeArrayUnlock(v10) >= 0 )
      SafeArrayDestroy(v10);
    if ( lpsz )
      CoTaskMemFree(lpsz);
LABEL_57:
    if ( v21 )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v21 + 16LL))(v21);
    return 2147549183LL;
  }
  if ( !pvarg.llVal )
  {
    VariantClear(&pvarg);
    VariantClear(&pvt);
    if ( v10 && SafeArrayUnlock(v10) >= 0 )
      SafeArrayDestroy(v10);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    goto LABEL_57;
  }
  if ( v7 )
  {
    v12 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, const struct _GUID *))pvarg.llVal)(
            pvarg.llVal,
            &GUID_eb0fe172_1a3a_11d0_89b3_00a0c90a90ac,
            v7);
    if ( v12 )
    {
      if ( v12 >= 0 )
        v12 = -2147467259;
      VariantClear(&pvarg);
      VariantClear(&pvt);
      if ( v10 && SafeArrayUnlock(v10) >= 0 )
        SafeArrayDestroy(v10);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      if ( v21 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v21 + 16LL))(v21);
      return (unsigned int)v12;
    }
  }
  VariantClear(&pvarg);
  VariantClear(&pvt);
  if ( v10 && SafeArrayUnlock(v10) >= 0 )
    SafeArrayDestroy(v10);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( v21 )
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v21 + 16LL))(v21);
  return 0;
}

```

## disassembly

```asm
0x180030ad4  mov     [rsp-18h+arg_10], rbx
0x180030ad9  mov     [rsp-18h+arg_18], r9
0x180030ade  mov     [rsp-18h+lpsz], rdx
0x180030ae3  push    rbp
0x180030ae4  push    rsi
0x180030ae5  push    rdi
0x180030ae6  mov     rbp, rsp
0x180030ae9  sub     rsp, 80h
0x180030af0  mov     rdi, r8
0x180030af3  test    rcx, rcx
0x180030af6  jnz     short loc_180030B10
0x180030af8  mov     eax, 80070057h
0x180030afd  mov     rbx, [rsp+80h+arg_10]
0x180030b05  add     rsp, 80h
0x180030b0c  pop     rdi
0x180030b0d  pop     rsi
0x180030b0e  pop     rbp
0x180030b0f  retn
0x180030b10  mov     rsi, [rbp+arg_20]
0x180030b14  test    rsi, rsi
0x180030b17  jz      short loc_180030B20
0x180030b19  mov     qword ptr [rsi], 0
0x180030b20  mov     [rbp+arg_18], 0
0x180030b28  mov     rax, [rcx]
0x180030b2b  lea     r8, [rbp+arg_18]
0x180030b2f  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x180030b36  mov     rax, [rax]
0x180030b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b3e  nop
0x180030b3f  cmp     [rbp+arg_18], 0
0x180030b44  jnz     short loc_180030B48
0x180030b46  jmp     short loc_180030AF8
0x180030b48  mov     [rbp+lpsz], 0
0x180030b50  lea     rdx, [rbp+lpsz]; lplpsz
0x180030b54  lea     rcx, _GUID_28bccb9a_e66b_463c_82a4_09f320de94d7; rclsid
0x180030b5b  call    cs:__imp_StringFromCLSID
0x180030b61  mov     ebx, eax
0x180030b63  test    eax, eax
0x180030b65  jz      short loc_180030B9E
0x180030b67  mov     eax, 80004005h
0x180030b6c  test    ebx, ebx
0x180030b6e  cmovns  ebx, eax
0x180030b71  mov     rcx, [rbp+lpsz]; pv
0x180030b75  test    rcx, rcx
0x180030b78  jz      short loc_180030B81
0x180030b7a  call    cs:__imp_CoTaskMemFree
0x180030b80  nop
0x180030b81  mov     rcx, [rbp+arg_18]
0x180030b85  test    rcx, rcx
0x180030b88  jz      short loc_180030B97
0x180030b8a  mov     rdx, [rcx]
0x180030b8d  mov     rax, [rdx+10h]
0x180030b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b96  nop
0x180030b97  mov     eax, ebx
0x180030b99  jmp     loc_180030AFD
0x180030b9e  mov     qword ptr [rbp+rgsabound.cElements], 4
0x180030ba6  mov     ecx, 8; vt
0x180030bab  lea     r8, [rbp+rgsabound]; rgsabound
0x180030baf  lea     edx, [rcx-7]; cDims
0x180030bb2  call    cs:__imp_SafeArrayCreate
0x180030bb8  mov     rbx, rax
0x180030bbb  mov     [rbp+arg_0], rax
0x180030bbf  test    rax, rax
0x180030bc2  jz      loc_180030F83
0x180030bc8  mov     rcx, rbx; psa
0x180030bcb  call    cs:__imp_SafeArrayLock
0x180030bd1  test    eax, eax
0x180030bd3  js      loc_180030F88
0x180030bd9  mov     rcx, [rbp+lpsz]; psz
0x180030bdd  call    cs:__imp_SysAllocString
0x180030be3  mov     qword ptr [rbp+rgsabound.cElements], rax
0x180030be7  lea     r8, [rbp+rgsabound]
0x180030beb  xor     edx, edx
0x180030bed  lea     rcx, [rbp+arg_0]
0x180030bf1  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x180030bf6  mov     rcx, rdi; psz
0x180030bf9  call    cs:__imp_SysAllocString
0x180030bff  mov     qword ptr [rbp+rgsabound.cElements], rax
0x180030c03  lea     r8, [rbp+rgsabound]
0x180030c07  mov     edx, 1
0x180030c0c  lea     rcx, [rbp+arg_0]
0x180030c10  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x180030c15  lea     rcx, String; psz
0x180030c1c  call    cs:__imp_SysAllocString
0x180030c22  mov     qword ptr [rbp+rgsabound.cElements], rax
0x180030c26  lea     r8, [rbp+rgsabound]
0x180030c2a  mov     edx, 2
0x180030c2f  lea     rcx, [rbp+arg_0]
0x180030c33  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x180030c38  lea     rcx, String; psz
0x180030c3f  call    cs:__imp_SysAllocString
0x180030c45  mov     qword ptr [rbp+rgsabound.cElements], rax
0x180030c49  lea     r8, [rbp+rgsabound]
0x180030c4d  mov     edx, 3
0x180030c52  lea     rcx, [rbp+arg_0]
0x180030c56  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x180030c5b  mov     edi, eax
0x180030c5d  test    eax, eax
0x180030c5f  jz      short loc_180030CB4
0x180030c61  mov     eax, 80004005h
0x180030c66  test    edi, edi
0x180030c68  cmovns  edi, eax
0x180030c6b  test    rbx, rbx
0x180030c6e  jz      short loc_180030C87
0x180030c70  mov     rcx, rbx; psa
0x180030c73  call    cs:__imp_SafeArrayUnlock
0x180030c79  test    eax, eax
0x180030c7b  js      short loc_180030C87
0x180030c7d  mov     rcx, rbx; psa
0x180030c80  call    cs:__imp_SafeArrayDestroy
0x180030c86  nop
0x180030c87  mov     rcx, [rbp+lpsz]; pv
0x180030c8b  test    rcx, rcx
0x180030c8e  jz      short loc_180030C97
0x180030c90  call    cs:__imp_CoTaskMemFree
0x180030c96  nop
0x180030c97  mov     rcx, [rbp+arg_18]
0x180030c9b  test    rcx, rcx
0x180030c9e  jz      short loc_180030CAD
0x180030ca0  mov     rdx, [rcx]
0x180030ca3  mov     rax, [rdx+10h]
0x180030ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cac  nop
0x180030cad  mov     eax, edi
0x180030caf  jmp     loc_180030AFD
0x180030cb4  mov     qword ptr [rbp+rgsabound.cElements], 0
0x180030cbc  lea     rdx, [rbp+rgsabound]; ppsaOut
0x180030cc0  mov     rcx, rbx; psa
0x180030cc3  call    cs:__imp_SafeArrayCopy
0x180030cc9  test    eax, eax
0x180030ccb  js      loc_180030F6C
0x180030cd1  cmp     qword ptr [rbp+rgsabound.cElements], 0
0x180030cd6  jz      loc_180030F6C
0x180030cdc  lea     rdx, [rbp+pvt]; pvt
0x180030ce0  mov     rcx, rbx; psa
0x180030ce3  call    cs:__imp_SafeArrayGetVartype
0x180030ce9  movzx   ecx, [rbp+pvt]
0x180030ced  test    eax, eax
0x180030cef  js      short loc_180030D0D
0x180030cf1  cmp     cx, 0Dh
0x180030cf5  jnz     short loc_180030D0D
0x180030cf7  movzx   eax, word ptr [rbx+2]
0x180030cfb  mov     edx, 440h
0x180030d00  and     ax, dx
0x180030d03  cmp     ax, dx
0x180030d06  jnz     short loc_180030D0D
0x180030d08  mov     ecx, 9
0x180030d0d  or      cx, 2000h
0x180030d12  mov     [rbp+pvt], cx
0x180030d16  mov     eax, [rbp+rgsabound.cElements]
0x180030d19  mov     [rbp+var_30], eax
0x180030d1c  mov     eax, [rbp+rgsabound.lLbound]
0x180030d1f  mov     [rbp+var_2C], eax
0x180030d22  lea     rcx, [rbp+pvarg]; pvarg
0x180030d26  call    cs:__imp_VariantInit
0x180030d2c  nop
0x180030d2d  mov     rcx, [rbp+arg_18]
0x180030d31  mov     rax, [rcx]
0x180030d34  lea     rdx, [rbp+pvarg]
0x180030d38  mov     [rsp+80h+var_58], rdx
0x180030d3d  lea     rdx, [rbp+pvt]
0x180030d41  mov     [rsp+80h+var_60], rdx
0x180030d46  xor     r9d, r9d
0x180030d49  mov     r8d, 0EDAh
0x180030d4f  lea     rdx, CGID_MSHTML
0x180030d56  mov     rax, [rax+20h]
0x180030d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d5f  mov     edi, eax
0x180030d61  test    eax, eax
0x180030d63  jz      short loc_180030DCC
0x180030d65  mov     eax, 80004005h
0x180030d6a  test    edi, edi
0x180030d6c  cmovns  edi, eax
0x180030d6f  lea     rcx, [rbp+pvarg]; pvarg
0x180030d73  call    cs:__imp_VariantClear
0x180030d79  nop
0x180030d7a  lea     rcx, [rbp+pvt]; pvarg
0x180030d7e  call    cs:__imp_VariantClear
0x180030d84  nop
0x180030d85  test    rbx, rbx
0x180030d88  jz      short loc_180030DA1
0x180030d8a  mov     rcx, rbx; psa
0x180030d8d  call    cs:__imp_SafeArrayUnlock
0x180030d93  test    eax, eax
0x180030d95  js      short loc_180030DA1
0x180030d97  mov     rcx, rbx; psa
0x180030d9a  call    cs:__imp_SafeArrayDestroy
0x180030da0  nop
0x180030da1  mov     rcx, [rbp+lpsz]; pv
0x180030da5  test    rcx, rcx
0x180030da8  jz      short loc_180030DB1
0x180030daa  call    cs:__imp_CoTaskMemFree
0x180030db0  nop
0x180030db1  mov     rcx, [rbp+arg_18]
0x180030db5  test    rcx, rcx
0x180030db8  jz      short loc_180030DC7
0x180030dba  mov     rdx, [rcx]
0x180030dbd  mov     rax, [rdx+10h]
0x180030dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030dc6  nop
0x180030dc7  jmp     loc_180030CAD
0x180030dcc  cmp     word ptr [rbp+pvarg], 0Dh
0x180030dd1  jz      short loc_180030E17
0x180030dd3  lea     rcx, [rbp+pvarg]; pvarg
0x180030dd7  call    cs:__imp_VariantClear
0x180030ddd  nop
0x180030dde  lea     rcx, [rbp+pvt]; pvarg
0x180030de2  call    cs:__imp_VariantClear
0x180030de8  nop
0x180030de9  test    rbx, rbx
0x180030dec  jz      short loc_180030E05
0x180030dee  mov     rcx, rbx; psa
0x180030df1  call    cs:__imp_SafeArrayUnlock
0x180030df7  test    eax, eax
0x180030df9  js      short loc_180030E05
0x180030dfb  mov     rcx, rbx; psa
0x180030dfe  call    cs:__imp_SafeArrayDestroy
0x180030e04  nop
0x180030e05  mov     rcx, [rbp+lpsz]; pv
0x180030e09  test    rcx, rcx
0x180030e0c  jz      short loc_180030E15
0x180030e0e  call    cs:__imp_CoTaskMemFree
0x180030e14  nop
0x180030e15  jmp     short loc_180030E62
0x180030e17  mov     rcx, qword ptr [rbp+pvarg+8]
0x180030e1b  test    rcx, rcx
0x180030e1e  jnz     short loc_180030E82
0x180030e20  lea     rcx, [rbp+pvarg]; pvarg
0x180030e24  call    cs:__imp_VariantClear
0x180030e2a  nop
0x180030e2b  lea     rcx, [rbp+pvt]; pvarg
0x180030e2f  call    cs:__imp_VariantClear
0x180030e35  nop
0x180030e36  test    rbx, rbx
0x180030e39  jz      short loc_180030E52
0x180030e3b  mov     rcx, rbx; psa
0x180030e3e  call    cs:__imp_SafeArrayUnlock
0x180030e44  test    eax, eax
0x180030e46  js      short loc_180030E52
0x180030e48  mov     rcx, rbx; psa
0x180030e4b  call    cs:__imp_SafeArrayDestroy
0x180030e51  nop
0x180030e52  mov     rcx, [rbp+lpsz]; pv
0x180030e56  test    rcx, rcx
0x180030e59  jz      short loc_180030E62
0x180030e5b  call    cs:__imp_CoTaskMemFree
0x180030e61  nop
0x180030e62  mov     rcx, [rbp+arg_18]
0x180030e66  test    rcx, rcx
0x180030e69  jz      short loc_180030E78
0x180030e6b  mov     rax, [rcx]
0x180030e6e  mov     rax, [rax+10h]
0x180030e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e77  nop
0x180030e78  mov     eax, 8000FFFFh
0x180030e7d  jmp     loc_180030AFD
0x180030e82  test    rsi, rsi
0x180030e85  jz      loc_180030F0D
0x180030e8b  mov     rax, [rcx]
0x180030e8e  mov     r8, rsi
0x180030e91  lea     rdx, _GUID_eb0fe172_1a3a_11d0_89b3_00a0c90a90ac
0x180030e98  mov     rax, [rax]
0x180030e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ea0  mov     edi, eax
0x180030ea2  test    eax, eax
0x180030ea4  jz      short loc_180030F0D
0x180030ea6  mov     eax, 80004005h
0x180030eab  test    edi, edi
0x180030ead  cmovns  edi, eax
0x180030eb0  lea     rcx, [rbp+pvarg]; pvarg
0x180030eb4  call    cs:__imp_VariantClear
0x180030eba  nop
0x180030ebb  lea     rcx, [rbp+pvt]; pvarg
0x180030ebf  call    cs:__imp_VariantClear
0x180030ec5  nop
0x180030ec6  test    rbx, rbx
0x180030ec9  jz      short loc_180030EE2
0x180030ecb  mov     rcx, rbx; psa
0x180030ece  call    cs:__imp_SafeArrayUnlock
0x180030ed4  test    eax, eax
0x180030ed6  js      short loc_180030EE2
0x180030ed8  mov     rcx, rbx; psa
0x180030edb  call    cs:__imp_SafeArrayDestroy
0x180030ee1  nop
0x180030ee2  mov     rcx, [rbp+lpsz]; pv
0x180030ee6  test    rcx, rcx
0x180030ee9  jz      short loc_180030EF2
0x180030eeb  call    cs:__imp_CoTaskMemFree
0x180030ef1  nop
0x180030ef2  mov     rcx, [rbp+arg_18]
0x180030ef6  test    rcx, rcx
0x180030ef9  jz      short loc_180030F08
0x180030efb  mov     rdx, [rcx]
0x180030efe  mov     rax, [rdx+10h]
0x180030f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f07  nop
0x180030f08  jmp     loc_180030CAD
0x180030f0d  lea     rcx, [rbp+pvarg]; pvarg
0x180030f11  call    cs:__imp_VariantClear
  ... truncated ...
```
