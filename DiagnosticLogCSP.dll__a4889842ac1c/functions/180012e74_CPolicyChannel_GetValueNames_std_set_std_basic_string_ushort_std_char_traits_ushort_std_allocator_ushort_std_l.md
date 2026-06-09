# CPolicyChannel::GetValueNames(std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180012e74`
- end: `0x18001308a`
- name: `?GetValueNames@CPolicyChannel@@QEAAJAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c410`

## callees

- `0x180001b60`
- `0x18000a600`
- `0x18000fb98`
- `0x180012238`
- `0x180012e74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012f52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012f6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012f84`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012fd4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012f52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012f6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012f84`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012fd4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180012f41`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180012f41`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012ee6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012ee6`

## string_xrefs

- `0x180012fc9`: `ChannelAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyChannel::GetValueNames(HKEY *a1, __int64 a2)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  DWORD v6; // edi
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v10[16]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v11[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v12[16]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v13; // [rsp+98h] [rbp-68h] BYREF
  __int128 v14; // [rsp+A8h] [rbp-58h]
  WCHAR ValueName[512]; // [rsp+C0h] [rbp-40h] BYREF

  cValues = 0;
  v4 = RegQueryInfoKeyW(*a1, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v5 = v4;
  if ( !v4 )
  {
    v5 = 0;
    v6 = 0;
    if ( !cValues )
      return v5;
    while ( 1 )
    {
      cchValueName = 512;
      RegEnumValueW(*a1, v6, ValueName, &cchValueName, 0, 0, 0, 0);
      if ( !(unsigned int)_o__wcsicmp(ValueName, L"Retention")
        || !(unsigned int)_o__wcsicmp(ValueName, L"AutoBackupLogFiles") )
      {
        v13 = 0;
        v14 = 0;
        std::wstring::_Construct<1,unsigned short const *>((char **)&v13, L"ActionWhenFull", 0xEu);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
          a2,
          v12,
          &v13);
        goto LABEL_12;
      }
      if ( !(unsigned int)_o__wcsicmp(ValueName, L"MaxSize") )
        break;
      if ( !(unsigned int)_o__wcsicmp(ValueName, L"ChannelAccess") )
      {
        v13 = 0;
        v14 = 0;
        std::wstring::_Construct<1,unsigned short const *>((char **)&v13, L"SDDL", 4u);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
          a2,
          v11,
          &v13);
        goto LABEL_12;
      }
LABEL_13:
      if ( ++v6 >= cValues )
        return v5;
    }
    v13 = 0;
    v14 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v13, L"MaximumFileSize", 0xFu);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      a2,
      v10,
      &v13);
LABEL_12:
    std::wstring::~wstring((char **)&v13);
    goto LABEL_13;
  }
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x180012e74  mov     [rsp-8+arg_10], rbx
0x180012e79  push    rbp
0x180012e7a  push    rsi
0x180012e7b  push    rdi
0x180012e7c  push    r14
0x180012e7e  push    r15
0x180012e80  lea     rbp, [rsp-3D0h]
0x180012e88  sub     rsp, 4D0h
0x180012e8f  mov     rax, cs:__security_cookie
0x180012e96  xor     rax, rsp
0x180012e99  mov     [rbp+3F0h+var_30], rax
0x180012ea0  mov     rsi, rdx
0x180012ea3  mov     r14, rcx
0x180012ea6  xor     r15d, r15d
0x180012ea9  mov     [rsp+4F0h+cValues], r15d
0x180012eae  mov     [rsp+4F0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180012eb3  mov     [rsp+4F0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180012eb8  mov     [rsp+4F0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180012ebd  mov     [rsp+4F0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180012ec2  lea     rax, [rsp+4F0h+cValues]
0x180012ec7  mov     [rsp+4F0h+lpcValues], rax; lpcValues
0x180012ecc  mov     [rsp+4F0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180012ed1  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180012ed6  mov     [rsp+4F0h+lpcSubKeys], r15; lpcSubKeys
0x180012edb  xor     r9d, r9d; lpReserved
0x180012ede  xor     r8d, r8d; lpcchClass
0x180012ee1  xor     edx, edx; lpClass
0x180012ee3  mov     rcx, [rcx]; hKey
0x180012ee6  call    cs:__imp_RegQueryInfoKeyW
0x180012eec  mov     ebx, eax
0x180012eee  test    eax, eax
0x180012ef0  jz      short loc_180012F06
0x180012ef2  jle     loc_180013062
0x180012ef8  movzx   ebx, ax
0x180012efb  or      ebx, 80070000h
0x180012f01  jmp     loc_180013062
0x180012f06  mov     ebx, r15d
0x180012f09  mov     edi, r15d
0x180012f0c  cmp     [rsp+4F0h+cValues], r15d
0x180012f11  jbe     loc_180013062
0x180012f17  mov     [rsp+4F0h+cchValueName], 200h
0x180012f1f  mov     [rsp+4F0h+lpcValues], r15; lpcbData
0x180012f24  mov     [rsp+4F0h+lpcbMaxClassLen], r15; lpData
0x180012f29  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r15; lpType
0x180012f2e  mov     [rsp+4F0h+lpcSubKeys], r15; lpReserved
0x180012f33  lea     r9, [rsp+4F0h+cchValueName]; lpcchValueName
0x180012f38  lea     r8, [rbp+3F0h+ValueName]; lpValueName
0x180012f3c  mov     edx, edi; dwIndex
0x180012f3e  mov     rcx, [r14]; hKey
0x180012f41  call    cs:__imp_RegEnumValueW
0x180012f47  lea     rdx, aRetention; "Retention"
0x180012f4e  lea     rcx, [rbp+3F0h+ValueName]
0x180012f52  call    cs:__imp__o__wcsicmp
0x180012f58  test    eax, eax
0x180012f5a  jz      loc_180013016
0x180012f60  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x180012f67  lea     rcx, [rbp+3F0h+ValueName]
0x180012f6b  call    cs:__imp__o__wcsicmp
0x180012f71  test    eax, eax
0x180012f73  jz      loc_180013016
0x180012f79  lea     rdx, aMaxsize; "MaxSize"
0x180012f80  lea     rcx, [rbp+3F0h+ValueName]
0x180012f84  call    cs:__imp__o__wcsicmp
0x180012f8a  test    eax, eax
0x180012f8c  jnz     short loc_180012FC9
0x180012f8e  xorps   xmm0, xmm0
0x180012f91  movups  [rbp+3F0h+var_458], xmm0
0x180012f95  xorps   xmm1, xmm1
0x180012f98  movdqu  [rbp+3F0h+var_448], xmm1
0x180012f9d  lea     r8d, [rax+0Fh]
0x180012fa1  lea     rdx, aMaximumfilesiz; "MaximumFileSize"
0x180012fa8  lea     rcx, [rbp+3F0h+var_458]
0x180012fac  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180012fb1  nop
0x180012fb2  lea     r8, [rbp+3F0h+var_458]
0x180012fb6  lea     rdx, [rsp+4F0h+var_488]
0x180012fbb  mov     rcx, rsi
0x180012fbe  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180012fc3  nop
0x180012fc4  jmp     loc_18001304D
0x180012fc9  lea     rdx, aChannelaccess; "ChannelAccess"
0x180012fd0  lea     rcx, [rbp+3F0h+ValueName]
0x180012fd4  call    cs:__imp__o__wcsicmp
0x180012fda  test    eax, eax
0x180012fdc  jnz     short loc_180013056
0x180012fde  xorps   xmm0, xmm0
0x180012fe1  movups  [rbp+3F0h+var_458], xmm0
0x180012fe5  xorps   xmm1, xmm1
0x180012fe8  movdqu  [rbp+3F0h+var_448], xmm1
0x180012fed  lea     r8d, [rax+4]
0x180012ff1  lea     rdx, aSddl; "SDDL"
0x180012ff8  lea     rcx, [rbp+3F0h+var_458]
0x180012ffc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013001  nop
0x180013002  lea     r8, [rbp+3F0h+var_458]
0x180013006  lea     rdx, [rsp+4F0h+var_478]
0x18001300b  mov     rcx, rsi
0x18001300e  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180013013  nop
0x180013014  jmp     short loc_18001304D
0x180013016  xorps   xmm0, xmm0
0x180013019  movups  [rbp+3F0h+var_458], xmm0
0x18001301d  xorps   xmm1, xmm1
0x180013020  movdqu  [rbp+3F0h+var_448], xmm1
0x180013025  mov     r8d, 0Eh
0x18001302b  lea     rdx, aActionwhenfull; "ActionWhenFull"
0x180013032  lea     rcx, [rbp+3F0h+var_458]
0x180013036  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001303b  nop
0x18001303c  lea     r8, [rbp+3F0h+var_458]
0x180013040  lea     rdx, [rbp+3F0h+var_468]
0x180013044  mov     rcx, rsi
0x180013047  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18001304c  nop
0x18001304d  lea     rcx, [rbp+3F0h+var_458]
0x180013051  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013056  inc     edi
0x180013058  cmp     edi, [rsp+4F0h+cValues]
0x18001305c  jb      loc_180012F17
0x180013062  mov     eax, ebx
0x180013064  mov     rcx, [rbp+3F0h+var_30]
0x18001306b  xor     rcx, rsp; StackCookie
0x18001306e  call    __security_check_cookie
0x180013073  mov     rbx, [rsp+4F0h+arg_10]
0x18001307b  add     rsp, 4D0h
0x180013082  pop     r15
0x180013084  pop     r14
0x180013086  pop     rdi
0x180013087  pop     rsi
0x180013088  pop     rbp
0x180013089  retn
```
