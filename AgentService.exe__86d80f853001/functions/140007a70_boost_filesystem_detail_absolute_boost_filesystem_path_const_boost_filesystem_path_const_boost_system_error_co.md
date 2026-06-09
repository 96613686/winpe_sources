# boost::filesystem::detail::absolute(boost::filesystem::path const &,boost::filesystem::path const &,boost::system::error_code *)

- ea: `0x140007a70`
- end: `0x140008117`
- name: `?absolute@detail@filesystem@boost@@YA?AVpath@23@AEBV423@0PEAVerror_code@system@3@@Z`
- size: `1703`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x140007a70`
- `0x140008120`
- `0x14008b514`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004f20`
- `0x140006380`
- `0x140006410`
- `0x140006640`
- `0x140007450`
- `0x140007a70`
- `0x140008120`
- `0x140008d00`
- `0x140008db0`
- `0x14000ac03`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x14008cfb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140007c14`
- `KERNEL32!GetLastError` at `0x140007c14`
- `KERNEL32!GetCurrentDirectoryW` at `0x140007bcf`
- `KERNEL32!GetCurrentDirectoryW` at `0x140007c0a`
- `KERNEL32!GetCurrentDirectoryW` at `0x140007bcf`
- `KERNEL32!GetCurrentDirectoryW` at `0x140007c0a`

## string_xrefs

- `0x140007c1e`: `boost::filesystem::current_path`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall boost::filesystem::detail::absolute(
        __int64 a1,
        boost::filesystem::path *a2,
        boost::filesystem::path *a3,
        __int64 a4)
{
  __int64 v8; // r14
  void *v9; // rax
  __int64 v10; // rax
  DWORD CurrentDirectoryW; // ebx
  WCHAR *v12; // r15
  DWORD LastError; // eax
  const char *v14; // r9
  size_t v15; // rax
  void *v16; // rcx
  void *v17; // rcx
  void **v18; // r14
  void **v19; // rbx
  void **v20; // rcx
  void **v21; // r8
  void *v22; // rcx
  __int64 v23; // rax
  const void *v24; // rdx
  void **v25; // rcx
  char *v26; // rdx
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // rcx
  void **v29; // rdx
  void *v30; // rcx
  void **v31; // rcx
  char *v32; // rdx
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  void *v37[2]; // [rsp+28h] [rbp-91h] BYREF
  __int128 v38; // [rsp+38h] [rbp-81h]
  void *Block[2]; // [rsp+48h] [rbp-71h] BYREF
  __int128 v40; // [rsp+58h] [rbp-61h]
  void *Src[2]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v42; // [rsp+78h] [rbp-41h]
  __int64 v43; // [rsp+88h] [rbp-31h] BYREF
  __int64 v44; // [rsp+90h] [rbp-29h]
  void *v45[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-11h]
  unsigned __int64 v47; // [rsp+B0h] [rbp-9h]
  _BYTE v48[16]; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v49; // [rsp+C8h] [rbp+Fh]

  v43 = a1;
  if ( a4 )
  {
    *(_OWORD *)a4 = 0;
    *(_QWORD *)(a4 + 16) = 0;
  }
  if ( boost::filesystem::path::is_absolute(a2) )
  {
    std::wstring::wstring(a1, (__int64)a2);
    return a1;
  }
  std::wstring::wstring((__int64)Block, (__int64)a3);
  if ( !boost::filesystem::path::is_absolute(a3) )
  {
    if ( a4 )
    {
      v8 = boost::filesystem::absolute(v45, a3, a4);
      if ( Block != (void **)v8 )
      {
        if ( *((_QWORD *)&v40 + 1) > 7u )
        {
          if ( (unsigned __int64)(2LL * *((_QWORD *)&v40 + 1) + 2) < 0x1000 )
          {
            v9 = Block[0];
          }
          else
          {
            v9 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
              goto LABEL_90;
          }
          operator delete(v9);
        }
        *(_QWORD *)&v40 = 0;
        *((_QWORD *)&v40 + 1) = 7;
        LOWORD(Block[0]) = 0;
        *(_OWORD *)Block = *(_OWORD *)v8;
        v40 = *(_OWORD *)(v8 + 16);
        *(_QWORD *)(v8 + 16) = 0;
        *(_QWORD *)(v8 + 24) = 7;
        *(_WORD *)v8 = 0;
      }
      std::wstring::_Tidy_deallocate(v45);
      v10 = *(_QWORD *)(a4 + 16);
      if ( (v10 & 1) != 0 && (v10 != 1 || *(_DWORD *)a4) )
      {
        *(_OWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 7;
        *(_WORD *)a1 = 0;
        goto LABEL_94;
      }
    }
    else
    {
      CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
      if ( !CurrentDirectoryW )
        CurrentDirectoryW = 1;
      v12 = (WCHAR *)operator new[](saturated_mul(CurrentDirectoryW, 2u));
      v43 = (__int64)v12;
      if ( !GetCurrentDirectoryW(CurrentDirectoryW, v12) )
      {
        LastError = GetLastError();
        if ( LastError )
          boost::filesystem::emit_error(
            (boost::filesystem *)LastError,
            0,
            (struct boost::system::error_code *)"boost::filesystem::current_path",
            v14);
      }
      *(_OWORD *)v45 = 0;
      v46 = 0;
      v47 = 0;
      v15 = wcslen_0(v12);
      std::wstring::_Construct<1,wchar_t *>(v45, v12, v15);
      operator delete(v12);
      boost::filesystem::detail::absolute(v37, a3, v45, 0);
      if ( *((_QWORD *)&v40 + 1) > 7u )
      {
        if ( (unsigned __int64)(2LL * *((_QWORD *)&v40 + 1) + 2) < 0x1000 )
        {
          v16 = Block[0];
        }
        else
        {
          v16 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v16 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v16);
      }
      *(_OWORD *)Block = *(_OWORD *)v37;
      v40 = v38;
      *(_QWORD *)&v38 = 0;
      *((_QWORD *)&v38 + 1) = 7;
      LOWORD(v37[0]) = 0;
      std::wstring::_Tidy_deallocate(v37);
      if ( v47 > 7 )
      {
        if ( 2 * v47 + 2 < 0x1000 )
        {
          v17 = v45[0];
        }
        else
        {
          v17 = (void *)*((_QWORD *)v45[0] - 1);
          if ( (unsigned __int64)((char *)v45[0] - (char *)v17 - 8) > 0x1F )
            goto LABEL_90;
        }
        operator delete(v17);
      }
    }
  }
  if ( !*((_QWORD *)a2 + 2) )
  {
    *(_OWORD *)a1 = *(_OWORD *)Block;
    *(_OWORD *)(a1 + 16) = v40;
    return a1;
  }
  *(_OWORD *)Src = 0;
  *(_QWORD *)&v42 = 0;
  *((_QWORD *)&v42 + 1) = 7;
  LOWORD(Src[0]) = 0;
  if ( boost::filesystem::path::find_root_name_size(a2) )
  {
    v18 = (void **)a2;
    if ( *((_QWORD *)a2 + 3) <= 7u )
    {
      v19 = (void **)a2;
    }
    else
    {
      v18 = *(void ***)a2;
      v19 = *(void ***)a2;
    }
    v20 = (void **)a2;
  }
  else
  {
    if ( *((_QWORD *)&v40 + 1) <= 7u )
    {
      v18 = Block;
      v19 = Block;
    }
    else
    {
      v19 = (void **)Block[0];
      v18 = (void **)Block[0];
    }
    v20 = Block;
  }
  v21 = (void **)((char *)v18 + 2 * boost::filesystem::path::find_root_name_size((boost::filesystem::path *)v20));
  *(_OWORD *)v37 = 0;
  v38 = 0u;
  if ( v19 == v21 )
  {
    *((_QWORD *)&v38 + 1) = 7;
    LOWORD(v37[0]) = 0;
  }
  else
  {
    std::wstring::_Construct<1,wchar_t *>(v37, v19, ((char *)v21 - (char *)v19) >> 1);
  }
  if ( *((_QWORD *)&v42 + 1) > 7u )
  {
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v42 + 1) + 2) < 0x1000 )
    {
      v22 = Src[0];
    }
    else
    {
      v22 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v22 - 8) > 0x1F )
        goto LABEL_82;
    }
    operator delete(v22);
  }
  v42 = v38;
  *(_OWORD *)Src = *(_OWORD *)v37;
  if ( *(_QWORD *)(boost::filesystem::path::find_root_directory(a2, &v43) + 8) )
  {
    v23 = boost::filesystem::path::root_directory(a2, v45);
    if ( *(_QWORD *)(v23 + 24) <= 7u )
      v24 = (const void *)v23;
    else
      v24 = *(const void **)v23;
    std::wstring::_Append<wchar_t>(Src, v24, *(_QWORD *)(v23 + 16));
    std::wstring::_Tidy_deallocate(v45);
    goto LABEL_85;
  }
  boost::filesystem::path::find_root_directory(Block, &v43);
  v25 = Block;
  if ( *((_QWORD *)&v40 + 1) > 7u )
    v25 = (void **)Block[0];
  v26 = (char *)v25 + 2 * v43;
  *(_OWORD *)v37 = 0;
  v38 = 0u;
  if ( v26 == &v26[2 * v44] )
  {
    v27 = 0;
    *(_QWORD *)&v38 = 0;
    v28 = 7;
    *((_QWORD *)&v38 + 1) = 7;
    LOWORD(v37[0]) = 0;
  }
  else
  {
    std::wstring::_Construct<1,wchar_t *>(v37, v26, (2 * v44) >> 1);
    v28 = *((_QWORD *)&v38 + 1);
    v27 = v38;
  }
  v29 = v37;
  if ( v28 > 7 )
    v29 = (void **)v37[0];
  std::wstring::_Append<wchar_t>(Src, v29, v27);
  if ( *((_QWORD *)&v38 + 1) > 7u )
  {
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v38 + 1) + 2) < 0x1000 )
    {
      v30 = v37[0];
    }
    else
    {
      v30 = (void *)*((_QWORD *)v37[0] - 1);
      if ( (unsigned __int64)((char *)v37[0] - (char *)v30 - 8) > 0x1F )
        goto LABEL_82;
    }
    operator delete(v30);
  }
  boost::filesystem::path::find_relative_path(Block, &v43);
  v31 = Block;
  if ( *((_QWORD *)&v40 + 1) > 7u )
    v31 = (void **)Block[0];
  v32 = (char *)v31 + 2 * v43;
  *(_OWORD *)v37 = 0;
  v38 = 0u;
  if ( v32 == &v32[2 * v44] )
  {
    *(_QWORD *)&v38 = 0;
    *((_QWORD *)&v38 + 1) = 7;
    LOWORD(v37[0]) = 0;
  }
  else
  {
    std::wstring::_Construct<1,wchar_t *>(v37, v32, (2 * v44) >> 1);
  }
  boost::filesystem::path::append_v4((boost::filesystem::path *)Src, (const struct boost::filesystem::path *)v37);
  if ( *((_QWORD *)&v38 + 1) > 7u )
  {
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v38 + 1) + 2) < 0x1000 )
    {
      v33 = v37[0];
    }
    else
    {
      v33 = (void *)*((_QWORD *)v37[0] - 1);
      if ( (unsigned __int64)((char *)v37[0] - (char *)v33 - 8) > 0x1F )
LABEL_82:
        __fastfail(5u);
    }
    operator delete(v33);
  }
LABEL_85:
  boost::filesystem::path::relative_path(a2, v48);
  if ( v49 )
    boost::filesystem::path::append_v4((boost::filesystem::path *)Src, (const struct boost::filesystem::path *)v48);
  *(_OWORD *)a1 = *(_OWORD *)Src;
  *(_OWORD *)(a1 + 16) = v42;
  *(_QWORD *)&v42 = 0;
  *((_QWORD *)&v42 + 1) = 7;
  LOWORD(Src[0]) = 0;
  std::wstring::_Tidy_deallocate(v48);
  if ( *((_QWORD *)&v42 + 1) > 7u )
  {
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v42 + 1) + 2) < 0x1000 )
    {
      v34 = Src[0];
    }
    else
    {
      v34 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v34 - 8) > 0x1F )
LABEL_90:
        __fastfail(5u);
    }
    operator delete(v34);
  }
  *(_QWORD *)&v42 = 0;
  *((_QWORD *)&v42 + 1) = 7;
  LOWORD(Src[0]) = 0;
LABEL_94:
  if ( *((_QWORD *)&v40 + 1) > 7u )
  {
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v40 + 1) + 2) < 0x1000 )
    {
      v35 = Block[0];
    }
    else
    {
      v35 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v35 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v35);
  }
  return a1;
}

```

