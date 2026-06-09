# ZtRegReadRules

- ea: `0x180007b64`
- end: `0x180007f44`
- name: `ZtRegReadRules`
- size: `992`
- prototype: `__int64 __fastcall(int, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18000897c`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x180007414`
- `0x180007630`
- `0x1800076b8`
- `0x180007b64`
- `0x180007f4c`
- `0x180009eac`
- `0x18000dc20`
- `0x18000eb1c`
- `0x180012564`
- `0x180015008`
- `0x180015040`
- `0x180015864`

## import_xrefs

- `DNSAPI!DnsFreeZtRules` at `0x180007ebc`
- `DNSAPI!DnsFreeZtRules` at `0x180007ebc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007d02`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007d02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007efe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007f12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007efe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007f12`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007d93`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007ddf`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180007c97`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180007c97`

## pseudocode

```c
__int64 __fastcall ZtRegReadRules(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  unsigned int v6; // r12d
  char *v7; // r15
  signed int Instance; // ebx
  DnsZtRuleMap **v9; // rbx
  signed int v10; // eax
  LSTATUS v11; // eax
  DWORD i; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  ULONG v15; // eax
  ULONG v16; // ebx
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = a1;
  hKey[0] = 0;
  phkResult = 0;
  memset_0(Name, 0, 0x20Au);
  v6 = 0;
  cchName = 0;
  v7 = 0;
  cSubKeys = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_dqq(1026, 0x22u, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v3, a2, a3);
  if ( a2 )
  {
    if ( a3 )
    {
      if ( (unsigned int)v3 <= 1 )
      {
        v9 = (DnsZtRuleMap **)&g_rgspDnsZtRuleMap[v3];
        if ( *v9 )
        {
          DnsZtRuleMap::Release(*v9);
          *v9 = 0;
        }
        Instance = DnsZtRuleMap::CreateInstance((struct DnsZtRuleMap **)&g_rgspDnsZtRuleMap[v3]);
        if ( Instance >= 0 )
        {
          v10 = RegOpenKeyExInternalW(a2, L"ZtRules", 0, 131097, hKey, a3);
          if ( v10 != 2 )
          {
            Instance = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
            if ( Instance >= 0 )
            {
              v11 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
              Instance = v11;
              if ( v11 > 0 )
                Instance = (unsigned __int16)v11 | 0x80070000;
              if ( Instance >= 0 && cSubKeys )
              {
                v7 = (char *)Dns_Allocate(48LL * cSubKeys);
                if ( v7 )
                {
                  Instance = 0;
                  for ( i = 0; i < cSubKeys; ++i )
                  {
                    cchName = 261;
                    v13 = RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0);
                    Instance = v13;
                    if ( v13 > 0 )
                      Instance = (unsigned __int16)v13 | 0x80070000;
                    if ( Instance < 0 )
                      break;
                    if ( (unsigned int)wcsicmp_ThatWorks(Name, &Format) )
                    {
                      v14 = RegOpenKeyExW(hKey[0], Name, 0, 0x20019u, &phkResult);
                      Instance = v14;
                      if ( v14 > 0 )
                        Instance = (unsigned __int16)v14 | 0x80070000;
                      if ( Instance < 0 )
                        break;
                      if ( (xmmword_18001F260 & 4) != 0 )
                        WPP_SF_S(1026, 0x23u, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, Name);
                      Instance = ZtRegReadSingleRule(phkResult, Name);
                      if ( Instance < 0 )
                        break;
                      Instance = ZtAddRuleToMap((unsigned int)v3, &v7[48 * i]);
                      if ( Instance < 0 )
                        break;
                      if ( phkResult )
                      {
                        RegCloseKey(phkResult);
                        phkResult = 0;
                      }
                      Name[0] = 0;
                      ++v6;
                    }
                  }
                }
                else
                {
                  Instance = -2147024809;
                }
              }
            }
          }
        }
      }
      else
      {
        Instance = -2147024809;
      }
    }
    else
    {
      Instance = -2147024809;
    }
  }
  else
  {
    Instance = -2147024809;
  }
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeRules(v6, v7);
  else
    DnsFreeZtRules(v6, v7);
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v15 = WX_WIN32_FROM_HR(Instance);
    WPP_SF_d(1026, 0x24u, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v15);
  }
  v16 = WX_WIN32_FROM_HR(Instance);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v16;
}

```

## disassembly

