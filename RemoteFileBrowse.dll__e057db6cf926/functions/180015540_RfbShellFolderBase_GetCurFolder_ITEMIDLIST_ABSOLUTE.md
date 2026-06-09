# RfbShellFolderBase::GetCurFolder(_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180015540`
- end: `0x180015586`
- name: `?GetCurFolder@RfbShellFolderBase@@UEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(LPCITEMIDLIST *this, LPITEMIDLIST *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015540`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180015562`
- `SHELL32!__imp_ILCombine` at `0x180015562`

## pseudocode

```c
__int64 __fastcall RfbShellFolderBase::GetCurFolder(LPCITEMIDLIST *this, LPITEMIDLIST *a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( *((_BYTE *)this + 32) )
      *a2 = ILCombine(this[7], 0);
    else
      return 1;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x180015540  mov     [rsp+arg_0], rbx
0x180015545  push    rdi
0x180015546  sub     rsp, 20h
0x18001554a  xor     ebx, ebx
0x18001554c  mov     rdi, rdx
0x18001554f  test    rdx, rdx
0x180015552  jz      short loc_180015574
0x180015554  mov     [rdx], rbx
0x180015557  cmp     [rcx+20h], bl
0x18001555a  jz      short loc_18001556D
0x18001555c  mov     rcx, [rcx+38h]; pidl1
0x180015560  xor     edx, edx; pidl2
0x180015562  call    cs:__imp_ILCombine
0x180015568  mov     [rdi], rax
0x18001556b  jmp     short loc_180015579
0x18001556d  mov     ebx, 1
0x180015572  jmp     short loc_180015579
0x180015574  mov     ebx, 80070057h
0x180015579  mov     eax, ebx
0x18001557b  mov     rbx, [rsp+28h+arg_0]
0x180015580  add     rsp, 20h
0x180015584  pop     rdi
0x180015585  retn
```
