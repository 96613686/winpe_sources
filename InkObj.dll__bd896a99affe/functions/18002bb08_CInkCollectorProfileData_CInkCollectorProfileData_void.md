# CInkCollectorProfileData::CInkCollectorProfileData(void)

- ea: `0x18002bb08`
- end: `0x18002bc74`
- name: `??0CInkCollectorProfileData@@QEAA@XZ`
- size: `364`
- prototype: `CInkCollectorProfileData *__fastcall(CInkCollectorProfileData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001490`

## callees

- `0x18002bb08`
- `0x18002bc7c`
- `0x18002be80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bb66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bb66`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bc1d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002bc1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bc49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002bc49`

## pseudocode

```c
CInkCollectorProfileData *__fastcall CInkCollectorProfileData::CInkCollectorProfileData(CInkCollectorProfileData *this)
{
  const unsigned __int16 *v1; // rdx
  CInkCollectorProfileData *v2; // rcx
  const unsigned __int16 *v3; // r8
  int HKCUValue_DWORD; // eax
  const unsigned __int16 *v5; // r8
  CInkCollectorProfileData *v6; // rcx
  __int64 v7; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-38h]
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  int v11; // [rsp+64h] [rbp+Ch]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v11 = HIDWORD(this);
  hKey = 0;
  cbData = 4;
  *(_DWORD *)&g_CollectorProfileData = 0;
  pv = 0;
  *(_DWORD *)&uElapse = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\\\Microsoft\\\\Wisp\\\\Pen\\\\Profile", 0, 1u, &hKey) )
  {
    RegQueryValueExW(hKey, L"TIMESTAMP", 0, 0, &g_CollectorProfileData, &cbData);
    RegCloseKey(hKey);
  }
  HKCUValue_DWORD = CInkCollectorProfileData::RetrieveHKCUValue_DWORD(v2, v1, v3, (unsigned int *)&uElapse, phkResult);
  v6 = (CInkCollectorProfileData *)*(unsigned int *)&uElapse;
  LODWORD(v7) = 500;
  if ( *(_DWORD *)&uElapse < 0x1F4u || (v7 = 2000, *(_DWORD *)&uElapse > 0x7D0u) )
  {
    *(_DWORD *)&uElapse = v7;
  }
  else if ( HKCUValue_DWORD != 1 )
  {
    goto LABEL_9;
  }
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\\\Microsoft\\\\TPG\\\\Recognizers",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          0) )
  {
    RegSetValueExW(hKey, L"GestureTimeout", 0, 4u, &uElapse, cbData);
    RegCloseKey(hKey);
  }
LABEL_9:
  CInkCollectorProfileData::RetrieveHKCUValue_String(v6, (const unsigned __int16 *)v7, v5, (unsigned __int16 **)&pv);
  return (CInkCollectorProfileData *)&g_CollectorProfileData;
}

