# std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(wchar_t const *,wchar_t const *)

- ea: `0x1832c9930`
- end: `0x1832c9d36`
- name: `?to_bytes@?$wstring_convert@V?$codecvt_utf8@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEB_W0@Z`
- size: `1030`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1832c98f0`

## callees

- `0x1815c1600`
- `0x1815cc350`
- `0x1815ceeb0`
- `0x182d46c40`
- `0x1832c3a30`
- `0x1832c4780`
- `0x1832c9930`
- `0x1832ce3b0`
- `0x1832dbe96`

## import_xrefs

- `MSVCP140!?out@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEB_W1AEAPEB_WPEAD3AEAPEAD@Z` at `0x1832c9a0f`
- `MSVCP140!?out@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEB_W1AEAPEB_WPEAD3AEAPEAD@Z` at `0x1832c9a0f`
- `VCRUNTIME140!memmove` at `0x1832c9c86`
- `VCRUNTIME140!memmove` at `0x1832c9c86`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9b82`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9b92`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9ba2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9baf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9bf4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9c04`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9c14`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9c25`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9cd7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9ce7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9cf7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9d04`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9b82`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9b92`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9ba2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9baf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9bf4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9c04`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9c14`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9c25`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9cd7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9ce7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9cf7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1832c9d04`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall std::wstring_convert<std::codecvt_utf8<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(
        __int64 a1,
        _QWORD *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  unsigned __int8 *i; // rdx
  void **v9; // rsi
  int v10; // eax
  _BYTE *v11; // rax
  _BYTE *v12; // rax
  void *v13; // rcx
  unsigned __int64 v14; // rax
  void *v15; // rcx
  void *v16; // rax
  _BYTE *v17; // rax
  unsigned __int64 v18; // rcx
  int v20; // [rsp+40h] [rbp-69h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v22; // [rsp+60h] [rbp-49h]
  unsigned __int8 *v23; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int64 v24; // [rsp+70h] [rbp-39h] BYREF
  _QWORD Src[2]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v26; // [rsp+88h] [rbp-21h]
  unsigned __int64 v27; // [rsp+90h] [rbp-19h]
  void *v28[2]; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v29; // [rsp+A8h] [rbp-1h]
  unsigned __int64 v30; // [rsp+B0h] [rbp+7h]

  v22 = -2;
  v23 = a3;
  v20 = 0;
  v30 = 15;
  v29 = 0;
  LOBYTE(v28[0]) = 0;
  v27 = 15;
  v26 = 0;
  LOBYTE(Src[0]) = 0;
  if ( !*(_BYTE *)(a1 + 104) )
    *(_QWORD *)(a1 + 96) = 0;
  std::string::append(v28, 8, 0);
  *(_QWORD *)(a1 + 112) = 0;
  i = v23;
  if ( v23 != a4 )
  {
    while ( 1 )
    {
      v9 = v28;
      if ( v30 >= 0x10 )
        v9 = (void **)v28[0];
      v10 = std::codecvt<wchar_t,char,_Mbstatet>::out(
              *(_QWORD *)(a1 + 8),
              a1 + 96,
              i,
              a4,
              &v23,
              v9,
              (char *)v9 + v29,
              &v24,
              v20);
      if ( v10 < 0 )
        break;
      if ( v10 <= 1 )
      {
        if ( (unsigned __int64)v9 >= v24 )
        {
          if ( v29 >= 0x10 )
          {
            if ( !*(_BYTE *)(a1 + 105) )
            {
              std::range_error::range_error((std::range_error *)pExceptionObject, "bad conversion");
              throw (std::range_error *)pExceptionObject;
            }
            a2[3] = 15;
            a2[2] = 0;
            if ( a2[3] < 0x10u )
              v11 = a2;
            else
              v11 = (_BYTE *)*a2;
            *v11 = 0;
            std::string::assign(a2);
            std::string::~string(Src);
            std::string::~string(v28);
            return a2;
          }
          std::string::append(v28, 8, 0);
        }
        else
        {
          std::string::append(Src, v9, v24 - (_QWORD)v9);
        }
        i = v23;
      }
      else
      {
        if ( v10 != 3 )
          break;
        for ( i = v23; i != a4; v23 = i )
        {
          std::string::append(Src, 1, *i);
          i = v23 + 2;
        }
      }
      *(_QWORD *)(a1 + 112) = (i - a3) >> 1;
      if ( i == a4 )
        goto LABEL_52;
    }
    if ( !*(_BYTE *)(a1 + 105) )
    {
      std::range_error::range_error((std::range_error *)pExceptionObject, "bad conversion");
      throw (std::range_error *)pExceptionObject;
    }
    a2[3] = 15;
    a2[2] = 0;
    if ( a2[3] < 0x10u )
      v12 = a2;
    else
      v12 = (_BYTE *)*a2;
    *v12 = 0;
    std::string::assign(a2);
    if ( v27 >= 0x10 )
    {
      v13 = (void *)Src[0];
      if ( v27 + 1 >= 0x1000 )
      {
        if ( (Src[0] & 0x1F) != 0 )
          _invalid_parameter_noinfo_noreturn();
        v14 = *(_QWORD *)(Src[0] - 8LL);
        if ( v14 >= Src[0] )
          _invalid_parameter_noinfo_noreturn();
        if ( Src[0] - v14 < 8 )
          _invalid_parameter_noinfo_noreturn();
        if ( Src[0] - v14 > 0x27 )
          _invalid_parameter_noinfo_noreturn();
        v13 = *(void **)(Src[0] - 8LL);
      }
      operator delete(v13);
    }
    v27 = 15;
    v26 = 0;
    LOBYTE(Src[0]) = 0;
    if ( v30 < 0x10 )
      return a2;
    v15 = v28[0];
    if ( v30 + 1 < 0x1000 )
      goto LABEL_70;
    if ( ((__int64)v28[0] & 0x1F) != 0 )
      _invalid_parameter_noinfo_noreturn();
    v16 = (void *)*((_QWORD *)v28[0] - 1);
    if ( v16 >= v28[0] )
      _invalid_parameter_noinfo_noreturn();
    if ( (void *)((char *)v28[0] - (char *)v16) < (void *)8 )
      _invalid_parameter_noinfo_noreturn();
    if ( (void *)((char *)v28[0] - (char *)v16) > (void *)0x27 )
      _invalid_parameter_noinfo_noreturn();
    goto LABEL_69;
  }
LABEL_52:
  a2[3] = 15;
  a2[2] = 0;
  if ( a2[3] < 0x10u )
    v17 = a2;
  else
    v17 = (_BYTE *)*a2;
  *v17 = 0;
  v18 = v27;
  if ( v27 >= 0x10 )
  {
    *a2 = Src[0];
    Src[0] = 0;
  }
  else if ( v26 != -1 )
  {
    memmove(a2, Src, v26 + 1);
    v18 = v27;
  }
  a2[2] = v26;
  a2[3] = v18;
  v27 = 15;
  v26 = 0;
  LOBYTE(Src[0]) = 0;
  if ( v30 >= 0x10 )
  {
    v15 = v28[0];
    if ( v30 + 1 < 0x1000 )
    {
LABEL_70:
      operator delete(v15);
      return a2;
    }
    if ( ((__int64)v28[0] & 0x1F) != 0 )
      _invalid_parameter_noinfo_noreturn();
    v16 = (void *)*((_QWORD *)v28[0] - 1);
    if ( v16 >= v28[0] )
      _invalid_parameter_noinfo_noreturn();
    if ( (void *)((char *)v28[0] - (char *)v16) < (void *)8 )
      _invalid_parameter_noinfo_noreturn();
    if ( (void *)((char *)v28[0] - (char *)v16) > (void *)0x27 )
      _invalid_parameter_noinfo_noreturn();
LABEL_69:
    v15 = v16;
    goto LABEL_70;
  }
  return a2;
}

```

