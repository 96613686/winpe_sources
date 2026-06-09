# type_info::operator==(type_info const &)

- ea: `0x1800a2eb8`
- end: `0x1800a2ed7`
- name: `??8type_info@@QEBA_NAEBV0@@Z`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800a52e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800a2ec7`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800a2ec7`

## pseudocode

```c
bool __fastcall type_info::operator==(__int64 a1)
{
  return (unsigned int)__std_type_info_compare(a1 + 8, &qword_180125318) == 0;
}

```

## disassembly

```asm
0x1800a2eb8  sub     rsp, 28h
0x1800a2ebc  add     rcx, 8
0x1800a2ec0  lea     rdx, qword_180125318
0x1800a2ec7  call    cs:__imp___std_type_info_compare
0x1800a2ecd  test    eax, eax
0x1800a2ecf  setz    al
0x1800a2ed2  add     rsp, 28h
0x1800a2ed6  retn
```
