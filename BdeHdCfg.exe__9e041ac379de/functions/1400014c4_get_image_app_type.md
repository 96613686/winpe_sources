# _get_image_app_type

- ea: `0x1400014c4`
- end: `0x14000150a`
- name: `_get_image_app_type`
- size: `70`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001020`

## callees

- `0x14000146c`
- `0x1400014c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400014ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400014ce`

## pseudocode

```c
__int64 __fastcall get_image_app_type(unsigned int a1)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rax

  ModuleHandleW = GetModuleHandleW(0);
  if ( ModuleHandleW )
  {
    v3 = RtlpImageNtHeader(ModuleHandleW);
    if ( v3 )
    {
      if ( *(_WORD *)(v3 + 92) == 2 )
        return 2;
      if ( *(_WORD *)(v3 + 92) == 3 )
        return 1;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400014c4  push    rbx
0x1400014c6  sub     rsp, 20h
0x1400014ca  mov     ebx, ecx
0x1400014cc  xor     ecx, ecx; lpModuleName
0x1400014ce  call    cs:__imp_GetModuleHandleW
0x1400014d4  test    rax, rax
0x1400014d7  jz      short loc_140001502
0x1400014d9  mov     rcx, rax
0x1400014dc  call    RtlpImageNtHeader
0x1400014e1  test    rax, rax
0x1400014e4  jz      short loc_140001502
0x1400014e6  mov     ecx, 2
0x1400014eb  cmp     [rax+5Ch], cx
0x1400014ef  jnz     short loc_1400014F5
0x1400014f1  mov     eax, ecx
0x1400014f3  jmp     short loc_140001504
0x1400014f5  cmp     word ptr [rax+5Ch], 3
0x1400014fa  mov     ecx, 1
0x1400014ff  cmovz   ebx, ecx
0x140001502  mov     eax, ebx
0x140001504  add     rsp, 20h
0x140001508  pop     rbx
0x140001509  retn
```
