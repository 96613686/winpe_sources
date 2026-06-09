# RegSetBinEx

- ea: `0x18004aa44`
- end: `0x18004ab28`
- name: `RegSetBinEx`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180047e1c`
- `0x18004ab30`

## callees

- `0x18004aa44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ab03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ab17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ab03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ab17`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aaa7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aaa7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004aad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004aaf9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004aad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004aaf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004aade`

## pseudocode

```c
_BOOL8 __fastcall RegSetBinEx(HKEY a1, const WCHAR *a2, const WCHAR *a3, DWORD a4, BYTE *lpData, DWORD cbData)
{
  BYTE *v8; // rdi
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  DWORD v12; // [rsp+90h] [rbp+8h] BYREF

  if ( a1 && (v8 = lpData) != 0 )
  {
    if ( a2 )
    {
      hKey = 0;
      v12 = 0;
      v9 = RegCreateKeyExW(a1, a2, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &v12);
      if ( !v9 )
      {
        v9 = RegSetValueExW(hKey, a3, 0, a4, v8, cbData);
        RegCloseKey(hKey);
      }
    }
    else
    {
      v9 = RegSetValueExW(a1, a3, 0, a4, lpData, cbData);
    }
    SetLastError(v9);
    return v9 == 0;
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
0x18004aa44  mov     r11, rsp
0x18004aa47  push    rbx
0x18004aa48  push    rbp
0x18004aa49  push    rsi
0x18004aa4a  push    rdi
0x18004aa4b  sub     rsp, 68h
0x18004aa4f  mov     esi, r9d
0x18004aa52  mov     rbp, r8
0x18004aa55  test    rcx, rcx
0x18004aa58  jz      loc_18004AB12
0x18004aa5e  mov     rdi, [rsp+88h+lpData]
0x18004aa66  test    rdi, rdi
0x18004aa69  jz      loc_18004AB12
0x18004aa6f  xor     r8d, r8d; Reserved
0x18004aa72  test    rdx, rdx
0x18004aa75  jz      short loc_18004AAE6
0x18004aa77  lea     rax, [r11+8]
0x18004aa7b  mov     [r11-38h], r8
0x18004aa7f  mov     [r11-48h], rax
0x18004aa83  lea     r9, Class; lpClass
0x18004aa8a  lea     rax, [r11-38h]
0x18004aa8e  mov     [r11+8], r8d
0x18004aa92  mov     [r11-50h], rax
0x18004aa96  mov     [r11-58h], r8
0x18004aa9a  mov     [rsp+88h+samDesired], 20006h; samDesired
0x18004aaa2  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x18004aaa7  call    cs:__imp_RegCreateKeyExW
0x18004aaad  mov     ebx, eax
0x18004aaaf  test    eax, eax
0x18004aab1  jnz     short loc_18004AB01
0x18004aab3  mov     eax, [rsp+88h+cbData]
0x18004aaba  mov     r9d, esi; dwType
0x18004aabd  mov     rcx, [rsp+88h+hKey]; hKey
0x18004aac2  xor     r8d, r8d; Reserved
0x18004aac5  mov     [rsp+88h+samDesired], eax; cbData
0x18004aac9  mov     rdx, rbp; lpValueName
0x18004aacc  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x18004aad1  call    cs:__imp_RegSetValueExW
0x18004aad7  mov     rcx, [rsp+88h+hKey]; hKey
0x18004aadc  mov     ebx, eax
0x18004aade  call    cs:__imp_RegCloseKey
0x18004aae4  jmp     short loc_18004AB01
0x18004aae6  mov     eax, [rsp+88h+cbData]
0x18004aaed  mov     rdx, rbp; lpValueName
0x18004aaf0  mov     [rsp+88h+samDesired], eax; cbData
0x18004aaf4  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x18004aaf9  call    cs:__imp_RegSetValueExW
0x18004aaff  mov     ebx, eax
0x18004ab01  mov     ecx, ebx; dwErrCode
0x18004ab03  call    cs:__imp_SetLastError
0x18004ab09  xor     eax, eax
0x18004ab0b  test    ebx, ebx
0x18004ab0d  setz    al
0x18004ab10  jmp     short loc_18004AB1F
0x18004ab12  mov     ecx, 57h ; 'W'; dwErrCode
0x18004ab17  call    cs:__imp_SetLastError
0x18004ab1d  xor     eax, eax
0x18004ab1f  add     rsp, 68h
0x18004ab23  pop     rdi
0x18004ab24  pop     rsi
0x18004ab25  pop     rbp
0x18004ab26  pop     rbx
0x18004ab27  retn
```
