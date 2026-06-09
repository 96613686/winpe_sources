# _GetConflictShellItem

- ea: `0x180048a40`
- end: `0x180048acc`
- name: `_GetConflictShellItem`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004822c`
- `0x18004833c`
- `0x1800484b8`

## callees

- `0x1800133b0`
- `0x1800134dc`
- `0x180048924`
- `0x180048a40`

## import_xrefs

- `SHELL32!SHCreateItemWithParent` at `0x180048aa2`
- `SHELL32!SHCreateItemWithParent` at `0x180048aa2`
- `SHELL32!__imp_ILFree` at `0x180048aaf`
- `SHELL32!__imp_ILFree` at `0x180048aaf`

## pseudocode

```c
__int64 __fastcall GetConflictShellItem(IShellFolder *a1, __int64 a2, const ITEMIDLIST *a3, void **a4)
{
  int v5; // edx
  int v6; // ecx
  int v7; // r9d
  HRESULT ConflictIDListAndParent; // ebx
  IShellFolder *psfParent; // [rsp+40h] [rbp+8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+50h] [rbp+18h] BYREF

  pidl = a3;
  psfParent = a1;
  *a4 = 0;
  ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&psfParent);
  pidl = 0;
  ConflictIDListAndParent = GetConflictIDListAndParent(v6, v5, (unsigned int)&pidl, v7, (__int64)&psfParent);
  if ( ConflictIDListAndParent >= 0 )
  {
    ConflictIDListAndParent = SHCreateItemWithParent(0, psfParent, pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a4);
    ILFree((LPITEMIDLIST)pidl);
  }
  ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&psfParent);
  return (unsigned int)ConflictIDListAndParent;
}

```

## disassembly

```asm
0x180048a40  mov     rax, rsp
0x180048a43  mov     [rax+10h], rbx
0x180048a47  mov     [rax+18h], r8
0x180048a4b  mov     [rax+8], rcx
0x180048a4f  push    rdi
0x180048a50  sub     rsp, 30h
0x180048a54  lea     rcx, [rax+8]; void *
0x180048a58  mov     qword ptr [r9], 0
0x180048a5f  mov     rdi, r9
0x180048a62  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180048a67  lea     rax, [rsp+38h+psfParent]
0x180048a6c  mov     [rsp+38h+pidl], 0
0x180048a75  lea     r8, [rsp+38h+pidl]
0x180048a7a  mov     [rsp+38h+ppvItem], rax
0x180048a7f  call    _GetConflictIDListAndParent
0x180048a84  mov     ebx, eax
0x180048a86  test    eax, eax
0x180048a88  js      short loc_180048AB5
0x180048a8a  mov     r8, [rsp+38h+pidl]; pidl
0x180048a8f  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180048a96  mov     rdx, [rsp+38h+psfParent]; psfParent
0x180048a9b  xor     ecx, ecx; pidlParent
0x180048a9d  mov     [rsp+38h+ppvItem], rdi; ppvItem
0x180048aa2  call    cs:__imp_SHCreateItemWithParent
0x180048aa8  mov     rcx, [rsp+38h+pidl]; pidl
0x180048aad  mov     ebx, eax
0x180048aaf  call    cs:__imp_ILFree
0x180048ab5  lea     rcx, [rsp+38h+psfParent]
0x180048aba  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180048abf  mov     eax, ebx
0x180048ac1  mov     rbx, [rsp+38h+arg_8]
0x180048ac6  add     rsp, 30h
0x180048aca  pop     rdi
0x180048acb  retn
```
