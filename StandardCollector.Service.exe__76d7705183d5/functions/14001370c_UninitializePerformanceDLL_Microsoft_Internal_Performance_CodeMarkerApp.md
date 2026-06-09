# UninitializePerformanceDLL(Microsoft::Internal::Performance::CodeMarkerApp)

- ea: `0x14001370c`
- end: `0x1400137c4`
- name: `?UninitializePerformanceDLL@@YAXW4CodeMarkerApp@Performance@Internal@Microsoft@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001388`
- `0x140001f8c`

## callees

- `0x14001370c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400137ac`
- `KERNEL32!FreeLibrary` at `0x1400137ac`
- `KERNEL32!DeleteAtom` at `0x14001373c`
- `KERNEL32!DeleteAtom` at `0x140013757`
- `KERNEL32!DeleteAtom` at `0x14001373c`
- `KERNEL32!DeleteAtom` at `0x140013757`
- `KERNEL32!FindAtomW` at `0x14001372e`
- `KERNEL32!FindAtomW` at `0x140013749`
- `KERNEL32!FindAtomW` at `0x14001372e`
- `KERNEL32!FindAtomW` at `0x140013749`

## pseudocode

```c
void __fastcall UninitializePerformanceDLL(int a1)
{
  ATOM AtomW; // ax
  ATOM v3; // ax

  if ( ghInstPerf )
  {
    AtomW = FindAtomW(lpString);
    if ( AtomW )
      DeleteAtom(AtomW);
    v3 = FindAtomW(off_140023018);
    if ( v3 )
      DeleteAtom(v3);
    if ( gpfUnInitPerf )
      gpfUnInitPerf(a1);
    gpfInitPerf = 0;
    gpfInitPerf2 = 0;
    gpfUnInitPerf = 0;
    gpfCodeMarker = 0;
    gpSetPerformanceRegRoot = 0;
    gpfBeginLogging = 0;
    gpfWriteLog = 0;
    gfTriedToAttachPerformanceDll = 0;
    FreeLibrary(ghInstPerf);
    ghInstPerf = 0;
  }
}

```

## disassembly

```asm
0x14001370c  mov     [rsp+arg_0], rbx
0x140013711  push    rdi
0x140013712  sub     rsp, 20h
0x140013716  xor     edi, edi
0x140013718  mov     ebx, ecx
0x14001371a  cmp     cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * ghInstPerf
0x140013721  jz      loc_1400137B9
0x140013727  mov     rcx, cs:lpString; lpString
0x14001372e  call    cs:__imp_FindAtomW
0x140013734  test    ax, ax
0x140013737  jz      short loc_140013742
0x140013739  movzx   ecx, ax; nAtom
0x14001373c  call    cs:__imp_DeleteAtom
0x140013742  mov     rcx, cs:off_140023018; lpString
0x140013749  call    cs:__imp_FindAtomW
0x14001374f  test    ax, ax
0x140013752  jz      short loc_14001375D
0x140013754  movzx   ecx, ax; nAtom
0x140013757  call    cs:__imp_DeleteAtom
0x14001375d  mov     rax, cs:?gpfUnInitPerf@@3P6AXH@ZEA; void (*gpfUnInitPerf)(int)
0x140013764  test    rax, rax
0x140013767  jz      short loc_14001376D
0x140013769  mov     ecx, ebx
0x14001376b  call    rax ; void (*gpfUnInitPerf)(int)
0x14001376d  mov     rcx, cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA; hLibModule
0x140013774  mov     cs:?gpfInitPerf@@3P6AXH@ZEA, rdi; void (*gpfInitPerf)(int)
0x14001377b  mov     cs:?gpfInitPerf2@@3P6AXHPEBG@ZEA, rdi; void (*gpfInitPerf2)(int,ushort const *)
0x140013782  mov     cs:?gpfUnInitPerf@@3P6AXH@ZEA, rdi; void (*gpfUnInitPerf)(int)
0x140013789  mov     cs:?gpfCodeMarker@@3P6AXHPEBXK@ZEA, rdi; void (*gpfCodeMarker)(int,void const *,ulong)
0x140013790  mov     cs:?gpSetPerformanceRegRoot@@3P6AXPEBG@ZEA, rdi; void (*gpSetPerformanceRegRoot)(ushort const *)
0x140013797  mov     cs:?gpfBeginLogging@@3P6AJH@ZEA, rdi; long (*gpfBeginLogging)(int)
0x14001379e  mov     cs:?gpfWriteLog@@3P6AJPEAUIStream@@@ZEA, rdi; long (*gpfWriteLog)(IStream *)
0x1400137a5  mov     cs:?gfTriedToAttachPerformanceDll@@3_NA, dil; bool gfTriedToAttachPerformanceDll
0x1400137ac  call    cs:__imp_FreeLibrary
0x1400137b2  mov     cs:?ghInstPerf@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * ghInstPerf
0x1400137b9  mov     rbx, [rsp+28h+arg_0]
0x1400137be  add     rsp, 20h
0x1400137c2  pop     rdi
0x1400137c3  retn
```
