# Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)

- ea: `0x18002c304`
- end: `0x18002c354`
- name: `?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z`
- size: `80`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800242dc`
- `0x180024ad8`
- `0x18002bca4`
- `0x18002c35c`
- `0x18002c3e8`
- `0x18002c6cc`

## callees

- `0x18000d9a4`
- `0x18002c304`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c339`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::Open(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)
{
  LSTATUS result; // eax

  Common::AutoHandleCloseHKEY<HKEY__ *>(*phkResult);
  *phkResult = 0;
  result = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002c304  push    rbx
0x18002c306  push    rbp
0x18002c307  push    rsi
0x18002c308  push    rdi
0x18002c309  sub     rsp, 38h
0x18002c30d  mov     rbx, rcx
0x18002c310  mov     edi, r9d
0x18002c313  mov     rcx, [rcx]
0x18002c316  mov     rsi, r8
0x18002c319  mov     rbp, rdx
0x18002c31c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002c321  mov     r9d, edi; samDesired
0x18002c324  mov     qword ptr [rbx], 0
0x18002c32b  xor     r8d, r8d; ulOptions
0x18002c32e  mov     [rsp+58h+phkResult], rbx; phkResult
0x18002c333  mov     rdx, rsi; lpSubKey
0x18002c336  mov     rcx, rbp; hKey
0x18002c339  call    cs:__imp_RegOpenKeyExW
0x18002c33f  test    eax, eax
0x18002c341  jle     short loc_18002C34B
0x18002c343  movzx   eax, ax
0x18002c346  or      eax, 80070000h
0x18002c34b  add     rsp, 38h
0x18002c34f  pop     rdi
0x18002c350  pop     rsi
0x18002c351  pop     rbp
0x18002c352  pop     rbx
0x18002c353  retn
```
