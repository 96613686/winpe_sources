# std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(std::shared_ptr<std::filesystem::_Dir_enum_impl> &,std::filesystem::path const &,std::filesystem::directory_options)

- ea: `0x180021a6c`
- end: `0x180021cd5`
- name: `??$_Initialize_dir_enum@U_Dir_enum_impl@filesystem@std@@@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@2@AEBVpath@12@W4directory_options@12@@Z`
- size: `617`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180024160`

## callees

- `0x180001f4c`
- `0x180001f74`
- `0x180001f9c`
- `0x180002880`
- `0x180002cac`
- `0x1800188d4`
- `0x18001da30`
- `0x1800214e8`
- `0x180021870`
- `0x180021a6c`
- `0x180022ce0`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v3; // r8
  LPCWSTR *v4; // rcx
  __int64 v5; // rax
  char v6; // bl
  const WCHAR *v7; // rcx
  int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rax
  volatile signed __int32 *v11; // rbx
  unsigned int v12; // ebx
  void *v14; // [rsp+28h] [rbp-D8h]
  __int128 v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h]
  __int64 v17; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  char v22[44]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v23; // [rsp+A4h] [rbp-5Ch]
  __int16 v24; // [rsp+A6h] [rbp-5Ah]
  __int16 v25; // [rsp+A8h] [rbp-58h]
  char v26; // [rsp+2C8h] [rbp+1C8h]
  __int16 v27; // [rsp+2C9h] [rbp+1C9h]
  char v28; // [rsp+2CBh] [rbp+1CBh]
  int v29; // [rsp+2CCh] [rbp+1CCh]

  *(_OWORD *)lpFileName = 0;
  v19 = 0;
  v20 = 0;
  v3 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::_Construct<2,unsigned short const *>(lpFileName, a2, v3);
  v21 = -1;
  v4 = lpFileName;
  if ( v20 > 7 )
    v4 = (LPCWSTR *)lpFileName[0];
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)v4 + v5) );
  if ( !v5 || v5 != v19 )
  {
    v8 = 2;
    goto LABEL_25;
  }
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v6 = 1;
  std::wstring::_Construct<1,unsigned short const *>(&v15, L"*", 1);
  std::filesystem::path::operator/=(lpFileName, (std::filesystem *)&v15);
  std::wstring::_Tidy_deallocate(&v15);
  v7 = (const WCHAR *)lpFileName;
  if ( v20 > 7 )
    v7 = lpFileName[0];
  v8 = _std_fs_directory_iterator_open(v7);
  if ( v8 )
    goto LABEL_22;
  v9 = v21;
  while ( v23 == 46 && (!v24 || v24 == 46 && !v25) )
  {
    v8 = _std_fs_directory_iterator_advance(v9, v22);
    if ( v8 )
      goto LABEL_20;
  }
  v8 = 0;
LABEL_20:
  if ( v8 )
  {
LABEL_22:
    if ( v8 == 18 )
    {
      v27 = 0;
      v28 = 0;
      v29 = 0;
LABEL_26:
      v6 = 0;
      goto LABEL_27;
    }
LABEL_25:
    v27 = 0;
    v28 = 0;
    v29 = v8;
    goto LABEL_26;
  }
  v27 = 0;
  v28 = 0;
  v29 = 0;
LABEL_27:
  v26 = v6;
  if ( v6 )
  {
    v14 = operator new(0x58u);
    v10 = std::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>(
            v14,
            lpFileName);
    *a1 = v10 + 16;
    v11 = (volatile signed __int32 *)a1[1];
    a1[1] = v10;
    if ( v11 )
    {
      if ( !_InterlockedDecrement(v11 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( !_InterlockedDecrement(v11 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  v12 = v29;
  _std_fs_directory_iterator_close(v21);
  std::wstring::_Tidy_deallocate(lpFileName);
  return v12;
}

```

## disassembly

