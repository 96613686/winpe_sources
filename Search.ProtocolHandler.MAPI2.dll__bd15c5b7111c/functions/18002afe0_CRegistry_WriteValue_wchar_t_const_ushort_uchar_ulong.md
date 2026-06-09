# CRegistry::WriteValue(wchar_t const *,ushort,uchar *,ulong)

- ea: `0x18002afe0`
- end: `0x18002b049`
- name: `?WriteValue@CRegistry@@UEAAHPEB_WGPEAEK@Z`
- size: `105`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18002a42c`
- `0x18002afe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002affc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b038`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002affc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b038`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b028`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b028`

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
0x18002afe0  push    rbx
0x18002afe2  sub     rsp, 30h
0x18002afe6  mov     r10, [rcx+0B0h]
0x18002afed  mov     r11, r9
0x18002aff0  mov     rbx, rdx
0x18002aff3  test    r10, r10
0x18002aff6  jnz     short loc_18002B006
0x18002aff8  lea     ecx, [r10+6]; dwErrCode
0x18002affc  call    cs:__imp_SetLastError
0x18002b002  xor     eax, eax
0x18002b004  jmp     short loc_18002B043
0x18002b006  movzx   ecx, r8w; unsigned __int16
0x18002b00a  call    ?ConvertDBTYPEToREGTYPE@@YAKG@Z; ConvertDBTYPEToREGTYPE(ushort)
0x18002b00f  mov     r9d, eax; dwType
0x18002b012  xor     r8d, r8d; Reserved
0x18002b015  mov     eax, [rsp+38h+arg_20]
0x18002b019  mov     rdx, rbx; lpValueName
0x18002b01c  mov     [rsp+38h+cbData], eax; cbData
0x18002b020  mov     rcx, r10; hKey
0x18002b023  mov     [rsp+38h+lpData], r11; lpData
0x18002b028  call    cs:__imp_RegSetValueExW
0x18002b02e  test    eax, eax
0x18002b030  jz      short loc_18002B036
0x18002b032  mov     ecx, eax
0x18002b034  jmp     short loc_18002AFFC
0x18002b036  xor     ecx, ecx; dwErrCode
0x18002b038  call    cs:__imp_SetLastError
0x18002b03e  mov     eax, 1
0x18002b043  add     rsp, 30h
0x18002b047  pop     rbx
0x18002b048  retn
```
