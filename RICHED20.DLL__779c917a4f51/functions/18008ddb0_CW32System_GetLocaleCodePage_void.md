# CW32System::GetLocaleCodePage(void)

- ea: `0x18008ddb0`
- end: `0x18008ddc5`
- name: `?GetLocaleCodePage@CW32System@@SAIXZ`
- size: `21`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18006d820`
- `0x18008b968`

## callees

- `0x180031cbc`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18008ddb4`
- `KERNEL32!GetThreadLocale` at `0x18008ddb4`

## pseudocode

```c
unsigned int CW32System::GetLocaleCodePage(void)
{
  unsigned __int16 ThreadLocale; // ax

  ThreadLocale = GetThreadLocale();
  return CW32System::ConvertLanguageIDtoCodePage(ThreadLocale);
}

```

## disassembly

```asm
0x18008ddb0  sub     rsp, 28h
0x18008ddb4  call    cs:__imp_GetThreadLocale
0x18008ddba  mov     ecx, eax; unsigned __int16
0x18008ddbc  add     rsp, 28h
0x18008ddc0  jmp     ?ConvertLanguageIDtoCodePage@CW32System@@SAIG@Z; CW32System::ConvertLanguageIDtoCodePage(ushort)
```
