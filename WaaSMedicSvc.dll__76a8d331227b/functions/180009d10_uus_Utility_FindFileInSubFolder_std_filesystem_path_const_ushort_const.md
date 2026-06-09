# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)

- ea: `0x180009d10`
- end: `0x180009e92`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `386`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180009b34`
- `0x180009c3c`

## callees

- `0x18000194c`
- `0x180002200`
- `0x180007940`
- `0x180008c00`
- `0x180008f20`
- `0x180009208`
- `0x180009d10`
- `0x18000b2a0`

## string_xrefs

- `0x180009d5c`: `uusbrain.dll`

## pseudocode

```c
std::filesystem::path *__fastcall uus::Utility::FindFileInSubFolder(
        std::filesystem::path *this,
        struct std::filesystem::path *a2)
{
  const WCHAR *v4; // rcx
  int stats; // eax
  const struct std::filesystem::path *v6; // r9
  int v7; // edx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  bool v15; // al
  char v17[16]; // [rsp+28h] [rbp-11h] BYREF
  __int128 v18; // [rsp+38h] [rbp-1h]
  LPCWSTR lpFileName[4]; // [rsp+48h] [rbp+Fh] BYREF
  __int128 v20; // [rsp+68h] [rbp+2Fh] BYREF
  __int64 v21; // [rsp+78h] [rbp+3Fh]
  __int64 v22; // [rsp+80h] [rbp+47h]

  v20 = 0;
  v21 = 0;
  v22 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v20, L"uusbrain.dll");
  std::filesystem::operator/(lpFileName, a2, (std::filesystem *)&v20);
  std::wstring::~wstring(&v20);
  *(_OWORD *)v17 = 0;
  v18 = 0;
  v4 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v4 = lpFileName[0];
  stats = _std_fs_get_stats(v4);
  v7 = stats;
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
              v14 = v13 - 38;
              if ( v14 )
              {
                if ( v14 != 106 )
                  v8 = 0;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    if ( (v18 & 0x400) == 0 )
      goto LABEL_9;
    if ( DWORD1(v18) == -1610612724 )
    {
      v8 = 4;
      goto LABEL_19;
    }
    if ( DWORD1(v18) == -1610612733 )
      v8 = 10;
    else
LABEL_9:
      v8 = (unsigned __int128)(v18 & 0x10 | 0x20) >> 4;
  }
LABEL_19:
  *(_DWORD *)v17 = v7;
  *(_QWORD *)&v17[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( (_DWORD)v8 )
  {
    v15 = (_DWORD)v8 != 1;
  }
  else
  {
    v15 = 0;
    if ( v7 )
      std::filesystem::_Throw_fs_error((std::filesystem *)v8, v17, (const struct std::error_code *)lpFileName, v6);
  }
  if ( v15 )
  {
    std::filesystem::path::path(this, (const struct std::filesystem::path *)lpFileName);
    *((_BYTE *)this + 32) = 1;
  }
  else
  {
    *((_BYTE *)this + 32) = 0;
  }
  std::wstring::~wstring(lpFileName);
  return this;
}

