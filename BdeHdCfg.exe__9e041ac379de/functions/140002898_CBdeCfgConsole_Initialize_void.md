# CBdeCfgConsole::Initialize(void)

- ea: `0x140002898`
- end: `0x1400028c9`
- name: `?Initialize@CBdeCfgConsole@@QEAAJXZ`
- size: `49`
- prototype: `int __fastcall(CBdeCfgConsole *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001dbc`
- `0x140003884`

## callees

- `0x140002898`
- `0x1400031c4`

## import_xrefs

- `BDEHDCFGLIB!?Load@CBdeCfgLibraryLoader@@QEAAJXZ` at `0x1400028bc`
- `BDEHDCFGLIB!?Load@CBdeCfgLibraryLoader@@QEAAJXZ` at `0x1400028bc`
- `BDEHDCFGLIB!BdeCfgIsElevated` at `0x1400028a1`
- `BDEHDCFGLIB!BdeCfgIsElevated` at `0x1400028a1`

## pseudocode

```c
int __fastcall CBdeCfgConsole::Initialize(CBdeCfgConsole *this)
{
  int result; // eax

  result = BdeCfgIsElevated();
  if ( result >= 0 )
  {
    CBdeCfgConsole::PrintConsoleMessage(this, 1084227636);
    return CBdeCfgLibraryLoader::Load((CBdeCfgConsole *)((char *)this + 8));
  }
  return result;
}

```

## disassembly

```asm
0x140002898  push    rbx
0x14000289a  sub     rsp, 20h
0x14000289e  mov     rbx, rcx
0x1400028a1  call    cs:__imp_?BdeCfgIsElevated@@YAJXZ; BdeCfgIsElevated(void)
0x1400028a7  test    eax, eax
0x1400028a9  js      short loc_1400028C3
0x1400028ab  mov     edx, 40A00034h; int
0x1400028b0  mov     rcx, rbx; this
0x1400028b3  call    ?PrintConsoleMessage@CBdeCfgConsole@@AEAAJJZZ; CBdeCfgConsole::PrintConsoleMessage(long,...)
0x1400028b8  lea     rcx, [rbx+8]
0x1400028bc  call    cs:__imp_?Load@CBdeCfgLibraryLoader@@QEAAJXZ; CBdeCfgLibraryLoader::Load(void)
0x1400028c2  nop
0x1400028c3  add     rsp, 20h
0x1400028c7  pop     rbx
0x1400028c8  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
