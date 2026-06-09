# std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>::_Xlen(void)

- ea: `0x18000cd9c`
- end: `0x18000cdad`
- name: `?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `17`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000c794`
- `0x18000c828`
- `0x18000cc9c`
- `0x18000d2bc`
- `0x18000f64c`
- `0x18000f710`
- `0x1800114c8`
- `0x18001161c`
- `0x180016f64`
- `0x18001734c`
- `0x18001932c`
- `0x180019494`
- `0x1800195b0`
- `0x18001a8a8`
- `0x18001ba44`
- `0x18001d4a8`
- `0x18001e498`

## callees

- `0x180001c00`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __noreturn std::vector<std::unique_ptr<FilterAgent>>::_Xlen()
{
  std::_Xlength_error("vector<T> too long");
}

```

## disassembly

```asm
0x18000cd9c  sub     rsp, 28h
0x18000cda0  lea     rcx, aVectorTTooLong
0x18000cda7  call    ?_Xlength_error@std@@YAXPEBD@Z
```
