# CRegistry::WriteValue(wchar_t const *,ushort,uchar *,ulong)

- ea: `0x140049e30`
- end: `0x140049e99`
- name: `?WriteValue@CRegistry@@UEAAHPEB_WGPEAEK@Z`
- size: `105`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1400492ac`
- `0x140049e30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140049e78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140049e78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049e4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049e88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049e4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049e88`

## pseudocode

```c
__int64 __fastcall CRegistry::WriteValue(
        CRegistry *this,
        const wchar_t *a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        DWORD cbData)
{
  DWORD v6; // ecx
  DWORD v8; // eax
  HKEY v9; // r10
  const BYTE *lpData; // r11
  LSTATUS v11; // eax

  if ( !*((_QWORD *)this + 22) )
  {
    v6 = 6;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  v8 = ConvertDBTYPEToREGTYPE(a3);
  v11 = RegSetValueExW(v9, a2, 0, v8, lpData, cbData);
  if ( v11 )
  {
    v6 = v11;
    goto LABEL_3;
  }
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x140049e30  push    rbx
0x140049e32  sub     rsp, 30h
0x140049e36  mov     r10, [rcx+0B0h]
0x140049e3d  mov     r11, r9
0x140049e40  mov     rbx, rdx
0x140049e43  test    r10, r10
0x140049e46  jnz     short loc_140049E56
0x140049e48  lea     ecx, [r10+6]; dwErrCode
0x140049e4c  call    cs:__imp_SetLastError
0x140049e52  xor     eax, eax
0x140049e54  jmp     short loc_140049E93
0x140049e56  movzx   ecx, r8w; unsigned __int16
0x140049e5a  call    ?ConvertDBTYPEToREGTYPE@@YAKG@Z; ConvertDBTYPEToREGTYPE(ushort)
0x140049e5f  mov     r9d, eax; dwType
0x140049e62  xor     r8d, r8d; Reserved
0x140049e65  mov     eax, [rsp+38h+arg_20]
0x140049e69  mov     rdx, rbx; lpValueName
0x140049e6c  mov     [rsp+38h+cbData], eax; cbData
0x140049e70  mov     rcx, r10; hKey
0x140049e73  mov     [rsp+38h+lpData], r11; lpData
0x140049e78  call    cs:__imp_RegSetValueExW
0x140049e7e  test    eax, eax
0x140049e80  jz      short loc_140049E86
0x140049e82  mov     ecx, eax
0x140049e84  jmp     short loc_140049E4C
0x140049e86  xor     ecx, ecx; dwErrCode
0x140049e88  call    cs:__imp_SetLastError
0x140049e8e  mov     eax, 1
0x140049e93  add     rsp, 30h
0x140049e97  pop     rbx
0x140049e98  retn
```
