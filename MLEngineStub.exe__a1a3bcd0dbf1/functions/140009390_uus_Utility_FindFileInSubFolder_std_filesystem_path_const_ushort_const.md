# uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)

- ea: `0x140009390`
- end: `0x140009505`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `373`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *this, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400091b4`
- `0x1400092bc`

## callees

- `0x14000193c`
- `0x140002120`
- `0x140007188`
- `0x1400084c4`
- `0x1400087e4`
- `0x140008a04`
- `0x140009390`
- `0x14000a1d0`

## string_xrefs

- `0x1400093bf`: `uusbrain.dll`

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
  char v17[16]; // [rsp+30h] [rbp-19h] BYREF
  __int128 v18; // [rsp+40h] [rbp-9h]
  LPCWSTR lpFileName[4]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp+27h] BYREF

  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v20);
  std::filesystem::operator/(lpFileName, a2, (std::filesystem *)v20);
  std::wstring::~wstring(v20);
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
0x140009390  mov     [rsp-8+arg_10], rbx
0x140009395  mov     [rsp-8+arg_18], rdi
0x14000939a  push    rbp
0x14000939b  lea     rbp, [rsp-57h]
0x1400093a0  sub     rsp, 0A0h
0x1400093a7  mov     rax, cs:__security_cookie
0x1400093ae  xor     rax, rsp
0x1400093b1  mov     [rbp+57h+var_10], rax
0x1400093b5  mov     rbx, rdx
0x1400093b8  mov     rdi, rcx
0x1400093bb  mov     qword ptr [rbp+57h+var_70], rcx
0x1400093bf  lea     rax, aUusbrainDll; "uusbrain.dll"
0x1400093c6  mov     qword ptr [rbp+57h+var_70], rax
0x1400093ca  mov     qword ptr [rbp+57h+var_70+8], 0Ch
0x1400093d2  lea     rdx, [rbp+57h+var_70]
0x1400093d6  lea     rcx, [rbp+57h+var_30]; void *
0x1400093da  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1400093df  nop
0x1400093e0  lea     r8, [rbp+57h+var_30]; this
0x1400093e4  mov     rdx, rbx; struct std::filesystem::path *
0x1400093e7  lea     rcx, [rbp+57h+lpFileName]; Src
0x1400093eb  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1400093f0  nop
0x1400093f1  lea     rcx, [rbp+57h+var_30]
0x1400093f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400093fa  xorps   xmm0, xmm0
0x1400093fd  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140009401  movups  [rbp+57h+var_60], xmm0
0x140009405  lea     rcx, [rbp+57h+lpFileName]
0x140009409  cmp     [rbp+57h+var_38], 7
0x14000940e  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x140009413  or      r9d, 0FFFFFFFFh
0x140009417  mov     r8d, 3
0x14000941d  lea     rdx, [rbp+57h+var_70]
0x140009421  call    __std_fs_get_stats
0x140009426  mov     edx, eax
0x140009428  test    eax, eax
0x14000942a  jnz     short loc_14000945E
0x14000942c  mov     ecx, dword ptr [rbp+57h+var_60]
0x14000942f  bt      ecx, 0Ah
0x140009433  jnb     short loc_140009453
0x140009435  cmp     dword ptr [rbp+57h+var_60+4], 0A000000Ch
0x14000943c  jnz     short loc_140009443
0x14000943e  lea     ecx, [rax+4]
0x140009441  jmp     short loc_14000948A
0x140009443  cmp     dword ptr [rbp+57h+var_60+4], 0A0000003h
0x14000944a  jnz     short loc_140009453
0x14000944c  mov     ecx, 0Ah
0x140009451  jmp     short loc_14000948A
0x140009453  and     ecx, 10h
0x140009456  or      ecx, 20h
0x140009459  shr     ecx, 4
0x14000945c  jmp     short loc_14000948A
0x14000945e  sub     eax, 2
0x140009461  jz      short loc_140009485
0x140009463  sub     eax, 1
0x140009466  jz      short loc_140009485
0x140009468  sub     eax, 32h ; '2'
0x14000946b  jz      short loc_140009485
0x14000946d  sub     eax, 0Bh
0x140009470  jz      short loc_140009485
0x140009472  sub     eax, 3Bh ; ';'
0x140009475  jz      short loc_140009485
0x140009477  sub     eax, 26h ; '&'
0x14000947a  jz      short loc_140009485
0x14000947c  cmp     eax, 6Ah ; 'j'
0x14000947f  jz      short loc_140009485
0x140009481  xor     ecx, ecx
0x140009483  jmp     short loc_14000948A
0x140009485  mov     ecx, 1; this
0x14000948a  mov     dword ptr [rbp+57h+var_70], edx
0x14000948d  mov     eax, dword ptr [rbp+57h+var_70+4]
0x140009490  mov     dword ptr [rbp+57h+var_70+4], eax
0x140009493  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x14000949a  mov     qword ptr [rbp+57h+var_70+8], rax
0x14000949e  test    ecx, ecx
0x1400094a0  jz      short loc_1400094BE
0x1400094a2  cmp     ecx, 1
0x1400094a5  setnz   al
0x1400094a8  test    al, al
0x1400094aa  jz      short loc_1400094C6
0x1400094ac  lea     rdx, [rbp+57h+lpFileName]; struct std::filesystem::path *
0x1400094b0  mov     rcx, rdi; this
0x1400094b3  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x1400094b8  mov     byte ptr [rdi+20h], 1
0x1400094bc  jmp     short loc_1400094CA
0x1400094be  xor     al, al
0x1400094c0  test    edx, edx
0x1400094c2  jnz     short loc_1400094F7
0x1400094c4  jmp     short loc_1400094A8
0x1400094c6  mov     byte ptr [rdi+20h], 0
0x1400094ca  lea     rcx, [rbp+57h+lpFileName]
0x1400094ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400094d3  mov     rax, rdi
0x1400094d6  mov     rcx, [rbp+57h+var_10]
0x1400094da  xor     rcx, rsp; StackCookie
0x1400094dd  call    __security_check_cookie
0x1400094e2  lea     r11, [rsp+0A0h+var_s0]
0x1400094ea  mov     rbx, [r11+20h]
0x1400094ee  mov     rdi, [r11+28h]
0x1400094f2  mov     rsp, r11
0x1400094f5  pop     rbp
0x1400094f6  retn
0x1400094f7  lea     r8, [rbp+57h+lpFileName]; struct std::error_code *
0x1400094fb  lea     rdx, [rbp+57h+var_70]; char *
0x1400094ff  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
