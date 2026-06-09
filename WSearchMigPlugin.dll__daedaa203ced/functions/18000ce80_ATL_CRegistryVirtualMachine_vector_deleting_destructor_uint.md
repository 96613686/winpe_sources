# ATL::CRegistryVirtualMachine::`vector deleting destructor'(uint)

- ea: `0x18000ce80`
- end: `0x18000cef4`
- name: `??_ECRegistryVirtualMachine@ATL@@UEAAPEAXI@Z`
- size: `116`
- prototype: `ATL::CRegistryVirtualMachine *__fastcall(ATL::CRegistryVirtualMachine *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180002b9c`
- `0x18000ce80`
- `0x18000d8f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cea7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cebe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cea7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cebe`

## pseudocode

```c
ATL::CRegistryVirtualMachine *__fastcall ATL::CRegistryVirtualMachine::`vector deleting destructor'(
        ATL::CRegistryVirtualMachine *this,
        char a2)
{
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &ATL::CRegistryVirtualMachine::`vftable';
  ATL::CRegistryVirtualMachine::ClearReplacements(this);
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ce80  mov     [rsp+arg_0], rbx
0x18000ce85  push    rdi
0x18000ce86  sub     rsp, 20h
0x18000ce8a  lea     rax, ??_7CRegistryVirtualMachine@ATL@@6B@; const ATL::CRegistryVirtualMachine::`vftable'
0x18000ce91  mov     edi, edx
0x18000ce93  mov     [rcx], rax
0x18000ce96  mov     rbx, rcx
0x18000ce99  call    ?ClearReplacements@CRegistryVirtualMachine@ATL@@UEAAJXZ; ATL::CRegistryVirtualMachine::ClearReplacements(void)
0x18000ce9e  mov     rcx, [rbx+8]; Block
0x18000cea2  test    rcx, rcx
0x18000cea5  jz      short loc_18000CEB5
0x18000cea7  call    cs:__imp_free
0x18000cead  mov     qword ptr [rbx+8], 0
0x18000ceb5  mov     rcx, [rbx+10h]; Block
0x18000ceb9  test    rcx, rcx
0x18000cebc  jz      short loc_18000CECC
0x18000cebe  call    cs:__imp_free
0x18000cec4  mov     qword ptr [rbx+10h], 0
0x18000cecc  mov     dword ptr [rbx+18h], 0
0x18000ced3  test    dil, 1
0x18000ced7  jz      short loc_18000CEE6
0x18000ced9  mov     edx, 28h ; '('
0x18000cede  mov     rcx, rbx; Block
0x18000cee1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cee6  mov     rax, rbx
0x18000cee9  mov     rbx, [rsp+28h+arg_0]
0x18000ceee  add     rsp, 20h
0x18000cef2  pop     rdi
0x18000cef3  retn
```
