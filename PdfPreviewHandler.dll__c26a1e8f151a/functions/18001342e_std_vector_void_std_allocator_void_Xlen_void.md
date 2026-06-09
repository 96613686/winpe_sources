# std::vector<void *,std::allocator<void *>>::_Xlen(void)

- ea: `0x18001342e`
- end: `0x18001343e`
- name: `?_Xlen@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEBAXXZ_0`
- size: `16`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d96`
- `0x180007e08`
- `0x180007e7c`
- `0x1800083a2`
- `0x180008474`
- `0x18000d6fe`
- `0x18000d91a`
- `0x18000da84`
- `0x18000dc64`
- `0x18000dd0e`
- `0x18000dfc6`
- `0x180010b7a`
- `0x180022062`
- `0x180024fad`

## callees

- `0x18001343f`

## pseudocode

```c
void __noreturn std::vector<void *>::_Xlen()
{
  sub_18001343F("basic_string");
}

```

## disassembly

```asm
0x18001342e  sub     rsp, 28h
0x180013432  lea     rcx, aBasicString
0x180013439  call    sub_18001343F
```
