# Microsoft::Applications::Events::LogSessionDataProvider::DeleteLogSessionDataFromFile(void)

- ea: `0x140134fe4`
- end: `0x140135179`
- name: `?DeleteLogSessionDataFromFile@LogSessionDataProvider@Events@Applications@Microsoft@@IEAAXXZ`
- size: `405`
- prototype: `void __fastcall(Microsoft::Applications::Events::LogSessionDataProvider *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140112d70`
- `0x140114420`

## callees

- `0x14003a5c0`
- `0x14007e088`
- `0x14007fb9c`
- `0x140084a18`
- `0x140084a8c`
- `0x140084b00`
- `0x140134fe4`
- `0x14015fef4`
- `0x140160090`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140135139`
- `KERNEL32!DeleteFileW` at `0x140135139`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Applications::Events::LogSessionDataProvider::DeleteLogSessionDataFromFile(
        Microsoft::Applications::Events::LogSessionDataProvider *this)
{
  char v1; // di
  size_t Size; // rdx
  CHAR *v3; // rdx
  size_t v4; // rbx
  size_t v5; // r8
  const char *v6; // rdx
  Microsoft::Applications::Events *v7; // rcx
  Microsoft::Applications::Events **v8; // rdx
  const WCHAR *v9; // rcx
  CHAR MultiByteStr[16]; // [rsp+48h] [rbp-11h] BYREF
  __int128 v11; // [rsp+58h] [rbp-1h]
  Microsoft::Applications::Events *v12[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v13; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v14; // [rsp+80h] [rbp+27h]
  LPCWSTR lpFileName[4]; // [rsp+88h] [rbp+2Fh] BYREF

  v1 = 0;
  Size = *((_QWORD *)this + 3);
  if ( Size )
  {
    if ( 0x7FFFFFFFFFFFFFFFLL - Size < 4 )
      std::_Xlen_string();
    _mm_lfence();
    std::string::string(MultiByteStr, Size, ".ses", 4u);
    v1 = 3;
    v3 = MultiByteStr;
    if ( *((_QWORD *)&v11 + 1) > 0xFu )
      v3 = *(CHAR **)MultiByteStr;
  }
  else
  {
    v3 = (CHAR *)qword_140194AF8;
  }
  *(_OWORD *)v12 = 0;
  v13 = 0;
  v14 = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( v3[v5] );
  std::string::_Construct<1,char const *>(v12, v3, v5);
  if ( (v1 & 1) != 0 )
    std::string::_Tidy_deallocate(MultiByteStr);
  if ( v13 )
  {
    v7 = (Microsoft::Applications::Events *)v12;
    if ( v14 > 0xF )
      v7 = v12[0];
    if ( Microsoft::Applications::Events::FileExists(v7, v6) )
    {
      v8 = v12;
      if ( v14 > 0xF )
        v8 = (Microsoft::Applications::Events **)v12[0];
      *(_OWORD *)MultiByteStr = 0;
      v11 = 0;
      do
        ++v4;
      while ( *((_BYTE *)v8 + v4) );
      std::string::_Construct<1,char const *>(MultiByteStr, v8, v4);
      Microsoft::Applications::Events::to_utf16_string((LPWSTR)lpFileName, MultiByteStr);
      std::string::_Tidy_deallocate(MultiByteStr);
      v9 = (const WCHAR *)lpFileName;
      if ( lpFileName[3] > (LPCWSTR)7 )
        v9 = lpFileName[0];
      DeleteFileW(v9);
      std::wstring::_Tidy_deallocate(lpFileName);
    }
  }
  std::string::_Tidy_deallocate(v12);
}

```

## disassembly

