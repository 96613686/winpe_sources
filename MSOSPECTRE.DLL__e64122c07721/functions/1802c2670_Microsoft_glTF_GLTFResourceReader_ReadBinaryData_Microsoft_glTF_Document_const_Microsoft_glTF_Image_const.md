# Microsoft::glTF::GLTFResourceReader::ReadBinaryData(Microsoft::glTF::Document const &,Microsoft::glTF::Image const &)

- ea: `0x1802c2670`
- end: `0x1802c2bed`
- name: `?ReadBinaryData@GLTFResourceReader@glTF@Microsoft@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@AEBVDocument@23@AEBUImage@23@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1802bf9b0`
- `0x180398bf0`

## callees

- `0x180014a60`
- `0x180015770`
- `0x18001dd60`
- `0x18001ebf0`
- `0x18002b7a0`
- `0x18002beb0`
- `0x18002c200`
- `0x18002eb54`
- `0x1801b2140`
- `0x1801b2320`
- `0x1801b3940`
- `0x1802ab950`
- `0x1802c2670`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802c2a41`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802c2a41`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1802c2990`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1802c2990`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802c2983`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802c29a5`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802c2983`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802c29a5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2788`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2829`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c292a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2a01`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2a99`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2788`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2829`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c292a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2a01`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802c2a99`

## string_xrefs

- `0x1802c2b0a`: `Cannot read the binary data`
- `0x1802c2bc0`: `Cannot read the binary data`
- `0x1802c2b5a`: `Invalid image, both uri and bufferView are unspecified`
- `0x1802c2b2b`: `Unable to read image data`
- `0x1802c2b91`: `Offset position as a base64 character index is outside the input range`

## pseudocode

```c
__int64 __fastcall Microsoft::glTF::GLTFResourceReader::ReadBinaryData(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  Microsoft::glTF::Validation *v7; // rdi
  const struct Microsoft::glTF::BufferView *v8; // rax
  int v9; // ebx
  const struct Microsoft::glTF::Buffer *v10; // r8
  void *v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rbx
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // r14
  void *v16; // rax
  void *v17; // rcx
  _QWORD *v18; // rax
  char *v19; // rsi
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rsi
  __int64 v22; // rsi
  _QWORD *v23; // rax
  size_t v24; // rdi
  void *v25; // rax
  void *v26; // rcx
  _QWORD *v27; // rax
  char *v28; // rbx
  void *v29; // rcx
  volatile signed __int32 *v30; // rbx
  void *Block[2]; // [rsp+30h] [rbp-89h] BYREF
  char *v33; // [rsp+40h] [rbp-79h]
  int v34; // [rsp+48h] [rbp-71h]
  __int128 v35; // [rsp+50h] [rbp-69h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v37[24]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v38[32]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-1h]
  __int128 v40; // [rsp+C0h] [rbp+7h] BYREF

  v39 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v34 = 1;
  *(_QWORD *)&v35 = 0;
  *(_QWORD *)&pExceptionObject[0] = 0;
  if ( a4[31] )
  {
    v12 = a4 + 29;
    if ( (unsigned __int8)Microsoft::glTF::IsUriBase64(a4 + 29) )
    {
      v13 = v35;
      *((_QWORD *)&v35 + 1) = *(_QWORD *)&pExceptionObject[0];
      v14 = *(_QWORD *)&pExceptionObject[0] - v35;
      v15 = (unsigned __int64)(3 * (*(_QWORD *)&pExceptionObject[0] - v35)) >> 2;
      *(_OWORD *)Block = 0;
      v33 = 0;
      if ( v15 )
      {
        if ( v15 < 0x1000 )
        {
          v18 = operator new((3 * v14) >> 2);
        }
        else
        {
          if ( v15 + 39 < v15 )
            __scrt_throw_std_bad_array_new_length();
          v16 = operator new(v15 + 39);
          v17 = v16;
          if ( !v16 )
            _invalid_parameter_noinfo_noreturn();
          v18 = (_QWORD *)(((unsigned __int64)v16 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v18 - 1) = v17;
        }
        Block[0] = v18;
        v19 = (char *)v18 + v15;
        v33 = (char *)v18 + v15;
        memset_0(v18, 0, (3 * v14) >> 2);
        Block[1] = v19;
      }
      else
      {
        v19 = (char *)Block[1];
      }
      v34 = 5;
      *(void **)&v40 = Block[0];
      *((_QWORD *)&v40 + 1) = v19 - (char *)Block[0];
      pExceptionObject[0] = v35;
      v20 = 4 * ((v19 - (char *)Block[0]) / 3uLL);
      v21 = (v19 - (char *)Block[0]) % 3uLL - 1;
      if ( v21 )
      {
        if ( v21 == 1 )
          v20 += 3LL;
      }
      else
      {
        v20 += 2LL;
      }
      if ( v20 > v14 )
      {
        std::string::string(v38, "Offset position as a base64 character index is outside the input range");
        Microsoft::glTF::GLTFException::GLTFException(v37, v38);
        throw (Microsoft::glTF::GLTFException *)v37;
      }
      *((_QWORD *)&pExceptionObject[0] + 1) = v20 + v13;
      v35 = v40;
      Microsoft::glTF::Base64Decode(pExceptionObject, &v35, 0);
      std::vector<unsigned char>::operator=(a2, Block);
      v11 = Block[0];
      if ( Block[0] )
      {
        if ( (unsigned __int64)(v33 - (char *)Block[0]) >= 0x1000 )
        {
          v11 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v11 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        goto LABEL_26;
      }
    }
    else
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD *))(**(_QWORD **)(a1 + 8) + 8LL))(
        *(_QWORD *)(a1 + 8),
        &v40,
        v12);
      v22 = v40;
      if ( !(_QWORD)v40 )
      {
        std::string::string(v38, "Unable to read image data");
        Microsoft::glTF::GLTFException::GLTFException(v37, v38);
        throw (Microsoft::glTF::GLTFException *)v37;
      }
      if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v40 + 4LL) + (_QWORD)v40 + 16LL) & 6) != 0 )
      {
        std::runtime_error::runtime_error((std::runtime_error *)v37, "Cannot read the binary data");
        throw (std::runtime_error *)v37;
      }
      std::istream::seekg(v40, 0, 2);
      v23 = (_QWORD *)std::istream::tellg(v22, v38);
      v24 = *v23 + v23[1];
      std::istream::seekg(v22, 0, 0);
      *(_OWORD *)Block = 0;
      v33 = 0;
      if ( v24 )
      {
        if ( v24 > 0x7FFFFFFFFFFFFFFFLL )
          std::vector<Microsoft::glTF::Buffer>::_Xlength();
        if ( v24 < 0x1000 )
        {
          v27 = operator new(v24);
        }
        else
        {
          if ( v24 + 39 < v24 )
            __scrt_throw_std_bad_array_new_length();
          v25 = operator new(v24 + 39);
          v26 = v25;
          if ( !v25 )
            _invalid_parameter_noinfo_noreturn();
          v27 = (_QWORD *)(((unsigned __int64)v25 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v27 - 1) = v26;
        }
        Block[0] = v27;
        v28 = (char *)v27 + v24;
        v33 = (char *)v27 + v24;
        memset_0(v27, 0, v24);
        Block[1] = v28;
      }
      v34 = 9;
      std::istream::read(v22, Block[0], v24);
      if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v22 + 4LL) + v22 + 16) & 6) != 0 )
      {
        std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Cannot read the binary data");
        throw (std::runtime_error *)pExceptionObject;
      }
      std::vector<unsigned char>::operator=(a2, Block);
      v29 = Block[0];
      if ( Block[0] )
      {
        if ( (unsigned __int64)(v33 - (char *)Block[0]) >= 0x1000 )
        {
          v29 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v29 - 8) > 0x1F )
            _invalid_parameter_noinfo_noreturn();
        }
        operator delete(v29);
      }
      v30 = (volatile signed __int32 *)*((_QWORD *)&v40 + 1);
      if ( *((_QWORD *)&v40 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
    }
  }
  else
  {
    if ( !a4[39] )
    {
      std::string::string(v38, "Invalid image, both uri and bufferView are unspecified");
      Microsoft::glTF::GLTFException::GLTFException(Block, v38);
      throw (Microsoft::glTF::GLTFException *)Block;
    }
    v7 = (Microsoft::glTF::Validation *)Microsoft::glTF::IndexedContainer<Microsoft::glTF::BufferView const,1>::operator[](
                                          a3 + 728,
                                          a4 + 37);
    v8 = (const struct Microsoft::glTF::BufferView *)Microsoft::glTF::IndexedContainer<Microsoft::glTF::Buffer const,1>::operator[](
                                                       a3 + 640,
                                                       (char *)v7 + 232);
    v9 = (int)v8;
    Microsoft::glTF::Validation::ValidateBufferView(v7, v8, v10);
    Microsoft::glTF::GLTFResourceReader::ReadBinaryData<unsigned char>(
      a1,
      (int)Block,
      v9,
      *((_QWORD *)v7 + 33),
      *((_QWORD *)v7 + 34));
    std::vector<unsigned char>::operator=(a2, Block);
    v11 = Block[0];
    if ( Block[0] )
    {
      if ( (unsigned __int64)(v33 - (char *)Block[0]) >= 0x1000 )
      {
        v11 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v11 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
LABEL_26:
      operator delete(v11);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1802c2670  push    rbp
0x1802c2672  push    rbx
0x1802c2673  push    rsi
0x1802c2674  push    rdi
0x1802c2675  push    r12
0x1802c2677  push    r14
0x1802c2679  push    r15
0x1802c267b  lea     rbp, [rsp-27h]
0x1802c2680  sub     rsp, 0E0h
0x1802c2687  mov     rax, cs:__security_cookie
0x1802c268e  xor     rax, rsp
0x1802c2691  mov     [rbp+57h+var_40], rax
0x1802c2695  mov     rbx, r8
0x1802c2698  mov     r15, rdx
0x1802c269b  mov     rsi, rcx
0x1802c269e  mov     [rbp+57h+var_58], rdx
0x1802c26a2  xor     r12d, r12d
0x1802c26a5  mov     [rbp+57h+var_C8], r12d
0x1802c26a9  xorps   xmm0, xmm0
0x1802c26ac  movups  xmmword ptr [rdx], xmm0
0x1802c26af  mov     [rdx], r12
0x1802c26b2  mov     [rdx+8], r12
0x1802c26b6  mov     [rdx+10h], r12
0x1802c26ba  mov     [rbp+57h+var_C8], 1
0x1802c26c1  mov     qword ptr [rbp+57h+var_C0], r12
0x1802c26c5  mov     qword ptr [rbp+57h+pExceptionObject], r12
0x1802c26c9  cmp     [r9+0F8h], r12
0x1802c26d0  jnz     loc_1802C278F
0x1802c26d6  cmp     [r9+138h], r12
0x1802c26dd  jz      loc_1802C2B5A
0x1802c26e3  lea     rdx, [r9+128h]
0x1802c26ea  lea     rcx, [r8+2D8h]
0x1802c26f1  call    ??A?$IndexedContainer@$$CBUBufferView@glTF@Microsoft@@$00@glTF@Microsoft@@QEBAAEBUBufferView@12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::IndexedContainer<Microsoft::glTF::BufferView const,1>::operator[](std::string const &)
0x1802c26f6  mov     rdi, rax
0x1802c26f9  lea     rdx, [rax+0E8h]
0x1802c2700  lea     rcx, [rbx+280h]
0x1802c2707  call    ??A?$IndexedContainer@$$CBUBuffer@glTF@Microsoft@@$00@glTF@Microsoft@@QEBAAEBUBuffer@12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::glTF::IndexedContainer<Microsoft::glTF::Buffer const,1>::operator[](std::string const &)
0x1802c270c  mov     rbx, rax
0x1802c270f  mov     rdx, rax; struct Microsoft::glTF::BufferView *
0x1802c2712  mov     rcx, rdi; this
0x1802c2715  call    ?ValidateBufferView@Validation@glTF@Microsoft@@YAXAEBUBufferView@23@AEBUBuffer@23@@Z; Microsoft::glTF::Validation::ValidateBufferView(Microsoft::glTF::BufferView const &,Microsoft::glTF::Buffer const &)
0x1802c271a  mov     rax, [rdi+110h]
0x1802c2721  mov     [rsp+110h+Size], rax; Size
0x1802c2726  mov     r9, [rdi+108h]; int
0x1802c272d  mov     r8, rbx; int
0x1802c2730  lea     rdx, [rsp+110h+Block]; int
0x1802c2735  mov     rcx, rsi; int
0x1802c2738  call    ??$ReadBinaryData@E@GLTFResourceReader@glTF@Microsoft@@AEBA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUBuffer@12@_J_K@Z; Microsoft::glTF::GLTFResourceReader::ReadBinaryData<uchar>(Microsoft::glTF::Buffer const &,__int64,unsigned __int64)
0x1802c273d  lea     rdx, [rsp+110h+Block]
0x1802c2742  mov     rcx, r15
0x1802c2745  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1802c274a  mov     rcx, [rsp+110h+Block]; Block
0x1802c274f  test    rcx, rcx
0x1802c2752  jz      loc_1802C2AE9
0x1802c2758  mov     rdx, [rbp+57h+var_D0]
0x1802c275c  sub     rdx, rcx
0x1802c275f  mov     rax, rcx
0x1802c2762  cmp     rdx, 1000h
0x1802c2769  jb      loc_1802C2931
0x1802c276f  add     rdx, 27h ; '''
0x1802c2773  mov     rcx, [rcx-8]
0x1802c2777  sub     rax, rcx
0x1802c277a  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802c277e  cmp     rax, 1Fh
0x1802c2782  jbe     loc_1802C2931
0x1802c2788  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802c278f  lea     rbx, [r9+0E8h]
0x1802c2796  lea     r8, [rbp+57h+pExceptionObject]
0x1802c279a  lea     rdx, [rbp+57h+var_C0]
0x1802c279e  mov     rcx, rbx; Buf
0x1802c27a1  call    ?IsUriBase64@glTF@Microsoft@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@4@1@Z; Microsoft::glTF::IsUriBase64(std::string const &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &)
0x1802c27a6  test    al, al
0x1802c27a8  jz      loc_1802C293B
0x1802c27ae  mov     rbx, qword ptr [rbp+57h+var_C0]
0x1802c27b2  mov     qword ptr [rbp+57h+var_C0], rbx
0x1802c27b6  mov     rdi, qword ptr [rbp+57h+pExceptionObject]
0x1802c27ba  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x1802c27be  cmp     rbx, rdi
0x1802c27c1  jz      short loc_1802C27DB
0x1802c27c3  mov     rax, rdi
0x1802c27c6  cmp     byte ptr [rax-1], 3Dh ; '='
0x1802c27ca  jnz     short loc_1802C27DB
0x1802c27cc  dec     rdi
0x1802c27cf  mov     rax, rdi
0x1802c27d2  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x1802c27d6  cmp     rbx, rdi
0x1802c27d9  jnz     short loc_1802C27C6
0x1802c27db  sub     rdi, rbx
0x1802c27de  lea     r14, [rdi+rdi*2]
0x1802c27e2  shr     r14, 2
0x1802c27e6  xorps   xmm1, xmm1
0x1802c27e9  movdqu  xmmword ptr [rsp+110h+Block], xmm1
0x1802c27ef  mov     [rbp+57h+var_D0], r12
0x1802c27f3  test    r14, r14
0x1802c27f6  jz      short loc_1802C2859
0x1802c27f8  cmp     r14, 1000h
0x1802c27ff  jb      short loc_1802C2830
0x1802c2801  lea     rcx, [r14+27h]; Size
0x1802c2805  cmp     rcx, r14
0x1802c2808  jbe     loc_1802C2B8B
0x1802c280e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802c2813  mov     rcx, rax
0x1802c2816  test    rax, rax
0x1802c2819  jz      short loc_1802C2829
0x1802c281b  add     rax, 27h ; '''
0x1802c281f  and     rax, 0FFFFFFFFFFFFFFE0h
0x1802c2823  mov     [rax-8], rcx
0x1802c2827  jmp     short loc_1802C2838
0x1802c2829  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802c2830  mov     rcx, r14; Size
0x1802c2833  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802c2838  mov     [rsp+110h+Block], rax
0x1802c283d  lea     rsi, [rax+r14]
0x1802c2841  mov     [rbp+57h+var_D0], rsi
0x1802c2845  mov     r8, r14; Size
0x1802c2848  xor     edx, edx; Val
0x1802c284a  mov     rcx, rax; void *
0x1802c284d  call    memset_0
0x1802c2852  mov     [rsp+110h+Block+8], rsi
0x1802c2857  jmp     short loc_1802C285E
0x1802c2859  mov     rsi, [rsp+110h+Block+8]
0x1802c285e  mov     [rbp+57h+var_C8], 5
0x1802c2865  mov     rax, [rsp+110h+Block]
0x1802c286a  sub     rsi, rax
0x1802c286d  mov     qword ptr [rbp+57h+var_50], rax
0x1802c2871  mov     qword ptr [rbp+57h+var_50+8], rsi
0x1802c2875  movaps  xmm0, [rbp+57h+var_C0]
0x1802c2879  movdqa  [rbp+57h+pExceptionObject], xmm0
0x1802c287e  mov     rax, 0AAAAAAAAAAAAAAABh
0x1802c2888  mul     rsi
0x1802c288b  shr     rdx, 1
0x1802c288e  lea     rcx, ds:0[rdx*4]
0x1802c2896  lea     rax, [rdx+rdx*2]
0x1802c289a  sub     rsi, rax
0x1802c289d  sub     rsi, 1
0x1802c28a1  jz      short loc_1802C28AF
0x1802c28a3  cmp     rsi, 1
0x1802c28a7  jnz     short loc_1802C28B3
0x1802c28a9  add     rcx, 3
0x1802c28ad  jmp     short loc_1802C28B3
0x1802c28af  add     rcx, 2
0x1802c28b3  cmp     rcx, rdi
0x1802c28b6  ja      loc_1802C2B91
0x1802c28bc  lea     rax, [rcx+rbx]
0x1802c28c0  mov     qword ptr [rbp+57h+pExceptionObject+8], rax
0x1802c28c4  movaps  xmm0, [rbp+57h+var_50]
0x1802c28c8  movdqa  [rbp+57h+var_C0], xmm0
0x1802c28cd  movaps  xmm1, [rbp+57h+pExceptionObject]
0x1802c28d1  movdqa  [rbp+57h+pExceptionObject], xmm1
0x1802c28d6  xor     r8d, r8d
0x1802c28d9  lea     rdx, [rbp+57h+var_C0]
0x1802c28dd  lea     rcx, [rbp+57h+pExceptionObject]
0x1802c28e1  call    ?Base64Decode@glTF@Microsoft@@YAXUBase64StringView@12@UBase64BufferView@12@_K@Z; Microsoft::glTF::Base64Decode(Microsoft::glTF::Base64StringView,Microsoft::glTF::Base64BufferView,unsigned __int64)
0x1802c28e6  lea     rdx, [rsp+110h+Block]
0x1802c28eb  mov     rcx, r15
0x1802c28ee  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1802c28f3  nop
0x1802c28f4  mov     rcx, [rsp+110h+Block]
0x1802c28f9  test    rcx, rcx
0x1802c28fc  jz      loc_1802C2AE9
0x1802c2902  mov     rdx, [rbp+57h+var_D0]
0x1802c2906  sub     rdx, rcx
0x1802c2909  mov     rax, rcx
0x1802c290c  cmp     rdx, 1000h
0x1802c2913  jb      short loc_1802C2931
0x1802c2915  add     rdx, 27h ; '''
0x1802c2919  mov     rcx, [rcx-8]
0x1802c291d  sub     rax, rcx
0x1802c2920  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802c2924  cmp     rax, 1Fh
0x1802c2928  jbe     short loc_1802C2931
0x1802c292a  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802c2931  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802c2936  jmp     loc_1802C2AE9
0x1802c293b  xorps   xmm0, xmm0
0x1802c293e  movups  [rbp+57h+var_50], xmm0
0x1802c2942  mov     rcx, [rsi+8]
0x1802c2946  mov     rax, [rcx]
0x1802c2949  mov     r8, rbx
0x1802c294c  lea     rdx, [rbp+57h+var_50]
0x1802c2950  mov     rax, [rax+8]
0x1802c2954  call    cs:__guard_dispatch_icall_fptr
0x1802c295a  nop
0x1802c295b  mov     rsi, qword ptr [rbp+57h+var_50]
0x1802c295f  test    rsi, rsi
0x1802c2962  jz      loc_1802C2B2B
0x1802c2968  mov     rax, [rsi]
0x1802c296b  movsxd  rcx, dword ptr [rax+4]
0x1802c296f  test    byte ptr [rcx+rsi+10h], 6
0x1802c2974  jnz     loc_1802C2BC0
0x1802c297a  xor     edx, edx
0x1802c297c  lea     r8d, [rdx+2]
0x1802c2980  mov     rcx, rsi
0x1802c2983  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802c2989  lea     rdx, [rbp+57h+var_78]
0x1802c298d  mov     rcx, rsi
0x1802c2990  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x1802c2996  mov     rdi, [rax+8]
0x1802c299a  add     rdi, [rax]
0x1802c299d  xor     r8d, r8d
0x1802c29a0  xor     edx, edx
0x1802c29a2  mov     rcx, rsi
0x1802c29a5  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802c29ab  xorps   xmm1, xmm1
0x1802c29ae  movdqu  xmmword ptr [rsp+110h+Block], xmm1
0x1802c29b4  mov     [rbp+57h+var_D0], r12
0x1802c29b8  test    rdi, rdi
0x1802c29bb  jz      short loc_1802C2A2F
0x1802c29bd  mov     rax, 7FFFFFFFFFFFFFFFh
0x1802c29c7  cmp     rdi, rax
0x1802c29ca  ja      loc_1802C2BE1
0x1802c29d0  cmp     rdi, 1000h
0x1802c29d7  jb      short loc_1802C2A08
0x1802c29d9  lea     rcx, [rdi+27h]; Size
0x1802c29dd  cmp     rcx, rdi
0x1802c29e0  jbe     loc_1802C2BE7
0x1802c29e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802c29eb  mov     rcx, rax
0x1802c29ee  test    rax, rax
0x1802c29f1  jz      short loc_1802C2A01
0x1802c29f3  add     rax, 27h ; '''
0x1802c29f7  and     rax, 0FFFFFFFFFFFFFFE0h
0x1802c29fb  mov     [rax-8], rcx
0x1802c29ff  jmp     short loc_1802C2A10
0x1802c2a01  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802c2a08  mov     rcx, rdi; Size
0x1802c2a0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802c2a10  mov     [rsp+110h+Block], rax
0x1802c2a15  lea     rbx, [rax+rdi]
0x1802c2a19  mov     [rbp+57h+var_D0], rbx
0x1802c2a1d  mov     r8, rdi; Size
0x1802c2a20  xor     edx, edx; Val
0x1802c2a22  mov     rcx, rax; void *
0x1802c2a25  call    memset_0
0x1802c2a2a  mov     [rsp+110h+Block+8], rbx
0x1802c2a2f  mov     [rbp+57h+var_C8], 9
0x1802c2a36  mov     r8, rdi
0x1802c2a39  mov     rdx, [rsp+110h+Block]
0x1802c2a3e  mov     rcx, rsi
0x1802c2a41  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1802c2a47  mov     rax, [rsi]
0x1802c2a4a  movsxd  rcx, dword ptr [rax+4]
0x1802c2a4e  test    byte ptr [rcx+rsi+10h], 6
0x1802c2a53  jnz     loc_1802C2B0A
0x1802c2a59  lea     rdx, [rsp+110h+Block]
0x1802c2a5e  mov     rcx, r15
0x1802c2a61  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1802c2a66  nop
0x1802c2a67  mov     rcx, [rsp+110h+Block]; Block
0x1802c2a6c  test    rcx, rcx
0x1802c2a6f  jz      short loc_1802C2AA6
0x1802c2a71  mov     rdx, [rbp+57h+var_D0]
0x1802c2a75  sub     rdx, rcx
0x1802c2a78  mov     rax, rcx
0x1802c2a7b  cmp     rdx, 1000h
0x1802c2a82  jb      short loc_1802C2AA0
0x1802c2a84  add     rdx, 27h ; '''
0x1802c2a88  mov     rcx, [rcx-8]
0x1802c2a8c  sub     rax, rcx
0x1802c2a8f  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802c2a93  cmp     rax, 1Fh
0x1802c2a97  jbe     short loc_1802C2AA0
0x1802c2a99  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802c2aa0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802c2aa5  nop
0x1802c2aa6  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x1802c2aaa  test    rbx, rbx
0x1802c2aad  jz      short loc_1802C2AE9
0x1802c2aaf  mov     edi, 0FFFFFFFFh
0x1802c2ab4  mov     eax, edi
0x1802c2ab6  lock xadd [rbx+8], eax
0x1802c2abb  cmp     eax, 1
0x1802c2abe  jnz     short loc_1802C2AE9
0x1802c2ac0  mov     rax, [rbx]
0x1802c2ac3  mov     rcx, rbx
0x1802c2ac6  mov     rax, [rax]
0x1802c2ac9  call    cs:__guard_dispatch_icall_fptr
0x1802c2acf  lock xadd [rbx+0Ch], edi
0x1802c2ad4  cmp     edi, 1
0x1802c2ad7  jnz     short loc_1802C2AE9
0x1802c2ad9  mov     rdx, [rbx]
0x1802c2adc  mov     rcx, rbx
0x1802c2adf  mov     rax, [rdx+8]
0x1802c2ae3  call    cs:__guard_dispatch_icall_fptr
0x1802c2ae9  mov     rax, r15
0x1802c2aec  mov     rcx, [rbp+57h+var_40]
0x1802c2af0  xor     rcx, rsp; StackCookie
0x1802c2af3  call    __security_check_cookie
0x1802c2af8  add     rsp, 0E0h
0x1802c2aff  pop     r15
0x1802c2b01  pop     r14
0x1802c2b03  pop     r12
0x1802c2b05  pop     rdi
0x1802c2b06  pop     rsi
0x1802c2b07  pop     rbx
0x1802c2b08  pop     rbp
0x1802c2b09  retn
0x1802c2b0a  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x1802c2b11  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1802c2b15  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
  ... truncated ...
```
