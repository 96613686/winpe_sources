# GetDefaultRssiFromRegistry

- ea: `0x180034ea0`
- end: `0x1800350ef`
- name: `GetDefaultRssiFromRegistry`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800349d4`

## callees

- `0x18000a7f8`
- `0x180012a48`
- `0x180012b74`
- `0x180019bbc`
- `0x180034ea0`
- `0x18003844c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034f91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035051`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034f91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035051`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f0b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f0b`

## pseudocode

```c
__int64 __fastcall GetDefaultRssiFromRegistry(char *a1, char *a2)
{
  char v3; // di
  char v5; // r14
  const WCHAR *v6; // rax
  unsigned int v7; // esi
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  char v10; // r8
  const WCHAR *v11; // rax
  char v12; // al
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY *p_hKey; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  char v17; // [rsp+48h] [rbp-8h]
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD Type; // [rsp+98h] [rbp+48h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v21; // [rsp+A8h] [rbp+58h] BYREF

  Data = -1;
  v21 = -1;
  hKey = 0;
  v3 = 1;
  p_hKey = &hKey;
  cbData = 0;
  Type = 0;
  v5 = 1;
  phkResult = 0;
  v17 = 1;
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_18005FAC0);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, v7);
  }
  else
  {
    cbData = 4;
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_18005FA60);
    v9 = RegQueryValueExW(hKey, v8, 0, &Type, (LPBYTE)&Data, &cbData);
    v10 = Data;
    if ( v9 || Type != 4 || Data > 0x7F )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dll(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, Data, v9, Type, Data);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, Data);
        v10 = Data;
      }
      v3 = -v10;
    }
    cbData = 4;
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_18005FA40);
    v7 = RegQueryValueExW(hKey, v11, 0, &Type, (LPBYTE)&v21, &cbData);
    v12 = v21;
    if ( v7 || Type != 4 || v21 > 0x7F )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dll(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, Type, v7, Type, v21);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, v21);
        v12 = v21;
      }
      v5 = -v12;
    }
  }
  *a1 = v3;
  *a2 = v5;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x180034ea0  push    rbp
