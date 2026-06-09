# Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800259c4`
- end: `0x180025b87`
- name: `?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180025b90`

## callees

- `0x1800045b0`
- `0x180009750`
- `0x1800105f4`
- `0x1800174f0`
- `0x1800175f4`
- `0x180019230`
- `0x18001cd64`
- `0x1800259c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a6f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025a62`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025ae2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025a62`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025ae2`

## string_xrefs

- `0x180025b4a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(__int64 a1, char a2, __int64 a3)
{
  signed int v5; // ebx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rdx
  char v8; // al
  const CHAR *v9; // rdi
  int v10; // eax
  unsigned __int64 cchWideChar; // rsi
  signed int LastError; // eax
  WCHAR *v13; // rax
  LPWSTR *v14; // rax
  LPWSTR *v15; // rcx
  char *v16; // rdi
  WCHAR *v17; // rdx
  __int64 trivial_2; // rax
  int lpWideCharStr; // [rsp+20h] [rbp-40h]
  _BYTE v21[8]; // [rsp+30h] [rbp-30h] BYREF
  LPWSTR Src[2]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-18h]
  unsigned __int64 v24; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v5 = 0;
  *(_OWORD *)Src = 0;
  v6 = 0;
  v23 = 0;
  v7 = 7;
  v24 = 7;
  LOWORD(Src[0]) = 0;
  if ( a2 )
  {
    v8 = 1;
    v9 = (const CHAR *)(a1 + *(unsigned __int8 *)(a1 + 1));
LABEL_6:
    if ( *v9 )
    {
      while ( v8 != a2 )
      {
        if ( !*++v9 )
        {
          ++v9;
          ++v8;
          goto LABEL_6;
        }
      }
    }
    v5 = *v9 == 0 ? 0x8000FFFF : 0;
    v10 = MultiByteToWideChar(0, 8u, v9, -1, 0, 0);
    cchWideChar = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v5 >= 0 && (int)cchWideChar > 65 )
      v5 = -2147418113;
    if ( cchWideChar > v23 )
    {
      std::wstring::append(Src);
    }
    else
    {
      v23 = cchWideChar;
      *((_WORD *)Src + cchWideChar) = 0;
    }
    v13 = (WCHAR *)Src;
    if ( v24 > 7 )
      v13 = Src[0];
    MultiByteToWideChar(0, 8u, v9, -1, v13, cchWideChar);
    v7 = v24;
    v6 = v23;
  }
  v14 = Src;
  v15 = (LPWSTR *)Src[0];
  if ( v7 > 7 )
    v14 = (LPWSTR *)Src[0];
  v16 = (char *)v14 + 2 * v6;
  if ( v7 <= 7 )
  {
    v17 = (WCHAR *)Src + v6;
    v15 = Src;
  }
  else
  {
    v17 = &Src[0][v6];
  }
  trivial_2 = _std_find_trivial_2(v15, v17, 0);
  std::wstring::erase(Src, v21, trivial_2, v16);
  std::wstring::operator=(a3, Src);
  if ( v5 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)(unsigned int)v5,
      lpWideCharStr);
  std::wstring::_Tidy_deallocate(Src);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800259c4  mov     [rsp-28h+arg_8], rbx
0x1800259c9  push    rbp
0x1800259ca  push    rsi
0x1800259cb  push    rdi
0x1800259cc  push    r13
0x1800259ce  push    r14
0x1800259d0  mov     rbp, rsp
0x1800259d3  sub     rsp, 60h
0x1800259d7  mov     rax, cs:__security_cookie
0x1800259de  xor     rax, rsp
0x1800259e1  mov     [rbp+var_8], rax
0x1800259e5  mov     r14, r8
0x1800259e8  mov     r9b, dl
0x1800259eb  xor     ebx, ebx
0x1800259ed  xorps   xmm0, xmm0
0x1800259f0  movups  xmmword ptr [rbp+Src], xmm0
0x1800259f4  xor     r8d, r8d
0x1800259f7  mov     [rbp+var_18], r8
0x1800259fb  lea     edx, [rbx+7]
0x1800259fe  mov     [rbp+var_10], rdx
0x180025a02  xor     eax, eax
0x180025a04  mov     word ptr [rbp+Src], ax
0x180025a08  test    r9b, r9b
0x180025a0b  jz      loc_180025AF0
0x180025a11  mov     al, 1
0x180025a13  movzx   edi, byte ptr [rcx+1]
0x180025a17  add     rdi, rcx
0x180025a1a  jmp     short loc_180025A2E
0x180025a1c  cmp     al, r9b
0x180025a1f  jz      short loc_180025A33
0x180025a21  inc     rdi
0x180025a24  cmp     byte ptr [rdi], 0
0x180025a27  jnz     short loc_180025A1C
0x180025a29  inc     rdi
0x180025a2c  inc     al
0x180025a2e  cmp     byte ptr [rdi], 0
0x180025a31  jnz     short loc_180025A1C
0x180025a33  mov     al, [rdi]
0x180025a35  neg     al
0x180025a37  sbb     ebx, ebx
0x180025a39  not     ebx
0x180025a3b  mov     r13d, 8000FFFFh
0x180025a41  and     ebx, r13d
0x180025a44  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x180025a4c  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x180025a55  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180025a59  mov     r8, rdi; lpMultiByteStr
0x180025a5c  lea     edx, [r9+9]; dwFlags
0x180025a60  xor     ecx, ecx; CodePage
0x180025a62  call    cs:__imp_MultiByteToWideChar
0x180025a68  movsxd  rsi, eax
0x180025a6b  test    eax, eax
0x180025a6d  jnz     short loc_180025A84
0x180025a6f  call    cs:__imp_GetLastError
0x180025a75  mov     ebx, eax
0x180025a77  test    eax, eax
0x180025a79  jle     short loc_180025A84
0x180025a7b  movzx   ebx, ax
0x180025a7e  or      ebx, 80070000h
0x180025a84  test    ebx, ebx
0x180025a86  js      short loc_180025A8F
0x180025a88  cmp     esi, 41h ; 'A'
0x180025a8b  cmovg   ebx, r13d
0x180025a8f  mov     rdx, rsi
0x180025a92  lea     rcx, [rbp+Src]; Src
0x180025a96  cmp     rsi, [rbp+var_18]
0x180025a9a  ja      short loc_180025AB2
0x180025a9c  mov     [rbp+var_18], rdx
0x180025aa0  cmp     [rbp+var_10], 7
0x180025aa5  cmova   rcx, [rbp+Src]
0x180025aaa  xor     eax, eax
0x180025aac  mov     [rcx+rsi*2], ax
0x180025ab0  jmp     short loc_180025ABE
0x180025ab2  xor     r8d, r8d
0x180025ab5  sub     rdx, [rbp+var_18]
0x180025ab9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180025abe  lea     rax, [rbp+Src]
0x180025ac2  cmp     [rbp+var_10], 7
0x180025ac7  cmova   rax, [rbp+Src]
0x180025acc  mov     [rsp+60h+cchWideChar], esi; cchWideChar
0x180025ad0  mov     [rsp+60h+lpWideCharStr], rax; int
0x180025ad5  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180025ad9  mov     r8, rdi; lpMultiByteStr
0x180025adc  lea     edx, [r9+9]; dwFlags
0x180025ae0  xor     ecx, ecx; CodePage
0x180025ae2  call    cs:__imp_MultiByteToWideChar
0x180025ae8  mov     rdx, [rbp+var_10]
0x180025aec  mov     r8, [rbp+var_18]
0x180025af0  lea     rax, [rbp+Src]
0x180025af4  mov     rcx, [rbp+Src]
0x180025af8  cmp     rdx, 7
0x180025afc  cmova   rax, rcx
0x180025b00  lea     rdi, [rax+r8*2]
0x180025b04  jbe     short loc_180025B0C
0x180025b06  lea     rdx, [rcx+r8*2]
0x180025b0a  jmp     short loc_180025B18
0x180025b0c  lea     rax, [rbp+Src]
0x180025b10  lea     rdx, [rax+r8*2]
0x180025b14  lea     rcx, [rbp+Src]
0x180025b18  xor     r8d, r8d
0x180025b1b  call    __std_find_trivial_2
0x180025b20  mov     r9, rdi
0x180025b23  mov     r8, rax
0x180025b26  lea     rdx, [rbp+var_30]
0x180025b2a  lea     rcx, [rbp+Src]
0x180025b2e  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@0@Z; std::wstring::erase(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180025b33  lea     rdx, [rbp+Src]
0x180025b37  mov     rcx, r14
0x180025b3a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180025b3f  test    ebx, ebx
0x180025b41  jns     short loc_180025B5C
0x180025b43  mov     rcx, [rbp+28h]; this
0x180025b47  mov     r9d, ebx; char *
0x180025b4a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025b51  mov     edx, 125h; void *
0x180025b56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b5b  nop
0x180025b5c  lea     rcx, [rbp+Src]
0x180025b60  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025b65  mov     eax, ebx
0x180025b67  mov     rcx, [rbp+var_8]
0x180025b6b  xor     rcx, rsp; StackCookie
0x180025b6e  call    __security_check_cookie
0x180025b73  mov     rbx, [rsp+60h+arg_8]
0x180025b7b  add     rsp, 60h
0x180025b7f  pop     r14
0x180025b81  pop     r13
0x180025b83  pop     rdi
0x180025b84  pop     rsi
0x180025b85  pop     rbp
0x180025b86  retn
```
