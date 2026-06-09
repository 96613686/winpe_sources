# WebAppUtil::CreateWebLink(_SwJob)

- ea: `0x1800182b4`
- end: `0x1800184db`
- name: `?CreateWebLink@WebAppUtil@@SAJU_SwJob@@@Z`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010eac`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x18000702c`
- `0x180009d64`
- `0x180009e20`
- `0x18000a290`
- `0x18000a358`
- `0x18000bd00`
- `0x1800182b4`
- `0x1800184e4`
- `0x180018cb4`
- `0x18001f420`

## import_xrefs

- `urlmon!IsValidURL` at `0x180018430`
- `urlmon!IsValidURL` at `0x180018430`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WebAppUtil::CreateWebLink(_SwJob *a1)
{
  __int64 v2; // rdx
  int UserShortCutFolderPath; // ebx
  _QWORD *v4; // r9
  _QWORD *v5; // r9
  __int64 v6; // rax
  _QWORD *v7; // rdx
  LPCWSTR *v8; // r9
  const WCHAR *v9; // rdx
  __int64 v10; // rdx
  LPCWSTR *v11; // rdx
  __int64 v12; // rbx
  _QWORD *v13; // rdx
  const WCHAR *v14; // rax
  __int64 v15; // rdx
  _BYTE v17[32]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-59h] BYREF
  _SwJob *v19; // [rsp+70h] [rbp-39h]
  LPCWSTR szURL[3]; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v21; // [rsp+90h] [rbp-19h]
  _QWORD v22[3]; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v23; // [rsp+B0h] [rbp+7h]
  _QWORD v24[4]; // [rsp+B8h] [rbp+Fh] BYREF

  v19 = a1;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids);
  std::wstring::wstring(v24, &dword_180022F6C);
  UserShortCutFolderPath = WebAppUtil::GetUserShortCutFolderPath(v24);
  if ( UserShortCutFolderPath >= 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v4 = v24;
      if ( v24[3] >= 8u )
        v4 = (_QWORD *)v24[0];
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v4);
    }
    std::wstring::wstring(v22, v24);
    std::wstring::append(v22, (char *)a1 + 32, 0, -1);
    std::wstring::append(v22, L".url");
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v5 = v22;
      if ( v23 >= 8 )
        v5 = (_QWORD *)v22[0];
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v5);
    }
    v6 = *((_QWORD *)a1 + 10);
    v7 = (_QWORD *)(*(_QWORD *)v6 + 16LL);
    if ( *(_QWORD *)(*(_QWORD *)v6 + 40LL) >= 8u )
      v7 = (_QWORD *)*v7;
    std::wstring::wstring(szURL, v7);
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = szURL;
      if ( v21 >= 8 )
        v8 = (LPCWSTR *)szURL[0];
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v8);
    }
    v9 = (const WCHAR *)szURL;
    if ( v21 >= 8 )
      v9 = szURL[0];
    UserShortCutFolderPath = IsValidURL(0, v9, 0);
    if ( UserShortCutFolderPath >= 0 )
    {
      v11 = szURL;
      if ( v21 >= 8 )
        v11 = (LPCWSTR *)szURL[0];
      v12 = std::wstring::wstring(v17, v11);
      v13 = v22;
      if ( v23 >= 8 )
        v13 = (_QWORD *)v22[0];
      v14 = (const WCHAR *)std::wstring::wstring(v18, v13);
      UserShortCutFolderPath = WebAppUtil::CreateWebLink(v14, v12);
    }
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(szURL, v10, 0);
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(v22, v15, 0);
  }
  LOBYTE(v2) = 1;
  std::wstring::_Tidy(v24, v2, 0);
  _SwJob::~_SwJob(a1);
  return (unsigned int)UserShortCutFolderPath;
}

