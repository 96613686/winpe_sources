# NgcMCloud::FidoHmacMetadata::FromCbor(std::span<uchar const,-1>)

- ea: `0x1801376b8`
- end: `0x180137d8e`
- name: `?FromCbor@FidoHmacMetadata@NgcMCloud@@SA?AU12@V?$span@$$CBE$0?0@std@@@Z`
- size: `1750`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x18013630c`

## callees

- `0x18001d5e4`
- `0x18001d5fc`
- `0x18001df88`
- `0x180023bc8`
- `0x1800350b4`
- `0x180037f6c`
- `0x18008e304`
- `0x18008e458`
- `0x18008f3e8`
- `0x18008f67c`
- `0x180090c44`
- `0x180090dc0`
- `0x180091034`
- `0x1800910c0`
- `0x1800912f4`
- `0x1800c1a14`
- `0x1800c1e48`
- `0x1800c1e84`
- `0x1800c3718`
- `0x180136010`
- `0x1801376b8`
- `0x18013c090`

## string_xrefs

- `0x18013776c`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x18013780d`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137835`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x1801378c9`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x1801378e8`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x18013790a`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137953`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137975`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x1801379be`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x1801379e0`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137a29`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137a4b`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137a94`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137ab6`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137aff`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137b24`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137b62`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137b90`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137be5`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137c13`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137c68`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137c8f`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137cc1`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137ce8`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`
- `0x180137d0f`: `onecore\ds\security\ngc\lockbox\common\lib\fidoprotector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall NgcMCloud::FidoHmacMetadata::FromCbor(char *a1, __int128 *a2)
{
  char *v3; // rdi
  int v4; // ebx
  int v5; // r14d
  int v6; // r15d
  int v7; // edi
  int v8; // esi
  int v9; // r12d
  int v10; // r13d
  __int128 *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 ByteString; // rax
  __int64 Int; // rax
  __int64 v18; // rax
  __int64 TextWString; // rax
  __int128 v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh]
  const char *v24; // [rsp+48h] [rbp-B8h]
  _BYTE v25[64]; // [rsp+50h] [rbp-B0h] BYREF
  char *Uint; // [rsp+90h] [rbp-70h]
  char *v27; // [rsp+A8h] [rbp-58h]
  _DWORD v28[2]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v29; // [rsp+B8h] [rbp-48h]
  _DWORD v30[2]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v31; // [rsp+C8h] [rbp-38h]
  _DWORD v32[2]; // [rsp+D0h] [rbp-30h] BYREF
  const char *v33; // [rsp+D8h] [rbp-28h]
  _DWORD v34[2]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v35; // [rsp+E8h] [rbp-18h]
  _DWORD v36[2]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v37; // [rsp+F8h] [rbp-8h]
  _DWORD v38[2]; // [rsp+100h] [rbp+0h] BYREF
  const char *v39; // [rsp+108h] [rbp+8h]
  _DWORD v40[2]; // [rsp+110h] [rbp+10h] BYREF
  const char *v41; // [rsp+118h] [rbp+18h]
  _DWORD v42[2]; // [rsp+120h] [rbp+20h] BYREF
  const char *v43; // [rsp+128h] [rbp+28h]
  _DWORD v44[2]; // [rsp+130h] [rbp+30h] BYREF
  const char *v45; // [rsp+138h] [rbp+38h]
  _DWORD v46[2]; // [rsp+140h] [rbp+40h] BYREF
  const char *v47; // [rsp+148h] [rbp+48h]
  _DWORD v48[2]; // [rsp+150h] [rbp+50h] BYREF
  const char *v49; // [rsp+158h] [rbp+58h]
  _DWORD v50[2]; // [rsp+160h] [rbp+60h] BYREF
  const char *v51; // [rsp+168h] [rbp+68h]
  _DWORD v52[2]; // [rsp+170h] [rbp+70h] BYREF
  const char *v53; // [rsp+178h] [rbp+78h]
  _DWORD v54[2]; // [rsp+180h] [rbp+80h] BYREF
  const char *v55; // [rsp+188h] [rbp+88h]
  _DWORD v56[2]; // [rsp+190h] [rbp+90h] BYREF
  const char *v57; // [rsp+198h] [rbp+98h]
  _DWORD v58[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  const char *v59; // [rsp+1A8h] [rbp+A8h]
  _DWORD v60[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  const char *v61; // [rsp+1B8h] [rbp+B8h]
  _DWORD v62[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  const char *v63; // [rsp+1C8h] [rbp+C8h]
  _DWORD v64[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  const char *v65; // [rsp+1D8h] [rbp+D8h]
  _DWORD v66[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  const char *v67; // [rsp+1E8h] [rbp+E8h]
  _BYTE v68[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v69; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v70[32]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v71[32]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v72; // [rsp+258h] [rbp+158h]
  _BYTE v73[24]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v74[24]; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v75[24]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v76[24]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v77[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v3 = a1;
  v27 = a1;
  Uint = a1;
  v69 = 0;
  std::wstring::wstring(v70);
  std::wstring::wstring(v71);
  v72 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v73);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v74);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v75);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v76);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v77);
  v22 = 39;
  v23 = DWORD1(v21);
  v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
  v21 = *a2;
  SimpleCbor::Decoder::Decoder(v25, &v21, &v22);
  v22 = 41;
  v23 = DWORD1(v21);
  v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
  SimpleCbor::Decoder::EnterMap(v25, &v22);
  v22 = 42;
  v4 = DWORD1(v21);
  v23 = DWORD1(v21);
  v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v25, &v22) )
  {
    v5 = DWORD1(v21);
    v6 = DWORD1(v21);
    v7 = DWORD1(v21);
    v8 = DWORD1(v21);
    v9 = DWORD1(v21);
    v10 = DWORD1(v21);
    do
    {
      v28[0] = 44;
      v28[1] = v5;
      v29 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
      Uint = (char *)SimpleCbor::Decoder::GetUint(v25, v28);
      v30[0] = 45;
      v30[1] = v6;
      v31 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
      SimpleCbor::Decoder::NextItem(v25, v30);
      if ( Uint == (char *)1 )
      {
        v66[0] = 50;
        v66[1] = v7;
        v67 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v69 = SimpleCbor::Decoder::GetUint(v25, v66);
        LODWORD(v21) = 51;
        DWORD1(v21) = v8;
        *((_QWORD *)&v21 + 1) = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = &v21;
      }
      else if ( Uint == (char *)2 )
      {
        v62[0] = 54;
        v62[1] = DWORD1(v21);
        v63 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        TextWString = SimpleCbor::Decoder::GetTextWString(v25, v68, v62);
        std::wstring::operator=(v70, TextWString);
        std::wstring::_Tidy_deallocate(v68);
        v64[0] = 55;
        v64[1] = DWORD1(v21);
        v65 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v64;
      }
      else if ( Uint == (char *)3 )
      {
        v58[0] = 58;
        v58[1] = DWORD1(v21);
        v59 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v18 = SimpleCbor::Decoder::GetTextWString(v25, v68, v58);
        std::wstring::operator=(v71, v18);
        std::wstring::_Tidy_deallocate(v68);
        v60[0] = 59;
        v60[1] = DWORD1(v21);
        v61 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v60;
      }
      else if ( Uint == (char *)4 )
      {
        v54[0] = 63;
        v54[1] = v9;
        v55 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        Int = SimpleCbor::Decoder::GetInt(v25, v54);
        LODWORD(v72) = wil::safe_cast<unsigned long,__int64,0>(Int);
        v56[0] = 64;
        v56[1] = v10;
        v57 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v56;
      }
      else if ( Uint == (char *)5 )
      {
        v50[0] = 67;
        v50[1] = DWORD1(v21);
        v51 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        ByteString = SimpleCbor::Decoder::GetByteString(v25, v68, v50);
        std::vector<unsigned char>::operator=(v73, ByteString);
        std::vector<unsigned char>::_Tidy(v68);
        v52[0] = 68;
        v52[1] = DWORD1(v21);
        v53 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v52;
      }
      else if ( Uint == (char *)6 )
      {
        v46[0] = 71;
        v46[1] = DWORD1(v21);
        v47 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v15 = SimpleCbor::Decoder::GetByteString(v25, v68, v46);
        std::vector<unsigned char>::operator=(v74, v15);
        std::vector<unsigned char>::_Tidy(v68);
        v48[0] = 72;
        v48[1] = DWORD1(v21);
        v49 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v48;
      }
      else if ( Uint == (char *)7 )
      {
        v42[0] = 75;
        v42[1] = DWORD1(v21);
        v43 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v14 = SimpleCbor::Decoder::GetByteString(v25, v68, v42);
        std::vector<unsigned char>::operator=(v75, v14);
        std::vector<unsigned char>::_Tidy(v68);
        v44[0] = 76;
        v44[1] = DWORD1(v21);
        v45 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v44;
      }
      else if ( Uint == (char *)8 )
      {
        v38[0] = 79;
        v38[1] = DWORD1(v21);
        v39 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v13 = SimpleCbor::Decoder::GetByteString(v25, v68, v38);
        std::vector<unsigned char>::operator=(v76, v13);
        std::vector<unsigned char>::_Tidy(v68);
        v40[0] = 80;
        v40[1] = DWORD1(v21);
        v41 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v40;
      }
      else if ( Uint == (char *)9 )
      {
        v34[0] = 83;
        v34[1] = DWORD1(v21);
        v35 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v12 = SimpleCbor::Decoder::GetByteString(v25, v68, v34);
        std::vector<unsigned char>::operator=(v77, v12);
        std::vector<unsigned char>::_Tidy(v68);
        v36[0] = 84;
        v36[1] = DWORD1(v21);
        v37 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v36;
      }
      else
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Unknown item in FidoHmacMetadata: %llu",
          Uint);
        v32[0] = 89;
        v32[1] = DWORD1(v21);
        v33 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
        v11 = (__int128 *)v32;
      }
      SimpleCbor::Decoder::NextItem(v25, v11);
      v22 = 42;
      v23 = v4;
      v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
    }
    while ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v25, &v22) );
    v3 = v27;
  }
  LODWORD(v21) = 93;
  *((_QWORD *)&v21 + 1) = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\fidoprotector.cpp";
  SimpleCbor::Decoder::LeaveContainer(v25, &v21);
  NgcMCloud::FidoHmacMetadata::FidoHmacMetadata(v3, &v69);
  SimpleCbor::Decoder::~Decoder((SimpleCbor::Decoder *)v25);
  NgcMCloud::FidoHmacMetadata::~FidoHmacMetadata((NgcMCloud::FidoHmacMetadata *)&v69);
  return v3;
}

