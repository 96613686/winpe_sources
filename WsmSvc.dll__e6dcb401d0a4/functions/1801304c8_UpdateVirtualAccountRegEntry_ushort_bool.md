# UpdateVirtualAccountRegEntry(ushort *,bool)

- ea: `0x1801304c8`
- end: `0x1801305b5`
- name: `?UpdateVirtualAccountRegEntry@@YAJPEAG_N@Z`
- size: `237`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18012fbc4`
- `0x18012ff68`

## callees

- `0x1801304c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180130522`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013056d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180130522`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013056d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013057c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013059d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013057c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013059d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18013058d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18013058d`

## pseudocode

```c
__int64 __fastcall UpdateVirtualAccountRegEntry(LPCWSTR lpSubKey, char a2)
{
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\LiveVirtualAccounts",
         0,
         0,
         0,
         0x109u,
         0,
         &hKey,
         0) )
  {
    goto LABEL_2;
  }
  v4 = 0;
  if ( a2 )
  {
    RegDeleteKeyExW(hKey, lpSubKey, 0x100u, 0);
  }
  else
  {
    phkResult = 0;
    if ( RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x100u, 0, &phkResult, 0) )
    {
LABEL_2:
      v4 = -2147023537;
      goto LABEL_7;
    }
    RegCloseKey(phkResult);
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1801304c8  mov     r11, rsp
0x1801304cb  mov     [r11+8], rbx
0x1801304cf  mov     [r11+10h], rsi
0x1801304d3  push    rdi
0x1801304d4  sub     rsp, 50h
0x1801304d8  mov     qword ptr [r11-18h], 0
0x1801304e0  lea     rax, [r11+18h]
0x1801304e4  mov     [r11-20h], rax
0x1801304e8  mov     sil, dl
0x1801304eb  mov     qword ptr [r11-28h], 0
0x1801304f3  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801304fa  mov     rdi, rcx
0x1801304fd  mov     [rsp+58h+samDesired], 109h; samDesired
0x180130505  xor     r9d, r9d; lpClass
0x180130508  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180130510  xor     r8d, r8d; Reserved
0x180130513  mov     qword ptr [r11+18h], 0
0x18013051b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180130522  call    cs:__imp_RegCreateKeyExW
0x180130528  test    eax, eax
0x18013052a  jz      short loc_180130533
0x18013052c  mov     ebx, 8007054Fh
0x180130531  jmp     short loc_180130593
0x180130533  mov     rcx, [rsp+58h+hKey]; hKey
0x180130538  xor     ebx, ebx
0x18013053a  mov     rdx, rdi; lpSubKey
0x18013053d  test    sil, sil
0x180130540  jnz     short loc_180130584
0x180130542  mov     [rsp+58h+lpdwDisposition], rbx; lpdwDisposition
0x180130547  lea     rax, [rsp+58h+arg_18]
0x18013054c  mov     [rsp+58h+phkResult], rax; phkResult
0x180130551  xor     r9d, r9d; lpClass
0x180130554  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180130559  xor     r8d, r8d; Reserved
0x18013055c  mov     [rsp+58h+samDesired], 100h; samDesired
0x180130564  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x180130568  mov     [rsp+58h+arg_18], rbx
0x18013056d  call    cs:__imp_RegCreateKeyExW
0x180130573  test    eax, eax
0x180130575  jnz     short loc_18013052C
0x180130577  mov     rcx, [rsp+58h+arg_18]; hKey
0x18013057c  call    cs:__imp_RegCloseKey
0x180130582  jmp     short loc_180130593
0x180130584  xor     r9d, r9d; Reserved
0x180130587  mov     r8d, 100h; samDesired
0x18013058d  call    cs:__imp_RegDeleteKeyExW
0x180130593  mov     rcx, [rsp+58h+hKey]; hKey
0x180130598  test    rcx, rcx
0x18013059b  jz      short loc_1801305A3
0x18013059d  call    cs:__imp_RegCloseKey
0x1801305a3  mov     rsi, [rsp+58h+arg_8]
0x1801305a8  mov     eax, ebx
0x1801305aa  mov     rbx, [rsp+58h+arg_0]
0x1801305af  add     rsp, 50h
0x1801305b3  pop     rdi
0x1801305b4  retn
```
