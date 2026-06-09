# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000674c`
- end: `0x180006893`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000674c`
- `0x180006c0c`

## callees

- `0x180001ef0`
- `0x180004f10`
- `0x18000674c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000682e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000682e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800067ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800067ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006842`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006864`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006842`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006864`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x18000674c  mov     [rsp-8+arg_10], rbx
0x180006751  mov     [rsp-8+arg_18], rsi
0x180006756  push    rbp
0x180006757  push    rdi
0x180006758  push    r14
0x18000675a  lea     rbp, [rsp-180h]
0x180006762  sub     rsp, 280h
0x180006769  mov     rax, cs:__security_cookie
0x180006770  xor     rax, rsp
0x180006773  mov     [rbp+190h+var_20], rax
0x18000677a  xor     r14d, r14d
0x18000677d  lea     rax, [rsp+290h+var_230]
0x180006782  mov     rdi, rcx
0x180006785  mov     [rsp+290h+hKey], r14
0x18000678a  mov     rcx, [rcx]; hKey
0x18000678d  mov     r9d, 2001Fh; samDesired
0x180006793  xor     r8d, r8d; ulOptions
0x180006796  mov     [rsp+290h+var_240], r14
0x18000679b  mov     [rsp+290h+var_238], r14
0x1800067a0  mov     rsi, rdx
0x1800067a3  mov     [rsp+290h+var_230], r14
0x1800067a8  mov     [rsp+290h+phkResult], rax; phkResult
0x1800067ad  call    cs:__imp_RegOpenKeyExW
0x1800067b3  mov     rcx, [rsp+290h+hKey]; hKey
0x1800067b8  mov     ebx, eax
0x1800067ba  test    eax, eax
0x1800067bc  jnz     loc_18000685F
0x1800067c2  mov     ebx, r14d
0x1800067c5  test    rcx, rcx
0x1800067c8  jz      short loc_1800067D2
0x1800067ca  call    cs:__imp_RegCloseKey
0x1800067d0  mov     ebx, eax
0x1800067d2  mov     rcx, [rsp+290h+var_230]
0x1800067d7  mov     [rsp+290h+hKey], rcx
0x1800067dc  test    ebx, ebx
0x1800067de  jnz     short loc_18000685F
0x1800067e0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800067e5  jmp     short loc_180006801
0x1800067e7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800067ec  lea     rcx, [rsp+290h+hKey]; this
0x1800067f1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800067f6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800067fb  mov     ebx, eax
0x1800067fd  test    eax, eax
0x1800067ff  jnz     short loc_18000685F
0x180006801  lea     rax, [rsp+290h+ftLastWriteTime]
0x180006806  mov     [rsp+290h+cchName], 100h
0x18000680e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180006813  lea     r9, [rsp+290h+cchName]; lpcchName
0x180006818  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000681d  lea     r8, [rsp+290h+Name]; lpName
0x180006822  mov     [rsp+290h+lpClass], r14; lpClass
0x180006827  xor     edx, edx; dwIndex
0x180006829  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000682e  call    cs:__imp_RegEnumKeyExW
0x180006834  test    eax, eax
0x180006836  jz      short loc_1800067E7
0x180006838  mov     rcx, [rsp+290h+hKey]; hKey
0x18000683d  test    rcx, rcx
0x180006840  jz      short loc_18000684D
0x180006842  call    cs:__imp_RegCloseKey
0x180006848  mov     [rsp+290h+hKey], r14
0x18000684d  mov     rdx, rsi; unsigned __int16 *
0x180006850  mov     rcx, rdi; this
0x180006853  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180006858  mov     rcx, [rsp+290h+hKey]; hKey
0x18000685d  mov     ebx, eax
0x18000685f  test    rcx, rcx
0x180006862  jz      short loc_18000686A
0x180006864  call    cs:__imp_RegCloseKey
0x18000686a  mov     eax, ebx
0x18000686c  mov     rcx, [rbp+190h+var_20]
0x180006873  xor     rcx, rsp; StackCookie
0x180006876  call    __security_check_cookie
0x18000687b  lea     r11, [rsp+290h+var_10]
0x180006883  mov     rbx, [r11+30h]
0x180006887  mov     rsi, [r11+38h]
0x18000688b  mov     rsp, r11
0x18000688e  pop     r14
0x180006890  pop     rdi
0x180006891  pop     rbp
0x180006892  retn
```
