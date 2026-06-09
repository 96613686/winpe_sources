# WebAppUtil::DeleteWebApp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800187f4`
- end: `0x180018a3e`
- name: `?DeleteWebApp@WebAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `586`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c354`
- `0x18000dcb4`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x180006998`
- `0x18000702c`
- `0x1800070a4`
- `0x1800070e4`
- `0x180009d64`
- `0x180009e20`
- `0x180009fb0`
- `0x18000a358`
- `0x180014c90`
- `0x1800187f4`
- `0x180018cb4`
- `0x18001a958`
- `0x18001f420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018949`
- `KERNEL32!GetLastError` at `0x180018949`
- `KERNEL32!DeleteFileW` at `0x180018939`
- `KERNEL32!DeleteFileW` at `0x180018939`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WebAppUtil::DeleteWebApp(_QWORD *a1)
{
  _QWORD *v2; // r9
  __int64 v3; // rdx
  int UserShortCutFolderPath; // edi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdi
  const WCHAR *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // r9
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rdx
  _BYTE v23[32]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v24[32]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v25[32]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    if ( a1[3] < 8u )
      v2 = a1;
    else
      v2 = (_QWORD *)*a1;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v2);
  }
  std::wstring::wstring(v26, &dword_180022F6C);
  UserShortCutFolderPath = WebAppUtil::GetUserShortCutFolderPath(v26);
  if ( UserShortCutFolderPath >= 0 )
  {
    v5 = std::char_traits<unsigned short>::length(L"|");
    v8 = std::wstring::find(a1, v6, v7, v5);
    std::wstring::wstring(v25, &dword_180022F6C);
    if ( v8 == -1 )
    {
      std::wstring::operator=(v25, a1);
    }
    else
    {
      v9 = std::wstring::substr(a1, v23, 0, v8);
      std::wstring::operator=(v25, v9);
      LOBYTE(v10) = 1;
      std::wstring::_Tidy(v23, v10, 0);
    }
    std::wstring::wstring(v24, v26);
    std::wstring::append(v24, v25, 0, -1);
    std::wstring::append(v24, L".url");
    v11 = std::wstring::wstring(v23, v24);
    v12 = v11;
    if ( *(_QWORD *)(v11 + 24) < 8u )
      v13 = (const WCHAR *)v11;
    else
      v13 = *(const WCHAR **)v11;
    if ( !DeleteFileW(v13) )
      GetLastError();
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v12, v14, 0);
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      if ( a1[3] < 8u )
        v15 = a1;
      else
        v15 = (_QWORD *)*a1;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v15);
    }
    v16 = (__int64 *)std::wstring::wstring(v23, a1);
    UserShortCutFolderPath = AppRegistry::DeleteApp(v17, v16);
    if ( UserShortCutFolderPath < 0
      && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      if ( a1[3] < 8u )
        v19 = a1;
      else
        v19 = (_QWORD *)*a1;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v19);
    }
    LOBYTE(v18) = 1;
    std::wstring::_Tidy(v24, v18, 0);
    LOBYTE(v20) = 1;
    std::wstring::_Tidy(v25, v20, 0);
  }
  LOBYTE(v3) = 1;
  std::wstring::_Tidy(v26, v3, 0);
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(a1, v21, 0);
  return (unsigned int)UserShortCutFolderPath;
}

```

## disassembly