```

## disassembly

```asm
0x1801376b8  mov     [rsp-8+arg_10], rbx
0x1801376bd  push    rbp
0x1801376be  push    rsi
0x1801376bf  push    rdi
0x1801376c0  push    r12
0x1801376c2  push    r13
0x1801376c4  push    r14
0x1801376c6  push    r15
0x1801376c8  lea     rbp, [rsp-1F0h]
0x1801376d0  sub     rsp, 2F0h
0x1801376d7  mov     rax, cs:__security_cookie
0x1801376de  xor     rax, rsp
0x1801376e1  mov     [rbp+220h+var_40], rax
0x1801376e8  mov     rbx, rdx
0x1801376eb  mov     rdi, rcx
0x1801376ee  mov     [rbp+220h+var_278], rcx
0x1801376f2  mov     [rbp+220h+var_290], rcx
0x1801376f6  xor     r14d, r14d
0x1801376f9  mov     [rbp+220h+var_110], r14
0x180137700  lea     rcx, [rbp+220h+var_108]
0x180137707  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013770c  lea     rcx, [rbp+220h+var_E8]
0x180137713  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180137718  mov     [rbp+220h+var_C8], r14
0x18013771f  lea     rcx, [rbp+220h+var_C0]
0x180137726  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18013772b  lea     rcx, [rbp+220h+var_A8]
0x180137732  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180137737  lea     rcx, [rbp+220h+var_90]
0x18013773e  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180137743  lea     rcx, [rbp+220h+var_78]
0x18013774a  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18013774f  lea     rcx, [rbp+220h+var_60]
0x180137756  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18013775b  nop
0x18013775c  mov     [rsp+320h+var_2E0], 27h ; '''
0x180137764  mov     eax, [rsp+320h+var_2EC]
0x180137768  mov     [rsp+320h+var_2DC], eax
0x18013776c  lea     rsi, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137773  mov     [rsp+320h+var_2D8], rsi
0x180137778  movaps  xmm0, xmmword ptr [rbx]
0x18013777b  movdqa  xmmword ptr [rsp+30h], xmm0
0x180137781  lea     r8, [rsp+320h+var_2E0]
0x180137786  lea     rdx, [rsp+320h+var_2F0]
0x18013778b  lea     rcx, [rsp+320h+var_2D0]
0x180137790  call    ??0Decoder@SimpleCbor@@QEAA@V?$span@$$CBE$0?0@std@@Uslim_source_location@impl@1@@Z; SimpleCbor::Decoder::Decoder(std::span<uchar const,-1>,SimpleCbor::impl::slim_source_location)
0x180137795  nop
0x180137796  mov     [rsp+320h+var_2E0], 29h ; ')'
0x18013779e  mov     eax, [rsp+320h+var_2EC]
0x1801377a2  mov     [rsp+320h+var_2DC], eax
0x1801377a6  mov     [rsp+320h+var_2D8], rsi
0x1801377ab  lea     rdx, [rsp+320h+var_2E0]
0x1801377b0  lea     rcx, [rsp+320h+var_2D0]
0x1801377b5  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x1801377ba  mov     [rsp+320h+var_2E0], 2Ah ; '*'
0x1801377c2  mov     ebx, [rsp+320h+var_2EC]
0x1801377c6  mov     [rsp+320h+var_2DC], ebx
0x1801377ca  mov     [rsp+320h+var_2D8], rsi
0x1801377cf  lea     rdx, [rsp+320h+var_2E0]
0x1801377d4  lea     rcx, [rsp+320h+var_2D0]
0x1801377d9  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x1801377de  test    al, al
0x1801377e0  jnz     loc_180137D16
0x1801377e6  mov     r14d, [rsp+320h+var_2EC]
0x1801377eb  mov     r15d, [rsp+320h+var_2EC]
0x1801377f0  mov     edi, [rsp+320h+var_2EC]
0x1801377f4  mov     esi, [rsp+320h+var_2EC]
0x1801377f8  mov     r12d, [rsp+320h+var_2EC]
0x1801377fd  mov     r13d, [rsp+320h+var_2EC]
0x180137802  mov     [rbp+220h+var_270], 2Ch ; ','
0x180137809  mov     [rbp+220h+var_26C], r14d
0x18013780d  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137814  mov     [rbp+220h+var_268], rax
0x180137818  lea     rdx, [rbp+220h+var_270]
0x18013781c  lea     rcx, [rsp+320h+var_2D0]
0x180137821  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180137826  mov     [rbp+220h+var_290], rax
0x18013782a  mov     [rbp+220h+var_260], 2Dh ; '-'
0x180137831  mov     [rbp+220h+var_25C], r15d
0x180137835  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013783c  mov     [rbp+220h+var_258], rax
0x180137840  lea     rdx, [rbp+220h+var_260]
0x180137844  lea     rcx, [rsp+320h+var_2D0]
0x180137849  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x18013784e  mov     rax, [rbp+220h+var_290]
0x180137852  mov     rcx, rax
0x180137855  sub     rcx, 1
0x180137859  jz      loc_180137C7F
0x18013785f  sub     rcx, 1
0x180137863  jz      loc_180137BFF
0x180137869  sub     rcx, 1
0x18013786d  jz      loc_180137B7C
0x180137873  sub     rcx, 1
0x180137877  jz      loc_180137B13
0x18013787d  sub     rcx, 1
0x180137881  jz      loc_180137AA8
0x180137887  sub     rcx, 1
0x18013788b  jz      loc_180137A3D
0x180137891  sub     rcx, 1
0x180137895  jz      loc_1801379D2
0x18013789b  sub     rcx, 1
0x18013789f  jz      loc_180137967
0x1801378a5  cmp     rcx, 1
0x1801378a9  jz      short loc_1801378FC
0x1801378ab  mov     rcx, [rbp+228h]; this
0x1801378b2  mov     [rsp+320h+var_2F8], rax; char *
0x1801378b7  lea     rax, aUnknownItemInF; "Unknown item in FidoHmacMetadata: %llu"
0x1801378be  mov     qword ptr [rsp+320h+var_300], rax; int
0x1801378c3  mov     r9d, 8000FFFFh; char *
0x1801378c9  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801378d0  mov     edx, 58h ; 'X'; void *
0x1801378d5  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801378da  mov     [rbp+220h+var_250], 59h ; 'Y'
0x1801378e1  mov     eax, [rsp+320h+var_2EC]
0x1801378e5  mov     [rbp+220h+var_24C], eax
0x1801378e8  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801378ef  mov     [rbp+220h+var_248], rax
0x1801378f3  lea     rdx, [rbp+220h+var_250]
0x1801378f7  jmp     loc_180137CD2
0x1801378fc  mov     [rbp+220h+var_240], 53h ; 'S'
0x180137903  mov     eax, [rsp+320h+var_2EC]
0x180137907  mov     [rbp+220h+var_23C], eax
0x18013790a  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137911  mov     [rbp+220h+var_238], rax
0x180137915  lea     r8, [rbp+220h+var_240]
0x180137919  lea     rdx, [rbp+220h+var_130]
0x180137920  lea     rcx, [rsp+320h+var_2D0]
0x180137925  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x18013792a  mov     rdx, rax
0x18013792d  lea     rcx, [rbp+220h+var_60]
0x180137934  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180137939  lea     rcx, [rbp+220h+var_130]
0x180137940  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180137945  mov     [rbp+220h+var_230], 54h ; 'T'
0x18013794c  mov     eax, [rsp+320h+var_2EC]
0x180137950  mov     [rbp+220h+var_22C], eax
0x180137953  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013795a  mov     [rbp+220h+var_228], rax
0x18013795e  lea     rdx, [rbp+220h+var_230]
0x180137962  jmp     loc_180137CD2
0x180137967  mov     [rbp+220h+var_220], 4Fh ; 'O'
0x18013796e  mov     eax, [rsp+320h+var_2EC]
0x180137972  mov     [rbp+220h+var_21C], eax
0x180137975  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013797c  mov     [rbp+220h+var_218], rax
0x180137980  lea     r8, [rbp+220h+var_220]
0x180137984  lea     rdx, [rbp+220h+var_130]
0x18013798b  lea     rcx, [rsp+320h+var_2D0]
0x180137990  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180137995  mov     rdx, rax
0x180137998  lea     rcx, [rbp+220h+var_78]
0x18013799f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1801379a4  lea     rcx, [rbp+220h+var_130]
0x1801379ab  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801379b0  mov     [rbp+220h+var_210], 50h ; 'P'
0x1801379b7  mov     eax, [rsp+320h+var_2EC]
0x1801379bb  mov     [rbp+220h+var_20C], eax
0x1801379be  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801379c5  mov     [rbp+220h+var_208], rax
0x1801379c9  lea     rdx, [rbp+220h+var_210]
0x1801379cd  jmp     loc_180137CD2
0x1801379d2  mov     [rbp+220h+var_200], 4Bh ; 'K'
0x1801379d9  mov     eax, [rsp+320h+var_2EC]
0x1801379dd  mov     [rbp+220h+var_1FC], eax
0x1801379e0  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801379e7  mov     [rbp+220h+var_1F8], rax
0x1801379eb  lea     r8, [rbp+220h+var_200]
0x1801379ef  lea     rdx, [rbp+220h+var_130]
0x1801379f6  lea     rcx, [rsp+320h+var_2D0]
0x1801379fb  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180137a00  mov     rdx, rax
0x180137a03  lea     rcx, [rbp+220h+var_90]
0x180137a0a  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180137a0f  lea     rcx, [rbp+220h+var_130]
0x180137a16  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180137a1b  mov     [rbp+220h+var_1F0], 4Ch ; 'L'
0x180137a22  mov     eax, [rsp+320h+var_2EC]
0x180137a26  mov     [rbp+220h+var_1EC], eax
0x180137a29  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137a30  mov     [rbp+220h+var_1E8], rax
0x180137a34  lea     rdx, [rbp+220h+var_1F0]
0x180137a38  jmp     loc_180137CD2
0x180137a3d  mov     [rbp+220h+var_1E0], 47h ; 'G'
0x180137a44  mov     eax, [rsp+320h+var_2EC]
0x180137a48  mov     [rbp+220h+var_1DC], eax
0x180137a4b  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137a52  mov     [rbp+220h+var_1D8], rax
0x180137a56  lea     r8, [rbp+220h+var_1E0]
0x180137a5a  lea     rdx, [rbp+220h+var_130]
0x180137a61  lea     rcx, [rsp+320h+var_2D0]
0x180137a66  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180137a6b  mov     rdx, rax
0x180137a6e  lea     rcx, [rbp+220h+var_A8]
0x180137a75  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180137a7a  lea     rcx, [rbp+220h+var_130]
0x180137a81  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180137a86  mov     [rbp+220h+var_1D0], 48h ; 'H'
0x180137a8d  mov     eax, [rsp+320h+var_2EC]
0x180137a91  mov     [rbp+220h+var_1CC], eax
0x180137a94  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137a9b  mov     [rbp+220h+var_1C8], rax
0x180137a9f  lea     rdx, [rbp+220h+var_1D0]
0x180137aa3  jmp     loc_180137CD2
0x180137aa8  mov     [rbp+220h+var_1C0], 43h ; 'C'
0x180137aaf  mov     eax, [rsp+320h+var_2EC]
0x180137ab3  mov     [rbp+220h+var_1BC], eax
0x180137ab6  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137abd  mov     [rbp+220h+var_1B8], rax
0x180137ac1  lea     r8, [rbp+220h+var_1C0]
0x180137ac5  lea     rdx, [rbp+220h+var_130]
0x180137acc  lea     rcx, [rsp+320h+var_2D0]
0x180137ad1  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180137ad6  mov     rdx, rax
0x180137ad9  lea     rcx, [rbp+220h+var_C0]
0x180137ae0  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180137ae5  lea     rcx, [rbp+220h+var_130]
0x180137aec  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180137af1  mov     [rbp+220h+var_1B0], 44h ; 'D'
0x180137af8  mov     eax, [rsp+320h+var_2EC]
0x180137afc  mov     [rbp+220h+var_1AC], eax
0x180137aff  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137b06  mov     [rbp+220h+var_1A8], rax
0x180137b0a  lea     rdx, [rbp+220h+var_1B0]
0x180137b0e  jmp     loc_180137CD2
0x180137b13  mov     [rbp+220h+var_1A0], 3Fh ; '?'
0x180137b1d  mov     [rbp+220h+var_19C], r12d
0x180137b24  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137b2b  mov     [rbp+220h+var_198], rax
0x180137b32  lea     rdx, [rbp+220h+var_1A0]
0x180137b39  lea     rcx, [rsp+320h+var_2D0]
0x180137b3e  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x180137b43  mov     rcx, rax
0x180137b46  call    ??$safe_cast@K_J$0A@@wil@@YAK_J@Z; wil::safe_cast<ulong,__int64,0>(__int64)
0x180137b4b  mov     dword ptr [rbp+220h+var_C8], eax
0x180137b51  mov     [rbp+220h+var_190], 40h ; '@'
0x180137b5b  mov     [rbp+220h+var_18C], r13d
0x180137b62  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137b69  mov     [rbp+220h+var_188], rax
0x180137b70  lea     rdx, [rbp+220h+var_190]
0x180137b77  jmp     loc_180137CD2
0x180137b7c  mov     [rbp+220h+var_180], 3Ah ; ':'
0x180137b86  mov     eax, [rsp+320h+var_2EC]
0x180137b8a  mov     [rbp+220h+var_17C], eax
0x180137b90  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137b97  mov     [rbp+220h+var_178], rax
0x180137b9e  lea     r8, [rbp+220h+var_180]
0x180137ba5  lea     rdx, [rbp+220h+var_130]
0x180137bac  lea     rcx, [rsp+320h+var_2D0]
0x180137bb1  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x180137bb6  mov     rdx, rax
0x180137bb9  lea     rcx, [rbp+220h+var_E8]
0x180137bc0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180137bc5  lea     rcx, [rbp+220h+var_130]
0x180137bcc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137bd1  mov     [rbp+220h+var_170], 3Bh ; ';'
0x180137bdb  mov     eax, [rsp+320h+var_2EC]
0x180137bdf  mov     [rbp+220h+var_16C], eax
0x180137be5  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137bec  mov     [rbp+220h+var_168], rax
0x180137bf3  lea     rdx, [rbp+220h+var_170]
0x180137bfa  jmp     loc_180137CD2
0x180137bff  mov     [rbp+220h+var_160], 36h ; '6'
0x180137c09  mov     eax, [rsp+320h+var_2EC]
0x180137c0d  mov     [rbp+220h+var_15C], eax
0x180137c13  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137c1a  mov     [rbp+220h+var_158], rax
0x180137c21  lea     r8, [rbp+220h+var_160]
0x180137c28  lea     rdx, [rbp+220h+var_130]
0x180137c2f  lea     rcx, [rsp+320h+var_2D0]
0x180137c34  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x180137c39  mov     rdx, rax
0x180137c3c  lea     rcx, [rbp+220h+var_108]
0x180137c43  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180137c48  lea     rcx, [rbp+220h+var_130]
0x180137c4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137c54  mov     [rbp+220h+var_150], 37h ; '7'
0x180137c5e  mov     eax, [rsp+320h+var_2EC]
0x180137c62  mov     [rbp+220h+var_14C], eax
0x180137c68  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137c6f  mov     [rbp+220h+var_148], rax
0x180137c76  lea     rdx, [rbp+220h+var_150]
0x180137c7d  jmp     short loc_180137CD2
0x180137c7f  mov     [rbp+220h+var_140], 32h ; '2'
0x180137c89  mov     [rbp+220h+var_13C], edi
0x180137c8f  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137c96  mov     [rbp+220h+var_138], rax
0x180137c9d  lea     rdx, [rbp+220h+var_140]
0x180137ca4  lea     rcx, [rsp+320h+var_2D0]
0x180137ca9  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180137cae  mov     [rbp+220h+var_110], rax
0x180137cb5  mov     [rsp+320h+var_2F0], 33h ; '3'
0x180137cbd  mov     [rsp+320h+var_2EC], esi
0x180137cc1  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180137cc8  mov     [rsp+320h+var_2E8], rax
0x180137ccd  lea     rdx, [rsp+320h+var_2F0]
0x180137cd2  lea     rcx, [rsp+320h+var_2D0]
0x180137cd7  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180137cdc  mov     [rsp+320h+var_2E0], 2Ah ; '*'
0x180137ce4  mov     [rsp+320h+var_2DC], ebx
0x180137ce8  lea     rax, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\lockbox\\co"...
  ... truncated ...
```
