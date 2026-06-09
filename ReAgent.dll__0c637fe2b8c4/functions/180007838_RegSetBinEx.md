# RegSetBinEx

- ea: `0x180007838`
- end: `0x180007925`
- name: `RegSetBinEx`
- size: `237`
- prototype: `__int64 __fastcall(int, int, int, int, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180042324`

## callees

- `0x180007838`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800078fe`
- `KERNEL32!SetLastError` at `0x180007912`
- `KERNEL32!SetLastError` at `0x1800078fe`
- `KERNEL32!SetLastError` at `0x180007912`
- `ADVAPI32!RegSetValueExW` at `0x1800078c8`
- `ADVAPI32!RegSetValueExW` at `0x1800078f4`
- `ADVAPI32!RegSetValueExW` at `0x1800078c8`
- `ADVAPI32!RegSetValueExW` at `0x1800078f4`
- `ADVAPI32!RegCreateKeyExW` at `0x18000789f`
- `ADVAPI32!RegCreateKeyExW` at `0x18000789f`
- `ADVAPI32!RegCloseKey` at `0x1800078d5`
- `ADVAPI32!RegCloseKey` at `0x1800078d5`

## pseudocode

```c
_BOOL8 __fastcall RegSetBinEx(HKEY a1, const WCHAR *a2, HKEY a3, DWORD a4, BYTE *lpData)
{
  const BYTE *v5; // rdi
  LSTATUS v6; // ebx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  DWORD v9; // [rsp+78h] [rbp+20h] BYREF

  v9 = a4;
  hKey = a3;
  if ( a1 && (v5 = lpData) != 0 )
  {
    if ( a2 )
    {
      hKey = 0;
      v9 = 0;
      v6 = RegCreateKeyExW(a1, a2, 0, (LPWSTR)&Default, 0, 0x20006u, 0, &hKey, &v9);
      if ( !v6 )
      {
        v6 = RegSetValueExW(hKey, L"BootDriverFlags", 0, 4u, v5, 4u);
        RegCloseKey(hKey);
      }
    }
    else
    {
      v6 = RegSetValueExW(a1, L"BootDriverFlags", 0, 4u, lpData, 4u);
    }
    SetLastError(v6);
    return v6 == 0;
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
0x180007838  mov     r11, rsp
0x18000783b  mov     [r11+8], rbx
0x18000783f  mov     [r11+20h], r9d
0x180007843  mov     [r11+18h], r8
0x180007847  push    rdi
0x180007848  sub     rsp, 50h
0x18000784c  test    rcx, rcx
0x18000784f  jz      loc_18000790D
0x180007855  mov     rdi, [rsp+58h+lpData]
0x18000785d  test    rdi, rdi
0x180007860  jz      loc_18000790D
0x180007866  xor     r8d, r8d; Reserved
0x180007869  test    rdx, rdx
0x18000786c  jz      short loc_1800078DD
0x18000786e  lea     rax, [r11+20h]
0x180007872  mov     [r11+18h], r8
0x180007876  mov     [r11-18h], rax
0x18000787a  lea     r9, Default; lpClass
0x180007881  lea     rax, [r11+18h]
0x180007885  mov     [rsp+58h+arg_18], r8d
0x18000788a  mov     [r11-20h], rax
0x18000788e  mov     [r11-28h], r8
0x180007892  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18000789a  mov     [rsp+58h+dwOptions], r8d; dwOptions
0x18000789f  call    cs:__imp_RegCreateKeyExW
0x1800078a5  mov     ebx, eax
0x1800078a7  test    eax, eax
0x1800078a9  jnz     short loc_1800078FC
0x1800078ab  mov     rcx, [rsp+58h+hKey]; hKey
0x1800078b0  lea     r9d, [rax+4]; dwType
0x1800078b4  mov     [rsp+58h+samDesired], r9d; cbData
0x1800078b9  lea     rdx, aBootdriverflag_0; "BootDriverFlags"
0x1800078c0  xor     r8d, r8d; Reserved
0x1800078c3  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x1800078c8  call    cs:__imp_RegSetValueExW
0x1800078ce  mov     rcx, [rsp+58h+hKey]; hKey
0x1800078d3  mov     ebx, eax
0x1800078d5  call    cs:__imp_RegCloseKey
0x1800078db  jmp     short loc_1800078FC
0x1800078dd  mov     r9d, 4; dwType
0x1800078e3  lea     rdx, aBootdriverflag_0; "BootDriverFlags"
0x1800078ea  mov     [rsp+58h+samDesired], r9d; cbData
0x1800078ef  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x1800078f4  call    cs:__imp_RegSetValueExW
0x1800078fa  mov     ebx, eax
0x1800078fc  mov     ecx, ebx; dwErrCode
0x1800078fe  call    cs:__imp_SetLastError
0x180007904  xor     eax, eax
0x180007906  test    ebx, ebx
0x180007908  setz    al
0x18000790b  jmp     short loc_18000791A
0x18000790d  mov     ecx, 57h ; 'W'; dwErrCode
0x180007912  call    cs:__imp_SetLastError
0x180007918  xor     eax, eax
0x18000791a  mov     rbx, [rsp+58h+arg_0]
0x18000791f  add     rsp, 50h
0x180007923  pop     rdi
0x180007924  retn
```
