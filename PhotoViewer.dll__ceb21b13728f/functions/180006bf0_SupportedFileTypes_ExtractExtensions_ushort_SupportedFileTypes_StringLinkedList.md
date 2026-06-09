# SupportedFileTypes::ExtractExtensions(ushort *,SupportedFileTypes::StringLinkedList *)

- ea: `0x180006bf0`
- end: `0x180006f9f`
- name: `?ExtractExtensions@SupportedFileTypes@@CAJPEAGPEAVStringLinkedList@1@@Z`
- size: `943`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct SupportedFileTypes::StringLinkedList *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006a20`

## callees

- `0x180006bf0`
- `0x180006fb0`
- `0x180007290`
- `0x18003f800`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180006c23`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180006d12`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180006c23`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180006d12`
- `KERNEL32!lstrlenW` at `0x180006f3e`
- `KERNEL32!lstrlenW` at `0x180006f3e`
- `KERNEL32!CompareStringW` at `0x180006dc9`
- `KERNEL32!CompareStringW` at `0x180006e50`
- `KERNEL32!CompareStringW` at `0x180006dc9`
- `KERNEL32!CompareStringW` at `0x180006e50`
- `KERNEL32!LocalAlloc` at `0x180006e89`
- `KERNEL32!LocalAlloc` at `0x180006f18`
- `KERNEL32!LocalAlloc` at `0x180006e89`
- `KERNEL32!LocalAlloc` at `0x180006f18`
- `ADVAPI32!RegQueryValueExW` at `0x180006cf1`
- `ADVAPI32!RegQueryValueExW` at `0x180006cf1`
- `ADVAPI32!RegCloseKey` at `0x180006d00`
- `ADVAPI32!RegCloseKey` at `0x180006d90`
- `ADVAPI32!RegCloseKey` at `0x180006d00`
- `ADVAPI32!RegCloseKey` at `0x180006d90`
- `ADVAPI32!RegOpenKeyExW` at `0x180006caf`
- `ADVAPI32!RegOpenKeyExW` at `0x180006caf`
- `ole32!CLSIDFromString` at `0x180006d7d`
- `ole32!CLSIDFromString` at `0x180006d7d`

## pseudocode

```c
__int64 __fastcall SupportedFileTypes::ExtractExtensions(
        unsigned __int16 *a1,
        struct SupportedFileTypes::StringLinkedList *a2)
{
  int v3; // ebp
  wchar_t *v4; // rdi
  __int64 i; // rbx
  int v7; // eax
  __int64 v8; // rsi
  __int64 v9; // rbx
  _WORD *v10; // rax
  wchar_t *v11; // rdx
  _WORD *v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  _QWORD *v15; // rax
  _DWORD *v16; // r14
  int v17; // eax
  DWORD Type; // [rsp+30h] [rbp-698h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-690h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-688h] BYREF
  CLSID pclsid; // [rsp+48h] [rbp-680h] BYREF
  OLECHAR Data[264]; // [rsp+60h] [rbp-668h] BYREF
  WCHAR SubKey[520]; // [rsp+270h] [rbp-458h] BYREF