```asm
0x1800187f4  push    rbp
0x1800187f6  push    rbx
0x1800187f7  push    rsi
0x1800187f8  push    rdi
0x1800187f9  lea     rbp, [rsp-3Fh]
0x1800187fe  sub     rsp, 0C8h
0x180018805  mov     rax, cs:__security_cookie
0x18001880c  xor     rax, rsp
0x18001880f  mov     [rbp+57h+var_30], rax
0x180018813  mov     rbx, rcx
0x180018816  mov     [rbp+57h+var_B8], rcx
0x18001881a  lea     rsi, WPP_GLOBAL_Control
0x180018821  mov     rcx, cs:WPP_GLOBAL_Control
0x180018828  cmp     rcx, rsi
0x18001882b  jz      short loc_180018857
0x18001882d  test    byte ptr [rcx+1Ch], 1
0x180018831  jz      short loc_180018857
0x180018833  cmp     qword ptr [rbx+18h], 8
0x180018838  jb      short loc_18001883F
0x18001883a  mov     r9, [rbx]
0x18001883d  jmp     short loc_180018842
0x18001883f  mov     r9, rbx
0x180018842  mov     edx, 16h
0x180018847  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x18001884e  mov     rcx, [rcx+10h]
0x180018852  call    WPP_SF_S
0x180018857  lea     rdx, dword_180022F6C
0x18001885e  lea     rcx, [rbp+57h+var_50]
0x180018862  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018867  nop
0x180018868  lea     rcx, [rbp+57h+var_50]
0x18001886c  call    ?GetUserShortCutFolderPath@WebAppUtil@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAppUtil::GetUserShortCutFolderPath(std::wstring &)
0x180018871  mov     edi, eax
0x180018873  test    eax, eax
0x180018875  js      loc_180018A07
0x18001887b  lea     rcx, asc_180024014; "|"
0x180018882  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180018887  mov     r9, rax
0x18001888a  mov     rdx, rcx
0x18001888d  mov     rcx, rbx
0x180018890  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180018895  mov     rdi, rax
0x180018898  lea     rdx, dword_180022F6C
0x18001889f  lea     rcx, [rbp+57h+var_70]
0x1800188a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800188a8  nop
0x1800188a9  cmp     edi, 0FFFFFFFFh
0x1800188ac  jz      short loc_1800188DC
0x1800188ae  movsxd  r9, edi
0x1800188b1  xor     r8d, r8d
0x1800188b4  lea     rdx, [rbp+57h+var_B0]
0x1800188b8  mov     rcx, rbx
0x1800188bb  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800188c0  mov     rdx, rax
0x1800188c3  lea     rcx, [rbp+57h+var_70]
0x1800188c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800188cc  xor     r8d, r8d
0x1800188cf  mov     dl, 1
0x1800188d1  lea     rcx, [rbp+57h+var_B0]
0x1800188d5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800188da  jmp     short loc_1800188E8
0x1800188dc  mov     rdx, rbx
0x1800188df  lea     rcx, [rbp+57h+var_70]
0x1800188e3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800188e8  lea     rdx, [rbp+57h+var_50]
0x1800188ec  lea     rcx, [rbp+57h+var_90]
0x1800188f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800188f5  nop
0x1800188f6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800188fa  xor     r8d, r8d
0x1800188fd  lea     rdx, [rbp+57h+var_70]
0x180018901  lea     rcx, [rbp+57h+var_90]
0x180018905  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001890a  lea     rdx, aUrl_0; ".url"
0x180018911  lea     rcx, [rbp+57h+var_90]
0x180018915  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001891a  lea     rdx, [rbp+57h+var_90]
0x18001891e  lea     rcx, [rbp+57h+var_B0]
0x180018922  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018927  mov     rdi, rax
0x18001892a  cmp     qword ptr [rax+18h], 8
0x18001892f  jb      short loc_180018936
0x180018931  mov     rcx, [rax]
0x180018934  jmp     short loc_180018939
0x180018936  mov     rcx, rdi; lpFileName
0x180018939  call    cs:__imp_DeleteFileW
0x180018940  nop     dword ptr [rax+rax+00h]
0x180018945  test    eax, eax
0x180018947  jnz     short loc_180018955
0x180018949  call    cs:__imp_GetLastError
0x180018950  nop     dword ptr [rax+rax+00h]
0x180018955  xor     r8d, r8d
0x180018958  mov     dl, 1
0x18001895a  mov     rcx, rdi
0x18001895d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018962  mov     rcx, cs:WPP_GLOBAL_Control
0x180018969  cmp     rcx, rsi
0x18001896c  jz      short loc_180018998
0x18001896e  test    byte ptr [rcx+1Ch], 1
0x180018972  jz      short loc_180018998
0x180018974  cmp     qword ptr [rbx+18h], 8
0x180018979  jb      short loc_180018980
0x18001897b  mov     r9, [rbx]
0x18001897e  jmp     short loc_180018983
0x180018980  mov     r9, rbx
0x180018983  mov     edx, 17h
0x180018988  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x18001898f  mov     rcx, [rcx+10h]
0x180018993  call    WPP_SF_S
0x180018998  mov     rdx, rbx
0x18001899b  lea     rcx, [rbp+57h+var_B0]
0x18001899f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800189a4  mov     rdx, rax
0x1800189a7  call    ?DeleteApp@AppRegistry@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppRegistry::DeleteApp(std::wstring)
0x1800189ac  mov     edi, eax
0x1800189ae  test    eax, eax
0x1800189b0  jns     short loc_1800189E9
0x1800189b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189b9  cmp     rcx, rsi
0x1800189bc  jz      short loc_1800189E9
0x1800189be  test    byte ptr [rcx+1Ch], 4
0x1800189c2  jz      short loc_1800189E9
0x1800189c4  cmp     qword ptr [rbx+18h], 8
0x1800189c9  jb      short loc_1800189D0
0x1800189cb  mov     r9, [rbx]
0x1800189ce  jmp     short loc_1800189D3
0x1800189d0  mov     r9, rbx
0x1800189d3  mov     edx, 18h
0x1800189d8  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x1800189df  mov     rcx, [rcx+10h]
0x1800189e3  call    WPP_SF_S
0x1800189e8  nop
0x1800189e9  xor     r8d, r8d
0x1800189ec  mov     dl, 1
0x1800189ee  lea     rcx, [rbp+57h+var_90]
0x1800189f2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800189f7  nop
0x1800189f8  xor     r8d, r8d
0x1800189fb  mov     dl, 1
0x1800189fd  lea     rcx, [rbp+57h+var_70]
0x180018a01  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018a06  nop
0x180018a07  xor     r8d, r8d
0x180018a0a  mov     dl, 1
0x180018a0c  lea     rcx, [rbp+57h+var_50]
0x180018a10  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018a15  nop
0x180018a16  xor     r8d, r8d
0x180018a19  mov     dl, 1
0x180018a1b  mov     rcx, rbx
0x180018a1e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018a23  mov     eax, edi
0x180018a25  mov     rcx, [rbp+57h+var_30]
0x180018a29  xor     rcx, rsp; StackCookie
0x180018a2c  call    __security_check_cookie
0x180018a31  add     rsp, 0C8h
0x180018a38  pop     rdi
0x180018a39  pop     rsi
0x180018a3a  pop     rbx
0x180018a3b  pop     rbp
0x180018a3c  retn
```
