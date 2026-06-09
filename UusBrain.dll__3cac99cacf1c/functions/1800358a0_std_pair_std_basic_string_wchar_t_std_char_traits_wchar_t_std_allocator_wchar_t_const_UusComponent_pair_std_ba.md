# std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>::~pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>(void)

- ea: `0x1800358a0`
- end: `0x1800358d1`
- name: `??1?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@QEAA@XZ`
- size: `49`
- prototype: `void(void *)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004ae74`
- `0x18004ca75`
- `0x18004cabd`
- `0x18004cb05`
- `0x18004cb4d`
- `0x18004cb95`
- `0x18004cbdd`
- `0x18004cc25`
- `0x18004cc6d`
- `0x18004ccb5`
- `0x18004ccfd`
- `0x18004cd45`
- `0x18004cd8d`
- `0x18004cdd5`
- `0x18004ce1d`
- `0x18004ce65`
- `0x18004cead`
- `0x18004cef5`
- `0x18004cf3d`

## callees

- `0x18000f84c`
- `0x180029644`

## pseudocode

```c
void __fastcall std::pair<std::wstring const,UusComponent>::~pair<std::wstring const,UusComponent>(char *a1)
{
  std::vector<enum UusCapability>::~vector<enum UusCapability>(a1 + 64);
  std::wstring::_Tidy_deallocate(a1 + 32);
  std::wstring::_Tidy_deallocate(a1);
}

```

## disassembly

```asm
0x1800358a0  mov     [rsp+arg_0], rbx
0x1800358a5  push    rdi
0x1800358a6  sub     rsp, 20h
0x1800358aa  mov     rdi, rcx
0x1800358ad  add     rcx, 40h ; '@'
0x1800358b1  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x1800358b6  lea     rcx, [rdi+20h]
0x1800358ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800358bf  mov     rcx, rdi
0x1800358c2  mov     rbx, [rsp+28h+arg_0]
0x1800358c7  add     rsp, 20h
0x1800358cb  pop     rdi
0x1800358cc  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
