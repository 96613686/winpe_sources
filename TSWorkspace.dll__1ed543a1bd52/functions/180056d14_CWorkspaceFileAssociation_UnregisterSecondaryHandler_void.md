# CWorkspaceFileAssociation::UnregisterSecondaryHandler(void *)

- ea: `0x180056d14`
- end: `0x180056fed`
- name: `?UnregisterSecondaryHandler@CWorkspaceFileAssociation@@IEAAJPEAX@Z`
- size: `729`
- prototype: `int(CWorkspaceFileAssociation *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180056a98`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18001e41c`
- `0x18001e610`
- `0x180020bf0`
- `0x180025824`
- `0x180056d14`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x180056e23`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x180056e23`
- `ADVAPI32!RegCloseKey` at `0x180056fb3`
- `ADVAPI32!RegCloseKey` at `0x180056fb3`
- `ADVAPI32!RegDeleteValueW` at `0x180056f17`
- `ADVAPI32!RegDeleteValueW` at `0x180056f17`

## string_xrefs

- `0x180056da4`: `OpenWithProgIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall CWorkspaceFileAssociation::UnregisterSecondaryHandler(CWorkspaceFileAssociation *this, void *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  const WCHAR *v8; // rax
  int v9; // ebx
  __int64 v10; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v12; // edi
  unsigned int v13; // eax
  const WCHAR *v14; // rax
  int v15; // ebx
  unsigned int v16; // edi
  unsigned int v17; // eax
  unsigned int v19; // [rsp+40h] [rbp-D8h]
  HKEY hKey[2]; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-C0h] BYREF
  _BYTE v22[32]; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v23[32]; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v24[32]; // [rsp+B8h] [rbp-60h] BYREF
  _BYTE v25[40]; // [rsp+D8h] [rbp-40h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  v4 = std::wstring::wstring(v25, L"Software\\classes");
  v5 = std::operator+<unsigned short>(v24, v4, L"\\");
  v6 = std::operator+<unsigned short>(v23, v5, (char *)this + 48);
  v7 = std::operator+<unsigned short>(v22, v6, L"\\");
  std::operator+<unsigned short>(v21, v7, L"OpenWithProgIds");
  std::wstring::~wstring(v22);
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(v25);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  v9 = RegOpenKeyTransactedW(HKEY_CURRENT_USER, v8, 0, 0x2001Fu, hKey, a2, 0);
  if ( v9 == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
        CurrentThreadActivityIdPrefix,
        v10);
    }
    v19 = 1;
  }
  else if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v9 > 0 )
        v12 = (unsigned __int16)v9 | 0x80070000;
      else
        v12 = v9;
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v13, v12);
    }
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v19 = v9;
  }
  else
  {
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
    v15 = RegDeleteValueW(hKey[0], v14);
    if ( v15 == 2 )
    {
      v19 = 1;
    }
    else if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        else
          v16 = v15;
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v17, v16);
      }
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v19 = v15;
    }
    else
    {
      v19 = 0;
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  std::wstring::~wstring(v21);
  return v19;
}

