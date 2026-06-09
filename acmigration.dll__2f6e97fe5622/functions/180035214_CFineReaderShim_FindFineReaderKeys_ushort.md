# CFineReaderShim::FindFineReaderKeys(ushort *)

- ea: `0x180035214`
- end: `0x1800353a4`
- name: `?FindFineReaderKeys@CFineReaderShim@@AEAAKPEAG@Z`
- size: `400`
- prototype: `unsigned int __fastcall(CFineReaderShim *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035400`

## callees

- `0x180001cf0`
- `0x180034f44`
- `0x180035214`
- `0x180035b3c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180035365`
- `ADVAPI32!RegCloseKey` at `0x180035375`
- `ADVAPI32!RegCloseKey` at `0x180035365`
- `ADVAPI32!RegCloseKey` at `0x180035375`
- `ADVAPI32!RegEnumKeyExW` at `0x18003534e`
- `ADVAPI32!RegEnumKeyExW` at `0x18003534e`
- `ADVAPI32!RegOpenKeyExW` at `0x18003528d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800352bc`
- `ADVAPI32!RegOpenKeyExW` at `0x18003528d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800352bc`

## string_xrefs

- `0x1800352b5`: `Software\Classes\Clsid`

## pseudocode

```c
__int64 __fastcall CFineReaderShim::FindFineReaderKeys(CFineReaderShim *this, unsigned __int16 *a2)
{
  HKEY v4; // rcx
  unsigned int v5; // ebx
  DWORD i; // edx
  HKEY v7; // r8
  CFineReaderShim *v8; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cchName = 259;
  phkResult = 0;
  if ( a2 )
  {
    v5 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x20019u, &hKey);
    if ( v5 )
      goto LABEL_12;
    v4 = hKey;
  }
  else
  {
    v4 = HKEY_LOCAL_MACHINE;
  }
  v5 = RegOpenKeyExW(v4, L"Software\\Classes\\Clsid", 0, 0x20019u, &phkResult);
  if ( !v5 )
  {
    for ( i = 0; ; i = v5 )
    {
      cchName = 259;
      if ( RegEnumKeyExW(phkResult, i, Name, &cchName, 0, 0, 0, 0) == 259 )
        break;
      if ( CFineReaderShim::CheckFineReaderKey(v8, phkResult, Name) )
      {
        v7 = phkResult;
        *(_DWORD *)this = 1;
        CFineReaderShim::SaveKey(this, a2, v7, Name);
      }
      ++v5;
    }
    v5 = 0;
  }
LABEL_12:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180035214  mov     [rsp-8+arg_10], rbx
0x180035219  mov     [rsp-8+arg_18], rsi
0x18003521e  push    rbp
0x18003521f  push    rdi
0x180035220  push    r15
0x180035222  lea     rbp, [rsp-180h]
0x18003522a  sub     rsp, 280h
0x180035231  mov     rax, cs:__security_cookie
0x180035238  xor     rax, rsp
0x18003523b  mov     [rbp+190h+var_20], rax
0x180035242  mov     [rsp+290h+hKey], 0
0x18003524b  mov     r15d, 103h
0x180035251  mov     [rsp+290h+cchName], r15d
0x180035256  mov     rdi, rdx
0x180035259  mov     [rsp+290h+var_248], 0
0x180035262  mov     rsi, rcx
0x180035265  test    rdx, rdx
0x180035268  jnz     short loc_180035273
0x18003526a  mov     rcx, 0FFFFFFFF80000002h
0x180035271  jmp     short loc_1800352A2
0x180035273  lea     rax, [rsp+290h+hKey]
0x180035278  mov     r9d, 20019h; samDesired
0x18003527e  xor     r8d, r8d; ulOptions
0x180035281  mov     [rsp+290h+phkResult], rax; phkResult
0x180035286  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003528d  call    cs:__imp_RegOpenKeyExW
0x180035293  mov     ebx, eax
0x180035295  test    eax, eax
0x180035297  jnz     loc_18003535B
0x18003529d  mov     rcx, [rsp+290h+hKey]; hKey
0x1800352a2  lea     rax, [rsp+290h+var_248]
0x1800352a7  mov     r9d, 20019h; samDesired
0x1800352ad  xor     r8d, r8d; ulOptions
0x1800352b0  mov     [rsp+290h+phkResult], rax; phkResult
0x1800352b5  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\Clsid"
0x1800352bc  call    cs:__imp_RegOpenKeyExW
0x1800352c2  mov     ebx, eax
0x1800352c4  test    eax, eax
0x1800352c6  jnz     loc_18003535B
0x1800352cc  mov     [rsp+290h+lpftLastWriteTime], rbx
0x1800352d1  xor     edx, edx
0x1800352d3  mov     [rsp+290h+lpcchClass], rbx
0x1800352d8  mov     [rsp+290h+lpClass], rbx
0x1800352dd  mov     [rsp+290h+phkResult], rbx
0x1800352e2  jmp     short loc_18003533A
0x1800352e4  mov     rdx, [rsp+290h+var_248]; HKEY
0x1800352e9  lea     r8, [rsp+290h+Name]; unsigned __int16 *
0x1800352ee  call    ?CheckFineReaderKey@CFineReaderShim@@AEAAHPEAUHKEY__@@PEAG@Z; CFineReaderShim::CheckFineReaderKey(HKEY__ *,ushort *)
0x1800352f3  test    eax, eax
0x1800352f5  jz      short loc_180035312
0x1800352f7  mov     r8, [rsp+290h+var_248]; HKEY
0x1800352fc  lea     r9, [rsp+290h+Name]; unsigned __int16 *
0x180035301  mov     rdx, rdi; unsigned __int16 *
0x180035304  mov     dword ptr [rsi], 1
0x18003530a  mov     rcx, rsi; this
0x18003530d  call    ?SaveKey@CFineReaderShim@@AEAAKPEBGPEAUHKEY__@@PEAG@Z; CFineReaderShim::SaveKey(ushort const *,HKEY__ *,ushort *)
0x180035312  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18003531b  inc     ebx
0x18003531d  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180035326  mov     edx, ebx; dwIndex
0x180035328  mov     [rsp+290h+lpClass], 0; lpClass
0x180035331  mov     [rsp+290h+phkResult], 0; lpReserved
0x18003533a  mov     rcx, [rsp+290h+var_248]; hKey
0x18003533f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180035344  lea     r8, [rsp+290h+Name]; lpName
0x180035349  mov     [rsp+290h+cchName], r15d
0x18003534e  call    cs:__imp_RegEnumKeyExW
0x180035354  cmp     eax, r15d
0x180035357  jnz     short loc_1800352E4
0x180035359  xor     ebx, ebx
0x18003535b  mov     rcx, [rsp+290h+var_248]; hKey
0x180035360  test    rcx, rcx
0x180035363  jz      short loc_18003536B
0x180035365  call    cs:__imp_RegCloseKey
0x18003536b  mov     rcx, [rsp+290h+hKey]; hKey
0x180035370  test    rcx, rcx
0x180035373  jz      short loc_18003537B
0x180035375  call    cs:__imp_RegCloseKey
0x18003537b  mov     eax, ebx
0x18003537d  mov     rcx, [rbp+190h+var_20]
0x180035384  xor     rcx, rsp; StackCookie
0x180035387  call    __security_check_cookie
0x18003538c  lea     r11, [rsp+290h+var_10]
0x180035394  mov     rbx, [r11+30h]
0x180035398  mov     rsi, [r11+38h]
0x18003539c  mov     rsp, r11
0x18003539f  pop     r15
0x1800353a1  pop     rdi
0x1800353a2  pop     rbp
0x1800353a3  retn
```
