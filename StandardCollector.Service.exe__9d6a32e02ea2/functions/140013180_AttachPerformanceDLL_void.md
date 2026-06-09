# AttachPerformanceDLL(void)

- ea: `0x140013180`
- end: `0x1400131e4`
- name: `?AttachPerformanceDLL@@YAXXZ`
- size: `100`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400131f0`
- `0x140013238`

## callees

- `0x1400130c0`
- `0x140013180`

## import_xrefs

- `KERNEL32!FindAtomW` at `0x1400131a7`
- `KERNEL32!FindAtomW` at `0x1400131a7`
- `KERNEL32!GetModuleHandleW` at `0x1400131b9`
- `KERNEL32!GetModuleHandleW` at `0x1400131cb`
- `KERNEL32!GetModuleHandleW` at `0x1400131b9`
- `KERNEL32!GetModuleHandleW` at `0x1400131cb`

## pseudocode

```c
void AttachPerformanceDLL(void)
{
  HMODULE ModuleHandleW; // rax

  if ( !gfTriedToAttachPerformanceDll )
  {
    gfTriedToAttachPerformanceDll = 1;
    if ( !ghInstPerf )
    {
      if ( FindAtomW(lpString) )
      {
        ModuleHandleW = GetModuleHandleW(lpModuleName);
        if ( ModuleHandleW || (ModuleHandleW = GetModuleHandleW(off_140023020)) != 0 )
          Attach(ModuleHandleW);
      }
    }
  }
}

```

## disassembly

```asm
0x140013180  push    rbx
0x140013182  sub     rsp, 20h
0x140013186  xor     ebx, ebx
0x140013188  cmp     cs:?gfTriedToAttachPerformanceDll@@3_NA, bl; bool gfTriedToAttachPerformanceDll
0x14001318e  jnz     short loc_1400131DE
0x140013190  cmp     cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * ghInstPerf
0x140013197  mov     cs:?gfTriedToAttachPerformanceDll@@3_NA, 1; bool gfTriedToAttachPerformanceDll
0x14001319e  jnz     short loc_1400131DE
0x1400131a0  mov     rcx, cs:lpString; lpString
0x1400131a7  call    cs:__imp_FindAtomW
0x1400131ad  test    ax, ax
0x1400131b0  jz      short loc_1400131DE
0x1400131b2  mov     rcx, cs:lpModuleName; lpModuleName
0x1400131b9  call    cs:__imp_GetModuleHandleW
0x1400131bf  test    rax, rax
0x1400131c2  jnz     short loc_1400131D6
0x1400131c4  mov     rcx, cs:off_140023020; lpModuleName
0x1400131cb  call    cs:__imp_GetModuleHandleW
0x1400131d1  test    rax, rax
0x1400131d4  jz      short loc_1400131DE
0x1400131d6  mov     rcx, rax; hModule
0x1400131d9  call    Attach
0x1400131de  add     rsp, 20h
0x1400131e2  pop     rbx
0x1400131e3  retn
```
