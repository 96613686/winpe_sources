# std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>::~pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>(void)

- ea: `0x18000f68c`
- end: `0x18000f6b0`
- name: `??1?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f0cc`
- `0x18000f62c`

## callees

- `0x18000f68c`
- `0x1800101cc`
- `0x180010718`

## pseudocode

```c
__int64 __fastcall std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::~pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>(
        __int64 a1)
{
  std::_Ref_count_base *v2; // rcx

  v2 = *(std::_Ref_count_base **)(a1 + 40);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  return std::string::_Tidy_deallocate(a1);
}

```

## disassembly

```asm
0x18000f68c  push    rbx
0x18000f68e  sub     rsp, 20h
0x18000f692  mov     rbx, rcx
0x18000f695  mov     rcx, [rcx+28h]; this
0x18000f699  test    rcx, rcx
0x18000f69c  jz      short loc_18000F6A3
0x18000f69e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f6a3  mov     rcx, rbx
0x18000f6a6  add     rsp, 20h
0x18000f6aa  pop     rbx
0x18000f6ab  jmp     ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
```
