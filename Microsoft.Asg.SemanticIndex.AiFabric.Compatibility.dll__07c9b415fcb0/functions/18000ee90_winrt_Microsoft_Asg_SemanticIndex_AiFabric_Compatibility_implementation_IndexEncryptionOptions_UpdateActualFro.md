# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::UpdateActualFromDeprecated(void)

- ea: `0x18000ee90`
- end: `0x18000f237`
- name: `?UpdateActualFromDeprecated@IndexEncryptionOptions@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAAXXZ`
- size: `935`
- prototype: `void __fastcall(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180067f30`

## callees

- `0x180003df0`
- `0x180004140`
- `0x180006e30`
- `0x180007a90`
- `0x180007b20`
- `0x180007ba0`
- `0x18000d230`
- `0x18000ee90`
- `0x18000fe80`
- `0x18000fff0`
- `0x180010400`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206ec0`
- `0x1802421a0`

## string_xrefs

- `0x18000f187`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexEncryptionOptions.cpp`
- `0x18000f1d5`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexEncryptionOptions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::UpdateActualFromDeprecated(
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions *this)
{
  int v2; // eax
  unsigned __int64 v3; // rdi
  _QWORD *v4; // r14
  __int64 v5; // rbx
  unsigned __int64 v6; // rcx
  __int64 v7; // rcx
  void **v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  void *v12; // r15
  size_t v13; // rdi
  char *v14; // r14
  _QWORD *v15; // rbx
  char *v16; // rax
  _QWORD *v17; // r8
  unsigned __int64 v18; // rdx
  void **v19; // [rsp+30h] [rbp-79h] BYREF
  __int64 v20; // [rsp+38h] [rbp-71h]
  __int64 v21; // [rsp+40h] [rbp-69h]
  __int64 v22; // [rsp+50h] [rbp-59h] BYREF
  __int128 v23; // [rsp+58h] [rbp-51h]
  char *v24; // [rsp+68h] [rbp-41h]
  char pExceptionObject[8]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v26; // [rsp+78h] [rbp-31h]
  char v27[8]; // [rsp+90h] [rbp-19h] BYREF
  void *Src; // [rsp+98h] [rbp-11h]
  _BYTE *v29; // [rsp+A0h] [rbp-9h]
  char v30; // [rsp+B0h] [rbp+7h]
  void *Block[2]; // [rsp+B8h] [rbp+Fh] BYREF
  unsigned __int64 v32; // [rsp+C8h] [rbp+1Fh]
  unsigned __int64 v33; // [rsp+D0h] [rbp+27h]

  v22 = 0;
  v23 = 0;
  v24 = 0;
  std::vector<unsigned char,asg::secure_allocator<unsigned char>>::operator=((char *)this + 176, &v22);
  std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(&v22);
  *((_DWORD *)this + 43) = 0;
  v2 = *((_DWORD *)this + 30);
  if ( v2 )
  {
    if ( v2 != 65537 )
    {
      LODWORD(v19) = 116;
      v20 = (__int64)"C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
      v21 = 0;
      winrt::param::hstring::hstring((winrt::param::hstring *)&v22, L"Unsupported or invalid encryption flags");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)&v22,
        (const struct winrt::impl::slim_source_location *)&v19);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
    v30 = *((_BYTE *)this + 128);
    *(_OWORD *)Block = 0;
    v32 = 0;
    v33 = 0;
    v3 = *((_QWORD *)this + 19);
    v4 = (_QWORD *)((char *)this + 136);
    if ( *((_QWORD *)this + 20) > 7u )
      v4 = (_QWORD *)*v4;
    v5 = 0x7FFFFFFFFFFFFFFELL;
    if ( v3 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v3 > 7 )
    {
      if ( (v3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        v5 = v3 | 7;
        if ( (v3 | 7) < 0xA )
          v5 = 10;
        v7 = v5 + 1;
        if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          __scrt_throw_std_bad_array_new_length();
      }
      else
      {
        v7 = 0x7FFFFFFFFFFFFFFFLL;
      }
      _mm_lfence();
      Block[0] = std::_Allocate<16,std::_Default_allocate_traits>(2 * v7);
      v32 = v3;
      v33 = v5;
      memmove(Block[0], v4, 2 * v3 + 2);
      v6 = v33;
      v3 = v32;
    }
    else
    {
      v32 = *((_QWORD *)this + 19);
      v6 = 7;
      v33 = 7;
      *(_OWORD *)Block = *(_OWORD *)v4;
    }
    if ( v3 != 64 )
    {
      LODWORD(v19) = 122;
      v20 = (__int64)"C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
      v21 = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)&v22,
        L"Invalid AES256 key size; expected 64 hex characters.");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)pExceptionObject,
        (const struct winrt::param::hstring *)&v22,
        (const struct winrt::impl::slim_source_location *)&v19);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    }
    v8 = Block;
    if ( v6 > 7 )
      v8 = (void **)Block[0];
    v19 = v8;
    v20 = 64;
    asg::HexStringToVector<unsigned char,std::vector<unsigned char,asg::secure_allocator<unsigned char>>>(v27, &v19);
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v12 = Src;
    v13 = v29 - (_BYTE *)Src;
    if ( v29 != Src && v13 != 32 && v13 != 8 )
    {
      std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "invalid encryption key");
      throw (std::invalid_argument *)pExceptionObject;
    }
    v26 = 0;
    v14 = 0;
    if ( v13 )
    {
      if ( v13 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
          v10,
          v9,
          v11);
      _mm_lfence();
      v15 = std::_Allocate<16,std::_Default_allocate_traits>(v29 - (_BYTE *)Src);
      v14 = (char *)v15 + v13;
      _mm_lfence();
      memmove(v15, v12, v13);
      v16 = (char *)v15 + v13;
    }
    else
    {
      v16 = (char *)*((_QWORD *)&v26 + 1);
      v15 = (_QWORD *)v26;
    }
    *(_QWORD *)&v23 = v15;
    *((_QWORD *)&v23 + 1) = v16;
    v24 = v14;
    std::vector<unsigned char,asg::secure_allocator<unsigned char>>::operator=((char *)this + 176, &v22);
    *((_DWORD *)this + 43) = 65538;
    std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(&v22);
    std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(v27);
    if ( v33 > 7 )
    {
      v17 = Block[0];
      v18 = 2 * v33 + 2;
      memset(Block[0], 0, v18);
      if ( v18 >= 0x1000 )
      {
        if ( (unsigned __int64)v17 - *(v17 - 1) - 8 > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
        v17 = (_QWORD *)*(v17 - 1);
      }
      _mm_lfence();
      operator delete(v17);
    }
  }
  *((_BYTE *)this + 168) = 0;
}

