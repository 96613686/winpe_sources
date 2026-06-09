# ReadContextStringFromRegistry

- ea: `0x18002b9d0`
- end: `0x18002bc54`
- name: `ReadContextStringFromRegistry`
- size: `644`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpString@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b1a4`

## callees

- `0x18000de80`
- `0x180019430`
- `0x18001c71c`
- `0x18001c7a8`
- `0x18002b898`
- `0x18002b924`
- `0x18002b9d0`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bad7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bad7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bb61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002ba22`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002ba2d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002bb9f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002ba22`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002ba2d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002bb9f`

## pseudocode

```c
__int64 __fastcall ReadContextStringFromRegistry(
        LPCWSTR lpString,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        wchar_t **a5)
{
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  size_t v12; // rbx
  wchar_t *v13; // rax
  const WCHAR *v14; // r14
  unsigned int v15; // ebx
  wchar_t *v16; // rdi
  size_t v17; // rcx
  BYTE *v18; // rsi
  const wchar_t *v19; // rbx
  unsigned int v20; // eax
  unsigned __int64 v21; // rax
  size_t v22; // r15
  wchar_t *v23; // rax
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpStringa; // [rsp+40h] [rbp-30h] BYREF
  wchar_t pszDest[8]; // [rsp+48h] [rbp-28h] BYREF
  int v30; // [rsp+58h] [rbp-18h]

  v30 = 0;
  hKey = 0;
  cbData = 0;
  *(_OWORD *)pszDest = 0;
  Type = 0;
  lpStringa = 0;
  v7 = lstrlenW(L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards");
  v8 = lstrlenW(lpString);
  v9 = v8 + v7;
  if ( v8 + v7 < v8 || (v10 = v9 + 2, (unsigned int)v10 < v9) || (v11 = 2 * v10, v11 > 0xFFFFFFFF) )
  {
    v15 = -2147024362;
  }
  else
  {
    v12 = (unsigned int)v11;
    v13 = (wchar_t *)MIDL_user_allocate((unsigned int)v11);
    v14 = v13;
    if ( v13 )
    {
      v16 = 0;
      v15 = StringCbPrintfW(v13, v12, L"%s\\%s", L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\SmartCards", lpString);
      if ( !v15 )
      {
        v15 = StringCchPrintfW(pszDest, 0xAu, L"%x", a2);
        if ( !v15 )
        {
          v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 1u, &hKey);
          if ( !v15 )
          {
            v15 = RegQueryValueExW(hKey, pszDest, 0, &Type, 0, &cbData);
            if ( !v15 )
            {
              if ( Type == 1 )
              {
                v17 = cbData + 2;
                if ( (unsigned int)v17 < cbData )
                {
                  v15 = -2147024362;
                }
                else
                {
                  v18 = (BYTE *)MIDL_user_allocate(v17);
                  if ( v18 )
                  {
                    v15 = RegQueryValueExW(hKey, pszDest, 0, 0, v18, &cbData);
                    if ( !v15 )
                    {
                      *(_WORD *)&v18[2 * ((unsigned __int64)cbData >> 1)] = 0;
                      I_GetLocalizedString(v18, cbData >> 1, &lpStringa);
                      v19 = lpStringa;
                      if ( lpStringa )
                      {
                        v20 = lstrlenW(lpStringa);
                        if ( v20 + 1 < v20 || (v21 = 2LL * (v20 + 1), v21 > 0xFFFFFFFF) )
                        {
                          v15 = -2147024362;
                        }
                        else
                        {
                          v22 = (unsigned int)v21;
                          v23 = (wchar_t *)MIDL_user_allocate((unsigned int)v21);
                          v16 = v23;
                          if ( v23 )
                          {
                            v15 = StringCchCopyW(v23, v22, v19);
                            if ( !v15 )
                            {
                              *a5 = v16;
                              v16 = 0;
                            }
                          }
                          else
                          {
                            v15 = 8;
                          }
                        }
                      }
                      else
                      {
                        v15 = 1168;
                      }
                    }
                    CspFreeH(v18);
                  }
                  else
                  {
                    v15 = 8;
                  }
                }
              }
              else
              {
                v15 = 13;
              }
            }
          }
        }
      }
      CspFreeH(v14);
      if ( v16 )
        CspFreeH(v16);
    }
    else
    {
      v15 = 8;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v15;
}

```

## disassembly

