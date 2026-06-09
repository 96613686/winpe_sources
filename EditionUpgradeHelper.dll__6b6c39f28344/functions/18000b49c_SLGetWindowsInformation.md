# SLGetWindowsInformation

- ea: `0x18000b49c`
- end: `0x18001d30a`
- name: `SLGetWindowsInformation`
- size: `73326`
- prototype: `HRESULT __stdcall(PCWSTR pwszValueName, SLDATATYPE *peDataType, UINT *pcbValue, PBYTE *ppbValue)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180008a40`
- `0x1800093c0`

## callees

- `0x1800018e0`
- `0x1800024d4`
- `0x180006fac`
- `0x180008450`
- `0x180009a2c`
- `0x180009a58`
- `0x18000b35c`
- `0x18000b3a0`
- `0x18000b3cc`
- `0x18000b404`
- `0x18000b49c`
- `0x1800264e4`
- `0x1800265e0`
- `0x180026634`
- `0x18002664c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ba2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d02c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000e7af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000eda7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180012512`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180013643`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180015927`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001717a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001776e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001af65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001c136`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ba2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d02c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000e7af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000eda7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180012512`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180013643`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180015927`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001717a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001776e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001af65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001c136`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bad7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d097`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e86e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800125c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800136a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001597a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017247`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001782f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b037`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bad7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d097`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e86e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ee68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800125c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800136a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001597a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017247`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001782f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b037`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b55d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b970`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bb98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c04f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c407`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c425`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c4f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c94f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c98f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c9c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c9f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cadd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cbd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d247`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d2ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d302`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d35c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d42b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d44c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d518`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d567`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d5bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dccc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000decb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000def7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e1f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e212`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eedf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012634`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001277c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001281b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001285a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012abf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012fe7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013013`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001303f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013091`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800130d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013174`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001324a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013307`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001341d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001383d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800138a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800138fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013950`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800139d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800139fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013a28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013a49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013af1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013b6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014398`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800143c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800143f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001441f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014440`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001445c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800144a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800144d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800144ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014520`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001453c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800145e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001461b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014634`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001467c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001472c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014840`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ce7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015195`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800151c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800151f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001524f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001539d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800153fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001542b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001547a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015544`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001565b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001587b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015b82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015be4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ce2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015d10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015d5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015df7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800165d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001670c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016736`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016770`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001678d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800167bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800167e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001680f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001682c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016849`

## string_xrefs

- `0x18000cff2`: `ntdll.dll`
- `0x180013619`: `ntdll.dll`
- `0x1800158f3`: `ntdll.dll`
- `0x18001c122`: `ntdll.dll`

## pseudocode

```c

