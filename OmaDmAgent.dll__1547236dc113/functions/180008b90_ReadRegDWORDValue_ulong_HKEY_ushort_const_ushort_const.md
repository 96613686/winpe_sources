# ReadRegDWORDValue(ulong *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x180008b90`
- end: `0x180008ce6`
- name: `?ReadRegDWORDValue@@YAJPEAKPEAUHKEY__@@PEBG2@Z`
- size: `342`
- prototype: `__int64 __fastcall(LPBYTE lpData, HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008544`
- `0x1800085d4`
- `0x18000e524`
- `0x18000ea88`

## callees

- `0x180008b90`
- `0x18000a3c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180008cc0`
- `ADVAPI32!RegCloseKey` at `0x180008cc0`
- `ADVAPI32!RegQueryValueExW` at `0x180008c5d`
- `ADVAPI32!RegQueryValueExW` at `0x180008c5d`
- `ADVAPI32!RegOpenKeyExW` at `0x180008bf2`
- `ADVAPI32!RegOpenKeyExW` at `0x180008bf2`
- `KERNEL32!SetLastError` at `0x180008cce`
- `KERNEL32!SetLastError` at `0x180008cce`

## pseudocode

```c
__int64 __fastcall ReadRegDWORDValue(LPBYTE lpData, HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName)
{
  int v6; // edi
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  LPCWSTR v9; // rcx
  int v10; // edx
  int v11; // r9d
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+8h] BYREF

  hKeya = 0;
  Type = 4;
  v6 = (int)lpSubKey;
  cbData = 4;
  if ( !lpData || !hKey || !lpSubKey || !lpValueName )
  {
    v7 = -2147024809;
    goto LABEL_23;
  }
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, &hKeya);
  if ( v8 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    else
      v7 = v8;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_21;
    v10 = 29;
    v11 = v6;
    goto LABEL_20;
  }
  v7 = 0;
  v8 = RegQueryValueExW(hKeya, lpValueName, 0, &Type, lpData, &cbData);
  if ( !v8 )
    goto LABEL_21;
  if ( v8 > 0 )
  {
    v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 == 2 )
      goto LABEL_21;
  }
  else
  {
    v7 = v8;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v10 = 30;
    v11 = (int)lpValueName;
LABEL_20:
    WPP_SF_Sd(*((_QWORD *)v9 + 2), v10, (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, v11, v8);
  }
LABEL_21:
  if ( hKeya )
    RegCloseKey(hKeya);
LABEL_23:
  SetLastError(0);
  return v7;
}

```

## disassembly

```asm
0x180008b90  push    rbx
0x180008b92  push    rbp
0x180008b93  push    rsi
0x180008b94  push    rdi
0x180008b95  sub     rsp, 48h
0x180008b99  mov     rbp, rcx
0x180008b9c  mov     [rsp+68h+hKey], 0
0x180008ba5  mov     ecx, 4
0x180008baa  mov     rsi, r9
0x180008bad  mov     [rsp+68h+Type], ecx
0x180008bb1  mov     rdi, r8
0x180008bb4  mov     [rsp+68h+cbData], ecx
0x180008bb8  mov     rax, rdx
0x180008bbb  test    rbp, rbp
0x180008bbe  jnz     short loc_180008BCA
0x180008bc0  mov     ebx, 80070057h
0x180008bc5  jmp     loc_180008CCC
0x180008bca  test    rax, rax
0x180008bcd  jz      short loc_180008BC0
0x180008bcf  test    rdi, rdi
0x180008bd2  jz      short loc_180008BC0
0x180008bd4  test    rsi, rsi
0x180008bd7  jz      short loc_180008BC0
0x180008bd9  lea     rcx, [rsp+68h+hKey]
0x180008bde  mov     r9d, 101h; samDesired
0x180008be4  mov     [rsp+68h+phkResult], rcx; phkResult
0x180008be9  xor     r8d, r8d; ulOptions
0x180008bec  mov     rcx, rax; hKey
0x180008bef  mov     rdx, rdi; lpSubKey
0x180008bf2  call    cs:__imp_RegOpenKeyExW
0x180008bf9  nop     dword ptr [rax+rax+00h]
0x180008bfe  test    eax, eax
0x180008c00  jz      short loc_180008C3C
0x180008c02  jg      short loc_180008C08
0x180008c04  mov     ebx, eax
0x180008c06  jmp     short loc_180008C11
0x180008c08  movzx   ebx, ax
0x180008c0b  or      ebx, 80070000h
0x180008c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c18  lea     rdx, WPP_GLOBAL_Control
0x180008c1f  cmp     rcx, rdx
0x180008c22  jz      loc_180008CB6
0x180008c28  test    byte ptr [rcx+1Ch], 1
0x180008c2c  jz      loc_180008CB6
0x180008c32  mov     edx, 1Dh
0x180008c37  mov     r9, rdi
0x180008c3a  jmp     short loc_180008CA2
0x180008c3c  mov     rcx, [rsp+68h+hKey]; hKey
0x180008c41  lea     rax, [rsp+68h+cbData]
0x180008c46  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180008c4b  lea     r9, [rsp+68h+Type]; lpType
0x180008c50  xor     r8d, r8d; lpReserved
0x180008c53  mov     [rsp+68h+phkResult], rbp; lpData
0x180008c58  mov     rdx, rsi; lpValueName
0x180008c5b  xor     ebx, ebx
0x180008c5d  call    cs:__imp_RegQueryValueExW
0x180008c64  nop     dword ptr [rax+rax+00h]
0x180008c69  test    eax, eax
0x180008c6b  jz      short loc_180008CB6
0x180008c6d  jg      short loc_180008C73
0x180008c6f  mov     ebx, eax
0x180008c71  jmp     short loc_180008C81
0x180008c73  movzx   ebx, ax
0x180008c76  or      ebx, 80070000h
0x180008c7c  cmp     eax, 2
0x180008c7f  jz      short loc_180008CB6
0x180008c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c88  lea     rdx, WPP_GLOBAL_Control
0x180008c8f  cmp     rcx, rdx
0x180008c92  jz      short loc_180008CB6
0x180008c94  test    byte ptr [rcx+1Ch], 1
0x180008c98  jz      short loc_180008CB6
0x180008c9a  mov     edx, 1Eh
0x180008c9f  mov     r9, rsi
0x180008ca2  mov     rcx, [rcx+10h]
0x180008ca6  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180008cad  mov     dword ptr [rsp+68h+phkResult], eax
0x180008cb1  call    WPP_SF_Sd
0x180008cb6  mov     rcx, [rsp+68h+hKey]; hKey
0x180008cbb  test    rcx, rcx
0x180008cbe  jz      short loc_180008CCC
0x180008cc0  call    cs:__imp_RegCloseKey
0x180008cc7  nop     dword ptr [rax+rax+00h]
0x180008ccc  xor     ecx, ecx; dwErrCode
0x180008cce  call    cs:__imp_SetLastError
0x180008cd5  nop     dword ptr [rax+rax+00h]
0x180008cda  mov     eax, ebx
0x180008cdc  add     rsp, 48h
0x180008ce0  pop     rdi
0x180008ce1  pop     rsi
0x180008ce2  pop     rbp
0x180008ce3  pop     rbx
0x180008ce4  retn
```
