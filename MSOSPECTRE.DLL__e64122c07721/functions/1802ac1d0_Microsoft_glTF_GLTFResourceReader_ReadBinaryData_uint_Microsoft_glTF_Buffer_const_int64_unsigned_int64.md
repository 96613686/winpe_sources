# Microsoft::glTF::GLTFResourceReader::ReadBinaryData<uint>(Microsoft::glTF::Buffer const &,__int64,unsigned __int64)

- ea: `0x1802ac1d0`
- end: `0x1802ac54b`
- name: `??$ReadBinaryData@I@GLTFResourceReader@glTF@Microsoft@@AEBA?AV?$vector@IV?$allocator@I@std@@@std@@AEBUBuffer@12@_J_K@Z`
- size: `891`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `10`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1802ae680`
- `0x1802af3e0`
- `0x1802b0310`
- `0x1804833a0`
- `0x180483650`
- `0x1804839f0`
- `0x180483ec0`
- `0x1804843a0`
- `0x18048cd00`
- `0x18048db50`

## callees

- `0x180014a60`
- `0x18001ebf0`
- `0x18002c200`
- `0x180040860`
- `0x1800fee60`
- `0x1802ac1d0`
- `0x1802b3aa0`
- `0x1802c2bf0`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802ac4a2`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802ac4a2`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802ac48a`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802ac48a`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802ac477`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802ac477`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac2de`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac3ab`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac2de`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802ac3ab`

## string_xrefs

- `0x1802ac51c`: `Cannot read the binary data`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 *__fastcall Microsoft::glTF::GLTFResourceReader::ReadBinaryData<unsigned int>(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned __int64 a4,
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
  unsigned __int64 v31; // [rsp+90h] [rbp-21h] BYREF
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
    Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(a1, v27, (__int64)&v28, &v31);
    std::vector<unsigned int>::operator=(a2, Block);
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
    std::vector<unsigned int>::_Resize_reallocate<std::_Value_init_tag>(a2, a5, v23);
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
0x1802ac1d0  push    rbp
0x1802ac1d2  push    rbx
0x1802ac1d3  push    rsi
0x1802ac1d4  push    rdi
0x1802ac1d5  push    r12
0x1802ac1d7  push    r13
0x1802ac1d9  push    r14
0x1802ac1db  push    r15
0x1802ac1dd  lea     rbp, [rsp-17h]
0x1802ac1e2  sub     rsp, 0C8h
0x1802ac1e9  mov     rax, cs:__security_cookie
0x1802ac1f0  xor     rax, rsp
0x1802ac1f3  mov     [rbp+4Fh+var_50], rax
0x1802ac1f7  mov     r12, r9
0x1802ac1fa  mov     r15, r8
0x1802ac1fd  mov     rdi, rdx
0x1802ac200  mov     r13, rcx
0x1802ac203  mov     [rbp+4Fh+var_90], rdx
0x1802ac207  mov     [rbp+4Fh+var_70], r9
0x1802ac20b  xor     ebx, ebx
0x1802ac20d  mov     [rsp+100h+var_DC], ebx
0x1802ac211  xorps   xmm0, xmm0
0x1802ac214  movups  xmmword ptr [rdx], xmm0
0x1802ac217  mov     [rdx], rbx
0x1802ac21a  mov     [rdx+8], rbx
0x1802ac21e  mov     [rdx+10h], rbx
0x1802ac222  mov     [rsp+100h+var_DC], 1
0x1802ac22a  mov     qword ptr [rbp+4Fh+var_B0], rbx
0x1802ac22e  mov     qword ptr [rbp+4Fh+var_A0], rbx
0x1802ac232  lea     rcx, [r8+0E8h]; Buf
0x1802ac239  lea     r8, [rbp+4Fh+var_A0]
0x1802ac23d  lea     rdx, [rbp+4Fh+var_B0]
0x1802ac241  call    ?IsUriBase64@glTF@Microsoft@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@4@1@Z; Microsoft::glTF::IsUriBase64(std::string const &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &)
0x1802ac246  test    al, al
0x1802ac248  jz      loc_1802AC3BC
0x1802ac24e  mov     rax, qword ptr [rbp+4Fh+var_B0]
0x1802ac252  mov     qword ptr [rbp+4Fh+var_B0], rax
0x1802ac256  mov     rcx, qword ptr [rbp+4Fh+var_A0]
0x1802ac25a  mov     qword ptr [rbp+4Fh+var_B0+8], rcx
0x1802ac25e  cmp     rax, rcx
0x1802ac261  jz      short loc_1802AC27B
0x1802ac263  mov     rdx, rcx
0x1802ac266  cmp     byte ptr [rdx-1], 3Dh ; '='
0x1802ac26a  jnz     short loc_1802AC27B
0x1802ac26c  dec     rcx
0x1802ac26f  mov     rdx, rcx
0x1802ac272  mov     qword ptr [rbp+4Fh+var_B0+8], rcx
0x1802ac276  cmp     rax, rcx
0x1802ac279  jnz     short loc_1802AC266
0x1802ac27b  xorps   xmm1, xmm1
0x1802ac27e  movdqu  xmmword ptr [rsp+100h+Block], xmm1
0x1802ac284  mov     [rbp+4Fh+var_C0], rbx
0x1802ac288  mov     rsi, [rbp+4Fh+arg_20]
0x1802ac28c  test    rsi, rsi
0x1802ac28f  jz      loc_1802AC315
0x1802ac295  mov     rax, 3FFFFFFFFFFFFFFFh
0x1802ac29f  cmp     rsi, rax
0x1802ac2a2  ja      loc_1802AC53F
0x1802ac2a8  lea     rsi, ds:0[rsi*4]
0x1802ac2b0  cmp     rsi, 1000h
0x1802ac2b7  jb      short loc_1802AC2E5
0x1802ac2b9  lea     rcx, [rsi+27h]; Size
0x1802ac2bd  cmp     rcx, rsi
0x1802ac2c0  jbe     loc_1802AC545
0x1802ac2c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802ac2cb  test    rax, rax
0x1802ac2ce  jz      short loc_1802AC2DE
0x1802ac2d0  lea     rbx, [rax+27h]
0x1802ac2d4  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1802ac2d8  mov     [rbx-8], rax
0x1802ac2dc  jmp     short loc_1802AC2F5
0x1802ac2de  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802ac2e5  test    rsi, rsi
0x1802ac2e8  jz      short loc_1802AC2F5
0x1802ac2ea  mov     rcx, rsi; Size
0x1802ac2ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802ac2f2  mov     rbx, rax
0x1802ac2f5  mov     [rsp+100h+Block], rbx
0x1802ac2fa  lea     r14, [rbx+rsi]
0x1802ac2fe  mov     [rbp+4Fh+var_C0], r14
0x1802ac302  mov     r8, rsi; Size
0x1802ac305  xor     edx, edx; Val
0x1802ac307  mov     rcx, rbx; void *
0x1802ac30a  call    memset_0
0x1802ac30f  mov     [rbp+4Fh+Block+8], r14
0x1802ac313  jmp     short loc_1802AC319
0x1802ac315  mov     r14, [rbp+4Fh+Block+8]
0x1802ac319  mov     [rsp+100h+var_DC], 3
0x1802ac321  mov     rax, [rsp+100h+Block]
0x1802ac326  sub     r14, rax
0x1802ac329  sar     r14, 2
0x1802ac32d  mov     qword ptr [rbp+4Fh+var_80], rax
0x1802ac331  lea     rax, ds:0[r14*4]
0x1802ac339  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x1802ac33d  movaps  xmm0, [rbp+4Fh+var_80]
0x1802ac341  movdqa  [rbp+4Fh+var_A0], xmm0
0x1802ac346  movaps  xmm1, [rbp+4Fh+var_B0]
0x1802ac34a  movdqa  [rbp+4Fh+var_B0], xmm1
0x1802ac34f  lea     r9, [rbp+4Fh+var_70]
0x1802ac353  lea     r8, [rbp+4Fh+var_A0]
0x1802ac357  lea     rdx, [rbp+4Fh+var_B0]
0x1802ac35b  mov     rcx, r13
0x1802ac35e  call    ?ReadBinaryDataUri@GLTFResourceReader@glTF@Microsoft@@AEBAXUBase64StringView@23@UBase64BufferView@23@PEB_J@Z; Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(Microsoft::glTF::Base64StringView,Microsoft::glTF::Base64BufferView,__int64 const *)
0x1802ac363  lea     rdx, [rsp+100h+Block]
0x1802ac368  mov     rcx, rdi
0x1802ac36b  call    ??4?$vector@IV?$allocator@I@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uint>::operator=(std::vector<uint> &&)
0x1802ac370  nop
0x1802ac371  mov     rcx, [rsp+100h+Block]; Block
0x1802ac376  test    rcx, rcx
0x1802ac379  jz      loc_1802AC4F9
0x1802ac37f  mov     rdx, [rbp+4Fh+var_C0]
0x1802ac383  sub     rdx, rcx
0x1802ac386  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1802ac38a  mov     rax, rcx
0x1802ac38d  cmp     rdx, 1000h
0x1802ac394  jb      short loc_1802AC3B2
0x1802ac396  add     rdx, 27h ; '''
0x1802ac39a  mov     rcx, [rcx-8]
0x1802ac39e  sub     rax, rcx
0x1802ac3a1  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802ac3a5  cmp     rax, 1Fh
0x1802ac3a9  jbe     short loc_1802AC3B2
0x1802ac3ab  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802ac3b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802ac3b7  jmp     loc_1802AC4F9
0x1802ac3bc  mov     r14, [rdi+8]
0x1802ac3c0  mov     rdx, [rdi]
0x1802ac3c3  mov     rcx, r14
0x1802ac3c6  sub     rcx, rdx
0x1802ac3c9  sar     rcx, 2
0x1802ac3cd  mov     rsi, [rbp+4Fh+arg_20]
0x1802ac3d1  cmp     rsi, rcx
0x1802ac3d4  jnb     short loc_1802AC3DC
0x1802ac3d6  lea     rax, [rdx+rsi*4]
0x1802ac3da  jmp     short loc_1802AC41F
0x1802ac3dc  jbe     short loc_1802AC423
0x1802ac3de  mov     rax, [rdi+10h]
0x1802ac3e2  sub     rax, rdx
0x1802ac3e5  sar     rax, 2
0x1802ac3e9  cmp     rsi, rax
0x1802ac3ec  jbe     short loc_1802AC400
0x1802ac3ee  lea     r8, [rsp+100h+var_E0]
0x1802ac3f3  mov     rdx, rsi
0x1802ac3f6  mov     rcx, rdi
0x1802ac3f9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@IV?$allocator@I@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uint>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1802ac3fe  jmp     short loc_1802AC423
0x1802ac400  mov     rax, rsi
0x1802ac403  sub     rax, rcx
0x1802ac406  lea     rbx, ds:0[rax*4]
0x1802ac40e  mov     r8, rbx; Size
0x1802ac411  xor     edx, edx; Val
0x1802ac413  mov     rcx, r14; void *
0x1802ac416  call    memset_0
0x1802ac41b  lea     rax, [rbx+r14]
0x1802ac41f  mov     [rdi+8], rax
0x1802ac423  xorps   xmm0, xmm0
0x1802ac426  movups  [rbp+4Fh+var_80], xmm0
0x1802ac42a  mov     rax, [r13+0]
0x1802ac42e  mov     r8, r15
0x1802ac431  lea     rdx, [rbp+4Fh+var_80]
0x1802ac435  mov     rcx, r13
0x1802ac438  mov     rax, [rax+8]
0x1802ac43c  call    cs:__guard_dispatch_icall_fptr
0x1802ac442  nop
0x1802ac443  mov     rax, [r13+0]
0x1802ac447  mov     r8, r15
0x1802ac44a  lea     rdx, [rbp+4Fh+var_68]
0x1802ac44e  mov     rcx, r13
0x1802ac451  mov     rax, [rax+10h]
0x1802ac455  call    cs:__guard_dispatch_icall_fptr
0x1802ac45b  movups  xmm0, [rbp+4Fh+var_68]
0x1802ac45f  movaps  xmmword ptr [rsp+100h+Block], xmm0
0x1802ac464  movsd   xmm1, [rbp+4Fh+var_58]
0x1802ac469  movsd   [rbp+4Fh+var_C0], xmm1
0x1802ac46e  lea     rdx, [rsp+100h+Block]
0x1802ac473  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x1802ac477  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x1802ac47d  mov     r8d, 1
0x1802ac483  mov     rdx, r12
0x1802ac486  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x1802ac48a  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802ac490  lea     r8, ds:0[rsi*4]
0x1802ac498  mov     rbx, qword ptr [rbp+4Fh+var_80]
0x1802ac49c  mov     rdx, [rdi]
0x1802ac49f  mov     rcx, rbx
0x1802ac4a2  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1802ac4a8  mov     rax, [rbx]
0x1802ac4ab  movsxd  rcx, dword ptr [rax+4]
0x1802ac4af  test    byte ptr [rcx+rbx+10h], 6
0x1802ac4b4  jnz     short loc_1802AC51C
0x1802ac4b6  mov     rbx, qword ptr [rbp+4Fh+var_80+8]
0x1802ac4ba  test    rbx, rbx
0x1802ac4bd  jz      short loc_1802AC4F9
0x1802ac4bf  mov     esi, 0FFFFFFFFh
0x1802ac4c4  mov     eax, esi
0x1802ac4c6  lock xadd [rbx+8], eax
0x1802ac4cb  cmp     eax, 1
0x1802ac4ce  jnz     short loc_1802AC4F9
0x1802ac4d0  mov     rax, [rbx]
0x1802ac4d3  mov     rcx, rbx
0x1802ac4d6  mov     rax, [rax]
0x1802ac4d9  call    cs:__guard_dispatch_icall_fptr
0x1802ac4df  lock xadd [rbx+0Ch], esi
0x1802ac4e4  cmp     esi, 1
0x1802ac4e7  jnz     short loc_1802AC4F9
0x1802ac4e9  mov     rdx, [rbx]
0x1802ac4ec  mov     rcx, rbx
0x1802ac4ef  mov     rax, [rdx+8]
0x1802ac4f3  call    cs:__guard_dispatch_icall_fptr
0x1802ac4f9  mov     rax, rdi
0x1802ac4fc  mov     rcx, [rbp+4Fh+var_50]
0x1802ac500  xor     rcx, rsp; StackCookie
0x1802ac503  call    __security_check_cookie
0x1802ac508  add     rsp, 0C8h
0x1802ac50f  pop     r15
0x1802ac511  pop     r14
0x1802ac513  pop     r13
0x1802ac515  pop     r12
0x1802ac517  pop     rdi
0x1802ac518  pop     rsi
0x1802ac519  pop     rbx
0x1802ac51a  pop     rbp
0x1802ac51b  retn
0x1802ac51c  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x1802ac523  lea     rcx, [rsp+100h+Block]; this
0x1802ac528  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1802ac52d  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1802ac534  lea     rcx, [rsp+100h+Block]; pExceptionObject
0x1802ac539  call    _CxxThrowException_0
0x1802ac53f  call    ?_Xlength@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@CAXXZ; std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(void)
0x1802ac545  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