  v3 = 0;
  v4 = wcstok(a1, L",", 0);
  if ( v4 )
  {
    while ( 1 )
    {
      if ( v3 < 0 )
        return (unsigned int)v3;
      if ( (int)StringCchPrintfW(
                  SubKey,
                  0x208u,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\PropertyHandlers\\%ws",
                  v4) >= 0 )
      {
        hKey = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
        {
          Type = 1;
          cbData = 520;
          if ( RegQueryValueExW(hKey, &WindowName, 0, &Type, (LPBYTE)Data, &cbData)
            || Type != 1
            || (pclsid = 0, CLSIDFromString(Data, &pclsid) < 0) )
          {
            RegCloseKey(hKey);
          }
          else
          {
            RegCloseKey(hKey);
            for ( i = *(_QWORD *)a2; i; i = *(_QWORD *)(i + 16) )
            {
              v7 = CompareStringW(0x400u, 1u, *(PCNZWCH *)i, -1, v4, -1);
              if ( v7 != 1 )
              {
                if ( v7 == 2 )
                {
                  *(_DWORD *)(i + 8) |= 1u;
                  v3 = 0;
                  goto LABEL_7;
                }
                break;
              }
            }
            v15 = LocalAlloc(0x40u, 0x18u);
            v16 = v15;
            if ( v15 )
            {
              *v15 = 0;
              *((_DWORD *)v15 + 2) = 0;
              v15[2] = 0;
              v17 = lstrlenW(v4);
              if ( v17 )
              {
                v14 = v17 + 1LL;
                if ( v14 >= v17 && 2 * (unsigned __int64)(unsigned int)v14 <= 0xFFFFFFFF )
                {
                  v10 = LocalAlloc(0x40u, (unsigned int)(2 * v14));
                  *(_QWORD *)v16 = v10;
                  v12 = v10;
                  if ( v10 )
                  {
                    if ( v14 )
                    {
                      if ( v14 > 0x7FFFFFFF )
                      {
                        v3 = -2147024809;
                        *v10 = 0;
                      }
                      else
                      {
                        v13 = 2147483646;
                        v11 = v4;
                        v3 = 0;
                        while ( v13 && *v11 )
                        {
                          *v12++ = *v11++;
                          --v13;
                          if ( !--v14 )
                          {
                            --v12;
                            v3 = -2147024774;
                            break;
                          }
                        }
                        *v12 = 0;
                      }
                    }
                    else
                    {
                      v3 = -2147024809;
                    }
                  }
                  else
                  {
                    v3 = -2147024882;
                  }
                }
                else
                {
                  v3 = -2147024362;
                }
                if ( v3 >= 0 )
                {
                  v16[2] = 1;
                  v8 = 0;
                  v9 = *(_QWORD *)a2;
                  if ( !*(_QWORD *)a2 )
                    goto LABEL_35;
                  do
                  {
                    if ( CompareStringW(0x400u, 1u, *(PCNZWCH *)v9, -1, v4, -1) != 1 )
                      break;
                    v8 = v9;
                    v9 = *(_QWORD *)(v9 + 16);
                  }
                  while ( v9 );
                  if ( v8 )
                  {
                    *((_QWORD *)v16 + 2) = *(_QWORD *)(v8 + 16);
                    *(_QWORD *)(v8 + 16) = v16;
                  }
                  else
                  {
LABEL_35:
                    *((_QWORD *)v16 + 2) = *(_QWORD *)a2;
                    *(_QWORD *)a2 = v16;
                  }
                  goto LABEL_7;
                }
              }
              else
              {
                v3 = -2147024809;
              }
              SupportedFileTypes::StringLinkedList::Node::`scalar deleting destructor'(v16, (unsigned int)v11);
            }
            else
            {
              v3 = -2147024882;
            }
          }
        }
      }
LABEL_7:
      v4 = wcstok(0, L",", 0);
      if ( !v4 )
        return (unsigned int)v3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006bf0  push    rbp
0x180006bf2  push    rdi
0x180006bf3  push    r12
0x180006bf5  push    r15
0x180006bf7  sub     rsp, 6A8h
0x180006bfe  mov     rax, cs:__security_cookie
0x180006c05  xor     rax, rsp
0x180006c08  mov     [rsp+6C8h+var_48], rax
0x180006c10  mov     r15, rdx
0x180006c13  xor     r12d, r12d
0x180006c16  lea     rdx, Delimiter; ","
0x180006c1d  xor     r8d, r8d; Context
0x180006c20  mov     ebp, r12d
0x180006c23  call    cs:__imp_wcstok
0x180006c29  mov     rdi, rax
0x180006c2c  test    rax, rax
0x180006c2f  jz      loc_180006DF0
0x180006c35  mov     [rsp+6C8h+arg_10], rbx
0x180006c3d  mov     [rsp+6C8h+var_28], rsi
0x180006c45  mov     [rsp+6C8h+var_30], r13
0x180006c4d  mov     r13d, 0FFFFFFFFh
0x180006c53  mov     [rsp+6C8h+var_38], r14
0x180006c5b  nop     dword ptr [rax+rax+00h]
0x180006c60  test    ebp, ebp
0x180006c62  js      loc_180006D24
0x180006c68  mov     r9, rdi
0x180006c6b  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006c72  mov     edx, 208h; unsigned __int64
0x180006c77  lea     rcx, [rsp+6C8h+SubKey]; unsigned __int16 *
0x180006c7f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006c84  test    eax, eax
0x180006c86  js      short loc_180006D06
0x180006c88  lea     rax, [rsp+6C8h+hKey]
0x180006c8d  mov     [rsp+6C8h+hKey], r12
0x180006c92  mov     r9d, 20019h; samDesired
0x180006c98  mov     [rsp+6C8h+phkResult], rax; phkResult
0x180006c9d  xor     r8d, r8d; ulOptions
0x180006ca0  lea     rdx, [rsp+6C8h+SubKey]; lpSubKey
0x180006ca8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006caf  call    cs:__imp_RegOpenKeyExW
0x180006cb5  test    eax, eax
0x180006cb7  jnz     short loc_180006D06
0x180006cb9  mov     rcx, [rsp+6C8h+hKey]; hKey
0x180006cbe  lea     rax, [rsp+6C8h+cbData]
0x180006cc3  mov     [rsp+6C8h+lpcbData], rax; lpcbData
0x180006cc8  lea     r9, [rsp+6C8h+Type]; lpType
0x180006ccd  lea     rax, [rsp+6C8h+Data]
0x180006cd2  mov     [rsp+6C8h+Type], 1
0x180006cda  xor     r8d, r8d; lpReserved
0x180006cdd  mov     [rsp+6C8h+phkResult], rax; lpData
0x180006ce2  lea     rdx, WindowName; lpValueName
0x180006ce9  mov     [rsp+6C8h+cbData], 208h
0x180006cf1  call    cs:__imp_RegQueryValueExW
0x180006cf7  test    eax, eax
0x180006cf9  jz      short loc_180006D64
0x180006cfb  mov     rcx, [rsp+6C8h+hKey]; hKey
0x180006d00  call    cs:__imp_RegCloseKey
0x180006d06  xor     r8d, r8d; Context
0x180006d09  lea     rdx, Delimiter; ","
0x180006d10  xor     ecx, ecx; String
0x180006d12  call    cs:__imp_wcstok
0x180006d18  mov     rdi, rax
0x180006d1b  test    rax, rax
0x180006d1e  jnz     loc_180006C60
0x180006d24  mov     r14, [rsp+6C8h+var_38]
0x180006d2c  mov     eax, ebp
0x180006d2e  mov     rsi, [rsp+6C8h+var_28]
0x180006d36  mov     rbx, [rsp+6C8h+arg_10]
0x180006d3e  mov     r13, [rsp+6C8h+var_30]
0x180006d46  mov     rcx, [rsp+6C8h+var_48]
0x180006d4e  xor     rcx, rsp; StackCookie
0x180006d51  call    __security_check_cookie
0x180006d56  add     rsp, 6A8h
0x180006d5d  pop     r15
0x180006d5f  pop     r12
0x180006d61  pop     rdi
0x180006d62  pop     rbp
0x180006d63  retn
0x180006d64  cmp     [rsp+6C8h+Type], 1
0x180006d69  jnz     short loc_180006CFB
0x180006d6b  xorps   xmm0, xmm0
0x180006d6e  lea     rdx, [rsp+6C8h+pclsid]; pclsid
0x180006d73  lea     rcx, [rsp+6C8h+Data]; lpsz
0x180006d78  movups  xmmword ptr [rsp+6C8h+pclsid.Data1], xmm0
0x180006d7d  call    cs:__imp_CLSIDFromString
0x180006d83  test    eax, eax
0x180006d85  js      loc_180006CFB
0x180006d8b  mov     rcx, [rsp+6C8h+hKey]; hKey
0x180006d90  call    cs:__imp_RegCloseKey
0x180006d96  mov     rbx, [r15]
0x180006d99  nop     dword ptr [rax+00000000h]
0x180006da0  test    rbx, rbx
0x180006da3  jz      loc_180006F0E
0x180006da9  mov     r8, [rbx]; lpString1
0x180006dac  mov     r9d, 0FFFFFFFFh; cchCount1
0x180006db2  mov     dword ptr [rsp+6C8h+lpcbData], 0FFFFFFFFh; cchCount2
0x180006dba  mov     edx, 1; dwCmpFlags
0x180006dbf  mov     ecx, 400h; Locale
0x180006dc4  mov     [rsp+6C8h+phkResult], rdi; lpString2
0x180006dc9  call    cs:__imp_CompareStringW
0x180006dcf  mov     ecx, eax
0x180006dd1  sub     ecx, 1
0x180006dd4  jnz     short loc_180006DDC
0x180006dd6  mov     rbx, [rbx+10h]
0x180006dda  jmp     short loc_180006DA0
0x180006ddc  cmp     ecx, 1
0x180006ddf  jnz     loc_180006F0E
0x180006de5  or      [rbx+8], ecx
0x180006de8  mov     ebp, r12d
0x180006deb  jmp     loc_180006D06
0x180006df0  mov     eax, r12d
0x180006df3  jmp     loc_180006D46
0x180006df8  mov     eax, ebx
0x180006dfa  add     rax, rax
0x180006dfd  mov     ecx, ebx
0x180006dff  cmp     rax, r13
0x180006e02  jbe     short loc_180006E81
0x180006e04  mov     ebp, 80070216h
0x180006e09  test    ebp, ebp
0x180006e0b  js      loc_180006F62
0x180006e11  mov     dword ptr [r14+8], 1
0x180006e19  mov     rsi, r12
0x180006e1c  mov     rbx, [r15]
0x180006e1f  test    rbx, rbx
0x180006e22  jz      loc_180006EFF
0x180006e28  nop     dword ptr [rax+rax+00000000h]
0x180006e30  mov     r8, [rbx]; lpString1
0x180006e33  mov     r9d, 0FFFFFFFFh; cchCount1
0x180006e39  mov     dword ptr [rsp+6C8h+lpcbData], 0FFFFFFFFh; cchCount2
0x180006e41  mov     edx, 1; dwCmpFlags
0x180006e46  mov     ecx, 400h; Locale
0x180006e4b  mov     [rsp+6C8h+phkResult], rdi; lpString2
0x180006e50  call    cs:__imp_CompareStringW
0x180006e56  cmp     eax, 1
0x180006e59  jnz     short loc_180006E67
0x180006e5b  mov     rsi, rbx
0x180006e5e  mov     rbx, [rbx+10h]
0x180006e62  test    rbx, rbx
0x180006e65  jnz     short loc_180006E30
0x180006e67  test    rsi, rsi
0x180006e6a  jz      loc_180006EFF
0x180006e70  mov     rax, [rsi+10h]
0x180006e74  mov     [r14+10h], rax
0x180006e78  mov     [rsi+10h], r14
0x180006e7c  jmp     loc_180006D06
0x180006e81  lea     edx, [rcx+rcx]; uBytes
0x180006e84  mov     ecx, 40h ; '@'; uFlags
0x180006e89  call    cs:__imp_LocalAlloc
0x180006e8f  mov     [r14], rax
0x180006e92  mov     rcx, rax
0x180006e95  test    rax, rax
0x180006e98  jz      short loc_180006EF5
0x180006e9a  test    rbx, rbx
0x180006e9d  jz      loc_180006F88
0x180006ea3  cmp     rbx, 7FFFFFFFh
0x180006eaa  ja      loc_180006F81
0x180006eb0  mov     eax, 7FFFFFFEh
0x180006eb5  mov     rdx, rdi
0x180006eb8  mov     ebp, r12d
0x180006ebb  test    rax, rax
0x180006ebe  jz      loc_180006F78
0x180006ec4  movzx   r8d, word ptr [rdx]
0x180006ec8  test    r8w, r8w
0x180006ecc  jz      loc_180006F6F
0x180006ed2  mov     [rcx], r8w
0x180006ed6  add     rdx, 2
0x180006eda  add     rcx, 2
0x180006ede  dec     rax
0x180006ee1  sub     rbx, 1
0x180006ee5  jnz     short loc_180006EBB
0x180006ee7  sub     rcx, 2
0x180006eeb  mov     ebp, 8007007Ah
0x180006ef0  jmp     loc_180006F78
0x180006ef5  mov     ebp, 8007000Eh
0x180006efa  jmp     loc_180006E09
0x180006eff  mov     rax, [r15]
0x180006f02  mov     [r14+10h], rax
0x180006f06  mov     [r15], r14
0x180006f09  jmp     loc_180006D06
0x180006f0e  mov     edx, 18h; uBytes
0x180006f13  mov     ecx, 40h ; '@'; uFlags
0x180006f18  call    cs:__imp_LocalAlloc
0x180006f1e  mov     r14, rax
0x180006f21  test    rax, rax
0x180006f24  jnz     short loc_180006F30
0x180006f26  mov     ebp, 8007000Eh
0x180006f2b  jmp     loc_180006D06
0x180006f30  mov     rcx, rdi; lpString
0x180006f33  mov     [rax], r12
0x180006f36  mov     [rax+8], r12d
0x180006f3a  mov     [rax+10h], r12
0x180006f3e  call    cs:__imp_lstrlenW
0x180006f44  movsxd  rcx, eax
0x180006f47  test    eax, eax
0x180006f49  jz      short loc_180006F5D
0x180006f4b  lea     rbx, [rcx+1]
0x180006f4f  cmp     rbx, rcx
0x180006f52  jb      loc_180006E04
0x180006f58  jmp     loc_180006DF8
0x180006f5d  mov     ebp, 80070057h
0x180006f62  mov     rcx, r14; hMem
0x180006f65  call    ??_GNode@StringLinkedList@SupportedFileTypes@@QEAAPEAXI@Z; SupportedFileTypes::StringLinkedList::Node::`scalar deleting destructor'(uint)
0x180006f6a  jmp     loc_180006D06
0x180006f6f  test    rbx, rbx
0x180006f72  jz      loc_180006EE7
0x180006f78  mov     [rcx], r12w
0x180006f7c  jmp     loc_180006E09
0x180006f81  mov     ebp, 80070057h
0x180006f86  jmp     short loc_180006F96
0x180006f88  mov     ebp, 80070057h
0x180006f8d  test    rbx, rbx
0x180006f90  jz      loc_180006E09
0x180006f96  mov     [rax], r12w
0x180006f9a  jmp     loc_180006E09
```
