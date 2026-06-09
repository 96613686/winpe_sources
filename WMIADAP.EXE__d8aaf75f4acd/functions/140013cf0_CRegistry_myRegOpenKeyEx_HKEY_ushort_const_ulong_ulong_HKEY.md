# CRegistry::myRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x140013cf0`
- end: `0x140013d18`
- name: `?myRegOpenKeyEx@CRegistry@@AEAAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z`
- size: `40`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, DWORD, REGSAM, HKEY *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013d11`

## pseudocode

```c
LSTATUS __fastcall CRegistry::myRegOpenKeyEx(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        REGSAM a5,
        HKEY *a6)
{
  return RegOpenKeyExW(a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x140013cf0  push    rbx
0x140013cf2  mov     rax, [rsp+8+arg_28]
0x140013cf7  mov     r10d, r9d
0x140013cfa  mov     r9d, [rsp+8+arg_20]
0x140013cff  mov     r11, r8
0x140013d02  mov     rcx, rdx
0x140013d05  mov     qword ptr [rsp+8+arg_20], rax
0x140013d0a  mov     r8d, r10d
0x140013d0d  mov     rdx, r11
0x140013d10  pop     rbx
0x140013d11  jmp     cs:__imp_RegOpenKeyExW
```