```

## disassembly

```asm
0x18000ee90  mov     [rsp-8+arg_8], rbx
0x18000ee95  mov     [rsp-8+arg_10], rsi
0x18000ee9a  mov     [rsp-8+arg_18], rdi
0x18000ee9f  push    rbp
0x18000eea0  push    r12
0x18000eea2  push    r13
0x18000eea4  push    r14
0x18000eea6  push    r15
0x18000eea8  lea     rbp, [rsp-37h]
0x18000eead  sub     rsp, 0E0h
0x18000eeb4  mov     rax, cs:__security_cookie
0x18000eebb  xor     rax, rsp
0x18000eebe  mov     [rbp+57h+var_28], rax
0x18000eec2  mov     rsi, rcx
0x18000eec5  xor     r13d, r13d
0x18000eec8  xorps   xmm0, xmm0
0x18000eecb  movups  [rbp+57h+var_B0], xmm0
0x18000eecf  movups  [rbp+57h+var_A0], xmm0
0x18000eed3  xorps   xmm1, xmm1
0x18000eed6  movdqu  [rbp+57h+var_B0+8], xmm1
0x18000eedb  mov     qword ptr [rbp+57h+var_A0+8], r13
0x18000eedf  lea     rdx, [rbp+57h+var_B0]
0x18000eee3  add     rcx, 0B0h
0x18000eeea  call    ??4?$vector@EU?$secure_allocator@E@asg@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,asg::secure_allocator<uchar>>::operator=(std::vector<uchar,asg::secure_allocator<uchar>> &&)
0x18000eeef  nop
0x18000eef0  lea     rcx, [rbp+57h+var_B0]
0x18000eef4  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18000eef9  mov     [rsi+0ACh], r13d
0x18000ef00  mov     eax, [rsi+78h]
0x18000ef03  test    eax, eax
0x18000ef05  jz      loc_18000F12B
0x18000ef0b  cmp     eax, 10001h
0x18000ef10  jnz     loc_18000F180
0x18000ef16  movzx   eax, byte ptr [rsi+80h]
0x18000ef1d  mov     [rbp+57h+var_50], al
0x18000ef20  xorps   xmm0, xmm0
0x18000ef23  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18000ef27  mov     [rbp+57h+var_38], r13
0x18000ef2b  mov     [rbp+57h+var_30], r13
0x18000ef2f  mov     rdi, [rsi+98h]
0x18000ef36  lea     r14, [rsi+88h]
0x18000ef3d  cmp     qword ptr [r14+18h], 7
0x18000ef42  jbe     short loc_18000EF47
0x18000ef44  mov     r14, [r14]
0x18000ef47  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18000ef51  cmp     rdi, rbx
0x18000ef54  ja      loc_18000F1C8
0x18000ef5a  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18000ef64  cmp     rdi, 7
0x18000ef68  ja      short loc_18000EF81
0x18000ef6a  mov     [rbp+57h+var_38], rdi
0x18000ef6e  mov     ecx, 7
0x18000ef73  mov     [rbp+57h+var_30], rcx
0x18000ef77  movups  xmm0, xmmword ptr [r14]
0x18000ef7b  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18000ef7f  jmp     short loc_18000EFC6
0x18000ef81  mov     rax, rdi
0x18000ef84  or      rax, 7
0x18000ef88  cmp     rax, rbx
0x18000ef8b  jbe     loc_18000F07C
0x18000ef91  mov     rcx, rdx
0x18000ef94  lfence
0x18000ef97  add     rcx, rcx
0x18000ef9a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000ef9f  mov     [rbp+57h+Block], rax
0x18000efa3  mov     [rbp+57h+var_38], rdi
0x18000efa7  mov     [rbp+57h+var_30], rbx
0x18000efab  lea     r8, ds:2[rdi*2]; Size
0x18000efb3  mov     rdx, r14; Src
0x18000efb6  mov     rcx, rax; void *
0x18000efb9  call    memmove
0x18000efbe  mov     rcx, [rbp+57h+var_30]
0x18000efc2  mov     rdi, [rbp+57h+var_38]
0x18000efc6  cmp     rdi, 40h ; '@'
0x18000efca  jnz     loc_18000F1CE
0x18000efd0  lea     rax, [rbp+57h+Block]
0x18000efd4  cmp     rcx, 7
0x18000efd8  cmova   rax, [rbp+57h+Block]
0x18000efdd  mov     qword ptr [rbp+57h+var_D0], rax
0x18000efe1  mov     qword ptr [rbp+57h+var_D0+8], 40h ; '@'
0x18000efe9  movaps  xmm0, [rbp+57h+var_D0]
0x18000efed  movdqa  [rbp+57h+var_D0], xmm0
0x18000eff2  lea     rdx, [rbp+57h+var_D0]
0x18000eff6  lea     rcx, [rbp+57h+var_70]
0x18000effa  call    ??$HexStringToVector@EV?$vector@EU?$secure_allocator@E@asg@@@std@@@asg@@YA?AV?$vector@EU?$secure_allocator@E@asg@@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@2@@Z; asg::HexStringToVector<uchar,std::vector<uchar,asg::secure_allocator<uchar>>>(std::u16string_view)
0x18000efff  nop
0x18000f000  xorps   xmm0, xmm0
0x18000f003  movups  [rbp+57h+var_B0], xmm0
0x18000f007  movups  [rbp+57h+var_A0], xmm0
0x18000f00b  xorps   xmm1, xmm1
0x18000f00e  movdqu  [rbp+57h+var_B0+8], xmm1
0x18000f013  mov     qword ptr [rbp+57h+var_A0+8], r13
0x18000f017  mov     r15, [rbp+57h+Src]
0x18000f01b  mov     rdi, [rbp+57h+var_60]
0x18000f01f  sub     rdi, r15
0x18000f022  jz      short loc_18000F034
0x18000f024  cmp     rdi, 20h ; ' '
0x18000f028  jz      short loc_18000F034
0x18000f02a  cmp     rdi, 8
0x18000f02e  jnz     loc_18000F216
0x18000f034  movdqu  [rbp+57h+var_88], xmm0
0x18000f039  mov     r14, r13
0x18000f03c  test    rdi, rdi
0x18000f03f  jz      short loc_18000F09D
0x18000f041  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000f04b  cmp     rdi, rax
0x18000f04e  ja      loc_18000F15F
0x18000f054  lfence
0x18000f057  mov     rcx, rdi
0x18000f05a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000f05f  mov     rbx, rax
0x18000f062  lea     r14, [rax+rdi]
0x18000f066  lfence
0x18000f069  mov     r8, rdi; Size
0x18000f06c  mov     rdx, r15; Src
0x18000f06f  mov     rcx, rax; void *
0x18000f072  call    memmove
0x18000f077  mov     rax, r14
0x18000f07a  jmp     short loc_18000F0A5
0x18000f07c  mov     rbx, rax
0x18000f07f  mov     ecx, 0Ah
0x18000f084  cmp     rax, rcx
0x18000f087  cmovb   rbx, rcx
0x18000f08b  lea     rcx, [rbx+1]
0x18000f08f  cmp     rcx, rdx
0x18000f092  ja      loc_18000F165
0x18000f098  jmp     loc_18000EF94
0x18000f09d  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18000f0a1  mov     rbx, qword ptr [rbp+57h+var_88]
0x18000f0a5  mov     qword ptr [rbp+57h+var_B0+8], rbx
0x18000f0a9  mov     qword ptr [rbp+57h+var_A0], rax
0x18000f0ad  mov     qword ptr [rbp+57h+var_A0+8], r14
0x18000f0b1  lea     rdx, [rbp+57h+var_B0]
0x18000f0b5  lea     rcx, [rsi+0B0h]
0x18000f0bc  call    ??4?$vector@EU?$secure_allocator@E@asg@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,asg::secure_allocator<uchar>>::operator=(std::vector<uchar,asg::secure_allocator<uchar>> &&)
0x18000f0c1  mov     dword ptr [rsi+0ACh], 10002h
0x18000f0cb  lea     rcx, [rbp+57h+var_B0]
0x18000f0cf  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18000f0d4  nop
0x18000f0d5  lea     rcx, [rbp+57h+var_70]
0x18000f0d9  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x18000f0de  nop
0x18000f0df  mov     rdx, [rbp+57h+var_30]
0x18000f0e3  cmp     rdx, 7
0x18000f0e7  jbe     short loc_18000F12B
0x18000f0e9  mov     r8, [rbp+57h+Block]
0x18000f0ed  lea     rdx, ds:2[rdx*2]
0x18000f0f5  mov     rdi, r8
0x18000f0f8  xor     eax, eax
0x18000f0fa  mov     rcx, rdx
0x18000f0fd  rep stosb
0x18000f0ff  cmp     rdx, 1000h
0x18000f106  jb      short loc_18000F120
0x18000f108  add     rdx, 27h ; '''
0x18000f10c  mov     rax, [r8-8]
0x18000f110  sub     r8, rax
0x18000f113  sub     r8, 8
0x18000f117  cmp     r8, 1Fh
0x18000f11b  ja      short loc_18000F16B
0x18000f11d  mov     r8, rax
0x18000f120  lfence
0x18000f123  mov     rcx, r8; Block
0x18000f126  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f12b  mov     byte ptr [rsi+0A8h], 0
0x18000f132  mov     rcx, [rbp+57h+var_28]
0x18000f136  xor     rcx, rsp; StackCookie
0x18000f139  call    __security_check_cookie
0x18000f13e  lea     r11, [rsp+100h+var_20]
0x18000f146  mov     rbx, [r11+38h]
0x18000f14a  mov     rsi, [r11+40h]
0x18000f14e  mov     rdi, [r11+48h]
0x18000f152  mov     rsp, r11
0x18000f155  pop     r15
0x18000f157  pop     r14
0x18000f159  pop     r13
0x18000f15b  pop     r12
0x18000f15d  pop     rbp
0x18000f15e  retn
0x18000f15f  call    ?_Xlength@?$vector@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@V?$allocator@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@std@@CAXXZ; std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> *>>::_Xlength(void)
0x18000f165  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18000f16b  mov     [rsp+100h+Reserved], r13; Reserved
0x18000f170  xor     r9d, r9d; LineNo
0x18000f173  xor     r8d, r8d; FileName
0x18000f176  xor     edx, edx; FunctionName
0x18000f178  xor     ecx, ecx; Expression
0x18000f17a  call    _invoke_watson
0x18000f180  mov     dword ptr [rbp+57h+var_D0], 74h ; 't'
0x18000f187  lea     rax, aCW1SSrcSemanti_25; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18000f18e  mov     qword ptr [rbp+57h+var_D0+8], rax
0x18000f192  mov     [rbp+57h+var_C0], r13
0x18000f196  lea     rdx, aUnsupportedOrI; "Unsupported or invalid encryption flags"
0x18000f19d  lea     rcx, [rbp+57h+var_B0]; this
0x18000f1a1  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18000f1a6  lea     r8, [rbp+57h+var_D0]; struct winrt::impl::slim_source_location *
0x18000f1aa  lea     rdx, [rbp+57h+var_B0]; struct winrt::param::hstring *
0x18000f1ae  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000f1b2  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18000f1b7  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18000f1be  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f1c2  call    _CxxThrowException
0x18000f1c8  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000f1ce  mov     dword ptr [rbp+57h+var_D0], 7Ah ; 'z'
0x18000f1d5  lea     rax, aCW1SSrcSemanti_25; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18000f1dc  mov     qword ptr [rbp+57h+var_D0+8], rax
0x18000f1e0  mov     [rbp+57h+var_C0], r13
0x18000f1e4  lea     rdx, aInvalidAes256K; "Invalid AES256 key size; expected 64 he"...
0x18000f1eb  lea     rcx, [rbp+57h+var_B0]; this
0x18000f1ef  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18000f1f4  lea     r8, [rbp+57h+var_D0]; struct winrt::impl::slim_source_location *
0x18000f1f8  lea     rdx, [rbp+57h+var_B0]; struct winrt::param::hstring *
0x18000f1fc  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000f200  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18000f205  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18000f20c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f210  call    _CxxThrowException
0x18000f216  lea     rdx, aInvalidEncrypt_0; "invalid encryption key"
0x18000f21d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000f221  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18000f226  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000f22d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000f231  call    _CxxThrowException
```
