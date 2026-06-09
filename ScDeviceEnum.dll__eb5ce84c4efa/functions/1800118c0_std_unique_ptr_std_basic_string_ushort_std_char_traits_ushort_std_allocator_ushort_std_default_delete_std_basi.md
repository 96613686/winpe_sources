# std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::reset(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800118c0`
- end: `0x1800118e8`
- name: `?reset@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `40`
- prototype: `void __fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fd90`
- `0x180010dd0`

## callees

- `0x18000db20`
- `0x1800118c0`

## pseudocode

```c
void __fastcall std::unique_ptr<std::wstring>::reset(__int64 *a1, __int64 a2)
{
  if ( a2 != *a1 )
  {
    std::unique_ptr<std::wstring>::_Delete(a1, a2);
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x1800118c0  mov     [rsp+arg_0], rbx
0x1800118c5  push    rdi
0x1800118c6  sub     rsp, 20h
0x1800118ca  mov     rdi, rdx
0x1800118cd  mov     rbx, rcx
0x1800118d0  cmp     rdx, [rcx]
0x1800118d3  jz      short loc_1800118DD
0x1800118d5  call    ?_Delete@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::wstring>::_Delete(void)
0x1800118da  mov     [rbx], rdi
0x1800118dd  mov     rbx, [rsp+28h+arg_0]
0x1800118e2  add     rsp, 20h
0x1800118e6  pop     rdi
0x1800118e7  retn
```
