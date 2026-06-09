# Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)

- ea: `0x18000ce40`
- end: `0x18000ce9f`
- name: `?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z`
- size: `95`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, unsigned int, struct Common::AutoHandleHKEY *)`
- caller_count: `52`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c94`
- `0x1800040dc`
- `0x1800095d0`
- `0x18000b5cc`
- `0x180012dcc`
- `0x180014240`
- `0x180014694`
- `0x180014a38`
- `0x180017330`
- `0x18001f2cc`
- `0x180020794`
- `0x180021c50`
- `0x180028528`
- `0x18002886c`
- `0x180028a5c`
- `0x180028e94`
- `0x18002919c`
- `0x180029300`
- `0x1800293b8`
- `0x18002977c`
- `0x180029940`
- `0x18002a21c`
- `0x18002a9f0`
- `0x18002b018`
- `0x18002bbf0`
- `0x180030d98`
- `0x1800316b8`
- `0x18003254c`
- `0x1800337b8`
- `0x1800348b8`
- `0x180038560`
- `0x180038a80`
- `0x180038c28`
- `0x180038d8c`
- `0x180038e58`
- `0x180038f20`
- `0x18003906c`
- `0x18003925c`
- `0x180039328`
- `0x180039434`
- `0x180039624`
- `0x1800396d4`
- `0x1800398a8`
- `0x1800399a0`
- `0x18003a274`
- `0x18003a884`
- `0x18003adb0`
- `0x18003daf4`
- `0x18003dd38`
- `0x18003e29c`

## callees

- `0x18000ce40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ce97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce7b`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::OpenSubKey(HKEY *this, const unsigned __int16 *a2, REGSAM a3, HKEY *a4)
{
  LSTATUS result; // eax

  if ( (unsigned __int64)*a4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(*a4);
  *a4 = 0;
  result = RegOpenKeyExW(*this, a2, 0, a3, a4);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000ce40  push    rbx
0x18000ce42  push    rsi
0x18000ce43  push    rdi
0x18000ce44  push    r14
0x18000ce46  sub     rsp, 38h
0x18000ce4a  mov     r14, rcx
0x18000ce4d  mov     rbx, r9
0x18000ce50  mov     rcx, [r9]; hKey
0x18000ce53  mov     edi, r8d
0x18000ce56  mov     rsi, rdx
0x18000ce59  lea     rax, [rcx-1]
0x18000ce5d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ce61  jbe     short loc_18000CE97
0x18000ce63  mov     qword ptr [rbx], 0
0x18000ce6a  mov     r9d, edi; samDesired
0x18000ce6d  mov     rcx, [r14]; hKey
0x18000ce70  xor     r8d, r8d; ulOptions
0x18000ce73  mov     rdx, rsi; lpSubKey
0x18000ce76  mov     [rsp+58h+phkResult], rbx; phkResult
0x18000ce7b  call    cs:__imp_RegOpenKeyExW
0x18000ce81  test    eax, eax
0x18000ce83  jle     short loc_18000CE8D
0x18000ce85  movzx   eax, ax
0x18000ce88  or      eax, 80070000h
0x18000ce8d  add     rsp, 38h
0x18000ce91  pop     r14
0x18000ce93  pop     rdi
0x18000ce94  pop     rsi
0x18000ce95  pop     rbx
0x18000ce96  retn
0x18000ce97  call    cs:__imp_RegCloseKey
0x18000ce9d  jmp     short loc_18000CE63
```
