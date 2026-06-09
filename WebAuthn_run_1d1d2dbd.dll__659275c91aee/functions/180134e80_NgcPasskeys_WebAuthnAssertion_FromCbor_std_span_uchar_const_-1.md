# NgcPasskeys::WebAuthnAssertion::FromCbor(std::span<uchar const,-1>)

- ea: `0x180134e80`
- end: `0x1801354e4`
- name: `?FromCbor@WebAuthnAssertion@NgcPasskeys@@SA?AU12@V?$span@$$CBE$0?0@std@@@Z`
- size: `1636`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18007d404`

## callees

- `0x18001d5e4`
- `0x18001d5fc`
- `0x18001df88`
- `0x180023bc8`
- `0x18002a07c`
- `0x1800350b4`
- `0x180036504`
- `0x180037f6c`
- `0x180039980`
- `0x180080720`
- `0x18008e458`
- `0x18008f288`
- `0x18008f3e8`
- `0x18008f67c`
- `0x180090c44`
- `0x180090dc0`
- `0x180091034`
- `0x1800910c0`
- `0x1800912f4`
- `0x1800c1e48`
- `0x1800c1e84`
- `0x1800c3718`
- `0x180134e80`
- `0x18013c090`

## string_xrefs

- `0x180134f1b`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134fbf`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134fe7`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135071`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135090`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801350b2`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801350e7`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135109`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135152`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135174`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801351bd`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801351dc`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135211`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135233`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013527c`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801352a4`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801352f9`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135324`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135362`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180135389`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801353bb`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801353e6`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013540d`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall NgcPasskeys::WebAuthnAssertion::FromCbor(char *a1, __int128 *a2)
{
  char *v3; // rdi
  int v4; // esi
  int v5; // r14d
  int v6; // ebx
  int v7; // edi
  int v8; // r15d
  int v9; // r12d
  int v10; // r13d
  __int128 *v11; // rdx
  __int64 Int; // rax
  __int64 TextWString; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 ByteString; // rax
  __int64 v18; // rax
  __int128 v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh]
  const char *v23; // [rsp+48h] [rbp-B8h]
  _BYTE v24[64]; // [rsp+50h] [rbp-B0h] BYREF
  char *Uint; // [rsp+90h] [rbp-70h]
  char *v26; // [rsp+A8h] [rbp-58h]
  _DWORD v27[2]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v28; // [rsp+B8h] [rbp-48h]
  _DWORD v29[2]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v30; // [rsp+C8h] [rbp-38h]
  _DWORD v31[2]; // [rsp+D0h] [rbp-30h] BYREF
  const char *v32; // [rsp+D8h] [rbp-28h]
  _DWORD v33[2]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v34; // [rsp+E8h] [rbp-18h]
  _DWORD v35[2]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v36; // [rsp+F8h] [rbp-8h]
  _DWORD v37[2]; // [rsp+100h] [rbp+0h] BYREF
  const char *v38; // [rsp+108h] [rbp+8h]
  _DWORD v39[2]; // [rsp+110h] [rbp+10h] BYREF
  const char *v40; // [rsp+118h] [rbp+18h]
  _DWORD v41[2]; // [rsp+120h] [rbp+20h] BYREF
  const char *v42; // [rsp+128h] [rbp+28h]
  _DWORD v43[2]; // [rsp+130h] [rbp+30h] BYREF
  const char *v44; // [rsp+138h] [rbp+38h]
  _DWORD v45[2]; // [rsp+140h] [rbp+40h] BYREF
  const char *v46; // [rsp+148h] [rbp+48h]
  _DWORD v47[2]; // [rsp+150h] [rbp+50h] BYREF
  const char *v48; // [rsp+158h] [rbp+58h]
  _DWORD v49[2]; // [rsp+160h] [rbp+60h] BYREF
  const char *v50; // [rsp+168h] [rbp+68h]
  _DWORD v51[2]; // [rsp+170h] [rbp+70h] BYREF
  const char *v52; // [rsp+178h] [rbp+78h]
  _DWORD v53[2]; // [rsp+180h] [rbp+80h] BYREF
  const char *v54; // [rsp+188h] [rbp+88h]
  _DWORD v55[2]; // [rsp+190h] [rbp+90h] BYREF
  const char *v56; // [rsp+198h] [rbp+98h]
  _DWORD v57[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  const char *v58; // [rsp+1A8h] [rbp+A8h]
  _DWORD v59[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  const char *v60; // [rsp+1B8h] [rbp+B8h]
  _DWORD v61[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  const char *v62; // [rsp+1C8h] [rbp+C8h]
  _BYTE v63[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v64; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v65[24]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v66[24]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v67; // [rsp+230h] [rbp+130h]
  _BYTE v68[24]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v69[32]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v70; // [rsp+270h] [rbp+170h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v3 = a1;
  v26 = a1;
  Uint = a1;
  v64 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v65);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v66);
  v67 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v68);
  std::wstring::wstring(v69);
  v70 = 0;
  v21 = 671;
  v22 = DWORD1(v20);
  v23 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
  v20 = *a2;
  SimpleCbor::Decoder::Decoder(v24, &v20, &v21);
  v21 = 673;
  v22 = DWORD1(v20);
  v23 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
  SimpleCbor::Decoder::EnterMap(v24, &v21);
  v21 = 674;
  v22 = DWORD1(v20);
  v23 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v24, &v21) )
  {
    v4 = DWORD1(v20);
    v5 = DWORD1(v20);
    v6 = DWORD1(v20);
    v7 = DWORD1(v20);
    v8 = DWORD1(v20);
    v9 = DWORD1(v20);
    v10 = DWORD1(v20);
    do
    {
      v27[0] = 676;
      v27[1] = v4;
      v28 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      Uint = (char *)SimpleCbor::Decoder::GetUint(v24, v27);
      v29[0] = 677;
      v29[1] = v5;
      v30 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      SimpleCbor::Decoder::NextItem(v24, v29);
      if ( Uint == (char *)1 )
      {
        v61[0] = 681;
        v61[1] = v6;
        v62 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        *(_QWORD *)&v64 = SimpleCbor::Decoder::GetUint(v24, v61);
        LODWORD(v20) = 682;
        DWORD1(v20) = v7;
        *((_QWORD *)&v20 + 1) = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = &v20;
      }
      else if ( Uint == (char *)2 )
      {
        v57[0] = 685;
        v57[1] = v8;
        v58 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v18 = SimpleCbor::Decoder::GetUint(v24, v57);
        DWORD2(v64) = wil::safe_cast<unsigned long,unsigned __int64,0>(v18);
        v59[0] = 686;
        v59[1] = v9;
        v60 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v59;
      }
      else if ( Uint == (char *)3 )
      {
        v53[0] = 689;
        v53[1] = DWORD1(v20);
        v54 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        ByteString = SimpleCbor::Decoder::GetByteString(v24, v63, v53);
        std::vector<unsigned char>::operator=(v65, ByteString);
        std::vector<unsigned char>::_Tidy(v63);
        v55[0] = 690;
        v55[1] = DWORD1(v20);
        v56 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v55;
      }
      else if ( Uint == (char *)4 )
      {
        v49[0] = 693;
        v49[1] = DWORD1(v20);
        v50 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v16 = SimpleCbor::Decoder::GetByteString(v24, v63, v49);
        std::vector<unsigned char>::operator=(v66, v16);
        std::vector<unsigned char>::_Tidy(v63);
        v51[0] = 694;
        v51[1] = DWORD1(v20);
        v52 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v51;
      }
      else if ( Uint == (char *)5 )
      {
        v45[0] = 697;
        v45[1] = v10;
        v46 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v15 = SimpleCbor::Decoder::GetUint(v24, v45);
        LODWORD(v67) = wil::safe_cast<unsigned long,unsigned __int64,0>(v15);
        v47[0] = 698;
        v47[1] = DWORD1(v20);
        v48 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v47;
      }
      else if ( Uint == (char *)6 )
      {
        v41[0] = 701;
        v41[1] = DWORD1(v20);
        v42 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v14 = SimpleCbor::Decoder::GetByteString(v24, v63, v41);
        std::vector<unsigned char>::operator=(v68, v14);
        std::vector<unsigned char>::_Tidy(v63);
        v43[0] = 702;
        v43[1] = DWORD1(v20);
        v44 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v43;
      }
      else if ( Uint == (char *)7 )
      {
        v37[0] = 705;
        v37[1] = DWORD1(v20);
        v38 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        TextWString = SimpleCbor::Decoder::GetTextWString(v24, v63, v37);
        std::wstring::operator=(v69, TextWString);
        std::wstring::_Tidy_deallocate(v63);
        v39[0] = 706;
        v39[1] = DWORD1(v20);
        v40 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v39;
      }
      else if ( Uint == (char *)8 )
      {
        v33[0] = 709;
        v33[1] = DWORD1(v20);
        v34 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        Int = SimpleCbor::Decoder::GetInt(v24, v33);
        LODWORD(v70) = wil::safe_cast<long,__int64,0>(Int);
        v35[0] = 710;
        v35[1] = DWORD1(v20);
        v36 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v35;
      }
      else
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x2CA,
          (unsigned int)"onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Unknown item in WebAuthnAssertion: %llu",
          Uint);
        v31[0] = 715;
        v31[1] = DWORD1(v20);
        v32 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = (__int128 *)v31;
      }
      SimpleCbor::Decoder::NextItem(v24, v11);
      v21 = 674;
      v22 = DWORD1(v20);
      v23 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
    }
    while ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v24, &v21) );
    v3 = v26;
  }
  LODWORD(v20) = 718;
  *((_QWORD *)&v20 + 1) = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
  SimpleCbor::Decoder::LeaveContainer(v24, &v20);
  *(_QWORD *)v3 = v64;
  *((_DWORD *)v3 + 2) = DWORD2(v64);
  std::vector<NgcPasskeys::WebAuthnAccountCredential>::vector<NgcPasskeys::WebAuthnAccountCredential>(v3 + 16, v65);
  std::vector<NgcPasskeys::WebAuthnAccountCredential>::vector<NgcPasskeys::WebAuthnAccountCredential>(v3 + 40, v66);
  *((_DWORD *)v3 + 16) = v67;
  std::vector<NgcPasskeys::WebAuthnAccountCredential>::vector<NgcPasskeys::WebAuthnAccountCredential>(v3 + 72, v68);
  std::wstring::wstring(v3 + 96, v69);
  *((_DWORD *)v3 + 32) = v70;
  SimpleCbor::Decoder::~Decoder((SimpleCbor::Decoder *)v24);
  NgcPasskeys::WebAuthnAssertion::~WebAuthnAssertion((NgcPasskeys::WebAuthnAssertion *)&v64);
  return v3;
}

```

