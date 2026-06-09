# LanguagePacksUninstaller::~LanguagePacksUninstaller(void)

- ea: `0x18001333c`
- end: `0x180013348`
- name: `??1LanguagePacksUninstaller@@QEAA@XZ`
- size: `12`
- prototype: `void __fastcall(LanguagePacksUninstaller *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180028c84`
- `0x180028e0e`

## callees

- `0x1800214f4`

## pseudocode

```c
void __fastcall LanguagePacksUninstaller::~LanguagePacksUninstaller(LanguagePacksUninstaller *this)
{
  std::vector<std::wstring>::_Tidy((char *)this + 208);
}

```

## disassembly

```asm
0x18001333c  add     rcx, 0D0h
0x180013343  jmp     ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
```
