# SetRegistryDword

- ea: `0x1400709fc`
- end: `0x140070a5e`
- name: `SetRegistryDword`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001eb10`
- `0x1400236a0`
- `0x140041e30`
- `0x14005144c`
- `0x140051874`
- `0x14005198c`
- `0x140051c5c`
- `0x140060ed0`
- `0x14007ae30`
- `0x14007b81c`
- `0x14007bc44`
- `0x14007c07c`
- `0x14007cdc4`
- `0x14007d650`
- `0x14007d9e4`
- `0x14007e520`
- `0x14007e844`
- `0x14007ee18`
- `0x14007f070`
- `0x14007f334`
- `0x14007f654`
- `0x14007fd10`

## callees

- `0x1400709fc`
- `0x140071ec8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140070a24`
- `ADVAPI32!RegSetValueExW` at `0x140070a24`
- `KERNEL32!SetLastError` at `0x140070a44`
- `KERNEL32!SetLastError` at `0x140070a44`

## string_xrefs

- `0x140070a33`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall SetRegistryDword(HKEY a1, const WCHAR *a2, int a3)
{
  unsigned int v4; // eax
  DWORD v5; // ebx
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  v4 = RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&v7, 4u);
  v5 = v4;
  if ( !v4 )
    return 1;
  fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", a2, v4);
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x1400709fc  mov     r11, rsp
0x1400709ff  mov     [r11+8], rbx
0x140070a03  mov     [r11+18h], r8d
0x140070a07  push    rdi
0x140070a08  sub     rsp, 30h
0x140070a0c  mov     r9d, 4; dwType
0x140070a12  lea     rax, [r11+18h]
0x140070a16  mov     [r11-10h], r9d
0x140070a1a  xor     r8d, r8d; Reserved
0x140070a1d  mov     [r11-18h], rax
0x140070a21  mov     rdi, rdx
0x140070a24  call    cs:__imp_RegSetValueExW
0x140070a2a  mov     ebx, eax
0x140070a2c  test    eax, eax
0x140070a2e  jz      short loc_140070A4E
0x140070a30  mov     r8d, eax
0x140070a33  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x140070a3a  mov     rdx, rdi
0x140070a3d  call    fax_dprintf
0x140070a42  mov     ecx, ebx; dwErrCode
0x140070a44  call    cs:__imp_SetLastError
0x140070a4a  xor     eax, eax
0x140070a4c  jmp     short loc_140070A53
0x140070a4e  mov     eax, 1
0x140070a53  mov     rbx, [rsp+38h+arg_0]
0x140070a58  add     rsp, 30h
0x140070a5c  pop     rdi
0x140070a5d  retn
```
