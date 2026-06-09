# CtapHybridRenderQrCode

- ea: `0x180107f04`
- end: `0x1801082a5`
- name: `CtapHybridRenderQrCode`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180074000`

## callees

- `0x18003164c`
- `0x1800350b4`
- `0x180036da4`
- `0x180041458`
- `0x1800472cc`
- `0x18005378c`
- `0x18006b260`
- `0x180091540`
- `0x18009b620`
- `0x1800ae65c`
- `0x180103f98`
- `0x180107a30`
- `0x180107f04`
- `0x18012470c`
- `0x1801251f0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108268`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108268`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18010824b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18010824b`

## string_xrefs

- `0x180107f4e`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180107f7b`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180107fa6`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180107fcf`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180107ffe`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x1801080e4`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108076`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridcrypto.cpp`
- `0x180108113`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridcrypto.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CtapHybridRenderQrCode(__int64 a1, char a2, void **a3, _DWORD *a4)
{
  __int64 v7; // rax
  __int128 v8; // xmm7
  __int128 v9; // xmm8
  __m128i v10; // xmm6
  int CtapOperationHint; // eax
  unsigned int v12; // ebx
  char *v13; // rax
  __int64 QRCodeString; // rax
  HLOCAL v15; // rbx
  SIZE_T v16; // rax
  _BYTE *i; // rcx
  int v18; // [rsp+20h] [rbp-1A8h]
  char *v19; // [rsp+30h] [rbp-198h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-190h] BYREF
  void *v21; // [rsp+40h] [rbp-188h] BYREF
  void *Src; // [rsp+48h] [rbp-180h] BYREF
  __int64 v23; // [rsp+50h] [rbp-178h]
  __int128 v24; // [rsp+A8h] [rbp-120h] BYREF
  _BYTE v25[32]; // [rsp+B8h] [rbp-110h] BYREF
  _BYTE v26[40]; // [rsp+D8h] [rbp-F0h] BYREF
  _BYTE v27[48]; // [rsp+100h] [rbp-C8h]
  __m256i v28; // [rsp+130h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  if ( a1 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( *(_DWORD *)a1 == 104 )
        {
          if ( *(_DWORD *)(a1 + 16) == 16 )
          {
            v7 = *(_QWORD *)(a1 + 8);
            *(_OWORD *)v27 = *(_OWORD *)v7;
            *(_OWORD *)&v27[16] = *(_OWORD *)(v7 + 16);
            *(_OWORD *)&v27[32] = *(_OWORD *)(v7 + 32);
            v28 = *(__m256i *)(v7 + 48);
            if ( _mm_cvtsi128_si32(*(__m128i *)v27) != 843793221 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x32,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridcrypto.cpp",
                (const char *)0x80070057LL,
                v18);
            v8 = *(_OWORD *)&v27[8];
            v9 = *(_OWORD *)&v27[24];
            v10 = *(__m128i *)&v28.m256i_u64[1];
            v24 = 0;
            v24 = *(_OWORD *)*(_QWORD *)(a1 + 24);
            LODWORD(v19) = 0;
            LOBYTE(a1) = a2;
            CtapOperationHint = GetCtapOperationHint(a1, &v19);
            v12 = CtapOperationHint;
            if ( CtapOperationHint >= 0 )
            {
              wil::details::in1diag3::Throw_HrIfMsg(
                retaddr,
                (void *)0x21,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridcrypto.cpp",
                (const char *)0x80070057LL,
                0,
                (bool)"Invalid key",
                v19);
              wil::make_unique_hlocal_secure<CtapHybridInternal::P256CompressedPublicKey,>(&hMem);
              *(_BYTE *)hMem = _mm_cvtsi128_si32(_mm_srli_si128(v10, 15)) & 1 | 2;
              v13 = (char *)hMem;
              *(_OWORD *)((char *)hMem + 1) = v8;
              *(_OWORD *)(v13 + 17) = v9;
              std::string::string(v25);
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport>::GetImpl'::`2'::impl) )
                QRCodeString = CtapHybridInternal::GenerateQRCodeString(
                                 (unsigned int)v26,
                                 (_DWORD)hMem,
                                 (unsigned int)&v24,
                                 (_DWORD)v19,
                                 0);
              else
                QRCodeString = CtapHybridInternal::GenerateQRCodeString(
                                 (unsigned int)v26,
                                 (_DWORD)hMem,
                                 (unsigned int)&v24,
                                 (_DWORD)v19,
                                 1);
              std::string::operator=(v25, QRCodeString);
              std::string::_Tidy_deallocate(v26);
              CtapHybridInternal::CreateFidoQrCodePng(&Src, v25);
              wil::make_unique_cotaskmem<unsigned char [0]>(&v21, v23 - (_QWORD)Src);
              memcpy_0(v21, Src, v23 - (_QWORD)Src);
              *a3 = v21;
              *a4 = v23 - (_DWORD)Src;
              v21 = 0;
              std::vector<unsigned char>::_Tidy(&Src);
              std::string::_Tidy_deallocate(v25);
              v15 = hMem;
              hMem = 0;
              if ( v15 )
              {
                v16 = LocalSize(v15);
                for ( i = v15; v16; --v16 )
                  *i++ = 0;
                LocalFree(v15);
              }
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x65,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                (const char *)(unsigned int)CtapOperationHint,
                v18);
              return v12;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5B,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
              (const char *)0x80070057LL,
              v18);
            return 2147942487LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5A,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
            (const char *)0x80070057LL,
            v18);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
          (const char *)0x80004003LL,
          v18);
        return 2147500035LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
        (const char *)0x80004003LL,
        v18);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
      (const char *)0x80004003LL,
      v18);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180107f04  mov     rax, rsp
