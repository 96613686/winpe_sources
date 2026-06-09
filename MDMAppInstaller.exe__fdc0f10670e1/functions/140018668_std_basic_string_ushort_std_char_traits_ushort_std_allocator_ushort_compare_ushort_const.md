# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(ushort const *)

- ea: `0x140018668`
- end: `0x140018694`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHPEBG@Z`
- size: `44`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001668c`

## callees

- `0x1400068c8`
- `0x140011e48`

## pseudocode

```c
__int64 std::wstring::compare()
{
  unsigned __int64 v0; // rax
  __int64 v1; // rdx
  __int64 v2; // rcx
  _QWORD *v3; // r10

  v0 = std::char_traits<unsigned short>::length(L"S-0-0-00-0000000000-0000000000-000000000-000");
  return std::wstring::compare(v3, v1, v3[2], v2, v0);
}

```

## disassembly

```asm
0x140018668  sub     rsp, 38h
0x14001866c  mov     r10, rcx
0x14001866f  lea     rcx, aS0000000000000_0; "S-0-0-00-0000000000-0000000000-00000000"...
0x140018676  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14001867b  mov     r8, [r10+10h]
0x14001867f  mov     r9, rcx
0x140018682  mov     rcx, r10
0x140018685  mov     [rsp+38h+var_18], rax
0x14001868a  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z; std::wstring::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x14001868f  add     rsp, 38h
0x140018693  retn
```
