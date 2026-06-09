# Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)

- ea: `0x18010968c`
- end: `0x1801096eb`
- name: `?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z`
- size: `95`
- prototype: `LSTATUS __fastcall(PHKEY phkResult, HKEY, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180105bbc`
- `0x180106008`
- `0x180109fac`

## callees

- `0x18010968c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801096ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801096ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801096a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801096a9`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::Open(PHKEY phkResult, HKEY a2, const unsigned __int16 *a3)
{
  HKEY v5; // rcx
  LSTATUS result; // eax

  v5 = *phkResult;
  if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v5);
  *phkResult = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20119u, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18010968c  mov     [rsp+arg_0], rbx
0x180109691  push    rdi
0x180109692  sub     rsp, 30h
0x180109696  mov     rbx, rcx
0x180109699  mov     rdi, r8
0x18010969c  mov     rcx, [rcx]; hKey
0x18010969f  lea     rax, [rcx-1]
0x1801096a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801096a7  ja      short loc_1801096AF
0x1801096a9  call    cs:__imp_RegCloseKey
0x1801096af  mov     r9d, 20119h; samDesired
0x1801096b5  mov     qword ptr [rbx], 0
0x1801096bc  xor     r8d, r8d; ulOptions
0x1801096bf  mov     [rsp+38h+phkResult], rbx; phkResult
0x1801096c4  mov     rdx, rdi; lpSubKey
0x1801096c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801096ce  call    cs:__imp_RegOpenKeyExW
0x1801096d4  test    eax, eax
0x1801096d6  jle     short loc_1801096E0
0x1801096d8  movzx   eax, ax
0x1801096db  or      eax, 80070000h
0x1801096e0  mov     rbx, [rsp+38h+arg_0]
0x1801096e5  add     rsp, 30h
0x1801096e9  pop     rdi
0x1801096ea  retn
```