```asm
0x180021a6c  mov     [rsp-8+arg_10], rbx
0x180021a71  push    rbp
0x180021a72  push    rsi
0x180021a73  push    rdi
0x180021a74  push    r14
0x180021a76  push    r15
0x180021a78  lea     rbp, [rsp-1E0h]
0x180021a80  sub     rsp, 2E0h
0x180021a87  mov     rax, cs:__security_cookie
0x180021a8e  xor     rax, rsp
0x180021a91  mov     [rbp+200h+var_30], rax
0x180021a98  mov     rsi, rcx
0x180021a9b  xor     r14d, r14d
0x180021a9e  xorps   xmm0, xmm0
0x180021aa1  movups  xmmword ptr [rsp+300h+lpFileName], xmm0
0x180021aa6  mov     [rsp+300h+var_2A0], r14
0x180021aab  mov     [rsp+300h+var_298], r14
0x180021ab0  mov     r8, [rdx+10h]
0x180021ab4  cmp     qword ptr [rdx+18h], 7
0x180021ab9  jbe     short loc_180021ABE
0x180021abb  mov     rdx, [rdx]
0x180021abe  lea     rcx, [rsp+300h+lpFileName]
0x180021ac3  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180021ac8  nop
0x180021ac9  or      r15, 0FFFFFFFFFFFFFFFFh
0x180021acd  mov     [rsp+300h+var_290], r15
0x180021ad2  lea     rcx, [rsp+300h+lpFileName]
0x180021ad7  cmp     [rsp+300h+var_298], 7
0x180021add  cmova   rcx, [rsp+300h+lpFileName]
0x180021ae3  mov     rax, r15
0x180021ae6  inc     rax
0x180021ae9  cmp     [rcx+rax*2], r14w
0x180021aee  jnz     short loc_180021AE6
0x180021af0  test    rax, rax
0x180021af3  jz      loc_180021BF5
0x180021af9  cmp     rax, [rsp+300h+var_2A0]
0x180021afe  jnz     loc_180021BF5
0x180021b04  xorps   xmm0, xmm0
0x180021b07  movups  [rsp+300h+var_2D0], xmm0
0x180021b0c  mov     [rsp+300h+var_2C0], r14
0x180021b11  mov     [rsp+300h+var_2B8], r14
0x180021b16  mov     ebx, 1
0x180021b1b  mov     r8d, ebx
0x180021b1e  lea     rdx, asc_180032CD4; "*"
0x180021b25  lea     rcx, [rsp+300h+var_2D0]
0x180021b2a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021b2f  nop
0x180021b30  lea     rdx, [rsp+300h+var_2D0]; this
0x180021b35  lea     rcx, [rsp+300h+lpFileName]; Src
0x180021b3a  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180021b3f  nop
0x180021b40  lea     rcx, [rsp+300h+var_2D0]
0x180021b45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021b4a  lea     rcx, [rsp+300h+lpFileName]
0x180021b4f  cmp     [rsp+300h+var_298], 7
0x180021b55  cmova   rcx, [rsp+300h+lpFileName]; lpFileName
0x180021b5b  lea     r8, [rsp+300h+var_288]
0x180021b60  lea     rdx, [rsp+300h+var_290]
0x180021b65  call    __std_fs_directory_iterator_open
0x180021b6a  test    eax, eax
0x180021b6c  jnz     short loc_180021BCF
0x180021b6e  mov     rdi, [rsp+300h+var_290]
0x180021b73  cmp     [rbp+200h+var_25C], 2Eh ; '.'
0x180021b78  jnz     short loc_180021BA3
0x180021b7a  movzx   eax, [rbp+200h+var_25A]
0x180021b7e  test    ax, ax
0x180021b81  jz      short loc_180021B90
0x180021b83  cmp     ax, 2Eh ; '.'
0x180021b87  jnz     short loc_180021BA3
0x180021b89  cmp     [rbp+200h+var_258], r14w
0x180021b8e  jnz     short loc_180021BA3
0x180021b90  lea     rdx, [rsp+300h+var_288]
0x180021b95  mov     rcx, rdi
0x180021b98  call    __std_fs_directory_iterator_advance
0x180021b9d  test    eax, eax
0x180021b9f  jz      short loc_180021B73
0x180021ba1  jmp     short loc_180021BA6
0x180021ba3  mov     eax, r14d
0x180021ba6  test    eax, eax
0x180021ba8  jnz     short loc_180021BCF
0x180021baa  mov     [rsp+300h+var_2E0], bl
0x180021bae  xor     eax, eax
0x180021bb0  mov     [rsp+300h+var_2DF], ax
0x180021bb5  mov     [rsp+300h+var_2DD], al
0x180021bb9  mov     [rbp+200h+var_37], ax
0x180021bc0  mov     [rbp+200h+var_35], al
0x180021bc6  mov     [rbp+200h+var_34], r14d
0x180021bcd  jmp     short loc_180021C20
0x180021bcf  cmp     eax, 12h
0x180021bd2  jnz     short loc_180021BFA
0x180021bd4  xor     eax, eax
0x180021bd6  mov     [rsp+300h+var_2DF], ax
0x180021bdb  mov     [rsp+300h+var_2DD], al
0x180021bdf  mov     [rbp+200h+var_37], ax
0x180021be6  mov     [rbp+200h+var_35], al
0x180021bec  mov     [rbp+200h+var_34], r14d
0x180021bf3  jmp     short loc_180021C18
0x180021bf5  mov     eax, 2
0x180021bfa  xor     ecx, ecx
0x180021bfc  mov     [rsp+300h+var_2DF], cx
0x180021c01  mov     [rsp+300h+var_2DD], cl
0x180021c05  mov     [rbp+200h+var_37], cx
0x180021c0c  mov     [rbp+200h+var_35], cl
0x180021c12  mov     [rbp+200h+var_34], eax
0x180021c18  mov     bl, r14b
0x180021c1b  mov     [rsp+300h+var_2E0], r14b
0x180021c20  mov     [rbp+200h+var_38], bl
0x180021c26  test    bl, bl
0x180021c28  jz      short loc_180021C92
0x180021c2a  mov     ecx, 58h ; 'X'; Size
0x180021c2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021c34  mov     [rsp+300h+var_2D8], rax
0x180021c39  lea     rdx, [rsp+300h+lpFileName]
0x180021c3e  mov     rcx, rax
0x180021c41  call    ??$?0U_Creator@_Dir_enum_impl@filesystem@std@@AEBW4directory_options@23@@?$_Ref_count_obj2@U_Dir_enum_impl@filesystem@std@@@std@@QEAA@$$QEAU_Creator@_Dir_enum_impl@filesystem@1@AEBW4directory_options@41@@Z; std::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>::_Ref_count_obj2<std::filesystem::_Dir_enum_impl>(std::filesystem::_Dir_enum_impl::_Creator &&,std::filesystem::directory_options const &)
0x180021c46  nop
0x180021c47  lea     rcx, [rax+10h]
0x180021c4b  mov     [rsi], rcx
0x180021c4e  mov     rbx, [rsi+8]
0x180021c52  mov     [rsi+8], rax
0x180021c56  test    rbx, rbx
0x180021c59  jz      short loc_180021C92
0x180021c5b  mov     eax, r15d
0x180021c5e  lock xadd [rbx+8], eax
0x180021c63  add     eax, r15d
0x180021c66  jnz     short loc_180021C92
0x180021c68  mov     rax, [rbx]
0x180021c6b  mov     rcx, rbx
0x180021c6e  mov     rax, [rax]
0x180021c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c76  mov     eax, r15d
0x180021c79  lock xadd [rbx+0Ch], eax
0x180021c7e  add     eax, r15d
0x180021c81  jnz     short loc_180021C92
0x180021c83  mov     rax, [rbx]
0x180021c86  mov     rcx, rbx
0x180021c89  mov     rax, [rax+8]
0x180021c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c92  mov     ebx, [rbp+200h+var_34]
0x180021c98  mov     rcx, [rsp+300h+var_290]
0x180021c9d  call    __std_fs_directory_iterator_close
0x180021ca2  lea     rcx, [rsp+300h+lpFileName]
0x180021ca7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021cac  mov     eax, ebx
0x180021cae  mov     rcx, [rbp+200h+var_30]
0x180021cb5  xor     rcx, rsp; StackCookie
0x180021cb8  call    __security_check_cookie
0x180021cbd  mov     rbx, [rsp+300h+arg_10]
0x180021cc5  add     rsp, 2E0h
0x180021ccc  pop     r15
0x180021cce  pop     r14
0x180021cd0  pop     rdi
0x180021cd1  pop     rsi
0x180021cd2  pop     rbp
0x180021cd3  retn
```