```

## disassembly

```asm
0x180009d10  mov     [rsp-8+arg_10], rbx
0x180009d15  mov     [rsp-8+arg_18], rdi
0x180009d1a  push    rbp
0x180009d1b  lea     rbp, [rsp-57h]
0x180009d20  sub     rsp, 90h
0x180009d27  mov     rax, cs:__security_cookie
0x180009d2e  xor     rax, rsp
0x180009d31  mov     [rbp+57h+var_8], rax
0x180009d35  mov     rbx, rdx
0x180009d38  mov     rdi, rcx
0x180009d3b  mov     qword ptr [rbp+57h+var_68], rcx
0x180009d3f  xorps   xmm0, xmm0
0x180009d42  movups  [rbp+57h+var_28], xmm0
0x180009d46  mov     [rbp+57h+var_18], 0
0x180009d4e  mov     [rbp+57h+var_10], 0
0x180009d56  mov     r8d, 0Ch
0x180009d5c  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x180009d63  lea     rcx, [rbp+57h+var_28]
0x180009d67  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180009d6c  nop
0x180009d6d  lea     r8, [rbp+57h+var_28]; this
0x180009d71  mov     rdx, rbx; struct std::filesystem::path *
0x180009d74  lea     rcx, [rbp+57h+lpFileName]; Src
0x180009d78  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009d7d  nop
0x180009d7e  lea     rcx, [rbp+57h+var_28]
0x180009d82  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009d87  xorps   xmm0, xmm0
0x180009d8a  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180009d8e  movups  [rbp+57h+var_58], xmm0
0x180009d92  lea     rcx, [rbp+57h+lpFileName]
0x180009d96  cmp     [rbp+57h+var_30], 7
0x180009d9b  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180009da0  or      r9d, 0FFFFFFFFh
0x180009da4  mov     r8d, 3
0x180009daa  lea     rdx, [rbp+57h+var_68]
0x180009dae  call    __std_fs_get_stats
0x180009db3  mov     edx, eax
0x180009db5  test    eax, eax
0x180009db7  jnz     short loc_180009DEB
0x180009db9  mov     ecx, dword ptr [rbp+57h+var_58]
0x180009dbc  bt      ecx, 0Ah
0x180009dc0  jnb     short loc_180009DE0
0x180009dc2  cmp     dword ptr [rbp+57h+var_58+4], 0A000000Ch
0x180009dc9  jnz     short loc_180009DD0
0x180009dcb  lea     ecx, [rax+4]
0x180009dce  jmp     short loc_180009E17
0x180009dd0  cmp     dword ptr [rbp+57h+var_58+4], 0A0000003h
0x180009dd7  jnz     short loc_180009DE0
0x180009dd9  mov     ecx, 0Ah
0x180009dde  jmp     short loc_180009E17
0x180009de0  and     ecx, 10h
0x180009de3  or      ecx, 20h
0x180009de6  shr     ecx, 4
0x180009de9  jmp     short loc_180009E17
0x180009deb  sub     eax, 2
0x180009dee  jz      short loc_180009E12
0x180009df0  sub     eax, 1
0x180009df3  jz      short loc_180009E12
0x180009df5  sub     eax, 32h ; '2'
0x180009df8  jz      short loc_180009E12
0x180009dfa  sub     eax, 0Bh
0x180009dfd  jz      short loc_180009E12
0x180009dff  sub     eax, 3Bh ; ';'
0x180009e02  jz      short loc_180009E12
0x180009e04  sub     eax, 26h ; '&'
0x180009e07  jz      short loc_180009E12
0x180009e09  cmp     eax, 6Ah ; 'j'
0x180009e0c  jz      short loc_180009E12
0x180009e0e  xor     ecx, ecx
0x180009e10  jmp     short loc_180009E17
0x180009e12  mov     ecx, 1; this
0x180009e17  mov     dword ptr [rbp+57h+var_68], edx
0x180009e1a  mov     eax, dword ptr [rbp+57h+var_68+4]
0x180009e1d  mov     dword ptr [rbp+57h+var_68+4], eax
0x180009e20  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180009e27  mov     qword ptr [rbp+57h+var_68+8], rax
0x180009e2b  test    ecx, ecx
0x180009e2d  jz      short loc_180009E4B
0x180009e2f  cmp     ecx, 1
0x180009e32  setnz   al
0x180009e35  test    al, al
0x180009e37  jz      short loc_180009E53
0x180009e39  lea     rdx, [rbp+57h+lpFileName]; struct std::filesystem::path *
0x180009e3d  mov     rcx, rdi; this
0x180009e40  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180009e45  mov     byte ptr [rdi+20h], 1
0x180009e49  jmp     short loc_180009E57
0x180009e4b  xor     al, al
0x180009e4d  test    edx, edx
0x180009e4f  jnz     short loc_180009E84
0x180009e51  jmp     short loc_180009E35
0x180009e53  mov     byte ptr [rdi+20h], 0
0x180009e57  lea     rcx, [rbp+57h+lpFileName]
0x180009e5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009e60  mov     rax, rdi
0x180009e63  mov     rcx, [rbp+57h+var_8]
0x180009e67  xor     rcx, rsp; StackCookie
0x180009e6a  call    __security_check_cookie
0x180009e6f  lea     r11, [rsp+90h+var_s0]
0x180009e77  mov     rbx, [r11+20h]
0x180009e7b  mov     rdi, [r11+28h]
0x180009e7f  mov     rsp, r11
0x180009e82  pop     rbp
0x180009e83  retn
0x180009e84  lea     r8, [rbp+57h+lpFileName]; struct std::error_code *
0x180009e88  lea     rdx, [rbp+57h+var_68]; char *
0x180009e8c  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