```

## disassembly

```asm
0x18002bb08  mov     rax, rsp
0x18002bb0b  mov     [rax+18h], rsi
0x18002bb0f  mov     [rax+8], rcx
0x18002bb13  push    rdi
0x18002bb14  sub     rsp, 50h
0x18002bb18  mov     qword ptr [rax+10h], 0
0x18002bb20  mov     r9d, 1; samDesired
0x18002bb26  mov     dword ptr [rax+8], 4
0x18002bb2d  lea     rax, [rax+10h]
0x18002bb31  xor     r8d, r8d; ulOptions
0x18002bb34  mov     [rsp+58h+phkResult], rax; phkResult
0x18002bb39  lea     rdx, SubKey; "Software\\\\Microsoft\\\\Wisp\\\\Pen\\"...
0x18002bb40  mov     cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A, 0; CInkCollectorProfileData g_CollectorProfileData
0x18002bb4a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002bb51  mov     cs:pv, 0
0x18002bb5c  mov     cs:uElapse, 0
0x18002bb66  call    cs:__imp_RegOpenKeyExW
0x18002bb6c  lea     rdi, ?g_CollectorProfileData@@3VCInkCollectorProfileData@@A; CInkCollectorProfileData g_CollectorProfileData
0x18002bb73  test    eax, eax
0x18002bb75  jnz     short loc_18002BBA9
0x18002bb77  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bb7c  lea     rax, [rsp+58h+cbData]
0x18002bb81  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002bb86  lea     rdx, ValueName; "TIMESTAMP"
0x18002bb8d  xor     r9d, r9d; lpType
0x18002bb90  mov     [rsp+58h+phkResult], rdi; unsigned int
0x18002bb95  xor     r8d, r8d; lpReserved
0x18002bb98  call    cs:__imp_RegQueryValueExW
0x18002bb9e  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bba3  call    cs:__imp_RegCloseKey
0x18002bba9  lea     rsi, uElapse
0x18002bbb0  mov     r9, rsi; unsigned int *
0x18002bbb3  call    ?RetrieveHKCUValue_DWORD@CInkCollectorProfileData@@AEAAJPEBG0PEAKK@Z; CInkCollectorProfileData::RetrieveHKCUValue_DWORD(ushort const *,ushort const *,ulong *,ulong)
0x18002bbb8  mov     ecx, cs:uElapse
0x18002bbbe  mov     edx, 1F4h
0x18002bbc3  cmp     ecx, edx
0x18002bbc5  jnb     short loc_18002BBCF
0x18002bbc7  mov     cs:uElapse, edx
0x18002bbcd  jmp     short loc_18002BBDD
0x18002bbcf  mov     edx, 7D0h
0x18002bbd4  cmp     ecx, edx
0x18002bbd6  ja      short loc_18002BBC7
0x18002bbd8  cmp     eax, 1
0x18002bbdb  jnz     short loc_18002BC5A
0x18002bbdd  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18002bbe6  lea     rax, [rsp+58h+hKey]
0x18002bbeb  mov     [rsp+58h+var_20], rax; phkResult
0x18002bbf0  lea     rdx, aSoftwareMicros_3; "Software\\\\Microsoft\\\\TPG\\\\Recogni"...
0x18002bbf7  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002bc00  xor     r9d, r9d; lpClass
0x18002bc03  mov     dword ptr [rsp+58h+lpcbData], 2001Fh; samDesired
0x18002bc0b  xor     r8d, r8d; Reserved
0x18002bc0e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002bc15  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x18002bc1d  call    cs:__imp_RegCreateKeyExW
0x18002bc23  test    eax, eax
0x18002bc25  jnz     short loc_18002BC5A
0x18002bc27  mov     eax, [rsp+58h+cbData]
0x18002bc2b  lea     rdx, aGesturetimeout; "GestureTimeout"
0x18002bc32  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bc37  mov     r9d, 4; dwType
0x18002bc3d  mov     dword ptr [rsp+58h+lpcbData], eax; cbData
0x18002bc41  xor     r8d, r8d; Reserved
0x18002bc44  mov     [rsp+58h+phkResult], rsi; unsigned __int16 *
0x18002bc49  call    cs:__imp_RegSetValueExW
0x18002bc4f  mov     rcx, [rsp+58h+hKey]; hKey
0x18002bc54  call    cs:__imp_RegCloseKey
0x18002bc5a  lea     r9, pv; unsigned __int16 **
0x18002bc61  call    ?RetrieveHKCUValue_String@CInkCollectorProfileData@@AEAAJPEBG0PEAPEAGPEAG@Z; CInkCollectorProfileData::RetrieveHKCUValue_String(ushort const *,ushort const *,ushort * *,ushort *)
0x18002bc66  mov     rsi, [rsp+58h+arg_10]
0x18002bc6b  mov     rax, rdi
0x18002bc6e  add     rsp, 50h
0x18002bc72  pop     rdi
0x18002bc73  retn
```
