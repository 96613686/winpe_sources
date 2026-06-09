# __invalid_parameter_noinfo

- ea: `0x410369`
- end: `0x410379`
- name: `__invalid_parameter_noinfo`
- size: `16`
- prototype: `void __cdecl()`
- caller_count: `47`
- callee_count: `1`
- tags: ``

## callers

- `0x401ef9`
- `0x402110`
- `0x4023c6`
- `0x4034e9`
- `0x4059df`
- `0x409593`
- `0x41092f`
- `0x411474`
- `0x411577`
- `0x4115e0`
- `0x411651`
- `0x4116ff`
- `0x411764`
- `0x411867`
- `0x4119ee`
- `0x41217b`
- `0x4122a3`
- `0x4123fc`
- `0x41245d`
- `0x412b13`
- `0x412c68`
- `0x412dcd`
- `0x412de8`
- `0x412fc9`
- `0x4135d1`
- `0x413c9a`
- `0x413e98`
- `0x414b0e`
- `0x414ba9`
- `0x415680`
- `0x415c54`
- `0x415dda`
- `0x415f4f`
- `0x4173f6`
- `0x4177ad`
- `0x417ca4`
- `0x417e00`
- `0x417eb0`
- `0x41874d`
- `0x418f45`
- `0x419037`
- `0x4192fc`
- `0x4196ff`
- `0x41b28a`
- `0x41b301`
- `0x41bf98`
- `0x41fa50`

## callees

- `0x410305`

## pseudocode

```c
void __cdecl _invalid_parameter_noinfo()
{
  _invalid_parameter(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x410369  xor     eax, eax
0x41036b  push    eax; Reserved
0x41036c  push    eax; LineNo
0x41036d  push    eax; FileName
0x41036e  push    eax; FunctionName
0x41036f  push    eax; Expression
0x410370  call    __invalid_parameter
0x410375  add     esp, 14h
0x410378  retn
```
