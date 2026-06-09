# std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)

- ea: `0x1800236e0`
- end: `0x180023944`
- name: `?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z`
- size: `612`
- prototype: `bool __fastcall(std::filesystem *__hidden this, const struct std::filesystem::path *, struct std::error_code *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015c0c`

## callees

- `0x1800236e0`
- `0x180026b58`
- `0x180028810`
- `0x180028e4c`
- `0x180029644`
- `0x1800403f0`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023878`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023863`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023863`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall std::filesystem::create_directories(
        std::filesystem *this,
        const struct std::filesystem::path *a2,
        struct std::error_code *a3)
{
  const struct std::filesystem::path *v3; // r13
  std::filesystem *v4; // rdi
  _QWORD *v5; // rbx
  char result; // al
  const wchar_t *v7; // r8
  std::filesystem *v8; // rcx
  const wchar_t *v9; // rsi
  const wchar_t *i; // rbx
  char v11; // r14
  DWORD LastError; // eax
  DWORD v13; // r12d
  const wchar_t *v14; // rdi
  const WCHAR *v15; // rbx
  DWORD v16; // ecx
  __int128 v17; // [rsp+28h] [rbp-58h]
  LPCWSTR lpPathName[2]; // [rsp+58h] [rbp-28h] BYREF
  __m128i si128; // [rsp+68h] [rbp-18h]

  v3 = a2;
  *(_QWORD *)&v17 = a2;
  v4 = this;
  v5 = (_QWORD *)((char *)this + 16);
  result = 0;
  if ( *((_QWORD *)this + 2) )
  {
    *(_DWORD *)a2 = 0;
    *((_QWORD *)a2 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)lpPathName = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpPathName[0]) = 0;
    std::wstring::reserve(lpPathName, *v5, a3);
    if ( *((_QWORD *)v4 + 3) <= 7u )
    {
      v8 = v4;
    }
    else
    {
      v8 = *(std::filesystem **)v4;
      v4 = *(std::filesystem **)v4;
    }
    v9 = (const wchar_t *)((char *)v8 + 2 * *v5);
    for ( i = std::filesystem::_Find_root_name_end(v4, v9, v7); i != v9; ++i )
    {
      if ( *i != 92 && *i != 47 )
        break;
    }
    if ( i != (const wchar_t *)v4
      && (__int64)(((char *)v9 - (char *)i) & 0xFFFFFFFFFFFFFFFEuLL) >= 6
      && (*(_DWORD *)i & 0xFFFFFFDF) - 3801153 < 0x1A
      && (i[2] == 92 || i[2] == 47) )
    {
      i += 2;
    }
    std::wstring::append(lpPathName);
    v11 = 0;
    LastError = 0;
    v13 = 0;
    if ( i != v9 )
    {
      do
      {
        v14 = i;
        do
        {
          if ( *v14 != 92 && *v14 != 47 )
            break;
          ++v14;
        }
        while ( v14 != v9 );
        while ( v14 != v9 && *v14 != 92 && *v14 != 47 )
          ++v14;
        std::wstring::append(lpPathName);
        v15 = (const WCHAR *)lpPathName;
        if ( si128.m128i_i64[1] > 7uLL )
          v15 = lpPathName[0];
        if ( CreateDirectoryW(v15, 0) )
        {
          v11 = 1;
          LastError = 0;
          v16 = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError == 183 )
          {
            LastError = _std_fs_get_stats(v15);
            if ( !LastError )
              LastError = 183;
          }
          v11 = 0;
          v16 = LastError;
          if ( LastError )
          {
            if ( LastError != 2
              && LastError != 3
              && LastError != 53
              && LastError != 64
              && LastError != 123
              && LastError != 267 )
            {
              v13 = LastError;
            }
            v16 = LastError;
          }
        }
        i = v14;
      }
      while ( v14 != v9 );
      v3 = (const struct std::filesystem::path *)v17;
      if ( v16 )
      {
        if ( v13 )
          LastError = v13;
      }
    }
    LODWORD(v17) = LastError;
    *((_QWORD *)&v17 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)v3 = v17;
    std::wstring::_Tidy_deallocate(lpPathName);
    return v11;
  }
  else
  {
    LODWORD(v17) = 3;
    *((_QWORD *)&v17 + 1) = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    *(_OWORD *)a2 = v17;
  }
  return result;
}

```

## disassembly

