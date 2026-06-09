# CLockScreenApplicationManagerBase::_CheckForDuplicate(ushort const *,ushort const *,ushort const *,LOCK_SCREEN_APPLICATION_CAPABILITIES,uint *)

- ea: `0x18011af34`
- end: `0x18011b273`
- name: `?_CheckForDuplicate@CLockScreenApplicationManagerBase@@IEAAJPEBG00W4LOCK_SCREEN_APPLICATION_CAPABILITIES@@PEAI@Z`
- size: `831`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum LOCK_SCREEN_APPLICATION_CAPABILITIES, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180389528`

## callees

- `0x18002fb8c`
- `0x18011af34`
- `0x180142e10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b112`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b143`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b1d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b208`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b112`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b143`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b1d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011b208`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011b195`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011b195`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011b231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011b231`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011afec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011afec`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18011b06e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18011b06e`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18011b0d8`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18011b0d8`

## pseudocode

```c
__int64 __fastcall CLockScreenApplicationManagerBase::_CheckForDuplicate(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        int a5,
        _DWORD *a6)
{
  const wchar_t *v8; // rax
  signed int v9; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  DWORD v12; // edi
  unsigned int v13; // eax
  LSTATUS v14; // eax
  LSTATUS ValueW; // eax
  bool v16; // sf
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcchName; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData[3]; // [rsp+74h] [rbp-8Ch] BYREF
  WCHAR pszName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pvData[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR SubKey[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  if ( a5 == 1 )
  {
    v8 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\Tile";
  }
  else
  {
    v8 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\Badge";
    if ( a5 != 2 )
      v8 = L"BadKey";
  }
  v9 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", a2, v8);
  if ( v9 >= 0 )
  {
    hKey = 0;
    v10 = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20019u, &hKey);
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v9 < 0 )
    {
      if ( v9 == -2147024894 )
        return 0;
    }
    else
    {
      cSubKeys = 0;
      v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 >= 0 )
      {
        v12 = 0;
        while ( v12 < cSubKeys )
        {
          if ( a5 == 1 )
          {
            v13 = 1;
          }
          else
          {
            v13 = 0;
            if ( a5 == 2 )
              v13 = 7;
          }
          if ( v12 >= v13 )
            break;
          pcchName = 260;
          v14 = SHEnumKeyExW(hKey, v12, pszName, &pcchName);
          v9 = v14;
          if ( v14 > 0 )
            v9 = (unsigned __int16)v14 | 0x80070000;
          if ( v9 < 0 )
            goto LABEL_33;
          if ( CompareStringOrdinal(pszName, -1, a3, -1, 1) == 2
            || a4 && CompareStringOrdinal(pszName, -1, a4, -1, 1) == 2 )
          {
            goto LABEL_32;
          }
          pcbData[0] = 520;
          ValueW = RegGetValueW(hKey, pszName, L"ParentAppId", 2u, 0, pvData, pcbData);
          v16 = ValueW < 0;
          if ( ValueW )
          {
            pvData[0] = 0;
            v16 = ValueW < 0;
            if ( ValueW > 0 )
              v16 = 1;
          }
          if ( !v16
            && (CompareStringOrdinal(pvData, -1, a3, -1, 1) == 2
             || a4 && CompareStringOrdinal(pvData, -1, a4, -1, 1) == 2) )
          {
LABEL_32:
            ++*a6;
            ++v12;
          }
          else
          {
LABEL_33:
            ++v12;
            if ( v9 < 0 )
              break;
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18011af34  mov     [rsp-8+arg_0], rbx
0x18011af39  push    rbp
0x18011af3a  push    rsi
0x18011af3b  push    rdi
0x18011af3c  push    r12
0x18011af3e  push    r15
0x18011af40  lea     rbp, [rsp-5C0h]
0x18011af48  sub     rsp, 6C0h
0x18011af4f  mov     rax, cs:__security_cookie
0x18011af56  xor     rax, rsp
0x18011af59  mov     [rbp+5E0h+var_30], rax
0x18011af60  cmp     [rbp+5E0h+arg_20], 1
0x18011af67  mov     r15, r9
0x18011af6a  mov     rsi, [rbp+5E0h+arg_28]
0x18011af71  mov     r12, r8
0x18011af74  jnz     short loc_18011AF7F
0x18011af76  lea     rax, aSoftwareMicros_59; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011af7d  jmp     short loc_18011AF98
0x18011af7f  cmp     [rbp+5E0h+arg_20], 2
0x18011af86  lea     rax, aSoftwareMicros_78; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011af8d  lea     rcx, aBadkey; "BadKey"
0x18011af94  cmovnz  rax, rcx
0x18011af98  mov     r9, rdx
0x18011af9b  mov     [rsp+6E0h+phkResult], rax
0x18011afa0  mov     edx, 104h; unsigned __int64
0x18011afa5  lea     r8, aSS_2; "%s\\%s"
0x18011afac  lea     rcx, [rbp+5E0h+SubKey]; unsigned __int16 *
0x18011afb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18011afb8  mov     ebx, eax
0x18011afba  test    eax, eax
0x18011afbc  js      loc_18011B24A
0x18011afc2  lea     rax, [rsp+6E0h+hKey]
0x18011afc7  mov     [rsp+6E0h+hKey], 0
0x18011afd0  mov     r9d, 20019h; samDesired
0x18011afd6  mov     [rsp+6E0h+phkResult], rax; phkResult
0x18011afdb  xor     r8d, r8d; ulOptions
0x18011afde  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x18011afe5  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18011afec  call    cs:__imp_RegOpenKeyExW
0x18011aff3  nop     dword ptr [rax+rax+00h]
0x18011aff8  mov     ebx, eax
0x18011affa  mov     edi, 80070000h
0x18011afff  test    eax, eax
0x18011b001  jle     short loc_18011B008
0x18011b003  movzx   ebx, ax
0x18011b006  or      ebx, edi
0x18011b008  test    ebx, ebx
0x18011b00a  js      loc_18011B23F
0x18011b010  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18011b015  lea     rax, [rsp+6E0h+cSubKeys]
0x18011b01a  mov     [rsp+6E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18011b023  xor     r9d, r9d; lpReserved
0x18011b026  mov     [rsp+6E0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18011b02f  xor     r8d, r8d; lpcchClass
0x18011b032  mov     [rsp+6E0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18011b03b  xor     edx, edx; lpClass
0x18011b03d  mov     [rsp+6E0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18011b046  mov     [rsp+6E0h+lpcValues], 0; lpcValues
0x18011b04f  mov     [rsp+6E0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18011b058  mov     [rsp+6E0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18011b061  mov     [rsp+6E0h+phkResult], rax; lpcSubKeys
0x18011b066  mov     [rsp+6E0h+cSubKeys], 0
0x18011b06e  call    cs:__imp_RegQueryInfoKeyW
0x18011b075  nop     dword ptr [rax+rax+00h]
0x18011b07a  mov     ebx, eax
0x18011b07c  test    eax, eax
0x18011b07e  jle     short loc_18011B085
0x18011b080  movzx   ebx, ax
0x18011b083  or      ebx, edi
0x18011b085  test    ebx, ebx
0x18011b087  js      loc_18011B22C
0x18011b08d  xor     edi, edi
0x18011b08f  cmp     edi, [rsp+6E0h+cSubKeys]
0x18011b093  jnb     loc_18011B22C
0x18011b099  cmp     [rbp+5E0h+arg_20], 1
0x18011b0a0  jnz     short loc_18011B0A9
0x18011b0a2  mov     eax, 1
0x18011b0a7  jmp     short loc_18011B0B8
0x18011b0a9  xor     eax, eax
0x18011b0ab  cmp     [rbp+5E0h+arg_20], 2
0x18011b0b2  lea     ecx, [rax+7]
0x18011b0b5  cmovz   eax, ecx
0x18011b0b8  cmp     edi, eax
0x18011b0ba  jnb     loc_18011B22C
0x18011b0c0  mov     rcx, [rsp+6E0h+hKey]; hkey
0x18011b0c5  lea     r9, [rsp+6E0h+pcchName]; pcchName
0x18011b0ca  lea     r8, [rbp+5E0h+pszName]; pszName
0x18011b0ce  mov     [rsp+6E0h+pcchName], 104h
0x18011b0d6  mov     edx, edi; dwIndex
0x18011b0d8  call    cs:__imp_SHEnumKeyExW
0x18011b0df  nop     dword ptr [rax+rax+00h]
0x18011b0e4  mov     ebx, eax
0x18011b0e6  test    eax, eax
0x18011b0e8  jle     short loc_18011B0F3
0x18011b0ea  movzx   ebx, ax
0x18011b0ed  or      ebx, 80070000h
0x18011b0f3  test    ebx, ebx
0x18011b0f5  js      loc_18011B222
0x18011b0fb  or      eax, 0FFFFFFFFh
0x18011b0fe  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x18011b106  mov     r9d, eax; cchCount2
0x18011b109  lea     rcx, [rbp+5E0h+pszName]; lpString1
0x18011b10d  mov     edx, eax; cchCount1
0x18011b10f  mov     r8, r12; lpString2
0x18011b112  call    cs:__imp_CompareStringOrdinal
0x18011b119  nop     dword ptr [rax+rax+00h]
0x18011b11e  cmp     eax, 2
0x18011b121  jz      loc_18011B219
0x18011b127  test    r15, r15
0x18011b12a  jz      short loc_18011B158
0x18011b12c  or      eax, 0FFFFFFFFh
0x18011b12f  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x18011b137  mov     r9d, eax; cchCount2
0x18011b13a  lea     rcx, [rbp+5E0h+pszName]; lpString1
0x18011b13e  mov     edx, eax; cchCount1
0x18011b140  mov     r8, r15; lpString2
0x18011b143  call    cs:__imp_CompareStringOrdinal
0x18011b14a  nop     dword ptr [rax+rax+00h]
0x18011b14f  cmp     eax, 2
0x18011b152  jz      loc_18011B219
0x18011b158  mov     rcx, [rsp+6E0h+hKey]; hkey
0x18011b15d  lea     rax, [rsp+6E0h+pcbData]
0x18011b162  mov     [rsp+6E0h+lpcbMaxClassLen], rax; pcbData
0x18011b167  lea     r8, aParentappid; "ParentAppId"
0x18011b16e  lea     rax, [rbp+5E0h+pvData]
0x18011b175  mov     [rsp+6E0h+pcbData], 208h
0x18011b17d  mov     [rsp+6E0h+lpcbMaxSubKeyLen], rax; pvData
0x18011b182  lea     rdx, [rbp+5E0h+pszName]; lpSubKey
0x18011b186  mov     r9d, 2; dwFlags
0x18011b18c  mov     [rsp+6E0h+phkResult], 0; pdwType
0x18011b195  call    cs:__imp_RegGetValueW
0x18011b19c  nop     dword ptr [rax+rax+00h]
0x18011b1a1  test    eax, eax
0x18011b1a3  jz      short loc_18011B1BC
0x18011b1a5  xor     ecx, ecx
0x18011b1a7  mov     [rbp+5E0h+pvData], cx
0x18011b1ae  test    eax, eax
0x18011b1b0  jle     short loc_18011B1BC
0x18011b1b2  movzx   eax, ax
0x18011b1b5  or      eax, 80070000h
0x18011b1ba  test    eax, eax
0x18011b1bc  js      short loc_18011B222
0x18011b1be  or      eax, 0FFFFFFFFh
0x18011b1c1  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x18011b1c9  mov     r9d, eax; cchCount2
0x18011b1cc  lea     rcx, [rbp+5E0h+pvData]; lpString1
0x18011b1d3  mov     edx, eax; cchCount1
0x18011b1d5  mov     r8, r12; lpString2
0x18011b1d8  call    cs:__imp_CompareStringOrdinal
0x18011b1df  nop     dword ptr [rax+rax+00h]
0x18011b1e4  cmp     eax, 2
0x18011b1e7  jz      short loc_18011B219
0x18011b1e9  test    r15, r15
0x18011b1ec  jz      short loc_18011B222
0x18011b1ee  or      eax, 0FFFFFFFFh
0x18011b1f1  mov     dword ptr [rsp+6E0h+phkResult], 1; bIgnoreCase
0x18011b1f9  mov     r9d, eax; cchCount2
0x18011b1fc  lea     rcx, [rbp+5E0h+pvData]; lpString1
0x18011b203  mov     edx, eax; cchCount1
0x18011b205  mov     r8, r15; lpString2
0x18011b208  call    cs:__imp_CompareStringOrdinal
0x18011b20f  nop     dword ptr [rax+rax+00h]
0x18011b214  cmp     eax, 2
0x18011b217  jnz     short loc_18011B222
0x18011b219  inc     dword ptr [rsi]
0x18011b21b  inc     edi
0x18011b21d  jmp     loc_18011B08F
0x18011b222  inc     edi
0x18011b224  test    ebx, ebx
0x18011b226  jns     loc_18011B08F
0x18011b22c  mov     rcx, [rsp+6E0h+hKey]; hKey
0x18011b231  call    cs:__imp_RegCloseKey
0x18011b238  nop     dword ptr [rax+rax+00h]
0x18011b23d  jmp     short loc_18011B24A
0x18011b23f  xor     eax, eax
0x18011b241  cmp     ebx, 80070002h
0x18011b247  cmovz   ebx, eax
0x18011b24a  mov     eax, ebx
0x18011b24c  mov     rcx, [rbp+5E0h+var_30]
0x18011b253  xor     rcx, rsp; StackCookie
0x18011b256  call    __security_check_cookie
0x18011b25b  mov     rbx, [rsp+6E0h+arg_0]
0x18011b263  add     rsp, 6C0h
0x18011b26a  pop     r15
0x18011b26c  pop     r12
0x18011b26e  pop     rdi
0x18011b26f  pop     rsi
0x18011b270  pop     rbp
0x18011b271  retn
```