## disassembly

```asm
0x140007a70  push    rbp
0x140007a72  push    rbx
0x140007a73  push    rsi
0x140007a74  push    rdi
0x140007a75  push    r12
0x140007a77  push    r14
0x140007a79  push    r15
0x140007a7b  lea     rbp, [rsp-27h]
0x140007a80  sub     rsp, 0E0h
0x140007a87  mov     rax, cs:__security_cookie
0x140007a8e  xor     rax, rsp
0x140007a91  mov     [rbp+57h+var_38], rax
0x140007a95  mov     rbx, r9
0x140007a98  mov     r14, r8
0x140007a9b  mov     rsi, rdx
0x140007a9e  mov     rdi, rcx
0x140007aa1  mov     [rbp+57h+var_88], rcx
0x140007aa5  xor     r12d, r12d
0x140007aa8  test    r9, r9
0x140007aab  jz      short loc_140007AB8
0x140007aad  xorps   xmm0, xmm0
0x140007ab0  movups  xmmword ptr [r9], xmm0
0x140007ab4  mov     [r9+10h], r12
0x140007ab8  mov     rcx, rsi; this
0x140007abb  call    ?is_absolute@path@filesystem@boost@@QEBA_NXZ; boost::filesystem::path::is_absolute(void)
0x140007ac0  test    al, al
0x140007ac2  jz      short loc_140007AD4
0x140007ac4  mov     rdx, rsi
0x140007ac7  mov     rcx, rdi
0x140007aca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140007acf  jmp     loc_1400080F6
0x140007ad4  mov     rdx, r14
0x140007ad7  lea     rcx, [rbp+57h+Block]
0x140007adb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140007ae0  nop
0x140007ae1  mov     rcx, r14; this
0x140007ae4  call    ?is_absolute@path@filesystem@boost@@QEBA_NXZ; boost::filesystem::path::is_absolute(void)
0x140007ae9  test    al, al
0x140007aeb  jnz     loc_140007D29
0x140007af1  test    rbx, rbx
0x140007af4  jz      loc_140007BCB
0x140007afa  mov     r8, rbx
0x140007afd  mov     rdx, r14
0x140007b00  lea     rcx, [rbp+57h+var_78]
0x140007b04  call    ?absolute@filesystem@boost@@YA?AVpath@12@AEBV312@AEAVerror_code@system@2@@Z; boost::filesystem::absolute(boost::filesystem::path const &,boost::system::error_code &)
0x140007b09  mov     r14, rax
0x140007b0c  lea     rax, [rbp+57h+Block]
0x140007b10  cmp     rax, r14
0x140007b13  jz      short loc_140007B8C
0x140007b15  mov     rdx, qword ptr [rbp+57h+var_B8+8]
0x140007b19  cmp     rdx, 7
0x140007b1d  jbe     short loc_140007B5A
0x140007b1f  mov     rcx, [rbp+57h+Block]
0x140007b23  lea     rdx, ds:2[rdx*2]
0x140007b2b  cmp     rdx, 1000h
0x140007b32  jb      short loc_140007B4F
0x140007b34  mov     rax, [rcx-8]
0x140007b38  sub     rcx, rax
0x140007b3b  sub     rcx, 8
0x140007b3f  cmp     rcx, 1Fh
0x140007b43  ja      loc_140008091
0x140007b49  add     rdx, 27h ; '''
0x140007b4d  jmp     short loc_140007B52
0x140007b4f  mov     rax, rcx
0x140007b52  mov     rcx, rax; Block
0x140007b55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007b5a  mov     qword ptr [rbp+57h+var_B8], r12
0x140007b5e  mov     qword ptr [rbp+57h+var_B8+8], 7
0x140007b66  mov     word ptr [rbp+57h+Block], r12w
0x140007b6b  movups  xmm0, xmmword ptr [r14]
0x140007b6f  movups  xmmword ptr [rbp+57h+Block], xmm0
0x140007b73  movups  xmm1, xmmword ptr [r14+10h]
0x140007b78  movups  [rbp+57h+var_B8], xmm1
0x140007b7c  mov     [r14+10h], r12
0x140007b80  mov     qword ptr [r14+18h], 7
0x140007b88  mov     [r14], r12w
0x140007b8c  lea     rcx, [rbp+57h+var_78]
0x140007b90  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140007b95  mov     rax, [rbx+10h]
0x140007b99  test    al, 1
0x140007b9b  jz      loc_140007D29
0x140007ba1  cmp     rax, 1
0x140007ba5  jnz     short loc_140007BB0
0x140007ba7  cmp     dword ptr [rbx], 0
0x140007baa  jz      loc_140007D29
0x140007bb0  xorps   xmm0, xmm0
0x140007bb3  movups  xmmword ptr [rdi], xmm0
0x140007bb6  mov     [rdi+10h], r12
0x140007bba  mov     qword ptr [rdi+18h], 7
0x140007bc2  mov     [rdi], r12w
0x140007bc6  jmp     loc_1400080B1
0x140007bcb  xor     edx, edx; lpBuffer
0x140007bcd  xor     ecx, ecx; nBufferLength
0x140007bcf  call    cs:__imp_GetCurrentDirectoryW
0x140007bd5  mov     ebx, eax
0x140007bd7  mov     eax, 1
0x140007bdc  test    ebx, ebx
0x140007bde  cmovz   ebx, eax
0x140007be1  mov     edx, ebx
0x140007be3  mov     eax, 2
0x140007be8  mul     rdx
0x140007beb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140007bf2  cmovb   rax, rcx
0x140007bf6  mov     rcx, rax; unsigned __int64
0x140007bf9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140007bfe  mov     r15, rax
0x140007c01  mov     [rbp+57h+var_88], rax
0x140007c05  mov     rdx, rax; lpBuffer
0x140007c08  mov     ecx, ebx; nBufferLength
0x140007c0a  call    cs:__imp_GetCurrentDirectoryW
0x140007c10  test    eax, eax
0x140007c12  jnz     short loc_140007C2E
0x140007c14  call    cs:__imp_GetLastError
0x140007c1a  test    eax, eax
0x140007c1c  jz      short loc_140007C2E
0x140007c1e  lea     r8, aBoostFilesyste; "boost::filesystem::current_path"
0x140007c25  xor     edx, edx; unsigned int
0x140007c27  mov     ecx, eax; this
0x140007c29  call    ?emit_error@filesystem@boost@@YAXKPEAVerror_code@system@2@PEBD@Z; boost::filesystem::emit_error(ulong,boost::system::error_code *,char const *)
0x140007c2e  xorps   xmm0, xmm0
0x140007c31  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140007c35  mov     [rbp+57h+var_68], r12
0x140007c39  mov     [rbp+57h+var_60], r12
0x140007c3d  mov     rcx, r15; String
0x140007c40  call    wcslen_0
0x140007c45  mov     r8, rax
0x140007c48  mov     rdx, r15
0x140007c4b  lea     rcx, [rbp+57h+var_78]
0x140007c4f  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140007c54  nop
0x140007c55  mov     rcx, r15; Block
0x140007c58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007c5d  nop
0x140007c5e  xor     r9d, r9d
0x140007c61  lea     r8, [rbp+57h+var_78]
0x140007c65  mov     rdx, r14
0x140007c68  lea     rcx, [rsp+110h+var_E8]
0x140007c6d  call    ?absolute@detail@filesystem@boost@@YA?AVpath@23@AEBV423@0PEAVerror_code@system@3@@Z; boost::filesystem::detail::absolute(boost::filesystem::path const &,boost::filesystem::path const &,boost::system::error_code *)
0x140007c72  mov     rdx, qword ptr [rbp+57h+var_B8+8]
0x140007c76  cmp     rdx, 7
0x140007c7a  jbe     short loc_140007CB7
0x140007c7c  mov     rax, [rbp+57h+Block]
0x140007c80  lea     rdx, ds:2[rdx*2]
0x140007c88  cmp     rdx, 1000h
0x140007c8f  jb      short loc_140007CAF
0x140007c91  mov     rcx, [rax-8]
0x140007c95  sub     rax, rcx
0x140007c98  sub     rax, 8
0x140007c9c  cmp     rax, 1Fh
0x140007ca0  ja      short loc_140007CA8
0x140007ca2  add     rdx, 27h ; '''
0x140007ca6  jmp     short loc_140007CB2
0x140007ca8  mov     ecx, 5
0x140007cad  int     29h; Win8: RtlFailFast(ecx)
0x140007caf  mov     rcx, rax; Block
0x140007cb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007cb7  movups  xmm0, xmmword ptr [rsp+110h+var_E8]
0x140007cbc  movups  xmmword ptr [rbp+57h+Block], xmm0
0x140007cc0  movups  xmm1, [rsp+110h+var_D8]
0x140007cc5  movups  [rbp+57h+var_B8], xmm1
0x140007cc9  mov     qword ptr [rsp+110h+var_D8], r12
0x140007cce  mov     qword ptr [rbp+57h+var_D8+8], 7
0x140007cd6  mov     word ptr [rsp+110h+var_E8], r12w
0x140007cdc  lea     rcx, [rsp+110h+var_E8]
0x140007ce1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140007ce6  nop
0x140007ce7  mov     rdx, [rbp+57h+var_60]
0x140007ceb  cmp     rdx, 7
0x140007cef  jbe     short loc_140007D29
0x140007cf1  mov     rax, [rbp+57h+var_78]
0x140007cf5  lea     rdx, ds:2[rdx*2]
0x140007cfd  cmp     rdx, 1000h
0x140007d04  jb      short loc_140007D21
0x140007d06  mov     rcx, [rax-8]
0x140007d0a  sub     rax, rcx
0x140007d0d  sub     rax, 8
0x140007d11  cmp     rax, 1Fh
0x140007d15  ja      loc_140008091
0x140007d1b  add     rdx, 27h ; '''
0x140007d1f  jmp     short loc_140007D24
0x140007d21  mov     rcx, rax; Block
0x140007d24  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007d29  cmp     qword ptr [rsi+10h], 0
0x140007d2e  jnz     short loc_140007D44
0x140007d30  movups  xmm0, xmmword ptr [rbp+57h+Block]
0x140007d34  movups  xmmword ptr [rdi], xmm0
0x140007d37  movups  xmm1, [rbp+57h+var_B8]
0x140007d3b  movups  xmmword ptr [rdi+10h], xmm1
0x140007d3f  jmp     loc_1400080F6
0x140007d44  xorps   xmm0, xmm0
0x140007d47  movups  xmmword ptr [rbp+57h+Src], xmm0
0x140007d4b  mov     qword ptr [rbp+57h+var_98], r12
0x140007d4f  mov     qword ptr [rbp+57h+var_98+8], 7
0x140007d57  mov     word ptr [rbp+57h+Src], r12w
0x140007d5c  mov     rcx, rsi; this
0x140007d5f  call    ?find_root_name_size@path@filesystem@boost@@AEBA_KXZ; boost::filesystem::path::find_root_name_size(void)
0x140007d64  test    rax, rax
0x140007d67  jz      short loc_140007D86
0x140007d69  mov     r14, rsi
0x140007d6c  cmp     qword ptr [rsi+18h], 7
0x140007d71  jbe     short loc_140007D7E
0x140007d73  mov     r14, [rsi]
0x140007d76  mov     rbx, r14
0x140007d79  mov     rcx, rsi
0x140007d7c  jmp     short loc_140007DA2
0x140007d7e  mov     rbx, rsi
0x140007d81  mov     rcx, rsi
0x140007d84  jmp     short loc_140007DA2
0x140007d86  cmp     qword ptr [rbp+57h+var_B8+8], 7
0x140007d8b  jbe     short loc_140007D96
0x140007d8d  mov     rbx, [rbp+57h+Block]
0x140007d91  mov     r14, rbx
0x140007d94  jmp     short loc_140007D9E
0x140007d96  lea     r14, [rbp+57h+Block]
0x140007d9a  lea     rbx, [rbp+57h+Block]
0x140007d9e  lea     rcx, [rbp+57h+Block]; this
0x140007da2  call    ?find_root_name_size@path@filesystem@boost@@AEBA_KXZ; boost::filesystem::path::find_root_name_size(void)
0x140007da7  lea     r8, [r14+rax*2]
0x140007dab  xorps   xmm0, xmm0
0x140007dae  movups  xmmword ptr [rsp+110h+var_E8], xmm0
0x140007db3  mov     qword ptr [rsp+110h+var_D8], r12
0x140007db8  mov     qword ptr [rbp+57h+var_D8+8], r12
0x140007dbc  cmp     rbx, r8
0x140007dbf  jnz     short loc_140007DD1
0x140007dc1  mov     qword ptr [rbp+57h+var_D8+8], 7
0x140007dc9  mov     word ptr [rsp+110h+var_E8], r12w
0x140007dcf  jmp     short loc_140007DE4
0x140007dd1  sub     r8, rbx
0x140007dd4  sar     r8, 1
0x140007dd7  mov     rdx, rbx
0x140007dda  lea     rcx, [rsp+110h+var_E8]
0x140007ddf  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140007de4  mov     rdx, qword ptr [rbp+57h+var_98+8]
0x140007de8  cmp     rdx, 7
0x140007dec  jbe     short loc_140007E26
0x140007dee  mov     rax, [rbp+57h+Src]
0x140007df2  lea     rdx, ds:2[rdx*2]
0x140007dfa  cmp     rdx, 1000h
0x140007e01  jb      short loc_140007E1E
0x140007e03  mov     rcx, [rax-8]
0x140007e07  sub     rax, rcx
0x140007e0a  sub     rax, 8
0x140007e0e  cmp     rax, 1Fh
0x140007e12  ja      loc_140008001
0x140007e18  add     rdx, 27h ; '''
0x140007e1c  jmp     short loc_140007E21
0x140007e1e  mov     rcx, rax; Block
0x140007e21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007e26  movups  xmm1, [rsp+110h+var_D8]
0x140007e2b  movups  xmm0, xmmword ptr [rsp+110h+var_E8]
0x140007e30  movups  [rbp+57h+var_98], xmm1
0x140007e34  movups  xmmword ptr [rbp+57h+Src], xmm0
0x140007e38  lea     rdx, [rbp+57h+var_88]
0x140007e3c  mov     rcx, rsi
0x140007e3f  call    ?find_root_directory@path@filesystem@boost@@AEBA?AUsubstring@path_detail@23@XZ; boost::filesystem::path::find_root_directory(void)
0x140007e44  cmp     qword ptr [rax+8], 0
0x140007e49  jbe     short loc_140007E83
0x140007e4b  lea     rdx, [rbp+57h+var_78]
0x140007e4f  mov     rcx, rsi
0x140007e52  call    ?root_directory@path@filesystem@boost@@QEBA?AV123@XZ; boost::filesystem::path::root_directory(void)
0x140007e57  nop
0x140007e58  cmp     qword ptr [rax+18h], 7
0x140007e5d  jbe     short loc_140007E64
0x140007e5f  mov     rdx, [rax]
0x140007e62  jmp     short loc_140007E67
0x140007e64  mov     rdx, rax
0x140007e67  mov     r8, [rax+10h]
0x140007e6b  lea     rcx, [rbp+57h+Src]; Src
0x140007e6f  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140007e74  nop
0x140007e75  lea     rcx, [rbp+57h+var_78]
0x140007e79  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140007e7e  jmp     loc_140008010
0x140007e83  lea     rdx, [rbp+57h+var_88]
0x140007e87  lea     rcx, [rbp+57h+Block]
0x140007e8b  call    ?find_root_directory@path@filesystem@boost@@AEBA?AUsubstring@path_detail@23@XZ; boost::filesystem::path::find_root_directory(void)
0x140007e90  lea     rcx, [rbp+57h+Block]
0x140007e94  cmp     qword ptr [rbp+57h+var_B8+8], 7
0x140007e99  cmova   rcx, [rbp+57h+Block]
0x140007e9e  mov     rax, [rbp+57h+var_88]
0x140007ea2  lea     rdx, [rcx+rax*2]
0x140007ea6  mov     rax, [rbp+57h+var_80]
0x140007eaa  lea     r8, [rax+rax]
0x140007eae  xorps   xmm0, xmm0
0x140007eb1  movups  xmmword ptr [rsp+110h+var_E8], xmm0
0x140007eb6  mov     qword ptr [rsp+110h+var_D8], r12
0x140007ebb  mov     qword ptr [rbp+57h+var_D8+8], r12
0x140007ebf  lea     rax, [r8+rdx]
0x140007ec3  cmp     rdx, rax
0x140007ec6  jnz     short loc_140007EE1
0x140007ec8  mov     r8, r12
0x140007ecb  mov     qword ptr [rsp+110h+var_D8], r12
0x140007ed0  mov     ecx, 7
0x140007ed5  mov     qword ptr [rbp+57h+var_D8+8], rcx
0x140007ed9  mov     word ptr [rsp+110h+var_E8], r12w
0x140007edf  jmp     short loc_140007EF7
0x140007ee1  sar     r8, 1
0x140007ee4  lea     rcx, [rsp+110h+var_E8]
0x140007ee9  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140007eee  mov     rcx, qword ptr [rbp+57h+var_D8+8]
  ... truncated ...
```
