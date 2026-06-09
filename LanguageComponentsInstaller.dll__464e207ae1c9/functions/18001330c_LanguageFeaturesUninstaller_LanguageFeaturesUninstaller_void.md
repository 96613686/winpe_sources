# LanguageFeaturesUninstaller::~LanguageFeaturesUninstaller(void)

- ea: `0x18001330c`
- end: `0x180013334`
- name: `??1LanguageFeaturesUninstaller@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(LanguageFeaturesUninstaller *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180028c60`
- `0x180028dea`

## callees

- `0x1800214f4`
- `0x180021590`

## pseudocode

```c
void __fastcall LanguageFeaturesUninstaller::~LanguageFeaturesUninstaller(LanguageFeaturesUninstaller *this)
{
  std::vector<CbsLanguageFeature>::_Tidy((char *)this + 48);
  std::vector<std::wstring>::_Tidy((char *)this + 24);
  std::vector<std::wstring>::_Tidy(this);
}

```

## disassembly

```asm
0x18001330c  push    rbx
0x18001330e  sub     rsp, 20h
0x180013312  mov     rbx, rcx
0x180013315  add     rcx, 30h ; '0'
0x180013319  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18001331e  lea     rcx, [rbx+18h]
0x180013322  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180013327  mov     rcx, rbx
0x18001332a  add     rsp, 20h
0x18001332e  pop     rbx
0x18001332f  jmp     ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
```
