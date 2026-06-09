# RegSetValue_Helper

- ea: `0x140018080`
- end: `0x140018117`
- name: `RegSetValue_Helper`
- size: `151`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64, const WCHAR *, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140018120`
- `0x140018170`

## callees

- `0x140017f90`
- `0x140018080`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400180ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400180ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400180d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400180d3`

## pseudocode

```c
__int64 __fastcall RegSetValue_Helper(
        HKEY a1,
        const WCHAR *a2,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  signed int KeyHelperPrivate; // ebx
  LSTATUS v9; // eax

  KeyHelperPrivate = RegCreateKeyHelperPrivate(a1, a2);
  if ( KeyHelperPrivate >= 0 )
  {
    v9 = RegSetValueExW(0, a4, 0, dwType, lpData, cbData);
    if ( v9 )
    {
      KeyHelperPrivate = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        return (unsigned int)v9;
    }
  }
  return (unsigned int)KeyHelperPrivate;
}

```

## disassembly

```asm
0x140018080  mov     rax, rsp
0x140018083  mov     [rax+8], rbx
0x140018087  mov     [rax+10h], rbp
0x14001808b  mov     [rax+18h], r8
0x14001808f  push    rsi
0x140018090  sub     rsp, 30h
0x140018094  mov     rbp, r9
0x140018097  mov     qword ptr [rax+18h], 0
0x14001809f  lea     r9, [rax+18h]
0x1400180a3  mov     rsi, rcx
0x1400180a6  call    RegCreateKeyHelperPrivate
0x1400180ab  mov     ebx, eax
0x1400180ad  test    eax, eax
0x1400180af  js      short loc_1400180EB
0x1400180b1  mov     edx, [rsp+38h+arg_30]
0x1400180b5  xor     r8d, r8d; Reserved
0x1400180b8  mov     rcx, [rsp+38h+arg_28]
0x1400180bd  mov     r9d, [rsp+38h+dwType]; dwType
0x1400180c2  mov     [rsp+38h+cbData], edx; cbData
0x1400180c6  mov     rdx, rbp; lpValueName
0x1400180c9  mov     [rsp+38h+lpData], rcx; lpData
0x1400180ce  mov     rcx, [rsp+38h+hKey]; hKey
0x1400180d3  call    cs:__imp_RegSetValueExW
0x1400180d9  test    eax, eax
0x1400180db  jz      short loc_1400180EB
0x1400180dd  movzx   ebx, ax
0x1400180e0  or      ebx, 80070000h
0x1400180e6  test    eax, eax
0x1400180e8  cmovle  ebx, eax
0x1400180eb  cmp     rsi, [rsp+38h+hKey]
0x1400180f0  jz      short loc_140018105
0x1400180f2  cmp     [rsp+38h+hKey], 0
0x1400180f8  jz      short loc_140018105
0x1400180fa  mov     rcx, [rsp+38h+hKey]; hKey
0x1400180ff  call    cs:__imp_RegCloseKey
0x140018105  mov     rbp, [rsp+38h+arg_8]
0x14001810a  mov     eax, ebx
0x14001810c  mov     rbx, [rsp+38h+arg_0]
0x140018111  add     rsp, 30h
0x140018115  pop     rsi
0x140018116  retn
```
