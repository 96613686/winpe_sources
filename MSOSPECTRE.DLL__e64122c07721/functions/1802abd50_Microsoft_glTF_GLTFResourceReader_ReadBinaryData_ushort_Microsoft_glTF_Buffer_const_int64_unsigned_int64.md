# Microsoft::glTF::GLTFResourceReader::ReadBinaryData<ushort>(Microsoft::glTF::Buffer const &,__int64,unsigned __int64)

- ea: `0x1802abd50`
- end: `0x1802ac0b5`
- name: `??$ReadBinaryData@G@GLTFResourceReader@glTF@Microsoft@@AEBA?AV?$vector@GV?$allocator@G@std@@@std@@AEBUBuffer@12@_J_K@Z`
- size: `869`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `10`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1802ab600`
- `0x1802ad860`
- `0x1802ae230`
- `0x1802aeae0`
- `0x1802aef50`
- `0x1802af3e0`
- `0x1802afdd0`
- `0x180483ec0`
- `0x18048c850`
- `0x18048d680`

## callees

- `0x180014a60`
- `0x18001ebf0`
- `0x18002c200`
- `0x180040860`
- `0x1802abd50`
- `0x1802b39d0`
- `0x1802b6e30`
- `0x1802c2bf0`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802ac00c`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802ac00c`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802abff8`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802abff8`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802abfe5`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802abfe5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802abe55`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802abf1f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802abe55`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802abf1f`

## string_xrefs

- `0x1802ac086`: `Cannot read the binary data`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 *__fastcall Microsoft::glTF::GLTFResourceReader::ReadBinaryData<unsigned short>(
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
      if ( a5 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(v28, v10);
      v11 = 2 * a5;
      if ( 2 * a5 < 0x1000 )
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
    *((_QWORD *)&v30 + 1) = 2 * ((v13 - (char *)Block[0]) >> 1);
    v28 = v30;
    Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(a1, v27, (__int64)&v28, &v31);
    std::vector<unsigned short>::operator=(a2, Block);
    v14 = Block[0];
    if ( Block[0] )
    {
      if ( (unsigned __int64)(2 * ((v26 - (char *)Block[0]) >> 1)) >= 0x1000 )
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
  v17 = (v15 - *a2) >> 1;
  if ( a5 < v17 )
  {
    v18 = v16 + 2 * a5;
LABEL_24:
    a2[1] = v18;
    goto LABEL_25;
  }
  if ( a5 > v17 )
  {
    if ( a5 <= (a2[2] - v16) >> 1 )
    {
      v19 = 2 * (a5 - v17);
      memset_0((void *)a2[1], 0, v19);
      v18 = v19 + v15;
      goto LABEL_24;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(a2, a5, v23);
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
  std::istream::read(v30, *a2, 2 * a5);
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
0x1802abd50  push    rbp
0x1802abd52  push    rbx
0x1802abd53  push    rsi
0x1802abd54  push    rdi
0x1802abd55  push    r12
0x1802abd57  push    r13
0x1802abd59  push    r14
0x1802abd5b  push    r15
0x1802abd5d  lea     rbp, [rsp-17h]
0x1802abd62  sub     rsp, 0C8h
0x1802abd69  mov     rax, cs:__security_cookie
0x1802abd70  xor     rax, rsp
0x1802abd73  mov     [rbp+4Fh+var_50], rax
0x1802abd77  mov     r12, r9
0x1802abd7a  mov     r15, r8
0x1802abd7d  mov     rdi, rdx
0x1802abd80  mov     r13, rcx
0x1802abd83  mov     [rbp+4Fh+var_90], rdx
0x1802abd87  mov     [rbp+4Fh+var_70], r9
0x1802abd8b  xor     ebx, ebx
0x1802abd8d  mov     [rsp+100h+var_DC], ebx
0x1802abd91  xorps   xmm0, xmm0
0x1802abd94  movups  xmmword ptr [rdx], xmm0
0x1802abd97  mov     [rdx], rbx
0x1802abd9a  mov     [rdx+8], rbx
0x1802abd9e  mov     [rdx+10h], rbx
0x1802abda2  mov     [rsp+100h+var_DC], 1
0x1802abdaa  mov     qword ptr [rbp+4Fh+var_B0], rbx
0x1802abdae  mov     qword ptr [rbp+4Fh+var_A0], rbx
0x1802abdb2  lea     rcx, [r8+0E8h]; Buf
0x1802abdb9  lea     r8, [rbp+4Fh+var_A0]
0x1802abdbd  lea     rdx, [rbp+4Fh+var_B0]
0x1802abdc1  call    ?IsUriBase64@glTF@Microsoft@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@4@1@Z; Microsoft::glTF::IsUriBase64(std::string const &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &)
0x1802abdc6  test    al, al
0x1802abdc8  jz      loc_1802ABF30
0x1802abdce  mov     rax, qword ptr [rbp+4Fh+var_B0]
0x1802abdd2  mov     qword ptr [rbp+4Fh+var_B0], rax
0x1802abdd6  mov     rcx, qword ptr [rbp+4Fh+var_A0]
0x1802abdda  mov     qword ptr [rbp+4Fh+var_B0+8], rcx
0x1802abdde  cmp     rax, rcx
0x1802abde1  jz      short loc_1802ABDFB
0x1802abde3  mov     rdx, rcx
0x1802abde6  cmp     byte ptr [rdx-1], 3Dh ; '='
0x1802abdea  jnz     short loc_1802ABDFB
0x1802abdec  dec     rcx
0x1802abdef  mov     rdx, rcx
0x1802abdf2  mov     qword ptr [rbp+4Fh+var_B0+8], rcx
0x1802abdf6  cmp     rax, rcx
0x1802abdf9  jnz     short loc_1802ABDE6
0x1802abdfb  xorps   xmm1, xmm1
0x1802abdfe  movdqu  xmmword ptr [rsp+100h+Block], xmm1
0x1802abe04  mov     [rbp+4Fh+var_C0], rbx
0x1802abe08  mov     rsi, [rbp+4Fh+arg_20]
0x1802abe0c  test    rsi, rsi
0x1802abe0f  jz      short loc_1802ABE8C
0x1802abe11  mov     rax, 7FFFFFFFFFFFFFFFh
0x1802abe1b  cmp     rsi, rax
0x1802abe1e  ja      loc_1802AC0A9
0x1802abe24  add     rsi, rsi
0x1802abe27  cmp     rsi, 1000h
0x1802abe2e  jb      short loc_1802ABE5C
0x1802abe30  lea     rcx, [rsi+27h]; Size
0x1802abe34  cmp     rcx, rsi
0x1802abe37  jbe     loc_1802AC0AF
0x1802abe3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802abe42  test    rax, rax
0x1802abe45  jz      short loc_1802ABE55
0x1802abe47  lea     rbx, [rax+27h]
0x1802abe4b  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1802abe4f  mov     [rbx-8], rax
0x1802abe53  jmp     short loc_1802ABE6C
0x1802abe55  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802abe5c  test    rsi, rsi
0x1802abe5f  jz      short loc_1802ABE6C
0x1802abe61  mov     rcx, rsi; Size
0x1802abe64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802abe69  mov     rbx, rax
0x1802abe6c  mov     [rsp+100h+Block], rbx
0x1802abe71  lea     r14, [rbx+rsi]
0x1802abe75  mov     [rbp+4Fh+var_C0], r14
0x1802abe79  mov     r8, rsi; Size
0x1802abe7c  xor     edx, edx; Val
0x1802abe7e  mov     rcx, rbx; void *
0x1802abe81  call    memset_0
0x1802abe86  mov     [rbp+4Fh+Block+8], r14
0x1802abe8a  jmp     short loc_1802ABE90
0x1802abe8c  mov     r14, [rbp+4Fh+Block+8]
0x1802abe90  mov     [rsp+100h+var_DC], 3
0x1802abe98  mov     rax, [rsp+100h+Block]
0x1802abe9d  sub     r14, rax
0x1802abea0  sar     r14, 1
0x1802abea3  mov     qword ptr [rbp+4Fh+var_80], rax
0x1802abea7  lea     rax, [r14+r14]
0x1802abeab  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x1802abeaf  movaps  xmm0, [rbp+4Fh+var_80]
0x1802abeb3  movdqa  [rbp+4Fh+var_A0], xmm0
0x1802abeb8  movaps  xmm1, [rbp+4Fh+var_B0]
0x1802abebc  movdqa  [rbp+4Fh+var_B0], xmm1
0x1802abec1  lea     r9, [rbp+4Fh+var_70]
0x1802abec5  lea     r8, [rbp+4Fh+var_A0]
0x1802abec9  lea     rdx, [rbp+4Fh+var_B0]
0x1802abecd  mov     rcx, r13
0x1802abed0  call    ?ReadBinaryDataUri@GLTFResourceReader@glTF@Microsoft@@AEBAXUBase64StringView@23@UBase64BufferView@23@PEB_J@Z; Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(Microsoft::glTF::Base64StringView,Microsoft::glTF::Base64BufferView,__int64 const *)
0x1802abed5  lea     rdx, [rsp+100h+Block]
0x1802abeda  mov     rcx, rdi
0x1802abedd  call    ??4?$vector@GV?$allocator@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<ushort>::operator=(std::vector<ushort> &&)
0x1802abee2  nop
0x1802abee3  mov     rcx, [rsp+100h+Block]; Block
0x1802abee8  test    rcx, rcx
0x1802abeeb  jz      loc_1802AC063
0x1802abef1  mov     rdx, [rbp+4Fh+var_C0]
0x1802abef5  sub     rdx, rcx
0x1802abef8  sar     rdx, 1
0x1802abefb  add     rdx, rdx
0x1802abefe  mov     rax, rcx
0x1802abf01  cmp     rdx, 1000h
0x1802abf08  jb      short loc_1802ABF26
0x1802abf0a  add     rdx, 27h ; '''
0x1802abf0e  mov     rcx, [rcx-8]
0x1802abf12  sub     rax, rcx
0x1802abf15  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802abf19  cmp     rax, 1Fh
0x1802abf1d  jbe     short loc_1802ABF26
0x1802abf1f  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802abf26  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802abf2b  jmp     loc_1802AC063
0x1802abf30  mov     r14, [rdi+8]
0x1802abf34  mov     rdx, [rdi]
0x1802abf37  mov     rcx, r14
0x1802abf3a  sub     rcx, rdx
0x1802abf3d  sar     rcx, 1
0x1802abf40  mov     rsi, [rbp+4Fh+arg_20]
0x1802abf44  cmp     rsi, rcx
0x1802abf47  jnb     short loc_1802ABF4F
0x1802abf49  lea     rax, [rdx+rsi*2]
0x1802abf4d  jmp     short loc_1802ABF8D
0x1802abf4f  jbe     short loc_1802ABF91
0x1802abf51  mov     rax, [rdi+10h]
0x1802abf55  sub     rax, rdx
0x1802abf58  sar     rax, 1
0x1802abf5b  cmp     rsi, rax
0x1802abf5e  jbe     short loc_1802ABF72
0x1802abf60  lea     r8, [rsp+100h+var_E0]
0x1802abf65  mov     rdx, rsi
0x1802abf68  mov     rcx, rdi
0x1802abf6b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1802abf70  jmp     short loc_1802ABF91
0x1802abf72  mov     rax, rsi
0x1802abf75  sub     rax, rcx
0x1802abf78  lea     rbx, [rax+rax]
0x1802abf7c  mov     r8, rbx; Size
0x1802abf7f  xor     edx, edx; Val
0x1802abf81  mov     rcx, r14; void *
0x1802abf84  call    memset_0
0x1802abf89  lea     rax, [rbx+r14]
0x1802abf8d  mov     [rdi+8], rax
0x1802abf91  xorps   xmm0, xmm0
0x1802abf94  movups  [rbp+4Fh+var_80], xmm0
0x1802abf98  mov     rax, [r13+0]
0x1802abf9c  mov     r8, r15
0x1802abf9f  lea     rdx, [rbp+4Fh+var_80]
0x1802abfa3  mov     rcx, r13
0x1802abfa6  mov     rax, [rax+8]
0x1802abfaa  call    cs:__guard_dispatch_icall_fptr
0x1802abfb0  nop
0x1802abfb1  mov     rax, [r13+0]
0x1802abfb5  mov     r8, r15
0x1802abfb8  lea     rdx, [rbp+4Fh+var_68]
0x1802abfbc  mov     rcx, r13
0x1802abfbf  mov     rax, [rax+10h]
0x1802abfc3  call    cs:__guard_dispatch_icall_fptr
0x1802abfc9  movups  xmm0, [rbp+4Fh+var_68]
0x1802abfcd  movaps  xmmword ptr [rsp+100h+Block], xmm0
0x1802abfd2  movsd   xmm1, [rbp+4Fh+var_58]
0x1802abfd7  movsd   [rbp+4Fh+var_C0], xmm1
0x1802abfdc  lea     rdx, [rsp+100h+Block]
0x1802abfe1  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x1802abfe5  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x1802abfeb  mov     r8d, 1
0x1802abff1  mov     rdx, r12
0x1802abff4  mov     rcx, qword ptr [rbp+4Fh+var_80]
0x1802abff8  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802abffe  lea     r8, [rsi+rsi]
0x1802ac002  mov     rbx, qword ptr [rbp+4Fh+var_80]
0x1802ac006  mov     rdx, [rdi]
0x1802ac009  mov     rcx, rbx
0x1802ac00c  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1802ac012  mov     rax, [rbx]
0x1802ac015  movsxd  rcx, dword ptr [rax+4]
0x1802ac019  test    byte ptr [rcx+rbx+10h], 6
0x1802ac01e  jnz     short loc_1802AC086
0x1802ac020  mov     rbx, qword ptr [rbp+4Fh+var_80+8]
0x1802ac024  test    rbx, rbx
0x1802ac027  jz      short loc_1802AC063
0x1802ac029  mov     esi, 0FFFFFFFFh
0x1802ac02e  mov     eax, esi
0x1802ac030  lock xadd [rbx+8], eax
0x1802ac035  cmp     eax, 1
0x1802ac038  jnz     short loc_1802AC063
0x1802ac03a  mov     rax, [rbx]
0x1802ac03d  mov     rcx, rbx
0x1802ac040  mov     rax, [rax]
0x1802ac043  call    cs:__guard_dispatch_icall_fptr
0x1802ac049  lock xadd [rbx+0Ch], esi
0x1802ac04e  cmp     esi, 1
0x1802ac051  jnz     short loc_1802AC063
0x1802ac053  mov     rdx, [rbx]
0x1802ac056  mov     rcx, rbx
0x1802ac059  mov     rax, [rdx+8]
0x1802ac05d  call    cs:__guard_dispatch_icall_fptr
0x1802ac063  mov     rax, rdi
0x1802ac066  mov     rcx, [rbp+4Fh+var_50]
0x1802ac06a  xor     rcx, rsp; StackCookie
0x1802ac06d  call    __security_check_cookie
0x1802ac072  add     rsp, 0C8h
0x1802ac079  pop     r15
0x1802ac07b  pop     r14
0x1802ac07d  pop     r13
0x1802ac07f  pop     r12
0x1802ac081  pop     rdi
0x1802ac082  pop     rsi
0x1802ac083  pop     rbx
0x1802ac084  pop     rbp
0x1802ac085  retn
0x1802ac086  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x1802ac08d  lea     rcx, [rsp+100h+Block]; this
0x1802ac092  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1802ac097  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1802ac09e  lea     rcx, [rsp+100h+Block]; pExceptionObject
0x1802ac0a3  call    _CxxThrowException_0
0x1802ac0a9  call    ?_Xlength@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@CAXXZ; std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(void)
0x1802ac0af  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
