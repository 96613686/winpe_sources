# MergedConfigTree::InitializeSectionGroupNodeChildSectionGroups(SectionGroupNode *,STRU &,IAppHostSectionGroup *,bool)

- ea: `0x1800109c0`
- end: `0x180010b5d`
- name: `?InitializeSectionGroupNodeChildSectionGroups@MergedConfigTree@@AEAAXPEAVSectionGroupNode@@AEAVSTRU@@PEAUIAppHostSectionGroup@@_N@Z`
- size: `413`
- prototype: `void __usercall(MergedConfigTree *__hidden this@<rcx>, struct SectionGroupNode *@<rdx>, struct STRU *@<r8>, struct IAppHostSectionGroup *@<r9>, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010d64`

## callees

- `0x1800021a4`
- `0x18000ab38`
- `0x18000aea0`
- `0x18000d894`
- `0x1800109c0`
- `0x180010d64`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180010a7b`
- `OLEAUT32!__imp_VariantClear` at `0x180010a7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MergedConfigTree::InitializeSectionGroupNodeChildSectionGroups(
        MergedConfigTree *this,
        struct SectionGroupNode *a2,
        struct STRU *a3,
        struct IAppHostSectionGroup *a4,
        bool a5)
{
  unsigned int v8; // r15d
  int v9; // eax
  unsigned int v10; // edi
  bool v11; // r13
  struct IAppHostSectionGroupVtbl *lpVtbl; // rax
  int v13; // esi
  int v14; // eax
  struct SectionGroupNode *SectionGroupChildWithName; // rsi
  unsigned int v16; // r9d
  int v17; // eax
  unsigned __int16 *v18; // [rsp+30h] [rbp-50h] BYREF
  struct IAppHostSectionGroup *v19; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG v21; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v23; // [rsp+D0h] [rbp+50h] BYREF
  int pExceptionObject; // [rsp+D8h] [rbp+58h] BYREF

  v8 = *((_DWORD *)a3 + 4);
  v23 = 0;
  v9 = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, unsigned int *))a4->lpVtbl->get_Count)(a4, &v23);
  if ( v9 < 0 )
  {
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
  v10 = 0;
  v11 = a5;
  while ( v10 < v23 )
  {
    STRU::SetLen(a3, v8);
    v19 = 0;
    lpVtbl = a4->lpVtbl;
    pvarg.vt = 19;
    pvarg.lVal = v10;
    v21 = pvarg;
    v13 = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, VARIANTARG *, struct IAppHostSectionGroup **))lpVtbl->get_Item)(
            a4,
            &v21,
            &v19);
    VariantClear(&pvarg);
    if ( v13 < 0 )
    {
      pExceptionObject = v13;
      throw (long *)&pExceptionObject;
    }
    v18 = 0;
    v14 = ((__int64 (__fastcall *)(struct IAppHostSectionGroup *, unsigned __int16 **))v19->lpVtbl->get_Name)(v19, &v18);
    if ( v14 < 0 )
    {
      pExceptionObject = v14;
      throw (long *)&pExceptionObject;
    }
    SectionGroupChildWithName = SectionGroupNode::FindOrCreateSectionGroupChildWithName(a2, this, v18);
    v17 = STRU::Append(a3, v18, 0, v16);
    if ( v17 < 0 )
    {
      pExceptionObject = v17;
      throw (long *)&pExceptionObject;
    }
    MergedConfigTree::InitializeSectionGroupNodeChildren(this, SectionGroupChildWithName, a3, v19, v11);
    ScopedBSTR::Reset((ScopedBSTR *)&v18);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
    ++v10;
  }
  STRU::SetLen(a3, v8);
}

