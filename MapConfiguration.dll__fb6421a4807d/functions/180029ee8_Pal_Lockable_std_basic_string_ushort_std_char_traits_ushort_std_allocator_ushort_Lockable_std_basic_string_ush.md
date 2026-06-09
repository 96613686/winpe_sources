# Pal::Lockable<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::~Lockable<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(void)

- ea: `0x180029ee8`
- end: `0x180029f09`
- name: `??1?$Lockable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Pal@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180029f10`
- `0x180029f30`
- `0x18002b638`

## callees

- `0x18000c354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029f02`

## pseudocode

```c
void __fastcall Pal::Lockable<std::wstring>::~Lockable<std::wstring>(struct _RTL_CRITICAL_SECTION *a1)
{
  std::wstring::_Tidy_deallocate(&a1[1]);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x180029ee8  push    rbx
0x180029eea  sub     rsp, 20h
0x180029eee  mov     rbx, rcx
0x180029ef1  add     rcx, 28h ; '('
0x180029ef5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029efa  mov     rcx, rbx
0x180029efd  add     rsp, 20h
0x180029f01  pop     rbx
0x180029f02  jmp     cs:__imp_DeleteCriticalSection
```
