# PrintCore::ImpersonateUserRAII::~ImpersonateUserRAII(void)

- ea: `0x180022c04`
- end: `0x180022c0f`
- name: `??1ImpersonateUserRAII@PrintCore@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(PrintCore::ImpersonateUserRAII *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180029de2`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022c08`

## pseudocode

```c
void __fastcall PrintCore::ImpersonateUserRAII::~ImpersonateUserRAII(PrintCore::ImpersonateUserRAII *this)
{
  SetThreadToken(0, 0);
}

```

## disassembly

```asm
0x180022c04  xor     edx, edx
0x180022c06  xor     ecx, ecx
0x180022c08  jmp     cs:__imp_SetThreadToken
```
