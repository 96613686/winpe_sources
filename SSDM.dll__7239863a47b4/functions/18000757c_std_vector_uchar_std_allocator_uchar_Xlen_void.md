# std::vector<uchar *,std::allocator<uchar *>>::_Xlen(void)

- ea: `0x18000757c`
- end: `0x18000758d`
- name: `?_Xlen@?$vector@PEAEV?$allocator@PEAE@std@@@std@@IEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800073ec`
- `0x180007820`
- `0x1800078e4`
- `0x18000bcdc`
- `0x18000bda0`
- `0x18000be94`
- `0x18000c9a8`

## callees

- `0x180002c18`

## pseudocode

```c
void __noreturn std::vector<unsigned char *>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x18000757c  sub     rsp, 28h
0x180007580  lea     rcx, aVectorTTooLong
0x180007587  call    ?_Xlength_error@std@@YAXPEBD@Z
```