0x180107f07  push    rbx
0x180107f08  push    rsi
0x180107f09  push    rdi
0x180107f0a  sub     rsp, 1B0h
0x180107f11  movaps  xmmword ptr [rax-28h], xmm6
0x180107f15  movaps  xmmword ptr [rax-38h], xmm7
0x180107f19  movaps  xmmword ptr [rax-48h], xmm8
0x180107f1e  mov     rax, cs:__security_cookie
0x180107f25  xor     rax, rsp
0x180107f28  mov     [rsp+1C8h+var_58], rax
0x180107f30  mov     rsi, r9
0x180107f33  mov     rdi, r8
0x180107f36  mov     r8b, dl
0x180107f39  test    rcx, rcx
0x180107f3c  jnz     short loc_180107F66
0x180107f3e  mov     rcx, [rsp+1C8h]; this
0x180107f46  mov     ebx, 80004003h
0x180107f4b  mov     r9d, ebx; char *
0x180107f4e  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180107f55  mov     edx, 56h ; 'V'; void *
0x180107f5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180107f5f  mov     eax, ebx
0x180107f61  jmp     loc_180108276
0x180107f66  test    rdi, rdi
0x180107f69  jnz     short loc_180107F91
0x180107f6b  mov     rcx, [rsp+1C8h]; this
0x180107f73  mov     ebx, 80004003h
0x180107f78  mov     r9d, ebx; char *
0x180107f7b  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180107f82  lea     edx, [rdi+57h]; void *
0x180107f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180107f8a  mov     eax, ebx
0x180107f8c  jmp     loc_180108276
0x180107f91  test    rsi, rsi
0x180107f94  jnz     short loc_180107FBC
0x180107f96  mov     rcx, [rsp+1C8h]; this
0x180107f9e  mov     ebx, 80004003h
0x180107fa3  mov     r9d, ebx; char *
0x180107fa6  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180107fad  lea     edx, [rsi+58h]; void *
0x180107fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180107fb5  mov     eax, ebx
0x180107fb7  jmp     loc_180108276
0x180107fbc  cmp     dword ptr [rcx], 68h ; 'h'
0x180107fbf  jz      short loc_180107FEA
0x180107fc1  mov     rcx, [rsp+1C8h]; this
0x180107fc9  mov     r9d, 80070057h; char *
0x180107fcf  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180107fd6  mov     edx, 5Ah ; 'Z'; void *
0x180107fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180107fe0  mov     eax, 80070057h
0x180107fe5  jmp     loc_180108276
0x180107fea  cmp     dword ptr [rcx+10h], 10h
0x180107fee  jz      short loc_180108019
0x180107ff0  mov     rcx, [rsp+1C8h]; this
0x180107ff8  mov     r9d, 80070057h; char *
0x180107ffe  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180108005  mov     edx, 5Bh ; '['; void *
0x18010800a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010800f  mov     eax, 80070057h
0x180108014  jmp     loc_180108276
0x180108019  mov     rax, [rcx+8]
0x18010801d  movups  xmm2, xmmword ptr [rax]
0x180108020  movaps  [rsp+1C8h+var_C8], xmm2
0x180108028  movups  xmm0, xmmword ptr [rax+10h]
0x18010802c  movaps  [rsp+1C8h+var_B8], xmm0
0x180108034  movups  xmm1, xmmword ptr [rax+20h]
0x180108038  movaps  [rsp+1C8h+var_A8], xmm1
0x180108040  movups  xmm0, xmmword ptr [rax+30h]
0x180108044  movaps  [rsp+1C8h+var_98], xmm0
0x18010804c  movups  xmm1, xmmword ptr [rax+40h]
0x180108050  movaps  [rsp+1C8h+var_88], xmm1
0x180108058  movd    eax, xmm2
0x18010805c  cmp     eax, 324B4345h
0x180108061  setz    al
0x180108064  mov     r10, [rsp+1C8h]
0x18010806c  test    al, al
0x18010806e  jnz     short loc_18010808A
0x180108070  mov     r9d, 80070057h; char *
0x180108076  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010807d  mov     edx, 32h ; '2'; void *
0x180108082  mov     rcx, r10; this
0x180108085  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010808a  movups  xmm7, [rsp+1C8h+var_C8+8]
0x180108092  movups  xmm8, [rsp+1C8h+var_B8+8]
0x18010809b  movups  xmm6, [rsp+1C8h+var_98+8]
0x1801080a3  xorps   xmm0, xmm0
0x1801080a6  movups  [rsp+1C8h+var_120], xmm0
0x1801080ae  mov     rax, [rcx+18h]
0x1801080b2  movups  xmm1, xmmword ptr [rax]
0x1801080b5  movdqu  [rsp+1C8h+var_120], xmm1
0x1801080be  mov     dword ptr [rsp+1C8h+var_198], 0; char *
0x1801080c6  lea     rdx, [rsp+1C8h+var_198]
0x1801080cb  mov     cl, r8b
0x1801080ce  call    GetCtapOperationHint
0x1801080d3  mov     ebx, eax
0x1801080d5  mov     rcx, [rsp+1C8h]; this
0x1801080dd  test    eax, eax
0x1801080df  jns     short loc_1801080FC
0x1801080e1  mov     r9d, eax; char *
0x1801080e4  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801080eb  mov     edx, 65h ; 'e'; void *
0x1801080f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801080f5  mov     eax, ebx
0x1801080f7  jmp     loc_180108276
0x1801080fc  lea     rax, aInvalidKey; "Invalid key"
0x180108103  mov     qword ptr [rsp+1C8h+var_1A0], rax; bool
0x180108108  mov     [rsp+1C8h+var_1A8], 0; char
0x18010810d  mov     r9d, 80070057h; char *
0x180108113  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010811a  mov     edx, 21h ; '!'; void *
0x18010811f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180108124  lea     rcx, [rsp+1C8h+hMem]
0x180108129  call    ??$make_unique_hlocal_secure@UP256CompressedPublicKey@CtapHybridInternal@@$$V@wil@@YA?AV?$unique_ptr@UP256CompressedPublicKey@CtapHybridInternal@@Uhlocal_secure_deleter@wil@@@wistd@@XZ; wil::make_unique_hlocal_secure<CtapHybridInternal::P256CompressedPublicKey,>(void)
0x18010812e  psrldq  xmm6, 0Fh
0x180108133  movd    ecx, xmm6
0x180108137  and     cl, 1
0x18010813a  or      cl, 2
0x18010813d  mov     rax, [rsp+1C8h+hMem]
0x180108142  mov     [rax], cl
0x180108144  mov     rax, [rsp+1C8h+hMem]
0x180108149  movups  xmmword ptr [rax+1], xmm7
0x18010814d  movups  xmmword ptr [rax+11h], xmm8
0x180108152  lea     rcx, [rsp+1C8h+var_110]
0x18010815a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18010815f  nop
0x180108160  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport> `wil::Feature<__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport>::GetImpl(void)'::`2'::impl
0x180108167  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableHybridLinkedDeviceSupport>::__private_IsEnabled(void)
0x18010816c  mov     r9d, dword ptr [rsp+1C8h+var_198]
0x180108171  lea     r8, [rsp+1C8h+var_120]
0x180108179  mov     rdx, [rsp+1C8h+hMem]
0x18010817e  lea     rcx, [rsp+1C8h+var_F0]
0x180108186  test    al, al
0x180108188  jnz     short loc_180108199
0x18010818a  mov     dword ptr [rsp+1C8h+var_1A8], 1
0x180108192  call    ?GenerateQRCodeString@CtapHybridInternal@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUP256CompressedPublicKey@1@AEBUQrSymetricSecret@1@W4CtapOperationHint@1@H@Z; CtapHybridInternal::GenerateQRCodeString(CtapHybridInternal::P256CompressedPublicKey const &,CtapHybridInternal::QrSymetricSecret const &,CtapHybridInternal::CtapOperationHint,int)
0x180108197  jmp     short loc_1801081A6
0x180108199  mov     dword ptr [rsp+1C8h+var_1A8], 0
0x1801081a1  call    ?GenerateQRCodeString@CtapHybridInternal@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUP256CompressedPublicKey@1@AEBUQrSymetricSecret@1@W4CtapOperationHint@1@H@Z; CtapHybridInternal::GenerateQRCodeString(CtapHybridInternal::P256CompressedPublicKey const &,CtapHybridInternal::QrSymetricSecret const &,CtapHybridInternal::CtapOperationHint,int)
0x1801081a6  mov     rdx, rax
0x1801081a9  lea     rcx, [rsp+1C8h+var_110]
0x1801081b1  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1801081b6  lea     rcx, [rsp+1C8h+var_F0]
0x1801081be  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801081c3  lea     rdx, [rsp+1C8h+var_110]
0x1801081cb  lea     rcx, [rsp+1C8h+Src]
0x1801081d0  call    ?CreateFidoQrCodePng@CtapHybridInternal@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; CtapHybridInternal::CreateFidoQrCodePng(std::string const &)
0x1801081d5  nop
0x1801081d6  mov     rdx, [rsp+1C8h+var_178]
0x1801081db  sub     rdx, [rsp+1C8h+Src]
0x1801081e0  lea     rcx, [rsp+1C8h+var_188]
0x1801081e5  call    ??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)
0x1801081ea  mov     rdx, [rsp+1C8h+Src]; Src
0x1801081ef  mov     r8, [rsp+1C8h+var_178]
0x1801081f4  sub     r8, rdx; Size
0x1801081f7  mov     rcx, [rsp+1C8h+var_188]; void *
0x1801081fc  call    memcpy_0
0x180108201  mov     rax, [rsp+1C8h+var_188]
0x180108206  mov     [rdi], rax
0x180108209  mov     eax, dword ptr [rsp+1C8h+var_178]
0x18010820d  sub     eax, dword ptr [rsp+1C8h+Src]
0x180108211  mov     [rsi], eax
0x180108213  mov     [rsp+1C8h+var_188], 0
0x18010821c  lea     rcx, [rsp+1C8h+Src]
0x180108221  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180108226  nop
0x180108227  lea     rcx, [rsp+1C8h+var_110]
0x18010822f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180108234  nop
0x180108235  mov     rbx, [rsp+1C8h+hMem]
0x18010823a  mov     [rsp+1C8h+hMem], 0
0x180108243  test    rbx, rbx
0x180108246  jz      short loc_18010826E
0x180108248  mov     rcx, rbx; hMem
0x18010824b  call    cs:__imp_LocalSize
0x180108251  mov     rcx, rbx
0x180108254  test    rax, rax
0x180108257  jz      short loc_180108265
0x180108259  mov     byte ptr [rcx], 0
0x18010825c  inc     rcx
0x18010825f  sub     rax, 1
0x180108263  jnz     short loc_180108259
0x180108265  mov     rcx, rbx; hMem
0x180108268  call    cs:__imp_LocalFree
0x18010826e  xor     eax, eax
0x180108270  jmp     short loc_180108276
0x180108272  mov     eax, dword ptr [rsp+1C8h+var_198]
0x180108276  mov     rcx, [rsp+1C8h+var_58]
0x18010827e  xor     rcx, rsp; StackCookie
0x180108281  call    __security_check_cookie
0x180108286  lea     r11, [rsp+1C8h+var_18]
0x18010828e  movaps  xmm6, xmmword ptr [r11-10h]
0x180108293  movaps  xmm7, xmmword ptr [r11-20h]
0x180108298  movaps  xmm8, xmmword ptr [r11-30h]
0x18010829d  mov     rsp, r11
0x1801082a0  pop     rdi
0x1801082a1  pop     rsi
0x1801082a2  pop     rbx
0x1801082a3  retn
```
