# ConfigSet::ReadWriteFailIfKeyAbsent(void)

- ea: `0x18001f188`
- end: `0x18001f2ac`
- name: `?ReadWriteFailIfKeyAbsent@ConfigSet@@QEAAJXZ`
- size: `292`
- prototype: `__int64 __fastcall(ConfigSet *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001e2ac`

## callees

- `0x180008870`
- `0x18000a754`
- `0x1800185f0`
- `0x18001cae4`
- `0x18001e4e8`
- `0x18001f188`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f217`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f26f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f217`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f26f`

## string_xrefs

- `0x18001f238`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::ReadWriteFailIfKeyAbsent(HKEY *this)
{
  __int128 v1; // xmm0
  int RegistryPath; // eax
  unsigned int v4; // ebx
  int v5; // ecx
  HKEY *phkResult; // rax
  LSTATUS v7; // eax
  HKEY *v8; // rax
  LPCWSTR v10[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v11; // [rsp+40h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v13; // [rsp+60h] [rbp-20h]

  v1 = 0;
  *(_OWORD *)lpSubKey = 0;
  v13 = 0;
  *(double *)&v1 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  *(_OWORD *)v10 = v1;
  v11 = v1;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v10);
  RegistryPath = ConfigSet::GetRegistryPath(this, lpSubKey, v10);
  v4 = RegistryPath;
  if ( RegistryPath < 0 )
  {
    v5 = RegistryPath;
LABEL_7:
    Log_HREvent_5(v5);
    goto LABEL_11;
  }
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(this + 10);
  v7 = RegOpenKeyExW(this[13], lpSubKey[0], 0, 0x13u, phkResult);
  v4 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    v5 = v4;
    goto LABEL_7;
  }
  if ( v10[0] != v10[1] )
  {
    v8 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(this + 11);
    RegOpenKeyExW(this[13], v10[0], 0, 0x11u, v8);
  }
  v4 = 0;
LABEL_11:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v10);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
  return v4;
}

```

## disassembly

```asm
0x18001f188  mov     [rsp-8+arg_8], rbx
0x18001f18d  mov     [rsp-8+arg_10], rdi
0x18001f192  push    rbp
0x18001f193  mov     rbp, rsp
0x18001f196  sub     rsp, 80h
0x18001f19d  mov     rax, cs:__security_cookie
0x18001f1a4  xor     rax, rsp
0x18001f1a7  mov     [rbp+var_10], rax
0x18001f1ab  xorps   xmm0, xmm0
0x18001f1ae  mov     rdi, rcx
0x18001f1b1  lea     rcx, [rbp+lpSubKey]
0x18001f1b5  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x18001f1b9  movups  [rbp+var_20], xmm0
0x18001f1bd  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001f1c2  lea     rcx, [rbp+var_50]
0x18001f1c6  movups  xmmword ptr [rbp+var_50], xmm0
0x18001f1ca  movups  [rbp+var_40], xmm0
0x18001f1ce  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001f1d3  lea     rdx, [rbp+lpSubKey]
0x18001f1d7  mov     rcx, rdi
0x18001f1da  lea     r8, [rbp+var_50]
0x18001f1de  call    ?GetRegistryPath@ConfigSet@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; ConfigSet::GetRegistryPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18001f1e3  mov     ebx, eax
0x18001f1e5  test    eax, eax
0x18001f1e7  jns     short loc_18001F1F8
0x18001f1e9  mov     r9d, 3FAh
0x18001f1ef  mov     edx, 1
0x18001f1f4  mov     ecx, eax
0x18001f1f6  jmp     short loc_18001F238
0x18001f1f8  lea     rcx, [rdi+50h]
0x18001f1fc  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f201  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001f205  mov     r9d, 13h; samDesired
0x18001f20b  mov     rcx, [rdi+68h]; hKey
0x18001f20f  xor     r8d, r8d; ulOptions
0x18001f212  mov     [rsp+80h+phkResult], rax; phkResult
0x18001f217  call    cs:__imp_RegOpenKeyExW
0x18001f21d  mov     ebx, eax
0x18001f21f  test    eax, eax
0x18001f221  jz      short loc_18001F246
0x18001f223  jle     short loc_18001F22E
0x18001f225  movzx   ebx, ax
0x18001f228  or      ebx, 80070000h
0x18001f22e  mov     r9d, 3FCh
0x18001f234  xor     edx, edx
0x18001f236  mov     ecx, ebx; int
0x18001f238  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18001f23f  call    Log_HREvent_5
0x18001f244  jmp     short loc_18001F277
0x18001f246  mov     rax, [rbp+var_50+8]
0x18001f24a  cmp     [rbp+var_50], rax
0x18001f24e  jz      short loc_18001F275
0x18001f250  lea     rcx, [rdi+58h]
0x18001f254  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f259  mov     rdx, [rbp+var_50]; lpSubKey
0x18001f25d  mov     r9d, 11h; samDesired
0x18001f263  mov     rcx, [rdi+68h]; hKey
0x18001f267  xor     r8d, r8d; ulOptions
0x18001f26a  mov     [rsp+80h+phkResult], rax; phkResult
0x18001f26f  call    cs:__imp_RegOpenKeyExW
0x18001f275  xor     ebx, ebx
0x18001f277  lea     rcx, [rbp+var_50]
0x18001f27b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001f280  lea     rcx, [rbp+lpSubKey]
0x18001f284  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001f289  mov     eax, ebx
0x18001f28b  mov     rcx, [rbp+var_10]
0x18001f28f  xor     rcx, rsp; StackCookie
0x18001f292  call    __security_check_cookie
0x18001f297  lea     r11, [rsp+80h+var_s0]
0x18001f29f  mov     rbx, [r11+18h]
0x18001f2a3  mov     rdi, [r11+20h]
0x18001f2a7  mov     rsp, r11
0x18001f2aa  pop     rbp
0x18001f2ab  retn
```
