# MergedConfigTree::InitializeSectionGroupNodeChildren(SectionGroupNode *,STRU &,IAppHostSectionGroup *,bool)

- ea: `0x180010d64`
- end: `0x180010e16`
- name: `?InitializeSectionGroupNodeChildren@MergedConfigTree@@AEAAXPEAVSectionGroupNode@@AEAVSTRU@@PEAUIAppHostSectionGroup@@_N@Z`
- size: `178`
- prototype: `void __fastcall(MergedConfigTree *__hidden this, struct SectionGroupNode *, struct STRU *, struct IAppHostSectionGroup *, bool pExceptionObject)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800109c0`
- `0x180010e40`

## callees

- `0x180007aac`
- `0x18000ab38`
- `0x18000d894`
- `0x1800109c0`
- `0x180010b64`
- `0x180010d64`
- `0x180012f3c`

## pseudocode

```c
void __fastcall MergedConfigTree::InitializeSectionGroupNodeChildren(
        MergedConfigTree *this,
        struct IUnknown **a2,
        struct STRU *a3,
        struct IUnknown *a4,
        int pExceptionObject)
{
  bool v5; // r14
  unsigned int v10; // esi
  int v11; // eax

  v5 = pExceptionObject;
  if ( (_BYTE)pExceptionObject && a2[11] != a4 )
    ATL::AtlComPtrAssign(a2 + 11, a4);
  v10 = *((_DWORD *)a3 + 4);
  if ( v10 )
  {
    v11 = STRU::Append(a3, L"/", 0, (unsigned int)a4);
    if ( v11 < 0 )
    {
      pExceptionObject = v11;
      throw (long *)&pExceptionObject;
    }
  }
  MergedConfigTree::InitializeSectionGroupNodeChildSectionGroups(
    this,
    (struct SectionGroupNode *)a2,
    a3,
    (struct IAppHostSectionGroup *)a4,
    v5);
  MergedConfigTree::InitializeSectionGroupNodeChildSections(
    this,
    (struct SectionGroupNode *)a2,
    a3,
    (struct IAppHostSectionGroup *)a4,
    v5);
  STRU::SetLen(a3, v10);
}

```

## disassembly

```asm
0x180010d64  push    rbx
0x180010d66  push    rbp
0x180010d67  push    rsi
0x180010d68  push    rdi
0x180010d69  push    r14
0x180010d6b  push    r15
0x180010d6d  sub     rsp, 38h
0x180010d71  mov     r14b, byte ptr [rsp+68h+pExceptionObject]
0x180010d79  mov     rdi, r9
0x180010d7c  mov     rbx, r8
0x180010d7f  mov     rbp, rdx
0x180010d82  mov     r15, rcx
0x180010d85  test    r14b, r14b
0x180010d88  jz      short loc_180010D9B
0x180010d8a  lea     rcx, [rdx+58h]; struct IUnknown **
0x180010d8e  cmp     [rcx], r9
0x180010d91  jz      short loc_180010D9B
0x180010d93  mov     rdx, r9; struct IUnknown *
0x180010d96  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180010d9b  mov     esi, [rbx+10h]
0x180010d9e  test    esi, esi
0x180010da0  jz      short loc_180010DD4
0x180010da2  xor     r8d, r8d; unsigned int
0x180010da5  lea     rdx, asc_180018280; "/"
0x180010dac  mov     rcx, rbx; this
0x180010daf  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180010db4  test    eax, eax
0x180010db6  jns     short loc_180010DD4
0x180010db8  lea     rdx, _TI1J; pThrowInfo
0x180010dbf  mov     [rsp+68h+pExceptionObject], eax
0x180010dc6  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180010dce  call    _CxxThrowException_0
0x180010dd4  mov     r9, rdi; struct IAppHostSectionGroup *
0x180010dd7  mov     [rsp+68h+var_48], r14b; bool
0x180010ddc  mov     r8, rbx; struct STRU *
0x180010ddf  mov     rdx, rbp; struct SectionGroupNode *
0x180010de2  mov     rcx, r15; this
0x180010de5  call    ?InitializeSectionGroupNodeChildSectionGroups@MergedConfigTree@@AEAAXPEAVSectionGroupNode@@AEAVSTRU@@PEAUIAppHostSectionGroup@@_N@Z; MergedConfigTree::InitializeSectionGroupNodeChildSectionGroups(SectionGroupNode *,STRU &,IAppHostSectionGroup *,bool)
0x180010dea  mov     r9, rdi; struct IAppHostSectionGroup *
0x180010ded  mov     [rsp+68h+var_48], r14b; bool
0x180010df2  mov     r8, rbx; struct STRU *
0x180010df5  mov     rdx, rbp; struct SectionGroupNode *
0x180010df8  mov     rcx, r15; this
0x180010dfb  call    ?InitializeSectionGroupNodeChildSections@MergedConfigTree@@AEAAXPEAVSectionGroupNode@@AEAVSTRU@@PEAUIAppHostSectionGroup@@_N@Z; MergedConfigTree::InitializeSectionGroupNodeChildSections(SectionGroupNode *,STRU &,IAppHostSectionGroup *,bool)
0x180010e00  mov     edx, esi; unsigned int
0x180010e02  mov     rcx, rbx; this
0x180010e05  add     rsp, 38h
0x180010e09  pop     r15
0x180010e0b  pop     r14
0x180010e0d  pop     rdi
0x180010e0e  pop     rsi
0x180010e0f  pop     rbp
0x180010e10  pop     rbx
0x180010e11  jmp     ?SetLen@STRU@@QEAAJK@Z; STRU::SetLen(ulong)
```
