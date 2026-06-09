# RfbShellFolderBase::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180014b80`
- end: `0x180014d7e`
- name: `?BindToObject@RfbShellFolderBase@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `510`
- prototype: `__int64 __fastcall(LPCITEMIDLIST *this, const ITEMIDLIST *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014b80`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ccb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d44`
- `SHELL32!__imp_ILCloneFirst` at `0x180014c13`
- `SHELL32!__imp_ILCloneFirst` at `0x180014c13`
- `SHELL32!__imp_ILCombine` at `0x180014c28`
- `SHELL32!__imp_ILCombine` at `0x180014c28`
- `SHELL32!__imp_ILGetNext` at `0x180014c60`
- `SHELL32!__imp_ILGetNext` at `0x180014c60`

## pseudocode

```c
__int64 __fastcall RfbShellFolderBase::BindToObject(
        LPCITEMIDLIST *this,
        const ITEMIDLIST *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **a5)
{
  void **v9; // r12
  ITEMIDLIST *v10; // rdi
  LPITEMIDLIST v11; // rax
  LPITEMIDLIST v12; // rsi
  const char *v13; // r9
  LPITEMIDLIST v14; // rax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 result; // rax
  unsigned int v18; // ebx
  _QWORD *v19; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  _QWORD *v21; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v9 = a5;
  if ( !a5 )
    return 2147942487LL;
  if ( (*(_QWORD *)&IID_IShellFolder.Data1 != *(_QWORD *)&a4->Data1
     || *(_QWORD *)IID_IShellFolder.Data4 != *(_QWORD *)a4->Data4)
    && (*(_QWORD *)&IID_IShellFolder2.Data1 != *(_QWORD *)&a4->Data1
     || *(_QWORD *)IID_IShellFolder2.Data4 != *(_QWORD *)a4->Data4)
    && (*(_QWORD *)&IID_IResolveShellLink.Data1 != *(_QWORD *)&a4->Data1
     || *(_QWORD *)IID_IResolveShellLink.Data4 != *(_QWORD *)a4->Data4) )
  {
    return 2147500033LL;
  }
  v10 = ILCloneFirst(a2);
  v11 = ILCombine(this[6], v10);
  try
  {
    v12 = v11;
    (*(void (__fastcall **)(char *, _QWORD **, LPITEMIDLIST))((char *)&(*(this - 1))[21].mkid.cb + 1))(
      (char *)this - 8,
      &v21,
      v11);
    if ( v21 )
    {
      v14 = ILGetNext(a2);
      if ( v14 && v14->mkid.cb )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD *, LPITEMIDLIST, struct IBindCtx *, const struct _GUID *, void **))(*v21 + 40LL))(
                v21,
                v14,
                a3,
                a4,
                v9);
        v16 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v16 + 16LL))(v16, *v16);
        }
        if ( v12 )
          CoTaskMemFree(v12);
        if ( v10 )
          CoTaskMemFree(v10);
        result = v15;
      }
      else
      {
        v18 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v21)(v21, a4, v9);
        v19 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v19 + 16LL))(v19, *v19);
        }
        if ( v12 )
          CoTaskMemFree(v12);
        if ( v10 )
          CoTaskMemFree(v10);
        result = v18;
      }
    }
    else
    {
      if ( v12 )
        CoTaskMemFree(v12);
      if ( v10 )
        CoTaskMemFree(v10);
      result = 1;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1EA,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180014b80  mov     [rsp+arg_0], rbx
0x180014b85  mov     [rsp+arg_10], rsi
0x180014b8a  push    rdi
0x180014b8b  push    r12
0x180014b8d  push    r13
0x180014b8f  push    r14
0x180014b91  push    r15
0x180014b93  sub     rsp, 40h
0x180014b97  mov     r14, r9
0x180014b9a  mov     r13, r8
0x180014b9d  mov     r15, rdx
0x180014ba0  mov     rbx, rcx
0x180014ba3  test    rdx, rdx
0x180014ba6  jz      loc_180014D5E
0x180014bac  mov     r12, [rsp+68h+arg_20]
0x180014bb4  test    r12, r12
0x180014bb7  jz      loc_180014D5E
0x180014bbd  mov     rax, qword ptr cs:IID_IShellFolder.Data1
0x180014bc4  cmp     rax, [r9]
0x180014bc7  jnz     short loc_180014BD6
0x180014bc9  mov     rax, qword ptr cs:IID_IShellFolder.Data4
0x180014bd0  cmp     rax, [r9+8]
0x180014bd4  jz      short loc_180014C10
0x180014bd6  mov     rax, qword ptr cs:IID_IShellFolder2.Data1
0x180014bdd  cmp     rax, [r9]
0x180014be0  jnz     short loc_180014BEF
0x180014be2  mov     rax, qword ptr cs:IID_IShellFolder2.Data4
0x180014be9  cmp     rax, [r9+8]
0x180014bed  jz      short loc_180014C10
0x180014bef  mov     rax, qword ptr cs:IID_IResolveShellLink.Data1
0x180014bf6  cmp     rax, [r9]
0x180014bf9  jnz     loc_180014D57
0x180014bff  mov     rax, qword ptr cs:IID_IResolveShellLink.Data4
0x180014c06  cmp     rax, [r9+8]
0x180014c0a  jnz     loc_180014D57
0x180014c10  mov     rcx, r15; pidl
0x180014c13  call    cs:__imp_ILCloneFirst
0x180014c19  mov     rdi, rax
0x180014c1c  mov     [rsp+68h+var_38], rax
0x180014c21  mov     rdx, rax; pidl2
0x180014c24  mov     rcx, [rbx+30h]; pidl1
0x180014c28  call    cs:__imp_ILCombine
0x180014c2e  mov     rsi, rax
0x180014c31  mov     [rsp+68h+var_30], rax
0x180014c36  mov     rdx, [rbx-8]
0x180014c3a  mov     rax, [rdx+40h]
0x180014c3e  mov     r8, rsi
0x180014c41  lea     rdx, [rsp+68h+arg_8]
0x180014c46  lea     rcx, [rbx-8]
0x180014c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c4f  nop
0x180014c50  xor     ebx, ebx
0x180014c52  cmp     [rsp+68h+arg_8], rbx
0x180014c57  jz      loc_180014D2D
0x180014c5d  mov     rcx, r15; pidl
0x180014c60  call    cs:__imp_ILGetNext
0x180014c66  mov     r10, rax
0x180014c69  xor     r15d, r15d
0x180014c6c  test    rax, rax
0x180014c6f  jz      short loc_180014CD8
0x180014c71  cmp     [rax], r15w
0x180014c75  jbe     short loc_180014CD8
0x180014c77  mov     rcx, [rsp+68h+arg_8]
0x180014c7c  mov     rdx, [rcx]
0x180014c7f  mov     rax, [rdx+28h]
0x180014c83  mov     [rsp+68h+var_48], r12
0x180014c88  mov     r9, r14
0x180014c8b  mov     r8, r13
0x180014c8e  mov     rdx, r10
0x180014c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c96  mov     ebx, eax
0x180014c98  mov     rcx, [rsp+68h+arg_8]
0x180014c9d  test    rcx, rcx
0x180014ca0  jz      short loc_180014CB4
0x180014ca2  mov     [rsp+68h+arg_8], r15
0x180014ca7  mov     rdx, [rcx]
0x180014caa  mov     rax, [rdx+10h]
0x180014cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cb3  nop
0x180014cb4  test    rsi, rsi
0x180014cb7  jz      short loc_180014CC3
0x180014cb9  mov     rcx, rsi; pv
0x180014cbc  call    cs:__imp_CoTaskMemFree
0x180014cc2  nop
0x180014cc3  test    rdi, rdi
0x180014cc6  jz      short loc_180014CD1
0x180014cc8  mov     rcx, rdi; pv
0x180014ccb  call    cs:__imp_CoTaskMemFree
0x180014cd1  mov     eax, ebx
0x180014cd3  jmp     loc_180014D63
0x180014cd8  mov     rcx, [rsp+68h+arg_8]
0x180014cdd  mov     rax, [rcx]
0x180014ce0  mov     r8, r12
0x180014ce3  mov     rdx, r14
0x180014ce6  mov     rax, [rax]
0x180014ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cee  mov     ebx, eax
0x180014cf0  mov     rcx, [rsp+68h+arg_8]
0x180014cf5  test    rcx, rcx
0x180014cf8  jz      short loc_180014D0C
0x180014cfa  mov     [rsp+68h+arg_8], r15
0x180014cff  mov     rdx, [rcx]
0x180014d02  mov     rax, [rdx+10h]
0x180014d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d0b  nop
0x180014d0c  test    rsi, rsi
0x180014d0f  jz      short loc_180014D1B
0x180014d11  mov     rcx, rsi; pv
0x180014d14  call    cs:__imp_CoTaskMemFree
0x180014d1a  nop
0x180014d1b  test    rdi, rdi
0x180014d1e  jz      short loc_180014D29
0x180014d20  mov     rcx, rdi; pv
0x180014d23  call    cs:__imp_CoTaskMemFree
0x180014d29  mov     eax, ebx
0x180014d2b  jmp     short loc_180014D63
0x180014d2d  test    rsi, rsi
0x180014d30  jz      short loc_180014D3C
0x180014d32  mov     rcx, rsi; pv
0x180014d35  call    cs:__imp_CoTaskMemFree
0x180014d3b  nop
0x180014d3c  test    rdi, rdi
0x180014d3f  jz      short loc_180014D4A
0x180014d41  mov     rcx, rdi; pv
0x180014d44  call    cs:__imp_CoTaskMemFree
0x180014d4a  mov     eax, 1
0x180014d4f  jmp     short loc_180014D63
0x180014d51  mov     eax, dword ptr [rsp+68h+arg_8]
0x180014d55  jmp     short loc_180014D63
0x180014d57  mov     eax, 80004001h
0x180014d5c  jmp     short loc_180014D63
0x180014d5e  mov     eax, 80070057h
0x180014d63  lea     r11, [rsp+68h+var_28]
0x180014d68  mov     rbx, [r11+30h]
0x180014d6c  mov     rsi, [r11+40h]
0x180014d70  mov     rsp, r11
0x180014d73  pop     r15
0x180014d75  pop     r14
0x180014d77  pop     r13
0x180014d79  pop     r12
0x180014d7b  pop     rdi
0x180014d7c  retn
```
