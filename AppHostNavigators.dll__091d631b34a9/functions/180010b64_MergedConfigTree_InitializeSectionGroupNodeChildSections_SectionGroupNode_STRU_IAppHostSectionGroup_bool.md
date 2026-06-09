# MergedConfigTree::InitializeSectionGroupNodeChildSections(SectionGroupNode *,STRU &,IAppHostSectionGroup *,bool)

- ea: `0x180010b64`
- end: `0x180010d5e`
- name: `?InitializeSectionGroupNodeChildSections@MergedConfigTree@@AEAAXPEAVSectionGroupNode@@AEAVSTRU@@PEAUIAppHostSectionGroup@@_N@Z`
- size: `506`
- prototype: `void __usercall(MergedConfigTree *__hidden this@<rcx>, struct SectionGroupNode *@<rdx>, struct STRU *@<r8>, struct IAppHostSectionGroup *@<r9>, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010d64`

## callees

- `0x1800021a4`
- `0x180007aac`
- `0x18000ab38`
- `0x18000acd0`
- `0x18000d894`
- `0x180010b64`
- `0x180012c1c`
- `0x180012e90`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180010c4a`
- `OLEAUT32!__imp_VariantClear` at `0x180010c4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall MergedConfigTree::InitializeSectionGroupNodeChildSections(
        MergedConfigTree *this,
        struct SectionGroupNode *a2,
        struct STRU *a3,
        struct IAppHostSectionGroup *a4,
        bool a5)
{
  unsigned int v8; // r15d
  int v9; // eax
  int v10; // eax
  unsigned int i; // ebx
  __int64 v12; // rax
  int v13; // esi
  int v14; // eax
  unsigned int CCH; // eax
  unsigned int v16; // r9d
  int v17; // eax
  struct SectionNode *SectionDescendantsWithName; // rax
  unsigned __int16 *v19; // [rsp+20h] [rbp-50h] BYREF
  struct IUnknown *v20; // [rsp+28h] [rbp-48h] BYREF
  __int64 *v21; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v23; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+B0h] [rbp+40h] BYREF
  __int64 pExceptionObject; // [rsp+B8h] [rbp+48h] BYREF

  v8 = *((_DWORD *)a3 + 4);
  v21 = 0;
  v9 = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, __int64 **))a4->lpVtbl->get_Sections)(a4, &v21);
  if ( v9 < 0 )
  {
    LODWORD(pExceptionObject) = v9;
    throw (long *)&pExceptionObject;
  }
  v24 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v21 + 24))(v21, &v24);
  if ( v10 < 0 )
  {
    LODWORD(pExceptionObject) = v10;
    throw (long *)&pExceptionObject;
  }
  for ( i = 0; i < v24; ++i )
  {
    STRU::SetLen(a3, v8);
    v20 = 0;
    v12 = *v21;
    pvarg.vt = 19;
    pvarg.lVal = i;
    v23 = pvarg;
    v13 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, struct IUnknown **))(v12 + 32))(v21, &v23, &v20);
    VariantClear(&pvarg);
    if ( v13 < 0 )
    {
      LODWORD(pExceptionObject) = v13;
      throw (long *)&pExceptionObject;
    }
    v19 = 0;
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 **))v20->lpVtbl[1].QueryInterface)(v20, &v19);
    if ( v14 < 0 )
    {
      LODWORD(pExceptionObject) = v14;
      throw (long *)&pExceptionObject;
    }
    CCH = ScopedBSTR::QueryCCH((ScopedBSTR *)&v19);
    v17 = STRU::Append(a3, v19, CCH, v16);
    if ( v17 < 0 )
    {
      LODWORD(pExceptionObject) = v17;
      throw (long *)&pExceptionObject;
    }
    pExceptionObject = *((_QWORD *)a3 + 1);
    HASH_TABLE<unsigned short const,unsigned short const *>::FindKey(
      *((_QWORD *)this + 3) + 24LL,
      pExceptionObject,
      &pExceptionObject);
    if ( pExceptionObject )
    {
      SectionDescendantsWithName = SectionGroupNode::FindOrCreateSectionDescendantsWithName(a2, this, v19);
      if ( a5 && *((struct IUnknown **)SectionDescendantsWithName + 13) != v20 )
        ATL::AtlComPtrAssign((struct IUnknown **)SectionDescendantsWithName + 13, v20);
    }
    ScopedBSTR::Reset((ScopedBSTR *)&v19);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
  }
  STRU::SetLen(a3, v8);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v21);
}