```asm
0x180007b64  mov     [rsp-8+arg_18], rbx
0x180007b69  push    rbp
0x180007b6a  push    rsi
0x180007b6b  push    rdi
0x180007b6c  push    r12
0x180007b6e  push    r13
0x180007b70  push    r14
0x180007b72  push    r15
0x180007b74  lea     rbp, [rsp-1B0h]
0x180007b7c  sub     rsp, 2B0h
0x180007b83  mov     rax, cs:__security_cookie
0x180007b8a  xor     rax, rsp
0x180007b8d  mov     [rbp+1E0h+var_40], rax
0x180007b94  xor     r13d, r13d
0x180007b97  movsxd  r14, ecx
0x180007b9a  mov     rsi, r8
0x180007b9d  mov     [rsp+2E0h+var_27C], r13d
0x180007ba2  mov     rdi, rdx
0x180007ba5  mov     [rbp+1E0h+hKey], r13
0x180007ba9  xor     edx, edx; Val
0x180007bab  mov     [rsp+2E0h+phkResult], r13
0x180007bb0  mov     r8d, 20Ah; Size
0x180007bb6  lea     rcx, [rbp+1E0h+Name]; void *
0x180007bba  call    memset_0
0x180007bbf  mov     r12d, r13d
0x180007bc2  mov     [rsp+2E0h+cchName], r13d
0x180007bc7  mov     r15d, r13d
0x180007bca  mov     [rsp+2E0h+cSubKeys], r13d
0x180007bcf  test    byte ptr cs:xmmword_18001F260, 4
0x180007bd6  jz      short loc_180007BFA
0x180007bd8  lea     edx, [r13+22h]
0x180007bdc  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi
0x180007be1  mov     ecx, 402h
0x180007be6  mov     [rsp+2E0h+lpcSubKeys], rdi
0x180007beb  mov     r9d, r14d
0x180007bee  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180007bf5  call    WPP_SF_dqq
0x180007bfa  test    rdi, rdi
0x180007bfd  jnz     short loc_180007C11
0x180007bff  mov     ebx, 80070057h
0x180007c04  mov     [rsp+2E0h+var_27C], 1B6h
0x180007c0c  jmp     loc_180007EA6
0x180007c11  test    rsi, rsi
0x180007c14  jnz     short loc_180007C28
0x180007c16  mov     ebx, 80070057h
0x180007c1b  mov     [rsp+2E0h+var_27C], 1B7h
0x180007c23  jmp     loc_180007EA6
0x180007c28  cmp     r14d, 1
0x180007c2c  jbe     short loc_180007C40
0x180007c2e  mov     ebx, 80070057h
0x180007c33  mov     [rsp+2E0h+var_27C], 1B9h
0x180007c3b  jmp     loc_180007EA6
0x180007c40  lea     rcx, ?g_rgspDnsZtRuleMap@@3PAV?$AutoInterface@VDnsZtRuleMap@@@@A; AutoInterface<DnsZtRuleMap> near * g_rgspDnsZtRuleMap
0x180007c47  lea     rbx, [rcx+r14*8]
0x180007c4b  mov     rcx, [rbx]; this
0x180007c4e  test    rcx, rcx
0x180007c51  jz      short loc_180007C5B
0x180007c53  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x180007c58  mov     [rbx], r13
0x180007c5b  mov     rcx, rbx; struct DnsZtRuleMap **
0x180007c5e  call    ?CreateInstance@DnsZtRuleMap@@SAJPEAPEAV1@@Z; DnsZtRuleMap::CreateInstance(DnsZtRuleMap * *)
0x180007c63  mov     ebx, eax
0x180007c65  test    eax, eax
0x180007c67  jns     short loc_180007C76
0x180007c69  mov     [rsp+2E0h+var_27C], 1C5h
0x180007c71  jmp     loc_180007EA6
0x180007c76  lea     rax, [rbp+1E0h+hKey]
0x180007c7a  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi
0x180007c7f  mov     r9d, 20019h
0x180007c85  mov     [rsp+2E0h+lpcSubKeys], rax
0x180007c8a  xor     r8d, r8d
0x180007c8d  lea     rdx, aZtrules; "ZtRules"
0x180007c94  mov     rcx, rdi
0x180007c97  call    cs:__imp_RegOpenKeyExInternalW
0x180007c9d  cmp     eax, 2
0x180007ca0  jz      loc_180007EA6
0x180007ca6  mov     esi, 80070000h
0x180007cab  test    eax, eax
0x180007cad  jg      short loc_180007CB3
0x180007caf  mov     ebx, eax
0x180007cb1  jmp     short loc_180007CB8
0x180007cb3  movzx   ebx, ax
0x180007cb6  or      ebx, esi
0x180007cb8  test    ebx, ebx
0x180007cba  jns     short loc_180007CC9
0x180007cbc  mov     [rsp+2E0h+var_27C], 1D2h
0x180007cc4  jmp     loc_180007EA6
0x180007cc9  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180007ccd  lea     rax, [rsp+2E0h+cSubKeys]
0x180007cd2  mov     [rsp+2E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180007cd7  xor     r9d, r9d; lpReserved
0x180007cda  mov     [rsp+2E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180007cdf  xor     r8d, r8d; lpcchClass
0x180007ce2  mov     [rsp+2E0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180007ce7  xor     edx, edx; lpClass
0x180007ce9  mov     [rsp+2E0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180007cee  mov     [rsp+2E0h+lpcValues], r13; lpcValues
0x180007cf3  mov     [rsp+2E0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180007cf8  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180007cfd  mov     [rsp+2E0h+lpcSubKeys], rax; lpcSubKeys
0x180007d02  call    cs:__imp_RegQueryInfoKeyW
0x180007d08  mov     ebx, eax
0x180007d0a  test    eax, eax
0x180007d0c  jle     short loc_180007D13
0x180007d0e  movzx   ebx, ax
0x180007d11  or      ebx, esi
0x180007d13  test    ebx, ebx
0x180007d15  jns     short loc_180007D24
0x180007d17  mov     [rsp+2E0h+var_27C], 1E3h
0x180007d1f  jmp     loc_180007EA6
0x180007d24  mov     eax, [rsp+2E0h+cSubKeys]
0x180007d28  test    eax, eax
0x180007d2a  jz      loc_180007EA6
0x180007d30  lea     rcx, [rax+rax*2]
0x180007d34  shl     rcx, 4
0x180007d38  call    Dns_Allocate
0x180007d3d  mov     r15, rax
0x180007d40  test    rax, rax
0x180007d43  jnz     short loc_180007D57
0x180007d45  mov     ebx, 80070057h
0x180007d4a  mov     [rsp+2E0h+var_27C], 1ECh
0x180007d52  jmp     loc_180007EA6
0x180007d57  mov     ebx, r13d
0x180007d5a  mov     edi, r13d
0x180007d5d  cmp     [rsp+2E0h+cSubKeys], r13d
0x180007d62  jbe     loc_180007EA6
0x180007d68  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180007d6c  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180007d71  mov     [rsp+2E0h+lpcValues], r13; lpftLastWriteTime
0x180007d76  lea     r8, [rbp+1E0h+Name]; lpName
0x180007d7a  mov     [rsp+2E0h+lpcbMaxClassLen], r13; lpcchClass
0x180007d7f  mov     edx, edi; dwIndex
0x180007d81  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r13; lpClass
0x180007d86  mov     [rsp+2E0h+lpcSubKeys], r13; lpReserved
0x180007d8b  mov     [rsp+2E0h+cchName], 105h
0x180007d93  call    cs:__imp_RegEnumKeyExW
0x180007d99  mov     ebx, eax
0x180007d9b  test    eax, eax
0x180007d9d  jle     short loc_180007DA4
0x180007d9f  movzx   ebx, ax
0x180007da2  or      ebx, esi
0x180007da4  test    ebx, ebx
0x180007da6  js      loc_180007E9E
0x180007dac  lea     rdx, Format; lpString2
0x180007db3  lea     rcx, [rbp+1E0h+Name]; lpString1
0x180007db7  call    wcsicmp_ThatWorks
0x180007dbc  test    eax, eax
0x180007dbe  jz      loc_180007E72
0x180007dc4  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180007dc8  lea     rax, [rsp+2E0h+phkResult]
0x180007dcd  mov     r9d, 20019h; samDesired
0x180007dd3  mov     [rsp+2E0h+lpcSubKeys], rax; phkResult
0x180007dd8  xor     r8d, r8d; ulOptions
0x180007ddb  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x180007ddf  call    cs:__imp_RegOpenKeyExW
0x180007de5  mov     ebx, eax
0x180007de7  test    eax, eax
0x180007de9  jle     short loc_180007DF0
0x180007deb  movzx   ebx, ax
0x180007dee  or      ebx, esi
0x180007df0  test    ebx, ebx
0x180007df2  js      loc_180007E94
0x180007df8  test    byte ptr cs:xmmword_18001F260, 4
0x180007dff  jz      short loc_180007E1B
0x180007e01  mov     edx, 23h ; '#'
0x180007e06  lea     r9, [rbp+1E0h+Name]
0x180007e0a  mov     ecx, 402h
0x180007e0f  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180007e16  call    WPP_SF_S
0x180007e1b  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180007e20  lea     rdx, [rbp+1E0h+Name]; Src
0x180007e24  mov     eax, edi
0x180007e26  lea     rsi, [rax+rax*2]
0x180007e2a  shl     rsi, 4
0x180007e2e  add     rsi, r15
0x180007e31  mov     r8, rsi
0x180007e34  call    ZtRegReadSingleRule
0x180007e39  mov     ebx, eax
0x180007e3b  test    eax, eax
0x180007e3d  js      short loc_180007E8A
0x180007e3f  mov     rdx, rsi
0x180007e42  mov     ecx, r14d
0x180007e45  call    ?ZtAddRuleToMap@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEBU_DNS_ZT_RULE@@@Z; ZtAddRuleToMap(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_RULE const *)
0x180007e4a  mov     ebx, eax
0x180007e4c  test    eax, eax
0x180007e4e  js      short loc_180007E80
0x180007e50  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180007e55  test    rcx, rcx
0x180007e58  jz      short loc_180007E65
0x180007e5a  call    cs:__imp_RegCloseKey
0x180007e60  mov     [rsp+2E0h+phkResult], r13
0x180007e65  mov     [rbp+1E0h+Name], r13w
0x180007e6a  inc     r12d
0x180007e6d  mov     esi, 80070000h
0x180007e72  inc     edi
0x180007e74  cmp     edi, [rsp+2E0h+cSubKeys]
0x180007e78  jb      loc_180007D68
0x180007e7e  jmp     short loc_180007EA6
0x180007e80  mov     [rsp+2E0h+var_27C], 20Bh
0x180007e88  jmp     short loc_180007EA6
0x180007e8a  mov     [rsp+2E0h+var_27C], 209h
0x180007e92  jmp     short loc_180007EA6
0x180007e94  mov     [rsp+2E0h+var_27C], 203h
0x180007e9c  jmp     short loc_180007EA6
0x180007e9e  mov     [rsp+2E0h+var_27C], 1F8h
0x180007ea6  cmp     cs:g_fVelocityZtdnsApiRefactor, r13d
0x180007ead  mov     rdx, r15
0x180007eb0  mov     ecx, r12d
0x180007eb3  jz      short loc_180007EBC
0x180007eb5  call    ZtFreeRules
0x180007eba  jmp     short loc_180007EC2
0x180007ebc  call    cs:__imp_DnsFreeZtRules
0x180007ec2  test    byte ptr cs:xmmword_18001F260, 4
0x180007ec9  jz      short loc_180007EEB
0x180007ecb  mov     ecx, ebx
0x180007ecd  call    WX_WIN32_FROM_HR
0x180007ed2  mov     r9d, eax
0x180007ed5  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180007edc  mov     edx, 24h ; '$'
0x180007ee1  mov     ecx, 402h
0x180007ee6  call    WPP_SF_d
0x180007eeb  mov     ecx, ebx
0x180007eed  call    WX_WIN32_FROM_HR
0x180007ef2  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180007ef7  mov     ebx, eax
0x180007ef9  test    rcx, rcx
0x180007efc  jz      short loc_180007F09
0x180007efe  call    cs:__imp_RegCloseKey
0x180007f04  mov     [rsp+2E0h+phkResult], r13
0x180007f09  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180007f0d  test    rcx, rcx
0x180007f10  jz      short loc_180007F18
0x180007f12  call    cs:__imp_RegCloseKey
0x180007f18  mov     eax, ebx
0x180007f1a  mov     rcx, [rbp+1E0h+var_40]
0x180007f21  xor     rcx, rsp; StackCookie
0x180007f24  call    __security_check_cookie
0x180007f29  mov     rbx, [rsp+2E0h+arg_18]
0x180007f31  add     rsp, 2B0h
0x180007f38  pop     r15
0x180007f3a  pop     r14
0x180007f3c  pop     r13
0x180007f3e  pop     r12
0x180007f40  pop     rdi
0x180007f41  pop     rsi
0x180007f42  pop     rbp
0x180007f43  retn
```
