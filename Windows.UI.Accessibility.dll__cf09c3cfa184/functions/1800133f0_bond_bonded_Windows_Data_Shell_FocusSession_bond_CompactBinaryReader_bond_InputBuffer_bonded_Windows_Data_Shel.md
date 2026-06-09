# bond::bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x1800133f0`
- end: `0x180013416`
- name: `??1?$bonded@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012110`
- `0x180019124`
- `0x18001b298`
- `0x18001c218`
- `0x18001c36c`
- `0x18001c504`
- `0x18001cc34`
- `0x18001f4c8`
- `0x180032d26`
- `0x1800331cc`
- `0x180033240`

## callees

- `0x180010618`
- `0x1800133f0`
- `0x180013880`

## pseudocode

```c
void __fastcall bond::bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 40) )
    bond::detail::Skip<bond::CompactBinaryReader<bond::InputBuffer>,bond::bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>>(*(_QWORD *)(a1 + 32));
  boost::detail::shared_count::~shared_count((boost::detail::shared_count *)(a1 + 24));
}

```

## disassembly

```asm
0x1800133f0  push    rbx
0x1800133f2  sub     rsp, 20h
0x1800133f6  mov     rbx, rcx
0x1800133f9  cmp     byte ptr [rcx+28h], 0
0x1800133fd  jz      short loc_180013408
0x1800133ff  mov     rcx, [rcx+20h]
0x180013403  call    ??$Skip@V?$CompactBinaryReader@VInputBuffer@bond@@@bond@@V?$bonded@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@2@@detail@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@AEBV?$bonded@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@1@AEBUnothrow_t@std@@@Z; bond::detail::Skip<bond::CompactBinaryReader<bond::InputBuffer>,bond::bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>>(bond::CompactBinaryReader<bond::InputBuffer> &,bond::bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &> const &,std::nothrow_t const &)
0x180013408  lea     rcx, [rbx+18h]; this
0x18001340c  add     rsp, 20h
0x180013410  pop     rbx
0x180013411  jmp     ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
```
