# Microsoft::glTF::GLTFResourceReader::ReadBinaryData<signed char>(Microsoft::glTF::Buffer const &,__int64,unsigned __int64)

- ea: `0x18048ae40`
- end: `0x18048b18a`
- name: `??$ReadBinaryData@C@GLTFResourceReader@glTF@Microsoft@@AEBA?AV?$vector@CV?$allocator@C@std@@@std@@AEBUBuffer@12@_J_K@Z`
- size: `842`
- prototype: `__int128 *__fastcall(__int64, __int128 *, __int64, unsigned __int64, size_t Size)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18048a900`
- `0x18048bcd0`
- `0x18048c3d0`
- `0x18048c850`
- `0x18048cd00`

## callees

- `0x18001ebf0`
- `0x18002c200`
- `0x180040860`
- `0x180184da0`
- `0x1802c2bf0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x18048ae40`
- `0x18048e220`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18048b102`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18048b102`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18048b0ee`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18048b0ee`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x18048b0da`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x18048b0da`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048afe0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048b037`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048afe0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18048b037`

## string_xrefs

- `0x18048b163`: `Cannot read the binary data`

## pseudocode

```c
__int128 *__fastcall Microsoft::glTF::GLTFResourceReader::ReadBinaryData<signed char>(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        unsigned __int64 a4,
        size_t Size)
{
  unsigned __int64 v5; // r15
  char *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // rcx
  char *v12; // r14
  char *v13; // rbx
  size_t v14; // r15
  char *v15; // r12
  _QWORD *v16; // rcx
  __int64 v17; // r14
  _QWORD *v18; // rdx
  size_t v19; // rcx
  size_t v20; // rsi
  size_t v21; // rax
  size_t v22; // rbx
  __int64 v23; // rbx
  volatile signed __int32 *v24; // rbx
  __int128 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h]
  __int128 v28; // [rsp+50h] [rbp-B0h] BYREF
  char *v29; // [rsp+60h] [rbp-A0h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+80h] [rbp-80h] BYREF
  __int128 v32; // [rsp+90h] [rbp-70h] BYREF
  __int128 v33; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-50h]
  __int128 v35; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-30h]
  _BYTE pExceptionObject[96]; // [rsp+E0h] [rbp-20h] BYREF
  char v39; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v40; // [rsp+168h] [rbp+68h] BYREF

  v40 = a4;
  v5 = a4;
  v9 = 0;
  *(_QWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  v27 = 0u;
  if ( (unsigned __int8)Microsoft::glTF::IsUriBase64((void *)(a3 + 232)) )
  {
    v30 = v27;
    v11 = *((_QWORD *)&v27 + 1);
    if ( (_QWORD)v27 != *((_QWORD *)&v27 + 1) )
    {
      v10 = *((_QWORD *)&v27 + 1);
      do
      {
        if ( *(_BYTE *)(v10 - 1) != 61 )
          break;
        v10 = --v11;
        *((_QWORD *)&v30 + 1) = v11;
      }
      while ( (_QWORD)v27 != v11 );
    }
    v28 = 0;
    v12 = 0;
    v29 = 0;
    v13 = 0;
    v14 = Size;
    if ( Size )
    {
      if ( Size > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(v11, v10);
      _mm_lfence();
      v13 = (char *)std::_Allocate<16,std::_Default_allocate_traits,0>(Size);
      v15 = v13;
      *(_QWORD *)&v28 = v13;
      v12 = &v13[v14];
      v29 = &v13[v14];
      memset_0(v13, 0, v14);
      *((_QWORD *)&v28 + 1) = &v13[v14];
      v9 = &v13[v14];
    }
    else
    {
      v15 = (char *)v28;
    }
    *(_QWORD *)&v26 = v15;
    *((_QWORD *)&v26 + 1) = v9 - v13;
    v31 = v26;
    v32 = v30;
    Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(a1, &v32, (__int64)&v31, &v40);
    if ( a2 != &v28 )
    {
      v16 = *(_QWORD **)a2;
      if ( *(_QWORD *)a2 )
      {
        if ( *((_QWORD *)a2 + 2) - (_QWORD)v16 >= 0x1000u )
        {
          if ( (unsigned __int64)v16 - *(v16 - 1) - 8 > 0x1F )
            _invalid_parameter_noinfo_noreturn();
          v16 = (_QWORD *)*(v16 - 1);
        }
        operator delete(v16);
        *(_QWORD *)a2 = 0;
        *((_QWORD *)a2 + 1) = 0;
        *((_QWORD *)a2 + 2) = 0;
      }
      *(_QWORD *)a2 = v13;
      *((_QWORD *)a2 + 1) = v9;
      *((_QWORD *)a2 + 2) = v12;
      v13 = 0;
      v9 = 0;
    }
    if ( v13 )
    {
      if ( (unsigned __int64)(v9 - v13) >= 0x1000 )
      {
        if ( (unsigned __int64)&v13[-*((_QWORD *)v13 - 1) - 8] > 0x1F )
          _invalid_parameter_noinfo_noreturn();
        v13 = (char *)*((_QWORD *)v13 - 1);
      }
      operator delete(v13);
    }
    return a2;
  }
  v17 = *((_QWORD *)a2 + 1);
  v18 = *(_QWORD **)a2;
  v19 = v17 - *(_QWORD *)a2;
  v20 = Size;
  if ( Size < v19 )
  {
    v21 = (size_t)v18 + Size;
LABEL_30:
    *((_QWORD *)a2 + 1) = v21;
    goto LABEL_31;
  }
  if ( Size > v19 )
  {
    if ( Size <= *((_QWORD *)a2 + 2) - (_QWORD)v18 )
    {
      v22 = Size - v19;
      memset_0(*((void **)a2 + 1), 0, Size - v19);
      v21 = v17 + v22;
      goto LABEL_30;
    }
    _mm_lfence();
    std::vector<signed char>::_Resize_reallocate<std::_Value_init_tag>(a2, Size, &v39);
    v5 = v40;
  }
LABEL_31:
  (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 8LL))(a1, &v26, a3);
  (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 16LL))(a1, &v33, a3);
  v35 = v33;
  v36 = v34;
  std::istream::seekg(v26, &v35);
  std::istream::seekg(v26, v5, 1);
  v23 = v26;
  std::istream::read(v26, *(_QWORD *)a2, v20);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v23 + 4LL) + v23 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Cannot read the binary data");
    throw (std::runtime_error *)pExceptionObject;
  }
  v24 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
  if ( *((_QWORD *)&v26 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18048ae40  mov     [rsp-8+arg_18], r9
0x18048ae45  mov     [rsp-8+arg_8], rdx
0x18048ae4a  mov     [rsp-8+arg_0], rcx
0x18048ae4f  push    rbp
0x18048ae50  push    rbx
0x18048ae51  push    rsi
0x18048ae52  push    rdi
0x18048ae53  push    r12
0x18048ae55  push    r13
0x18048ae57  push    r14
0x18048ae59  push    r15
0x18048ae5b  lea     rbp, [rsp-8]
0x18048ae60  sub     rsp, 108h
0x18048ae67  mov     r15, r9
0x18048ae6a  mov     r13, r8
0x18048ae6d  mov     rdi, rdx
0x18048ae70  mov     r12, rcx
0x18048ae73  xor     esi, esi
0x18048ae75  mov     [rsp+140h+var_120], esi
0x18048ae79  mov     [rdx], rsi
0x18048ae7c  mov     [rdx+8], rsi
0x18048ae80  mov     [rdx+10h], rsi
0x18048ae84  mov     [rsp+140h+var_120], 1
0x18048ae8c  mov     qword ptr [rsp+140h+var_100], rsi
0x18048ae91  mov     qword ptr [rsp+140h+var_100+8], rsi
0x18048ae96  lea     rcx, [r8+0E8h]; Buf
0x18048ae9d  lea     r8, [rsp+140h+var_100+8]
0x18048aea2  lea     rdx, [rsp+140h+var_100]
0x18048aea7  call    ?IsUriBase64@glTF@Microsoft@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@4@1@Z; Microsoft::glTF::IsUriBase64(std::string const &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &)
0x18048aeac  test    al, al
0x18048aeae  jz      loc_18048B03E
0x18048aeb4  mov     rax, qword ptr [rsp+140h+var_100]
0x18048aeb9  mov     qword ptr [rsp+140h+var_D0], rax
0x18048aebe  mov     rcx, qword ptr [rsp+140h+var_100+8]
0x18048aec3  mov     qword ptr [rsp+140h+var_D0+8], rcx
0x18048aec8  cmp     rax, rcx
0x18048aecb  jz      short loc_18048AEE6
0x18048aecd  mov     rdx, rcx
0x18048aed0  cmp     byte ptr [rdx-1], 3Dh ; '='
0x18048aed4  jnz     short loc_18048AEE6
0x18048aed6  dec     rcx
0x18048aed9  mov     rdx, rcx
0x18048aedc  mov     qword ptr [rsp+140h+var_D0+8], rcx
0x18048aee1  cmp     rax, rcx
0x18048aee4  jnz     short loc_18048AED0
0x18048aee6  xorps   xmm0, xmm0
0x18048aee9  movdqu  [rsp+140h+var_F0], xmm0
0x18048aeef  mov     r14, rsi
0x18048aef2  mov     [rsp+140h+var_E0], rsi
0x18048aef7  mov     rbx, rsi
0x18048aefa  mov     r15, [rbp+40h+Size]
0x18048aefe  test    r15, r15
0x18048af01  jz      short loc_18048AF4C
0x18048af03  mov     rax, 7FFFFFFFFFFFFFFFh
0x18048af0d  cmp     r15, rax
0x18048af10  ja      loc_18048B184
0x18048af16  lfence
0x18048af19  mov     rcx, r15
0x18048af1c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x18048af21  mov     rbx, rax
0x18048af24  mov     r12, rax
0x18048af27  mov     qword ptr [rsp+140h+var_F0], rax
0x18048af2c  lea     r14, [rax+r15]
0x18048af30  mov     [rsp+140h+var_E0], r14
0x18048af35  mov     r8, r15; Size
0x18048af38  xor     edx, edx; Val
0x18048af3a  mov     rcx, rax; void *
0x18048af3d  call    memset_0
0x18048af42  mov     qword ptr [rsp+140h+var_F0+8], r14
0x18048af47  mov     rsi, r14
0x18048af4a  jmp     short loc_18048AF51
0x18048af4c  mov     r12, qword ptr [rsp+140h+var_F0]
0x18048af51  mov     [rsp+140h+var_120], 3
0x18048af59  mov     rax, rsi
0x18048af5c  sub     rax, rbx
0x18048af5f  mov     qword ptr [rsp+140h+var_110], r12
0x18048af64  mov     qword ptr [rsp+140h+var_110+8], rax
0x18048af69  movaps  xmm0, [rsp+140h+var_110]
0x18048af6e  movdqa  [rbp+40h+var_C0], xmm0
0x18048af73  movaps  xmm1, [rsp+140h+var_D0]
0x18048af78  movdqa  [rbp+40h+var_B0], xmm1
0x18048af7d  lea     r9, [rbp+40h+arg_18]
0x18048af81  lea     r8, [rbp+40h+var_C0]
0x18048af85  lea     rdx, [rbp+40h+var_B0]
0x18048af89  mov     rcx, [rbp+40h+arg_0]
0x18048af8d  call    ?ReadBinaryDataUri@GLTFResourceReader@glTF@Microsoft@@AEBAXUBase64StringView@23@UBase64BufferView@23@PEB_J@Z; Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(Microsoft::glTF::Base64StringView,Microsoft::glTF::Base64BufferView,__int64 const *)
0x18048af92  lea     rax, [rsp+140h+var_F0]
0x18048af97  cmp     rdi, rax
0x18048af9a  jz      short loc_18048AFFA
0x18048af9c  mov     rcx, [rdi]
0x18048af9f  test    rcx, rcx
0x18048afa2  jz      short loc_18048AFE7
0x18048afa4  mov     rdx, [rdi+10h]
0x18048afa8  sub     rdx, rcx
0x18048afab  cmp     rdx, 1000h
0x18048afb2  jb      short loc_18048AFCC
0x18048afb4  add     rdx, 27h ; '''
0x18048afb8  mov     r8, [rcx-8]
0x18048afbc  sub     rcx, r8
0x18048afbf  lea     rax, [rcx-8]
0x18048afc3  cmp     rax, 1Fh
0x18048afc7  ja      short loc_18048AFE0
0x18048afc9  mov     rcx, r8; Block
0x18048afcc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18048afd1  xor     eax, eax
0x18048afd3  mov     [rdi], rax
0x18048afd6  mov     [rdi+8], rax
0x18048afda  mov     [rdi+10h], rax
0x18048afde  jmp     short loc_18048AFE9
0x18048afe0  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18048afe7  xor     eax, eax
0x18048afe9  mov     [rdi], rbx
0x18048afec  mov     [rdi+8], rsi
0x18048aff0  mov     [rdi+10h], r14
0x18048aff4  mov     rbx, rax
0x18048aff7  mov     rsi, rax
0x18048affa  test    rbx, rbx
0x18048affd  jz      loc_18048B14C
0x18048b003  sub     rsi, rbx
0x18048b006  cmp     rsi, 1000h
0x18048b00d  jb      short loc_18048B027
0x18048b00f  add     rsi, 27h ; '''
0x18048b013  mov     rcx, [rbx-8]
0x18048b017  sub     rbx, rcx
0x18048b01a  lea     rax, [rbx-8]
0x18048b01e  cmp     rax, 1Fh
0x18048b022  ja      short loc_18048B037
0x18048b024  mov     rbx, rcx
0x18048b027  mov     rdx, rsi
0x18048b02a  mov     rcx, rbx; Block
0x18048b02d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18048b032  jmp     loc_18048B14C
0x18048b037  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18048b03e  mov     r14, [rdi+8]
0x18048b042  mov     rdx, [rdi]
0x18048b045  mov     rcx, r14
0x18048b048  sub     rcx, rdx
0x18048b04b  mov     rsi, [rbp+40h+Size]
0x18048b04f  cmp     rsi, rcx
0x18048b052  jnb     short loc_18048B05A
0x18048b054  lea     rax, [rdx+rsi]
0x18048b058  jmp     short loc_18048B097
0x18048b05a  jbe     short loc_18048B09B
0x18048b05c  mov     rax, [rdi+10h]
0x18048b060  sub     rax, rdx
0x18048b063  cmp     rsi, rax
0x18048b066  jbe     short loc_18048B080
0x18048b068  lfence
0x18048b06b  lea     r8, [rbp+40h+arg_10]
0x18048b06f  mov     rdx, rsi
0x18048b072  mov     rcx, rdi
0x18048b075  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@CV?$allocator@C@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<signed char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18048b07a  mov     r15, [rbp+40h+arg_18]
0x18048b07e  jmp     short loc_18048B09B
0x18048b080  mov     rbx, rsi
0x18048b083  sub     rbx, rcx
0x18048b086  mov     r8, rbx; Size
0x18048b089  xor     edx, edx; Val
0x18048b08b  mov     rcx, r14; void *
0x18048b08e  call    memset_0
0x18048b093  lea     rax, [r14+rbx]
0x18048b097  mov     [rdi+8], rax
0x18048b09b  mov     rax, [r12]
0x18048b09f  mov     r8, r13
0x18048b0a2  lea     rdx, [rsp+140h+var_110]
0x18048b0a7  mov     rcx, r12
0x18048b0aa  call    qword ptr [rax+8]
0x18048b0ad  nop
0x18048b0ae  mov     rax, [r12]
0x18048b0b2  mov     r8, r13
0x18048b0b5  lea     rdx, [rbp+40h+var_A0]
0x18048b0b9  mov     rcx, r12
0x18048b0bc  call    qword ptr [rax+10h]
0x18048b0bf  movups  xmm0, [rbp+40h+var_A0]
0x18048b0c3  movaps  [rbp+40h+var_80], xmm0
0x18048b0c7  movsd   xmm1, [rbp+40h+var_90]
0x18048b0cc  movsd   [rbp+40h+var_70], xmm1
0x18048b0d1  lea     rdx, [rbp+40h+var_80]
0x18048b0d5  mov     rcx, qword ptr [rsp+140h+var_110]
0x18048b0da  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x18048b0e0  mov     r8d, 1
0x18048b0e6  mov     rdx, r15
0x18048b0e9  mov     rcx, qword ptr [rsp+140h+var_110]
0x18048b0ee  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x18048b0f4  mov     rbx, qword ptr [rsp+140h+var_110]
0x18048b0f9  mov     r8, rsi
0x18048b0fc  mov     rdx, [rdi]
0x18048b0ff  mov     rcx, rbx
0x18048b102  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18048b108  mov     rax, [rbx]
0x18048b10b  movsxd  rcx, dword ptr [rax+4]
0x18048b10f  test    byte ptr [rcx+rbx+10h], 6
0x18048b114  jnz     short loc_18048B163
0x18048b116  mov     rbx, qword ptr [rsp+140h+var_110+8]
0x18048b11b  test    rbx, rbx
0x18048b11e  jz      short loc_18048B14C
0x18048b120  mov     esi, 0FFFFFFFFh
0x18048b125  mov     eax, esi
0x18048b127  lock xadd [rbx+8], eax
0x18048b12c  cmp     eax, 1
0x18048b12f  jnz     short loc_18048B14C
0x18048b131  mov     rax, [rbx]
0x18048b134  mov     rcx, rbx
0x18048b137  call    qword ptr [rax]
0x18048b139  lock xadd [rbx+0Ch], esi
0x18048b13e  cmp     esi, 1
0x18048b141  jnz     short loc_18048B14C
0x18048b143  mov     rax, [rbx]
0x18048b146  mov     rcx, rbx
0x18048b149  call    qword ptr [rax+8]
0x18048b14c  mov     rax, rdi
0x18048b14f  add     rsp, 108h
0x18048b156  pop     r15
0x18048b158  pop     r14
0x18048b15a  pop     r13
0x18048b15c  pop     r12
0x18048b15e  pop     rdi
0x18048b15f  pop     rsi
0x18048b160  pop     rbx
0x18048b161  pop     rbp
0x18048b162  retn
0x18048b163  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x18048b16a  lea     rcx, [rbp+40h+pExceptionObject]; this
0x18048b16e  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18048b173  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18048b17a  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18048b17e  call    _CxxThrowException_0
0x18048b184  call    ?_Xlength@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@CAXXZ; std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(void)
```
