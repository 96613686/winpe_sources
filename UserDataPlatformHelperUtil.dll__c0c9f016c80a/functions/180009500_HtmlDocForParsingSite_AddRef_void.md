# HtmlDocForParsingSite::AddRef(void)

- ea: `0x180009500`
- end: `0x18000950d`
- name: `?AddRef@HtmlDocForParsingSite@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(HtmlDocForParsingSite *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180009520`
- `0x180009530`
- `0x180009540`
- `0x180009550`

## pseudocode

```c
__int64 __fastcall HtmlDocForParsingSite::AddRef(HtmlDocForParsingSite *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 10);
}

```

## disassembly

```asm
0x180009500  mov     eax, 1
0x180009505  lock xadd [rcx+28h], eax
0x18000950a  inc     eax
0x18000950c  retn
```
