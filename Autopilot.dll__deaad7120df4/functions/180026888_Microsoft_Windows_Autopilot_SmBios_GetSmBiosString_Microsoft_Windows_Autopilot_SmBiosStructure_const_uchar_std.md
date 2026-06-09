# Microsoft::Windows::Autopilot::SmBios::GetSmBiosString(Microsoft::Windows::Autopilot::SmBiosStructure const *,uchar,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180026888`
- end: `0x180026a5e`
- name: `?GetSmBiosString@SmBios@Autopilot@Windows@Microsoft@@SAJPEBUSmBiosStructure@234@EAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64, char, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180026a64`

## callees

- `0x1800045d0`
- `0x1800096e0`
- `0x180010764`
- `0x180017a20`
- `0x180017b2c`
- `0x18001982c`
- `0x18001d4e4`
- `0x180026888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026939`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180026926`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800269b2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180026926`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800269b2`

## string_xrefs

- `0x180026a20`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\smbios.cpp`

## pseudocode

```c
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
  __int64 v19; // r8
  int lpWideCharStr; // [rsp+20h] [rbp-40h]
  _BYTE v22[8]; // [rsp+30h] [rbp-30h] BYREF
  LPWSTR Src[2]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v24; // [rsp+48h] [rbp-18h]
  unsigned __int64 v25; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v5 = 0;
  *(_OWORD *)Src = 0;
  v6 = 0;
  v24 = 0;
  v7 = 7;
  v25 = 7;
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
    if ( cchWideChar > v24 )
    {
      std::wstring::append(Src);
    }
    else
    {
      v24 = cchWideChar;
      *((_WORD *)Src + cchWideChar) = 0;
    }
    v13 = (WCHAR *)Src;
    if ( v25 > 7 )
      v13 = Src[0];
    MultiByteToWideChar(0, 8u, v9, -1, v13, cchWideChar);
    v7 = v25;
    v6 = v24;
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
  std::wstring::erase(Src, v22, trivial_2, v16);
  std::wstring::operator=(a3, Src, v19);
  if ( v5 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\smbios.cpp",
      (const char *)(unsigned int)v5,
      lpWideCharStr);
  std::wstring::_Tidy_deallocate((char **)Src);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180026888  mov     [rsp-28h+arg_8], rbx
0x18002688d  push    rbp
0x18002688e  push    rsi
0x18002688f  push    rdi
0x180026890  push    r13
0x180026892  push    r14
0x180026894  mov     rbp, rsp
0x180026897  sub     rsp, 60h
0x18002689b  mov     rax, cs:__security_cookie
0x1800268a2  xor     rax, rsp
0x1800268a5  mov     [rbp+var_8], rax
0x1800268a9  mov     r14, r8
0x1800268ac  mov     r9b, dl
0x1800268af  xor     ebx, ebx
0x1800268b1  xorps   xmm0, xmm0
0x1800268b4  movups  xmmword ptr [rbp+Src], xmm0
0x1800268b8  xor     r8d, r8d
0x1800268bb  mov     [rbp+var_18], r8
0x1800268bf  lea     edx, [rbx+7]
0x1800268c2  mov     [rbp+var_10], rdx
0x1800268c6  xor     eax, eax
0x1800268c8  mov     word ptr [rbp+Src], ax
0x1800268cc  test    r9b, r9b
0x1800268cf  jz      loc_1800269C6
0x1800268d5  mov     al, 1
0x1800268d7  movzx   edi, byte ptr [rcx+1]
0x1800268db  add     rdi, rcx
0x1800268de  jmp     short loc_1800268F2
0x1800268e0  cmp     al, r9b
0x1800268e3  jz      short loc_1800268F7
0x1800268e5  inc     rdi
0x1800268e8  cmp     byte ptr [rdi], 0
0x1800268eb  jnz     short loc_1800268E0
0x1800268ed  inc     rdi
0x1800268f0  inc     al
0x1800268f2  cmp     byte ptr [rdi], 0
0x1800268f5  jnz     short loc_1800268E0
0x1800268f7  mov     al, [rdi]
0x1800268f9  neg     al
0x1800268fb  sbb     ebx, ebx
0x1800268fd  not     ebx
0x1800268ff  mov     r13d, 8000FFFFh
0x180026905  and     ebx, r13d
0x180026908  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x180026910  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x180026919  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002691d  mov     r8, rdi; lpMultiByteStr
0x180026920  lea     edx, [r9+9]; dwFlags
0x180026924  xor     ecx, ecx; CodePage
0x180026926  call    cs:__imp_MultiByteToWideChar
0x18002692d  nop     dword ptr [rax+rax+00h]
0x180026932  movsxd  rsi, eax
0x180026935  test    eax, eax
0x180026937  jnz     short loc_180026954
0x180026939  call    cs:__imp_GetLastError
0x180026940  nop     dword ptr [rax+rax+00h]
0x180026945  mov     ebx, eax
0x180026947  test    eax, eax
0x180026949  jle     short loc_180026954
0x18002694b  movzx   ebx, ax
0x18002694e  or      ebx, 80070000h
0x180026954  test    ebx, ebx
0x180026956  js      short loc_18002695F
0x180026958  cmp     esi, 41h ; 'A'
0x18002695b  cmovg   ebx, r13d
0x18002695f  mov     rdx, rsi
0x180026962  lea     rcx, [rbp+Src]; Src
0x180026966  cmp     rsi, [rbp+var_18]
0x18002696a  ja      short loc_180026982
0x18002696c  mov     [rbp+var_18], rdx
0x180026970  cmp     [rbp+var_10], 7
0x180026975  cmova   rcx, [rbp+Src]
0x18002697a  xor     eax, eax
0x18002697c  mov     [rcx+rsi*2], ax
0x180026980  jmp     short loc_18002698E
0x180026982  xor     r8d, r8d
0x180026985  sub     rdx, [rbp+var_18]
0x180026989  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18002698e  lea     rax, [rbp+Src]
0x180026992  cmp     [rbp+var_10], 7
0x180026997  cmova   rax, [rbp+Src]
0x18002699c  mov     [rsp+60h+cchWideChar], esi; cchWideChar
0x1800269a0  mov     [rsp+60h+lpWideCharStr], rax; int
0x1800269a5  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800269a9  mov     r8, rdi; lpMultiByteStr
0x1800269ac  lea     edx, [r9+9]; dwFlags
0x1800269b0  xor     ecx, ecx; CodePage
0x1800269b2  call    cs:__imp_MultiByteToWideChar
0x1800269b9  nop     dword ptr [rax+rax+00h]
0x1800269be  mov     rdx, [rbp+var_10]
0x1800269c2  mov     r8, [rbp+var_18]
0x1800269c6  lea     rax, [rbp+Src]
0x1800269ca  mov     rcx, [rbp+Src]
0x1800269ce  cmp     rdx, 7
0x1800269d2  cmova   rax, rcx
0x1800269d6  lea     rdi, [rax+r8*2]
0x1800269da  jbe     short loc_1800269E2
0x1800269dc  lea     rdx, [rcx+r8*2]
0x1800269e0  jmp     short loc_1800269EE
0x1800269e2  lea     rax, [rbp+Src]
0x1800269e6  lea     rdx, [rax+r8*2]
0x1800269ea  lea     rcx, [rbp+Src]
0x1800269ee  xor     r8d, r8d
0x1800269f1  call    __std_find_trivial_2
0x1800269f6  mov     r9, rdi
0x1800269f9  mov     r8, rax
0x1800269fc  lea     rdx, [rbp+var_30]
0x180026a00  lea     rcx, [rbp+Src]
0x180026a04  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@0@Z; std::wstring::erase(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x180026a09  lea     rdx, [rbp+Src]
0x180026a0d  mov     rcx, r14
0x180026a10  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180026a15  test    ebx, ebx
0x180026a17  jns     short loc_180026A32
0x180026a19  mov     rcx, [rbp+28h]; this
0x180026a1d  mov     r9d, ebx; char *
0x180026a20  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026a27  mov     edx, 125h; void *
0x180026a2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a31  nop
0x180026a32  lea     rcx, [rbp+Src]
0x180026a36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026a3b  mov     eax, ebx
0x180026a3d  mov     rcx, [rbp+var_8]
0x180026a41  xor     rcx, rsp; StackCookie
0x180026a44  call    __security_check_cookie
0x180026a49  mov     rbx, [rsp+60h+arg_8]
0x180026a51  add     rsp, 60h
0x180026a55  pop     r14
0x180026a57  pop     r13
0x180026a59  pop     rdi
0x180026a5a  pop     rsi
0x180026a5b  pop     rbp
0x180026a5c  retn
```
