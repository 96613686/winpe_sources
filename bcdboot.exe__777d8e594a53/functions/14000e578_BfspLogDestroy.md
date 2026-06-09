# BfspLogDestroy

- ea: `0x14000e578`
- end: `0x14000e5c2`
- name: `BfspLogDestroy`
- size: `74`
- prototype: `__int64()`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140003d30`
- `0x140004080`
- `0x140009658`
- `0x140009fd4`
- `0x140010728`

## callees

- `0x14000e578`
- `0x140013334`

## pseudocode

```c
__int64 BfspLogDestroy()
{
  int v0; // ecx

  if ( BcdLogInitialized )
  {
    BcdSetLogging(0, 0);
    BcdLogInitialized = v0;
  }
  if ( LogEnabled )
  {
    LogEnabled = 0;
    FilterLevel = 5;
    LogInitialized = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e578  sub     rsp, 28h
0x14000e57c  cmp     cs:BcdLogInitialized, 0
0x14000e583  jz      short loc_14000E594
0x14000e585  xor     edx, edx
0x14000e587  xor     ecx, ecx
0x14000e589  call    BcdSetLogging
0x14000e58e  mov     cs:BcdLogInitialized, ecx
0x14000e594  cmp     cs:LogEnabled, 0
0x14000e59b  jz      short loc_14000E5BB
0x14000e59d  mov     cs:LogEnabled, 0
0x14000e5a7  mov     cs:FilterLevel, 5
0x14000e5b1  mov     cs:LogInitialized, 0
0x14000e5bb  xor     eax, eax
0x14000e5bd  add     rsp, 28h
0x14000e5c1  retn
```