```asm
0x140134fe4  mov     [rsp-8+arg_8], rbx
0x140134fe9  mov     [rsp-8+arg_10], rdi
0x140134fee  push    rbp
0x140134fef  lea     rbp, [rsp-57h]
0x140134ff4  sub     rsp, 0B0h
0x140134ffb  mov     rax, cs:__security_cookie
0x140135002  xor     rax, rsp
0x140135005  mov     [rbp+57h+var_8], rax
0x140135009  xor     edi, edi
0x14013500b  mov     [rbp+57h+var_70], edi
0x14013500e  mov     rdx, [rcx+18h]
0x140135012  test    rdx, rdx
0x140135015  jnz     short loc_140135020
0x140135017  lea     rdx, qword_140194AF8
0x14013501e  jmp     short loc_140135082
0x140135020  lea     r9, [rcx+8]
0x140135024  mov     rax, 7FFFFFFFFFFFFFFFh
0x14013502e  sub     rax, rdx
0x140135031  cmp     rax, 4
0x140135035  jb      loc_140135173
0x14013503b  lfence
0x14013503e  cmp     qword ptr [r9+18h], 0Fh
0x140135043  jbe     short loc_140135048
0x140135045  mov     r9, [r9]
0x140135048  mov     [rsp+0B0h+var_80], 4; size_t
0x140135051  lea     rax, aSes; ".ses"
0x140135058  mov     [rsp+0B0h+Src], rax; Src
0x14013505d  mov     [rsp+0B0h+Size], rdx; Size
0x140135062  lea     rcx, [rbp+57h+MultiByteStr]; void *
0x140135066  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x14013506b  nop
0x14013506c  mov     edi, 3
0x140135071  mov     [rbp+57h+var_70], edi
0x140135074  lea     rdx, [rbp+57h+MultiByteStr]
0x140135078  cmp     [rbp+57h+var_50], 0Fh
0x14013507d  cmova   rdx, qword ptr [rbp+57h+MultiByteStr]
0x140135082  xorps   xmm0, xmm0
0x140135085  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140135089  mov     [rbp+57h+var_38], 0
0x140135091  mov     [rbp+57h+var_30], 0
0x140135099  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14013509d  mov     r8, rbx
0x1401350a0  inc     r8
0x1401350a3  cmp     byte ptr [rdx+r8], 0
0x1401350a8  jnz     short loc_1401350A0
0x1401350aa  lea     rcx, [rbp+57h+var_48]
0x1401350ae  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1401350b3  nop
0x1401350b4  test    dil, 1
0x1401350b8  jz      short loc_1401350C3
0x1401350ba  lea     rcx, [rbp+57h+MultiByteStr]
0x1401350be  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1401350c3  cmp     [rbp+57h+var_38], 0
0x1401350c8  jz      short loc_140135149
0x1401350ca  lea     rcx, [rbp+57h+var_48]
0x1401350ce  cmp     [rbp+57h+var_30], 0Fh
0x1401350d3  cmova   rcx, [rbp+57h+var_48]; this
0x1401350d8  call    ?FileExists@Events@Applications@Microsoft@@YA_NPEBD@Z; Microsoft::Applications::Events::FileExists(char const *)
0x1401350dd  test    al, al
0x1401350df  jz      short loc_140135149
0x1401350e1  lea     rdx, [rbp+57h+var_48]
0x1401350e5  cmp     [rbp+57h+var_30], 0Fh
0x1401350ea  cmova   rdx, [rbp+57h+var_48]
0x1401350ef  xorps   xmm0, xmm0
0x1401350f2  movups  xmmword ptr [rbp+57h+MultiByteStr], xmm0
0x1401350f6  xorps   xmm1, xmm1
0x1401350f9  movdqu  xmmword ptr [rbp-1], xmm1
0x1401350fe  inc     rbx
0x140135101  cmp     byte ptr [rdx+rbx], 0
0x140135105  jnz     short loc_1401350FE
0x140135107  mov     r8, rbx
0x14013510a  lea     rcx, [rbp+57h+MultiByteStr]
0x14013510e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140135113  nop
0x140135114  lea     rdx, [rbp+57h+MultiByteStr]; lpMultiByteStr
0x140135118  lea     rcx, [rbp+57h+lpFileName]; lpWideCharStr
0x14013511c  call    ?to_utf16_string@Events@Applications@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Applications::Events::to_utf16_string(std::string const &)
0x140135121  nop
0x140135122  lea     rcx, [rbp+57h+MultiByteStr]
0x140135126  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14013512b  lea     rcx, [rbp+57h+lpFileName]
0x14013512f  cmp     [rbp+57h+var_10], 7
0x140135134  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x140135139  call    cs:__imp_DeleteFileW
0x14013513f  lea     rcx, [rbp+57h+lpFileName]
0x140135143  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140135148  nop
0x140135149  lea     rcx, [rbp+57h+var_48]
0x14013514d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140135152  mov     rcx, [rbp+57h+var_8]
0x140135156  xor     rcx, rsp; StackCookie
0x140135159  call    __security_check_cookie
0x14013515e  lea     r11, [rsp+0B0h+var_s0]
0x140135166  mov     rbx, [r11+18h]
0x14013516a  mov     rdi, [r11+20h]
0x14013516e  mov     rsp, r11
0x140135171  pop     rbp
0x140135172  retn
0x140135173  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
