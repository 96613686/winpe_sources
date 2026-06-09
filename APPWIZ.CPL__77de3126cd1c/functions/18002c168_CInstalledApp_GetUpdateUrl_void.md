# CInstalledApp::_GetUpdateUrl(void)

- ea: `0x18002c168`
- end: `0x18002c2db`
- name: `?_GetUpdateUrl@CInstalledApp@@AEAAXXZ`
- size: `371`
- prototype: `void __fastcall(CInstalledApp *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180029da8`
- `0x18002a058`

## callees

- `0x180007960`
- `0x18000b2dc`
- `0x18002c168`
- `0x180044bd8`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHQueryValueExW` at `0x18002c216`
- `SHCORE!SHQueryValueExW` at `0x18002c288`
- `SHCORE!SHQueryValueExW` at `0x18002c216`
- `SHCORE!SHQueryValueExW` at `0x18002c288`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c1df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c1df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2b4`

## string_xrefs

- `0x18002c1f2`: `URLUpdateInfo`
- `0x18002c1a4`: `Software\Installer\Products\%s`

## pseudocode

```c
void __fastcall CInstalledApp::_GetUpdateUrl(CInstalledApp *this)
{
  unsigned __int128 v2; // rax
  void *v3; // rax
  void *v4; // rcx
  void *v5; // rbx
  HKEY v6; // rcx
  void *v7; // rcx
  DWORD pcbData; // [rsp+30h] [rbp-238h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  hkey = 0;
  if ( StringCchPrintfW(SubKey, 0x104u, L"Software\\Installer\\Products\\%s", (char *)this + 4196) >= 0
    && !RegOpenKeyExW((HKEY)(((*((_DWORD *)this + 7) & 1) == 0) - 0x7FFFFFFFLL), SubKey, 0, 0x20019u, &hkey) )
  {
    pcbData = 0;
    if ( !SHQueryValueExW(hkey, L"URLUpdateInfo", 0, 0, 0, &pcbData) )
    {
      v2 = ((unsigned __int64)pcbData >> 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
        *(_QWORD *)&v2 = -1;
      v3 = DirectUI::HAllocAndZero((DirectUI *)v2, *((unsigned __int64 *)&v2 + 1));
      v4 = (void *)*((_QWORD *)this + 535);
      v5 = v3;
      *((_QWORD *)this + 535) = 0;
      operator delete(v4);
      v6 = hkey;
      *((_QWORD *)this + 535) = v5;
      if ( SHQueryValueExW(v6, &WindowName, 0, 0, v5, &pcbData) )
      {
        v7 = (void *)*((_QWORD *)this + 535);
        *((_QWORD *)this + 535) = 0;
        operator delete(v7);
      }
      else
      {
        *((_DWORD *)this + 6) |= 0x10u;
      }
    }
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x18002c168  mov     [rsp+arg_8], rbx
0x18002c16d  push    rdi
0x18002c16e  sub     rsp, 260h
0x18002c175  mov     rax, cs:__security_cookie
0x18002c17c  xor     rax, rsp
0x18002c17f  mov     [rsp+268h+var_18], rax
0x18002c187  mov     rdi, rcx
0x18002c18a  mov     [rsp+268h+hkey], 0
0x18002c193  lea     r9, [rcx+1064h]
0x18002c19a  mov     edx, 104h; unsigned __int64
0x18002c19f  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18002c1a4  lea     r8, aSoftwareInstal; "Software\\Installer\\Products\\%s"
0x18002c1ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c1b0  test    eax, eax
0x18002c1b2  js      loc_18002C2BA
0x18002c1b8  mov     ecx, [rdi+1Ch]
0x18002c1bb  lea     rax, [rsp+268h+hkey]
0x18002c1c0  not     ecx
0x18002c1c2  mov     [rsp+268h+phkResult], rax; phkResult
0x18002c1c7  and     ecx, 1
0x18002c1ca  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002c1cf  sub     rcx, 7FFFFFFFh; hKey
0x18002c1d6  mov     r9d, 20019h; samDesired
0x18002c1dc  xor     r8d, r8d; ulOptions
0x18002c1df  call    cs:__imp_RegOpenKeyExW
0x18002c1e5  test    eax, eax
0x18002c1e7  jnz     loc_18002C2BA
0x18002c1ed  mov     rcx, [rsp+268h+hkey]; hkey
0x18002c1f2  lea     rdx, aUrlupdateinfo_0; "URLUpdateInfo"
0x18002c1f9  mov     [rsp+268h+var_238], eax
0x18002c1fd  xor     r9d, r9d; pdwType
0x18002c200  lea     rax, [rsp+268h+var_238]
0x18002c205  xor     r8d, r8d; pdwReserved
0x18002c208  mov     [rsp+268h+pcbData], rax; pcbData
0x18002c20d  mov     [rsp+268h+phkResult], 0; pvData
0x18002c216  call    cs:__imp_SHQueryValueExW
0x18002c21c  test    eax, eax
0x18002c21e  jnz     loc_18002C2AF
0x18002c224  mov     ecx, [rsp+268h+var_238]
0x18002c228  mov     eax, 2
0x18002c22d  shr     rcx, 1
0x18002c230  mul     rcx
0x18002c233  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c23a  cmovb   rax, rcx
0x18002c23e  mov     rcx, rax; this
0x18002c241  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18002c246  mov     rcx, [rdi+10B8h]; lpMem
0x18002c24d  mov     rbx, rax
0x18002c250  mov     qword ptr [rdi+10B8h], 0
0x18002c25b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c260  mov     rcx, [rsp+268h+hkey]; hkey
0x18002c265  lea     rax, [rsp+268h+var_238]
0x18002c26a  mov     [rsp+268h+pcbData], rax; pcbData
0x18002c26f  lea     rdx, WindowName; pszValue
0x18002c276  xor     r9d, r9d; pdwType
0x18002c279  mov     [rsp+268h+phkResult], rbx; pvData
0x18002c27e  xor     r8d, r8d; pdwReserved
0x18002c281  mov     [rdi+10B8h], rbx
0x18002c288  call    cs:__imp_SHQueryValueExW
0x18002c28e  test    eax, eax
0x18002c290  jz      short loc_18002C2AB
0x18002c292  mov     rcx, [rdi+10B8h]; lpMem
0x18002c299  mov     qword ptr [rdi+10B8h], 0
0x18002c2a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c2a9  jmp     short loc_18002C2AF
0x18002c2ab  or      dword ptr [rdi+18h], 10h
0x18002c2af  mov     rcx, [rsp+268h+hkey]; hKey
0x18002c2b4  call    cs:__imp_RegCloseKey
0x18002c2ba  mov     rcx, [rsp+268h+var_18]
0x18002c2c2  xor     rcx, rsp; StackCookie
0x18002c2c5  call    __security_check_cookie
0x18002c2ca  mov     rbx, [rsp+268h+arg_8]
0x18002c2d2  add     rsp, 260h
0x18002c2d9  pop     rdi
0x18002c2da  retn
```
