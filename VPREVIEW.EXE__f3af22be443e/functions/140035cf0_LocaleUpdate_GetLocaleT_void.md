# _LocaleUpdate::GetLocaleT(void)

- ea: `0x140035cf0`
- end: `0x140035cf5`
- name: `?GetLocaleT@_LocaleUpdate@@QEAAPEAU__crt_locale_pointers@@XZ`
- size: `5`
- prototype: `struct __crt_locale_pointers *__fastcall(_LocaleUpdate *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
struct __crt_locale_pointers *__fastcall _LocaleUpdate::GetLocaleT(_LocaleUpdate *this)
{
  return (struct __crt_locale_pointers *)((char *)this + 8);
}

```

## disassembly

```asm
0x140035cf0  lea     rax, [rcx+8]
0x140035cf4  retn
```
