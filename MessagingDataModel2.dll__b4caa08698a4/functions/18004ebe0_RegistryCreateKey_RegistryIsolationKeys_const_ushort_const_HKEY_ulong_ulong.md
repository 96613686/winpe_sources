# RegistryCreateKey(RegistryIsolationKeys const &,ushort const *,HKEY__ * *,ulong,ulong)

- ea: `0x18004ebe0`
- end: `0x18004ed4a`
- name: `?RegistryCreateKey@@YAJAEBURegistryIsolationKeys@@PEBGPEAPEAUHKEY__@@KK@Z`
- size: `362`
- prototype: `int(const struct RegistryIsolationKeys *, const unsigned __int16 *, HKEY *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800519bc`
- `0x180053484`
- `0x180053558`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18004e2ec`
- `0x18004eb80`
- `0x18004ebe0`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004ec8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004ecf6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004ec8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004ecf6`

## string_xrefs

- `0x18004ecb4`: `onecoreuap\internal\net\inc\phone\RegistryIsolationUtil.h`

## pseudocode

```c
__int64 __fastcall RegistryCreateKey(HKEY *a1, const unsigned __int16 *a2, HKEY *a3)
{
  __int128 v3; // xmm0
  __int64 v6; // r10
  int NewRegistryPath; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  LSTATUS Key; // eax
  LSTATUS v11; // eax
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-11h] BYREF
  __int128 v14; // [rsp+60h] [rbp-1h]
  _OWORD v15[2]; // [rsp+70h] [rbp+Fh] BYREF

  v3 = 0;
  *(_OWORD *)lpSubKey = 0;
  v14 = 0;
  *(double *)&v3 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  v15[0] = v3;
  v15[1] = v3;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v15);
  NewRegistryPath = RegistryIsolationUtil::GetNewRegistryPath(a1, v6, lpSubKey, v15);
  v8 = NewRegistryPath;
  if ( NewRegistryPath >= 0 )
  {
    Key = RegCreateKeyExW(*a1, lpSubKey[0], 0, 0, 0, 0x2011Fu, 0, a3, 0);
    v8 = Key;
    if ( Key == 1021 )
    {
      v11 = RegCreateKeyExW(*a1, lpSubKey[0], 0, 0, 1u, 0x2011Fu, 0, a3, 0);
      v8 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_7;
      }
    }
    else if ( Key )
    {
      if ( Key > 0 )
        v8 = (unsigned __int16)Key | 0x80070000;
LABEL_7:
      v9 = v8;
      goto LABEL_8;
    }
    v8 = 0;
    goto LABEL_14;
  }
  v9 = NewRegistryPath;
LABEL_8:
  Log_HREvent_27(v9);
LABEL_14:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v15);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
  return v8;
}

```

## disassembly

