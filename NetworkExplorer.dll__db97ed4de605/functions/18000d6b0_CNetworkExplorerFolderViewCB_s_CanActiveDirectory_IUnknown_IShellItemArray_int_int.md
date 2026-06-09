# CNetworkExplorerFolderViewCB::s_CanActiveDirectory(IUnknown *,IShellItemArray *,int,int *)

- ea: `0x18000d6b0`
- end: `0x18000d710`
- name: `?s_CanActiveDirectory@CNetworkExplorerFolderViewCB@@SAJPEAUIUnknown@@PEAUIShellItemArray@@HPEAH@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItemArray *, int, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d6b0`
- `0x180010010`

## import_xrefs

- `SHLWAPI!__imp_IsOS` at `0x18000d6ec`
- `SHLWAPI!__imp_IsOS` at `0x18000d6ec`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::s_CanActiveDirectory(
        struct IUnknown *a1,
        struct IShellItemArray *a2,
        __int64 a3,
        int *a4)
{
  struct IUnknownVtbl *lpVtbl; // rcx
  int v6; // ebx
  int v8; // [rsp+30h] [rbp+8h] BYREF

  *a4 = 2;
  lpVtbl = a1[8].lpVtbl;
  v8 = 0;
  v6 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, int *))lpVtbl->QueryInterface + 11))(lpVtbl, &v8);
  if ( v6 >= 0 && IsOS(0x1Cu) && v8 )
    *a4 = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d6b0  mov     [rsp+arg_8], rbx
0x18000d6b5  push    rdi
0x18000d6b6  sub     rsp, 20h
0x18000d6ba  mov     dword ptr [r9], 2
0x18000d6c1  lea     rdx, [rsp+28h+arg_0]
0x18000d6c6  mov     rcx, [rcx+40h]
0x18000d6ca  mov     rdi, r9
0x18000d6cd  mov     [rsp+28h+arg_0], 0
0x18000d6d5  mov     rax, [rcx]
0x18000d6d8  mov     rax, [rax+58h]
0x18000d6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6e1  mov     ebx, eax
0x18000d6e3  test    eax, eax
0x18000d6e5  js      short loc_18000D703
0x18000d6e7  mov     ecx, 1Ch; dwOS
0x18000d6ec  call    cs:__imp_IsOS
0x18000d6f2  test    eax, eax
0x18000d6f4  jz      short loc_18000D703
0x18000d6f6  cmp     [rsp+28h+arg_0], 0
0x18000d6fb  jz      short loc_18000D703
0x18000d6fd  mov     dword ptr [rdi], 0
0x18000d703  mov     eax, ebx
0x18000d705  mov     rbx, [rsp+28h+arg_8]
0x18000d70a  add     rsp, 20h
0x18000d70e  pop     rdi
0x18000d70f  retn
```
