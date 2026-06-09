# pre_cpp_init

- ea: `0x1400010f0`
- end: `0x140001139`
- name: `pre_cpp_init`
- size: `73`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!__wgetmainargs` at `0x140001128`
- `msvcrt!__wgetmainargs` at `0x140001128`

## pseudocode

```c
__int64 pre_cpp_init()
{
  __int64 result; // rax

  dword_1400050C4 = newmode;
  result = __wgetmainargs(
             &dword_1400050A8,
             &qword_1400050B0,
             &qword_1400050B8,
             (unsigned int)dowildcard,
             &dword_1400050C4);
  dword_1400050AC = result;
  return result;
}

```

## disassembly

```asm
0x1400010f0  sub     rsp, 38h
0x1400010f4  mov     eax, cs:_newmode
0x1400010fa  lea     r8, qword_1400050B8
0x140001101  mov     r9d, cs:_dowildcard
0x140001108  lea     rdx, qword_1400050B0
0x14000110f  mov     cs:dword_1400050C4, eax
0x140001115  lea     rcx, dword_1400050A8
0x14000111c  lea     rax, dword_1400050C4
0x140001123  mov     [rsp+38h+var_18], rax
0x140001128  call    cs:__imp___wgetmainargs
0x14000112e  mov     cs:dword_1400050AC, eax
0x140001134  add     rsp, 38h
0x140001138  retn
```
