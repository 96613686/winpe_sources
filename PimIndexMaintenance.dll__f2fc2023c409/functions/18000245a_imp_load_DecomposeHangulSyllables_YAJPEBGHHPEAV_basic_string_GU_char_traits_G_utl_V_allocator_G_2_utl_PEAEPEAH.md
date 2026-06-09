# __imp_load_?DecomposeHangulSyllables@@YAJPEBGHHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAEPEAH@Z

- ea: `0x18000245a`
- end: `0x180002466`
- name: `__imp_load_?DecomposeHangulSyllables@@YAJPEBGHHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAEPEAH@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800023c9`

## import_xrefs

- `UserDataLanguageUtil!DecomposeHangulSyllables` at `0x18000245a`

## pseudocode

```c
__int64 load__DecomposeHangulSyllables__YAJPEBGHHPEAV__basic_string_GU__char_traits_G_utl__V__allocator_G_2__utl__PEAEPEAH_Z()
{
  return _tailMerge_userdatalanguageutil_dll();
}

```

## disassembly

```asm
0x18000245a  lea     rax, __imp_?DecomposeHangulSyllables@@YAJPEBGHHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAEPEAH@Z; DecomposeHangulSyllables(ushort const *,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,uchar *,int *)
0x180002461  jmp     __tailMerge_userdatalanguageutil_dll
```
