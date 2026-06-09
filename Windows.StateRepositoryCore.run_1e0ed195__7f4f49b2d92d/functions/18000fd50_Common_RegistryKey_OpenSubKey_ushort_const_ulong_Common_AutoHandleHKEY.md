# Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)

- ea: `0x18000fd50`
- end: `0x18000fda2`
- name: `?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z`
- size: `82`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, unsigned int, struct Common::AutoHandleHKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fda8`

## callees

- `0x18000be00`
- `0x18000fd50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd86`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::OpenSubKey(HKEY *this, const unsigned __int16 *a2, __int64 a3, HKEY *a4)
{
  REGSAM v6; // edi
  LSTATUS result; // eax

  v6 = a3;
  Common::AutoHandleCloseHKEY<HKEY__ *>(*a4, a2, a3);
  *a4 = 0;
  result = RegOpenKeyExW(*this, a2, 0, v6, a4);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fd50  push    rbx
0x18000fd52  push    rsi
0x18000fd53  push    rdi
0x18000fd54  push    r14
0x18000fd56  sub     rsp, 38h
0x18000fd5a  mov     r14, rcx
0x18000fd5d  mov     rbx, r9
0x18000fd60  mov     rcx, [r9]
0x18000fd63  mov     edi, r8d
0x18000fd66  mov     rsi, rdx
0x18000fd69  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000fd6e  mov     qword ptr [rbx], 0
0x18000fd75  mov     r9d, edi; samDesired
0x18000fd78  mov     rcx, [r14]; hKey
0x18000fd7b  xor     r8d, r8d; ulOptions
0x18000fd7e  mov     rdx, rsi; lpSubKey
0x18000fd81  mov     [rsp+58h+phkResult], rbx; phkResult
0x18000fd86  call    cs:__imp_RegOpenKeyExW
0x18000fd8c  test    eax, eax
0x18000fd8e  jle     short loc_18000FD98
0x18000fd90  movzx   eax, ax
0x18000fd93  or      eax, 80070000h
0x18000fd98  add     rsp, 38h
0x18000fd9c  pop     r14
0x18000fd9e  pop     rdi
0x18000fd9f  pop     rsi
0x18000fda0  pop     rbx
0x18000fda1  retn
```
