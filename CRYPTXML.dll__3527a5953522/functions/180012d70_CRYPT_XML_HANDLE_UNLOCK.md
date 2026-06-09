# _CRYPT_XML_HANDLE_UNLOCK

- ea: `0x180012d70`
- end: `0x180012d7b`
- name: `_CRYPT_XML_HANDLE_UNLOCK`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d74`

## pseudocode

```c
void __fastcall CRYPT_XML_HANDLE_UNLOCK(__int64 a1)
{
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
}

```

## disassembly

```asm
0x180012d70  add     rcx, 8
0x180012d74  jmp     cs:__imp_LeaveCriticalSection
```
