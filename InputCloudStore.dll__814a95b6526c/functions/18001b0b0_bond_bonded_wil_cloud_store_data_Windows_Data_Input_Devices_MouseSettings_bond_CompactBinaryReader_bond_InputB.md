# bond::bonded<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b0b0`
- end: `0x18001b0d6`
- name: `??1?$bonded@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018f98`
- `0x180019250`
- `0x18002f116`

## callees

- `0x180010ef4`
- `0x18001b0b0`
- `0x18001b8d8`

## pseudocode

```c
void __fastcall bond::bonded<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 40) )
    bond::detail::Skip<bond::CompactBinaryReader<bond::InputBuffer>,bond::bonded<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>>(*(bond::InputBuffer **)(a1 + 32));
  boost::detail::shared_count::~shared_count((boost::detail::shared_count *)(a1 + 24));
}

```

## disassembly

```asm
0x18001b0b0  push    rbx
0x18001b0b2  sub     rsp, 20h
0x18001b0b6  mov     rbx, rcx
0x18001b0b9  cmp     byte ptr [rcx+28h], 0
0x18001b0bd  jz      short loc_18001B0C8
0x18001b0bf  mov     rcx, [rcx+20h]
0x18001b0c3  call    ??$Skip@V?$CompactBinaryReader@VInputBuffer@bond@@@bond@@V?$bonded@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@2@@detail@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@AEBV?$bonded@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@1@AEBUnothrow_t@std@@@Z; bond::detail::Skip<bond::CompactBinaryReader<bond::InputBuffer>,bond::bonded<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::CompactBinaryReader<bond::InputBuffer> &>>(bond::CompactBinaryReader<bond::InputBuffer> &,bond::bonded<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::CompactBinaryReader<bond::InputBuffer> &> const &,std::nothrow_t const &)
0x18001b0c8  lea     rcx, [rbx+18h]; this
0x18001b0cc  add     rsp, 20h
0x18001b0d0  pop     rbx
0x18001b0d1  jmp     ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
```
