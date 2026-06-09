# PathConvertToCSC(ushort const *,ushort * *)

- ea: `0x18009a7b0`
- end: `0x18009a971`
- name: `?PathConvertToCSC@@YAJPEBGPEAPEAG@Z`
- size: `449`
- prototype: `__int64 __fastcall(LPCWSTR lpLocalPath, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003c220`

## callees

- `0x18003d2a4`
- `0x18003d55c`
- `0x18003e1dc`
- `0x18003e570`
- `0x18006c5c8`
- `0x18006c6bc`
- `0x180099f50`
- `0x18009a7b0`
- `0x1800bedc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009a7e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009a7e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a8be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a8be`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009a8aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009a8aa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18009a818`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18009a818`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PathConvertToCSC(LPCWSTR lpLocalPath, unsigned __int16 **a2)
{
  int Error; // ebx
  int v5; // eax
  int v6; // edx
  void *v7; // rcx
  DWORD v8; // r8d
  HLOCAL v9; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 i; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v14; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v15; // [rsp+28h] [rbp-48h]
  __int64 v16; // [rsp+30h] [rbp-40h]
  LPWSTR StringSid; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h]
  __int64 v19; // [rsp+48h] [rbp-28h]
  unsigned __int16 *v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h]
  __int64 v22; // [rsp+60h] [rbp-10h]
  HLOCAL hMem; // [rsp+98h] [rbp+28h] BYREF

  *a2 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)_o__wcsnicmp(lpLocalPath, L"csc:", 4) )
  {
    v20 = 0;
    v21 = 0;
    v22 = 0;
    if ( PathIsUNCW(lpLocalPath) )
    {
      v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
             (__int64)&v20,
             lpLocalPath,
             0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v20);
      v21 = -1;
      v22 = -1;
      v5 = PathConvertToUNC(lpLocalPath, &v20);
    }
    Error = v5;
    if ( v5 >= 0 && v5 != 1 )
    {
      StringSid = 0;
      v18 = 0;
      v19 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&StringSid);
      v18 = -1;
      v19 = -1;
      StringSid = 0;
      hMem = 0;
      Error = SHQueryToken<_TOKEN_USER>(v7, v6, v8, &hMem);
      if ( Error >= 0 )
      {
        v9 = hMem;
        if ( !ConvertSidToStringSidW(*(PSID *)hMem, &StringSid) )
          Error = ResultFromKnownLastError();
        LocalFree(v9);
        if ( Error >= 0 )
        {
          Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                    &v14,
                    L"csc://{%s}/",
                    StringSid);
          if ( Error >= 0 )
          {
            Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                      &v14,
                      v20 + 2);
            if ( Error >= 0 )
            {
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&v14);
              v10 = 0;
              for ( i = v15; v10 < i; ++v10 )
              {
                if ( v14[v10] == 92 )
                  v14[v10] = 47;
              }
            }
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&StringSid);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v20);
  }
  else
  {
    Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              (__int64)&v14,
              lpLocalPath,
              0xFFFFFFFFFFFFFFFFuLL);
  }
  if ( Error >= 0 )
  {
    v12 = v14;
    v14 = 0;
    v16 = 0;
    v15 = 0;
    *a2 = v12;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v14);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18009a7b0  mov     [rsp-18h+arg_0], rbx