```asm
0x18004ebe0  mov     [rsp-8+arg_18], rbx
0x18004ebe5  push    rbp
0x18004ebe6  push    rsi
0x18004ebe7  push    rdi
0x18004ebe8  lea     rbp, [rsp-3Fh]
0x18004ebed  sub     rsp, 0A0h
0x18004ebf4  mov     rax, cs:__security_cookie
0x18004ebfb  xor     rax, rsp
0x18004ebfe  mov     [rbp+4Fh+var_20], rax
0x18004ec02  xorps   xmm0, xmm0
0x18004ec05  mov     rdi, rcx
0x18004ec08  lea     rcx, [rbp+4Fh+lpSubKey]
0x18004ec0c  mov     rsi, r8
0x18004ec0f  movups  xmmword ptr [rbp+4Fh+lpSubKey], xmm0
0x18004ec13  mov     r10, rdx
0x18004ec16  movups  [rbp+4Fh+var_50], xmm0
0x18004ec1a  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004ec1f  lea     rcx, [rbp+4Fh+var_40]
0x18004ec23  movups  [rbp+4Fh+var_40], xmm0
0x18004ec27  movups  [rbp+4Fh+var_30], xmm0
0x18004ec2b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004ec30  mov     rdx, r10
0x18004ec33  lea     r9, [rbp+4Fh+var_40]
0x18004ec37  lea     r8, [rbp+4Fh+lpSubKey]
0x18004ec3b  mov     rcx, rdi
0x18004ec3e  call    ?GetNewRegistryPath@RegistryIsolationUtil@@YAJAEBURegistryIsolationKeys@@PEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@2@Z; RegistryIsolationUtil::GetNewRegistryPath(RegistryIsolationKeys const &,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18004ec43  mov     ebx, eax
0x18004ec45  test    eax, eax
0x18004ec47  jns     short loc_18004EC58
0x18004ec49  mov     r9d, 92h
0x18004ec4f  mov     edx, 1
0x18004ec54  mov     ecx, eax
0x18004ec56  jmp     short loc_18004ECB4
0x18004ec58  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18004ec5c  xor     r9d, r9d; lpClass
0x18004ec5f  mov     rcx, [rdi]; hKey
0x18004ec62  xor     r8d, r8d; Reserved
0x18004ec65  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18004ec6e  mov     [rsp+0B0h+phkResult], rsi; phkResult
0x18004ec73  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004ec7c  mov     [rsp+0B0h+samDesired], 2011Fh; samDesired
0x18004ec84  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18004ec8c  call    cs:__imp_RegCreateKeyExW
0x18004ec92  mov     ebx, eax
0x18004ec94  cmp     eax, 3FDh
0x18004ec99  jz      short loc_18004ECC2
0x18004ec9b  test    eax, eax
0x18004ec9d  jz      short loc_18004ED15
0x18004ec9f  jle     short loc_18004ECAA
0x18004eca1  movzx   ebx, ax
0x18004eca4  or      ebx, 80070000h
0x18004ecaa  mov     r9d, 98h
0x18004ecb0  xor     edx, edx
0x18004ecb2  mov     ecx, ebx; int
0x18004ecb4  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18004ecbb  call    Log_HREvent_27
0x18004ecc0  jmp     short loc_18004ED17
0x18004ecc2  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18004ecc6  xor     r9d, r9d; lpClass
0x18004ecc9  mov     rcx, [rdi]; hKey
0x18004eccc  xor     r8d, r8d; Reserved
0x18004eccf  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18004ecd8  mov     [rsp+0B0h+phkResult], rsi; phkResult
0x18004ecdd  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004ece6  mov     [rsp+0B0h+samDesired], 2011Fh; samDesired
0x18004ecee  mov     [rsp+0B0h+dwOptions], 1; dwOptions
0x18004ecf6  call    cs:__imp_RegCreateKeyExW
0x18004ecfc  mov     ebx, eax
0x18004ecfe  test    eax, eax
0x18004ed00  jz      short loc_18004ED15
0x18004ed02  jle     short loc_18004ED0D
0x18004ed04  movzx   ebx, ax
0x18004ed07  or      ebx, 80070000h
0x18004ed0d  mov     r9d, 9Fh
0x18004ed13  jmp     short loc_18004ECB0
0x18004ed15  xor     ebx, ebx
0x18004ed17  lea     rcx, [rbp+4Fh+var_40]
0x18004ed1b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004ed20  lea     rcx, [rbp+4Fh+lpSubKey]
0x18004ed24  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004ed29  mov     eax, ebx
0x18004ed2b  mov     rcx, [rbp+4Fh+var_20]
0x18004ed2f  xor     rcx, rsp; StackCookie
0x18004ed32  call    __security_check_cookie
0x18004ed37  mov     rbx, [rsp+0B0h+arg_18]
0x18004ed3f  add     rsp, 0A0h
0x18004ed46  pop     rdi
0x18004ed47  pop     rsi
0x18004ed48  pop     rbp
0x18004ed49  retn
```
