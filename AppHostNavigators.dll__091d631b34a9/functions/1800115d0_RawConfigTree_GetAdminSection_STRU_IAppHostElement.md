# RawConfigTree::GetAdminSection(STRU &,IAppHostElement * *)

- ea: `0x1800115d0`
- end: `0x180011677`
- name: `?GetAdminSection@RawConfigTree@@UEAAXAEAVSTRU@@PEAPEAUIAppHostElement@@@Z`
- size: `167`
- prototype: `void __fastcall(RawConfigTree *__hidden this, struct STRU *, struct IAppHostElement **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800115d0`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800115fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800115fd`
- `OLEAUT32!__imp_VariantInit` at `0x1800115e9`
- `OLEAUT32!__imp_VariantInit` at `0x1800115e9`
- `OLEAUT32!__imp_VariantClear` at `0x180011668`
- `OLEAUT32!__imp_VariantClear` at `0x180011668`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RawConfigTree::GetAdminSection(RawConfigTree *this, const OLECHAR **a2, struct IAppHostElement **a3)
{
  __int64 v6; // rcx
  int v7; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG v9; // [rsp+40h] [rbp-28h] BYREF
  int pExceptionObject; // [rsp+98h] [rbp+30h] BYREF

  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a2[1]);
  if ( !pvarg.llVal )
  {
    pExceptionObject = 0;
    throw (long *)&pExceptionObject;
  }
  v6 = *((_QWORD *)this + 19);
  v9 = pvarg;
  v7 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v6 + 40LL))(v6, &v9, a3);
  if ( v7 < 0 )
  {
    pExceptionObject = v7;
    throw (long *)&pExceptionObject;
  }
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x1800115d0  push    rbp
0x1800115d2  push    rbx
0x1800115d3  push    rsi
0x1800115d4  push    rdi
0x1800115d5  mov     rbp, rsp
0x1800115d8  sub     rsp, 68h
0x1800115dc  mov     rdi, r8
0x1800115df  mov     rbx, rdx
0x1800115e2  mov     rsi, rcx
0x1800115e5  lea     rcx, [rbp+pvarg]; pvarg
0x1800115e9  call    cs:__imp_VariantInit
0x1800115ef  nop
0x1800115f0  mov     eax, 8
0x1800115f5  mov     word ptr [rbp+pvarg], ax
0x1800115f9  mov     rcx, [rbx+8]; psz
0x1800115fd  call    cs:__imp_SysAllocString
0x180011603  mov     qword ptr [rbp+pvarg+8], rax
0x180011607  test    rax, rax
0x18001160a  jnz     short loc_180011620
0x18001160c  mov     [rbp+pExceptionObject], eax
0x18001160f  lea     rdx, _TI1J; pThrowInfo
0x180011616  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001161a  call    _CxxThrowException_0
0x180011620  mov     rcx, [rsi+98h]
0x180011627  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001162b  movaps  [rbp+var_28], xmm0
0x18001162f  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180011634  movsd   [rbp+var_18], xmm1
0x180011639  mov     rax, [rcx]
0x18001163c  mov     r8, rdi
0x18001163f  lea     rdx, [rbp+var_28]
0x180011643  mov     rax, [rax+28h]
0x180011647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164c  test    eax, eax
0x18001164e  jns     short loc_180011664
0x180011650  mov     [rbp+pExceptionObject], eax
0x180011653  lea     rdx, _TI1J; pThrowInfo
0x18001165a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001165e  call    _CxxThrowException_0
0x180011664  lea     rcx, [rbp+pvarg]; pvarg
0x180011668  call    cs:__imp_VariantClear
0x18001166e  add     rsp, 68h
0x180011672  pop     rdi
0x180011673  pop     rsi
0x180011674  pop     rbx
0x180011675  pop     rbp
0x180011676  retn
```
