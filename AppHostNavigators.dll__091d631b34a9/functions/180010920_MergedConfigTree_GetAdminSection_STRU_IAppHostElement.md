# MergedConfigTree::GetAdminSection(STRU &,IAppHostElement * *)

- ea: `0x180010920`
- end: `0x1800109b7`
- name: `?GetAdminSection@MergedConfigTree@@UEAAXAEAVSTRU@@PEAPEAUIAppHostElement@@@Z`
- size: `151`
- prototype: `void __fastcall(MergedConfigTree *__hidden this, struct STRU *, struct IAppHostElement **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180010920`
- `0x180012e40`
- `0x180012ea8`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MergedConfigTree::GetAdminSection(MergedConfigTree *this, struct STRU *a2, struct IAppHostElement **a3)
{
  int v5; // eax
  int v6; // eax
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF
  __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  v5 = ScopedBSTR::CopyStringCCH((ScopedBSTR *)&v8, *((OLECHAR **)a2 + 1), *((_DWORD *)a2 + 4));
  if ( v5 < 0 )
  {
    pExceptionObject = v5;
    throw (long *)&pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, struct IAppHostElement **))(**(_QWORD **)(*((_QWORD *)this + 3) + 16LL)
                                                                                     + 24LL))(
         *(_QWORD *)(*((_QWORD *)this + 3) + 16LL),
         v8,
         *((_QWORD *)this + 17),
         a3);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  ScopedBSTR::Reset((ScopedBSTR *)&v8);
}

```

## disassembly

```asm
0x180010920  mov     [rsp+arg_0], rbx
0x180010925  push    rdi
0x180010926  sub     rsp, 30h
0x18001092a  mov     rdi, r8
0x18001092d  mov     rbx, rcx
0x180010930  mov     [rsp+38h+arg_18], 0
0x180010939  mov     r8d, [rdx+10h]; ui
0x18001093d  mov     rdx, [rdx+8]; strIn
0x180010941  lea     rcx, [rsp+38h+arg_18]; this
0x180010946  call    ?CopyStringCCH@ScopedBSTR@@QEAAJPEBGI@Z; ScopedBSTR::CopyStringCCH(ushort const *,uint)
0x18001094b  test    eax, eax
0x18001094d  jns     short loc_180010965
0x18001094f  mov     [rsp+38h+pExceptionObject], eax
0x180010953  lea     rdx, _TI1J; pThrowInfo
0x18001095a  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001095f  call    _CxxThrowException_0
0x180010965  mov     rax, [rbx+18h]
0x180010969  mov     rcx, [rax+10h]
0x18001096d  mov     rax, [rcx]
0x180010970  mov     r9, rdi
0x180010973  mov     r8, [rbx+88h]
0x18001097a  mov     rdx, [rsp+38h+arg_18]
0x18001097f  mov     rax, [rax+18h]
0x180010983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010988  test    eax, eax
0x18001098a  jns     short loc_1800109A2
0x18001098c  mov     [rsp+38h+pExceptionObject], eax
0x180010990  lea     rdx, _TI1J; pThrowInfo
0x180010997  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18001099c  call    _CxxThrowException_0
0x1800109a2  lea     rcx, [rsp+38h+arg_18]; this
0x1800109a7  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x1800109ac  mov     rbx, [rsp+38h+arg_0]
0x1800109b1  add     rsp, 30h
0x1800109b5  pop     rdi
0x1800109b6  retn
```
