# Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)

- ea: `0x18000d6a0`
- end: `0x18000d6fd`
- name: `?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z`
- size: `93`
- prototype: `LSTATUS __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)`
- caller_count: `67`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c94`
- `0x1800040dc`
- `0x1800095d0`
- `0x18000d180`
- `0x1800110cc`
- `0x180011dd0`
- `0x1800137e0`
- `0x1800143e4`
- `0x18001487c`
- `0x180015540`
- `0x1800156d0`
- `0x180015be8`
- `0x180016924`
- `0x180016ba8`
- `0x180017198`
- `0x180017330`
- `0x1800175c4`
- `0x1800178e8`
- `0x180017f80`
- `0x180018130`
- `0x180018698`
- `0x1800187d8`
- `0x180019604`
- `0x180020544`
- `0x180020794`
- `0x1800210c8`
- `0x180021884`
- `0x180021b64`
- `0x180021c50`
- `0x1800264d8`
- `0x180026d44`
- `0x1800277a8`
- `0x180027b58`
- `0x180027d54`
- `0x1800280a8`
- `0x18002a9f0`
- `0x18002ac4c`
- `0x18002ad3c`
- `0x18002ae38`
- `0x18002e8c0`
- `0x18002f2d0`
- `0x18002f4b0`
- `0x18002f9e0`
- `0x18002fdf0`
- `0x180030540`
- `0x180031828`
- `0x1800318d4`
- `0x180032000`
- `0x18003254c`
- `0x1800334f4`

## callees

- `0x18000d6a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d6f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d6f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d6da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d6da`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::Open(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)
{
  HKEY v6; // rcx
  LSTATUS result; // eax

  v6 = *phkResult;
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v6);
  *phkResult = 0;
  result = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000d6a0  push    rbx
0x18000d6a2  push    rbp
0x18000d6a3  push    rsi
0x18000d6a4  push    rdi
0x18000d6a5  sub     rsp, 38h
0x18000d6a9  mov     rbx, rcx
0x18000d6ac  mov     edi, r9d
0x18000d6af  mov     rcx, [rcx]; hKey
0x18000d6b2  mov     rsi, r8
0x18000d6b5  mov     rbp, rdx
0x18000d6b8  lea     rax, [rcx-1]
0x18000d6bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d6c0  jbe     short loc_18000D6F5
0x18000d6c2  mov     r9d, edi; samDesired
0x18000d6c5  mov     qword ptr [rbx], 0
0x18000d6cc  xor     r8d, r8d; ulOptions
0x18000d6cf  mov     [rsp+58h+phkResult], rbx; phkResult
0x18000d6d4  mov     rdx, rsi; lpSubKey
0x18000d6d7  mov     rcx, rbp; hKey
0x18000d6da  call    cs:__imp_RegOpenKeyExW
0x18000d6e0  test    eax, eax
0x18000d6e2  jle     short loc_18000D6EC
0x18000d6e4  movzx   eax, ax
0x18000d6e7  or      eax, 80070000h
0x18000d6ec  add     rsp, 38h
0x18000d6f0  pop     rdi
0x18000d6f1  pop     rsi
0x18000d6f2  pop     rbp
0x18000d6f3  pop     rbx
0x18000d6f4  retn
0x18000d6f5  call    cs:__imp_RegCloseKey
0x18000d6fb  jmp     short loc_18000D6C2
```
