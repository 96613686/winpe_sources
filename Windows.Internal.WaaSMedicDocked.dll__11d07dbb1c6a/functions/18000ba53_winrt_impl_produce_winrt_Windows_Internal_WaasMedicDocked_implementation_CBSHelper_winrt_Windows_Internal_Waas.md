# _winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor$1

- ea: `0x18000ba53`
- end: `0x18000bac8`
- name: `_winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor$1`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180001940`
- `0x18000ba53`

## pseudocode

```c
void __fastcall winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  if ( *(_WORD *)(*(_QWORD *)(a2 + 80) + 10LL) )
  {
    *(_QWORD *)(a2 + 32) = 272;
    *(_QWORD *)(a2 + 40) = *(_QWORD *)(a2 + 80) - 112LL;
    operator delete(*(void **)(a2 + 40));
  }
}

```

## disassembly

```asm
0x18000ba53  push    rbp
0x18000ba55  sub     rsp, 20h
0x18000ba59  mov     rbp, rdx
0x18000ba5c  mov     rax, [rbp+50h]
0x18000ba60  add     rax, 8
0x18000ba64  add     rax, 2
0x18000ba68  movzx   eax, word ptr [rax]
0x18000ba6b  test    eax, eax
0x18000ba6d  jz      short loc_18000BAC2
0x18000ba6f  mov     eax, 90h
0x18000ba74  add     rax, 80h
0x18000ba7a  mov     [rbp+20h], rax
0x18000ba7e  mov     eax, 10h
0x18000ba83  cmp     rax, 10h
0x18000ba87  jbe     short loc_18000BAA9
0x18000ba89  mov     rdx, [rbp+50h]
0x18000ba8d  sub     rdx, 70h ; 'p'
0x18000ba91  mov     eax, 8
0x18000ba96  imul    rcx, rax, -1
0x18000ba9a  mov     rax, rdx
0x18000ba9d  add     rax, rcx
0x18000baa0  mov     rax, [rax]
0x18000baa3  mov     [rbp+28h], rax
0x18000baa7  jmp     short loc_18000BAB5
0x18000baa9  mov     rax, [rbp+50h]
0x18000baad  sub     rax, 70h ; 'p'
0x18000bab1  mov     [rbp+28h], rax
0x18000bab5  mov     rdx, [rbp+20h]; unsigned __int64
0x18000bab9  mov     rcx, [rbp+28h]; void *
0x18000babd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bac2  add     rsp, 20h
0x18000bac6  pop     rbp
0x18000bac7  retn
```
