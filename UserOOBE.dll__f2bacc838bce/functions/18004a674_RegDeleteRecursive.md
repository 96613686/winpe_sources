# RegDeleteRecursive

- ea: `0x18004a674`
- end: `0x18004a722`
- name: `RegDeleteRecursive`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004afa8`

## callees

- `0x18004a674`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a6fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a70f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a6fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a70f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004a6c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18004a6c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a6b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a6b3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004a6f1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18004a6f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a6d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a6d3`

## pseudocode

```c
_BOOL8 __fastcall RegDeleteRecursive(__int64 a1, const WCHAR *a2)
{
  LSTATUS v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x2000000u, &hKey);
    if ( !v3 )
    {
      v3 = RegDeleteTreeW(hKey, 0);
      v4 = RegCloseKey(hKey);
      if ( !v3 )
      {
        if ( !v4 )
          v4 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0);
        v3 = v4;
      }
    }
    SetLastError(v3);
    return v3 == 0;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18004a674  mov     r11, rsp
0x18004a677  mov     [r11+10h], rbx
0x18004a67b  mov     [r11+8], rcx
0x18004a67f  push    rdi
0x18004a680  sub     rsp, 30h
0x18004a684  mov     qword ptr [r11+8], 0
0x18004a68c  mov     rdi, rdx
0x18004a68f  test    rdx, rdx
0x18004a692  jz      short loc_18004A70A
0x18004a694  xor     eax, eax
0x18004a696  cmp     ax, [rdx]
0x18004a699  jz      short loc_18004A70A
0x18004a69b  lea     rax, [r11+8]
0x18004a69f  mov     r9d, 2000000h; samDesired
0x18004a6a5  xor     r8d, r8d; ulOptions
0x18004a6a8  mov     [r11-18h], rax
0x18004a6ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a6b3  call    cs:__imp_RegOpenKeyExW
0x18004a6b9  mov     ebx, eax
0x18004a6bb  test    eax, eax
0x18004a6bd  jnz     short loc_18004A6F9
0x18004a6bf  mov     rcx, [rsp+38h+hKey]; hKey
0x18004a6c4  xor     edx, edx; lpSubKey
0x18004a6c6  call    cs:__imp_RegDeleteTreeW
0x18004a6cc  mov     rcx, [rsp+38h+hKey]; hKey
0x18004a6d1  mov     ebx, eax
0x18004a6d3  call    cs:__imp_RegCloseKey
0x18004a6d9  test    ebx, ebx
0x18004a6db  jnz     short loc_18004A6F9
0x18004a6dd  test    eax, eax
0x18004a6df  jnz     short loc_18004A6F7
0x18004a6e1  xor     r9d, r9d; Reserved
0x18004a6e4  xor     r8d, r8d; samDesired
0x18004a6e7  mov     rdx, rdi; lpSubKey
0x18004a6ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a6f1  call    cs:__imp_RegDeleteKeyExW
0x18004a6f7  mov     ebx, eax
0x18004a6f9  mov     ecx, ebx; dwErrCode
0x18004a6fb  call    cs:__imp_SetLastError
0x18004a701  xor     eax, eax
0x18004a703  test    ebx, ebx
0x18004a705  setz    al
0x18004a708  jmp     short loc_18004A717
0x18004a70a  mov     ecx, 57h ; 'W'; dwErrCode
0x18004a70f  call    cs:__imp_SetLastError
0x18004a715  xor     eax, eax
0x18004a717  mov     rbx, [rsp+38h+arg_8]
0x18004a71c  add     rsp, 30h
0x18004a720  pop     rdi
0x18004a721  retn
```
