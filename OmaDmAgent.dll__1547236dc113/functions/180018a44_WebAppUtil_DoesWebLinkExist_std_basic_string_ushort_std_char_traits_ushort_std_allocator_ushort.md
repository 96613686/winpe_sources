# WebAppUtil::DoesWebLinkExist(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180018a44`
- end: `0x180018cae`
- name: `?DoesWebLinkExist@WebAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000c354`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x180006998`
- `0x18000702c`
- `0x180009d64`
- `0x180009e20`
- `0x180009fb0`
- `0x18000a358`
- `0x180014c90`
- `0x180017ef4`
- `0x1800181dc`
- `0x180018a44`
- `0x180018cb4`
- `0x18001f420`

## import_xrefs

- `msvcp110_win!?good@ios_base@std@@QEBA_NXZ` at `0x180018b77`
- `msvcp110_win!?good@ios_base@std@@QEBA_NXZ` at `0x180018b77`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WebAppUtil::DoesWebLinkExist(_QWORD *a1)
{
  _QWORD *v2; // r9
  __int64 v3; // rdx
  int UserShortCutFolderPath; // ebx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // ebx
  _QWORD *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  _QWORD *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  _QWORD v19[35]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int64 v21; // [rsp+160h] [rbp+60h]
  unsigned __int16 v22[16]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v23[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v24[32]; // [rsp+1A8h] [rbp+A8h] BYREF

  v19[34] = a1;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    if ( a1[3] < 8u )
      v2 = a1;
    else
      v2 = (_QWORD *)*a1;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v2);
  }
  std::wstring::wstring(v23, &dword_180022F6C);
  UserShortCutFolderPath = WebAppUtil::GetUserShortCutFolderPath(v23);
  if ( UserShortCutFolderPath >= 0 )
  {
    v5 = std::char_traits<unsigned short>::length(L"|");
    v8 = std::wstring::find(a1, v6, v7, v5);
    std::wstring::substr(a1, v20, 0, v8);
    std::wstring::substr(a1, v24, v8 + 1, a1[2]);
    std::wstring::wstring(v22, v23);
    std::wstring::append(v22, v20, 0, -1);
    std::wstring::append(v22, L".url");
    std::ifstream::ifstream(v19, v22);
    if ( std::ios_base::good((std::ios_base *)((char *)v19 + *(int *)(v19[0] + 4LL))) )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v9 = v20;
        if ( v21 >= 8 )
          v9 = (_QWORD *)v20[0];
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v9);
      }
      std::ifstream::`vbase destructor'(v19);
      LOBYTE(v10) = 1;
      std::wstring::_Tidy(v22, v10, 0);
      LOBYTE(v11) = 1;
      std::wstring::_Tidy(v24, v11, 0);
      LOBYTE(v12) = 1;
      std::wstring::_Tidy(v20, v12, 0);
      UserShortCutFolderPath = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = v20;
        if ( v21 >= 8 )
          v13 = (_QWORD *)v20[0];
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids, v13);
      }
      std::ifstream::`vbase destructor'(v19);
      LOBYTE(v14) = 1;
      std::wstring::_Tidy(v22, v14, 0);
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(v24, v15, 0);
      LOBYTE(v16) = 1;
      std::wstring::_Tidy(v20, v16, 0);
      UserShortCutFolderPath = 1;
    }
  }
  LOBYTE(v3) = 1;
  std::wstring::_Tidy(v23, v3, 0);
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(a1, v17, 0);
  return (unsigned int)UserShortCutFolderPath;
}

```

## disassembly