## disassembly

```asm
0x180134e80  mov     [rsp-8+arg_10], rbx
0x180134e85  push    rbp
0x180134e86  push    rsi
0x180134e87  push    rdi
0x180134e88  push    r12
0x180134e8a  push    r13
0x180134e8c  push    r14
0x180134e8e  push    r15
0x180134e90  lea     rbp, [rsp-190h]
0x180134e98  sub     rsp, 290h
0x180134e9f  mov     rax, cs:__security_cookie
0x180134ea6  xor     rax, rsp
0x180134ea9  mov     [rbp+1C0h+var_40], rax
0x180134eb0  mov     rbx, rdx
0x180134eb3  mov     rdi, rcx
0x180134eb6  mov     [rbp+1C0h+var_218], rcx
0x180134eba  mov     [rbp+1C0h+var_230], rcx
0x180134ebe  xorps   xmm0, xmm0
0x180134ec1  movups  [rbp+1C0h+var_D0], xmm0
0x180134ec8  lea     rcx, [rbp+1C0h+var_C0]
0x180134ecf  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180134ed4  lea     rcx, [rbp+1C0h+var_A8]
0x180134edb  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180134ee0  xor     eax, eax
0x180134ee2  mov     [rbp+1C0h+var_90], rax
0x180134ee9  lea     rcx, [rbp+1C0h+var_88]
0x180134ef0  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180134ef5  lea     rcx, [rbp+1C0h+var_70]
0x180134efc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180134f01  nop
0x180134f02  xor     eax, eax
0x180134f04  mov     [rbp+1C0h+var_50], rax
0x180134f0b  mov     [rsp+2C0h+var_280], 29Fh
0x180134f13  mov     eax, [rsp+2C0h+var_28C]
0x180134f17  mov     [rsp+2C0h+var_27C], eax
0x180134f1b  lea     rsi, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134f22  mov     [rsp+2C0h+var_278], rsi
0x180134f27  movaps  xmm0, xmmword ptr [rbx]
0x180134f2a  movdqa  xmmword ptr [rsp+30h], xmm0
0x180134f30  lea     r8, [rsp+2C0h+var_280]
0x180134f35  lea     rdx, [rsp+2C0h+var_290]
0x180134f3a  lea     rcx, [rsp+2C0h+var_270]
0x180134f3f  call    ??0Decoder@SimpleCbor@@QEAA@V?$span@$$CBE$0?0@std@@Uslim_source_location@impl@1@@Z; SimpleCbor::Decoder::Decoder(std::span<uchar const,-1>,SimpleCbor::impl::slim_source_location)
0x180134f44  nop
0x180134f45  mov     [rsp+2C0h+var_280], 2A1h
0x180134f4d  mov     eax, [rsp+2C0h+var_28C]
0x180134f51  mov     [rsp+2C0h+var_27C], eax
0x180134f55  mov     [rsp+2C0h+var_278], rsi
0x180134f5a  lea     rdx, [rsp+2C0h+var_280]
0x180134f5f  lea     rcx, [rsp+2C0h+var_270]
0x180134f64  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x180134f69  mov     [rsp+2C0h+var_280], 2A2h
0x180134f71  mov     eax, [rsp+2C0h+var_28C]
0x180134f75  mov     [rsp+2C0h+var_27C], eax
0x180134f79  mov     [rsp+2C0h+var_278], rsi
0x180134f7e  lea     rdx, [rsp+2C0h+var_280]
0x180134f83  lea     rcx, [rsp+2C0h+var_270]
0x180134f88  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x180134f8d  test    al, al
0x180134f8f  jnz     loc_180135414
0x180134f95  mov     esi, [rsp+2C0h+var_28C]
0x180134f99  mov     r14d, [rsp+2C0h+var_28C]
0x180134f9e  mov     ebx, [rsp+2C0h+var_28C]
0x180134fa2  mov     edi, [rsp+2C0h+var_28C]
0x180134fa6  mov     r15d, [rsp+2C0h+var_28C]
0x180134fab  mov     r12d, [rsp+2C0h+var_28C]
0x180134fb0  mov     r13d, [rsp+2C0h+var_28C]
0x180134fb5  mov     [rbp+1C0h+var_210], 2A4h
0x180134fbc  mov     [rbp+1C0h+var_20C], esi
0x180134fbf  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134fc6  mov     [rbp+1C0h+var_208], rax
0x180134fca  lea     rdx, [rbp+1C0h+var_210]
0x180134fce  lea     rcx, [rsp+2C0h+var_270]
0x180134fd3  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180134fd8  mov     [rbp+1C0h+var_230], rax
0x180134fdc  mov     [rbp+1C0h+var_200], 2A5h
0x180134fe3  mov     [rbp+1C0h+var_1FC], r14d
0x180134fe7  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134fee  mov     [rbp+1C0h+var_1F8], rax
0x180134ff2  lea     rdx, [rbp+1C0h+var_200]
0x180134ff6  lea     rcx, [rsp+2C0h+var_270]
0x180134ffb  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180135000  mov     rax, [rbp+1C0h+var_230]
0x180135004  mov     rcx, rax
0x180135007  sub     rcx, 1
0x18013500b  jz      loc_180135379
0x180135011  sub     rcx, 1
0x180135015  jz      loc_180135313
0x18013501b  sub     rcx, 1
0x18013501f  jz      loc_180135290
0x180135025  sub     rcx, 1
0x180135029  jz      loc_180135225
0x18013502f  sub     rcx, 1
0x180135033  jz      loc_1801351D1
0x180135039  sub     rcx, 1
0x18013503d  jz      loc_180135166
0x180135043  sub     rcx, 1
0x180135047  jz      loc_1801350FB
0x18013504d  cmp     rcx, 1
0x180135051  jz      short loc_1801350A4
0x180135053  mov     rcx, [rbp+1C8h]; this
0x18013505a  mov     [rsp+2C0h+var_298], rax; char *
0x18013505f  lea     rax, aUnknownItemInW_1; "Unknown item in WebAuthnAssertion: %llu"
0x180135066  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x18013506b  mov     r9d, 8000FFFFh; char *
0x180135071  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135078  mov     edx, 2CAh; void *
0x18013507d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180135082  mov     [rbp+1C0h+var_1F0], 2CBh
0x180135089  mov     eax, [rsp+2C0h+var_28C]
0x18013508d  mov     [rbp+1C0h+var_1EC], eax
0x180135090  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135097  mov     [rbp+1C0h+var_1E8], rax
0x18013509b  lea     rdx, [rbp+1C0h+var_1F0]
0x18013509f  jmp     loc_1801353CC
0x1801350a4  mov     [rbp+1C0h+var_1E0], 2C5h
0x1801350ab  mov     eax, [rsp+2C0h+var_28C]
0x1801350af  mov     [rbp+1C0h+var_1DC], eax
0x1801350b2  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801350b9  mov     [rbp+1C0h+var_1D8], rax
0x1801350bd  lea     rdx, [rbp+1C0h+var_1E0]
0x1801350c1  lea     rcx, [rsp+2C0h+var_270]
0x1801350c6  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x1801350cb  mov     rcx, rax
0x1801350ce  call    ??$safe_cast@J_J$0A@@wil@@YAJ_J@Z; wil::safe_cast<long,__int64,0>(__int64)
0x1801350d3  mov     dword ptr [rbp+1C0h+var_50], eax
0x1801350d9  mov     [rbp+1C0h+var_1D0], 2C6h
0x1801350e0  mov     eax, [rsp+2C0h+var_28C]
0x1801350e4  mov     [rbp+1C0h+var_1CC], eax
0x1801350e7  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801350ee  mov     [rbp+1C0h+var_1C8], rax
0x1801350f2  lea     rdx, [rbp+1C0h+var_1D0]
0x1801350f6  jmp     loc_1801353CC
0x1801350fb  mov     [rbp+1C0h+var_1C0], 2C1h
0x180135102  mov     eax, [rsp+2C0h+var_28C]
0x180135106  mov     [rbp+1C0h+var_1BC], eax
0x180135109  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135110  mov     [rbp+1C0h+var_1B8], rax
0x180135114  lea     r8, [rbp+1C0h+var_1C0]
0x180135118  lea     rdx, [rbp+1C0h+var_F0]
0x18013511f  lea     rcx, [rsp+2C0h+var_270]
0x180135124  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x180135129  mov     rdx, rax
0x18013512c  lea     rcx, [rbp+1C0h+var_70]
0x180135133  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180135138  lea     rcx, [rbp+1C0h+var_F0]
0x18013513f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180135144  mov     [rbp+1C0h+var_1B0], 2C2h
0x18013514b  mov     eax, [rsp+2C0h+var_28C]
0x18013514f  mov     [rbp+1C0h+var_1AC], eax
0x180135152  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135159  mov     [rbp+1C0h+var_1A8], rax
0x18013515d  lea     rdx, [rbp+1C0h+var_1B0]
0x180135161  jmp     loc_1801353CC
0x180135166  mov     [rbp+1C0h+var_1A0], 2BDh
0x18013516d  mov     eax, [rsp+2C0h+var_28C]
0x180135171  mov     [rbp+1C0h+var_19C], eax
0x180135174  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013517b  mov     [rbp+1C0h+var_198], rax
0x18013517f  lea     r8, [rbp+1C0h+var_1A0]
0x180135183  lea     rdx, [rbp+1C0h+var_F0]
0x18013518a  lea     rcx, [rsp+2C0h+var_270]
0x18013518f  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180135194  mov     rdx, rax
0x180135197  lea     rcx, [rbp+1C0h+var_88]
0x18013519e  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1801351a3  lea     rcx, [rbp+1C0h+var_F0]
0x1801351aa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801351af  mov     [rbp+1C0h+var_190], 2BEh
0x1801351b6  mov     eax, [rsp+2C0h+var_28C]
0x1801351ba  mov     [rbp+1C0h+var_18C], eax
0x1801351bd  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801351c4  mov     [rbp+1C0h+var_188], rax
0x1801351c8  lea     rdx, [rbp+1C0h+var_190]
0x1801351cc  jmp     loc_1801353CC
0x1801351d1  mov     [rbp+1C0h+var_180], 2B9h
0x1801351d8  mov     [rbp+1C0h+var_17C], r13d
0x1801351dc  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801351e3  mov     [rbp+1C0h+var_178], rax
0x1801351e7  lea     rdx, [rbp+1C0h+var_180]
0x1801351eb  lea     rcx, [rsp+2C0h+var_270]
0x1801351f0  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x1801351f5  mov     rcx, rax
0x1801351f8  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x1801351fd  mov     dword ptr [rbp+1C0h+var_90], eax
0x180135203  mov     [rbp+1C0h+var_170], 2BAh
0x18013520a  mov     eax, [rsp+2C0h+var_28C]
0x18013520e  mov     [rbp+1C0h+var_16C], eax
0x180135211  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135218  mov     [rbp+1C0h+var_168], rax
0x18013521c  lea     rdx, [rbp+1C0h+var_170]
0x180135220  jmp     loc_1801353CC
0x180135225  mov     [rbp+1C0h+var_160], 2B5h
0x18013522c  mov     eax, [rsp+2C0h+var_28C]
0x180135230  mov     [rbp+1C0h+var_15C], eax
0x180135233  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013523a  mov     [rbp+1C0h+var_158], rax
0x18013523e  lea     r8, [rbp+1C0h+var_160]
0x180135242  lea     rdx, [rbp+1C0h+var_F0]
0x180135249  lea     rcx, [rsp+2C0h+var_270]
0x18013524e  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180135253  mov     rdx, rax
0x180135256  lea     rcx, [rbp+1C0h+var_A8]
0x18013525d  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180135262  lea     rcx, [rbp+1C0h+var_F0]
0x180135269  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18013526e  mov     [rbp+1C0h+var_150], 2B6h
0x180135275  mov     eax, [rsp+2C0h+var_28C]
0x180135279  mov     [rbp+1C0h+var_14C], eax
0x18013527c  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135283  mov     [rbp+1C0h+var_148], rax
0x180135287  lea     rdx, [rbp+1C0h+var_150]
0x18013528b  jmp     loc_1801353CC
0x180135290  mov     [rbp+1C0h+var_140], 2B1h
0x18013529a  mov     eax, [rsp+2C0h+var_28C]
0x18013529e  mov     [rbp+1C0h+var_13C], eax
0x1801352a4  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801352ab  mov     [rbp+1C0h+var_138], rax
0x1801352b2  lea     r8, [rbp+1C0h+var_140]
0x1801352b9  lea     rdx, [rbp+1C0h+var_F0]
0x1801352c0  lea     rcx, [rsp+2C0h+var_270]
0x1801352c5  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x1801352ca  mov     rdx, rax
0x1801352cd  lea     rcx, [rbp+1C0h+var_C0]
0x1801352d4  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1801352d9  lea     rcx, [rbp+1C0h+var_F0]
0x1801352e0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801352e5  mov     [rbp+1C0h+var_130], 2B2h
0x1801352ef  mov     eax, [rsp+2C0h+var_28C]
0x1801352f3  mov     [rbp+1C0h+var_12C], eax
0x1801352f9  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135300  mov     [rbp+1C0h+var_128], rax
0x180135307  lea     rdx, [rbp+1C0h+var_130]
0x18013530e  jmp     loc_1801353CC
0x180135313  mov     [rbp+1C0h+var_120], 2ADh
0x18013531d  mov     [rbp+1C0h+var_11C], r15d
0x180135324  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013532b  mov     [rbp+1C0h+var_118], rax
0x180135332  lea     rdx, [rbp+1C0h+var_120]
0x180135339  lea     rcx, [rsp+2C0h+var_270]
0x18013533e  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180135343  mov     rcx, rax
0x180135346  call    ??$safe_cast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast<ulong,unsigned __int64,0>(unsigned __int64)
0x18013534b  mov     dword ptr [rbp+1C0h+var_D0+8], eax
0x180135351  mov     [rbp+1C0h+var_110], 2AEh
0x18013535b  mov     [rbp+1C0h+var_10C], r12d
0x180135362  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135369  mov     [rbp+1C0h+var_108], rax
0x180135370  lea     rdx, [rbp+1C0h+var_110]
0x180135377  jmp     short loc_1801353CC
0x180135379  mov     [rbp+1C0h+var_100], 2A9h
0x180135383  mov     [rbp+1C0h+var_FC], ebx
0x180135389  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135390  mov     [rbp+1C0h+var_F8], rax
0x180135397  lea     rdx, [rbp+1C0h+var_100]
0x18013539e  lea     rcx, [rsp+2C0h+var_270]
0x1801353a3  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x1801353a8  mov     qword ptr [rbp+1C0h+var_D0], rax
0x1801353af  mov     [rsp+2C0h+var_290], 2AAh
0x1801353b7  mov     [rsp+2C0h+var_28C], edi
0x1801353bb  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801353c2  mov     [rsp+2C0h+var_288], rax
0x1801353c7  lea     rdx, [rsp+2C0h+var_290]
0x1801353cc  lea     rcx, [rsp+2C0h+var_270]
0x1801353d1  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x1801353d6  mov     [rsp+2C0h+var_280], 2A2h
0x1801353de  mov     eax, [rsp+2C0h+var_28C]
0x1801353e2  mov     [rsp+2C0h+var_27C], eax
0x1801353e6  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801353ed  mov     [rsp+2C0h+var_278], rax
0x1801353f2  lea     rdx, [rsp+2C0h+var_280]
0x1801353f7  lea     rcx, [rsp+2C0h+var_270]
0x1801353fc  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x180135401  test    al, al
0x180135403  jz      loc_180134FB5
0x180135409  mov     rdi, [rbp+1C0h+var_218]
0x18013540d  lea     rsi, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180135414  mov     [rsp+2C0h+var_290], 2CEh
0x18013541c  mov     eax, [rsp+2C0h+var_28C]
0x180135420  mov     [rsp+2C0h+var_28C], eax
0x180135424  mov     [rsp+2C0h+var_288], rsi
0x180135429  lea     rdx, [rsp+2C0h+var_290]
0x18013542e  lea     rcx, [rsp+2C0h+var_270]
0x180135433  call    ?LeaveContainer@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::LeaveContainer(SimpleCbor::impl::slim_source_location)
0x180135438  mov     rax, qword ptr [rbp+1C0h+var_D0]
0x18013543f  mov     [rdi], rax
0x180135442  mov     eax, dword ptr [rbp+1C0h+var_D0+8]
0x180135448  mov     [rdi+8], eax
0x18013544b  lea     rcx, [rdi+10h]
0x18013544f  lea     rdx, [rbp+1C0h+var_C0]
0x180135456  call    ??0?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<NgcPasskeys::WebAuthnAccountCredential>::vector<NgcPasskeys::WebAuthnAccountCredential>(std::vector<NgcPasskeys::WebAuthnAccountCredential> &&)
0x18013545b  lea     rcx, [rdi+28h]
0x18013545f  lea     rdx, [rbp+1C0h+var_A8]
0x180135466  call    ??0?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<NgcPasskeys::WebAuthnAccountCredential>::vector<NgcPasskeys::WebAuthnAccountCredential>(std::vector<NgcPasskeys::WebAuthnAccountCredential> &&)
0x18013546b  mov     eax, dword ptr [rbp+1C0h+var_90]
0x180135471  mov     [rdi+40h], eax
0x180135474  lea     rcx, [rdi+48h]
0x180135478  lea     rdx, [rbp+1C0h+var_88]
0x18013547f  call    ??0?$vector@UWebAuthnAccountCredential@NgcPasskeys@@V?$allocator@UWebAuthnAccountCredential@NgcPasskeys@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<NgcPasskeys::WebAuthnAccountCredential>::vector<NgcPasskeys::WebAuthnAccountCredential>(std::vector<NgcPasskeys::WebAuthnAccountCredential> &&)
0x180135484  lea     rcx, [rdi+60h]
  ... truncated ...
```
