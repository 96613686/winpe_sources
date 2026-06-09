# WinApiLite::GetThreadPreferredUILanguages(ulong,ulong *,ushort *,ulong *)

- ea: `0x180017210`
- end: `0x18001722a`
- name: `?GetThreadPreferredUILanguages@WinApiLite@@UEAAHKPEAKPEAG0@Z`
- size: `26`
- prototype: `BOOL __fastcall(WinApiLite *this, DWORD, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180017223`

## pseudocode

```c
BOOL __fastcall WinApiLite::GetThreadPreferredUILanguages(
        WinApiLite *this,
        DWORD a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  return GetThreadPreferredUILanguages(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180017210  mov     rax, r9
0x180017213  mov     r10, r8
0x180017216  mov     r9, [rsp+arg_20]
0x18001721b  mov     ecx, edx
0x18001721d  mov     r8, rax
0x180017220  mov     rdx, r10
0x180017223  jmp     cs:__imp_GetThreadPreferredUILanguages
```
