# _get_image_app_type

- ea: `0x1400014a4`
- end: `0x1400014ea`
- name: `_get_image_app_type`
- size: `70`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001010`

## callees

- `0x14000144c`
- `0x1400014a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400014ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400014ae`

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
0x1400014a4  push    rbx
0x1400014a6  sub     rsp, 20h
0x1400014aa  mov     ebx, ecx
0x1400014ac  xor     ecx, ecx; lpModuleName
0x1400014ae  call    cs:__imp_GetModuleHandleW
0x1400014b4  test    rax, rax
0x1400014b7  jz      short loc_1400014E2
0x1400014b9  mov     rcx, rax
0x1400014bc  call    RtlpImageNtHeader
0x1400014c1  test    rax, rax
0x1400014c4  jz      short loc_1400014E2
0x1400014c6  mov     ecx, 2
0x1400014cb  cmp     [rax+5Ch], cx
0x1400014cf  jnz     short loc_1400014D5
0x1400014d1  mov     eax, ecx
0x1400014d3  jmp     short loc_1400014E4
0x1400014d5  cmp     word ptr [rax+5Ch], 3
0x1400014da  mov     ecx, 1
0x1400014df  cmovz   ebx, ecx
0x1400014e2  mov     eax, ebx
0x1400014e4  add     rsp, 20h
0x1400014e8  pop     rbx
0x1400014e9  retn
```
