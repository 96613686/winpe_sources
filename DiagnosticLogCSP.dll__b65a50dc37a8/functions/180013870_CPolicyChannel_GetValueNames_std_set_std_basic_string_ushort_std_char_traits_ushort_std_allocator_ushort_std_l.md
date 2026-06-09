# CPolicyChannel::GetValueNames(std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180013870`
- end: `0x180013aab`
- name: `?GetValueNames@CPolicyChannel@@QEAAJAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c980`

## callees

- `0x180001b90`
- `0x18000a924`
- `0x1800103a8`
- `0x180012bf8`
- `0x180013870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001395a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013979`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013998`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800139ee`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001395a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013979`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180013998`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800139ee`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013943`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013943`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800138e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800138e2`

## string_xrefs

- `0x1800139e3`: `ChannelAccess`

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
        std::wstring::_Construct<1,unsigned short const *>(&v13, L"ActionWhenFull", 14);
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
        std::wstring::_Construct<1,unsigned short const *>(&v13, L"SDDL", 4);
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
    std::wstring::_Construct<1,unsigned short const *>(&v13, L"MaximumFileSize", 15);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      a2,
      v10,
      &v13);
LABEL_12:
    std::wstring::~wstring(&v13);
    goto LABEL_13;
  }
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x180013870  mov     [rsp-8+arg_10], rbx
0x180013875  push    rbp
0x180013876  push    rsi
0x180013877  push    rdi
0x180013878  push    r14
0x18001387a  push    r15
0x18001387c  lea     rbp, [rsp-3D0h]
0x180013884  sub     rsp, 4D0h
0x18001388b  mov     rax, cs:__security_cookie
0x180013892  xor     rax, rsp
0x180013895  mov     [rbp+3F0h+var_30], rax
0x18001389c  mov     rsi, rdx
0x18001389f  mov     r14, rcx
0x1800138a2  xor     r15d, r15d
0x1800138a5  mov     [rsp+4F0h+cValues], r15d
0x1800138aa  mov     [rsp+4F0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800138af  mov     [rsp+4F0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800138b4  mov     [rsp+4F0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800138b9  mov     [rsp+4F0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800138be  lea     rax, [rsp+4F0h+cValues]
0x1800138c3  mov     [rsp+4F0h+lpcValues], rax; lpcValues
0x1800138c8  mov     [rsp+4F0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800138cd  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800138d2  mov     [rsp+4F0h+lpcSubKeys], r15; lpcSubKeys
0x1800138d7  xor     r9d, r9d; lpReserved
0x1800138da  xor     r8d, r8d; lpcchClass
0x1800138dd  xor     edx, edx; lpClass
0x1800138df  mov     rcx, [rcx]; hKey
0x1800138e2  call    cs:__imp_RegQueryInfoKeyW
0x1800138e9  nop     dword ptr [rax+rax+00h]
0x1800138ee  mov     ebx, eax
0x1800138f0  test    eax, eax
0x1800138f2  jz      short loc_180013908
0x1800138f4  jle     loc_180013A82
0x1800138fa  movzx   ebx, ax
0x1800138fd  or      ebx, 80070000h
0x180013903  jmp     loc_180013A82
0x180013908  mov     ebx, r15d
0x18001390b  mov     edi, r15d
0x18001390e  cmp     [rsp+4F0h+cValues], r15d
0x180013913  jbe     loc_180013A82
0x180013919  mov     [rsp+4F0h+cchValueName], 200h
0x180013921  mov     [rsp+4F0h+lpcValues], r15; lpcbData
0x180013926  mov     [rsp+4F0h+lpcbMaxClassLen], r15; lpData
0x18001392b  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r15; lpType
0x180013930  mov     [rsp+4F0h+lpcSubKeys], r15; lpReserved
0x180013935  lea     r9, [rsp+4F0h+cchValueName]; lpcchValueName
0x18001393a  lea     r8, [rbp+3F0h+ValueName]; lpValueName
0x18001393e  mov     edx, edi; dwIndex
0x180013940  mov     rcx, [r14]; hKey
0x180013943  call    cs:__imp_RegEnumValueW
0x18001394a  nop     dword ptr [rax+rax+00h]
0x18001394f  lea     rdx, aRetention; "Retention"
0x180013956  lea     rcx, [rbp+3F0h+ValueName]
0x18001395a  call    cs:__imp__o__wcsicmp
0x180013961  nop     dword ptr [rax+rax+00h]
0x180013966  test    eax, eax
0x180013968  jz      loc_180013A36
0x18001396e  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x180013975  lea     rcx, [rbp+3F0h+ValueName]
0x180013979  call    cs:__imp__o__wcsicmp
0x180013980  nop     dword ptr [rax+rax+00h]
0x180013985  test    eax, eax
0x180013987  jz      loc_180013A36
0x18001398d  lea     rdx, aMaxsize; "MaxSize"
0x180013994  lea     rcx, [rbp+3F0h+ValueName]
0x180013998  call    cs:__imp__o__wcsicmp
0x18001399f  nop     dword ptr [rax+rax+00h]
0x1800139a4  test    eax, eax
0x1800139a6  jnz     short loc_1800139E3
0x1800139a8  xorps   xmm0, xmm0
0x1800139ab  movups  [rbp+3F0h+var_458], xmm0
0x1800139af  xorps   xmm1, xmm1
0x1800139b2  movdqu  [rbp+3F0h+var_448], xmm1
0x1800139b7  lea     r8d, [rax+0Fh]
0x1800139bb  lea     rdx, aMaximumfilesiz; "MaximumFileSize"
0x1800139c2  lea     rcx, [rbp+3F0h+var_458]
0x1800139c6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800139cb  nop
0x1800139cc  lea     r8, [rbp+3F0h+var_458]
0x1800139d0  lea     rdx, [rsp+4F0h+var_488]
0x1800139d5  mov     rcx, rsi
0x1800139d8  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x1800139dd  nop
0x1800139de  jmp     loc_180013A6D
0x1800139e3  lea     rdx, aChannelaccess; "ChannelAccess"
0x1800139ea  lea     rcx, [rbp+3F0h+ValueName]
0x1800139ee  call    cs:__imp__o__wcsicmp
0x1800139f5  nop     dword ptr [rax+rax+00h]
0x1800139fa  test    eax, eax
0x1800139fc  jnz     short loc_180013A76
0x1800139fe  xorps   xmm0, xmm0
0x180013a01  movups  [rbp+3F0h+var_458], xmm0
0x180013a05  xorps   xmm1, xmm1
0x180013a08  movdqu  [rbp+3F0h+var_448], xmm1
0x180013a0d  lea     r8d, [rax+4]
0x180013a11  lea     rdx, aSddl; "SDDL"
0x180013a18  lea     rcx, [rbp+3F0h+var_458]
0x180013a1c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013a21  nop
0x180013a22  lea     r8, [rbp+3F0h+var_458]
0x180013a26  lea     rdx, [rsp+4F0h+var_478]
0x180013a2b  mov     rcx, rsi
0x180013a2e  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180013a33  nop
0x180013a34  jmp     short loc_180013A6D
0x180013a36  xorps   xmm0, xmm0
0x180013a39  movups  [rbp+3F0h+var_458], xmm0
0x180013a3d  xorps   xmm1, xmm1
0x180013a40  movdqu  [rbp+3F0h+var_448], xmm1
0x180013a45  mov     r8d, 0Eh
0x180013a4b  lea     rdx, aActionwhenfull; "ActionWhenFull"
0x180013a52  lea     rcx, [rbp+3F0h+var_458]
0x180013a56  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013a5b  nop
0x180013a5c  lea     r8, [rbp+3F0h+var_458]
0x180013a60  lea     rdx, [rbp+3F0h+var_468]
0x180013a64  mov     rcx, rsi
0x180013a67  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180013a6c  nop
0x180013a6d  lea     rcx, [rbp+3F0h+var_458]
0x180013a71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013a76  inc     edi
0x180013a78  cmp     edi, [rsp+4F0h+cValues]
0x180013a7c  jb      loc_180013919
0x180013a82  mov     eax, ebx
0x180013a84  mov     rcx, [rbp+3F0h+var_30]
0x180013a8b  xor     rcx, rsp; StackCookie
0x180013a8e  call    __security_check_cookie
0x180013a93  mov     rbx, [rsp+4F0h+arg_10]
0x180013a9b  add     rsp, 4D0h
0x180013aa2  pop     r15
0x180013aa4  pop     r14
0x180013aa6  pop     rdi
0x180013aa7  pop     rsi
0x180013aa8  pop     rbp
0x180013aa9  retn
```