```

## disassembly

```asm
0x180056d14  mov     r11, rsp
0x180056d17  push    rdi
0x180056d18  sub     rsp, 110h
0x180056d1f  mov     [rsp+118h+var_C8], 0FFFFFFFFFFFFFFFEh
0x180056d28  mov     [r11+18h], rbx
0x180056d2c  mov     [r11+20h], rsi
0x180056d30  mov     rax, cs:__security_cookie
0x180056d37  xor     rax, rsp
0x180056d3a  mov     [rsp+118h+var_18], rax
0x180056d42  mov     rbx, rdx
0x180056d45  mov     rdi, rcx
0x180056d48  mov     [rsp+118h+hKey], 0
0x180056d51  lea     rdx, aSoftwareClasse; "Software\\classes"
0x180056d58  lea     rcx, [r11-40h]
0x180056d5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180056d61  nop
0x180056d62  lea     r8, SubStr; "\\"
0x180056d69  mov     rdx, rax
0x180056d6c  lea     rcx, [rsp+118h+var_60]
0x180056d74  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180056d79  nop
0x180056d7a  lea     r8, [rdi+30h]
0x180056d7e  mov     rdx, rax
0x180056d81  lea     rcx, [rsp+118h+var_80]
0x180056d89  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180056d8e  nop
0x180056d8f  lea     r8, SubStr; "\\"
0x180056d96  mov     rdx, rax
0x180056d99  lea     rcx, [rsp+118h+var_A0]
0x180056d9e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180056da3  nop
0x180056da4  lea     r8, aOpenwithprogid; "OpenWithProgIds"
0x180056dab  mov     rdx, rax
0x180056dae  lea     rcx, [rsp+118h+var_C0]
0x180056db3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180056db8  nop
0x180056db9  lea     rcx, [rsp+118h+var_A0]; void *
0x180056dbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056dc3  nop
0x180056dc4  lea     rcx, [rsp+118h+var_80]; void *
0x180056dcc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056dd1  nop
0x180056dd2  lea     rcx, [rsp+118h+var_60]; void *
0x180056dda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056ddf  nop
0x180056de0  lea     rcx, [rsp+118h+var_40]; void *
0x180056de8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056ded  nop
0x180056dee  lea     rcx, [rsp+118h+var_C0]
0x180056df3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056df8  mov     rdx, rax; lpSubKey
0x180056dfb  mov     [rsp+118h+pExtendedParemeter], 0; pExtendedParemeter
0x180056e04  mov     [rsp+118h+hTransaction], rbx; hTransaction
0x180056e09  lea     rax, [rsp+118h+hKey]
0x180056e0e  mov     [rsp+118h+phkResult], rax; phkResult
0x180056e13  mov     r9d, 2001Fh; samDesired
0x180056e19  xor     r8d, r8d; ulOptions
0x180056e1c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180056e23  call    cs:__imp_RegOpenKeyTransactedW
0x180056e29  mov     ebx, eax
0x180056e2b  cmp     eax, 2
0x180056e2e  jnz     short loc_180056E91
0x180056e30  lea     rax, WPP_GLOBAL_Control
0x180056e37  mov     rdx, cs:WPP_GLOBAL_Control
0x180056e3e  cmp     rdx, rax
0x180056e41  jz      short loc_180056E84
0x180056e43  test    byte ptr [rdx+1Ch], 1
0x180056e47  jz      short loc_180056E84
0x180056e49  cmp     byte ptr [rdx+19h], 4
0x180056e4d  jb      short loc_180056E84
0x180056e4f  lea     rcx, [rdi+30h]
0x180056e53  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056e58  mov     rbx, rax
0x180056e5b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056e60  mov     edx, 46h ; 'F'
0x180056e65  mov     [rsp+118h+phkResult], rbx
0x180056e6a  mov     r9d, eax
0x180056e6d  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056e74  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e7b  mov     rcx, [rcx+10h]
0x180056e7f  call    WPP_SF_DS
0x180056e84  mov     [rsp+118h+var_D8], 1
0x180056e8c  jmp     loc_180056FA9
0x180056e91  test    ebx, ebx
0x180056e93  jz      short loc_180056F03
0x180056e95  lea     rax, WPP_GLOBAL_Control
0x180056e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ea3  cmp     rcx, rax
0x180056ea6  jz      short loc_180056EED
0x180056ea8  test    byte ptr [rcx+1Ch], 8
0x180056eac  jz      short loc_180056EED
0x180056eae  cmp     byte ptr [rcx+19h], 2
0x180056eb2  jb      short loc_180056EED
0x180056eb4  test    ebx, ebx
0x180056eb6  jg      short loc_180056EBC
0x180056eb8  mov     edi, ebx
0x180056eba  jmp     short loc_180056EC5
0x180056ebc  movzx   edi, bx
0x180056ebf  or      edi, 80070000h
0x180056ec5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056eca  mov     edx, 47h ; 'G'
0x180056ecf  mov     dword ptr [rsp+118h+phkResult], edi
0x180056ed3  mov     r9d, eax
0x180056ed6  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ee4  mov     rcx, [rcx+10h]
0x180056ee8  call    WPP_SF_Dd
0x180056eed  test    ebx, ebx
0x180056eef  jle     short loc_180056EFA
0x180056ef1  movzx   ebx, bx
0x180056ef4  or      ebx, 80070000h
0x180056efa  mov     [rsp+118h+var_D8], ebx
0x180056efe  jmp     loc_180056FA9
0x180056f03  lea     rcx, [rdi+0D8h]
0x180056f0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056f0f  mov     rdx, rax; lpValueName
0x180056f12  mov     rcx, [rsp+118h+hKey]; hKey
0x180056f17  call    cs:__imp_RegDeleteValueW
0x180056f1d  mov     ebx, eax
0x180056f1f  cmp     eax, 2
0x180056f22  jnz     short loc_180056F2E
0x180056f24  mov     [rsp+118h+var_D8], 1
0x180056f2c  jmp     short loc_180056FA9
0x180056f2e  test    ebx, ebx
0x180056f30  jz      short loc_180056F9D
0x180056f32  lea     rax, WPP_GLOBAL_Control
0x180056f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f40  cmp     rcx, rax
0x180056f43  jz      short loc_180056F8A
0x180056f45  test    byte ptr [rcx+1Ch], 8
0x180056f49  jz      short loc_180056F8A
0x180056f4b  cmp     byte ptr [rcx+19h], 2
0x180056f4f  jb      short loc_180056F8A
0x180056f51  test    ebx, ebx
0x180056f53  jg      short loc_180056F59
0x180056f55  mov     edi, ebx
0x180056f57  jmp     short loc_180056F62
0x180056f59  movzx   edi, bx
0x180056f5c  or      edi, 80070000h
0x180056f62  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180056f67  mov     edx, 48h ; 'H'
0x180056f6c  mov     dword ptr [rsp+118h+phkResult], edi
0x180056f70  mov     r9d, eax
0x180056f73  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180056f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f81  mov     rcx, [rcx+10h]
0x180056f85  call    WPP_SF_Dd
0x180056f8a  test    ebx, ebx
0x180056f8c  jle     short loc_180056F97
0x180056f8e  movzx   ebx, bx
0x180056f91  or      ebx, 80070000h
0x180056f97  mov     [rsp+118h+var_D8], ebx
0x180056f9b  jmp     short loc_180056FA9
0x180056f9d  mov     [rsp+118h+var_D8], 0
0x180056fa5  jmp     short loc_180056FA9
0x180056fa7  jmp     short $+2
0x180056fa9  mov     rcx, [rsp+118h+hKey]; hKey
0x180056fae  test    rcx, rcx
0x180056fb1  jz      short loc_180056FBA
0x180056fb3  call    cs:__imp_RegCloseKey
0x180056fb9  nop
0x180056fba  lea     rcx, [rsp+118h+var_C0]; void *
0x180056fbf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056fc4  mov     eax, [rsp+118h+var_D8]
0x180056fc8  mov     rcx, [rsp+118h+var_18]
0x180056fd0  xor     rcx, rsp; StackCookie
0x180056fd3  call    __security_check_cookie
0x180056fd8  lea     r11, [rsp+118h+var_8]
0x180056fe0  mov     rbx, [r11+20h]
0x180056fe4  mov     rsi, [r11+28h]
0x180056fe8  mov     rsp, r11
0x180056feb  pop     rdi
0x180056fec  retn
```
