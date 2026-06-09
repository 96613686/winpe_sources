# Microsoft::glTF::GLTFResourceReader::ReadBinaryData<uchar>(Microsoft::glTF::Buffer const &,__int64,unsigned __int64)

- ea: `0x1802ab950`
- end: `0x1802abc38`
- name: `??$ReadBinaryData@E@GLTFResourceReader@glTF@Microsoft@@AEBA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUBuffer@12@_J_K@Z`
- size: `744`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, unsigned __int64, size_t Size)`
- caller_count: `11`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1802ab470`
- `0x1802ad5b0`
- `0x1802addf0`
- `0x1802ae230`
- `0x1802ae680`
- `0x1802aeae0`
- `0x1802af880`
- `0x1802c2670`
- `0x1804839f0`
- `0x18048c3d0`
- `0x18048d1c0`

## callees

- `0x180014a60`
- `0x18001dd60`
- `0x18001e340`
- `0x18001ebf0`
- `0x18002c200`
- `0x18002eb54`
- `0x1802ab950`
- `0x1802c2bf0`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802abb95`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x1802abb95`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802abb81`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1802abb81`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802abb6e`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1802abb6e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802aba50`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802abb01`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802aba50`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802abb01`

## string_xrefs

- `0x1802abc0b`: `Cannot read the binary data`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
_QWORD *__fastcall Microsoft::glTF::GLTFResourceReader::ReadBinaryData<unsigned char>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned __int64 a4,
        size_t Size)
{
  __int64 v9; // rdx
  void *v10; // rax
  void *v11; // rcx
  _QWORD *v12; // rax
  char *v13; // rdi
  void *v14; // rcx
  __int64 v15; // rbx
  volatile signed __int32 *v16; // rbx
  void *Block[2]; // [rsp+30h] [rbp-71h] BYREF
  size_t v19; // [rsp+40h] [rbp-61h]
  _QWORD v20[2]; // [rsp+50h] [rbp-51h] BYREF
  __int128 v21; // [rsp+60h] [rbp-41h] BYREF
  _QWORD *v22; // [rsp+70h] [rbp-31h]
  __int128 v23; // [rsp+80h] [rbp-21h] BYREF
  unsigned __int64 v24; // [rsp+90h] [rbp-11h] BYREF
  __int128 v25; // [rsp+98h] [rbp-9h] BYREF
  size_t v26; // [rsp+A8h] [rbp+7h]

  v22 = a2;
  v24 = a4;
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v20[0] = 0;
  *(_QWORD *)&v21 = 0;
  if ( (unsigned __int8)Microsoft::glTF::IsUriBase64((void *)(a3 + 232)) )
  {
    v20[1] = v21;
    *(_OWORD *)Block = 0;
    v19 = 0;
    if ( Size )
    {
      if ( Size > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<Microsoft::glTF::Buffer>::_Xlength(v21, v9);
      if ( Size < 0x1000 )
      {
        v12 = operator new(Size);
      }
      else
      {
        if ( Size + 39 < Size )
          __scrt_throw_std_bad_array_new_length();
        v10 = operator new(Size + 39);
        v11 = v10;
        if ( !v10 )
          _invalid_parameter_noinfo_noreturn();
        v12 = (_QWORD *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v12 - 1) = v11;
      }
      Block[0] = v12;
      v13 = (char *)v12 + Size;
      v19 = (size_t)v12 + Size;
      memset_0(v12, 0, Size);
      Block[1] = v13;
    }
    else
    {
      v13 = (char *)Block[1];
    }
    *(void **)&v23 = Block[0];
    *((_QWORD *)&v23 + 1) = v13 - (char *)Block[0];
    v21 = v23;
    Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(a1, v20, (__int64)&v21, &v24);
    std::vector<unsigned char>::operator=(a2, Block);
    v14 = Block[0];
    if ( Block[0] )
    {
      if ( v19 - (unsigned __int64)Block[0] >= 0x1000 )
      {
        v14 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v14);
    }
  }
  else
  {
    std::vector<unsigned char>::resize(a2, Size);
    v23 = 0;
    (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 8LL))(a1, &v23, a3);
    (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)a1 + 16LL))(a1, &v25, a3);
    *(_OWORD *)Block = v25;
    v19 = v26;
    std::istream::seekg(v23, Block);
    std::istream::seekg(v23, a4, 1);
    v15 = v23;
    std::istream::read(v23, *a2, Size);
    if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v15 + 4LL) + v15 + 16) & 6) != 0 )
    {
      std::runtime_error::runtime_error((std::runtime_error *)Block, "Cannot read the binary data");
      throw (std::runtime_error *)Block;
    }
    v16 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1802ab950  push    rbp
0x1802ab952  push    rbx
0x1802ab953  push    rsi
0x1802ab954  push    rdi
0x1802ab955  push    r14
0x1802ab957  push    r15
0x1802ab959  lea     rbp, [rsp-27h]
0x1802ab95e  sub     rsp, 0C8h
0x1802ab965  mov     rax, cs:__security_cookie
0x1802ab96c  xor     rax, rsp
0x1802ab96f  mov     [rbp+4Fh+var_40], rax
0x1802ab973  mov     r14, r9
0x1802ab976  mov     rbx, r8
0x1802ab979  mov     rsi, rdx
0x1802ab97c  mov     r15, rcx
0x1802ab97f  mov     [rbp+4Fh+var_80], rdx
0x1802ab983  mov     [rbp+4Fh+var_60], r9
0x1802ab987  xor     edi, edi
0x1802ab989  mov     [rsp+0F0h+var_D0], edi
0x1802ab98d  xorps   xmm0, xmm0
0x1802ab990  movups  xmmword ptr [rdx], xmm0
0x1802ab993  mov     [rdx], rdi
0x1802ab996  mov     [rdx+8], rdi
0x1802ab99a  mov     [rdx+10h], rdi
0x1802ab99e  mov     [rsp+0F0h+var_D0], 1
0x1802ab9a6  mov     qword ptr [rbp+4Fh+var_A0], rdi
0x1802ab9aa  mov     qword ptr [rbp+4Fh+var_90], rdi
0x1802ab9ae  lea     rcx, [r8+0E8h]; Buf
0x1802ab9b5  lea     r8, [rbp+4Fh+var_90]
0x1802ab9b9  lea     rdx, [rbp+4Fh+var_A0]
0x1802ab9bd  call    ?IsUriBase64@glTF@Microsoft@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@4@1@Z; Microsoft::glTF::IsUriBase64(std::string const &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>> &)
0x1802ab9c2  test    al, al
0x1802ab9c4  jz      loc_1802ABB12
0x1802ab9ca  mov     rax, qword ptr [rbp+4Fh+var_A0]
0x1802ab9ce  mov     qword ptr [rbp+4Fh+var_A0], rax
0x1802ab9d2  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x1802ab9d6  mov     qword ptr [rbp+4Fh+var_A0+8], rcx
0x1802ab9da  cmp     rax, rcx
0x1802ab9dd  jz      short loc_1802AB9F7
0x1802ab9df  mov     rdx, rcx
0x1802ab9e2  cmp     byte ptr [rdx-1], 3Dh ; '='
0x1802ab9e6  jnz     short loc_1802AB9F7
0x1802ab9e8  dec     rcx
0x1802ab9eb  mov     rdx, rcx
0x1802ab9ee  mov     qword ptr [rbp+4Fh+var_A0+8], rcx
0x1802ab9f2  cmp     rax, rcx
0x1802ab9f5  jnz     short loc_1802AB9E2
0x1802ab9f7  xorps   xmm1, xmm1
0x1802ab9fa  movdqu  xmmword ptr [rbp+4Fh+Block], xmm1
0x1802ab9ff  mov     [rbp+4Fh+var_B0], rdi
0x1802aba03  mov     rbx, [rbp+4Fh+Size]
0x1802aba07  test    rbx, rbx
0x1802aba0a  jz      short loc_1802ABA7E
0x1802aba0c  mov     rax, 7FFFFFFFFFFFFFFFh
0x1802aba16  cmp     rbx, rax
0x1802aba19  ja      loc_1802ABC2C
0x1802aba1f  cmp     rbx, 1000h
0x1802aba26  jb      short loc_1802ABA57
0x1802aba28  lea     rcx, [rbx+27h]; Size
0x1802aba2c  cmp     rcx, rbx
0x1802aba2f  jbe     loc_1802ABC32
0x1802aba35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802aba3a  mov     rcx, rax
0x1802aba3d  test    rax, rax
0x1802aba40  jz      short loc_1802ABA50
0x1802aba42  add     rax, 27h ; '''
0x1802aba46  and     rax, 0FFFFFFFFFFFFFFE0h
0x1802aba4a  mov     [rax-8], rcx
0x1802aba4e  jmp     short loc_1802ABA5F
0x1802aba50  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802aba57  mov     rcx, rbx; Size
0x1802aba5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802aba5f  mov     [rbp+4Fh+Block], rax
0x1802aba63  lea     rdi, [rax+rbx]
0x1802aba67  mov     [rbp+4Fh+var_B0], rdi
0x1802aba6b  mov     r8, rbx; Size
0x1802aba6e  xor     edx, edx; Val
0x1802aba70  mov     rcx, rax; void *
0x1802aba73  call    memset_0
0x1802aba78  mov     [rbp+4Fh+Block+8], rdi
0x1802aba7c  jmp     short loc_1802ABA82
0x1802aba7e  mov     rdi, [rbp+4Fh+Block+8]
0x1802aba82  mov     [rsp+0F0h+var_D0], 3
0x1802aba8a  mov     rax, [rbp+4Fh+Block]
0x1802aba8e  sub     rdi, rax
0x1802aba91  mov     qword ptr [rbp+4Fh+var_70], rax
0x1802aba95  mov     qword ptr [rbp+4Fh+var_70+8], rdi
0x1802aba99  movaps  xmm0, [rbp+4Fh+var_70]
0x1802aba9d  movdqa  [rbp+4Fh+var_90], xmm0
0x1802abaa2  movaps  xmm1, [rbp+4Fh+var_A0]
0x1802abaa6  movdqa  [rbp+4Fh+var_A0], xmm1
0x1802abaab  lea     r9, [rbp+4Fh+var_60]
0x1802abaaf  lea     r8, [rbp+4Fh+var_90]
0x1802abab3  lea     rdx, [rbp+4Fh+var_A0]
0x1802abab7  mov     rcx, r15
0x1802ababa  call    ?ReadBinaryDataUri@GLTFResourceReader@glTF@Microsoft@@AEBAXUBase64StringView@23@UBase64BufferView@23@PEB_J@Z; Microsoft::glTF::GLTFResourceReader::ReadBinaryDataUri(Microsoft::glTF::Base64StringView,Microsoft::glTF::Base64BufferView,__int64 const *)
0x1802ababf  lea     rdx, [rbp+4Fh+Block]
0x1802abac3  mov     rcx, rsi
0x1802abac6  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1802abacb  nop
0x1802abacc  mov     rcx, [rbp+4Fh+Block]; Block
0x1802abad0  test    rcx, rcx
0x1802abad3  jz      loc_1802ABBEC
0x1802abad9  mov     rdx, [rbp+4Fh+var_B0]
0x1802abadd  sub     rdx, rcx
0x1802abae0  mov     rax, rcx
0x1802abae3  cmp     rdx, 1000h
0x1802abaea  jb      short loc_1802ABB08
0x1802abaec  add     rdx, 27h ; '''
0x1802abaf0  mov     rcx, [rcx-8]
0x1802abaf4  sub     rax, rcx
0x1802abaf7  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802abafb  cmp     rax, 1Fh
0x1802abaff  jbe     short loc_1802ABB08
0x1802abb01  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802abb08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802abb0d  jmp     loc_1802ABBEC
0x1802abb12  mov     rdx, [rbp+4Fh+Size]
0x1802abb16  mov     rcx, rsi
0x1802abb19  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1802abb1e  xorps   xmm0, xmm0
0x1802abb21  movups  [rbp+4Fh+var_70], xmm0
0x1802abb25  mov     rax, [r15]
0x1802abb28  mov     r8, rbx
0x1802abb2b  lea     rdx, [rbp+4Fh+var_70]
0x1802abb2f  mov     rcx, r15
0x1802abb32  mov     rax, [rax+8]
0x1802abb36  call    cs:__guard_dispatch_icall_fptr
0x1802abb3c  nop
0x1802abb3d  mov     rax, [r15]
0x1802abb40  mov     r8, rbx
0x1802abb43  lea     rdx, [rbp+4Fh+var_58]
0x1802abb47  mov     rcx, r15
0x1802abb4a  mov     rax, [rax+10h]
0x1802abb4e  call    cs:__guard_dispatch_icall_fptr
0x1802abb54  movups  xmm0, [rbp+4Fh+var_58]
0x1802abb58  movaps  xmmword ptr [rbp+4Fh+Block], xmm0
0x1802abb5c  movsd   xmm1, [rbp+4Fh+var_48]
0x1802abb61  movsd   [rbp+4Fh+var_B0], xmm1
0x1802abb66  lea     rdx, [rbp+4Fh+Block]
0x1802abb6a  mov     rcx, qword ptr [rbp+4Fh+var_70]
0x1802abb6e  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x1802abb74  mov     r8d, 1
0x1802abb7a  mov     rdx, r14
0x1802abb7d  mov     rcx, qword ptr [rbp+4Fh+var_70]
0x1802abb81  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x1802abb87  mov     rbx, qword ptr [rbp+4Fh+var_70]
0x1802abb8b  mov     r8, [rbp+4Fh+Size]
0x1802abb8f  mov     rdx, [rsi]
0x1802abb92  mov     rcx, rbx
0x1802abb95  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x1802abb9b  mov     rax, [rbx]
0x1802abb9e  movsxd  rcx, dword ptr [rax+4]
0x1802abba2  test    byte ptr [rcx+rbx+10h], 6
0x1802abba7  jnz     short loc_1802ABC0B
0x1802abba9  mov     rbx, qword ptr [rbp+4Fh+var_70+8]
0x1802abbad  test    rbx, rbx
0x1802abbb0  jz      short loc_1802ABBEC
0x1802abbb2  mov     edi, 0FFFFFFFFh
0x1802abbb7  mov     eax, edi
0x1802abbb9  lock xadd [rbx+8], eax
0x1802abbbe  cmp     eax, 1
0x1802abbc1  jnz     short loc_1802ABBEC
0x1802abbc3  mov     rax, [rbx]
0x1802abbc6  mov     rcx, rbx
0x1802abbc9  mov     rax, [rax]
0x1802abbcc  call    cs:__guard_dispatch_icall_fptr
0x1802abbd2  lock xadd [rbx+0Ch], edi
0x1802abbd7  cmp     edi, 1
0x1802abbda  jnz     short loc_1802ABBEC
0x1802abbdc  mov     rdx, [rbx]
0x1802abbdf  mov     rcx, rbx
0x1802abbe2  mov     rax, [rdx+8]
0x1802abbe6  call    cs:__guard_dispatch_icall_fptr
0x1802abbec  mov     rax, rsi
0x1802abbef  mov     rcx, [rbp+4Fh+var_40]
0x1802abbf3  xor     rcx, rsp; StackCookie
0x1802abbf6  call    __security_check_cookie
0x1802abbfb  add     rsp, 0C8h
0x1802abc02  pop     r15
0x1802abc04  pop     r14
0x1802abc06  pop     rdi
0x1802abc07  pop     rsi
0x1802abc08  pop     rbx
0x1802abc09  pop     rbp
0x1802abc0a  retn
0x1802abc0b  lea     rdx, aCannotReadTheB; "Cannot read the binary data"
0x1802abc12  lea     rcx, [rbp+4Fh+Block]; this
0x1802abc16  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1802abc1b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1802abc22  lea     rcx, [rbp+4Fh+Block]; pExceptionObject
0x1802abc26  call    _CxxThrowException_0
0x1802abc2c  call    ?_Xlength@?$vector@UBuffer@glTF@Microsoft@@V?$allocator@UBuffer@glTF@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::glTF::Buffer>::_Xlength(void)
0x1802abc32  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
