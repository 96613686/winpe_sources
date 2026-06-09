# CExtensionStateManager::_SaveExtensionState(EXTENSION_STATE const *)

- ea: `0x1800423c4`
- end: `0x1800424d2`
- name: `?_SaveExtensionState@CExtensionStateManager@@AEAAJPEBUEXTENSION_STATE@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CExtensionStateManager *__hidden this, const struct EXTENSION_STATE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800630d0`
- `0x180065d20`
- `0x180066e50`
- `0x180067140`

## callees

- `0x1800423c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004241f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004241f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800424bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800424bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180042464`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800424a5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180042464`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800424a5`

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
0x1800423c4  mov     [rsp+arg_8], rbx
0x1800423c9  push    rdi
0x1800423ca  sub     rsp, 50h
0x1800423ce  mov     rcx, [rcx+10h]; hKey
0x1800423d2  mov     rdi, rdx
0x1800423d5  test    rcx, rcx
0x1800423d8  jnz     short loc_1800423E4
0x1800423da  mov     ebx, 8000FFFFh
0x1800423df  jmp     loc_1800424C5
0x1800423e4  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800423ed  lea     rax, [rsp+58h+hKey]
0x1800423f2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800423f7  xor     r9d, r9d; lpClass
0x1800423fa  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180042403  xor     r8d, r8d; Reserved
0x180042406  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18004240e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180042416  mov     [rsp+58h+hKey], 0
0x18004241f  call    cs:__imp_RegCreateKeyExW
0x180042425  mov     ebx, eax
0x180042427  test    eax, eax
0x180042429  jle     short loc_180042434
0x18004242b  movzx   ebx, ax
0x18004242e  or      ebx, 80070000h
0x180042434  test    ebx, ebx
0x180042436  js      loc_1800424C5
0x18004243c  mov     rcx, [rsp+58h+hKey]; hKey
0x180042441  lea     rax, [rdi+208h]
0x180042448  mov     [rsp+58h+samDesired], 4; cbData
0x180042450  lea     r8, aState; "State"
0x180042457  mov     r9d, 4; dwType
0x18004245d  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180042462  xor     edx, edx; lpSubKey
0x180042464  call    cs:__imp_RegSetKeyValueW
0x18004246a  mov     ebx, eax
0x18004246c  test    eax, eax
0x18004246e  jle     short loc_180042479
0x180042470  movzx   ebx, ax
0x180042473  or      ebx, 80070000h
0x180042479  test    ebx, ebx
0x18004247b  js      short loc_1800424BA
0x18004247d  mov     rcx, [rsp+58h+hKey]; hKey
0x180042482  lea     rax, [rdi+20Ch]
0x180042489  mov     [rsp+58h+samDesired], 4; cbData
0x180042491  lea     r8, aPinnedorder; "PinnedOrder"
0x180042498  mov     r9d, 4; dwType
0x18004249e  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800424a3  xor     edx, edx; lpSubKey
0x1800424a5  call    cs:__imp_RegSetKeyValueW
0x1800424ab  mov     ebx, eax
0x1800424ad  test    eax, eax
0x1800424af  jle     short loc_1800424BA
0x1800424b1  movzx   ebx, ax
0x1800424b4  or      ebx, 80070000h
0x1800424ba  mov     rcx, [rsp+58h+hKey]; hKey
0x1800424bf  call    cs:__imp_RegCloseKey
0x1800424c5  mov     eax, ebx
0x1800424c7  mov     rbx, [rsp+58h+arg_8]
0x1800424cc  add     rsp, 50h
0x1800424d0  pop     rdi
0x1800424d1  retn
```
