# SiteSectionElementCollectionProcessorBase::Invoke(ConfigPathNavigationTree *,IAppHostElement *,ushort *,STRU &)

- ea: `0x18000d1a8`
- end: `0x18000d3d4`
- name: `?Invoke@SiteSectionElementCollectionProcessorBase@@QEAAXPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@PEAGAEAVSTRU@@@Z`
- size: `556`
- prototype: `void __fastcall(SiteSectionElementCollectionProcessorBase *__hidden this, struct ConfigPathNavigationTree *, struct IAppHostElement *, unsigned __int16 *, struct STRU *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cee0`
- `0x18000d4c0`
- `0x18000d590`

## callees

- `0x1800021a4`
- `0x180004728`
- `0x18000d1a8`
- `0x18000d894`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000d288`
- `OLEAUT32!__imp_VariantClear` at `0x18000d288`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SiteSectionElementCollectionProcessorBase::Invoke(
        SiteSectionElementCollectionProcessorBase *this,
        struct ConfigPathNavigationTree *a2,
        struct IAppHostElement *a3,
        unsigned __int16 *a4,
        struct STRU *a5)
{
  STRU *v8; // rsi
  unsigned int v9; // r13d
  int v10; // eax
  int v11; // eax
  unsigned int i; // ebx
  __int64 v13; // rax
  int v14; // edi
  int v15; // eax
  int v16; // eax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rcx
  unsigned __int16 j; // dx
  int v20; // eax
  unsigned __int16 *v21; // [rsp+30h] [rbp-61h] BYREF
  __int64 v22; // [rsp+38h] [rbp-59h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-51h] BYREF
  __int64 v24; // [rsp+48h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v26[3]; // [rsp+68h] [rbp-29h] BYREF
  VARIANTARG v27; // [rsp+80h] [rbp-11h] BYREF
  int pExceptionObject; // [rsp+100h] [rbp+6Fh] BYREF

  v8 = a5;
  v9 = *((_DWORD *)a5 + 4);
  v23 = 0;
  v10 = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 **))a3->lpVtbl->get_Collection)(a3, &v23);
  if ( v10 < 0 )
  {
    pExceptionObject = v10;
    throw (long *)&pExceptionObject;
  }
  LODWORD(a5) = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, struct STRU **))(*v23 + 24))(v23, &a5);
  if ( v11 < 0 )
  {
    pExceptionObject = v11;
    throw (long *)&pExceptionObject;
  }
  for ( i = 0; i < (unsigned int)a5; ++i )
  {
    STRU::SetLen(v8, v9);
    v22 = 0;
    v13 = *v23;
    pvarg.vt = 19;
    pvarg.lVal = i;
    v27 = pvarg;
    v14 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v13 + 32))(v23, &v27, &v22);
    VariantClear(&pvarg);
    if ( v14 < 0 )
    {
      pExceptionObject = v14;
      throw (long *)&pExceptionObject;
    }
    v24 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 *))(*(_QWORD *)v22 + 88LL))(v22, a4, &v24);
    if ( v15 < 0 )
    {
      pExceptionObject = v15;
      throw (long *)&pExceptionObject;
    }
    v21 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v24 + 56LL))(v24, &v21);
    if ( v16 < 0 )
    {
      pExceptionObject = v16;
      throw (long *)&pExceptionObject;
    }
    v17 = v21;
    v18 = v21;
    for ( j = *v21; j == 47; j = *v18 )
      ++v18;
    if ( j )
    {
      v26[0] = L"/";
      v26[1] = v18;
      v20 = STRU::AuxAppend(v8, (const unsigned __int16 *const *const)v26, 2u);
      if ( v20 < 0 )
      {
        pExceptionObject = v20;
        throw (long *)&pExceptionObject;
      }
      v17 = v21;
    }
    (**(void (__fastcall ***)(SiteSectionElementCollectionProcessorBase *, struct ConfigPathNavigationTree *, __int64, STRU *, unsigned __int16 *))this)(
      this,
      a2,
      v22,
      v8,
      v17);
    ScopedBSTR::Reset((ScopedBSTR *)&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v23);
}

```

