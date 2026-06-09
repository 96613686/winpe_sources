# ConfigSet::ReadOnlyFailIfKeyAbsent(void)

- ea: `0x18001ee54`
- end: `0x18001efac`
- name: `?ReadOnlyFailIfKeyAbsent@ConfigSet@@QEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(ConfigSet *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001e2ac`

## callees

- `0x180008870`
- `0x18000a754`
- `0x1800185f0`
- `0x18001cae4`
- `0x18001e4e8`
- `0x18001ee54`
- `0x1800237bc`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eeec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eeec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef25`

## string_xrefs

- `0x18001ef9e`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::ReadOnlyFailIfKeyAbsent(HKEY *this)
{
  __int128 v1; // xmm0
  int RegistryPath; // eax
  int v4; // ebx
  int v5; // ecx
  _QWORD *v6; // rsi
  HKEY *phkResult; // rax
  __int64 *v8; // rdi
  LSTATUS v9; // eax
  HKEY *v10; // rax
  __int64 v11; // rbx
  LPCWSTR v13[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v14; // [rsp+40h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v16; // [rsp+60h] [rbp-20h]

  v1 = 0;
  *(_OWORD *)lpSubKey = 0;
  v16 = 0;
  *(double *)&v1 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  *(_OWORD *)v13 = v1;
  v14 = v1;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v13);
  RegistryPath = ConfigSet::GetRegistryPath(this, lpSubKey, v13);
  v4 = RegistryPath;
  if ( RegistryPath < 0 )
  {
    v5 = RegistryPath;
LABEL_14:
    Log_HREvent_5(v5);
    goto LABEL_10;
  }
  v6 = this + 10;
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(this + 10);
  v8 = (__int64 *)(this + 11);
  v4 = RegOpenKeyExW(this[13], lpSubKey[0], 0, 0x11u, phkResult);
  v9 = 2;
  if ( v13[0] != v13[1] )
  {
    v10 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(this + 11);
    v9 = RegOpenKeyExW(this[13], v13[0], 0, 0x11u, v10);
  }
  if ( v4 )
  {
    if ( v9 )
    {
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4;
      goto LABEL_14;
    }
    v11 = *v8;
    *v8 = 0;
    if ( v11 != *v6 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(this + 10);
      *v6 = v11;
    }
  }
  v4 = 0;
LABEL_10:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v13);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ee54  mov     [rsp-18h+arg_8], rbx
0x18001ee59  mov     [rsp-18h+arg_10], rsi
0x18001ee5e  push    rbp
0x18001ee5f  push    rdi
0x18001ee60  push    r14
0x18001ee62  mov     rbp, rsp
0x18001ee65  sub     rsp, 80h
0x18001ee6c  mov     rax, cs:__security_cookie
0x18001ee73  xor     rax, rsp
0x18001ee76  mov     [rbp+var_10], rax
0x18001ee7a  xorps   xmm0, xmm0
0x18001ee7d  mov     r14, rcx
0x18001ee80  lea     rcx, [rbp+lpSubKey]
0x18001ee84  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x18001ee88  movups  [rbp+var_20], xmm0
0x18001ee8c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001ee91  lea     rcx, [rbp+var_50]
0x18001ee95  movups  xmmword ptr [rbp+var_50], xmm0
0x18001ee99  movups  [rbp+var_40], xmm0
0x18001ee9d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001eea2  lea     rdx, [rbp+lpSubKey]
0x18001eea6  mov     rcx, r14
0x18001eea9  lea     r8, [rbp+var_50]
0x18001eead  call    ?GetRegistryPath@ConfigSet@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; ConfigSet::GetRegistryPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18001eeb2  mov     ebx, eax
0x18001eeb4  test    eax, eax
0x18001eeb6  jns     short loc_18001EECA
0x18001eeb8  mov     r9d, 3DBh
0x18001eebe  mov     edx, 1
0x18001eec3  mov     ecx, eax
0x18001eec5  jmp     loc_18001EF9E
0x18001eeca  lea     rsi, [r14+50h]
0x18001eece  mov     rcx, rsi
0x18001eed1  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001eed6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001eeda  mov     r9d, 11h; samDesired
0x18001eee0  mov     rcx, [r14+68h]; hKey
0x18001eee4  xor     r8d, r8d; ulOptions
0x18001eee7  mov     [rsp+80h+phkResult], rax; phkResult
0x18001eeec  call    cs:__imp_RegOpenKeyExW
0x18001eef2  mov     rcx, [rbp+var_50+8]
0x18001eef6  lea     rdi, [r14+58h]
0x18001eefa  mov     ebx, eax
0x18001eefc  mov     eax, 2
0x18001ef01  cmp     [rbp+var_50], rcx
0x18001ef05  jz      short loc_18001EF2B
0x18001ef07  mov     rcx, rdi
0x18001ef0a  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001ef0f  mov     rdx, [rbp+var_50]; lpSubKey
0x18001ef13  mov     r9d, 11h; samDesired
0x18001ef19  mov     rcx, [r14+68h]; hKey
0x18001ef1d  xor     r8d, r8d; ulOptions
0x18001ef20  mov     [rsp+80h+phkResult], rax; phkResult
0x18001ef25  call    cs:__imp_RegOpenKeyExW
0x18001ef2b  test    ebx, ebx
0x18001ef2d  jz      short loc_18001EF4D
0x18001ef2f  test    eax, eax
0x18001ef31  jnz     short loc_18001EF87
0x18001ef33  mov     rbx, [rdi]
0x18001ef36  mov     qword ptr [rdi], 0
0x18001ef3d  cmp     rbx, [rsi]
0x18001ef40  jz      short loc_18001EF4D
0x18001ef42  mov     rcx, rsi
0x18001ef45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001ef4a  mov     [rsi], rbx
0x18001ef4d  xor     ebx, ebx
0x18001ef4f  lea     rcx, [rbp+var_50]
0x18001ef53  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001ef58  lea     rcx, [rbp+lpSubKey]
0x18001ef5c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001ef61  mov     eax, ebx
0x18001ef63  mov     rcx, [rbp+var_10]
0x18001ef67  xor     rcx, rsp; StackCookie
0x18001ef6a  call    __security_check_cookie
0x18001ef6f  lea     r11, [rsp+80h+var_s0]
0x18001ef77  mov     rbx, [r11+28h]
0x18001ef7b  mov     rsi, [r11+30h]
0x18001ef7f  mov     rsp, r11
0x18001ef82  pop     r14
0x18001ef84  pop     rdi
0x18001ef85  pop     rbp
0x18001ef86  retn
0x18001ef87  test    ebx, ebx
0x18001ef89  jle     short loc_18001EF94
0x18001ef8b  movzx   ebx, bx
0x18001ef8e  or      ebx, 80070000h
0x18001ef94  mov     r9d, 3F0h
0x18001ef9a  xor     edx, edx
0x18001ef9c  mov     ecx, ebx; int
0x18001ef9e  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18001efa5  call    Log_HREvent_5
0x18001efaa  jmp     short loc_18001EF4F
```
