# IsSecureBootEnabled(SBServicingState::State *)

- ea: `0x180038c00`
- end: `0x180038cf7`
- name: `?IsSecureBootEnabled@@YAJPEAW4State@SBServicingState@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(enum SBServicingState::State *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1800166dc`
- `0x18001e5d0`
- `0x1800340e0`
- `0x180034634`

## callees

- `0x180038c00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038c94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038ce4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038ce4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038c45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038c45`

## pseudocode

```c
__int64 __fastcall IsSecureBootEnabled(enum SBServicingState::State *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  int Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = 0;
  cbData = 4;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\State", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 == -2147024894 )
  {
    *(_DWORD *)a1 = 2;
  }
  else
  {
    if ( v3 < 0 )
      goto LABEL_15;
    v4 = RegQueryValueExW(hKey, L"UEFISecureBootEnabled", 0, 0, (LPBYTE)&Data, &cbData);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      if ( Data == 1 )
        *(_DWORD *)a1 = 0;
      else
        *(_DWORD *)a1 = (Data != 0) + 1;
    }
    else
    {
      if ( v3 != -2147024894 )
        goto LABEL_15;
      *(_DWORD *)a1 = 1;
    }
  }
  v3 = 0;
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180038c00  mov     rax, rsp
0x180038c03  mov     [rax+8], rbx
0x180038c07  push    rdi
0x180038c08  sub     rsp, 30h
0x180038c0c  mov     dword ptr [rax+10h], 0
0x180038c13  mov     rdi, rcx
0x180038c16  mov     dword ptr [rax+18h], 4
0x180038c1d  mov     r9d, 20019h; samDesired
0x180038c23  mov     qword ptr [rax+20h], 0
0x180038c2b  lea     rax, [rax+20h]
0x180038c2f  xor     r8d, r8d; ulOptions
0x180038c32  mov     [rsp+38h+phkResult], rax; phkResult
0x180038c37  lea     rdx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180038c3e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038c45  call    cs:__imp_RegOpenKeyExW
0x180038c4b  mov     ebx, eax
0x180038c4d  test    eax, eax
0x180038c4f  jle     short loc_180038C5A
0x180038c51  movzx   ebx, ax
0x180038c54  or      ebx, 80070000h
0x180038c5a  cmp     ebx, 80070002h
0x180038c60  jnz     short loc_180038C6A
0x180038c62  mov     dword ptr [rdi], 2
0x180038c68  jmp     short loc_180038CD8
0x180038c6a  test    ebx, ebx
0x180038c6c  js      short loc_180038CDA
0x180038c6e  mov     rcx, [rsp+38h+hKey]; hKey
0x180038c73  lea     rax, [rsp+38h+cbData]
0x180038c78  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180038c7d  lea     rdx, aUefisecureboot; "UEFISecureBootEnabled"
0x180038c84  lea     rax, [rsp+38h+Data]
0x180038c89  xor     r9d, r9d; lpType
0x180038c8c  xor     r8d, r8d; lpReserved
0x180038c8f  mov     [rsp+38h+phkResult], rax; lpData
0x180038c94  call    cs:__imp_RegQueryValueExW
0x180038c9a  mov     ebx, eax
0x180038c9c  test    eax, eax
0x180038c9e  jle     short loc_180038CA9
0x180038ca0  movzx   ebx, ax
0x180038ca3  or      ebx, 80070000h
0x180038ca9  test    ebx, ebx
0x180038cab  jns     short loc_180038CBD
0x180038cad  cmp     ebx, 80070002h
0x180038cb3  jnz     short loc_180038CDA
0x180038cb5  mov     dword ptr [rdi], 1
0x180038cbb  jmp     short loc_180038CD8
0x180038cbd  mov     eax, [rsp+38h+Data]
0x180038cc1  cmp     eax, 1
0x180038cc4  jnz     short loc_180038CCE
0x180038cc6  mov     dword ptr [rdi], 0
0x180038ccc  jmp     short loc_180038CD8
0x180038cce  neg     eax
0x180038cd0  sbb     eax, eax
0x180038cd2  neg     eax
0x180038cd4  inc     eax
0x180038cd6  mov     [rdi], eax
0x180038cd8  xor     ebx, ebx
0x180038cda  mov     rcx, [rsp+38h+hKey]; hKey
0x180038cdf  test    rcx, rcx
0x180038ce2  jz      short loc_180038CEA
0x180038ce4  call    cs:__imp_RegCloseKey
0x180038cea  mov     eax, ebx
0x180038cec  mov     rbx, [rsp+38h+arg_0]
0x180038cf1  add     rsp, 30h
0x180038cf5  pop     rdi
0x180038cf6  retn
```
