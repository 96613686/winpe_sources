# DxDbFileCompression::DecompressDatabaseFile(ushort const *,ushort const *,ushort const *)

- ea: `0x140014be4`
- end: `0x140014dab`
- name: `?DecompressDatabaseFile@DxDbFileCompression@@YAJPEBG00@Z`
- size: `455`
- prototype: `__int64 __fastcall(DxDbFileCompression *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007ad8`

## callees

- `0x14000a49c`
- `0x14000a4bc`
- `0x140011a4c`
- `0x1400143a4`
- `0x140014478`
- `0x14001454c`
- `0x140014784`
- `0x1400147b0`
- `0x140014be4`
- `0x140014db4`
- `0x140015530`

## import_xrefs

- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140014cad`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140014ce0`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140014d6d`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140014cad`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140014ce0`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x140014d6d`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x140014d42`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x140014d42`

## string_xrefs

- `0x140014c2b`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`
- `0x140014c74`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`
- `0x140014d05`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFile(
        DxDbFileCompression *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const char *v6; // r9
  unsigned int LastError; // ebx
  int v8; // eax
  const char *v9; // r9
  int v11; // [rsp+20h] [rbp-E0h]
  _QWORD v12[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[128]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+F0h] [rbp-10h]
  __int64 v16; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v17[128]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v18; // [rsp+1F8h] [rbp+F8h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  std::vector<unsigned char>::vector<unsigned char>(v12, this, a3, a4);
  std::ifstream::ifstream(v13);
  if ( v15 )
  {
    v8 = DxDbFileCompression::DecompressDatabaseFileImpl(v13, a3, v12);
    LastError = v8;
    if ( v8 >= 0 )
    {
      if ( !std::filebuf::close(v14) )
        std::ios::setstate((char *)v13 + *(int *)(v13[0] + 4LL), 2);
      std::ofstream::ofstream(&v16, a2);
      if ( v18 )
      {
        std::ostream::write(&v16, v12[0], v12[1] - v12[0]);
        if ( !std::filebuf::close(v17) )
          std::ios::setstate(&v17[*(int *)(v16 + 4) - 8], 2);
        std::ofstream::`vbase destructor'(&v16);
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xCF,
                      (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
                      v9);
        std::ofstream::`vbase destructor'(&v16);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
        (const char *)(unsigned int)v8,
        v11);
      if ( !std::filebuf::close(v14) )
        std::ios::setstate((char *)v13 + *(int *)(v13[0] + 4LL), 2);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC3,
                  (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
                  v6);
  }
  std::ifstream::`vbase destructor'(v13);
  std::vector<unsigned char>::_Tidy(v12);
  return LastError;
}

```

## disassembly

```asm
0x140014be4  mov     [rsp-8+arg_0], rbx
0x140014be9  mov     [rsp-8+arg_8], rdi
0x140014bee  push    rbp
0x140014bef  lea     rbp, [rsp-180h]
0x140014bf7  sub     rsp, 280h
0x140014bfe  mov     rbx, r8
0x140014c01  mov     rdi, rdx
0x140014c04  mov     rdx, rcx
0x140014c07  lea     rcx, [rsp+280h+var_240]
0x140014c0c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x140014c11  nop
0x140014c12  lea     rcx, [rsp+280h+var_220]
0x140014c17  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x140014c1c  nop
0x140014c1d  cmp     [rbp+180h+var_190], 0
0x140014c22  jnz     short loc_140014C43
0x140014c24  mov     rcx, [rbp+188h]; this
0x140014c2b  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x140014c32  mov     edx, 0C3h; void *
0x140014c37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140014c3c  mov     ebx, eax
0x140014c3e  jmp     loc_140014D7F
0x140014c43  lea     rax, [rsp+280h+var_220]
0x140014c48  mov     [rsp+280h+var_250], rax
0x140014c4d  mov     [rsp+280h+var_248], 1
0x140014c52  lea     r8, [rsp+280h+var_240]
0x140014c57  mov     rdx, rbx
0x140014c5a  lea     rcx, [rsp+280h+var_220]
0x140014c5f  call    ?DecompressDatabaseFileImpl@DxDbFileCompression@@YAJAEAV?$basic_istream@DU?$char_traits@D@std@@@std@@PEBGPEAV?$vector@EV?$allocator@E@std@@@3@@Z; DxDbFileCompression::DecompressDatabaseFileImpl(std::istream &,ushort const *,std::vector<uchar> *)
0x140014c64  mov     ebx, eax
0x140014c66  test    eax, eax
0x140014c68  jns     short loc_140014CB9
0x140014c6a  mov     rcx, [rbp+188h]; this
0x140014c71  mov     r9d, eax; char *
0x140014c74  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x140014c7b  mov     edx, 0CAh; void *
0x140014c80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014c85  nop
0x140014c86  lea     rcx, [rsp+280h+var_210]
0x140014c8b  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x140014c90  test    rax, rax
0x140014c93  jnz     short loc_140014CB4
0x140014c95  mov     rax, [rsp+280h+var_220]
0x140014c9a  movsxd  rcx, dword ptr [rax+4]
0x140014c9e  lea     rax, [rsp+280h+var_220]
0x140014ca3  add     rcx, rax
0x140014ca6  xor     r8d, r8d
0x140014ca9  lea     edx, [r8+2]
0x140014cad  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x140014cb3  nop
0x140014cb4  jmp     loc_140014D7F
0x140014cb9  lea     rcx, [rsp+280h+var_210]
0x140014cbe  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x140014cc3  test    rax, rax
0x140014cc6  jnz     short loc_140014CE7
0x140014cc8  mov     rax, [rsp+280h+var_220]
0x140014ccd  movsxd  rcx, dword ptr [rax+4]
0x140014cd1  lea     rax, [rsp+280h+var_220]
0x140014cd6  add     rcx, rax
0x140014cd9  xor     r8d, r8d
0x140014cdc  lea     edx, [r8+2]
0x140014ce0  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x140014ce6  nop
0x140014ce7  mov     rdx, rdi
0x140014cea  lea     rcx, [rbp+180h+var_110]
0x140014cee  call    ??0?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ofstream::ofstream(ushort const *,int,int)
0x140014cf3  nop
0x140014cf4  cmp     [rbp+180h+var_88], 0
0x140014cfc  jnz     short loc_140014D23
0x140014cfe  mov     rcx, [rbp+188h]; this
0x140014d05  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x140014d0c  mov     edx, 0CFh; void *
0x140014d11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140014d16  mov     ebx, eax
0x140014d18  lea     rcx, [rbp+180h+var_110]
0x140014d1c  call    ??_D?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ofstream::`vbase destructor'(void)
0x140014d21  jmp     short loc_140014D7F
0x140014d23  lea     rax, [rbp+180h+var_110]
0x140014d27  mov     [rsp+280h+var_250], rax
0x140014d2c  mov     [rsp+280h+var_248], 1
0x140014d31  mov     r8, [rsp+280h+var_238]
0x140014d36  mov     rdx, [rsp+280h+var_240]
0x140014d3b  sub     r8, rdx
0x140014d3e  lea     rcx, [rbp+180h+var_110]
0x140014d42  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x140014d48  nop
0x140014d49  lea     rcx, [rbp+180h+var_108]
0x140014d4d  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x140014d52  test    rax, rax
0x140014d55  jnz     short loc_140014D74
0x140014d57  mov     rax, [rbp+180h+var_110]
0x140014d5b  movsxd  rcx, dword ptr [rax+4]
0x140014d5f  lea     rax, [rbp+180h+var_110]
0x140014d63  add     rcx, rax
0x140014d66  xor     r8d, r8d
0x140014d69  lea     edx, [r8+2]
0x140014d6d  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x140014d73  nop
0x140014d74  lea     rcx, [rbp+180h+var_110]
0x140014d78  call    ??_D?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ofstream::`vbase destructor'(void)
0x140014d7d  xor     ebx, ebx
0x140014d7f  lea     rcx, [rsp+280h+var_220]
0x140014d84  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x140014d89  nop
0x140014d8a  lea     rcx, [rsp+280h+var_240]
0x140014d8f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140014d94  mov     eax, ebx
0x140014d96  lea     r11, [rsp+280h+var_s0]
0x140014d9e  mov     rbx, [r11+10h]
0x140014da2  mov     rdi, [r11+18h]
0x140014da6  mov     rsp, r11
0x140014da9  pop     rbp
0x140014daa  retn
```
