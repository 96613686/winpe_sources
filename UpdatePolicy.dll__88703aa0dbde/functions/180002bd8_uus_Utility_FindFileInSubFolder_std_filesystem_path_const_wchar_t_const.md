# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)

- ea: `0x180002bd8`
- end: `0x180002d47`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z`
- size: `367`
- prototype: `__int64 __fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180002b10`
- `0x180002db0`

## callees

- `0x180001fe4`
- `0x180002198`
- `0x180002788`
- `0x180002bd8`
- `0x18000593c`
- `0x1800078ac`
- `0x18000de80`
- `0x18000ed40`

## string_xrefs

- `0x180002c24`: `uusbrain.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
std::filesystem::path *__fastcall uus::Utility::FindFileInSubFolder(
        std::filesystem::path *this,
        struct std::filesystem::path *a2)
{
  const WCHAR *v4; // rcx
  unsigned int stats; // eax
  const struct std::filesystem::path *v6; // r9
  std::filesystem *v7; // rcx
  int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  char v15[16]; // [rsp+20h] [rbp-19h] BYREF
  __int128 v16; // [rsp+30h] [rbp-9h]
  __int128 v17; // [rsp+48h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+58h] [rbp+1Fh]
  __int64 v19; // [rsp+60h] [rbp+27h]
  LPCWSTR lpFileName[4]; // [rsp+68h] [rbp+2Fh] BYREF