## disassembly

```asm
0x1832c9930  push    rbp
0x1832c9932  push    rbx
0x1832c9933  push    rsi
0x1832c9934  push    rdi
0x1832c9935  push    r12
0x1832c9937  push    r13
0x1832c9939  push    r14
0x1832c993b  push    r15
0x1832c993d  lea     rbp, [rsp-1Fh]
0x1832c9942  sub     rsp, 0C8h
0x1832c9949  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1832c9951  mov     rax, cs:__security_cookie
0x1832c9958  xor     rax, rsp
0x1832c995b  mov     [rbp+57h+var_48], rax
0x1832c995f  mov     rdi, r9
0x1832c9962  mov     r15, r8
0x1832c9965  mov     rbx, rdx
0x1832c9968  mov     r14, rcx
0x1832c996b  mov     [rbp+57h+var_98], r8
0x1832c996f  xor     r13d, r13d
0x1832c9972  mov     [rbp+57h+var_C0], r13d
0x1832c9976  mov     [rbp+57h+var_50], 0Fh
0x1832c997e  mov     [rbp+57h+var_58], r13
0x1832c9982  mov     byte ptr [rbp+57h+var_68], r13b
0x1832c9986  mov     [rbp+57h+var_70], 0Fh
0x1832c998e  mov     [rbp+57h+var_78], r13
0x1832c9992  mov     byte ptr [rbp+57h+Src], r13b
0x1832c9996  cmp     [rcx+68h], r13b
0x1832c999a  jnz     short loc_1832C99A2
0x1832c999c  xor     eax, eax
0x1832c999e  mov     [rcx+60h], rax
0x1832c99a2  xor     r8d, r8d
0x1832c99a5  lea     edx, [r8+8]
0x1832c99a9  lea     rcx, [rbp+57h+var_68]
0x1832c99ad  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x1832c99b2  mov     [r14+70h], r13
0x1832c99b6  mov     rdx, [rbp+57h+var_98]
0x1832c99ba  cmp     rdx, rdi
0x1832c99bd  jz      loc_1832C9C4D
0x1832c99c3  nop     dword ptr [rax+00h]
0x1832c99c7  nop     word ptr [rax+rax+00000000h]
0x1832c99d0  lea     rsi, [rbp+57h+var_68]
0x1832c99d4  cmp     [rbp+57h+var_50], 10h
0x1832c99d9  cmovnb  rsi, [rbp+57h+var_68]
0x1832c99de  mov     rcx, [rbp+57h+var_58]
0x1832c99e2  add     rcx, rsi
0x1832c99e5  lea     rax, [rbp+57h+var_90]
0x1832c99e9  mov     [rsp+100h+var_C8], rax
0x1832c99ee  mov     [rsp+100h+var_D0], rcx
0x1832c99f3  mov     [rsp+100h+var_D8], rsi
0x1832c99f8  lea     rax, [rbp+57h+var_98]
0x1832c99fc  mov     [rsp+100h+var_E0], rax
0x1832c9a01  mov     r9, rdi
0x1832c9a04  mov     r8, rdx
0x1832c9a07  lea     rdx, [r14+60h]
0x1832c9a0b  mov     rcx, [r14+8]
0x1832c9a0f  call    cs:__imp_?out@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEB_W1AEAPEB_WPEAD3AEAPEAD@Z; std::codecvt<wchar_t,char,_Mbstatet>::out(_Mbstatet &,wchar_t const *,wchar_t const *,wchar_t const * &,char *,char *,char * &)
0x1832c9a15  test    eax, eax
0x1832c9a17  js      loc_1832C9B27
0x1832c9a1d  cmp     eax, 1
0x1832c9a20  jle     short loc_1832C9A65
0x1832c9a22  cmp     eax, 3
0x1832c9a25  jnz     loc_1832C9B27
0x1832c9a2b  mov     rdx, [rbp+57h+var_98]
0x1832c9a2f  cmp     rdx, rdi
0x1832c9a32  jz      short loc_1832C9A9A
0x1832c9a34  nop     dword ptr [rax+00h]
0x1832c9a38  nop     dword ptr [rax+rax+00000000h]
0x1832c9a40  movzx   r8d, byte ptr [rdx]
0x1832c9a44  mov     edx, 1
0x1832c9a49  lea     rcx, [rbp+57h+Src]
0x1832c9a4d  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x1832c9a52  mov     rdx, [rbp+57h+var_98]
0x1832c9a56  add     rdx, 2
0x1832c9a5a  mov     [rbp+57h+var_98], rdx
0x1832c9a5e  cmp     rdx, rdi
0x1832c9a61  jnz     short loc_1832C9A40
0x1832c9a63  jmp     short loc_1832C9A9A
0x1832c9a65  mov     r8, [rbp+57h+var_90]
0x1832c9a69  cmp     rsi, r8
0x1832c9a6c  jnb     short loc_1832C9A7F
0x1832c9a6e  sub     r8, rsi; Size
0x1832c9a71  mov     rdx, rsi; void *
0x1832c9a74  lea     rcx, [rbp+57h+Src]; Src
0x1832c9a78  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::append(char const *,unsigned __int64)
0x1832c9a7d  jmp     short loc_1832C9A96
0x1832c9a7f  cmp     [rbp+57h+var_58], 10h
0x1832c9a84  jnb     short loc_1832C9AB5
0x1832c9a86  xor     r8d, r8d
0x1832c9a89  lea     edx, [r8+8]
0x1832c9a8d  lea     rcx, [rbp+57h+var_68]
0x1832c9a91  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x1832c9a96  mov     rdx, [rbp+57h+var_98]
0x1832c9a9a  mov     rax, rdx
0x1832c9a9d  sub     rax, r15
0x1832c9aa0  sar     rax, 1
0x1832c9aa3  mov     [r14+70h], rax
0x1832c9aa7  cmp     rdx, rdi
0x1832c9aaa  jnz     loc_1832C99D0
0x1832c9ab0  jmp     loc_1832C9C4D
0x1832c9ab5  cmp     byte ptr [r14+69h], 0
0x1832c9aba  jz      short loc_1832C9B06
0x1832c9abc  lea     rdx, [r14+20h]
0x1832c9ac0  mov     qword ptr [rbx+18h], 0Fh
0x1832c9ac8  mov     [rbx+10h], r13
0x1832c9acc  cmp     qword ptr [rbx+18h], 10h
0x1832c9ad1  jb      short loc_1832C9AD8
0x1832c9ad3  mov     rax, [rbx]
0x1832c9ad6  jmp     short loc_1832C9ADB
0x1832c9ad8  mov     rax, rbx
0x1832c9adb  mov     byte ptr [rax], 0
0x1832c9ade  or      r9, 0FFFFFFFFFFFFFFFFh
0x1832c9ae2  xor     r8d, r8d
0x1832c9ae5  mov     rcx, rbx; void *
0x1832c9ae8  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1832c9aed  nop
0x1832c9aee  lea     rcx, [rbp+57h+Src]
0x1832c9af2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1832c9af7  nop
0x1832c9af8  lea     rcx, [rbp+57h+var_68]
0x1832c9afc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1832c9b01  jmp     loc_1832C9D13
0x1832c9b06  lea     rdx, aBadConversion; "bad conversion"
0x1832c9b0d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1832c9b11  call    ??0range_error@std@@QEAA@PEBD@Z; std::range_error::range_error(char const *)
0x1832c9b16  lea     rdx, _TI3?AVrange_error@std@@; pThrowInfo
0x1832c9b1d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1832c9b21  call    _CxxThrowException_0
0x1832c9b27  cmp     byte ptr [r14+69h], 0
0x1832c9b2c  jz      loc_1832C9C2C
0x1832c9b32  lea     rdx, [r14+20h]
0x1832c9b36  mov     qword ptr [rbx+18h], 0Fh
0x1832c9b3e  mov     [rbx+10h], r13
0x1832c9b42  cmp     qword ptr [rbx+18h], 10h
0x1832c9b47  jb      short loc_1832C9B4E
0x1832c9b49  mov     rax, [rbx]
0x1832c9b4c  jmp     short loc_1832C9B51
0x1832c9b4e  mov     rax, rbx
0x1832c9b51  mov     byte ptr [rax], 0
0x1832c9b54  or      r9, 0FFFFFFFFFFFFFFFFh
0x1832c9b58  xor     r8d, r8d
0x1832c9b5b  mov     rcx, rbx; void *
0x1832c9b5e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1832c9b63  nop
0x1832c9b64  mov     rax, [rbp+57h+var_70]
0x1832c9b68  cmp     rax, 10h
0x1832c9b6c  jb      short loc_1832C9BBE
0x1832c9b6e  inc     rax
0x1832c9b71  mov     rcx, [rbp+57h+Src]
0x1832c9b75  cmp     rax, 1000h
0x1832c9b7b  jb      short loc_1832C9BB9
0x1832c9b7d  test    cl, 1Fh
0x1832c9b80  jz      short loc_1832C9B89
0x1832c9b82  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9b89  mov     rax, [rcx-8]
0x1832c9b8d  cmp     rax, rcx
0x1832c9b90  jb      short loc_1832C9B99
0x1832c9b92  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9b99  sub     rcx, rax
0x1832c9b9c  cmp     rcx, 8
0x1832c9ba0  jnb     short loc_1832C9BA9
0x1832c9ba2  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9ba9  cmp     rcx, 27h ; '''
0x1832c9bad  jbe     short loc_1832C9BB6
0x1832c9baf  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9bb6  mov     rcx, rax; void *
0x1832c9bb9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1832c9bbe  mov     [rbp+57h+var_70], 0Fh
0x1832c9bc6  mov     [rbp+57h+var_78], r13
0x1832c9bca  mov     byte ptr [rbp+57h+Src], 0
0x1832c9bce  mov     rax, [rbp+57h+var_50]
0x1832c9bd2  cmp     rax, 10h
0x1832c9bd6  jb      loc_1832C9D13
0x1832c9bdc  inc     rax
0x1832c9bdf  mov     rcx, [rbp+57h+var_68]
0x1832c9be3  cmp     rax, 1000h
0x1832c9be9  jb      loc_1832C9D0E
0x1832c9bef  test    cl, 1Fh
0x1832c9bf2  jz      short loc_1832C9BFB
0x1832c9bf4  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9bfb  mov     rax, [rcx-8]
0x1832c9bff  cmp     rax, rcx
0x1832c9c02  jb      short loc_1832C9C0B
0x1832c9c04  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9c0b  sub     rcx, rax
0x1832c9c0e  cmp     rcx, 8
0x1832c9c12  jnb     short loc_1832C9C1B
0x1832c9c14  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9c1b  cmp     rcx, 27h ; '''
0x1832c9c1f  jbe     loc_1832C9D0B
0x1832c9c25  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9c2c  lea     rdx, aBadConversion; "bad conversion"
0x1832c9c33  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1832c9c37  call    ??0range_error@std@@QEAA@PEBD@Z; std::range_error::range_error(char const *)
0x1832c9c3c  lea     rdx, _TI3?AVrange_error@std@@; pThrowInfo
0x1832c9c43  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1832c9c47  call    _CxxThrowException_0
0x1832c9c4d  mov     qword ptr [rbx+18h], 0Fh
0x1832c9c55  mov     [rbx+10h], r13
0x1832c9c59  cmp     qword ptr [rbx+18h], 10h
0x1832c9c5e  jb      short loc_1832C9C65
0x1832c9c60  mov     rax, [rbx]
0x1832c9c63  jmp     short loc_1832C9C68
0x1832c9c65  mov     rax, rbx
0x1832c9c68  mov     byte ptr [rax], 0
0x1832c9c6b  mov     rcx, [rbp+57h+var_70]
0x1832c9c6f  cmp     rcx, 10h
0x1832c9c73  jnb     short loc_1832C9C92
0x1832c9c75  mov     r8, [rbp+57h+var_78]
0x1832c9c79  add     r8, 1; Size
0x1832c9c7d  jz      short loc_1832C9C9D
0x1832c9c7f  lea     rdx, [rbp+57h+Src]; Src
0x1832c9c83  mov     rcx, rbx; void *
0x1832c9c86  call    cs:__imp_memmove
0x1832c9c8c  mov     rcx, [rbp+57h+var_70]
0x1832c9c90  jmp     short loc_1832C9C9D
0x1832c9c92  mov     rax, [rbp+57h+Src]
0x1832c9c96  mov     [rbx], rax
0x1832c9c99  mov     [rbp+57h+Src], r13
0x1832c9c9d  mov     rax, [rbp+57h+var_78]
0x1832c9ca1  mov     [rbx+10h], rax
0x1832c9ca5  mov     [rbx+18h], rcx
0x1832c9ca9  mov     [rbp+57h+var_70], 0Fh
0x1832c9cb1  mov     [rbp+57h+var_78], r13
0x1832c9cb5  mov     byte ptr [rbp+57h+Src], 0
0x1832c9cb9  mov     rax, [rbp+57h+var_50]
0x1832c9cbd  cmp     rax, 10h
0x1832c9cc1  jb      short loc_1832C9D13
0x1832c9cc3  inc     rax
0x1832c9cc6  mov     rcx, [rbp+57h+var_68]
0x1832c9cca  cmp     rax, 1000h
0x1832c9cd0  jb      short loc_1832C9D0E
0x1832c9cd2  test    cl, 1Fh
0x1832c9cd5  jz      short loc_1832C9CDE
0x1832c9cd7  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9cde  mov     rax, [rcx-8]
0x1832c9ce2  cmp     rax, rcx
0x1832c9ce5  jb      short loc_1832C9CEE
0x1832c9ce7  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9cee  sub     rcx, rax
0x1832c9cf1  cmp     rcx, 8
0x1832c9cf5  jnb     short loc_1832C9CFE
0x1832c9cf7  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9cfe  cmp     rcx, 27h ; '''
0x1832c9d02  jbe     short loc_1832C9D0B
0x1832c9d04  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1832c9d0b  mov     rcx, rax; void *
0x1832c9d0e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1832c9d13  mov     rax, rbx
0x1832c9d16  mov     rcx, [rbp+57h+var_48]
0x1832c9d1a  xor     rcx, rsp; StackCookie
0x1832c9d1d  call    __security_check_cookie
0x1832c9d22  add     rsp, 0C8h
0x1832c9d29  pop     r15
0x1832c9d2b  pop     r14
0x1832c9d2d  pop     r13
0x1832c9d2f  pop     r12
0x1832c9d31  pop     rdi
0x1832c9d32  pop     rsi
0x1832c9d33  pop     rbx
0x1832c9d34  pop     rbp
0x1832c9d35  retn
```
