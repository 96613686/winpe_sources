# boost::filesystem::detail::create_directories(boost::filesystem::path const &,boost::system::error_code *)

- ea: `0x1400082b0`
- end: `0x14000882f`
- name: `?create_directories@detail@filesystem@boost@@YA_NAEBVpath@23@PEAVerror_code@system@3@@Z`
- size: `1407`
- prototype: `bool __fastcall(boost::filesystem::detail *__hidden this, const struct boost::filesystem::path *, struct boost::system::error_code *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14008a66c`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140004ab4`
- `0x140004f20`
- `0x1400054d0`
- `0x140005580`
- `0x140005910`
- `0x140005a00`
- `0x140005af0`
- `0x1400061d0`
- `0x140006380`
- `0x140006680`
- `0x140006a60`
- `0x140006e10`
- `0x140006f50`
- `0x140007370`
- `0x1400082b0`
- `0x140008920`
- `0x140009070`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000c2b8`
- `0x140013dc4`
- `0x14009b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000867c`
- `KERNEL32!GetLastError` at `0x14000867c`
- `KERNEL32!CreateDirectoryW` at `0x1400085e9`
- `KERNEL32!CreateDirectoryW` at `0x1400085e9`

## string_xrefs

- `0x140008788`: `boost::filesystem::create_directories`
- `0x1400087d1`: `boost::filesystem::create_directories`
- `0x14000880e`: `boost::filesystem::create_directories`
- `0x1400086ab`: `boost::filesystem::create_directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall boost::filesystem::detail::create_directories(
        boost::filesystem::detail *this,
        const struct boost::filesystem::path *a2,
        struct boost::system::error_code *a3)
{
  unsigned __int8 v5; // al
  boost::filesystem::detail *v6; // rcx
  const struct boost::filesystem::path *v7; // rsi
  boost::filesystem::detail *v8; // rcx
  const struct boost::filesystem::path *v9; // r14
  unsigned __int64 filename_v4_size; // rax
  LPCWSTR *v11; // rcx
  char *v12; // rdx
  unsigned __int64 v13; // rax
  LPCWSTR *v14; // rcx
  char *v15; // rdx
  void *v16; // rcx
  char v17; // bl
  const WCHAR *v18; // rcx
  __int64 v19; // xmm1_8
  void *v20; // rcx
  DWORD LastError; // ebx
  __int64 v23; // xmm1_8
  __int64 error_code; // rax
  const char *v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpPathName[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h]
  void *Block[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v36; // [rsp+A8h] [rbp-58h]
  _BYTE v37[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int128 pExceptionObject; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v42; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v43; // [rsp+F8h] [rbp-8h]
  _BYTE v44[32]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v45; // [rsp+138h] [rbp+38h]
  __int64 v46; // [rsp+140h] [rbp+40h]

  if ( *((_QWORD *)this + 2) )
  {
    if ( a2 )
    {
      *(_OWORD *)a2 = 0;
      *((_QWORD *)a2 + 2) = 0;
    }
    boost::filesystem::path::end(this, v44, a3);
    std::wstring::wstring((__int64)v37, (__int64)v44);
    v39 = v45;
    v40 = v46;
    std::wstring::wstring((__int64)lpPathName, (__int64)this);
    v7 = boost::filesystem::detail::dot_path(v6);
    v9 = boost::filesystem::detail::dot_dot_path(v8);
    v27 = 0;
    v28 = 0;
    filename_v4_size = boost::filesystem::path::find_filename_v4_size((boost::filesystem::path *)lpPathName);
    v11 = lpPathName;
    if ( v31 > 7 )
      v11 = (LPCWSTR *)lpPathName[0];
    v12 = (char *)v11 + 2 * (v30 - filename_v4_size);
    *(_OWORD *)Block = 0;
    v35 = 0;
    v36 = 0;
    if ( v12 == &v12[2 * filename_v4_size] )
    {
      v35 = 0;
      v36 = 7;
      LOWORD(Block[0]) = 0;
    }
    else
    {
      std::wstring::_Construct<1,wchar_t *>(Block, v12, (__int64)(2 * filename_v4_size) >> 1);
    }
    if ( *(_QWORD *)(boost::filesystem::path::find_relative_path(lpPathName, &v32) + 8) )
    {
      while ( 1 )
      {
        if ( v35
          && (unsigned int)boost::filesystem::path::compare_v4((boost::filesystem::path *)Block, v7)
          && (unsigned int)boost::filesystem::path::compare_v4((boost::filesystem::path *)Block, v9) )
        {
          boost::filesystem::detail::_anonymous_namespace_::status_impl(&v26, lpPathName, &v27);
          if ( (_DWORD)v26 == 3 )
            goto LABEL_31;
          if ( !(_DWORD)v26 )
            break;
        }
        boost::filesystem::path::iterator::decrement_v4((boost::filesystem::path::iterator *)v37);
        boost::filesystem::path::remove_filename((boost::filesystem::path *)lpPathName);
        v13 = boost::filesystem::path::find_filename_v4_size((boost::filesystem::path *)lpPathName);
        v14 = lpPathName;
        if ( v31 > 7 )
          v14 = (LPCWSTR *)lpPathName[0];
        v15 = (char *)v14 + 2 * (v30 - v13);
        pExceptionObject = 0;
        v42 = 0;
        v43 = 0;
        if ( v15 == &v15[2 * v13] )
        {
          v43 = 7;
          LOWORD(pExceptionObject) = 0;
        }
        else
        {
          std::wstring::_Construct<1,wchar_t *>(&pExceptionObject, v15, (__int64)(2 * v13) >> 1);
        }
        std::wstring::operator=(Block, &pExceptionObject);
        if ( v43 > 7 )
        {
          v16 = (void *)pExceptionObject;
          if ( 2 * v43 + 2 >= 0x1000 )
          {
            if ( (unsigned __int64)(pExceptionObject - *(_QWORD *)(pExceptionObject - 8) - 8) > 0x1F )
              __fastfail(5u);
            v16 = *(void **)(pExceptionObject - 8);
          }
          operator delete(v16);
        }
        if ( !*(_QWORD *)(boost::filesystem::path::find_relative_path(lpPathName, &v32) + 8) )
          goto LABEL_31;
      }
      v19 = v28;
      if ( !a2 )
      {
        v32 = v27;
        v33 = v28;
        boost::filesystem::filesystem_error::filesystem_error(
          &pExceptionObject,
          "boost::filesystem::create_directories",
          (__int64)this,
          (__int64)lpPathName,
          (struct boost::system::error_code *)&v32);
        throw (boost::filesystem::filesystem_error *)&pExceptionObject;
      }
      *(_OWORD *)a2 = v27;
      *((_QWORD *)a2 + 2) = v19;
      if ( v36 > 7 )
      {
        if ( 2 * v36 + 2 < 0x1000 )
        {
          v20 = Block[0];
        }
        else
        {
          v20 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v20);
      }
      v35 = 0;
      v36 = 7;
      LOWORD(Block[0]) = 0;
    }
    else
    {
LABEL_31:
      std::wstring::_Tidy_deallocate(Block);
      v17 = 0;
      while ( 1 )
      {
        if ( v39 == v45 && v40 == v46 )
        {
          std::wstring::_Tidy_deallocate(lpPathName);
          std::wstring::_Tidy_deallocate(v37);
          std::wstring::_Tidy_deallocate(v44);
          return v17;
        }
        boost::filesystem::path::append_v4(
          (boost::filesystem::path *)lpPathName,
          (const struct boost::filesystem::path *)v37);
        if ( v38
          && (unsigned int)boost::filesystem::path::compare_v4((boost::filesystem::path *)v37, v7)
          && (unsigned int)boost::filesystem::path::compare_v4((boost::filesystem::path *)v37, v9) )
        {
          v27 = 0;
          v28 = 0;
          v18 = (const WCHAR *)lpPathName;
          if ( v31 > 7 )
            v18 = lpPathName[0];
          if ( CreateDirectoryW(v18, 0) )
          {
            v17 = 1;
          }
          else
          {
            LastError = GetLastError();
            v32 = 0;
            v33 = 0;
            boost::filesystem::detail::_anonymous_namespace_::status_impl(&v26, lpPathName, &v32);
            if ( (_DWORD)v26 != 3 )
              boost::filesystem::emit_error(
                (boost::filesystem *)LastError,
                (unsigned int)lpPathName,
                (const struct boost::filesystem::path *)&v27,
                (struct boost::system::error_code *)"boost::filesystem::create_directory",
                v25);
            v17 = 0;
          }
          if ( (v28 & 1) != 0 && (v28 != 1 || (_DWORD)v27) )
            break;
        }
        boost::filesystem::path::iterator::increment_v4((boost::filesystem::path::iterator *)v37);
      }
      v23 = v28;
      if ( !a2 )
      {
        v32 = v27;
        v33 = v28;
        boost::filesystem::filesystem_error::filesystem_error(
          &pExceptionObject,
          "boost::filesystem::create_directories",
          (__int64)this,
          (__int64)lpPathName,
          (struct boost::system::error_code *)&v32);
        throw (boost::filesystem::filesystem_error *)&pExceptionObject;
      }
      *(_OWORD *)a2 = v27;
      *((_QWORD *)a2 + 2) = v23;
    }
    std::wstring::_Tidy_deallocate(lpPathName);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v44);
  }
  else
  {
    if ( !a2 )
    {
      error_code = boost::system::errc::make_error_code(Block, 22, a3);
      v32 = *(_OWORD *)error_code;
      v33 = *(_QWORD *)(error_code + 16);
      boost::filesystem::filesystem_error::filesystem_error(
        &pExceptionObject,
        "boost::filesystem::create_directories",
        (__int64)this,
        (const struct boost::system::error_code *)&v32);
      throw (boost::filesystem::filesystem_error *)&pExceptionObject;
    }
    DWORD1(v32) = 0;
    if ( (unsigned __int64)(qword_1400CB2C0 + 0x4D54EE85DA812030LL) <= 1 )
      v5 = 1;
    else
      v5 = ((__int64 (__fastcall *)(void ***, __int64, struct boost::system::error_code *))boost::system::detail::generic_cat_holder<void>::instance[6])(
             &boost::system::detail::generic_cat_holder<void>::instance,
             22,
             a3);
    LODWORD(v32) = 22;
    *((_QWORD *)&v32 + 1) = &boost::system::detail::generic_cat_holder<void>::instance;
    *(_OWORD *)a2 = v32;
    *((_QWORD *)a2 + 2) = v5 + 2LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1400082b0  mov     [rsp-8+arg_10], rbx
0x1400082b5  mov     [rsp-8+arg_18], rsi
0x1400082ba  push    rbp
0x1400082bb  push    rdi
0x1400082bc  push    r12
0x1400082be  push    r14
0x1400082c0  push    r15
0x1400082c2  lea     rbp, [rsp-50h]
0x1400082c7  sub     rsp, 150h
0x1400082ce  mov     rax, cs:__security_cookie
0x1400082d5  xor     rax, rsp
0x1400082d8  mov     [rbp+70h+var_28], rax
0x1400082dc  mov     rdi, rdx
0x1400082df  mov     r15, rcx
0x1400082e2  xor     r12d, r12d
0x1400082e5  cmp     [rcx+10h], r12
0x1400082e9  jnz     short loc_140008358
0x1400082eb  test    rdx, rdx
0x1400082ee  jz      loc_1400087A9
0x1400082f4  mov     dword ptr [rsp+170h+var_100+4], r12d
0x1400082f9  mov     rcx, 4D54EE85DA812030h
0x140008303  add     rcx, cs:qword_1400CB2C0
0x14000830a  lea     rbx, ?instance@?$generic_cat_holder@X@detail@system@boost@@2Vgeneric_error_category@234@B; boost::system::detail::generic_error_category const boost::system::detail::generic_cat_holder<void>::instance
0x140008311  cmp     rcx, 1
0x140008315  jbe     short loc_140008331
0x140008317  mov     rax, cs:?instance@?$generic_cat_holder@X@detail@system@boost@@2Vgeneric_error_category@234@B; boost::system::detail::generic_error_category const boost::system::detail::generic_cat_holder<void>::instance
0x14000831e  mov     edx, 16h
0x140008323  mov     rcx, rbx
0x140008326  mov     rax, [rax+30h]
0x14000832a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000832f  jmp     short loc_140008333
0x140008331  mov     al, 1
0x140008333  movzx   eax, al
0x140008336  add     rax, 2
0x14000833a  mov     dword ptr [rsp+170h+var_100], 16h
0x140008342  mov     qword ptr [rsp+170h+var_100+8], rbx
0x140008347  movups  xmm0, [rsp+170h+var_100]
0x14000834c  movups  xmmword ptr [rdi], xmm0
0x14000834f  mov     [rdi+10h], rax
0x140008353  jmp     loc_140008742
0x140008358  test    rdi, rdi
0x14000835b  jz      short loc_140008367
0x14000835d  xorps   xmm0, xmm0
0x140008360  movups  xmmword ptr [rdx], xmm0
0x140008363  mov     [rdx+10h], r12
0x140008367  lea     rdx, [rbp+70h+var_58]
0x14000836b  call    ?end@path@filesystem@boost@@QEBA?AViterator@123@XZ; boost::filesystem::path::end(void)
0x140008370  nop
0x140008371  lea     rdx, [rbp+70h+var_58]
0x140008375  lea     rcx, [rbp+70h+var_C0]
0x140008379  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000837e  mov     rax, [rbp+70h+var_38]
0x140008382  mov     [rbp+70h+var_A0], rax
0x140008386  mov     rax, [rbp+70h+var_30]
0x14000838a  mov     [rbp+70h+var_98], rax
0x14000838e  mov     rdx, r15
0x140008391  lea     rcx, [rsp+170h+lpPathName]
0x140008396  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000839b  nop
0x14000839c  call    ?dot_path@detail@filesystem@boost@@YAAEBVpath@23@XZ; boost::filesystem::detail::dot_path(void)
0x1400083a1  mov     rsi, rax
0x1400083a4  call    ?dot_dot_path@detail@filesystem@boost@@YAAEBVpath@23@XZ; boost::filesystem::detail::dot_dot_path(void)
0x1400083a9  mov     r14, rax
0x1400083ac  xorps   xmm0, xmm0
0x1400083af  movups  [rsp+170h+var_138], xmm0
0x1400083b4  mov     [rsp+170h+var_128], r12
0x1400083b9  lea     rcx, [rsp+170h+lpPathName]; this
0x1400083be  call    ?find_filename_v4_size@path@filesystem@boost@@AEBA_KXZ; boost::filesystem::path::find_filename_v4_size(void)
0x1400083c3  mov     rdx, [rsp+170h+var_110]
0x1400083c8  sub     rdx, rax
0x1400083cb  lea     rcx, [rsp+170h+lpPathName]
0x1400083d0  cmp     [rsp+170h+var_108], 7
0x1400083d6  cmova   rcx, [rsp+170h+lpPathName]
0x1400083dc  lea     rdx, [rcx+rdx*2]
0x1400083e0  lea     r8, [rax+rax]
0x1400083e4  xorps   xmm0, xmm0
0x1400083e7  movups  xmmword ptr [rbp+70h+Block], xmm0
0x1400083eb  mov     [rbp+70h+var_D0], r12
0x1400083ef  mov     [rbp+70h+var_C8], r12
0x1400083f3  lea     rax, [r8+rdx]
0x1400083f7  cmp     rdx, rax
0x1400083fa  jnz     short loc_14000840F
0x1400083fc  mov     [rbp+70h+var_D0], r12
0x140008400  mov     [rbp+70h+var_C8], 7
0x140008408  mov     word ptr [rbp+70h+Block], r12w
0x14000840d  jmp     short loc_14000841C
0x14000840f  sar     r8, 1
0x140008412  lea     rcx, [rbp+70h+Block]
0x140008416  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14000841b  nop
0x14000841c  lea     rdx, [rsp+170h+var_100]
0x140008421  lea     rcx, [rsp+170h+lpPathName]
0x140008426  call    ?find_relative_path@path@filesystem@boost@@AEBA?AUsubstring@path_detail@23@XZ; boost::filesystem::path::find_relative_path(void)
0x14000842b  cmp     qword ptr [rax+8], 0
0x140008430  jbe     loc_14000855F
0x140008436  cmp     [rbp+70h+var_D0], 0
0x14000843b  jz      short loc_140008487
0x14000843d  mov     rdx, rsi; struct boost::filesystem::path *
0x140008440  lea     rcx, [rbp+70h+Block]; this
0x140008444  call    ?compare_v4@path@filesystem@boost@@AEBAHAEBV123@@Z; boost::filesystem::path::compare_v4(boost::filesystem::path const &)
0x140008449  test    eax, eax
0x14000844b  jz      short loc_140008487
0x14000844d  mov     rdx, r14; struct boost::filesystem::path *
0x140008450  lea     rcx, [rbp+70h+Block]; this
0x140008454  call    ?compare_v4@path@filesystem@boost@@AEBAHAEBV123@@Z; boost::filesystem::path::compare_v4(boost::filesystem::path const &)
0x140008459  test    eax, eax
0x14000845b  jz      short loc_140008487
0x14000845d  lea     r8, [rsp+170h+var_138]
0x140008462  lea     rdx, [rsp+170h+lpPathName]
0x140008467  lea     rcx, [rsp+170h+var_140]
0x14000846c  call    boost__filesystem__detail___anonymous_namespace___status_impl
0x140008471  mov     rax, [rsp+170h+var_140]
0x140008476  cmp     eax, 3
0x140008479  jz      loc_14000855F
0x14000847f  test    eax, eax
0x140008481  jz      loc_1400085FE
0x140008487  lea     rcx, [rbp+70h+var_C0]; this
0x14000848b  call    ?decrement_v4@iterator@path@filesystem@boost@@AEAAXXZ; boost::filesystem::path::iterator::decrement_v4(void)
0x140008490  lea     rcx, [rsp+170h+lpPathName]; this
0x140008495  call    ?remove_filename@path@filesystem@boost@@QEAAAEAV123@XZ; boost::filesystem::path::remove_filename(void)
0x14000849a  lea     rcx, [rsp+170h+lpPathName]; this
0x14000849f  call    ?find_filename_v4_size@path@filesystem@boost@@AEBA_KXZ; boost::filesystem::path::find_filename_v4_size(void)
0x1400084a4  mov     rdx, [rsp+170h+var_110]
0x1400084a9  sub     rdx, rax
0x1400084ac  lea     rcx, [rsp+170h+lpPathName]
0x1400084b1  cmp     [rsp+170h+var_108], 7
0x1400084b7  cmova   rcx, [rsp+170h+lpPathName]
0x1400084bd  lea     rdx, [rcx+rdx*2]
0x1400084c1  lea     r8, [rax+rax]
0x1400084c5  xorps   xmm0, xmm0
0x1400084c8  movups  [rbp+70h+pExceptionObject], xmm0
0x1400084cc  mov     [rbp+70h+var_80], r12
0x1400084d0  mov     [rbp+70h+var_78], r12
0x1400084d4  lea     rax, [r8+rdx]
0x1400084d8  cmp     rdx, rax
0x1400084db  jnz     short loc_1400084EC
0x1400084dd  mov     [rbp+70h+var_78], 7
0x1400084e5  mov     word ptr [rbp+70h+pExceptionObject], r12w
0x1400084ea  jmp     short loc_1400084F8
0x1400084ec  sar     r8, 1
0x1400084ef  lea     rcx, [rbp+70h+pExceptionObject]
0x1400084f3  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400084f8  lea     rdx, [rbp+70h+pExceptionObject]
0x1400084fc  lea     rcx, [rbp+70h+Block]
0x140008500  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140008505  mov     rdx, [rbp+70h+var_78]
0x140008509  cmp     rdx, 7
0x14000850d  jbe     short loc_140008545
0x14000850f  lea     rdx, ds:2[rdx*2]
0x140008517  mov     rcx, qword ptr [rbp+70h+pExceptionObject]
0x14000851b  cmp     rdx, 1000h
0x140008522  jb      short loc_140008540
0x140008524  mov     rax, [rcx-8]
0x140008528  sub     rcx, rax
0x14000852b  sub     rcx, 8
0x14000852f  cmp     rcx, 1Fh
0x140008533  ja      loc_140008675
0x140008539  add     rdx, 27h ; '''
0x14000853d  mov     rcx, rax; Block
0x140008540  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008545  lea     rdx, [rsp+170h+var_100]
0x14000854a  lea     rcx, [rsp+170h+lpPathName]
0x14000854f  call    ?find_relative_path@path@filesystem@boost@@AEBA?AUsubstring@path_detail@23@XZ; boost::filesystem::path::find_relative_path(void)
0x140008554  cmp     qword ptr [rax+8], 0
0x140008559  ja      loc_140008436
0x14000855f  lea     rcx, [rbp+70h+Block]
0x140008563  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008568  xor     bl, bl
0x14000856a  nop     word ptr [rax+rax+00h]
0x140008570  mov     rax, [rbp+70h+var_38]
0x140008574  cmp     [rbp+70h+var_A0], rax
0x140008578  jnz     short loc_140008588
0x14000857a  mov     rax, [rbp+70h+var_30]
0x14000857e  cmp     [rbp+70h+var_98], rax
0x140008582  jz      loc_1400086E9
0x140008588  lea     rdx, [rbp+70h+var_C0]; struct boost::filesystem::path *
0x14000858c  lea     rcx, [rsp+170h+lpPathName]; this
0x140008591  call    ?append_v4@path@filesystem@boost@@AEAAXAEBV123@@Z; boost::filesystem::path::append_v4(boost::filesystem::path const &)
0x140008596  cmp     [rbp+70h+var_B0], 0
0x14000859b  jz      loc_1400086DB
0x1400085a1  mov     rdx, rsi; struct boost::filesystem::path *
0x1400085a4  lea     rcx, [rbp+70h+var_C0]; this
0x1400085a8  call    ?compare_v4@path@filesystem@boost@@AEBAHAEBV123@@Z; boost::filesystem::path::compare_v4(boost::filesystem::path const &)
0x1400085ad  test    eax, eax
0x1400085af  jz      loc_1400086DB
0x1400085b5  mov     rdx, r14; struct boost::filesystem::path *
0x1400085b8  lea     rcx, [rbp+70h+var_C0]; this
0x1400085bc  call    ?compare_v4@path@filesystem@boost@@AEBAHAEBV123@@Z; boost::filesystem::path::compare_v4(boost::filesystem::path const &)
0x1400085c1  test    eax, eax
0x1400085c3  jz      loc_1400086DB
0x1400085c9  xorps   xmm0, xmm0
0x1400085cc  movups  [rsp+170h+var_138], xmm0
0x1400085d1  mov     [rsp+170h+var_128], r12
0x1400085d6  lea     rcx, [rsp+170h+lpPathName]
0x1400085db  cmp     [rsp+170h+var_108], 7
0x1400085e1  cmova   rcx, [rsp+170h+lpPathName]; lpPathName
0x1400085e7  xor     edx, edx; lpSecurityAttributes
0x1400085e9  call    cs:__imp_CreateDirectoryW
0x1400085ef  test    eax, eax
0x1400085f1  jz      loc_14000867C
0x1400085f7  mov     bl, 1
0x1400085f9  jmp     loc_1400086C5
0x1400085fe  movups  xmm0, [rsp+170h+var_138]
0x140008603  movsd   xmm1, [rsp+170h+var_128]
0x140008609  test    rdi, rdi
0x14000860c  jz      loc_1400087F2
0x140008612  movups  xmmword ptr [rdi], xmm0
0x140008615  movsd   qword ptr [rdi+10h], xmm1
0x14000861a  mov     rdx, [rbp+70h+var_C8]
0x14000861e  cmp     rdx, 7
0x140008622  jbe     short loc_14000865F
0x140008624  mov     rax, [rbp+70h+Block]
0x140008628  lea     rdx, ds:2[rdx*2]
0x140008630  cmp     rdx, 1000h
0x140008637  jb      short loc_140008657
0x140008639  mov     rcx, [rax-8]
0x14000863d  sub     rax, rcx
0x140008640  sub     rax, 8
0x140008644  cmp     rax, 1Fh
0x140008648  ja      short loc_140008650
0x14000864a  add     rdx, 27h ; '''
0x14000864e  jmp     short loc_14000865A
0x140008650  mov     ecx, 5
0x140008655  int     29h; Win8: RtlFailFast(ecx)
0x140008657  mov     rcx, rax; Block
0x14000865a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000865f  mov     [rbp+70h+var_D0], r12
0x140008663  mov     [rbp+70h+var_C8], 7
0x14000866b  mov     word ptr [rbp+70h+Block], r12w
0x140008670  jmp     loc_140008724
0x140008675  mov     ecx, 5
0x14000867a  int     29h; Win8: RtlFailFast(ecx)
0x14000867c  call    cs:__imp_GetLastError
0x140008682  mov     ebx, eax
0x140008684  xorps   xmm0, xmm0
0x140008687  movups  [rsp+170h+var_100], xmm0
0x14000868c  mov     [rbp+70h+var_F0], r12
0x140008690  lea     r8, [rsp+170h+var_100]
0x140008695  lea     rdx, [rsp+170h+lpPathName]
0x14000869a  lea     rcx, [rsp+170h+var_140]
0x14000869f  call    boost__filesystem__detail___anonymous_namespace___status_impl
0x1400086a4  cmp     dword ptr [rsp+170h+var_140], 3
0x1400086a9  jz      short loc_1400086C3
0x1400086ab  lea     r9, aBoostFilesyste_2; "boost::filesystem::create_directory"
0x1400086b2  lea     r8, [rsp+170h+var_138]; struct boost::filesystem::path *
0x1400086b7  lea     rdx, [rsp+170h+lpPathName]; unsigned int
0x1400086bc  mov     ecx, ebx; this
0x1400086be  call    ?emit_error@filesystem@boost@@YAXKAEBVpath@12@PEAVerror_code@system@2@PEBD@Z; boost::filesystem::emit_error(ulong,boost::filesystem::path const &,boost::system::error_code *,char const *)
0x1400086c3  xor     bl, bl
0x1400086c5  test    byte ptr [rsp+170h+var_128], 1
0x1400086ca  jz      short loc_1400086DB
0x1400086cc  cmp     [rsp+170h+var_128], 1
0x1400086d2  jnz     short loc_14000870C
0x1400086d4  cmp     dword ptr [rsp+170h+var_138], 0
0x1400086d9  jnz     short loc_14000870C
0x1400086db  lea     rcx, [rbp+70h+var_C0]; this
0x1400086df  call    ?increment_v4@iterator@path@filesystem@boost@@AEAAXXZ; boost::filesystem::path::iterator::increment_v4(void)
0x1400086e4  jmp     loc_140008570
0x1400086e9  lea     rcx, [rsp+170h+lpPathName]
0x1400086ee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400086f3  nop
0x1400086f4  lea     rcx, [rbp+70h+var_C0]
0x1400086f8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400086fd  nop
0x1400086fe  lea     rcx, [rbp+70h+var_58]
0x140008702  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008707  movzx   eax, bl
0x14000870a  jmp     short loc_140008744
0x14000870c  movups  xmm0, [rsp+170h+var_138]
0x140008711  movsd   xmm1, [rsp+170h+var_128]
0x140008717  test    rdi, rdi
0x14000871a  jz      short loc_14000876C
0x14000871c  movups  xmmword ptr [rdi], xmm0
0x14000871f  movsd   qword ptr [rdi+10h], xmm1
0x140008724  lea     rcx, [rsp+170h+lpPathName]
0x140008729  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000872e  nop
0x14000872f  lea     rcx, [rbp+70h+var_C0]
0x140008733  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008738  nop
0x140008739  lea     rcx, [rbp+70h+var_58]
0x14000873d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008742  xor     al, al
0x140008744  mov     rcx, [rbp+70h+var_28]
0x140008748  xor     rcx, rsp; StackCookie
0x14000874b  call    __security_check_cookie
0x140008750  lea     r11, [rsp+170h+var_20]
0x140008758  mov     rbx, [r11+40h]
0x14000875c  mov     rsi, [r11+48h]
0x140008760  mov     rsp, r11
0x140008763  pop     r15
0x140008765  pop     r14
0x140008767  pop     r12
0x140008769  pop     rdi
0x14000876a  pop     rbp
0x14000876b  retn
0x14000876c  movaps  [rsp+170h+var_100], xmm0
0x140008771  movsd   [rbp+70h+var_F0], xmm1
0x140008776  lea     rax, [rsp+170h+var_100]
0x14000877b  mov     [rsp+170h+var_150], rax
  ... truncated ...
```