```

## disassembly

```asm
0x1800182b4  push    rbp
0x1800182b6  push    rbx
0x1800182b7  push    rdi
0x1800182b8  push    r14
0x1800182ba  lea     rbp, [rsp-3Fh]
0x1800182bf  sub     rsp, 0E8h
0x1800182c6  mov     rax, cs:__security_cookie
0x1800182cd  xor     rax, rsp
0x1800182d0  mov     [rbp+57h+var_28], rax
0x1800182d4  mov     rdi, rcx
0x1800182d7  mov     [rbp+57h+var_90], rcx
0x1800182db  lea     r14, WPP_GLOBAL_Control
0x1800182e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182e9  cmp     rcx, r14
0x1800182ec  jz      short loc_180018309
0x1800182ee  test    byte ptr [rcx+1Ch], 1
0x1800182f2  jz      short loc_180018309
0x1800182f4  mov     edx, 0Bh
0x1800182f9  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018300  mov     rcx, [rcx+10h]
0x180018304  call    WPP_SF_
0x180018309  lea     rdx, dword_180022F6C
0x180018310  lea     rcx, [rbp+57h+var_48]
0x180018314  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018319  nop
0x18001831a  lea     rcx, [rbp+57h+var_48]
0x18001831e  call    ?GetUserShortCutFolderPath@WebAppUtil@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAppUtil::GetUserShortCutFolderPath(std::wstring &)
0x180018323  mov     ebx, eax
0x180018325  test    eax, eax
0x180018327  js      loc_1800184A8
0x18001832d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018334  cmp     rcx, r14
0x180018337  jz      short loc_180018362
0x180018339  test    byte ptr [rcx+1Ch], 1
0x18001833d  jz      short loc_180018362
0x18001833f  lea     r9, [rbp+57h+var_48]
0x180018343  cmp     [rbp+57h+var_30], 8
0x180018348  cmovnb  r9, [rbp+57h+var_48]
0x18001834d  mov     edx, 0Ch
0x180018352  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018359  mov     rcx, [rcx+10h]
0x18001835d  call    WPP_SF_S
0x180018362  lea     rdx, [rbp+57h+var_48]
0x180018366  lea     rcx, [rbp+57h+var_68]
0x18001836a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001836f  nop
0x180018370  lea     rdx, [rdi+20h]
0x180018374  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018378  xor     r8d, r8d
0x18001837b  lea     rcx, [rbp+57h+var_68]
0x18001837f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180018384  lea     rdx, aUrl_0; ".url"
0x18001838b  lea     rcx, [rbp+57h+var_68]
0x18001838f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180018394  mov     rcx, cs:WPP_GLOBAL_Control
0x18001839b  cmp     rcx, r14
0x18001839e  jz      short loc_1800183C9
0x1800183a0  test    byte ptr [rcx+1Ch], 1
0x1800183a4  jz      short loc_1800183C9
0x1800183a6  lea     r9, [rbp+57h+var_68]
0x1800183aa  cmp     [rbp+57h+var_50], 8
0x1800183af  cmovnb  r9, [rbp+57h+var_68]
0x1800183b4  mov     edx, 0Dh
0x1800183b9  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x1800183c0  mov     rcx, [rcx+10h]
0x1800183c4  call    WPP_SF_S
0x1800183c9  mov     rax, [rdi+50h]
0x1800183cd  mov     rdx, [rax]
0x1800183d0  add     rdx, 10h
0x1800183d4  cmp     qword ptr [rdx+18h], 8
0x1800183d9  jb      short loc_1800183DE
0x1800183db  mov     rdx, [rdx]
0x1800183de  lea     rcx, [rbp+57h+szURL]
0x1800183e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800183e7  nop
0x1800183e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183ef  cmp     rcx, r14
0x1800183f2  jz      short loc_18001841D
0x1800183f4  test    byte ptr [rcx+1Ch], 1
0x1800183f8  jz      short loc_18001841D
0x1800183fa  lea     r9, [rbp+57h+szURL]
0x1800183fe  cmp     [rbp+57h+var_70], 8
0x180018403  cmovnb  r9, [rbp+57h+szURL]
0x180018408  mov     edx, 0Eh
0x18001840d  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018414  mov     rcx, [rcx+10h]
0x180018418  call    WPP_SF_S
0x18001841d  lea     rdx, [rbp+57h+szURL]
0x180018421  cmp     [rbp+57h+var_70], 8
0x180018426  cmovnb  rdx, [rbp+57h+szURL]; szURL
0x18001842b  xor     r8d, r8d; dwReserved
0x18001842e  xor     ecx, ecx; pBC
0x180018430  call    cs:__imp_IsValidURL
0x180018437  nop     dword ptr [rax+rax+00h]
0x18001843c  mov     ebx, eax
0x18001843e  test    eax, eax
0x180018440  js      short loc_18001848A
0x180018442  lea     rax, [rbp+57h+var_D0]
0x180018446  mov     [rsp+100h+var_E0], rax
0x18001844b  lea     rdx, [rbp+57h+szURL]
0x18001844f  cmp     [rbp+57h+var_70], 8
0x180018454  cmovnb  rdx, [rbp+57h+szURL]
0x180018459  lea     rcx, [rbp+57h+var_D0]
0x18001845d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018462  mov     rbx, rax
0x180018465  lea     rdx, [rbp+57h+var_68]
0x180018469  cmp     [rbp+57h+var_50], 8
0x18001846e  cmovnb  rdx, [rbp+57h+var_68]
0x180018473  lea     rcx, [rbp+57h+var_B0]
0x180018477  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001847c  nop
0x18001847d  mov     rdx, rbx
0x180018480  mov     rcx, rax; lpFileName
0x180018483  call    ?CreateWebLink@WebAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WebAppUtil::CreateWebLink(std::wstring,std::wstring)
0x180018488  mov     ebx, eax
0x18001848a  xor     r8d, r8d
0x18001848d  mov     dl, 1
0x18001848f  lea     rcx, [rbp+57h+szURL]
0x180018493  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018498  nop
0x180018499  xor     r8d, r8d
0x18001849c  mov     dl, 1
0x18001849e  lea     rcx, [rbp+57h+var_68]
0x1800184a2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800184a7  nop
0x1800184a8  xor     r8d, r8d
0x1800184ab  mov     dl, 1
0x1800184ad  lea     rcx, [rbp+57h+var_48]
0x1800184b1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800184b6  nop
0x1800184b7  mov     rcx, rdi; this
0x1800184ba  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x1800184bf  mov     eax, ebx
0x1800184c1  mov     rcx, [rbp+57h+var_28]
0x1800184c5  xor     rcx, rsp; StackCookie
0x1800184c8  call    __security_check_cookie
0x1800184cd  add     rsp, 0E8h
0x1800184d4  pop     r14
0x1800184d6  pop     rdi
0x1800184d7  pop     rbx
0x1800184d8  pop     rbp
0x1800184d9  retn
```
