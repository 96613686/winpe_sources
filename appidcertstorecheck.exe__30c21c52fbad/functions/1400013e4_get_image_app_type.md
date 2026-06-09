# _get_image_app_type

- ea: `0x1400013e4`
- end: `0x14000142a`
- name: `_get_image_app_type`
- size: `70`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001010`

## callees

- `0x14000138c`
- `0x1400013e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400013ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400013ee`

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
0x1400013e4  push    rbx
0x1400013e6  sub     rsp, 20h
0x1400013ea  mov     ebx, ecx
0x1400013ec  xor     ecx, ecx; lpModuleName
0x1400013ee  call    cs:__imp_GetModuleHandleW
0x1400013f4  test    rax, rax
0x1400013f7  jz      short loc_140001422
0x1400013f9  mov     rcx, rax
0x1400013fc  call    RtlpImageNtHeader
0x140001401  test    rax, rax
0x140001404  jz      short loc_140001422
0x140001406  mov     ecx, 2
0x14000140b  cmp     [rax+5Ch], cx
0x14000140f  jnz     short loc_140001415
0x140001411  mov     eax, ecx
0x140001413  jmp     short loc_140001424
0x140001415  cmp     word ptr [rax+5Ch], 3
0x14000141a  mov     ecx, 1
0x14000141f  cmovz   ebx, ecx
0x140001422  mov     eax, ebx
0x140001424  add     rsp, 20h
0x140001428  pop     rbx
0x140001429  retn
```
