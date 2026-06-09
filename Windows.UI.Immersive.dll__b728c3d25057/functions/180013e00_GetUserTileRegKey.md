# GetUserTileRegKey

- ea: `0x180013e00`
- end: `0x180013fd2`
- name: `GetUserTileRegKey`
- size: `466`
- prototype: `__int64 __fastcall(LPCWSTR psz, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038920`
- `0x18004fe60`
- `0x1800c9f00`
- `0x1800ca0c0`
- `0x1800ca398`

## callees

- `0x180013e00`
- `0x180014a10`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f5c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013ea9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013fc5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013ea9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f72`

## pseudocode

```c
__int64 __fastcall GetUserTileRegKey(LPCWSTR psz, REGSAM samDesired, PHKEY phkResult)
{
  WCHAR *v3; // r9
  __int64 v4; // rdi
  __int64 v5; // rbx
  const wchar_t *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  WCHAR *v12; // rdx
  int v13; // esi
  HRESULT CurrentUsersSidString; // eax
  WCHAR *v15; // rax
  LPWSTR v16; // rcx
  _WORD *v17; // rdx
  _WORD *v18; // rcx
  LPWSTR v19; // rcx
  LSTATUS v20; // eax
  WCHAR *v21; // rcx
  LPWSTR ppwsz; // [rsp+30h] [rbp-258h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-250h] BYREF
  WCHAR psza[260]; // [rsp+40h] [rbp-248h] BYREF
  _BYTE v26[8]; // [rsp+248h] [rbp-40h] BYREF

  v3 = psza;
  v4 = 2147483646;
  *phkResult = 0;
  v5 = 260;
  lpSubKey = 0;
  v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
  v10 = 260;
  v11 = 2147483646;
  do
  {
    if ( !v11 )
      break;
    if ( !*v9 )
      break;
    *v3++ = *v9++;
    --v11;
    --v10;
  }
  while ( v10 );
  v12 = v3 - 1;
  v13 = -2147024774;
  if ( v10 )
  {
    v12 = v3;
    v13 = 0;
  }
  *v12 = 0;
  if ( v10 )
  {
    ppwsz = 0;
    if ( psz )
      CurrentUsersSidString = SHStrDupW(psz, &ppwsz);
    else
      CurrentUsersSidString = GetCurrentUsersSidString(&ppwsz);
    v13 = CurrentUsersSidString;
    if ( CurrentUsersSidString >= 0 )
    {
      v15 = psza;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v5;
      }
      while ( v5 );
      v13 = -2147024809;
      if ( v5 )
      {
        v16 = ppwsz;
        v17 = &v26[-2 * v5];
        do
        {
          if ( !v4 )
            break;
          if ( !*v16 )
            break;
          *v17++ = *v16++;
          --v4;
          --v5;
        }
        while ( v5 );
        v18 = v17 - 1;
        v13 = -2147024774;
        if ( v5 )
        {
          v18 = v17;
          v13 = 0;
        }
        *v18 = 0;
        if ( v5 )
          v13 = SHStrDupW(psza, (LPWSTR *)&lpSubKey);
      }
    }
    v19 = ppwsz;
    ppwsz = 0;
    CoTaskMemFree(v19);
    if ( v13 >= 0 )
    {
      v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, samDesired, phkResult);
      v13 = v20;
      if ( v20 > 0 )
        v13 = (unsigned __int16)v20 | 0x80070000;
    }
  }
  v21 = (WCHAR *)lpSubKey;
  lpSubKey = 0;
  CoTaskMemFree(v21);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180013e00  mov     [rsp+arg_18], rbx