```

## disassembly

```asm
0x18000b49c  push    rbp
0x18000b49e  push    rbx
0x18000b49f  push    rsi
0x18000b4a0  push    rdi
0x18000b4a1  push    r12
0x18000b4a3  push    r13
0x18000b4a5  push    r14
0x18000b4a7  push    r15
0x18000b4a9  lea     rbp, [rsp-19C8h]
0x18000b4b1  mov     eax, 1AC8h
0x18000b4b6  call    _alloca_probe
0x18000b4bb  sub     rsp, rax
0x18000b4be  mov     rax, cs:__security_cookie
0x18000b4c5  xor     rax, rsp
0x18000b4c8  mov     [rbp+1A00h+var_50], rax
0x18000b4cf  mov     rax, rcx
0x18000b4d2  mov     [rbp+1A00h+psz], rcx
0x18000b4d6  xor     ecx, ecx
0x18000b4d8  mov     [rbp+1A00h+var_1930], r9
0x18000b4df  mov     [rbp+1A00h+var_1928], r8
0x18000b4e6  mov     [rbp+1A00h+var_1920], rdx
0x18000b4ed  mov     [rbp+1A00h+var_1918], rcx
0x18000b4f4  test    rax, rax
0x18000b4f7  jnz     short loc_18000B503
0x18000b4f9  mov     ebx, 80070057h
0x18000b4fe  jmp     loc_18001D2D9
0x18000b503  xor     eax, eax
0x18000b505  test    r8, r8
0x18000b508  jz      short loc_18000B4F9
0x18000b50a  test    r9, r9
0x18000b50d  jz      short loc_18000B4F9
0x18000b50f  mov     [rbp+1A00h+var_1954], eax
0x18000b515  lea     r15d, [rax+1]
0x18000b519  mov     [rbp+1A00h+var_1978], rax
0x18000b520  jmp     short loc_18000B524
0x18000b522  xor     eax, eax
0x18000b524  lock cmpxchg cs:dword_18002F8EC, r15d
0x18000b52d  jnz     short loc_18000B522
0x18000b52f  mov     eax, cs:dword_18002F8E8
0x18000b535  lea     r14, qword_18002F860
0x18000b53c  or      ebx, 0FFFFFFFFh
0x18000b53f  lea     r13, off_18002F000
0x18000b546  mov     [rbp+1A00h+var_1970], ebx
0x18000b54c  mov     esi, 4
0x18000b551  lea     r12d, [rsi+5Ch]
0x18000b555  test    eax, eax
0x18000b557  jnz     loc_18000B992
0x18000b55d  call    cs:__imp_GetProcessHeap
0x18000b563  xor     edx, edx; dwFlags
0x18000b565  mov     r8d, 338h; dwBytes
0x18000b56b  mov     rcx, rax; hHeap
0x18000b56e  call    cs:__imp_HeapAlloc
0x18000b574  mov     rdi, rax
0x18000b577  test    rax, rax
0x18000b57a  jz      loc_18000B8FD
0x18000b580  xor     ecx, ecx
0x18000b582  lea     rsi, qword_18002B6E0
0x18000b589  mov     r14, rax
0x18000b58c  mov     r12d, ecx
0x18000b58f  mov     r13d, ebx
0x18000b592  mov     r10d, ecx
0x18000b595  mov     r8d, ecx
0x18000b598  mov     eax, 0AB69605Eh
0x18000b59d  lea     r15d, [rcx+67h]
0x18000b5a1  movzx   ecx, byte ptr [rsi+1]
0x18000b5a5  movzx   ebx, byte ptr [rsi]
0x18000b5a8  movzx   r11d, byte ptr [rsi+4]
0x18000b5ad  lea     rsi, [rsi+8]
0x18000b5b1  shl     ebx, 8
0x18000b5b4  or      ebx, ecx
0x18000b5b6  shl     r11d, 8
0x18000b5ba  movzx   ecx, byte ptr [rsi-6]
0x18000b5be  shl     ebx, 8
0x18000b5c1  or      ebx, ecx
0x18000b5c3  movzx   ecx, byte ptr [rsi-5]
0x18000b5c7  shl     ebx, 8
0x18000b5ca  or      ebx, ecx
0x18000b5cc  movzx   ecx, byte ptr [rsi-3]
0x18000b5d0  or      r11d, ecx
0x18000b5d3  mov     edx, ebx
0x18000b5d5  movzx   ecx, byte ptr [rsi-2]
0x18000b5d9  xor     edx, r8d
0x18000b5dc  mov     r8d, edx
0x18000b5df  shl     r11d, 8
0x18000b5e3  or      r11d, ecx
0x18000b5e6  movzx   ecx, byte ptr [rsi-1]
0x18000b5ea  shl     r11d, 8
0x18000b5ee  or      r11d, ecx
0x18000b5f1  xor     r8d, r11d
0x18000b5f4  xor     r8d, r10d
0x18000b5f7  xor     r8d, 0AC987321h
0x18000b5fe  lea     ecx, [r8+54969FA2h]
0x18000b605  ror     ecx, 1Bh
0x18000b608  imul    r9d, ecx, 137Fh
0x18000b60f  mov     ecx, r8d
0x18000b612  ror     ecx, 16h
0x18000b615  add     r9d, ecx
0x18000b618  xor     r9d, edx
0x18000b61b  lea     ecx, [r9+7F1137Fh]
0x18000b622  ror     ecx, 9
0x18000b625  imul    edx, ecx, 0AB69h
0x18000b62b  mov     ecx, r9d
0x18000b62e  ror     ecx, 1Eh
0x18000b631  sub     edx, ecx
0x18000b633  xor     edx, r8d
0x18000b636  imul    r10d, edx, 605Eh
0x18000b63d  mov     ecx, edx
0x18000b63f  shr     ecx, 0Dh
0x18000b642  sub     r10d, ecx
0x18000b645  sub     r10d, 756C8A2h
0x18000b64c  xor     r10d, r9d
0x18000b64f  mov     r9d, 7F1137Fh
0x18000b655  mov     ecx, r10d
0x18000b658  xor     ecx, 0AB69h
0x18000b65e  ror     ecx, 1Ah
0x18000b661  imul    r8d, ecx, 7F1h
0x18000b668  mov     ecx, r10d
0x18000b66b  ror     ecx, 1Eh
0x18000b66e  sub     r8d, ecx
0x18000b671  xor     r8d, edx
0x18000b674  mov     ecx, r8d
0x18000b677  xor     ecx, eax
0x18000b679  sub     r9d, ecx
0x18000b67c  xor     r9d, r10d
0x18000b67f  mov     ecx, r9d
0x18000b682  mov     r10d, r9d
0x18000b685  xor     ecx, 137Fh
0x18000b68b  ror     r10d, 6
0x18000b68f  imul    edx, ecx, 0AB69h
0x18000b695  xor     r10d, edx
0x18000b698  xor     r10d, r8d
0x18000b69b  lea     ecx, [r10+7F1137Fh]
0x18000b6a2  ror     ecx, 0Fh
0x18000b6a5  imul    edx, ecx, 605Eh
0x18000b6ab  mov     ecx, r10d
0x18000b6ae  ror     ecx, 1Eh
0x18000b6b1  add     edx, ecx
0x18000b6b3  xor     edx, r9d
0x18000b6b6  lea     ecx, [rdx+54969FA2h]
0x18000b6bc  ror     ecx, 0Eh
0x18000b6bf  imul    r8d, ecx, 7F1h
0x18000b6c6  mov     ecx, edx
0x18000b6c8  ror     ecx, 18h
0x18000b6cb  sub     r8d, ecx
0x18000b6ce  xor     r8d, r10d
0x18000b6d1  mov     ecx, r8d
0x18000b6d4  mov     r10d, 7F1h
0x18000b6da  xor     ecx, eax
0x18000b6dc  ror     ecx, 0Ch
0x18000b6df  imul    r9d, ecx, 137Fh
0x18000b6e6  mov     ecx, r8d
0x18000b6e9  ror     ecx, 0Ah
0x18000b6ec  xor     r9d, ecx
0x18000b6ef  xor     r9d, edx
0x18000b6f2  mov     ecx, r9d
0x18000b6f5  xor     ecx, r10d
0x18000b6f8  imul    edx, ecx, 0AB69h
0x18000b6fe  mov     ecx, r9d
0x18000b701  shr     ecx, 0Ah
0x18000b704  xor     edx, ecx
0x18000b706  xor     edx, r8d
0x18000b709  mov     ecx, edx
0x18000b70b  not     ecx
0x18000b70d  ror     ecx, 5
0x18000b710  add     ecx, 605Eh
0x18000b716  imul    r8d, ecx, 7F1h
0x18000b71d  xor     r8d, r9d
0x18000b720  lea     r9d, [r8-7F1h]
0x18000b727  xor     r9d, edx
0x18000b72a  xor     r9d, eax
0x18000b72d  mov     ecx, r9d
0x18000b730  xor     ecx, r10d
0x18000b733  ror     ecx, 1Eh
0x18000b736  imul    r10d, ecx, 137Fh
0x18000b73d  mov     ecx, r9d
0x18000b740  shr     ecx, 2
0x18000b743  add     r10d, ecx
0x18000b746  xor     r10d, r8d
0x18000b749  lea     ecx, [r10-7F1137Fh]
0x18000b750  ror     ecx, 6
0x18000b753  imul    r8d, ecx, 0AB69h
0x18000b75a  mov     ecx, r10d
0x18000b75d  ror     ecx, 19h
0x18000b760  add     r8d, ecx
0x18000b763  xor     r8d, r9d
0x18000b766  mov     ecx, r8d
0x18000b769  mov     r9d, r8d
0x18000b76c  xor     ecx, 137Fh
0x18000b772  ror     r9d, 9
0x18000b776  imul    edx, ecx, 605Eh
0x18000b77c  add     r9d, edx
0x18000b77f  xor     r9d, r10d
0x18000b782  mov     ecx, r9d
0x18000b785  xor     ecx, 0AB69h
0x18000b78b  ror     ecx, 1Bh
0x18000b78e  imul    edx, ecx, 7F1h
0x18000b794  mov     ecx, r9d
0x18000b797  ror     ecx, 19h
0x18000b79a  add     edx, ecx
0x18000b79c  xor     edx, r8d
0x18000b79f  mov     r8d, edx
0x18000b7a2  xor     r8d, r9d
0x18000b7a5  xor     r8d, 0AC987321h
0x18000b7ac  mov     ecx, r8d
0x18000b7af  ror     ecx, 3
0x18000b7b2  imul    r9d, ecx, 137Fh
0x18000b7b9  sub     r9d, 0D0DD417h
0x18000b7c0  xor     r9d, edx
0x18000b7c3  lea     ecx, [r9-7F1137Fh]
0x18000b7ca  ror     ecx, 1
0x18000b7cc  imul    edx, ecx, 605Eh
0x18000b7d2  mov     ecx, r9d
0x18000b7d5  ror     ecx, 6
0x18000b7d8  sub     edx, ecx
0x18000b7da  xor     edx, r8d
0x18000b7dd  lea     ecx, [rdx-54969FA2h]
0x18000b7e3  ror     ecx, 1Dh
0x18000b7e6  imul    r8d, ecx, 7F1h
0x18000b7ed  mov     ecx, edx
0x18000b7ef  ror     ecx, 12h
0x18000b7f2  add     r8d, ecx
0x18000b7f5  xor     r8d, r9d
0x18000b7f8  lea     ecx, [r8-54969FA2h]
0x18000b7ff  ror     ecx, 11h
0x18000b802  imul    r9d, ecx, 137Fh
0x18000b809  mov     ecx, r8d
0x18000b80c  ror     ecx, 0Eh
0x18000b80f  sub     r9d, ecx
0x18000b812  xor     r9d, edx
0x18000b815  mov     ecx, r9d
0x18000b818  xor     ecx, 605Eh
0x18000b81e  imul    r10d, ecx, 0AB69h
0x18000b825  mov     ecx, r9d
0x18000b828  shr     ecx, 3
0x18000b82b  xor     r10d, ecx
0x18000b82e  xor     r10d, r8d
0x18000b831  mov     ecx, r10d
0x18000b834  xor     ecx, 7F1137Fh
0x18000b83a  ror     ecx, 1Ch
0x18000b83d  imul    r8d, ecx, 605Eh
0x18000b844  mov     ecx, r10d
0x18000b847  ror     ecx, 1Eh
0x18000b84a  xor     r10d, r13d
0x18000b84d  mov     r13d, r11d
0x18000b850  xor     r8d, ecx
0x18000b853  xor     r8d, r9d
0x18000b856  xor     r8d, r12d
0x18000b859  mov     r12d, ebx
0x18000b85c  mov     [r14+3], r8b
0x18000b860  mov     ecx, r8d
0x18000b863  ror     ecx, 8
0x18000b866  mov     [r14+7], r10b
0x18000b86a  mov     [r14+2], cl
0x18000b86e  mov     ecx, r10d
0x18000b871  ror     ecx, 8
0x18000b874  mov     [r14+6], cl
0x18000b878  mov     ecx, r8d
0x18000b87b  ror     ecx, 10h
0x18000b87e  mov     [r14+1], cl
0x18000b882  mov     ecx, r10d
0x18000b885  ror     ecx, 10h
0x18000b888  mov     [r14+5], cl
0x18000b88c  mov     ecx, r8d
0x18000b88f  ror     ecx, 18h
0x18000b892  mov     [r14], cl
0x18000b895  mov     ecx, r10d
0x18000b898  ror     ecx, 18h
0x18000b89b  mov     [r14+4], cl
0x18000b89f  lea     r14, [r14+8]
0x18000b8a3  sub     r15, 1
0x18000b8a7  jnz     loc_18000B5A1
0x18000b8ad  xor     ecx, ecx
0x18000b8af  mov     al, cl
0x18000b8b1  lea     r15d, [rcx+1]
0x18000b8b5  xor     al, [rcx+rdi]
0x18000b8b8  add     rcx, r15
0x18000b8bb  cmp     rcx, 338h
0x18000b8c2  jb      short loc_18000B8B5
0x18000b8c4  movzx   ecx, al
0x18000b8c7  cmp     rcx, cs:qword_18002BA18
0x18000b8ce  jz      short loc_18000B93E
0x18000b8d0  call    cs:__imp_GetProcessHeap
0x18000b8d6  mov     r8, rdi; lpMem
0x18000b8d9  xor     edx, edx; dwFlags
0x18000b8db  mov     rcx, rax; hHeap
0x18000b8de  call    cs:__imp_HeapFree
0x18000b8e4  mov     r12d, 60h ; '`'
0x18000b8ea  lea     r13, off_18002F000
0x18000b8f1  lea     r14, qword_18002F860
0x18000b8f8  lea     esi, [r12-5Ch]
0x18000b8fd  xor     ebx, ebx
0x18000b8ff  lea     rax, [rbx+rbx*2]
0x18000b903  mov     rcx, [r14+rax*8]; hLibModule
0x18000b907  test    rcx, rcx
0x18000b90a  jz      short loc_18000B912
0x18000b90c  call    cs:__imp_FreeLibrary
0x18000b912  add     rbx, r15
0x18000b915  cmp     rbx, rsi
0x18000b918  jnz     short loc_18000B8FF
0x18000b91a  mov     r8, r12; Size
  ... truncated ...
```
