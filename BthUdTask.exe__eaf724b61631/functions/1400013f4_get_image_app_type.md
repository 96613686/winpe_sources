# _get_image_app_type

- ea: `0x1400013f4`
- end: `0x14000143a`
- name: `_get_image_app_type`
- size: `70`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001010`

## callees

- `0x14000139c`
- `0x1400013f4`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400013fe`
- `KERNEL32!GetModuleHandleW` at `0x1400013fe`

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
0x1400013f4  push    rbx
0x1400013f6  sub     rsp, 20h
0x1400013fa  mov     ebx, ecx
0x1400013fc  xor     ecx, ecx; lpModuleName
0x1400013fe  call    cs:__imp_GetModuleHandleW
0x140001404  test    rax, rax
0x140001407  jz      short loc_140001432
0x140001409  mov     rcx, rax
0x14000140c  call    RtlpImageNtHeader
0x140001411  test    rax, rax
0x140001414  jz      short loc_140001432
0x140001416  mov     ecx, 2
0x14000141b  cmp     [rax+5Ch], cx
0x14000141f  jnz     short loc_140001425
0x140001421  mov     eax, ecx
0x140001423  jmp     short loc_140001434
0x140001425  cmp     word ptr [rax+5Ch], 3
0x14000142a  mov     ecx, 1
0x14000142f  cmovz   ebx, ecx
0x140001432  mov     eax, ebx
0x140001434  add     rsp, 20h
0x140001438  pop     rbx
0x140001439  retn
```
