# CRegistry::myRegDeleteKey(HKEY__ *,ushort const *)

- ea: `0x140013c20`
- end: `0x140013c36`
- name: `?myRegDeleteKey@CRegistry@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `22`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140013c2f`

## pseudocode

```c
LSTATUS __fastcall CRegistry::myRegDeleteKey(CRegistry *this, HKEY a2, const unsigned __int16 *a3)
{
  return RegDeleteKeyExW(a2, a3, 0, 0);
}

```

## disassembly

```asm
0x140013c20  mov     rax, r8
0x140013c23  mov     rcx, rdx
0x140013c26  mov     rdx, rax
0x140013c29  xor     r9d, r9d
0x140013c2c  xor     r8d, r8d
0x140013c2f  jmp     cs:__imp_RegDeleteKeyExW
```
