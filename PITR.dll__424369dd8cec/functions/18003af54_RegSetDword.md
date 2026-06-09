# RegSetDword

- ea: `0x18003af54`
- end: `0x18003b037`
- name: `RegSetDword`
- size: `227`
- prototype: `_BOOL8 __fastcall(HKEY, const WCHAR *, const WCHAR *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800170f0`
- `0x18001c130`
- `0x180021458`

## callees

- `0x18003af54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003afd6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b006`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003afd6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afe3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003afe3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003afa9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003afa9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b010`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b024`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b010`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b024`

## pseudocode

```c
_BOOL8 __fastcall RegSetDword(HKEY a1, const WCHAR *a2, const WCHAR *a3, int a4)
{
  LSTATUS v5; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  DWORD v8; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  if ( a1 )
  {
    if ( a2 )
    {
      hKey = 0;
      v8 = 0;
      v5 = RegCreateKeyExW(a1, a2, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &v8);
      if ( !v5 )
      {
        v5 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
        RegCloseKey(hKey);
      }
    }
    else
    {
      v5 = RegSetValueExW(a1, a3, 0, 4u, (const BYTE *)&Data, 4u);
    }
    SetLastError(v5);
    return v5 == 0;
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
0x18003af54  mov     r11, rsp
0x18003af57  mov     [r11+10h], rbx
0x18003af5b  mov     [r11+20h], r9d
0x18003af5f  push    rdi
0x18003af60  sub     rsp, 60h
0x18003af64  mov     rdi, r8
0x18003af67  test    rcx, rcx
0x18003af6a  jz      loc_18003B01F
0x18003af70  xor     r8d, r8d; Reserved
0x18003af73  test    rdx, rdx
0x18003af76  jz      short loc_18003AFEB
0x18003af78  lea     rax, [r11+8]
0x18003af7c  mov     [r11-18h], r8
0x18003af80  mov     [r11-28h], rax
0x18003af84  lea     r9, Class; lpClass
0x18003af8b  lea     rax, [r11-18h]
0x18003af8f  mov     [rsp+68h+arg_0], r8d
0x18003af94  mov     [r11-30h], rax
0x18003af98  mov     [r11-38h], r8
0x18003af9c  mov     [rsp+68h+samDesired], 20006h; samDesired
0x18003afa4  mov     [rsp+68h+dwOptions], r8d; dwOptions
0x18003afa9  call    cs:__imp_RegCreateKeyExW
0x18003afaf  mov     ebx, eax
0x18003afb1  test    eax, eax
0x18003afb3  jnz     short loc_18003B00E
0x18003afb5  mov     rcx, [rsp+68h+hKey]; hKey
0x18003afba  lea     r9d, [rax+4]; dwType
0x18003afbe  lea     rax, [rsp+68h+Data]
0x18003afc6  mov     [rsp+68h+samDesired], r9d; cbData
0x18003afcb  xor     r8d, r8d; Reserved
0x18003afce  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003afd3  mov     rdx, rdi; lpValueName
0x18003afd6  call    cs:__imp_RegSetValueExW
0x18003afdc  mov     rcx, [rsp+68h+hKey]; hKey
0x18003afe1  mov     ebx, eax
0x18003afe3  call    cs:__imp_RegCloseKey
0x18003afe9  jmp     short loc_18003B00E
0x18003afeb  mov     r9d, 4; dwType
0x18003aff1  lea     rax, [rsp+68h+Data]
0x18003aff9  mov     [rsp+68h+samDesired], r9d; cbData
0x18003affe  mov     rdx, rdi; lpValueName
0x18003b001  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003b006  call    cs:__imp_RegSetValueExW
0x18003b00c  mov     ebx, eax
0x18003b00e  mov     ecx, ebx; dwErrCode
0x18003b010  call    cs:__imp_SetLastError
0x18003b016  xor     eax, eax
0x18003b018  test    ebx, ebx
0x18003b01a  setz    al
0x18003b01d  jmp     short loc_18003B02C
0x18003b01f  mov     ecx, 57h ; 'W'; dwErrCode
0x18003b024  call    cs:__imp_SetLastError
0x18003b02a  xor     eax, eax
0x18003b02c  mov     rbx, [rsp+68h+arg_8]
0x18003b031  add     rsp, 60h
0x18003b035  pop     rdi
0x18003b036  retn
```
