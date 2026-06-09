# _CRYPT_XML_HANDLE_LOCK

- ea: `0x180015160`
- end: `0x18001516b`
- name: `_CRYPT_XML_HANDLE_LOCK`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015164`

## pseudocode

```c
void __fastcall CRYPT_XML_HANDLE_LOCK(__int64 a1)
{
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x180015160  add     rcx, 8
0x180015164  jmp     cs:__imp_EnterCriticalSection
```
