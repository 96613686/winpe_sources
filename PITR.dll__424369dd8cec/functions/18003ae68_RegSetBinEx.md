# RegSetBinEx

- ea: `0x18003ae68`
- end: `0x18003af4c`
- name: `RegSetBinEx`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003b040`

## callees

- `0x18003ae68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003aef5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003af1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003aef5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003af1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003af02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003aecb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003aecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af3b`

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
0x18003ae68  mov     r11, rsp
0x18003ae6b  push    rbx
0x18003ae6c  push    rbp
0x18003ae6d  push    rsi
0x18003ae6e  push    rdi
0x18003ae6f  sub     rsp, 68h
0x18003ae73  mov     esi, r9d
0x18003ae76  mov     rbp, r8
0x18003ae79  test    rcx, rcx
0x18003ae7c  jz      loc_18003AF36
0x18003ae82  mov     rdi, [rsp+88h+lpData]
0x18003ae8a  test    rdi, rdi
0x18003ae8d  jz      loc_18003AF36
0x18003ae93  xor     r8d, r8d; Reserved
0x18003ae96  test    rdx, rdx
0x18003ae99  jz      short loc_18003AF0A
0x18003ae9b  lea     rax, [r11+8]
0x18003ae9f  mov     [r11-38h], r8
0x18003aea3  mov     [r11-48h], rax
0x18003aea7  lea     r9, Class; lpClass
0x18003aeae  lea     rax, [r11-38h]
0x18003aeb2  mov     [r11+8], r8d
0x18003aeb6  mov     [r11-50h], rax
0x18003aeba  mov     [r11-58h], r8
0x18003aebe  mov     [rsp+88h+samDesired], 20006h; samDesired
0x18003aec6  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x18003aecb  call    cs:__imp_RegCreateKeyExW
0x18003aed1  mov     ebx, eax
0x18003aed3  test    eax, eax
0x18003aed5  jnz     short loc_18003AF25
0x18003aed7  mov     eax, [rsp+88h+cbData]
0x18003aede  mov     r9d, esi; dwType
0x18003aee1  mov     rcx, [rsp+88h+hKey]; hKey
0x18003aee6  xor     r8d, r8d; Reserved
0x18003aee9  mov     [rsp+88h+samDesired], eax; cbData
0x18003aeed  mov     rdx, rbp; lpValueName
0x18003aef0  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x18003aef5  call    cs:__imp_RegSetValueExW
0x18003aefb  mov     rcx, [rsp+88h+hKey]; hKey
0x18003af00  mov     ebx, eax
0x18003af02  call    cs:__imp_RegCloseKey
0x18003af08  jmp     short loc_18003AF25
0x18003af0a  mov     eax, [rsp+88h+cbData]
0x18003af11  mov     rdx, rbp; lpValueName
0x18003af14  mov     [rsp+88h+samDesired], eax; cbData
0x18003af18  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x18003af1d  call    cs:__imp_RegSetValueExW
0x18003af23  mov     ebx, eax
0x18003af25  mov     ecx, ebx; dwErrCode
0x18003af27  call    cs:__imp_SetLastError
0x18003af2d  xor     eax, eax
0x18003af2f  test    ebx, ebx
0x18003af31  setz    al
0x18003af34  jmp     short loc_18003AF43
0x18003af36  mov     ecx, 57h ; 'W'; dwErrCode
0x18003af3b  call    cs:__imp_SetLastError
0x18003af41  xor     eax, eax
0x18003af43  add     rsp, 68h
0x18003af47  pop     rdi
0x18003af48  pop     rsi
0x18003af49  pop     rbp
0x18003af4a  pop     rbx
0x18003af4b  retn
```
