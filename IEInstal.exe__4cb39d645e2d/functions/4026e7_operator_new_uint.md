# operator new(uint)

- ea: `0x4026e7`
- end: `0x40270b`
- name: `??2@YAPAXI@Z`
- size: `36`
- prototype: `LPVOID __cdecl(SIZE_T dwBytes)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x402ae4`
- `0x402d20`
- `0x40373b`
- `0x404864`
- `0x405be0`
- `0x405c60`
- `0x4091c5`
- `0x40d860`
- `0x40dc30`
- `0x40e280`

## callees

- `0x4026e7`
- `0x409a27`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x4026f2`
- `KERNEL32!GetProcessHeap` at `0x4026f2`
- `KERNEL32!HeapAlloc` at `0x4026f9`
- `KERNEL32!HeapAlloc` at `0x4026f9`

## pseudocode

```c
LPVOID __cdecl operator new(SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // eax
  LPVOID result; // eax

  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 8u, dwBytes);
  if ( !result )
    std::_Xbad_alloc();
  return result;
}

```

## disassembly

```asm
0x4026e7  mov     edi, edi
0x4026e9  push    ebp
0x4026ea  mov     ebp, esp
0x4026ec  push    ecx
0x4026ed  push    [ebp+dwBytes]; dwBytes
0x4026f0  push    8; dwFlags
0x4026f2  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x4026f8  push    eax; hHeap
0x4026f9  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x4026ff  test    eax, eax
0x402701  jz      short loc_402706
0x402703  pop     ecx
0x402704  pop     ebp
0x402705  retn
0x402706  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
