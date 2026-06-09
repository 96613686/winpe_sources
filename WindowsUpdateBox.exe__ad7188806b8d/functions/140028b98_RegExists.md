# RegExists

- ea: `0x140028b98`
- end: `0x140028c62`
- name: `RegExists`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14005b208`

## callees

- `0x140028b98`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140028c0e`
- `ADVAPI32!RegQueryValueExW` at `0x140028c0e`
- `ADVAPI32!RegOpenKeyExW` at `0x140028bd5`
- `ADVAPI32!RegOpenKeyExW` at `0x140028bd5`
- `ADVAPI32!RegCloseKey` at `0x140028c33`
- `ADVAPI32!RegCloseKey` at `0x140028c33`
- `KERNEL32!SetLastError` at `0x140028c43`
- `KERNEL32!SetLastError` at `0x140028c43`

## pseudocode

```c
__int64 __fastcall RegExists(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rcx
  LSTATUS Value; // eax
  BOOL v8; // esi
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  v10 = 0;
  v6 = -2147483646;
  if ( a2 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, (PHKEY)&v10) )
      goto LABEL_12;
    v6 = v10;
    if ( !v10 )
      goto LABEL_12;
  }
  else
  {
    v10 = -2147483646;
  }
  if ( a3 )
  {
    Value = RegQueryValueExW((HKEY)v6, a3, 0, 0, 0, 0);
    v6 = v10;
    v8 = Value == 0;
  }
  else
  {
    v8 = 1;
  }
  if ( a2 )
    RegCloseKey((HKEY)v6);
  v3 = v8;
LABEL_12:
  SetLastError(0);
  return v3;
}

```

## disassembly

```asm
0x140028b98  mov     r11, rsp
0x140028b9b  mov     [r11+10h], rbx
0x140028b9f  mov     [r11+18h], rsi
0x140028ba3  mov     [r11+8], rcx
0x140028ba7  push    rdi
0x140028ba8  sub     rsp, 30h
0x140028bac  xor     ebx, ebx
0x140028bae  mov     rsi, r8
0x140028bb1  mov     [r11+8], rbx
0x140028bb5  mov     rdi, rdx
0x140028bb8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140028bbf  test    rdx, rdx
0x140028bc2  jz      short loc_140028BF1
0x140028bc4  lea     rax, [r11+8]
0x140028bc8  mov     r9d, 20019h; samDesired
0x140028bce  xor     r8d, r8d; ulOptions
0x140028bd1  mov     [r11-18h], rax
0x140028bd5  call    cs:__imp_RegOpenKeyExW
0x140028bdc  nop     dword ptr [rax+rax+00h]
0x140028be1  test    eax, eax
0x140028be3  jnz     short loc_140028C41
0x140028be5  mov     rcx, [rsp+38h+arg_0]
0x140028bea  test    rcx, rcx
0x140028bed  jnz     short loc_140028BF6
0x140028bef  jmp     short loc_140028C41
0x140028bf1  mov     [rsp+38h+arg_0], rcx
0x140028bf6  test    rsi, rsi
0x140028bf9  jz      short loc_140028C29
0x140028bfb  mov     [rsp+38h+lpcbData], rbx; lpcbData
0x140028c00  xor     r9d, r9d; lpType
0x140028c03  xor     r8d, r8d; lpReserved
0x140028c06  mov     [rsp+38h+lpData], rbx; lpData
0x140028c0b  mov     rdx, rsi; lpValueName
0x140028c0e  call    cs:__imp_RegQueryValueExW
0x140028c15  nop     dword ptr [rax+rax+00h]
0x140028c1a  mov     rcx, [rsp+38h+arg_0]
0x140028c1f  mov     esi, ebx
0x140028c21  test    eax, eax
0x140028c23  setz    sil
0x140028c27  jmp     short loc_140028C2E
0x140028c29  mov     esi, 1
0x140028c2e  test    rdi, rdi
0x140028c31  jz      short loc_140028C3F
0x140028c33  call    cs:__imp_RegCloseKey
0x140028c3a  nop     dword ptr [rax+rax+00h]
0x140028c3f  mov     ebx, esi
0x140028c41  xor     ecx, ecx; dwErrCode
0x140028c43  call    cs:__imp_SetLastError
0x140028c4a  nop     dword ptr [rax+rax+00h]
0x140028c4f  mov     rsi, [rsp+38h+arg_10]
0x140028c54  mov     eax, ebx
0x140028c56  mov     rbx, [rsp+38h+arg_8]
0x140028c5b  add     rsp, 30h
0x140028c5f  pop     rdi
0x140028c60  retn
```