0x180013e05  push    rbp
0x180013e06  push    rsi
0x180013e07  push    rdi
0x180013e08  push    r14
0x180013e0a  push    r15
0x180013e0c  sub     rsp, 260h
0x180013e13  mov     rax, cs:__security_cookie
0x180013e1a  xor     rax, rsp
0x180013e1d  mov     [rsp+288h+var_38], rax
0x180013e25  xor     r15d, r15d
0x180013e28  lea     r9, [rsp+288h+psz]
0x180013e2d  mov     edi, 7FFFFFFEh
0x180013e32  mov     [r8], r15
0x180013e35  mov     ebx, 104h
0x180013e3a  mov     [rsp+288h+lpSubKey], r15
0x180013e3f  mov     r14, r8
0x180013e42  mov     ebp, edx
0x180013e44  mov     r10, rcx
0x180013e47  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013e4e  mov     r8d, ebx
0x180013e51  mov     ecx, edi
0x180013e53  test    rcx, rcx
0x180013e56  jz      short loc_180013E75
0x180013e58  movzx   eax, word ptr [rdx]
0x180013e5b  test    ax, ax
0x180013e5e  jz      short loc_180013E75
0x180013e60  mov     [r9], ax
0x180013e64  add     rdx, 2
0x180013e68  add     r9, 2
0x180013e6c  dec     rcx
0x180013e6f  sub     r8, 1
0x180013e73  jnz     short loc_180013E53
0x180013e75  test    r8, r8
0x180013e78  lea     rdx, [r9-2]
0x180013e7c  mov     esi, 8007007Ah
0x180013e81  cmovnz  rdx, r9
0x180013e85  cmovnz  esi, r15d
0x180013e89  mov     [rdx], r15w
0x180013e8d  jz      loc_180013F68
0x180013e93  mov     [rsp+288h+ppwsz], r15
0x180013e98  test    r10, r10
0x180013e9b  jz      loc_180013FAC
0x180013ea1  lea     rdx, [rsp+288h+ppwsz]; ppwsz
0x180013ea6  mov     rcx, r10; psz
0x180013ea9  call    cs:__imp_SHStrDupW
0x180013eaf  mov     esi, eax
0x180013eb1  test    eax, eax
0x180013eb3  js      short loc_180013F31
0x180013eb5  lea     rax, [rsp+288h+psz]
0x180013eba  nop     word ptr [rax+rax+00h]
0x180013ec0  cmp     [rax], r15w
0x180013ec4  jz      short loc_180013ED0
0x180013ec6  add     rax, 2
0x180013eca  sub     rbx, 1
0x180013ece  jnz     short loc_180013EC0
0x180013ed0  test    rbx, rbx
0x180013ed3  mov     esi, 80070057h
0x180013ed8  cmovnz  esi, r15d
0x180013edc  jz      short loc_180013F31
0x180013ede  mov     rcx, [rsp+288h+ppwsz]
0x180013ee3  lea     rax, [rbx+rbx]
0x180013ee7  lea     rdx, [rsp+288h+var_40]
0x180013eef  sub     rdx, rax
0x180013ef2  test    rdi, rdi
0x180013ef5  jz      short loc_180013F13
0x180013ef7  movzx   eax, word ptr [rcx]
0x180013efa  test    ax, ax
0x180013efd  jz      short loc_180013F13
0x180013eff  mov     [rdx], ax
0x180013f02  add     rcx, 2
0x180013f06  add     rdx, 2
0x180013f0a  dec     rdi
0x180013f0d  sub     rbx, 1
0x180013f11  jnz     short loc_180013EF2
0x180013f13  test    rbx, rbx
0x180013f16  lea     rcx, [rdx-2]
0x180013f1a  mov     esi, 8007007Ah
0x180013f1f  cmovnz  rcx, rdx
0x180013f23  cmovnz  esi, r15d
0x180013f27  mov     [rcx], r15w
0x180013f2b  jnz     loc_180013FBB
0x180013f31  mov     rcx, [rsp+288h+ppwsz]; pv
0x180013f36  mov     [rsp+288h+ppwsz], r15
0x180013f3b  call    cs:__imp_CoTaskMemFree
0x180013f41  test    esi, esi
0x180013f43  js      short loc_180013F68
0x180013f45  mov     rdx, [rsp+288h+lpSubKey]; lpSubKey
0x180013f4a  mov     r9d, ebp; samDesired
0x180013f4d  xor     r8d, r8d; ulOptions
0x180013f50  mov     [rsp+288h+phkResult], r14; phkResult
0x180013f55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013f5c  call    cs:__imp_RegOpenKeyExW
0x180013f62  mov     esi, eax
0x180013f64  test    eax, eax
0x180013f66  jg      short loc_180013FA1
0x180013f68  mov     rcx, [rsp+288h+lpSubKey]; pv
0x180013f6d  mov     [rsp+288h+lpSubKey], r15
0x180013f72  call    cs:__imp_CoTaskMemFree
0x180013f78  mov     eax, esi
0x180013f7a  mov     rcx, [rsp+288h+var_38]
0x180013f82  xor     rcx, rsp; StackCookie
0x180013f85  call    __security_check_cookie
0x180013f8a  mov     rbx, [rsp+288h+arg_18]
0x180013f92  add     rsp, 260h
0x180013f99  pop     r15
0x180013f9b  pop     r14
0x180013f9d  pop     rdi
0x180013f9e  pop     rsi
0x180013f9f  pop     rbp
0x180013fa0  retn
0x180013fa1  movzx   esi, ax
0x180013fa4  or      esi, 80070000h
0x180013faa  jmp     short loc_180013F68
0x180013fac  lea     rcx, [rsp+288h+ppwsz]; ppwsz
0x180013fb1  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180013fb6  jmp     loc_180013EAF
0x180013fbb  lea     rdx, [rsp+288h+lpSubKey]; ppwsz
0x180013fc0  lea     rcx, [rsp+288h+psz]; psz
0x180013fc5  call    cs:__imp_SHStrDupW
0x180013fcb  mov     esi, eax
0x180013fcd  jmp     loc_180013F31
```