  v17 = 0;
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v17, L"uusbrain.dll", 12);
  std::filesystem::operator/(lpFileName, a2, &v17);
  std::wstring::~wstring(&v17);
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v4 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v4 = lpFileName[0];
  stats = _std_fs_get_stats(v4);
  v7 = (std::filesystem *)stats;
  if ( stats )
  {
    v9 = stats - 2;
    v8 = 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 50;
        if ( v11 )
        {
          v12 = v11 - 11;
          if ( v12 )
          {
            v13 = v12 - 59;
            if ( v13 )
            {
              if ( v13 != 144 )
                v8 = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    if ( (v16 & 0x400) == 0 )
      goto LABEL_9;
    if ( DWORD1(v16) == -1610612724 )
    {
      v8 = stats + 4;
      goto LABEL_18;
    }
    if ( DWORD1(v16) == -1610612733 )
      v8 = 10;
    else
LABEL_9:
      v8 = (unsigned __int128)(v16 & 0x10 | 0x20) >> 4;
  }
LABEL_18:
  *(_DWORD *)v15 = (_DWORD)v7;
  *(_QWORD *)&v15[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      std::filesystem::path::path(this, (const struct std::filesystem::path *)lpFileName);
      *((_BYTE *)this + 32) = 1;
      goto LABEL_21;
    }
  }
  else if ( (_DWORD)v7 )
  {
    std::filesystem::_Throw_fs_error(v7, v15, (const struct std::error_code *)lpFileName, v6);
  }
  *((_BYTE *)this + 32) = 0;
LABEL_21:
  std::wstring::~wstring(lpFileName);
  return this;
}

```

## disassembly

```asm
0x180002bd8  mov     [rsp-8+arg_10], rbx
0x180002bdd  mov     [rsp-8+arg_18], rdi
0x180002be2  push    rbp
0x180002be3  lea     rbp, [rsp-57h]
0x180002be8  sub     rsp, 90h
0x180002bef  mov     rax, cs:__security_cookie
0x180002bf6  xor     rax, rsp
0x180002bf9  mov     [rbp+57h+var_8], rax
0x180002bfd  mov     rbx, rdx
0x180002c00  mov     rdi, rcx
0x180002c03  mov     qword ptr [rbp+57h+var_70], rcx
0x180002c07  xorps   xmm0, xmm0
0x180002c0a  movups  [rbp+57h+var_48], xmm0
0x180002c0e  mov     [rbp+57h+var_38], 0
0x180002c16  mov     [rbp+57h+var_30], 0
0x180002c1e  mov     r8d, 0Ch
0x180002c24  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x180002c2b  lea     rcx, [rbp+57h+var_48]
0x180002c2f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002c34  nop
0x180002c35  lea     r8, [rbp+57h+var_48]; void *
0x180002c39  mov     rdx, rbx; struct std::filesystem::path *
0x180002c3c  lea     rcx, [rbp+57h+lpFileName]; Src
0x180002c40  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180002c45  nop
0x180002c46  lea     rcx, [rbp+57h+var_48]
0x180002c4a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002c4f  xorps   xmm0, xmm0
0x180002c52  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180002c56  movups  [rbp+57h+var_60], xmm0
0x180002c5a  lea     rcx, [rbp+57h+lpFileName]
0x180002c5e  cmp     [rbp+57h+var_10], 7
0x180002c63  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180002c68  lea     rdx, [rbp+57h+var_70]
0x180002c6c  call    __std_fs_get_stats
0x180002c71  mov     ecx, eax; this
0x180002c73  test    eax, eax
0x180002c75  jnz     short loc_180002CA9
0x180002c77  mov     eax, dword ptr [rbp+57h+var_60]
0x180002c7a  bt      eax, 0Ah
0x180002c7e  jnb     short loc_180002C9E
0x180002c80  cmp     dword ptr [rbp+57h+var_60+4], 0A000000Ch
0x180002c87  jnz     short loc_180002C8E
0x180002c89  lea     eax, [rcx+4]
0x180002c8c  jmp     short loc_180002CD2
0x180002c8e  cmp     dword ptr [rbp+57h+var_60+4], 0A0000003h
0x180002c95  jnz     short loc_180002C9E
0x180002c97  mov     eax, 0Ah
0x180002c9c  jmp     short loc_180002CD2
0x180002c9e  and     eax, 10h
0x180002ca1  or      eax, 20h
0x180002ca4  shr     eax, 4
0x180002ca7  jmp     short loc_180002CD2
0x180002ca9  sub     eax, 2
0x180002cac  jz      short loc_180002CCD
0x180002cae  sub     eax, 1
0x180002cb1  jz      short loc_180002CCD
0x180002cb3  sub     eax, 32h ; '2'
0x180002cb6  jz      short loc_180002CCD
0x180002cb8  sub     eax, 0Bh
0x180002cbb  jz      short loc_180002CCD
0x180002cbd  sub     eax, 3Bh ; ';'
0x180002cc0  jz      short loc_180002CCD
0x180002cc2  cmp     eax, 90h
0x180002cc7  jz      short loc_180002CCD
0x180002cc9  xor     eax, eax
0x180002ccb  jmp     short loc_180002CD2
0x180002ccd  mov     eax, 1
0x180002cd2  mov     dword ptr [rbp+57h+var_70], ecx
0x180002cd5  lea     rdx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180002cdc  mov     qword ptr [rbp+57h+var_70+8], rdx
0x180002ce0  movaps  xmm0, xmmword ptr [rbp+57h+var_70]
0x180002ce4  movdqa  xmmword ptr [rbp+57h+var_70], xmm0
0x180002ce9  test    eax, eax
0x180002ceb  jnz     short loc_180002D22
0x180002ced  test    ecx, ecx
0x180002cef  jnz     short loc_180002D39
0x180002cf1  mov     byte ptr [rdi+20h], 0
0x180002cf5  lea     rcx, [rbp+57h+lpFileName]
0x180002cf9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002cfe  mov     rax, rdi
0x180002d01  mov     rcx, [rbp+57h+var_8]
0x180002d05  xor     rcx, rsp; StackCookie
0x180002d08  call    __security_check_cookie
0x180002d0d  lea     r11, [rsp+90h+var_s0]
0x180002d15  mov     rbx, [r11+20h]
0x180002d19  mov     rdi, [r11+28h]
0x180002d1d  mov     rsp, r11
0x180002d20  pop     rbp
0x180002d21  retn
0x180002d22  cmp     eax, 1
0x180002d25  jz      short loc_180002CF1
0x180002d27  lea     rdx, [rbp+57h+lpFileName]; struct std::filesystem::path *
0x180002d2b  mov     rcx, rdi; this
0x180002d2e  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180002d33  mov     byte ptr [rdi+20h], 1
0x180002d37  jmp     short loc_180002CF5
0x180002d39  lea     r8, [rbp+57h+lpFileName]; struct std::error_code *
0x180002d3d  lea     rdx, [rbp+57h+var_70]; char *
0x180002d41  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
