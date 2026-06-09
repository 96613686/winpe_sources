# RegDelete

- ea: `0x140028afc`
- end: `0x140028b8f`
- name: `RegDelete`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1400570e0`

## callees

- `0x140028afc`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x140028b4f`
- `ADVAPI32!RegDeleteValueW` at `0x140028b4f`
- `ADVAPI32!RegOpenKeyExW` at `0x140028b31`
- `ADVAPI32!RegOpenKeyExW` at `0x140028b31`
- `ADVAPI32!RegCloseKey` at `0x140028b62`
- `ADVAPI32!RegCloseKey` at `0x140028b62`
- `KERNEL32!SetLastError` at `0x140028b70`
- `KERNEL32!SetLastError` at `0x140028b70`

## pseudocode

```c
__int64 RegDelete()
{
  unsigned int v0; // ebx
  LSTATUS v1; // edi
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\SetupPlatform", 0, 0x20006u, &hKey);
  if ( !v1 )
  {
    v1 = RegDeleteValueW(hKey, L"SuspendedData");
    RegCloseKey(hKey);
  }
  SetLastError(v1);
  LOBYTE(v0) = v1 == 0;
  return v0;
}

```

## disassembly

```asm
0x140028afc  mov     r11, rsp
0x140028aff  mov     [r11+8], rbx
0x140028b03  mov     [r11+18h], r8
0x140028b07  push    rdi
0x140028b08  sub     rsp, 30h
0x140028b0c  lea     rax, [r11+18h]
0x140028b10  xor     ebx, ebx
0x140028b12  mov     r9d, 20006h; samDesired
0x140028b18  mov     [r11+18h], rbx
0x140028b1c  xor     r8d, r8d; ulOptions
0x140028b1f  mov     [r11-18h], rax
0x140028b23  lea     rdx, aSystemSetupSet; "SYSTEM\\Setup\\SetupPlatform"
0x140028b2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140028b31  call    cs:__imp_RegOpenKeyExW
0x140028b38  nop     dword ptr [rax+rax+00h]
0x140028b3d  mov     edi, eax
0x140028b3f  test    eax, eax
0x140028b41  jnz     short loc_140028B6E
0x140028b43  mov     rcx, [rsp+38h+hKey]; hKey
0x140028b48  lea     rdx, aSuspendeddata; "SuspendedData"
0x140028b4f  call    cs:__imp_RegDeleteValueW
0x140028b56  nop     dword ptr [rax+rax+00h]
0x140028b5b  mov     rcx, [rsp+38h+hKey]; hKey
0x140028b60  mov     edi, eax
0x140028b62  call    cs:__imp_RegCloseKey
0x140028b69  nop     dword ptr [rax+rax+00h]
0x140028b6e  mov     ecx, edi; dwErrCode
0x140028b70  call    cs:__imp_SetLastError
0x140028b77  nop     dword ptr [rax+rax+00h]
0x140028b7c  test    edi, edi
0x140028b7e  setz    bl
0x140028b81  mov     eax, ebx
0x140028b83  mov     rbx, [rsp+38h+arg_0]
0x140028b88  add     rsp, 30h
0x140028b8c  pop     rdi
0x140028b8d  retn
```
