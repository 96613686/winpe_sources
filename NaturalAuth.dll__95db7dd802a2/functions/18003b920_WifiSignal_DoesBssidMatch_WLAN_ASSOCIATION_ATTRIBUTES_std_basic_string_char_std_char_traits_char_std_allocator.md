# WifiSignal::DoesBssidMatch(_WLAN_ASSOCIATION_ATTRIBUTES,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x18003b920`
- end: `0x18003bacf`
- name: `?DoesBssidMatch@WifiSignal@@AEAA_NU_WLAN_ASSOCIATION_ATTRIBUTES@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18003c128`

## callees

- `0x180004170`
- `0x18000c9e0`
- `0x18000cab8`
- `0x18000d37c`
- `0x180011c68`
- `0x18001af38`
- `0x18003aad4`
- `0x18003b0d0`
- `0x18003b5fc`
- `0x18003b920`
- `0x18003d03c`
- `0x180046010`

## import_xrefs

- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18003b9a2`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18003b9a2`
- `msvcp_win!?fill@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAADD@Z` at `0x18003b980`
- `msvcp_win!?fill@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAADD@Z` at `0x18003b980`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003b96b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003b990`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003b96b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18003b990`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x18003b9cf`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x18003b9cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall WifiSignal::DoesBssidMatch(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // r10
  unsigned __int8 *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r9
  int v14; // edx
  int v15; // r8d
  bool v16; // bl
  _QWORD v18[3]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[232]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+130h] [rbp+30h]
  _BYTE v22[32]; // [rsp+138h] [rbp+38h] BYREF

  v21 = a3;
  std::ostringstream::ostringstream(&v19);
  v5 = std::ostream::operator<<(&v19, std::hex);
  LOBYTE(v6) = 48;
  std::ios::fill(v5 + *(int *)(*(_QWORD *)v5 + 4LL), v6);
  std::ostream::operator<<(v5, std::nouppercase);
  v7 = 0;
  do
  {
    v8 = std::setw(v18, 2);
    (*(void (__fastcall **)(_BYTE *, _QWORD))v8)(&v20[*(int *)(v19 + 4) - 8], *(_QWORD *)(v8 + 8));
    std::ostream::operator<<(&v19, *(unsigned __int8 *)(v7 + a2 + 40));
    if ( (_DWORD)v7 != 5 )
      std::operator<<<std::char_traits<char>>(&v19);
    v7 = (unsigned int)(v7 + 1);
  }
  while ( (int)v7 < 6 );
  std::string::string(v22);
  std::stringbuf::_Get_buffer_view(v20, v18);
  if ( v18[0] )
    std::string::assign(v22, v18[0], v18[1]);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v9 = std::_String_val<std::_Simple_types<char>>::_Myptr(v22);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 23, &WPP_144dc3462c353fa21006ff9a189489cc_Traceguids, v9);
  }
  std::_String_val<std::_Simple_types<char>>::_Myptr(a3);
  v11 = (unsigned __int8 *)std::_String_val<std::_Simple_types<char>>::_Myptr(v22);
  v13 = v12 - (_QWORD)v11;
  do
  {
    v14 = v11[v13];
    v15 = *v11 - v14;
    if ( v15 )
      break;
    ++v11;
  }
  while ( v14 );
  v16 = v15 == 0;
  std::string::_Tidy_deallocate(v22);
  std::ostringstream::`vbase destructor'(&v19);
  std::string::_Tidy_deallocate(a3);
  return v16;
}

