# WPDLibSetRegistryValue

- ea: `0x180007160`
- end: `0x180007221`
- name: `WPDLibSetRegistryValue`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002c70`
- `0x1800069d0`
- `0x180008128`
- `0x18000f390`
- `0x18000fc24`
- `0x1800106e0`
- `0x180010f60`

## callees

- `0x180007160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800071dd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800071d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000720e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800071d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000720e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071a4`

## pseudocode

```c
LSTATUS __fastcall WPDLibSetRegistryValue(
        HKEY a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  LSTATUS result; // eax
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( a1 )
  {
    if ( !a3 )
    {
      hKey = a1;
      return RegSetValueExW(a1, a4, 0, dwType, lpData, cbData);
    }
    return 87;
  }
  if ( !a3 )
    return 87;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x2001Fu, &hKey);
  if ( !result )
  {
    v9 = RegSetValueExW(hKey, a4, 0, dwType, lpData, cbData);
    RegCloseKey(hKey);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180007160  mov     [rsp+hKey], rdx
0x180007165  push    rbx
0x180007166  sub     rsp, 30h
0x18000716a  mov     [rsp+38h+hKey], 0
0x180007173  mov     rbx, r9
0x180007176  mov     rax, r8
0x180007179  test    rcx, rcx
0x18000717c  jnz     short loc_1800071E7
0x18000717e  test    rax, rax
0x180007181  jz      loc_180007216
0x180007187  lea     rcx, [rsp+38h+hKey]
0x18000718c  mov     r9d, 2001Fh; samDesired
0x180007192  mov     [rsp+38h+phkResult], rcx; phkResult
0x180007197  xor     r8d, r8d; ulOptions
0x18000719a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800071a1  mov     rdx, rax; lpSubKey
0x1800071a4  call    cs:__imp_RegOpenKeyExW
0x1800071aa  test    eax, eax
0x1800071ac  jnz     short loc_18000721B
0x1800071ae  mov     eax, [rsp+38h+arg_30]
0x1800071b2  xor     r8d, r8d; Reserved
0x1800071b5  mov     r9d, [rsp+38h+dwType]; dwType
0x1800071ba  mov     rdx, rbx; lpValueName
0x1800071bd  mov     rcx, [rsp+38h+hKey]; hKey
0x1800071c2  mov     [rsp+38h+cbData], eax; cbData
0x1800071c6  mov     rax, [rsp+38h+lpData]
0x1800071cb  mov     [rsp+38h+phkResult], rax; lpData
0x1800071d0  call    cs:__imp_RegSetValueExW
0x1800071d6  mov     rcx, [rsp+38h+hKey]; hKey
0x1800071db  mov     ebx, eax
0x1800071dd  call    cs:__imp_RegCloseKey
0x1800071e3  mov     eax, ebx
0x1800071e5  jmp     short loc_18000721B
0x1800071e7  test    rax, rax
0x1800071ea  jnz     short loc_180007216
0x1800071ec  mov     eax, [rsp+38h+arg_30]
0x1800071f0  xor     r8d, r8d; Reserved
0x1800071f3  mov     r9d, [rsp+38h+dwType]; dwType
0x1800071f8  mov     rdx, rbx; lpValueName
0x1800071fb  mov     [rsp+38h+cbData], eax; cbData
0x1800071ff  mov     rax, [rsp+38h+lpData]
0x180007204  mov     [rsp+38h+phkResult], rax; lpData
0x180007209  mov     [rsp+38h+hKey], rcx
0x18000720e  call    cs:__imp_RegSetValueExW
0x180007214  jmp     short loc_18000721B
0x180007216  mov     eax, 57h ; 'W'
0x18000721b  add     rsp, 30h
0x18000721f  pop     rbx
0x180007220  retn
```
