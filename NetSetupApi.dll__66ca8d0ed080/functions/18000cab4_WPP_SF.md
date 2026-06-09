# WPP_SF_

- ea: `0x18000cab4`
- end: `0x18000cad5`
- name: `WPP_SF_`
- size: `33`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64)`
- caller_count: `87`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001afc`
- `0x180001c48`
- `0x180002320`
- `0x18000266c`
- `0x180003490`
- `0x180003818`
- `0x180003970`
- `0x180004260`
- `0x180004430`
- `0x180004a20`
- `0x180004d40`
- `0x18000515c`
- `0x180005c60`
- `0x180005ce4`
- `0x180005d60`
- `0x180005de4`
- `0x180005e60`
- `0x180006068`
- `0x1800060f8`
- `0x1800063f8`
- `0x180006528`
- `0x180006af8`
- `0x18000be20`
- `0x18000c188`
- `0x18000c5e8`
- `0x18000de90`
- `0x18000fd78`
- `0x1800108e4`
- `0x180011520`
- `0x18001167c`
- `0x180011bc2`
- `0x180011c0c`
- `0x180011c56`
- `0x180011d6f`
- `0x180011db9`
- `0x180011e03`
- `0x180011f1f`
- `0x180011f69`
- `0x180011fb3`
- `0x180012142`
- `0x18001218c`
- `0x1800121d6`
- `0x1800123ff`
- `0x180012449`
- `0x180012493`
- `0x180012695`
- `0x1800126df`
- `0x180012729`
- `0x180012838`
- `0x180012882`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000caca`
- `ntdll!EtwTraceMessage` at `0x18000caca`

## pseudocode

```c
__int64 __fastcall WPP_SF_(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  return EtwTraceMessage(a1, 43, a3, a2, 0);
}

```

## disassembly

```asm
0x18000cab4  sub     rsp, 38h
0x18000cab8  movzx   r9d, dx
0x18000cabc  mov     edx, 2Bh ; '+'
0x18000cac1  mov     [rsp+38h+var_18], 0
0x18000caca  call    cs:__imp_EtwTraceMessage
0x18000cad0  add     rsp, 38h
0x18000cad4  retn
```
