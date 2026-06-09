# CExtensionStateManager::_SaveExtensionState(EXTENSION_STATE const *)

- ea: `0x18004b1cc`
- end: `0x18004b2da`
- name: `?_SaveExtensionState@CExtensionStateManager@@AEAAJPEBUEXTENSION_STATE@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CExtensionStateManager *__hidden this, const struct EXTENSION_STATE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800442b0`
- `0x180047160`
- `0x180048150`
- `0x180048440`

## callees

- `0x18004b1cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b227`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b2c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b2c7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004b26c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004b2ad`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004b26c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004b2ad`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_SaveExtensionState(CExtensionStateManager *this, const WCHAR *a2)
{
  HKEY v2; // rcx
  signed int v4; // ebx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
  {
    hKey = 0;
    v5 = RegCreateKeyExW(v2, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( v4 >= 0 )
    {
      v6 = RegSetKeyValueW(hKey, 0, L"State", 4u, a2 + 260, 4u);
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 >= 0 )
      {
        v7 = RegSetKeyValueW(hKey, 0, L"PinnedOrder", 4u, a2 + 262, 4u);
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
      }
      RegCloseKey(hKey);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004b1cc  mov     [rsp+arg_8], rbx
0x18004b1d1  push    rdi
0x18004b1d2  sub     rsp, 50h
0x18004b1d6  mov     rcx, [rcx+10h]; hKey
0x18004b1da  mov     rdi, rdx
0x18004b1dd  test    rcx, rcx
0x18004b1e0  jnz     short loc_18004B1EC
0x18004b1e2  mov     ebx, 8000FFFFh
0x18004b1e7  jmp     loc_18004B2CD
0x18004b1ec  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18004b1f5  lea     rax, [rsp+58h+hKey]
0x18004b1fa  mov     [rsp+58h+phkResult], rax; phkResult
0x18004b1ff  xor     r9d, r9d; lpClass
0x18004b202  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004b20b  xor     r8d, r8d; Reserved
0x18004b20e  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18004b216  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18004b21e  mov     [rsp+58h+hKey], 0
0x18004b227  call    cs:__imp_RegCreateKeyExW
0x18004b22d  mov     ebx, eax
0x18004b22f  test    eax, eax
0x18004b231  jle     short loc_18004B23C
0x18004b233  movzx   ebx, ax
0x18004b236  or      ebx, 80070000h
0x18004b23c  test    ebx, ebx
0x18004b23e  js      loc_18004B2CD
0x18004b244  mov     rcx, [rsp+58h+hKey]; hKey
0x18004b249  lea     rax, [rdi+208h]
0x18004b250  mov     [rsp+58h+samDesired], 4; cbData
0x18004b258  lea     r8, ValueName; "State"
0x18004b25f  mov     r9d, 4; dwType
0x18004b265  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18004b26a  xor     edx, edx; lpSubKey
0x18004b26c  call    cs:__imp_RegSetKeyValueW
0x18004b272  mov     ebx, eax
0x18004b274  test    eax, eax
0x18004b276  jle     short loc_18004B281
0x18004b278  movzx   ebx, ax
0x18004b27b  or      ebx, 80070000h
0x18004b281  test    ebx, ebx
0x18004b283  js      short loc_18004B2C2
0x18004b285  mov     rcx, [rsp+58h+hKey]; hKey
0x18004b28a  lea     rax, [rdi+20Ch]
0x18004b291  mov     [rsp+58h+samDesired], 4; cbData
0x18004b299  lea     r8, aPinnedorder; "PinnedOrder"
0x18004b2a0  mov     r9d, 4; dwType
0x18004b2a6  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18004b2ab  xor     edx, edx; lpSubKey
0x18004b2ad  call    cs:__imp_RegSetKeyValueW
0x18004b2b3  mov     ebx, eax
0x18004b2b5  test    eax, eax
0x18004b2b7  jle     short loc_18004B2C2
0x18004b2b9  movzx   ebx, ax
0x18004b2bc  or      ebx, 80070000h
0x18004b2c2  mov     rcx, [rsp+58h+hKey]; hKey
0x18004b2c7  call    cs:__imp_RegCloseKey
0x18004b2cd  mov     eax, ebx
0x18004b2cf  mov     rbx, [rsp+58h+arg_8]
0x18004b2d4  add     rsp, 50h
0x18004b2d8  pop     rdi
0x18004b2d9  retn
```
