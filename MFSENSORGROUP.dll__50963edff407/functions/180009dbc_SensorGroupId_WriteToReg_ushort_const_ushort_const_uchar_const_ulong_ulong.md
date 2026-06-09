# SensorGroupId::WriteToReg(ushort const *,ushort const *,uchar const *,ulong,ulong)

- ea: `0x180009dbc`
- end: `0x180009ec9`
- name: `?WriteToReg@SensorGroupId@@SAJPEBG0PEBEKK@Z`
- size: `269`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, DWORD, DWORD dwType)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009bf0`
- `0x18004f600`
- `0x1800503e0`

## callees

- `0x180005fa0`
- `0x180009dbc`
- `0x18000ec30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009ebe`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009ebe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009e30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009e30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009e49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009e49`

## pseudocode

```c
__int64 __fastcall SensorGroupId::WriteToReg(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        DWORD a4,
        DWORD dwType)
{
  unsigned int v8; // edi
  LSTATUS v9; // eax
  __int64 v11; // rdx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
      return v8;
    v11 = 59;
LABEL_14:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
      0,
      -2147024809);
    return v8;
  }
  if ( a3 )
  {
    if ( a4 )
      goto LABEL_4;
    goto LABEL_16;
  }
  if ( a4 )
  {
LABEL_16:
    v8 = -2147024809;
    if ( !g_wppLevels )
      return v8;
    v11 = 60;
    goto LABEL_14;
  }
LABEL_4:
  hKey = 0;
  v8 = OpenSensorGroupRegistryKey(a1, 0x20106u, 0, &hKey);
  if ( (v8 & 0x80000000) == 0 )
  {
    v9 = a3 ? RegSetValueExW(hKey, a2, 0, dwType, a3, a4) : RegDeleteValueW(hKey, a2);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180009dbc  push    rbp
0x180009dbe  push    rsi
0x180009dbf  push    rdi
0x180009dc0  push    r14
0x180009dc2  sub     rsp, 38h
0x180009dc6  mov     esi, r9d
0x180009dc9  mov     rbp, r8
0x180009dcc  mov     r14, rdx
0x180009dcf  test    rdx, rdx
0x180009dd2  jz      loc_180009E5B
0x180009dd8  test    r8, r8
0x180009ddb  jz      loc_180009EA4
0x180009de1  test    r9d, r9d
0x180009de4  jz      loc_180009EAC
0x180009dea  lea     r9, [rsp+58h+hKey]; HKEY *
0x180009def  mov     [rsp+58h+hKey], 0
0x180009df8  xor     r8d, r8d; bool *
0x180009dfb  mov     edx, 20106h; unsigned int
0x180009e00  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180009e05  mov     edi, eax
0x180009e07  test    eax, eax
0x180009e09  js      short loc_180009E3C
0x180009e0b  mov     rcx, [rsp+58h+hKey]; hKey
0x180009e10  mov     rdx, r14; lpValueName
0x180009e13  test    rbp, rbp
0x180009e16  jz      loc_180009EBE
0x180009e1c  mov     r9d, [rsp+58h+dwType]; dwType
0x180009e24  xor     r8d, r8d; Reserved
0x180009e27  mov     [rsp+58h+cbData], esi; cbData
0x180009e2b  mov     [rsp+58h+lpData], rbp; lpData
0x180009e30  call    cs:__imp_RegSetValueExW
0x180009e36  mov     edi, eax
0x180009e38  test    eax, eax
0x180009e3a  jnz     short loc_180009E72
0x180009e3c  cmp     [rsp+58h+hKey], 0
0x180009e42  jz      short loc_180009E4F
0x180009e44  mov     rcx, [rsp+58h+hKey]; hKey
0x180009e49  call    cs:__imp_RegCloseKey
0x180009e4f  mov     eax, edi
0x180009e51  add     rsp, 38h
0x180009e55  pop     r14
0x180009e57  pop     rdi
0x180009e58  pop     rsi
0x180009e59  pop     rbp
0x180009e5a  retn
0x180009e5b  mov     eax, 80070057h
0x180009e60  mov     edi, eax
0x180009e62  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180009e69  jb      short loc_180009E4F
0x180009e6b  mov     edx, 3Bh ; ';'
0x180009e70  jmp     short loc_180009E84
0x180009e72  jle     short loc_180009E3C
0x180009e74  movzx   edi, di
0x180009e77  or      edi, 80070000h
0x180009e7d  jmp     short loc_180009E3C
0x180009e7f  mov     edx, 3Ch ; '<'
0x180009e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e8b  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180009e92  xor     r9d, r9d
0x180009e95  mov     dword ptr [rsp+58h+lpData], eax
0x180009e99  mov     rcx, [rcx+10h]
0x180009e9d  call    WPP_SF_qD
0x180009ea2  jmp     short loc_180009E4F
0x180009ea4  test    esi, esi
0x180009ea6  jz      loc_180009DEA
0x180009eac  mov     eax, 80070057h
0x180009eb1  mov     edi, eax
0x180009eb3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180009eba  jb      short loc_180009E4F
0x180009ebc  jmp     short loc_180009E7F
0x180009ebe  call    cs:__imp_RegDeleteValueW
0x180009ec4  jmp     loc_180009E36
```