```

## disassembly

```asm
0x1800109c0  mov     [rsp-38h+arg_0], rbx
0x1800109c5  mov     [rsp-38h+arg_8], rdx
0x1800109ca  push    rbp
0x1800109cb  push    rsi
0x1800109cc  push    rdi
0x1800109cd  push    r12
0x1800109cf  push    r13
0x1800109d1  push    r14
0x1800109d3  push    r15
0x1800109d5  mov     rbp, rsp
0x1800109d8  sub     rsp, 80h
0x1800109df  mov     r14, r9
0x1800109e2  mov     rbx, r8
0x1800109e5  mov     r12, rcx
0x1800109e8  mov     r15d, [r8+10h]
0x1800109ec  mov     [rbp+arg_10], 0
0x1800109f3  mov     rax, [r9]
0x1800109f6  lea     rdx, [rbp+arg_10]
0x1800109fa  mov     rcx, r9
0x1800109fd  mov     rax, [rax+18h]
0x180010a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a06  test    eax, eax
0x180010a08  jns     short loc_180010A1E
0x180010a0a  mov     [rbp+pExceptionObject], eax
0x180010a0d  lea     rdx, _TI1J; pThrowInfo
0x180010a14  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010a18  call    _CxxThrowException_0
0x180010a1e  xor     edi, edi
0x180010a20  mov     r13b, [rbp+arg_20]
0x180010a24  mov     edx, r15d; unsigned int
0x180010a27  mov     rcx, rbx; this
0x180010a2a  cmp     edi, [rbp+arg_10]
0x180010a2d  jnb     loc_180010B3D
0x180010a33  call    ?SetLen@STRU@@QEAAJK@Z; STRU::SetLen(ulong)
0x180010a38  mov     [rbp+var_48], 0
0x180010a40  mov     rax, [r14]
0x180010a43  mov     ecx, 13h
0x180010a48  mov     word ptr [rbp+pvarg], cx
0x180010a4c  mov     dword ptr [rbp+pvarg+8], edi
0x180010a4f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180010a53  movaps  [rbp+var_20], xmm0
0x180010a57  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180010a5c  movsd   [rbp+var_10], xmm1
0x180010a61  lea     r8, [rbp+var_48]
0x180010a65  lea     rdx, [rbp+var_20]
0x180010a69  mov     rcx, r14
0x180010a6c  mov     rax, [rax+20h]
0x180010a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a75  mov     esi, eax
0x180010a77  lea     rcx, [rbp+pvarg]; pvarg
0x180010a7b  call    cs:__imp_VariantClear
0x180010a81  test    esi, esi
0x180010a83  js      loc_180010B29
0x180010a89  mov     [rbp+var_50], 0
0x180010a91  mov     rcx, [rbp+var_48]
0x180010a95  mov     rax, [rcx]
0x180010a98  lea     rdx, [rbp+var_50]
0x180010a9c  mov     rax, [rax+40h]
0x180010aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa5  test    eax, eax
0x180010aa7  js      short loc_180010B15
0x180010aa9  mov     r8, [rbp+var_50]; unsigned __int16 *
0x180010aad  mov     rdx, r12; struct ConfigTreeBase *
0x180010ab0  mov     rcx, [rbp+arg_8]; this
0x180010ab4  call    ?FindOrCreateSectionGroupChildWithName@SectionGroupNode@@QEAAPEAV1@PEAVConfigTreeBase@@PEBG@Z; SectionGroupNode::FindOrCreateSectionGroupChildWithName(ConfigTreeBase *,ushort const *)
0x180010ab9  mov     rsi, rax
0x180010abc  xor     r8d, r8d; unsigned int
0x180010abf  mov     rdx, [rbp+var_50]; unsigned __int16 *
0x180010ac3  mov     rcx, rbx; this
0x180010ac6  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180010acb  test    eax, eax
0x180010acd  js      short loc_180010B01
0x180010acf  mov     [rsp+80h+var_60], r13b; pExceptionObject
0x180010ad4  mov     r9, [rbp+var_48]; struct IAppHostSectionGroup *
0x180010ad8  mov     r8, rbx; struct STRU *
0x180010adb  mov     rdx, rsi; struct SectionGroupNode *
0x180010ade  mov     rcx, r12; this
0x180010ae1  call    ?InitializeSectionGroupNodeChildren@MergedConfigTree@@AEAAXPEAVSectionGroupNode@@AEAVSTRU@@PEAUIAppHostSectionGroup@@_N@Z; MergedConfigTree::InitializeSectionGroupNodeChildren(SectionGroupNode *,STRU &,IAppHostSectionGroup *,bool)
0x180010ae6  nop
0x180010ae7  lea     rcx, [rbp+var_50]; this
0x180010aeb  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x180010af0  nop
0x180010af1  lea     rcx, [rbp+var_48]
0x180010af5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010afa  inc     edi
0x180010afc  jmp     loc_180010A24
0x180010b01  mov     [rbp+pExceptionObject], eax
0x180010b04  lea     rdx, _TI1J; pThrowInfo
0x180010b0b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010b0f  call    _CxxThrowException_0
0x180010b15  mov     [rbp+pExceptionObject], eax
0x180010b18  lea     rdx, _TI1J; pThrowInfo
0x180010b1f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010b23  call    _CxxThrowException_0
0x180010b29  mov     [rbp+pExceptionObject], esi
0x180010b2c  lea     rdx, _TI1J; pThrowInfo
0x180010b33  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010b37  call    _CxxThrowException_0
0x180010b3d  call    ?SetLen@STRU@@QEAAJK@Z; STRU::SetLen(ulong)
0x180010b42  mov     rbx, [rsp+80h+arg_0]
0x180010b4a  add     rsp, 80h
0x180010b51  pop     r15
0x180010b53  pop     r14
0x180010b55  pop     r13
0x180010b57  pop     r12
0x180010b59  pop     rdi
0x180010b5a  pop     rsi
0x180010b5b  pop     rbp
0x180010b5c  retn
```