```asm
0x180018a44  push    rbp
0x180018a46  push    rbx
0x180018a47  push    rdi
0x180018a48  push    r14
0x180018a4a  lea     rbp, [rsp-0D8h]
0x180018a52  sub     rsp, 1D8h
0x180018a59  mov     rax, cs:__security_cookie
0x180018a60  xor     rax, rsp
0x180018a63  mov     [rbp+0F0h+var_28], rax
0x180018a6a  mov     rdi, rcx
0x180018a6d  mov     [rbp+0F0h+var_B0], rcx
0x180018a71  lea     r14, WPP_GLOBAL_Control
0x180018a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a7f  cmp     rcx, r14
0x180018a82  jz      short loc_180018AAE
0x180018a84  test    byte ptr [rcx+1Ch], 1
0x180018a88  jz      short loc_180018AAE
0x180018a8a  cmp     qword ptr [rdi+18h], 8
0x180018a8f  jb      short loc_180018A96
0x180018a91  mov     r9, [rdi]
0x180018a94  jmp     short loc_180018A99
0x180018a96  mov     r9, rdi
0x180018a99  mov     edx, 13h
0x180018a9e  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018aa5  mov     rcx, [rcx+10h]
0x180018aa9  call    WPP_SF_S
0x180018aae  lea     rdx, dword_180022F6C
0x180018ab5  lea     rcx, [rbp+0F0h+var_68]
0x180018abc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018ac1  nop
0x180018ac2  lea     rcx, [rbp+0F0h+var_68]
0x180018ac9  call    ?GetUserShortCutFolderPath@WebAppUtil@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAppUtil::GetUserShortCutFolderPath(std::wstring &)
0x180018ace  mov     ebx, eax
0x180018ad0  test    eax, eax
0x180018ad2  js      loc_180018C70
0x180018ad8  lea     rcx, asc_180024014; "|"
0x180018adf  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180018ae4  mov     r9, rax
0x180018ae7  mov     rdx, rcx
0x180018aea  mov     rcx, rdi
0x180018aed  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180018af2  mov     rbx, rax
0x180018af5  movsxd  r9, eax
0x180018af8  xor     r8d, r8d
0x180018afb  lea     rdx, [rbp+0F0h+var_A8]
0x180018aff  mov     rcx, rdi
0x180018b02  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180018b07  nop
0x180018b08  lea     eax, [rbx+1]
0x180018b0b  movsxd  r8, eax
0x180018b0e  mov     r9, [rdi+10h]
0x180018b12  lea     rdx, [rbp+0F0h+var_48]
0x180018b19  mov     rcx, rdi
0x180018b1c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180018b21  nop
0x180018b22  lea     rdx, [rbp+0F0h+var_68]
0x180018b29  lea     rcx, [rbp+0F0h+var_88]
0x180018b2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018b32  nop
0x180018b33  or      r9, 0FFFFFFFFFFFFFFFFh
0x180018b37  xor     r8d, r8d
0x180018b3a  lea     rdx, [rbp+0F0h+var_A8]
0x180018b3e  lea     rcx, [rbp+0F0h+var_88]
0x180018b42  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180018b47  lea     rdx, aUrl_0; ".url"
0x180018b4e  lea     rcx, [rbp+0F0h+var_88]
0x180018b52  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180018b57  lea     rdx, [rbp+0F0h+var_88]
0x180018b5b  lea     rcx, [rsp+1F0h+var_1C0]
0x180018b60  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@HH@Z; std::ifstream::ifstream(std::wstring const &,int,int)
0x180018b65  nop
0x180018b66  mov     rax, [rsp+1F0h+var_1C0]
0x180018b6b  movsxd  rcx, dword ptr [rax+4]
0x180018b6f  lea     rax, [rsp+1F0h+var_1C0]
0x180018b74  add     rcx, rax
0x180018b77  call    cs:__imp_?good@ios_base@std@@QEBA_NXZ; std::ios_base::good(void)
0x180018b7e  nop     dword ptr [rax+rax+00h]
0x180018b83  test    al, al
0x180018b85  jz      short loc_180018BFB
0x180018b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b8e  cmp     rcx, r14
0x180018b91  jz      short loc_180018BBD
0x180018b93  test    byte ptr [rcx+1Ch], 1
0x180018b97  jz      short loc_180018BBD
0x180018b99  lea     r9, [rbp+0F0h+var_A8]
0x180018b9d  cmp     [rbp+0F0h+var_90], 8
0x180018ba2  cmovnb  r9, [rbp+0F0h+var_A8]
0x180018ba7  mov     edx, 14h
0x180018bac  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018bb3  mov     rcx, [rcx+10h]
0x180018bb7  call    WPP_SF_S
0x180018bbc  nop
0x180018bbd  lea     rcx, [rsp+1F0h+var_1C0]
0x180018bc2  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x180018bc7  nop
0x180018bc8  xor     r8d, r8d
0x180018bcb  mov     dl, 1
0x180018bcd  lea     rcx, [rbp+0F0h+var_88]
0x180018bd1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018bd6  nop
0x180018bd7  xor     r8d, r8d
0x180018bda  mov     dl, 1
0x180018bdc  lea     rcx, [rbp+0F0h+var_48]
0x180018be3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018be8  nop
0x180018be9  xor     r8d, r8d
0x180018bec  mov     dl, 1
0x180018bee  lea     rcx, [rbp+0F0h+var_A8]
0x180018bf2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018bf7  xor     ebx, ebx
0x180018bf9  jmp     short loc_180018C70
0x180018bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c02  cmp     rcx, r14
0x180018c05  jz      short loc_180018C31
0x180018c07  test    byte ptr [rcx+1Ch], 1
0x180018c0b  jz      short loc_180018C31
0x180018c0d  lea     r9, [rbp+0F0h+var_A8]
0x180018c11  cmp     [rbp+0F0h+var_90], 8
0x180018c16  cmovnb  r9, [rbp+0F0h+var_A8]
0x180018c1b  mov     edx, 15h
0x180018c20  lea     r8, WPP_af15a1953f8a3e062c8ff46a001ccea3_Traceguids
0x180018c27  mov     rcx, [rcx+10h]
0x180018c2b  call    WPP_SF_S
0x180018c30  nop
0x180018c31  lea     rcx, [rsp+1F0h+var_1C0]
0x180018c36  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x180018c3b  nop
0x180018c3c  xor     r8d, r8d
0x180018c3f  mov     dl, 1
0x180018c41  lea     rcx, [rbp+0F0h+var_88]
0x180018c45  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018c4a  nop
0x180018c4b  xor     r8d, r8d
0x180018c4e  mov     dl, 1
0x180018c50  lea     rcx, [rbp+0F0h+var_48]
0x180018c57  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018c5c  nop
0x180018c5d  xor     r8d, r8d
0x180018c60  mov     dl, 1
0x180018c62  lea     rcx, [rbp+0F0h+var_A8]
0x180018c66  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018c6b  mov     ebx, 1
0x180018c70  xor     r8d, r8d
0x180018c73  mov     dl, 1
0x180018c75  lea     rcx, [rbp+0F0h+var_68]
0x180018c7c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018c81  nop
0x180018c82  xor     r8d, r8d
0x180018c85  mov     dl, 1
0x180018c87  mov     rcx, rdi
0x180018c8a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018c8f  mov     eax, ebx
0x180018c91  mov     rcx, [rbp+0F0h+var_28]
0x180018c98  xor     rcx, rsp; StackCookie
0x180018c9b  call    __security_check_cookie
0x180018ca0  add     rsp, 1D8h
0x180018ca7  pop     r14
0x180018ca9  pop     rdi
0x180018caa  pop     rbx
0x180018cab  pop     rbp
0x180018cac  retn
```
