# RfbShellFolderBase::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180015d70`
- end: `0x180015dbc`
- name: `?Initialize@RfbShellFolderBase@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(RfbShellFolderBase *this, const ITEMIDLIST *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005e70`
- `0x180007d40`
- `0x180016730`

## callees

- `0x180015d70`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d94`
- `SHELL32!__imp_ILCombine` at `0x180015d81`
- `SHELL32!__imp_ILCombine` at `0x180015d81`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RfbShellFolderBase::Initialize(RfbShellFolderBase *this, const ITEMIDLIST *a2)
{
  LPITEMIDLIST v3; // rax
  void *v4; // rcx
  const char *v5; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = ILCombine(a2, 0);
  v4 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v3;
  if ( v4 )
    CoTaskMemFree(v4);
  *((_BYTE *)this + 32) = 1;
  try
  {
    (*(void (**)(void))(*(_QWORD *)this + 56LL))();
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x79,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180015d70  push    rbx
0x180015d72  sub     rsp, 20h
0x180015d76  mov     rax, rdx
0x180015d79  mov     rbx, rcx
0x180015d7c  xor     edx, edx; pidl2
0x180015d7e  mov     rcx, rax; pidl1
0x180015d81  call    cs:__imp_ILCombine
0x180015d87  mov     rcx, [rbx+38h]; pv
0x180015d8b  mov     [rbx+38h], rax
0x180015d8f  test    rcx, rcx
0x180015d92  jz      short loc_180015D9A
0x180015d94  call    cs:__imp_CoTaskMemFree
0x180015d9a  mov     byte ptr [rbx+20h], 1
0x180015d9e  mov     rax, [rbx]
0x180015da1  mov     rcx, rbx
0x180015da4  mov     rax, [rax+38h]
0x180015da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dad  xor     eax, eax
0x180015daf  jmp     short loc_180015DB5
0x180015db1  mov     eax, [rsp+28h+arg_0]
0x180015db5  add     rsp, 20h
0x180015db9  pop     rbx
0x180015dba  retn
```