```asm
0x18002b9d0  mov     [rsp-28h+arg_10], rbx
0x18002b9d5  mov     [rsp-28h+arg_18], rsi
0x18002b9da  push    rbp
0x18002b9db  push    rdi
0x18002b9dc  push    r12
0x18002b9de  push    r14
0x18002b9e0  push    r15
0x18002b9e2  mov     rbp, rsp
0x18002b9e5  sub     rsp, 70h
0x18002b9e9  mov     rax, cs:__security_cookie
0x18002b9f0  xor     rax, rsp
0x18002b9f3  mov     [rbp+var_10], rax
0x18002b9f7  mov     r12, [rbp+arg_20]
0x18002b9fb  xor     eax, eax
0x18002b9fd  mov     rsi, rcx
0x18002ba00  mov     [rbp+var_18], eax
0x18002ba03  xorps   xmm0, xmm0
0x18002ba06  mov     [rbp+hKey], rax
0x18002ba0a  lea     rcx, String; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002ba11  mov     [rbp+cbData], eax
0x18002ba14  movups  xmmword ptr [rbp+pszDest], xmm0
0x18002ba18  mov     [rbp+Type], eax
0x18002ba1b  mov     r15d, edx
0x18002ba1e  mov     [rbp+lpString], rax
0x18002ba22  call    cs:__imp_lstrlenW
0x18002ba28  mov     rcx, rsi; lpString
0x18002ba2b  mov     ebx, eax
0x18002ba2d  call    cs:__imp_lstrlenW
0x18002ba33  lea     ecx, [rax+rbx]
0x18002ba36  cmp     ecx, eax
0x18002ba38  jb      loc_18002BC19
0x18002ba3e  lea     eax, [rcx+2]
0x18002ba41  cmp     eax, ecx
0x18002ba43  jb      loc_18002BC19
0x18002ba49  add     rax, rax
0x18002ba4c  mov     ecx, 0FFFFFFFFh
0x18002ba51  cmp     rax, rcx
0x18002ba54  ja      loc_18002BC19
0x18002ba5a  mov     ecx, eax; size
0x18002ba5c  mov     ebx, eax
0x18002ba5e  call    MIDL_user_allocate
0x18002ba63  mov     r14, rax
0x18002ba66  test    rax, rax
0x18002ba69  jnz     short loc_18002BA73
0x18002ba6b  lea     ebx, [rax+8]
0x18002ba6e  jmp     loc_18002BC1E
0x18002ba73  lea     r9, String; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002ba7a  mov     [rsp+70h+phkResult], rsi
0x18002ba7f  lea     r8, aSS; "%s\\%s"
0x18002ba86  mov     rdx, rbx; cbDest
0x18002ba89  mov     rcx, r14; pszDest
0x18002ba8c  xor     edi, edi
0x18002ba8e  call    StringCbPrintfW
0x18002ba93  mov     ebx, eax
0x18002ba95  test    eax, eax
0x18002ba97  jnz     loc_18002BC02
0x18002ba9d  mov     r9d, r15d
0x18002baa0  lea     r8, asc_180035114; "%x"
0x18002baa7  lea     edx, [rdi+0Ah]; cchDest
0x18002baaa  lea     rcx, [rbp+pszDest]; pszDest
0x18002baae  call    StringCchPrintfW
0x18002bab3  mov     ebx, eax
0x18002bab5  test    eax, eax
0x18002bab7  jnz     loc_18002BC02
0x18002babd  lea     rax, [rbp+hKey]
0x18002bac1  xor     r8d, r8d; ulOptions
0x18002bac4  lea     r9d, [rdi+1]; samDesired
0x18002bac8  mov     [rsp+70h+phkResult], rax; phkResult
0x18002bacd  mov     rdx, r14; lpSubKey
0x18002bad0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bad7  call    cs:__imp_RegOpenKeyExW
0x18002badd  mov     ebx, eax
0x18002badf  test    eax, eax
0x18002bae1  jnz     loc_18002BC02
0x18002bae7  mov     rcx, [rbp+hKey]; hKey
0x18002baeb  lea     rax, [rbp+cbData]
0x18002baef  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18002baf4  lea     r9, [rbp+Type]; lpType
0x18002baf8  xor     r8d, r8d; lpReserved
0x18002bafb  mov     [rsp+70h+phkResult], rdi; lpData
0x18002bb00  lea     rdx, [rbp+pszDest]; lpValueName
0x18002bb04  call    cs:__imp_RegQueryValueExW
0x18002bb0a  mov     ebx, eax
0x18002bb0c  test    eax, eax
0x18002bb0e  jnz     loc_18002BC02
0x18002bb14  cmp     [rbp+Type], 1
0x18002bb18  jz      short loc_18002BB22
0x18002bb1a  lea     ebx, [rdi+0Dh]
0x18002bb1d  jmp     loc_18002BC02
0x18002bb22  mov     eax, [rbp+cbData]
0x18002bb25  lea     ecx, [rax+2]; size
0x18002bb28  cmp     ecx, eax
0x18002bb2a  jb      loc_18002BBFD
0x18002bb30  call    MIDL_user_allocate
0x18002bb35  mov     rsi, rax
0x18002bb38  test    rax, rax
0x18002bb3b  jnz     short loc_18002BB45
0x18002bb3d  lea     ebx, [rax+8]
0x18002bb40  jmp     loc_18002BC02
0x18002bb45  mov     rcx, [rbp+hKey]; hKey
0x18002bb49  lea     rax, [rbp+cbData]
0x18002bb4d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18002bb52  lea     rdx, [rbp+pszDest]; lpValueName
0x18002bb56  xor     r9d, r9d; lpType
0x18002bb59  mov     [rsp+70h+phkResult], rsi; lpData
0x18002bb5e  xor     r8d, r8d; lpReserved
0x18002bb61  call    cs:__imp_RegQueryValueExW
0x18002bb67  mov     ebx, eax
0x18002bb69  test    eax, eax
0x18002bb6b  jnz     loc_18002BBF3
0x18002bb71  mov     ecx, [rbp+cbData]
0x18002bb74  lea     r8, [rbp+lpString]
0x18002bb78  shr     rcx, 1
0x18002bb7b  mov     [rsi+rcx*2], ax
0x18002bb7f  mov     rcx, rsi
0x18002bb82  mov     edx, [rbp+cbData]
0x18002bb85  shr     edx, 1
0x18002bb87  call    I_GetLocalizedString
0x18002bb8c  mov     rbx, [rbp+lpString]
0x18002bb90  test    rbx, rbx
0x18002bb93  jnz     short loc_18002BB9C
0x18002bb95  mov     ebx, 490h
0x18002bb9a  jmp     short loc_18002BBF3
0x18002bb9c  mov     rcx, rbx; lpString
0x18002bb9f  call    cs:__imp_lstrlenW
0x18002bba5  lea     ecx, [rax+1]
0x18002bba8  cmp     ecx, eax
0x18002bbaa  jb      short loc_18002BBEE
0x18002bbac  mov     eax, ecx
0x18002bbae  mov     ecx, 0FFFFFFFFh
0x18002bbb3  add     rax, rax
0x18002bbb6  cmp     rax, rcx
0x18002bbb9  ja      short loc_18002BBEE
0x18002bbbb  mov     ecx, eax; size
0x18002bbbd  mov     r15d, eax
0x18002bbc0  call    MIDL_user_allocate
0x18002bbc5  mov     rdi, rax
0x18002bbc8  test    rax, rax
0x18002bbcb  jnz     short loc_18002BBD2
0x18002bbcd  lea     ebx, [rax+8]
0x18002bbd0  jmp     short loc_18002BBF3
0x18002bbd2  mov     r8, rbx; pszSrc
0x18002bbd5  mov     rdx, r15; cchDest
0x18002bbd8  mov     rcx, rdi; pszDest
0x18002bbdb  call    StringCchCopyW
0x18002bbe0  mov     ebx, eax
0x18002bbe2  test    eax, eax
0x18002bbe4  jnz     short loc_18002BBF3
0x18002bbe6  mov     [r12], rdi
0x18002bbea  xor     edi, edi
0x18002bbec  jmp     short loc_18002BBF3
0x18002bbee  mov     ebx, 80070216h
0x18002bbf3  mov     rcx, rsi
0x18002bbf6  call    CspFreeH
0x18002bbfb  jmp     short loc_18002BC02
0x18002bbfd  mov     ebx, 80070216h
0x18002bc02  mov     rcx, r14
0x18002bc05  call    CspFreeH
0x18002bc0a  test    rdi, rdi
0x18002bc0d  jz      short loc_18002BC1E
0x18002bc0f  mov     rcx, rdi
0x18002bc12  call    CspFreeH
0x18002bc17  jmp     short loc_18002BC1E
0x18002bc19  mov     ebx, 80070216h
0x18002bc1e  mov     rcx, [rbp+hKey]; hKey
0x18002bc22  test    rcx, rcx
0x18002bc25  jz      short loc_18002BC2D
0x18002bc27  call    cs:__imp_RegCloseKey
0x18002bc2d  mov     eax, ebx
0x18002bc2f  mov     rcx, [rbp+var_10]
0x18002bc33  xor     rcx, rsp; StackCookie
0x18002bc36  call    __security_check_cookie
0x18002bc3b  lea     r11, [rsp+70h+var_s0]
0x18002bc40  mov     rbx, [r11+40h]
0x18002bc44  mov     rsi, [r11+48h]
0x18002bc48  mov     rsp, r11
0x18002bc4b  pop     r15
0x18002bc4d  pop     r14
0x18002bc4f  pop     r12
0x18002bc51  pop     rdi
0x18002bc52  pop     rbp
0x18002bc53  retn
```
