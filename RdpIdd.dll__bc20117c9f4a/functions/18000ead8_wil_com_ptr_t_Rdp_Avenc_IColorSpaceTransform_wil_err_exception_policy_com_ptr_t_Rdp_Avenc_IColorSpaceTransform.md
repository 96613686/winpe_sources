# wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)

- ea: `0x18000ead8`
- end: `0x18000eaf7`
- name: `??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `83`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ec90`
- `0x1800145c4`
- `0x180014e40`
- `0x180014f74`
- `0x18001509c`
- `0x1800151dc`
- `0x180015424`
- `0x18001638c`
- `0x180017b74`
- `0x18001818c`
- `0x1800184b4`
- `0x18001a6bc`
- `0x18001afa8`
- `0x18001b1a0`
- `0x18001d3fc`
- `0x18001d5f0`
- `0x18001d938`
- `0x180023578`
- `0x180023924`
- `0x1800239c4`
- `0x180023b6c`
- `0x18002476c`
- `0x180025c90`
- `0x180027398`
- `0x180027724`
- `0x18002784c`
- `0x180027b88`
- `0x180027c78`
- `0x180027d70`
- `0x180027e24`
- `0x180028cdc`
- `0x1800291b0`
- `0x1800299ac`
- `0x180029c18`
- `0x18002a390`
- `0x18002a3f8`
- `0x18002a460`
- `0x18002b6c8`
- `0x18002e4e0`
- `0x18002e614`
- `0x18002e668`
- `0x18002e6dc`
- `0x18002e860`
- `0x18002ee40`
- `0x18002f0b0`
- `0x18002f4e0`
- `0x18002f688`
- `0x180032b00`
- `0x18003bf7c`
- `0x18003c063`

## callees

- `0x18000ead8`
- `0x18003f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000ead8  sub     rsp, 28h
0x18000eadc  mov     rcx, [rcx]
0x18000eadf  test    rcx, rcx
0x18000eae2  jz      short loc_18000EAF1
0x18000eae4  mov     rax, [rcx]
0x18000eae7  mov     rax, [rax+10h]
0x18000eaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaf0  nop
0x18000eaf1  add     rsp, 28h
0x18000eaf5  retn
```
