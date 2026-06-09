# ConfigSet::ReadWriteCreateKey(void)

- ea: `0x18001efb4`
- end: `0x18001f181`
- name: `?ReadWriteCreateKey@ConfigSet@@QEAAJXZ`
- size: `461`
- prototype: `__int64 __fastcall(ConfigSet *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e2ac`

## callees

- `0x180008870`
- `0x18000a754`
- `0x1800185f0`
- `0x18001cae4`
- `0x18001e4e8`
- `0x18001efb4`
- `0x1800c50ec`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f061`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f0a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f061`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f0a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f140`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f140`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f0de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f0de`

## string_xrefs

- `0x18001f0c9`: `\Service\CallIDMatchOverrides`
- `0x18001f109`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::ReadWriteCreateKey(ConfigSet *this)
{
  __int128 v1; // xmm0
  int RegistryPath; // eax
  int Key; // ebx
  int v5; // ecx
  HKEY *phkResult; // rax
  HKEY *v7; // rax
  _WORD *v8; // rax
  HKEY *v9; // rax
  LPCWSTR v11[2]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v12; // [rsp+60h] [rbp+7h]
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp+17h] BYREF
  __int128 v14; // [rsp+80h] [rbp+27h]

  v1 = 0;
  *(_OWORD *)lpSubKey = 0;
  v14 = 0;
  *(double *)&v1 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  *(_OWORD *)v11 = v1;
  v12 = v1;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v11);
  RegistryPath = ConfigSet::GetRegistryPath(this, lpSubKey, v11);
  Key = RegistryPath;
  if ( RegistryPath < 0 )
  {
    v5 = RegistryPath;
LABEL_14:
    Log_HREvent_5(v5);
    goto LABEL_18;
  }
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((_QWORD *)this + 10);
  Key = RegCreateKeyExW(*((HKEY *)this + 13), lpSubKey[0], 0, 0, 0, 0x13u, 0, phkResult, 0);
  if ( Key == 1021 )
  {
    v7 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((_QWORD *)this + 10);
    Key = RegCreateKeyExW(*((HKEY *)this + 13), lpSubKey[0], 0, 0, 1u, 0x13u, 0, v7, 0);
  }
  if ( Key == 5 )
  {
    v8 = (_WORD *)*((_QWORD *)this + 15);
    if ( (!v8 || *v8)
      && CompareStringOrdinal(L"\\Service\\CallIDMatchOverrides", -1, *((LPCWCH *)this + 16), -1, 1) != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    goto LABEL_12;
  }
  if ( Key )
  {
    if ( Key <= 0 )
    {
LABEL_13:
      v5 = Key;
      goto LABEL_14;
    }
LABEL_12:
    Key = (unsigned __int16)Key | 0x80070000;
    goto LABEL_13;
  }
  if ( v11[0] != v11[1] )
  {
    v9 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((_QWORD *)this + 11);
    RegOpenKeyExW(*((HKEY *)this + 13), v11[0], 0, 0x11u, v9);
  }
  Key = 0;
LABEL_18:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v11);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18001efb4  mov     [rsp-8+arg_8], rbx
0x18001efb9  mov     [rsp-8+arg_10], rsi
0x18001efbe  push    rbp
0x18001efbf  push    rdi
0x18001efc0  push    r14
0x18001efc2  lea     rbp, [rsp-47h]
0x18001efc7  sub     rsp, 0A0h
0x18001efce  mov     rax, cs:__security_cookie
0x18001efd5  xor     rax, rsp
0x18001efd8  mov     [rbp+57h+var_20], rax
0x18001efdc  xorps   xmm0, xmm0
0x18001efdf  mov     rdi, rcx
0x18001efe2  lea     rcx, [rbp+57h+lpSubKey]
0x18001efe6  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18001efea  movups  [rbp+57h+var_30], xmm0
0x18001efee  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001eff3  lea     rcx, [rbp+57h+var_60]
0x18001eff7  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18001effb  movups  [rbp+57h+var_50], xmm0
0x18001efff  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001f004  lea     rdx, [rbp+57h+lpSubKey]
0x18001f008  mov     rcx, rdi
0x18001f00b  lea     r8, [rbp+57h+var_60]
0x18001f00f  call    ?GetRegistryPath@ConfigSet@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; ConfigSet::GetRegistryPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18001f014  xor     r14d, r14d
0x18001f017  mov     ebx, eax
0x18001f019  test    eax, eax
0x18001f01b  jns     short loc_18001F02E
0x18001f01d  mov     r9d, 40Eh
0x18001f023  lea     edx, [r14+1]
0x18001f027  mov     ecx, eax
0x18001f029  jmp     loc_18001F109
0x18001f02e  lea     rcx, [rdi+50h]
0x18001f032  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f037  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001f03b  xor     r9d, r9d; lpClass
0x18001f03e  mov     rcx, [rdi+68h]; hKey
0x18001f042  xor     r8d, r8d; Reserved
0x18001f045  mov     [rsp+0B0h+lpdwDisposition], r14; lpdwDisposition
0x18001f04a  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18001f04f  mov     [rsp+0B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001f054  mov     [rsp+0B0h+samDesired], 13h; samDesired
0x18001f05c  mov     [rsp+0B0h+dwOptions], r14d; dwOptions
0x18001f061  call    cs:__imp_RegCreateKeyExW
0x18001f067  mov     ebx, eax
0x18001f069  cmp     eax, 3FDh
0x18001f06e  jnz     short loc_18001F0AE
0x18001f070  lea     rcx, [rdi+50h]
0x18001f074  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f079  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001f07d  xor     r9d, r9d; lpClass
0x18001f080  mov     rcx, [rdi+68h]; hKey
0x18001f084  xor     r8d, r8d; Reserved
0x18001f087  mov     [rsp+0B0h+lpdwDisposition], r14; lpdwDisposition
0x18001f08c  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18001f091  mov     [rsp+0B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001f096  mov     [rsp+0B0h+samDesired], 13h; samDesired
0x18001f09e  mov     [rsp+0B0h+dwOptions], 1; dwOptions
0x18001f0a6  call    cs:__imp_RegCreateKeyExW
0x18001f0ac  mov     ebx, eax
0x18001f0ae  cmp     ebx, 5
0x18001f0b1  jnz     short loc_18001F0F0
0x18001f0b3  mov     rax, [rdi+78h]
0x18001f0b7  test    rax, rax
0x18001f0ba  jz      short loc_18001F0C2
0x18001f0bc  cmp     [rax], r14w
0x18001f0c0  jz      short loc_18001F0F6
0x18001f0c2  mov     r8, [rdi+80h]; lpString2
0x18001f0c9  lea     rcx, String1; "\\Service\\CallIDMatchOverrides"
0x18001f0d0  or      edx, 0FFFFFFFFh; cchCount1
0x18001f0d3  mov     [rsp+0B0h+dwOptions], 1; bIgnoreCase
0x18001f0db  mov     r9d, edx; cchCount2
0x18001f0de  call    cs:__imp_CompareStringOrdinal
0x18001f0e4  cmp     eax, 2
0x18001f0e7  jz      short loc_18001F0F6
0x18001f0e9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f0ee  jmp     short loc_18001F0F6
0x18001f0f0  test    ebx, ebx
0x18001f0f2  jz      short loc_18001F117
0x18001f0f4  jle     short loc_18001F0FF
0x18001f0f6  movzx   ebx, bx
0x18001f0f9  or      ebx, 80070000h
0x18001f0ff  mov     r9d, 42Dh
0x18001f105  xor     edx, edx
0x18001f107  mov     ecx, ebx; int
0x18001f109  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18001f110  call    Log_HREvent_5
0x18001f115  jmp     short loc_18001F149
0x18001f117  mov     rax, [rbp+57h+var_60+8]
0x18001f11b  cmp     [rbp+57h+var_60], rax
0x18001f11f  jz      short loc_18001F146
0x18001f121  lea     rcx, [rdi+58h]
0x18001f125  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f12a  mov     rdx, [rbp+57h+var_60]; lpSubKey
0x18001f12e  mov     r9d, 11h; samDesired
0x18001f134  mov     rcx, [rdi+68h]; hKey
0x18001f138  xor     r8d, r8d; ulOptions
0x18001f13b  mov     qword ptr [rsp+0B0h+dwOptions], rax; phkResult
0x18001f140  call    cs:__imp_RegOpenKeyExW
0x18001f146  mov     ebx, r14d
0x18001f149  lea     rcx, [rbp+57h+var_60]
0x18001f14d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001f152  lea     rcx, [rbp+57h+lpSubKey]
0x18001f156  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001f15b  mov     eax, ebx
0x18001f15d  mov     rcx, [rbp+57h+var_20]
0x18001f161  xor     rcx, rsp; StackCookie
0x18001f164  call    __security_check_cookie
0x18001f169  lea     r11, [rsp+0B0h+var_10]
0x18001f171  mov     rbx, [r11+28h]
0x18001f175  mov     rsi, [r11+30h]
0x18001f179  mov     rsp, r11
0x18001f17c  pop     r14
0x18001f17e  pop     rdi
0x18001f17f  pop     rbp
0x18001f180  retn
```
