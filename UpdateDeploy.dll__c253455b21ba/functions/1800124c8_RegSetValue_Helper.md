# RegSetValue_Helper

- ea: `0x1800124c8`
- end: `0x180012557`
- name: `RegSetValue_Helper`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012560`
- `0x1800125b4`

## callees

- `0x180012358`
- `0x1800124c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012544`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012544`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012514`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012514`

## pseudocode

```c
__int64 __fastcall RegSetValue_Helper(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  int v8; // ebx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v8 = RegCreateKeyHelperPrivate(a1, a2, a3, &hKey);
  if ( v8 >= 0 )
  {
    v9 = RegSetValueExW(hKey, a4, 0, dwType, lpData, cbData);
    if ( v9 )
    {
      v8 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v8 = v9;
    }
  }
  if ( hKey != HKEY_LOCAL_MACHINE && hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800124c8  mov     rax, rsp
0x1800124cb  mov     [rax+10h], rbx
0x1800124cf  mov     [rax+8], rcx
0x1800124d3  push    rsi
0x1800124d4  sub     rsp, 30h
0x1800124d8  mov     rsi, r9
0x1800124db  mov     qword ptr [rax+8], 0
0x1800124e3  lea     r9, [rax+8]
0x1800124e7  call    RegCreateKeyHelperPrivate
0x1800124ec  mov     ebx, eax
0x1800124ee  test    eax, eax
0x1800124f0  js      short loc_18001252C
0x1800124f2  mov     ecx, [rsp+38h+arg_30]
0x1800124f6  xor     r8d, r8d; Reserved
0x1800124f9  mov     r9d, [rsp+38h+dwType]; dwType
0x1800124fe  mov     rdx, rsi; lpValueName
0x180012501  mov     [rsp+38h+cbData], ecx; cbData
0x180012505  mov     rcx, [rsp+38h+arg_28]
0x18001250a  mov     [rsp+38h+lpData], rcx; lpData
0x18001250f  mov     rcx, [rsp+38h+hKey]; hKey
0x180012514  call    cs:__imp_RegSetValueExW
0x18001251a  test    eax, eax
0x18001251c  jz      short loc_18001252C
0x18001251e  movzx   ebx, ax
0x180012521  or      ebx, 80070000h
0x180012527  test    eax, eax
0x180012529  cmovle  ebx, eax
0x18001252c  cmp     [rsp+38h+hKey], 0FFFFFFFF80000002h
0x180012535  jz      short loc_18001254A
0x180012537  cmp     [rsp+38h+hKey], 0
0x18001253d  jz      short loc_18001254A
0x18001253f  mov     rcx, [rsp+38h+hKey]; hKey
0x180012544  call    cs:__imp_RegCloseKey
0x18001254a  mov     eax, ebx
0x18001254c  mov     rbx, [rsp+38h+arg_8]
0x180012551  add     rsp, 30h
0x180012555  pop     rsi
0x180012556  retn
```
