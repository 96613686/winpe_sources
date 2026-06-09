# Microsoft::glTF::GLTFResourceReader::ReadBinaryData<float>(Microsoft::glTF::Buffer const &,__int64,unsigned __int64)

- ea: `0x1802ac550`
- end: `0x1802ac8cb`
- name: `??$ReadBinaryData@M@GLTFResourceReader@glTF@Microsoft@@AEBA?AV?$vector@MV?$allocator@M@std@@@std@@AEBUBuffer@12@_J_K@Z`
- size: `891`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64, __int64, unsigned __int64)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1802ab7b0`
- `0x1802adb20`
- `0x1802af880`
- `0x1802afdd0`
- `0x1802b0310`

## callees

- `0x180014a60`
- `0x18001ebf0`
- `0x18002c200`
- `0x180040860`
- `0x1801f8750`
- `0x1802ac550`
- `0x1802b3b80`
- `0x1802c2bf0`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802ac822`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802ac822`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802ac80a`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802ac80a`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802ac7f7`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802ac7f7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac65e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac72b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac65e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac72b`

## string_xrefs

- `0x1802ac89c`: `Cannot read the binary data`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Microsoft::glTF::GLTFResourceReader::ReadBinaryData<float>(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  size_t v11; // rsi
  void *v12; // rax
  char *v13; // r14
  void *v14; // rcx
  __int64 v15; // r14
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  size_t v19; // rbx
  __int64 v20; // rbx
  volatile signed __int32 *v21; // rbx
  char v23[4]; // [rsp+20h] [rbp-91h] BYREF
  int v24; // [rsp+24h] [rbp-8Dh]
  void *Block[2]; // [rsp+30h] [rbp-81h] BYREF
  char *v26; // [rsp+40h] [rbp-71h]
  _QWORD v27[2]; // [rsp+50h] [rbp-61h] BYREF
  __int128 v28; // [rsp+60h] [rbp-51h] BYREF
  __int64 *v29; // [rsp+70h] [rbp-41h]
  __int128 v30; // [rsp+80h] [rbp-31h] BYREF
  __int64 v31; // [rsp+90h] [rbp-21h] BYREF
  __int128 v32; // [rsp+98h] [rbp-19h] BYREF
  char *v33; // [rsp+A8h] [rbp-9h]

  v29 = a2;
  v31 = a4;
  v9 = 0;
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v24 = 1;
  v27[0] = 0;
  *(_QWORD *)&v28 = 0;
  if ( (unsigned __int8)Microsoft::glTF::IsUriBase64((void *)(a3 + 232)) )
  {
    v27[1] = v28;
    *(_OWORD *)Block = 0;
    v26 = 0;
    if ( a5 )
    {
      if ( a5 > 0x3FFFFFFFFFFFFFFFLL )
        std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(v28, v10);
      v11 = 4 * a5;
      if ( 4 * a5 < 0x1000 )
      {
        if ( v11 )
          v9 = operator new(v11);
      }
      else
      {
        if ( v11 + 39 < v11 )
          __scrt_throw_std_bad_array_new_length();
        v12 = operator new(v11 + 39);
        if ( !v12 )
          _invalid_parameter_noinfo_noreturn();
        v9 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v12;
      }
      Block[0] = v9;
      v13 = (char *)v9 + v11;
      v26 = (char *)v9 + v11;
      memset_0(v9, 0, v11);
      Block[1] = (char *)v9 + v11;
    }
    else
    {
      v13 = (char *)Block[1];
    }
    v24 = 3;
    *(void **)&v30 = Block[0];
    *((_QWORD *)&v30 + 1) = 4 * ((v13 - (char *)Block[0]) >> 2);
    v28 = v30;
    Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(a1, v27, &v28, &v31);
    std::vector<float>::operator=(a2, Block);
    v14 = Block[0];
    if ( Block[0] )
    {
      if ( ((v26 - (char *)Block[0]) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
      {
        v14 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v14);
    }
    return a2;
  }
  v15 = a2[1];
  v16 = *a2;
  v17 = (v15 - *a2) >> 2;
  if ( a5 < v17 )
  {
    v18 = v16 + 4 * a5;
LABEL_24:
    a2[1] = v18;
    goto LABEL_25;
  }
  if ( a5 > v17 )
  {
    if ( a5 <= (a2[2] - v16) >> 2 )
    {
      v19 = 4 * (a5 - v17);
      memset_0((void *)a2[1], 0, v19);
      v18 = v19 + v15;
      goto LABEL_24;
    }
    std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(a2, a5, v23);
  }
LABEL_25:
  v30 = 0;
  (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 8LL))(a1, &v30, a3);
  (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 16LL))(a1, &v32, a3);
  *(_OWORD *)Block = v32;
  v26 = v33;
  std::istream::seekg(v30, Block);
  std::istream::seekg(v30, a4, 1);
  v20 = v30;
  std::istream::read(v30, *a2, 4 * a5);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v20 + 4LL) + v20 + 16) & 6) != 0 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)Block, "Cannot read the binary data");
    throw (std::runtime_error *)Block;
  }
  v21 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
  if ( *((_QWORD *)&v30 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1802ac550  push    rbp
0x1802ac552  push    rbx
0x1802ac553  push    rsi
0x1802ac554  push    rdi
0x1802ac555  push    r12
0x1802ac557  push    r13
0x1802ac559  push    r14
0x1802ac55b  push    r15
0x1802ac55d  lea     rbp, [rsp-17h]
0x1802ac562  sub     rsp, 0C8h
0x1802ac569  mov     rax, cs:__security_cookie
0x1802ac570  xor     rax, rsp
0x1802ac573  mov     [rbp+4Fh+var_50], rax
0x1802ac577  mov     r12, r9
0x1802ac57a  mov     r15, r8
0x1802ac57d  mov     rdi, rdx
0x1802ac580  mov     r13, rcx
0x1802ac583  mov     [rbp+4Fh+var_90], rdx
0x1802ac587  mov     [rbp+4Fh+var_70], r9
0x1802ac58b  xor     ebx, ebx
0x1802ac58d  mov     [rsp+100h+var_DC], ebx
0x1802ac591  xorps   xmm0, xmm0
0x1802ac594  movups  xmmword ptr [rdx], xmm0
0x1802ac597  mov     [rdx], rbx
0x1802ac59a  mov     [rdx+8], rbx
0x1802ac59e  mov     [rdx+10h], rbx
0x1802ac5a2  mov     [rsp+100h+var_DC], 1
0x1802ac5aa  mov     qword ptr [rbp+4Fh+var_B0], rbx
0x1802ac5ae  mov     qword ptr [rbp+4Fh+var_A0], rbx
0x1802ac5b2  lea     rcx, [r8+0E8h]; Buf
0x1802ac5b9  lea     r8, [rbp+4Fh+var_A0]
0x1802ac5bd  lea     rdx, [rbp+4Fh+var_B0]
0x1802ac5c1  call    ?IsUriBase64@glTF@Microsoft@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@4@1@Z; Microsoft::glTF::IsUriBase64(std::string const &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &)
0x1802ac5c6  test    al, al
0x1802ac5c8  jz      loc_1802AC73C
0x1802ac5ce  mov     rax, qword ptr [rbp+4Fh+var_B0]
0x1802ac5d2  mov     qword ptr [rbp+4Fh+var_B0], rax
0x1802ac5d6  mov     rcx, qword ptr [rbp+4Fh+var_A0]
0x1802ac5da  mov     qword ptr [rbp+4Fh+var_B0+8], rcx
0x1802ac5de  cmp     rax, rcx
0x1802ac5e1  jz      short loc_1802AC5FB
0x1802ac5e3  mov     rdx, rcx
0x1802ac5e6  cmp     byte ptr [rdx-1], 3Dh ; '='
0x1802ac5ea  jnz     short loc_1802AC5FB
0x1802ac5ec  dec     rcx
0x1802ac5ef  mov     rdx, rcx
0x1802ac5f2  mov     qword ptr [rbp+4Fh+var_B0+8], rcx
0x1802ac5f6  cmp     rax, rcx
0x1802ac5f9  jnz     short loc_1802AC5E6
0x1802ac5fb  xorps   xmm1, xmm1
0x1802ac5fe  movdqu  xmmword ptr [rsp+100h+Block], xmm1
0x1802ac604  mov     [rbp+4Fh+var_C0], rbx
0x1802ac608  mov     rsi, [rbp+4Fh+arg_20]
0x1802ac60c  test    rsi, rsi
0x1802ac60f  jz      loc_1802AC695
0x1802ac615  mov     rax, 3FFFFFFFFFFFFFFFh
0x1802ac61f  cmp     rsi, rax
0x1802ac622  ja      loc_1802AC8BF
0x1802ac628  lea     rsi, ds:0[rsi*4]
0x1802ac630  cmp     rsi, 1000h
0x1802ac637  jb      short loc_1802AC665
0x1802ac639  lea     rcx, [rsi+27h]; Size
0x1802ac63d  cmp     rcx, rsi
0x1802ac640  jbe     loc_1802AC8C5
0x1802ac646  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802ac64b  test    rax, rax
0x1802ac64e  jz      short loc_1802AC65E
0x1802ac650  lea     rbx, [rax+27h]
0x1802ac654  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1802ac658  mov     [rbx-8], rax
0x1802ac65c  jmp     short loc_1802AC675
0x1802ac65e  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802ac665  test    rsi, rsi
0x1802ac668  jz      short loc_1802AC675
0x1802ac66a  mov     rcx, rsi; Size
0x1802ac66d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802ac672  mov     rbx, rax
0x1802ac675  mov     [rsp+100h+Block], rbx
0x1802ac67a  lea     r14, [rbx+rsi]
0x1802ac67e  mov     [rbp+4Fh+var_C0], r14
0x1802ac682  mov     r8, rsi; Size
0x1802ac685  xor     edx, edx; Val
0x1802ac687  mov     rcx, rbx; void *
0x1802ac68a  call    memset_0
0x1802ac68f  mov     [rbp+4Fh+Block+8], r14
0x1802ac693  jmp     short loc_1802AC699
0x1802ac695  mov     r14, [rbp+4Fh+Block+8]
0x1802ac699  mov     [rsp+100h+var_DC], 3
0x1802ac6a1  mov     rax, [rsp+100h+Block]
0x1802ac6a6  sub     r14, rax
0x1802ac6a9  sar     r14, 2
0x1802ac6ad  mov     qword ptr [rbp+4Fh+var_80], rax
0x1802ac6b1  lea     rax, ds:0[r14*4]
0x1802ac6b9  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x1802ac6bd  movaps  xmm0, [rbp+4Fh+var_80]
0x1802ac6c1  movdqa  [rbp+4Fh+var_A0], xmm0
0x1802ac6c6  movaps  xmm1, [rbp+4Fh+var_B0]
0x1802ac6ca  movdqa  [rbp+4Fh+var_B0], xmm1
0x1802ac6cf  lea     r9, [rbp+4Fh+var_70]
0x1802ac6d3  lea     r8, [rbp+4Fh+var_A0]
0x1802ac6d7  lea     rdx, [rbp+4Fh+var_B0]
0x1802ac6db  mov     rcx, r13
0x1802ac6de  call    ?ReadBinaryDataUri@GLTFResourceReader@glTF@Microsoft@@AEBAXUBase64StringView@23@UBase64BufferView@23@PEB_J@Z; Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(Microsoft::glTF::Base64StringView,Microsoft::glTF::Base64BufferView,__int64 const *)
0x1802ac6e3  lea     rdx, [rsp+100h+Block]
0x1802ac6e8  mov     rcx, rdi
0x1802ac6eb  call    ??4?$vector@MV?$allocator@M@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<float>::operator=(std::vector<float> &&)
0x1802ac6f0  nop
0x1802ac6f1  mov     rcx, [rsp+100h+Block]; Block
0x1802ac6f6  test    rcx, rcx
0x1802ac6f9  jz      loc_1802AC879
0x1802ac6ff  mov     rdx, [rbp+4Fh+var_C0]
0x1802ac703  sub     rdx, rcx
0x1802ac706  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1802ac70a  mov     rax, rcx
0x1802ac70d  cmp     rdx, 1000h
0x1802ac714  jb      short loc_1802AC732
0x1802ac716  add     rdx, 27h ; '''
0x1802ac71a  mov     rcx, [rcx-8]
0x1802ac71e  sub     rax, rcx
0x1802ac721  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802ac725  cmp     rax, 1Fh
0x1802ac729  jbe     short loc_1802AC732
0x1802ac72b  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802ac732  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802ac737  jmp     loc_1802AC879
0x1802ac73c  mov     r14, [rdi+8]
0x1802ac740  mov     rdx, [rdi]
0x1802ac743  mov     rcx, r14
0x1802ac746  sub     rcx, rdx
0x1802ac749  sar     rcx, 2
0x1802ac74d  mov     rsi, [rbp+4Fh+arg_20]
0x1802ac751  cmp     rsi, rcx
0x1802ac754  jnb     short loc_1802AC75C
0x1802ac756  lea     rax, [rdx+rsi*4]
0x1802ac75a  jmp     short loc_1802AC79F
0x1802ac75c  jbe     short loc_1802AC7A3
0x1802ac75e  mov     rax, [rdi+10h]
0x1802ac762  sub     rax, rdx
0x1802ac765  sar     rax, 2
0x1802ac769  cmp     rsi, rax
0x1802ac76c  jbe     short loc_1802AC780
0x1802ac76e  lea     r8, [rsp+100h+var_E0]
0x1802ac773  mov     rdx, rsi
0x1802ac776  mov     rcx, rdi
0x1802ac779  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@MV?$allocator@M@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<float>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1802ac77e  jmp     short loc_1802AC7A3
0x1802ac780  mov     rax, rsi
0x1802ac783  sub     rax, rcx
0x1802ac786  lea     rbx, ds:0[rax*4]
0x1802ac78e  mov     r8, rbx; Size
0x1802ac791  xor     edx, edx; Val
0x1802ac793  mov     rcx, r14; void *
0x1802ac796  call    memset_0
0x1802ac79b  lea     rax, [rbx+r14]
0x1802ac79f  mov     [rdi+8], rax
0x1802ac7a3  xorps   xmm0, xmm0
0x1802ac7a6  movups  [rbp+4Fh+var_80], xmm0
0x1802ac7aa  mov     rax, [r13+0]
0x1802ac7ae  mov     r8, r15
0x1802ac7b1  lea     rdx, [rbp+4Fh+var_80]
0x1802ac7b5  mov     rcx, r13
0x1802ac7b8  mov     rax, [rax+8]
0x1802ac7bc  call    cs:__guard_dispatch_icall_fptr
0x1802ac7c2  nop
0x1802ac7c3  mov     rax, [r13+0]
0x1802ac7c7  mov     r8, r15
0x1802ac7ca  lea     rdx, [rbp+4Fh+var_68]
0x1802ac7ce  mov     rcx, r13
0x1802ac7d1  mov     rax, [rax+10h]
0x1802ac7d5  call    cs:__guard_dispatch_icall_fptr
0x1802ac7db  movups  xmm0, [rbp+4Fh+var_68]
0x1802ac7df  movaps  xmmword ptr [rsp+100h+Block], xmm0
0x1802ac7e4  movsd   xmm1, [rbp+4Fh+var_58]
0x1802ac7e9  movsd   [rbp+4Fh+var_C0], xmm1
0x1802ac7ee  lea     rdx, [rsp+100h+Block]
0x1802ac7f3  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x1802ac7f7  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x1802ac7fd  mov     r8d, 1
0x1802ac803  mov     rdx, r12
0x1802ac806  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x1802ac80a  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802ac810  lea     r8, ds:0[rsi*4]
0x1802ac818  mov     rbx, qword ptr [rbp+4Fh+var_80]
0x1802ac81c  mov     rdx, [rdi]
0x1802ac81f  mov     rcx, rbx
0x1802ac822  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1802ac828  mov     rax, [rbx]
0x1802ac82b  movsxd  rcx, dword ptr [rax+4]
0x1802ac82f  test    byte ptr [rcx+rbx+10h], 6
0x1802ac834  jnz     short loc_1802AC89C
0x1802ac836  mov     rbx, qword ptr [rbp+4Fh+var_80+8]
0x1802ac83a  test    rbx, rbx
0x1802ac83d  jz      short loc_1802AC879
0x1802ac83f  mov     esi, 0FFFFFFFFh
0x1802ac844  mov     eax, esi
0x1802ac846  lock xadd [rbx+8], eax
0x1802ac84b  cmp     eax, 1
0x1802ac84e  jnz     short loc_1802AC879
0x1802ac850  mov     rax, [rbx]
0x1802ac853  mov     rcx, rbx
0x1802ac856  mov     rax, [rax]
0x1802ac859  call    cs:__guard_dispatch_icall_fptr
0x1802ac85f  lock xadd [rbx+0Ch], esi
0x1802ac864  cmp     esi, 1
0x1802ac867  jnz     short loc_1802AC879
0x1802ac869  mov     rdx, [rbx]
0x1802ac86c  mov     rcx, rbx
0x1802ac86f  mov     rax, [rdx+8]
0x1802ac873  call    cs:__guard_dispatch_icall_fptr
0x1802ac879  mov     rax, rdi
0x1802ac87c  mov     rcx, [rbp+4Fh+var_50]
0x1802ac880  xor     rcx, rsp; StackCookie
0x1802ac883  call    __security_check_cookie
0x1802ac888  add     rsp, 0C8h
0x1802ac88f  pop     r15
0x1802ac891  pop     r14
0x1802ac893  pop     r13
0x1802ac895  pop     r12
0x1802ac897  pop     rdi
0x1802ac898  pop     rsi
0x1802ac899  pop     rbx
0x1802ac89a  pop     rbp
0x1802ac89b  retn
0x1802ac89c  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x1802ac8a3  lea     rcx, [rsp+100h+Block]; this
0x1802ac8a8  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1802ac8ad  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1802ac8b4  lea     rcx, [rsp+100h+Block]; pExceptionObject
0x1802ac8b9  call    _CxxThrowException_0
0x1802ac8bf  call    ?_Xlength@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@CAXXZ; std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(void)
0x1802ac8c5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