```

## disassembly

```asm
0x18003b920  mov     [rsp-8+arg_0], rbx
0x18003b925  push    rbp
0x18003b926  push    rsi
0x18003b927  push    rdi
0x18003b928  lea     rbp, [rsp-60h]
0x18003b92d  sub     rsp, 160h
0x18003b934  mov     rax, cs:__security_cookie
0x18003b93b  xor     rax, rsp
0x18003b93e  mov     [rbp+70h+var_18], rax
0x18003b942  mov     rdi, r8
0x18003b945  mov     rsi, rdx
0x18003b948  mov     [rbp+70h+var_40], r8
0x18003b94c  mov     [rsp+170h+var_150], 0
0x18003b954  lea     rcx, [rsp+170h+var_130]
0x18003b959  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18003b95e  nop
0x18003b95f  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18003b966  lea     rcx, [rsp+170h+var_130]
0x18003b96b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18003b971  mov     rbx, rax
0x18003b974  mov     rcx, [rax]
0x18003b977  movsxd  rcx, dword ptr [rcx+4]
0x18003b97b  add     rcx, rax
0x18003b97e  mov     dl, 30h ; '0'
0x18003b980  call    cs:__imp_?fill@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAADD@Z; std::ios::fill(char)
0x18003b986  lea     rdx, ?nouppercase@std@@YAAEAVios_base@1@AEAV21@@Z; std::nouppercase(std::ios_base &)
0x18003b98d  mov     rcx, rbx
0x18003b990  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18003b996  xor     ebx, ebx
0x18003b998  mov     edx, 2
0x18003b99d  lea     rcx, [rsp+170h+var_148]
0x18003b9a2  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x18003b9a8  mov     rcx, [rsp+170h+var_130]
0x18003b9ad  movsxd  rdx, dword ptr [rcx+4]
0x18003b9b1  lea     rcx, [rsp+170h+var_130]
0x18003b9b6  add     rcx, rdx
0x18003b9b9  mov     rdx, [rax+8]
0x18003b9bd  mov     rax, [rax]
0x18003b9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9c5  movzx   edx, byte ptr [rbx+rsi+28h]
0x18003b9ca  lea     rcx, [rsp+170h+var_130]
0x18003b9cf  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x18003b9d5  cmp     ebx, 5
0x18003b9d8  jz      short loc_18003B9E4
0x18003b9da  lea     rcx, [rsp+170h+var_130]
0x18003b9df  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@D@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char)
0x18003b9e4  inc     ebx
0x18003b9e6  cmp     ebx, 6
0x18003b9e9  jl      short loc_18003B998
0x18003b9eb  lea     rcx, [rbp+70h+var_38]
0x18003b9ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18003b9f4  mov     [rsp+170h+var_150], 2
0x18003b9fc  lea     rdx, [rsp+170h+var_148]
0x18003ba01  lea     rcx, [rsp+170h+var_128]
0x18003ba06  call    ?_Get_buffer_view@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::stringbuf::_Get_buffer_view(void)
0x18003ba0b  mov     rdx, [rsp+170h+var_148]
0x18003ba10  test    rdx, rdx
0x18003ba13  jz      short loc_18003BA24
0x18003ba15  mov     r8, [rsp+170h+var_140]
0x18003ba1a  lea     rcx, [rbp+70h+var_38]
0x18003ba1e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18003ba23  nop
0x18003ba24  lea     rax, WPP_GLOBAL_Control
0x18003ba2b  mov     r10, cs:WPP_GLOBAL_Control
0x18003ba32  cmp     r10, rax
0x18003ba35  jz      short loc_18003BA5F
0x18003ba37  test    byte ptr [r10+1Ch], 4
0x18003ba3c  jz      short loc_18003BA5F
0x18003ba3e  lea     rcx, [rbp+70h+var_38]
0x18003ba42  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18003ba47  mov     r9, rax
0x18003ba4a  mov     edx, 17h
0x18003ba4f  lea     r8, WPP_144dc3462c353fa21006ff9a189489cc_Traceguids
0x18003ba56  mov     rcx, [r10+10h]
0x18003ba5a  call    WPP_SF_s
0x18003ba5f  mov     rcx, rdi
0x18003ba62  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18003ba67  mov     r9, rax
0x18003ba6a  lea     rcx, [rbp+70h+var_38]
0x18003ba6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18003ba73  sub     r9, rax
0x18003ba76  movzx   r8d, byte ptr [rax]
0x18003ba7a  movzx   edx, byte ptr [rax+r9]
0x18003ba7f  sub     r8d, edx
0x18003ba82  jnz     short loc_18003BA8B
0x18003ba84  inc     rax
0x18003ba87  test    edx, edx
0x18003ba89  jnz     short loc_18003BA76
0x18003ba8b  test    r8d, r8d
0x18003ba8e  setz    bl
0x18003ba91  lea     rcx, [rbp+70h+var_38]
0x18003ba95  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003ba9a  nop
0x18003ba9b  lea     rcx, [rsp+170h+var_130]
0x18003baa0  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x18003baa5  nop
0x18003baa6  mov     rcx, rdi
0x18003baa9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003baae  mov     al, bl
0x18003bab0  mov     rcx, [rbp+70h+var_18]
0x18003bab4  xor     rcx, rsp; StackCookie
0x18003bab7  call    __security_check_cookie
0x18003babc  mov     rbx, [rsp+170h+arg_0]
0x18003bac4  add     rsp, 160h
0x18003bacb  pop     rdi
0x18003bacc  pop     rsi
0x18003bacd  pop     rbp
0x18003bace  retn
```