```

## disassembly

```asm
0x180010b64  mov     [rsp-28h+arg_0], rbx
0x180010b69  mov     [rsp-28h+arg_8], rsi
0x180010b6e  push    rbp
0x180010b6f  push    rdi
0x180010b70  push    r12
0x180010b72  push    r14
0x180010b74  push    r15
0x180010b76  mov     rbp, rsp
0x180010b79  sub     rsp, 70h
0x180010b7d  mov     rdi, r8
0x180010b80  mov     r12, rdx
0x180010b83  mov     r14, rcx
0x180010b86  mov     r15d, [r8+10h]
0x180010b8a  mov     [rbp+var_40], 0
0x180010b92  mov     rax, [r9]
0x180010b95  lea     rdx, [rbp+var_40]
0x180010b99  mov     rcx, r9
0x180010b9c  mov     rax, [rax+28h]
0x180010ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ba5  test    eax, eax
0x180010ba7  jns     short loc_180010BBD
0x180010ba9  mov     dword ptr [rbp+pExceptionObject], eax
0x180010bac  lea     rdx, _TI1J; pThrowInfo
0x180010bb3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010bb7  call    _CxxThrowException_0
0x180010bbd  mov     [rbp+arg_10], 0
0x180010bc4  mov     rcx, [rbp+var_40]
0x180010bc8  mov     rax, [rcx]
0x180010bcb  lea     rdx, [rbp+arg_10]
0x180010bcf  mov     rax, [rax+18h]
0x180010bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bd8  test    eax, eax
0x180010bda  jns     short loc_180010BF0
0x180010bdc  mov     dword ptr [rbp+pExceptionObject], eax
0x180010bdf  lea     rdx, _TI1J; pThrowInfo
0x180010be6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010bea  call    _CxxThrowException_0
0x180010bf0  xor     ebx, ebx
0x180010bf2  mov     edx, r15d; unsigned int
0x180010bf5  mov     rcx, rdi; this
0x180010bf8  cmp     ebx, [rbp+arg_10]
0x180010bfb  jnb     loc_180010D36
0x180010c01  call    ?SetLen@STRU@@QEAAJK@Z; STRU::SetLen(ulong)
0x180010c06  mov     [rbp+var_48], 0
0x180010c0e  mov     rcx, [rbp+var_40]
0x180010c12  mov     rax, [rcx]
0x180010c15  mov     edx, 13h
0x180010c1a  mov     word ptr [rbp+pvarg], dx
0x180010c1e  mov     dword ptr [rbp+pvarg+8], ebx
0x180010c21  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180010c25  movaps  [rbp+var_20], xmm0
0x180010c29  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180010c2e  movsd   [rbp+var_10], xmm1
0x180010c33  lea     r8, [rbp+var_48]
0x180010c37  lea     rdx, [rbp+var_20]
0x180010c3b  mov     rax, [rax+20h]
0x180010c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c44  mov     esi, eax
0x180010c46  lea     rcx, [rbp+pvarg]; pvarg
0x180010c4a  call    cs:__imp_VariantClear
0x180010c50  test    esi, esi
0x180010c52  js      loc_180010D22
0x180010c58  mov     [rbp+var_50], 0
0x180010c60  mov     rcx, [rbp+var_48]
0x180010c64  mov     rax, [rcx]
0x180010c67  lea     rdx, [rbp+var_50]
0x180010c6b  mov     rax, [rax+18h]
0x180010c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c74  test    eax, eax
0x180010c76  js      loc_180010D0E
0x180010c7c  lea     rcx, [rbp+var_50]; this
0x180010c80  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x180010c85  mov     r8d, eax; unsigned int
0x180010c88  mov     rdx, [rbp+var_50]; unsigned __int16 *
0x180010c8c  mov     rcx, rdi; this
0x180010c8f  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180010c94  test    eax, eax
0x180010c96  js      short loc_180010CFA
0x180010c98  mov     rdx, [rdi+8]
0x180010c9c  mov     [rbp+pExceptionObject], rdx
0x180010ca0  mov     rcx, [r14+18h]
0x180010ca4  add     rcx, 18h
0x180010ca8  lea     r8, [rbp+pExceptionObject]
0x180010cac  call    ?FindKey@?$HASH_TABLE@$$CBGPEBG@@QEAAXPEBGPEAPEBG@Z; HASH_TABLE<ushort const,ushort const *>::FindKey(ushort const *,ushort const * *)
0x180010cb1  cmp     [rbp+pExceptionObject], 0
0x180010cb6  jz      short loc_180010CE0
0x180010cb8  mov     r8, [rbp+var_50]; unsigned __int16 *
0x180010cbc  mov     rdx, r14; struct ConfigTreeBase *
0x180010cbf  mov     rcx, r12; this
0x180010cc2  call    ?FindOrCreateSectionDescendantsWithName@SectionGroupNode@@QEAAPEAVSectionNode@@PEAVConfigTreeBase@@PEBG@Z; SectionGroupNode::FindOrCreateSectionDescendantsWithName(ConfigTreeBase *,ushort const *)
0x180010cc7  cmp     [rbp+arg_20], 0
0x180010ccb  jz      short loc_180010CE0
0x180010ccd  mov     rdx, [rbp+var_48]; struct IUnknown *
0x180010cd1  lea     rcx, [rax+68h]; struct IUnknown **
0x180010cd5  cmp     [rcx], rdx
0x180010cd8  jz      short loc_180010CE0
0x180010cda  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180010cdf  nop
0x180010ce0  lea     rcx, [rbp+var_50]; this
0x180010ce4  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x180010ce9  nop
0x180010cea  lea     rcx, [rbp+var_48]
0x180010cee  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010cf3  inc     ebx
0x180010cf5  jmp     loc_180010BF2
0x180010cfa  mov     dword ptr [rbp+pExceptionObject], eax
0x180010cfd  lea     rdx, _TI1J; pThrowInfo
0x180010d04  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010d08  call    _CxxThrowException_0
0x180010d0e  mov     dword ptr [rbp+pExceptionObject], eax
0x180010d11  lea     rdx, _TI1J; pThrowInfo
0x180010d18  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010d1c  call    _CxxThrowException_0
0x180010d22  mov     dword ptr [rbp+pExceptionObject], esi
0x180010d25  lea     rdx, _TI1J; pThrowInfo
0x180010d2c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010d30  call    _CxxThrowException_0
0x180010d36  call    ?SetLen@STRU@@QEAAJK@Z; STRU::SetLen(ulong)
0x180010d3b  nop
0x180010d3c  lea     rcx, [rbp+var_40]
0x180010d40  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010d45  lea     r11, [rsp+70h+var_s0]
0x180010d4a  mov     rbx, [r11+30h]
0x180010d4e  mov     rsi, [r11+38h]
0x180010d52  mov     rsp, r11
0x180010d55  pop     r15
0x180010d57  pop     r14
0x180010d59  pop     r12
0x180010d5b  pop     rdi
0x180010d5c  pop     rbp
0x180010d5d  retn
```
