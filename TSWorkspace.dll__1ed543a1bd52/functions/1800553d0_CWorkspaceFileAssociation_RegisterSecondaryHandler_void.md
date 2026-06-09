# CWorkspaceFileAssociation::RegisterSecondaryHandler(void *)

- ea: `0x1800553d0`
- end: `0x1800556e1`
- name: `?RegisterSecondaryHandler@CWorkspaceFileAssociation@@IEAAJPEAX@Z`
- size: `785`
- prototype: `__int64 __fastcall(CWorkspaceFileAssociation *this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180054b64`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18001e41c`
- `0x18001e610`
- `0x180025824`
- `0x18003ce1c`
- `0x1800553d0`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055579`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055579`
- `ADVAPI32!RegCloseKey` at `0x1800556a3`
- `ADVAPI32!RegCloseKey` at `0x1800556a3`
- `ADVAPI32!RegSetValueExW` at `0x18005561d`
- `ADVAPI32!RegSetValueExW` at `0x18005561d`

## string_xrefs

- `0x18005546f`: `OpenWithProgIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkspaceFileAssociation::RegisterSecondaryHandler(CWorkspaceFileAssociation *this, void *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  const WCHAR *v10; // rax
  int v11; // ebx
  unsigned int v12; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const WCHAR *v14; // rax
  int v15; // ebx
  unsigned int v16; // edi
  unsigned int v17; // eax
  unsigned int v19; // [rsp+60h] [rbp-E8h]
  DWORD dwDisposition; // [rsp+64h] [rbp-E4h] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp-E0h] BYREF
  _BYTE v22[32]; // [rsp+78h] [rbp-D0h] BYREF
  _BYTE v23[32]; // [rsp+98h] [rbp-B0h] BYREF
  _BYTE v24[32]; // [rsp+B8h] [rbp-90h] BYREF
  _BYTE v25[32]; // [rsp+D8h] [rbp-70h] BYREF
  _BYTE v26[40]; // [rsp+F8h] [rbp-50h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  dwDisposition = 0;
  v4 = std::wstring::wstring(v26, L"Software\\classes");
  v5 = std::operator+<unsigned short>(v25, v4, L"\\");
  v6 = std::operator+<unsigned short>(v24, v5, (char *)this + 48);
  v7 = std::operator+<unsigned short>(v23, v6, L"\\");
  std::operator+<unsigned short>(v22, v7, L"OpenWithProgIds");
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(v25);
  std::wstring::~wstring(v26);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v8);
  }
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  v11 = RegCreateKeyTransactedW(HKEY_CURRENT_USER, v10, 0, 0, 0, 0x20006u, 0, hKey, &dwDisposition, a2, 0);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      else
        v12 = v11;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
        CurrentThreadActivityIdPrefix,
        v12);
    }
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v19 = v11;
  }
  else
  {
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
    v15 = RegSetValueExW(hKey[0], v14, 0, 1u, (const BYTE *)&LocaleName, 2u);
    if ( v15 )
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
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v17, v16);
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
  std::wstring::~wstring(v22);
  return v19;
}

