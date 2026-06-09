# _ParseSettingsMasterDatastoreXML_::_1_::dtor$2

- ea: `0x180011a7f`
- end: `0x180011aa8`
- name: `_ParseSettingsMasterDatastoreXML_::_1_::dtor$2`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008f84`
- `0x180011a7f`

## pseudocode

```c
void __fastcall ParseSettingsMasterDatastoreXML_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    std::vector<std::shared_ptr<CConfigSource>>::~vector<std::shared_ptr<CConfigSource>>(*(_QWORD **)(a2 + 160));
  }
}

```

## disassembly

```asm
0x180011a7f  push    rbp
0x180011a81  sub     rsp, 20h
0x180011a85  mov     rbp, rdx
0x180011a88  mov     eax, [rbp+20h]
0x180011a8b  and     eax, 1
0x180011a8e  test    eax, eax
0x180011a90  jz      short loc_180011AA2
0x180011a92  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180011a96  mov     rcx, [rbp+0A0h]
0x180011a9d  call    ??1?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<CConfigSource>>::~vector<std::shared_ptr<CConfigSource>>(void)
0x180011aa2  add     rsp, 20h
0x180011aa6  pop     rbp
0x180011aa7  retn
```
