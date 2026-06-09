# __invalid_parameter_noinfo

- ea: `0x10015cbc`
- end: `0x10015ccc`
- name: `__invalid_parameter_noinfo`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `43`
- callee_count: `1`
- tags: ``

## callers

- `0x1000b036`
- `0x1000c6bd`
- `0x10012e0a`
- `0x10013031`
- `0x100136f6`
- `0x1001371f`
- `0x1001374d`
- `0x1001380a`
- `0x1001398a`
- `0x100142de`
- `0x100143f2`
- `0x10014588`
- `0x100145a7`
- `0x1001460b`
- `0x100146bc`
- `0x1001480a`
- `0x10015370`
- `0x100154c3`
- `0x1001561a`
- `0x100163d0`
- `0x10016c0f`
- `0x100178f4`
- `0x10017da2`
- `0x10018161`
- `0x100185f7`
- `0x10018734`
- `0x10018a9a`
- `0x10018eb1`
- `0x10019e3a`
- `0x1001a7af`
- `0x1001b876`
- `0x1001d215`
- `0x1001d31d`
- `0x1001d488`
- `0x1001d540`
- `0x1001d9e7`
- `0x1001da85`
- `0x1001dc99`
- `0x1001e49d`
- `0x1001e585`
- `0x1001ecc6`
- `0x1001ed3d`
- `0x100200b2`

## callees

- `0x10015c58`

## pseudocode

```c
void __cdecl _invalid_parameter_noinfo()
{
  _invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x10015cbc  xor     eax, eax
0x10015cbe  push    eax; Reserved
0x10015cbf  push    eax; LineNo
0x10015cc0  push    eax; FileName
0x10015cc1  push    eax; FunctionName
0x10015cc2  push    eax; Expression
0x10015cc3  call    __invalid_parameter
0x10015cc8  add     esp, 14h
0x10015ccb  retn
```
