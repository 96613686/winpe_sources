# PrintAssertionMessageW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18002292c`
- end: `0x180022994`
- name: `?PrintAssertionMessageW@@YAXPEBG000K@Z`
- size: `104`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008d60`
- `0x18000fa90`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180022989`
- `ntdll!DbgPrintEx` at `0x180022989`

## string_xrefs

- `0x18002293b`: `onecoreuap\windows\wgi\common\shared\milcom.cpp`
- `0x180022961`: `CMILCOMBase::InternalAddRef`

## pseudocode

```c
void __fastcall PrintAssertionMessageW(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DbgPrintEx(
    0x65u,
    0,
    "\n*** Assertion failed: %ls%ls%ls\n***   %s%ls%sSource: `%ls:%ld`\n\n",
    L"Tried to AddRef an object which has previously been freed (refcount went to 0).",
    &word_180037ED4,
    &word_180037ED4,
    "Function: ",
    L"CMILCOMBase::InternalAddRef",
    ", ",
    L"onecoreuap\\windows\\wgi\\common\\shared\\milcom.cpp",
    39);
}

```

## disassembly

```asm
0x18002292c  mov     r11, rsp
0x18002292f  sub     rsp, 68h
0x180022933  mov     [rsp+68h+var_18], 27h ; '''
0x18002293b  lea     rax, aOnecoreuapWind; "onecoreuap\\windows\\wgi\\common\\share"...
0x180022942  mov     [r11-20h], rax
0x180022946  lea     r9, aTriedToAddrefA; "Tried to AddRef an object which has pre"...
0x18002294d  lea     rax, asc_180039508; ", "
0x180022954  xor     edx, edx; Level
0x180022956  mov     [r11-28h], rax
0x18002295a  lea     r8, Format; "\n*** Assertion failed: %ls%ls%ls\n*** "...
0x180022961  lea     rax, aCmilcombaseInt; "CMILCOMBase::InternalAddRef"
0x180022968  mov     [r11-30h], rax
0x18002296c  lea     rax, aFunction; "Function: "
0x180022973  mov     [r11-38h], rax
0x180022977  lea     ecx, [rdx+65h]; ComponentId
0x18002297a  lea     rax, word_180037ED4
0x180022981  mov     [r11-40h], rax
0x180022985  mov     [r11-48h], rax
0x180022989  call    cs:__imp_DbgPrintEx
0x18002298f  add     rsp, 68h
0x180022993  retn
```