```

## disassembly

```asm
0x1800553d0  mov     r11, rsp
0x1800553d3  push    rdi
0x1800553d4  push    r14
0x1800553d6  push    r15
0x1800553d8  sub     rsp, 130h
0x1800553df  mov     [rsp+148h+var_D8], 0FFFFFFFFFFFFFFFEh
0x1800553e8  mov     [r11+18h], rbx
0x1800553ec  mov     [r11+20h], rsi
0x1800553f0  mov     rax, cs:__security_cookie
0x1800553f7  xor     rax, rsp
0x1800553fa  mov     [rsp+148h+var_28], rax
0x180055402  mov     r14, rdx
0x180055405  mov     rsi, rcx
0x180055408  mov     [rsp+148h+hKey], 0
0x180055411  mov     [rsp+148h+dwDisposition], 0
0x180055419  lea     rdx, aSoftwareClasse; "Software\\classes"
0x180055420  lea     rcx, [r11-50h]
0x180055424  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180055429  nop
0x18005542a  lea     r8, SubStr; "\\"
0x180055431  mov     rdx, rax
0x180055434  lea     rcx, [rsp+148h+var_70]
0x18005543c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180055441  nop
0x180055442  lea     r8, [rsi+30h]
0x180055446  mov     rdx, rax
0x180055449  lea     rcx, [rsp+148h+var_90]
0x180055451  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180055456  nop
0x180055457  lea     r8, SubStr; "\\"
0x18005545e  mov     rdx, rax
0x180055461  lea     rcx, [rsp+148h+var_B0]
0x180055469  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18005546e  nop
0x18005546f  lea     r8, aOpenwithprogid; "OpenWithProgIds"
0x180055476  mov     rdx, rax
0x180055479  lea     rcx, [rsp+148h+var_D0]
0x18005547e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180055483  nop
0x180055484  lea     rcx, [rsp+148h+var_B0]; void *
0x18005548c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055491  nop
0x180055492  lea     rcx, [rsp+148h+var_90]; void *
0x18005549a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005549f  nop
0x1800554a0  lea     rcx, [rsp+148h+var_70]; void *
0x1800554a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800554ad  nop
0x1800554ae  lea     rcx, [rsp+148h+var_50]; void *
0x1800554b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800554bb  lea     r15, WPP_GLOBAL_Control
0x1800554c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800554c9  cmp     rax, r15
0x1800554cc  jz      short loc_180055524
0x1800554ce  test    byte ptr [rax+1Ch], 1
0x1800554d2  jz      short loc_180055524
0x1800554d4  cmp     byte ptr [rax+19h], 4
0x1800554d8  jb      short loc_180055524
0x1800554da  lea     rcx, [rsi+30h]
0x1800554de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800554e3  mov     rdi, rax
0x1800554e6  lea     rcx, [rsi+0D8h]
0x1800554ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800554f2  mov     rbx, rax
0x1800554f5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800554fa  mov     edx, 3Eh ; '>'
0x1800554ff  mov     qword ptr [rsp+148h+samDesired], rdi; __int64
0x180055504  mov     qword ptr [rsp+148h+dwOptions], rbx; __int64
0x180055509  mov     r9d, eax
0x18005550c  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180055513  mov     rcx, cs:WPP_GLOBAL_Control
0x18005551a  mov     rcx, [rcx+10h]; LoggerHandle
0x18005551e  call    WPP_SF_DSS
0x180055523  nop
0x180055524  lea     rcx, [rsp+148h+var_D0]
0x180055529  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005552e  mov     rdx, rax; lpSubKey
0x180055531  mov     [rsp+148h+pExtendedParemeter], 0; pExtendedParemeter
0x18005553a  mov     [rsp+148h+hTransaction], r14; hTransaction
0x18005553f  lea     rax, [rsp+148h+dwDisposition]
0x180055544  mov     [rsp+148h+lpdwDisposition], rax; lpdwDisposition
0x180055549  lea     rax, [rsp+148h+hKey]
0x18005554e  mov     [rsp+148h+phkResult], rax; phkResult
0x180055553  mov     [rsp+148h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005555c  mov     [rsp+148h+samDesired], 20006h; samDesired
0x180055564  mov     [rsp+148h+dwOptions], 0; dwOptions
0x18005556c  xor     r9d, r9d; lpClass
0x18005556f  xor     r8d, r8d; Reserved
0x180055572  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180055579  call    cs:__imp_RegCreateKeyTransactedW
0x18005557f  mov     ebx, eax
0x180055581  test    eax, eax
0x180055583  jz      short loc_1800555EC
0x180055585  mov     rax, cs:WPP_GLOBAL_Control
0x18005558c  cmp     rax, r15
0x18005558f  jz      short loc_1800555D6
0x180055591  test    byte ptr [rax+1Ch], 8
0x180055595  jz      short loc_1800555D6
0x180055597  cmp     byte ptr [rax+19h], 2
0x18005559b  jb      short loc_1800555D6
0x18005559d  test    ebx, ebx
0x18005559f  jg      short loc_1800555A5
0x1800555a1  mov     edi, ebx
0x1800555a3  jmp     short loc_1800555AE
0x1800555a5  movzx   edi, bx
0x1800555a8  or      edi, 80070000h
0x1800555ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800555b3  mov     edx, 3Fh ; '?'
0x1800555b8  mov     [rsp+148h+dwOptions], edi
0x1800555bc  mov     r9d, eax
0x1800555bf  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x1800555c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800555cd  mov     rcx, [rcx+10h]
0x1800555d1  call    WPP_SF_Dd
0x1800555d6  test    ebx, ebx
0x1800555d8  jle     short loc_1800555E3
0x1800555da  movzx   ebx, bx
0x1800555dd  or      ebx, 80070000h
0x1800555e3  mov     [rsp+148h+var_E8], ebx
0x1800555e7  jmp     loc_180055699
0x1800555ec  lea     rcx, [rsi+0D8h]
0x1800555f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800555f8  mov     [rsp+148h+samDesired], 2; cbData
0x180055600  lea     rcx, LocaleName
0x180055607  mov     qword ptr [rsp+148h+dwOptions], rcx; lpData
0x18005560c  mov     r9d, 1; dwType
0x180055612  xor     r8d, r8d; Reserved
0x180055615  mov     rdx, rax; lpValueName
0x180055618  mov     rcx, [rsp+148h+hKey]; hKey
0x18005561d  call    cs:__imp_RegSetValueExW
0x180055623  mov     ebx, eax
0x180055625  test    eax, eax
0x180055627  jz      short loc_18005568D
0x180055629  mov     rax, cs:WPP_GLOBAL_Control
0x180055630  cmp     rax, r15
0x180055633  jz      short loc_18005567A
0x180055635  test    byte ptr [rax+1Ch], 8
0x180055639  jz      short loc_18005567A
0x18005563b  cmp     byte ptr [rax+19h], 2
0x18005563f  jb      short loc_18005567A
0x180055641  test    ebx, ebx
0x180055643  jg      short loc_180055649
0x180055645  mov     edi, ebx
0x180055647  jmp     short loc_180055652
0x180055649  movzx   edi, bx
0x18005564c  or      edi, 80070000h
0x180055652  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055657  mov     edx, 40h ; '@'
0x18005565c  mov     [rsp+148h+dwOptions], edi
0x180055660  mov     r9d, eax
0x180055663  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x18005566a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055671  mov     rcx, [rcx+10h]
0x180055675  call    WPP_SF_Dd
0x18005567a  test    ebx, ebx
0x18005567c  jle     short loc_180055687
0x18005567e  movzx   ebx, bx
0x180055681  or      ebx, 80070000h
0x180055687  mov     [rsp+148h+var_E8], ebx
0x18005568b  jmp     short loc_180055699
0x18005568d  mov     [rsp+148h+var_E8], 0
0x180055695  jmp     short loc_180055699
0x180055697  jmp     short $+2
0x180055699  mov     rcx, [rsp+148h+hKey]; hKey
0x18005569e  test    rcx, rcx
0x1800556a1  jz      short loc_1800556AA
0x1800556a3  call    cs:__imp_RegCloseKey
0x1800556a9  nop
0x1800556aa  lea     rcx, [rsp+148h+var_D0]; void *
0x1800556af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800556b4  mov     eax, [rsp+148h+var_E8]
0x1800556b8  mov     rcx, [rsp+148h+var_28]
0x1800556c0  xor     rcx, rsp; StackCookie
0x1800556c3  call    __security_check_cookie
0x1800556c8  lea     r11, [rsp+148h+var_18]
0x1800556d0  mov     rbx, [r11+30h]
0x1800556d4  mov     rsi, [r11+38h]
0x1800556d8  mov     rsp, r11
0x1800556db  pop     r15
0x1800556dd  pop     r14
0x1800556df  pop     rdi
0x1800556e0  retn
```