## disassembly

```asm
0x18000d1a8  push    rbp
0x18000d1aa  push    rbx
0x18000d1ab  push    rsi
0x18000d1ac  push    rdi
0x18000d1ad  push    r12
0x18000d1af  push    r13
0x18000d1b1  push    r14
0x18000d1b3  push    r15
0x18000d1b5  lea     rbp, [rsp-17h]
0x18000d1ba  sub     rsp, 0A8h
0x18000d1c1  mov     r15, r9
0x18000d1c4  mov     r12, rdx
0x18000d1c7  mov     r14, rcx
0x18000d1ca  mov     rsi, [rbp+4Fh+arg_20]
0x18000d1ce  mov     r13d, [rsi+10h]
0x18000d1d2  xor     edi, edi
0x18000d1d4  mov     [rbp+4Fh+var_A0], rdi
0x18000d1d8  mov     rax, [r8]
0x18000d1db  lea     rdx, [rbp+4Fh+var_A0]
0x18000d1df  mov     rcx, r8
0x18000d1e2  mov     rax, [rax+20h]
0x18000d1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1eb  test    eax, eax
0x18000d1ed  jns     short loc_18000D203
0x18000d1ef  mov     [rbp+4Fh+pExceptionObject], eax
0x18000d1f2  lea     rdx, _TI1J; pThrowInfo
0x18000d1f9  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000d1fd  call    _CxxThrowException_0
0x18000d203  mov     dword ptr [rbp+4Fh+arg_20], edi
0x18000d206  mov     rcx, [rbp+4Fh+var_A0]
0x18000d20a  mov     rax, [rcx]
0x18000d20d  lea     rdx, [rbp+4Fh+arg_20]
0x18000d211  mov     rax, [rax+18h]
0x18000d215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d21a  test    eax, eax
0x18000d21c  jns     short loc_18000D232
0x18000d21e  mov     [rbp+4Fh+pExceptionObject], eax
0x18000d221  lea     rdx, _TI1J; pThrowInfo
0x18000d228  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000d22c  call    _CxxThrowException_0
0x18000d232  mov     ebx, edi
0x18000d234  cmp     ebx, dword ptr [rbp+4Fh+arg_20]
0x18000d237  jnb     loc_18000D3B7
0x18000d23d  mov     edx, r13d; unsigned int
0x18000d240  mov     rcx, rsi; this
0x18000d243  call    ?SetLen@STRU@@QEAAJK@Z; STRU::SetLen(ulong)
0x18000d248  mov     [rbp+4Fh+var_A8], rdi
0x18000d24c  mov     rcx, [rbp+4Fh+var_A0]
0x18000d250  mov     rax, [rcx]
0x18000d253  mov     edx, 13h
0x18000d258  mov     word ptr [rbp+4Fh+pvarg], dx
0x18000d25c  mov     dword ptr [rbp+4Fh+pvarg+8], ebx
0x18000d25f  movups  xmm0, xmmword ptr [rbp+4Fh+pvarg]
0x18000d263  movaps  [rbp+4Fh+var_60], xmm0
0x18000d267  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18000d26c  movsd   [rbp+4Fh+var_50], xmm1
0x18000d271  lea     r8, [rbp+4Fh+var_A8]
0x18000d275  lea     rdx, [rbp+4Fh+var_60]
0x18000d279  mov     rax, [rax+20h]
0x18000d27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d282  mov     edi, eax
0x18000d284  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000d288  call    cs:__imp_VariantClear
0x18000d28e  test    edi, edi
0x18000d290  js      loc_18000D3A3
0x18000d296  xor     edi, edi
0x18000d298  mov     [rbp+4Fh+var_98], rdi
0x18000d29c  mov     rcx, [rbp+4Fh+var_A8]
0x18000d2a0  mov     rax, [rcx]
0x18000d2a3  lea     r8, [rbp+4Fh+var_98]
0x18000d2a7  mov     rdx, r15
0x18000d2aa  mov     rax, [rax+58h]
0x18000d2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2b3  test    eax, eax
0x18000d2b5  js      loc_18000D38F
0x18000d2bb  mov     [rbp+4Fh+var_B0], rdi
0x18000d2bf  mov     rcx, [rbp+4Fh+var_98]
0x18000d2c3  mov     rax, [rcx]
0x18000d2c6  lea     rdx, [rbp+4Fh+var_B0]
0x18000d2ca  mov     rax, [rax+38h]
0x18000d2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2d3  test    eax, eax
0x18000d2d5  js      loc_18000D37B
0x18000d2db  mov     rax, [rbp+4Fh+var_B0]
0x18000d2df  mov     rcx, rax
0x18000d2e2  movzx   edx, word ptr [rax]
0x18000d2e5  jmp     short loc_18000D2EE
0x18000d2e7  add     rcx, 2
0x18000d2eb  movzx   edx, word ptr [rcx]
0x18000d2ee  cmp     dx, 2Fh ; '/'
0x18000d2f2  jz      short loc_18000D2E7
0x18000d2f4  test    dx, dx
0x18000d2f7  jz      short loc_18000D322
0x18000d2f9  lea     rax, asc_180018280; "/"
0x18000d300  mov     [rbp+4Fh+var_78], rax
0x18000d304  mov     [rbp+4Fh+var_70], rcx
0x18000d308  mov     r8d, 2; unsigned __int64
0x18000d30e  lea     rdx, [rbp+4Fh+var_78]; unsigned __int16 **
0x18000d312  mov     rcx, rsi; this
0x18000d315  call    ?AuxAppend@STRU@@AEAAJQEBQEBG_K@Z; STRU::AuxAppend(ushort const * const * const,unsigned __int64)
0x18000d31a  test    eax, eax
0x18000d31c  js      short loc_18000D367
0x18000d31e  mov     rax, [rbp+4Fh+var_B0]
0x18000d322  mov     rcx, [r14]
0x18000d325  mov     r10, [rcx]
0x18000d328  mov     [rsp+0E0h+var_C0], rax
0x18000d32d  mov     r9, rsi
0x18000d330  mov     r8, [rbp+4Fh+var_A8]
0x18000d334  mov     rdx, r12
0x18000d337  mov     rcx, r14
0x18000d33a  mov     rax, r10
0x18000d33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d342  nop
0x18000d343  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000d347  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000d34c  nop
0x18000d34d  lea     rcx, [rbp+4Fh+var_98]
0x18000d351  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d356  nop
0x18000d357  lea     rcx, [rbp+4Fh+var_A8]
0x18000d35b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d360  inc     ebx
0x18000d362  jmp     loc_18000D234
0x18000d367  mov     [rbp+4Fh+pExceptionObject], eax
0x18000d36a  lea     rdx, _TI1J; pThrowInfo
0x18000d371  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000d375  call    _CxxThrowException_0
0x18000d37b  mov     [rbp+4Fh+pExceptionObject], eax
0x18000d37e  lea     rdx, _TI1J; pThrowInfo
0x18000d385  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000d389  call    _CxxThrowException_0
0x18000d38f  mov     [rbp+4Fh+pExceptionObject], eax
0x18000d392  lea     rdx, _TI1J; pThrowInfo
0x18000d399  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000d39d  call    _CxxThrowException_0
0x18000d3a3  mov     [rbp+4Fh+pExceptionObject], edi
0x18000d3a6  lea     rdx, _TI1J; pThrowInfo
0x18000d3ad  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000d3b1  call    _CxxThrowException_0
0x18000d3b7  lea     rcx, [rbp+4Fh+var_A0]
0x18000d3bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d3c0  add     rsp, 0A8h
0x18000d3c7  pop     r15
0x18000d3c9  pop     r14
0x18000d3cb  pop     r13
0x18000d3cd  pop     r12
0x18000d3cf  pop     rdi
0x18000d3d0  pop     rsi
0x18000d3d1  pop     rbx
0x18000d3d2  pop     rbp
0x18000d3d3  retn
```
