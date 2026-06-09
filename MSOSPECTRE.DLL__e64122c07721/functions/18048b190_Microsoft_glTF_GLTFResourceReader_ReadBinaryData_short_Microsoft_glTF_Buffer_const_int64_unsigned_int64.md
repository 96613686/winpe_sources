# Microsoft::glTF::GLTFResourceReader::ReadBinaryData<short>(Microsoft::glTF::Buffer const &,__int64,unsigned __int64)

- ea: `0x18048b190`
- end: `0x18048b500`
- name: `??$ReadBinaryData@F@GLTFResourceReader@glTF@Microsoft@@AEBA?AV?$vector@FV?$allocator@F@std@@@std@@AEBUBuffer@12@_J_K@Z`
- size: `880`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18048ab90`
- `0x18048c040`
- `0x18048d1c0`
- `0x18048d680`
- `0x18048db50`

## callees

- `0x18001ebf0`
- `0x18002c200`
- `0x180040860`
- `0x180184da0`
- `0x1802c2bf0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x18048b190`
- `0x18048e2e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18048b471`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18048b471`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18048b45c`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18048b45c`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x18048b448`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x18048b448`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048b33e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048b39b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048b33e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048b39b`

## string_xrefs

- `0x18048b4d9`: `Cannot read the binary data`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int128 *Microsoft::glTF::GLTFResourceReader::ReadBinaryData<short>(__int64 a1, __int128 *a2, __int64 a3, ...)
{
  unsigned __int64 v3; // r15
  char *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  char *v10; // r14
  char *v11; // rsi
  size_t v12; // rbx
  char *v13; // r15
  _QWORD *v14; // rcx
  __int64 v15; // r14
  _QWORD *v16; // rdx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rsi
  char *v19; // rax
  size_t v20; // rbx
  __int64 v21; // rbx
  volatile signed __int32 *v22; // rbx
  __int128 v24; // [rsp+30h] [rbp-B1h] BYREF
  __int128 v25; // [rsp+40h] [rbp-A1h] BYREF
  __int128 v26; // [rsp+50h] [rbp-91h] BYREF
  char *v27; // [rsp+60h] [rbp-81h]
  __int128 v28; // [rsp+70h] [rbp-71h]
  __int128 v29; // [rsp+80h] [rbp-61h] BYREF
  __int128 v30; // [rsp+90h] [rbp-51h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-41h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-31h]
  __int128 v33; // [rsp+C0h] [rbp-21h] BYREF
  __int64 v34; // [rsp+D0h] [rbp-11h]
  _BYTE pExceptionObject[80]; // [rsp+E0h] [rbp-1h] BYREF
  char v36; // [rsp+150h] [rbp+6Fh] BYREF
  unsigned __int64 v37; // [rsp+158h] [rbp+77h] BYREF
  va_list va; // [rsp+158h] [rbp+77h]
  unsigned __int64 v39; // [rsp+160h] [rbp+7Fh]
  va_list va1; // [rsp+168h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v37 = va_arg(va1, _QWORD);
  v39 = va_arg(va1, _QWORD);
  v3 = v37;
  v7 = 0;
  *(_QWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  v25 = 0u;
  if ( Microsoft::glTF::IsUriBase64((char *)(a3 + 232), &v25, (_QWORD *)&v25 + 1) )
  {
    v28 = v25;
    v9 = *((_QWORD *)&v25 + 1);
    if ( (_QWORD)v25 != *((_QWORD *)&v25 + 1) )
    {
      v8 = *((_QWORD *)&v25 + 1);
      do
      {
        if ( *(_BYTE *)(v8 - 1) != 61 )
          break;
        v8 = --v9;
        *((_QWORD *)&v28 + 1) = v9;
      }
      while ( (_QWORD)v25 != v9 );
    }
    v26 = 0;
    v10 = 0;
    v27 = 0;
    v11 = 0;
    if ( v39 )
    {
      if ( v39 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(0x7FFFFFFFFFFFFFFFLL, v8);
      _mm_lfence();
      v12 = 2 * v39;
      v11 = (char *)std::_Allocate<16,std::_Default_allocate_traits,0>(2 * v39);
      v13 = v11;
      *(_QWORD *)&v26 = v11;
      v10 = &v11[v12];
      v27 = &v11[v12];
      memset_0(v11, 0, v12);
      *((_QWORD *)&v26 + 1) = &v11[v12];
      v7 = &v11[v12];
    }
    else
    {
      v13 = (char *)v26;
    }
    *(_QWORD *)&v24 = v13;
    *((_QWORD *)&v24 + 1) = 2 * ((v7 - v11) >> 1);
    v29 = v24;
    v30 = v28;
    Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(a1, &v30, (__int64)&v29, (unsigned __int64 *)va);
    if ( a2 != &v26 )
    {
      v14 = *(_QWORD **)a2;
      if ( *(_QWORD *)a2 )
      {
        if ( (unsigned __int64)(2 * ((__int64)(*((_QWORD *)a2 + 2) - (_QWORD)v14) >> 1)) >= 0x1000 )
        {
          if ( (unsigned __int64)v14 - *(v14 - 1) - 8 > 0x1F )
            _invalid_parameter_noinfo_noreturn();
          v14 = (_QWORD *)*(v14 - 1);
        }
        operator delete(v14);
        *(_QWORD *)a2 = 0;
        *((_QWORD *)a2 + 1) = 0;
        *((_QWORD *)a2 + 2) = 0;
      }
      *(_QWORD *)a2 = v11;
      *((_QWORD *)a2 + 1) = v7;
      *((_QWORD *)a2 + 2) = v10;
      v11 = 0;
      v7 = 0;
    }
    if ( v11 )
    {
      if ( (unsigned __int64)(2 * ((v7 - v11) >> 1)) >= 0x1000 )
      {
        if ( (unsigned __int64)&v11[-*((_QWORD *)v11 - 1) - 8] > 0x1F )
          _invalid_parameter_noinfo_noreturn();
        v11 = (char *)*((_QWORD *)v11 - 1);
      }
      operator delete(v11);
    }
    return a2;
  }
  v15 = *((_QWORD *)a2 + 1);
  v16 = *(_QWORD **)a2;
  v17 = (v15 - *(_QWORD *)a2) >> 1;
  v18 = v39;
  if ( v39 < v17 )
  {
    v19 = (char *)v16 + 2 * v39;
LABEL_30:
    *((_QWORD *)a2 + 1) = v19;
    goto LABEL_31;
  }
  if ( v39 > v17 )
  {
    if ( v39 <= (__int64)(*((_QWORD *)a2 + 2) - (_QWORD)v16) >> 1 )
    {
      v20 = 2 * (v39 - v17);
      memset_0(*((void **)a2 + 1), 0, v20);
      v19 = (char *)(v20 + v15);
      goto LABEL_30;
    }
    _mm_lfence();
    std::vector<short>::_Resize_reallocate<std::_Value_init_tag>(a2, v39, &v36);
    v3 = v37;
  }
LABEL_31:
  (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 8LL))(a1, &v24, a3);
  (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 16LL))(a1, &v31, a3);
  v33 = v31;
  v34 = v32;
  std::istream::seekg(v24, &v33);
  std::istream::seekg(v24, v3, 1);
  v21 = v24;
  std::istream::read(v24, *(_QWORD *)a2, 2 * v18);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v21 + 4LL) + v21 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Cannot read the binary data");
    throw (std::runtime_error *)pExceptionObject;
  }
  v22 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
  if ( *((_QWORD *)&v24 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18048b190  mov     [rsp-8+arg_0], rbx
0x18048b195  mov     [rsp-8+arg_18], r9
0x18048b19a  mov     [rsp-8+arg_8], rdx
0x18048b19f  push    rbp
0x18048b1a0  push    rsi
0x18048b1a1  push    rdi
0x18048b1a2  push    r12
0x18048b1a4  push    r13
0x18048b1a6  push    r14
0x18048b1a8  push    r15
0x18048b1aa  lea     rbp, [rsp-1Fh]
0x18048b1af  sub     rsp, 100h
0x18048b1b6  mov     r15, r9
0x18048b1b9  mov     r13, r8
0x18048b1bc  mov     rdi, rdx
0x18048b1bf  mov     r12, rcx
0x18048b1c2  xor     ebx, ebx
0x18048b1c4  mov     [rsp+130h+var_110], ebx
0x18048b1c8  mov     [rdx], rbx
0x18048b1cb  mov     [rdx+8], rbx
0x18048b1cf  mov     [rdx+10h], rbx
0x18048b1d3  mov     [rsp+130h+var_110], 1
0x18048b1db  mov     qword ptr [rsp+130h+var_F0], rbx
0x18048b1e0  mov     qword ptr [rsp+130h+var_F0+8], rbx
0x18048b1e5  lea     rcx, [r8+0E8h]; Buf
0x18048b1ec  lea     r8, [rsp+130h+var_F0+8]
0x18048b1f1  lea     rdx, [rsp+130h+var_F0]
0x18048b1f6  call    ?IsUriBase64@glTF@Microsoft@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@4@1@Z; Microsoft::glTF::IsUriBase64(std::string const &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &)
0x18048b1fb  test    al, al
0x18048b1fd  jz      loc_18048B3A2
0x18048b203  mov     rax, qword ptr [rsp+130h+var_F0]
0x18048b208  mov     qword ptr [rbp+4Fh+var_C0], rax
0x18048b20c  mov     rcx, qword ptr [rsp+130h+var_F0+8]
0x18048b211  mov     qword ptr [rbp+4Fh+var_C0+8], rcx
0x18048b215  cmp     rax, rcx
0x18048b218  jz      short loc_18048B235
0x18048b21a  mov     rdx, rcx
0x18048b21d  nop     dword ptr [rax]
0x18048b220  cmp     byte ptr [rdx-1], 3Dh ; '='
0x18048b224  jnz     short loc_18048B235
0x18048b226  dec     rcx
0x18048b229  mov     rdx, rcx
0x18048b22c  mov     qword ptr [rbp+4Fh+var_C0+8], rcx
0x18048b230  cmp     rax, rcx
0x18048b233  jnz     short loc_18048B220
0x18048b235  xorps   xmm0, xmm0
0x18048b238  movdqu  [rsp+130h+var_E0], xmm0
0x18048b23e  mov     r14, rbx
0x18048b241  mov     [rsp+130h+var_D0], rbx
0x18048b246  mov     rsi, rbx
0x18048b249  mov     rax, [rbp+4Fh+arg_20]
0x18048b24d  test    rax, rax
0x18048b250  jz      short loc_18048B29F
0x18048b252  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18048b25c  cmp     rax, rcx
0x18048b25f  ja      loc_18048B4FA
0x18048b265  lfence
0x18048b268  lea     rbx, [rax+rax]
0x18048b26c  mov     rcx, rbx
0x18048b26f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x18048b274  mov     rsi, rax
0x18048b277  mov     r15, rax
0x18048b27a  mov     qword ptr [rsp+130h+var_E0], rax
0x18048b27f  lea     r14, [rbx+rax]
0x18048b283  mov     [rsp+130h+var_D0], r14
0x18048b288  mov     r8, rbx; Size
0x18048b28b  xor     edx, edx; Val
0x18048b28d  mov     rcx, rax; void *
0x18048b290  call    memset_0
0x18048b295  mov     qword ptr [rsp+130h+var_E0+8], r14
0x18048b29a  mov     rbx, r14
0x18048b29d  jmp     short loc_18048B2A4
0x18048b29f  mov     r15, qword ptr [rsp+130h+var_E0]
0x18048b2a4  mov     [rsp+130h+var_110], 3
0x18048b2ac  mov     rax, rbx
0x18048b2af  sub     rax, rsi
0x18048b2b2  sar     rax, 1
0x18048b2b5  mov     qword ptr [rsp+130h+var_100], r15
0x18048b2ba  add     rax, rax
0x18048b2bd  mov     qword ptr [rsp+130h+var_100+8], rax
0x18048b2c2  movaps  xmm0, [rsp+130h+var_100]
0x18048b2c7  movdqa  [rbp+4Fh+var_B0], xmm0
0x18048b2cc  movaps  xmm1, [rbp+4Fh+var_C0]
0x18048b2d0  movdqa  [rbp+4Fh+var_A0], xmm1
0x18048b2d5  lea     r9, [rbp+4Fh+arg_18]
0x18048b2d9  lea     r8, [rbp+4Fh+var_B0]
0x18048b2dd  lea     rdx, [rbp+4Fh+var_A0]
0x18048b2e1  mov     rcx, r12
0x18048b2e4  call    ?ReadBinaryDataUri@GLTFResourceReader@glTF@Microsoft@@AEBAXUBase64StringView@23@UBase64BufferView@23@PEB_J@Z; Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(Microsoft::glTF::Base64StringView,Microsoft::glTF::Base64BufferView,__int64 const *)
0x18048b2e9  lea     rax, [rsp+130h+var_E0]
0x18048b2ee  cmp     rdi, rax
0x18048b2f1  jz      short loc_18048B358
0x18048b2f3  mov     rcx, [rdi]
0x18048b2f6  test    rcx, rcx
0x18048b2f9  jz      short loc_18048B345
0x18048b2fb  mov     rax, [rdi+10h]
0x18048b2ff  sub     rax, rcx
0x18048b302  sar     rax, 1
0x18048b305  lea     rdx, [rax+rax]
0x18048b309  cmp     rdx, 1000h
0x18048b310  jb      short loc_18048B32A
0x18048b312  add     rdx, 27h ; '''
0x18048b316  mov     r8, [rcx-8]
0x18048b31a  sub     rcx, r8
0x18048b31d  lea     rax, [rcx-8]
0x18048b321  cmp     rax, 1Fh
0x18048b325  ja      short loc_18048B33E
0x18048b327  mov     rcx, r8; Block
0x18048b32a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18048b32f  xor     eax, eax
0x18048b331  mov     [rdi], rax
0x18048b334  mov     [rdi+8], rax
0x18048b338  mov     [rdi+10h], rax
0x18048b33c  jmp     short loc_18048B347
0x18048b33e  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18048b345  xor     eax, eax
0x18048b347  mov     [rdi], rsi
0x18048b34a  mov     [rdi+8], rbx
0x18048b34e  mov     [rdi+10h], r14
0x18048b352  mov     rsi, rax
0x18048b355  mov     rbx, rax
0x18048b358  test    rsi, rsi
0x18048b35b  jz      loc_18048B4BB
0x18048b361  sub     rbx, rsi
0x18048b364  sar     rbx, 1
0x18048b367  add     rbx, rbx
0x18048b36a  cmp     rbx, 1000h
0x18048b371  jb      short loc_18048B38B
0x18048b373  add     rbx, 27h ; '''
0x18048b377  mov     rcx, [rsi-8]
0x18048b37b  sub     rsi, rcx
0x18048b37e  lea     rax, [rsi-8]
0x18048b382  cmp     rax, 1Fh
0x18048b386  ja      short loc_18048B39B
0x18048b388  mov     rsi, rcx
0x18048b38b  mov     rdx, rbx
0x18048b38e  mov     rcx, rsi; Block
0x18048b391  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18048b396  jmp     loc_18048B4BB
0x18048b39b  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18048b3a2  mov     r14, [rdi+8]
0x18048b3a6  mov     rdx, [rdi]
0x18048b3a9  mov     rcx, r14
0x18048b3ac  sub     rcx, rdx
0x18048b3af  sar     rcx, 1
0x18048b3b2  mov     rsi, [rbp+4Fh+arg_20]
0x18048b3b6  cmp     rsi, rcx
0x18048b3b9  jnb     short loc_18048B3C1
0x18048b3bb  lea     rax, [rdx+rsi*2]
0x18048b3bf  jmp     short loc_18048B405
0x18048b3c1  jbe     short loc_18048B409
0x18048b3c3  mov     rax, [rdi+10h]
0x18048b3c7  sub     rax, rdx
0x18048b3ca  sar     rax, 1
0x18048b3cd  cmp     rsi, rax
0x18048b3d0  jbe     short loc_18048B3EA
0x18048b3d2  lfence
0x18048b3d5  lea     r8, [rbp+4Fh+arg_10]
0x18048b3d9  mov     rdx, rsi
0x18048b3dc  mov     rcx, rdi
0x18048b3df  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@FV?$allocator@F@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<short>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18048b3e4  mov     r15, [rbp+4Fh+arg_18]
0x18048b3e8  jmp     short loc_18048B409
0x18048b3ea  mov     rax, rsi
0x18048b3ed  sub     rax, rcx
0x18048b3f0  lea     rbx, [rax+rax]
0x18048b3f4  mov     r8, rbx; Size
0x18048b3f7  xor     edx, edx; Val
0x18048b3f9  mov     rcx, r14; void *
0x18048b3fc  call    memset_0
0x18048b401  lea     rax, [rbx+r14]
0x18048b405  mov     [rdi+8], rax
0x18048b409  mov     rax, [r12]
0x18048b40d  mov     r8, r13
0x18048b410  lea     rdx, [rsp+130h+var_100]
0x18048b415  mov     rcx, r12
0x18048b418  call    qword ptr [rax+8]
0x18048b41b  nop
0x18048b41c  mov     rax, [r12]
0x18048b420  mov     r8, r13
0x18048b423  lea     rdx, [rbp+4Fh+var_90]
0x18048b427  mov     rcx, r12
0x18048b42a  call    qword ptr [rax+10h]
0x18048b42d  movups  xmm0, [rbp+4Fh+var_90]
0x18048b431  movaps  [rbp+4Fh+var_70], xmm0
0x18048b435  movsd   xmm1, [rbp+4Fh+var_80]
0x18048b43a  movsd   [rbp+4Fh+var_60], xmm1
0x18048b43f  lea     rdx, [rbp+4Fh+var_70]
0x18048b443  mov     rcx, qword ptr [rsp+130h+var_100]
0x18048b448  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x18048b44e  mov     r8d, 1
0x18048b454  mov     rdx, r15
0x18048b457  mov     rcx, qword ptr [rsp+130h+var_100]
0x18048b45c  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18048b462  lea     r8, [rsi+rsi]
0x18048b466  mov     rbx, qword ptr [rsp+130h+var_100]
0x18048b46b  mov     rdx, [rdi]
0x18048b46e  mov     rcx, rbx
0x18048b471  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18048b477  mov     rax, [rbx]
0x18048b47a  movsxd  rcx, dword ptr [rax+4]
0x18048b47e  test    byte ptr [rcx+rbx+10h], 6
0x18048b483  jnz     short loc_18048B4D9
0x18048b485  mov     rbx, qword ptr [rsp+130h+var_100+8]
0x18048b48a  test    rbx, rbx
0x18048b48d  jz      short loc_18048B4BB
0x18048b48f  mov     esi, 0FFFFFFFFh
0x18048b494  mov     eax, esi
0x18048b496  lock xadd [rbx+8], eax
0x18048b49b  cmp     eax, 1
0x18048b49e  jnz     short loc_18048B4BB
0x18048b4a0  mov     rax, [rbx]
0x18048b4a3  mov     rcx, rbx
0x18048b4a6  call    qword ptr [rax]
0x18048b4a8  lock xadd [rbx+0Ch], esi
0x18048b4ad  cmp     esi, 1
0x18048b4b0  jnz     short loc_18048B4BB
0x18048b4b2  mov     rax, [rbx]
0x18048b4b5  mov     rcx, rbx
0x18048b4b8  call    qword ptr [rax+8]
0x18048b4bb  mov     rax, rdi
0x18048b4be  mov     rbx, [rsp+130h+arg_0]
0x18048b4c6  add     rsp, 100h
0x18048b4cd  pop     r15
0x18048b4cf  pop     r14
0x18048b4d1  pop     r13
0x18048b4d3  pop     r12
0x18048b4d5  pop     rdi
0x18048b4d6  pop     rsi
0x18048b4d7  pop     rbp
0x18048b4d8  retn
0x18048b4d9  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x18048b4e0  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18048b4e4  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18048b4e9  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18048b4f0  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18048b4f4  call    _CxxThrowException_0
0x18048b4fa  call    ?_Xlength@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@CAXXZ; std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(void)
```