0x18009a7b5  mov     [rsp-18h+arg_10], rsi
0x18009a7ba  push    rbp
0x18009a7bb  push    rdi
0x18009a7bc  push    r14
0x18009a7be  mov     rbp, rsp
0x18009a7c1  sub     rsp, 70h
0x18009a7c5  mov     rsi, rdx
0x18009a7c8  mov     rbx, rcx
0x18009a7cb  xor     r14d, r14d
0x18009a7ce  mov     [rdx], r14
0x18009a7d1  mov     [rbp+var_50], r14
0x18009a7d5  mov     [rbp+var_48], r14
0x18009a7d9  mov     [rbp+var_40], r14
0x18009a7dd  lea     r8d, [r14+4]
0x18009a7e1  lea     rdx, aCsc; "csc:"
0x18009a7e8  call    cs:__imp__o__wcsnicmp
0x18009a7ee  test    eax, eax
0x18009a7f0  jnz     short loc_18009A809
0x18009a7f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009a7f6  mov     rdx, rbx
0x18009a7f9  lea     rcx, [rbp+var_50]
0x18009a7fd  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18009a802  mov     ebx, eax
0x18009a804  jmp     loc_18009A93A
0x18009a809  mov     [rbp+var_20], r14
0x18009a80d  mov     [rbp+var_18], r14
0x18009a811  mov     [rbp+var_10], r14
0x18009a815  mov     rcx, rbx; pszPath
0x18009a818  call    cs:__imp_PathIsUNCW
0x18009a81e  lea     rcx, [rbp+var_20]
0x18009a822  test    eax, eax
0x18009a824  jz      short loc_18009A837
0x18009a826  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009a82a  mov     r8, rdi
0x18009a82d  mov     rdx, rbx
0x18009a830  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18009a835  jmp     short loc_18009A854
0x18009a837  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009a83c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009a840  mov     [rbp+var_18], rdi
0x18009a844  mov     [rbp+var_10], rdi
0x18009a848  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x18009a84c  mov     rcx, rbx; lpLocalPath
0x18009a84f  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x18009a854  mov     ebx, eax
0x18009a856  test    eax, eax
0x18009a858  js      loc_18009A931
0x18009a85e  cmp     eax, 1
0x18009a861  jz      loc_18009A931
0x18009a867  mov     [rbp+StringSid], r14
0x18009a86b  mov     [rbp+var_30], r14
0x18009a86f  mov     [rbp+var_28], r14
0x18009a873  lea     rcx, [rbp+StringSid]
0x18009a877  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009a87c  mov     [rbp+var_30], rdi
0x18009a880  mov     [rbp+var_28], rdi
0x18009a884  mov     [rbp+StringSid], r14
0x18009a888  mov     [rbp+hMem], r14
0x18009a88c  lea     r9, [rbp+hMem]
0x18009a890  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x18009a895  mov     ebx, eax
0x18009a897  test    eax, eax
0x18009a899  js      loc_18009A927
0x18009a89f  lea     rdx, [rbp+StringSid]; StringSid
0x18009a8a3  mov     rdi, [rbp+hMem]
0x18009a8a7  mov     rcx, [rdi]; Sid
0x18009a8aa  call    cs:__imp_ConvertSidToStringSidW
0x18009a8b0  test    eax, eax
0x18009a8b2  jnz     short loc_18009A8BB
0x18009a8b4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18009a8b9  mov     ebx, eax
0x18009a8bb  mov     rcx, rdi; hMem
0x18009a8be  call    cs:__imp_LocalFree
0x18009a8c4  test    ebx, ebx
0x18009a8c6  js      short loc_18009A927
0x18009a8c8  mov     r8, [rbp+StringSid]
0x18009a8cc  lea     rdx, aCscS; "csc://{%s}/"
0x18009a8d3  lea     rcx, [rbp+var_50]
0x18009a8d7  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18009a8dc  mov     ebx, eax
0x18009a8de  test    eax, eax
0x18009a8e0  js      short loc_18009A927
0x18009a8e2  mov     rdx, [rbp+var_20]
0x18009a8e6  add     rdx, 4
0x18009a8ea  lea     rcx, [rbp+var_50]
0x18009a8ee  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18009a8f3  mov     ebx, eax
0x18009a8f5  test    eax, eax
0x18009a8f7  js      short loc_18009A927
0x18009a8f9  lea     rcx, [rbp+var_50]
0x18009a8fd  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18009a902  mov     rcx, r14
0x18009a905  mov     rax, [rbp+var_48]
0x18009a909  test    rax, rax
0x18009a90c  jz      short loc_18009A927
0x18009a90e  mov     rdx, [rbp+var_50]
0x18009a912  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x18009a917  jnz     short loc_18009A91F
0x18009a919  mov     word ptr [rdx+rcx*2], 2Fh ; '/'
0x18009a91f  inc     rcx
0x18009a922  cmp     rcx, rax
0x18009a925  jb      short loc_18009A90E
0x18009a927  lea     rcx, [rbp+StringSid]
0x18009a92b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009a930  nop
0x18009a931  lea     rcx, [rbp+var_20]
0x18009a935  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009a93a  test    ebx, ebx
0x18009a93c  js      short loc_18009A951
0x18009a93e  mov     rax, [rbp+var_50]
0x18009a942  mov     [rbp+var_50], r14
0x18009a946  mov     [rbp+var_40], r14
0x18009a94a  mov     [rbp+var_48], r14
0x18009a94e  mov     [rsi], rax
0x18009a951  lea     rcx, [rbp+var_50]
0x18009a955  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009a95a  mov     eax, ebx
0x18009a95c  lea     r11, [rsp+70h+var_s0]
0x18009a961  mov     rbx, [r11+20h]
0x18009a965  mov     rsi, [r11+30h]
0x18009a969  mov     rsp, r11
0x18009a96c  pop     r14
0x18009a96e  pop     rdi
0x18009a96f  pop     rbp
0x18009a970  retn
```