0x180034ea2  push    rbx
0x180034ea3  push    rsi
0x180034ea4  push    rdi
0x180034ea5  push    r12
0x180034ea7  push    r14
0x180034ea9  push    r15
0x180034eab  mov     rbp, rsp
0x180034eae  sub     rsp, 50h
0x180034eb2  or      eax, 0FFFFFFFFh
0x180034eb5  xor     ebx, ebx
0x180034eb7  mov     [rbp+Data], eax
0x180034eba  mov     r12, rcx
0x180034ebd  mov     [rbp+arg_18], eax
0x180034ec0  lea     rcx, qword_18005FAC0
0x180034ec7  lea     rax, [rbp+hKey]
0x180034ecb  mov     [rbp+hKey], rbx
0x180034ecf  mov     dil, 1
0x180034ed2  mov     [rbp+var_18], rax
0x180034ed6  mov     r15, rdx
0x180034ed9  mov     [rbp+cbData], ebx
0x180034edc  mov     [rbp+Type], ebx
0x180034edf  mov     r14b, dil
0x180034ee2  mov     [rbp+var_10], rbx
0x180034ee6  mov     [rbp+var_8], dil
0x180034eea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034eef  mov     rdx, rax; lpSubKey
0x180034ef2  mov     r9d, 20019h; samDesired
0x180034ef8  lea     rax, [rbp+var_10]
0x180034efc  xor     r8d, r8d; ulOptions
0x180034eff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034f06  mov     [rsp+50h+phkResult], rax; phkResult
0x180034f0b  call    cs:__imp_RegOpenKeyExW
0x180034f11  lea     rcx, [rbp+var_18]
0x180034f15  mov     esi, eax
0x180034f17  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180034f1c  test    esi, esi
0x180034f1e  jz      short loc_180034F5E
0x180034f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f27  lea     rbx, WPP_GLOBAL_Control
0x180034f2e  cmp     rcx, rbx
0x180034f31  jz      loc_1800350CE
0x180034f37  test    [rcx+1Ch], dil
0x180034f3b  jz      loc_1800350CE
0x180034f41  mov     rcx, [rcx+10h]
0x180034f45  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x180034f4c  mov     edx, 49h ; 'I'
0x180034f51  mov     r9d, esi
0x180034f54  call    WPP_SF_d
0x180034f59  jmp     loc_1800350CE
0x180034f5e  lea     rcx, qword_18005FA60
0x180034f65  mov     [rbp+cbData], 4
0x180034f6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034f71  mov     rcx, [rbp+hKey]; hKey
0x180034f75  lea     r9, [rbp+Type]; lpType
0x180034f79  mov     rdx, rax; lpValueName
0x180034f7c  xor     r8d, r8d; lpReserved
0x180034f7f  lea     rax, [rbp+cbData]
0x180034f83  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180034f88  lea     rax, [rbp+Data]
0x180034f8c  mov     [rsp+50h+phkResult], rax; lpData
0x180034f91  call    cs:__imp_RegQueryValueExW
0x180034f97  mov     r9d, [rbp+Type]
0x180034f9b  mov     r8d, [rbp+Data]
0x180034f9f  test    eax, eax
0x180034fa1  jnz     short loc_180034FEA
0x180034fa3  cmp     r9d, 4
0x180034fa7  jnz     short loc_180034FEA
0x180034fa9  cmp     r8d, 7Fh
0x180034fad  ja      short loc_180034FEA
0x180034faf  mov     rcx, cs:WPP_GLOBAL_Control
0x180034fb6  lea     rbx, WPP_GLOBAL_Control
0x180034fbd  cmp     rcx, rbx
0x180034fc0  jz      short loc_180034FE2
0x180034fc2  test    [rcx+1Ch], r9b
0x180034fc6  jz      short loc_180034FE2
0x180034fc8  mov     rcx, [rcx+10h]
0x180034fcc  lea     edx, [rax+4Ah]
0x180034fcf  mov     r9d, r8d
0x180034fd2  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x180034fd9  call    WPP_SF_d
0x180034fde  mov     r8d, [rbp+Data]
0x180034fe2  mov     dil, r8b
0x180034fe5  neg     dil
0x180034fe8  jmp     short loc_18003501E
0x180034fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ff1  lea     rbx, WPP_GLOBAL_Control
0x180034ff8  cmp     rcx, rbx
0x180034ffb  jz      short loc_18003501E
0x180034ffd  test    byte ptr [rcx+1Ch], 4
0x180035001  jz      short loc_18003501E
0x180035003  mov     rcx, [rcx+10h]
0x180035007  mov     edx, 4Bh ; 'K'
0x18003500c  mov     dword ptr [rsp+50h+lpcbData], r8d
0x180035011  mov     dword ptr [rsp+50h+phkResult], r9d
0x180035016  mov     r9d, eax
0x180035019  call    WPP_SF_Dll
0x18003501e  lea     rcx, qword_18005FA40
0x180035025  mov     [rbp+cbData], 4
0x18003502c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035031  mov     rcx, [rbp+hKey]; hKey
0x180035035  lea     r9, [rbp+Type]; lpType
0x180035039  mov     rdx, rax; lpValueName
0x18003503c  xor     r8d, r8d; lpReserved
0x18003503f  lea     rax, [rbp+cbData]
0x180035043  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180035048  lea     rax, [rbp+arg_18]
0x18003504c  mov     [rsp+50h+phkResult], rax; lpData
0x180035051  call    cs:__imp_RegQueryValueExW
0x180035057  mov     r8d, [rbp+Type]
0x18003505b  mov     esi, eax
0x18003505d  mov     eax, [rbp+arg_18]
0x180035060  test    esi, esi
0x180035062  jnz     short loc_1800350A2
0x180035064  cmp     r8d, 4
0x180035068  jnz     short loc_1800350A2
0x18003506a  cmp     eax, 7Fh
0x18003506d  ja      short loc_1800350A2
0x18003506f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035076  cmp     rcx, rbx
0x180035079  jz      short loc_18003509A
0x18003507b  test    [rcx+1Ch], r8b
0x18003507f  jz      short loc_18003509A
0x180035081  mov     rcx, [rcx+10h]
0x180035085  lea     edx, [rsi+4Ch]
0x180035088  mov     r9d, eax
0x18003508b  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x180035092  call    WPP_SF_d
0x180035097  mov     eax, [rbp+arg_18]
0x18003509a  mov     r14b, al
0x18003509d  neg     r14b
0x1800350a0  jmp     short loc_1800350CE
0x1800350a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350a9  cmp     rcx, rbx
0x1800350ac  jz      short loc_1800350CE
0x1800350ae  test    byte ptr [rcx+1Ch], 4
0x1800350b2  jz      short loc_1800350CE
0x1800350b4  mov     rcx, [rcx+10h]
0x1800350b8  mov     edx, 4Dh ; 'M'
0x1800350bd  mov     dword ptr [rsp+50h+lpcbData], eax
0x1800350c1  mov     r9d, esi
0x1800350c4  mov     dword ptr [rsp+50h+phkResult], r8d
0x1800350c9  call    WPP_SF_Dll
0x1800350ce  lea     rcx, [rbp+hKey]
0x1800350d2  mov     [r12], dil
0x1800350d6  mov     [r15], r14b
0x1800350d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800350de  mov     eax, esi
0x1800350e0  add     rsp, 50h
0x1800350e4  pop     r15
0x1800350e6  pop     r14
0x1800350e8  pop     r12
0x1800350ea  pop     rdi
0x1800350eb  pop     rsi
0x1800350ec  pop     rbx
0x1800350ed  pop     rbp
0x1800350ee  retn
```