```asm
0x1800236e0  mov     [rsp-38h+arg_10], rbx
0x1800236e5  push    rbp
0x1800236e6  push    rsi
0x1800236e7  push    rdi
0x1800236e8  push    r12
0x1800236ea  push    r13
0x1800236ec  push    r14
0x1800236ee  push    r15
0x1800236f0  mov     rbp, rsp
0x1800236f3  sub     rsp, 80h
0x1800236fa  mov     rax, cs:__security_cookie
0x180023701  xor     rax, rsp
0x180023704  mov     [rbp+var_8], rax
0x180023708  mov     r13, rdx
0x18002370b  mov     qword ptr [rbp+var_58], rdx
0x18002370f  mov     rdi, rcx
0x180023712  lea     rbx, [rcx+10h]
0x180023716  xor     eax, eax
0x180023718  lea     r15, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18002371f  cmp     [rbx], rax
0x180023722  jnz     short loc_18002373C
0x180023724  mov     dword ptr [rbp+var_58], 3
0x18002372b  mov     qword ptr [rbp+var_58+8], r15
0x18002372f  movups  xmm0, [rbp+var_58]
0x180023733  movdqu  xmmword ptr [rdx], xmm0
0x180023737  jmp     loc_18002391D
0x18002373c  mov     [rdx], eax
0x18002373e  mov     [rdx+8], r15
0x180023742  xorps   xmm0, xmm0
0x180023745  movups  xmmword ptr [rbp+lpPathName], xmm0
0x180023749  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180023751  movdqu  [rbp+var_18], xmm1
0x180023756  mov     word ptr [rbp+lpPathName], ax
0x18002375a  mov     rdx, [rbx]
0x18002375d  lea     rcx, [rbp+lpPathName]
0x180023761  call    ?reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x180023766  cmp     qword ptr [rdi+18h], 7
0x18002376b  jbe     short loc_180023775
0x18002376d  mov     rcx, [rdi]
0x180023770  mov     rdi, rcx
0x180023773  jmp     short loc_180023778
0x180023775  mov     rcx, rdi
0x180023778  mov     rax, [rbx]
0x18002377b  lea     rsi, [rcx+rax*2]
0x18002377f  mov     rdx, rsi; wchar_t *
0x180023782  mov     rcx, rdi; this
0x180023785  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18002378a  mov     rbx, rax
0x18002378d  cmp     rax, rsi
0x180023790  jz      short loc_1800237A7
0x180023792  cmp     word ptr [rbx], 5Ch ; '\'
0x180023796  jz      short loc_18002379E
0x180023798  cmp     word ptr [rbx], 2Fh ; '/'
0x18002379c  jnz     short loc_1800237A7
0x18002379e  add     rbx, 2
0x1800237a2  cmp     rbx, rsi
0x1800237a5  jnz     short loc_180023792
0x1800237a7  cmp     rbx, rdi
0x1800237aa  jz      short loc_1800237DE
0x1800237ac  mov     rax, rsi
0x1800237af  sub     rax, rbx
0x1800237b2  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800237b6  cmp     rax, 6
0x1800237ba  jl      short loc_1800237DE
0x1800237bc  mov     eax, [rbx]
0x1800237be  and     eax, 0FFFFFFDFh
0x1800237c1  sub     eax, 3A0041h
0x1800237c6  cmp     eax, 1Ah
0x1800237c9  jnb     short loc_1800237DE
0x1800237cb  lea     rax, [rbx+4]
0x1800237cf  cmp     word ptr [rax], 5Ch ; '\'
0x1800237d3  jz      short loc_1800237DB
0x1800237d5  cmp     word ptr [rax], 2Fh ; '/'
0x1800237d9  jnz     short loc_1800237DE
0x1800237db  mov     rbx, rax
0x1800237de  mov     r8, rbx
0x1800237e1  sub     r8, rdi
0x1800237e4  sar     r8, 1
0x1800237e7  mov     rdx, rdi
0x1800237ea  lea     rcx, [rbp+lpPathName]; Src
0x1800237ee  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800237f3  xor     edx, edx
0x1800237f5  mov     r14b, dl
0x1800237f8  mov     eax, edx
0x1800237fa  mov     r12d, edx
0x1800237fd  cmp     rbx, rsi
0x180023800  jz      loc_180023900
0x180023806  mov     r13d, 0B7h
0x18002380c  mov     rdi, rbx
0x18002380f  cmp     word ptr [rdi], 5Ch ; '\'
0x180023813  jz      short loc_18002381B
0x180023815  cmp     word ptr [rdi], 2Fh ; '/'
0x180023819  jnz     short loc_180023836
0x18002381b  add     rdi, 2
0x18002381f  cmp     rdi, rsi
0x180023822  jnz     short loc_18002380F
0x180023824  jmp     short loc_180023836
0x180023826  cmp     word ptr [rdi], 5Ch ; '\'
0x18002382a  jz      short loc_18002383B
0x18002382c  cmp     word ptr [rdi], 2Fh ; '/'
0x180023830  jz      short loc_18002383B
0x180023832  add     rdi, 2
0x180023836  cmp     rdi, rsi
0x180023839  jnz     short loc_180023826
0x18002383b  mov     r8, rdi
0x18002383e  sub     r8, rbx
0x180023841  sar     r8, 1
0x180023844  mov     rdx, rbx
0x180023847  lea     rcx, [rbp+lpPathName]; Src
0x18002384b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180023850  lea     rbx, [rbp+lpPathName]
0x180023854  cmp     qword ptr [rbp+var_18+8], 7
0x180023859  cmova   rbx, [rbp+lpPathName]
0x18002385e  xor     edx, edx; lpSecurityAttributes
0x180023860  mov     rcx, rbx; lpPathName
0x180023863  call    cs:__imp_CreateDirectoryW
0x180023869  xor     edx, edx
0x18002386b  test    eax, eax
0x18002386d  jz      short loc_180023878
0x18002386f  mov     r14b, 1
0x180023872  xor     eax, eax
0x180023874  mov     ecx, edx
0x180023876  jmp     short loc_1800238E5
0x180023878  call    cs:__imp_GetLastError
0x18002387e  cmp     eax, r13d
0x180023881  jnz     short loc_1800238B4
0x180023883  xorps   xmm0, xmm0
0x180023886  movups  [rbp+var_48], xmm0
0x18002388a  movups  [rbp+var_38], xmm0
0x18002388e  or      r9d, 0FFFFFFFFh
0x180023892  mov     r8d, 3
0x180023898  lea     rdx, [rbp+var_48]
0x18002389c  mov     rcx, rbx; lpFileName
0x18002389f  call    __std_fs_get_stats
0x1800238a4  xor     edx, edx
0x1800238a6  test    eax, eax
0x1800238a8  jnz     short loc_1800238B6
0x1800238aa  test    byte ptr [rbp+var_38], 10h
0x1800238ae  cmovz   eax, r13d
0x1800238b2  jmp     short loc_1800238B6
0x1800238b4  xor     edx, edx
0x1800238b6  mov     r14b, dl
0x1800238b9  mov     ecx, eax
0x1800238bb  test    eax, eax
0x1800238bd  jz      short loc_1800238E5
0x1800238bf  sub     ecx, 2
0x1800238c2  jz      short loc_1800238E3
0x1800238c4  sub     ecx, 1
0x1800238c7  jz      short loc_1800238E3
0x1800238c9  sub     ecx, 32h ; '2'
0x1800238cc  jz      short loc_1800238E3
0x1800238ce  sub     ecx, 0Bh
0x1800238d1  jz      short loc_1800238E3
0x1800238d3  sub     ecx, 3Bh ; ';'
0x1800238d6  jz      short loc_1800238E3
0x1800238d8  cmp     ecx, 90h
0x1800238de  jz      short loc_1800238E3
0x1800238e0  mov     r12d, eax
0x1800238e3  mov     ecx, eax
0x1800238e5  mov     rbx, rdi
0x1800238e8  cmp     rdi, rsi
0x1800238eb  jnz     loc_18002380C
0x1800238f1  test    ecx, ecx
0x1800238f3  mov     r13, qword ptr [rbp+var_58]
0x1800238f7  jz      short loc_180023900
0x1800238f9  test    r12d, r12d
0x1800238fc  cmovnz  eax, r12d
0x180023900  mov     dword ptr [rbp+var_58], eax
0x180023903  mov     qword ptr [rbp+var_58+8], r15
0x180023907  movups  xmm0, [rbp+var_58]
0x18002390b  movdqu  xmmword ptr [r13+0], xmm0
0x180023911  lea     rcx, [rbp+lpPathName]
0x180023915  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002391a  mov     al, r14b
0x18002391d  mov     rcx, [rbp+var_8]
0x180023921  xor     rcx, rsp; StackCookie
0x180023924  call    __security_check_cookie
0x180023929  mov     rbx, [rsp+80h+arg_10]
0x180023931  add     rsp, 80h
0x180023938  pop     r15
0x18002393a  pop     r14
0x18002393c  pop     r13
0x18002393e  pop     r12
0x180023940  pop     rdi
0x180023941  pop     rsi
0x180023942  pop     rbp
0x180023943  retn
```
