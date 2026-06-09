# _get_image_app_type

- ea: `0x140001634`
- end: `0x14000167a`
- name: `_get_image_app_type`
- size: `70`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1400010b0`

## callees

- `0x1400015dc`
- `0x140001634`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000163e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000163e`

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
0x140001634  push    rbx
0x140001636  sub     rsp, 20h
0x14000163a  mov     ebx, ecx
0x14000163c  xor     ecx, ecx; lpModuleName
0x14000163e  call    cs:__imp_GetModuleHandleW
0x140001644  test    rax, rax
0x140001647  jz      short loc_140001672
0x140001649  mov     rcx, rax
0x14000164c  call    RtlpImageNtHeader
0x140001651  test    rax, rax
0x140001654  jz      short loc_140001672
0x140001656  mov     ecx, 2
0x14000165b  cmp     [rax+5Ch], cx
0x14000165f  jnz     short loc_140001665
0x140001661  mov     eax, ecx
0x140001663  jmp     short loc_140001674
0x140001665  cmp     word ptr [rax+5Ch], 3
0x14000166a  mov     ecx, 1
0x14000166f  cmovz   ebx, ecx
0x140001672  mov     eax, ebx
0x140001674  add     rsp, 20h
0x140001678  pop     rbx
0x140001679  retn
```
