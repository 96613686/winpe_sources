# NgcPasskeys::WebAuthnAccountCredential::FromCbor(SimpleCbor::Decoder &)

- ea: `0x1801343fc`
- end: `0x180134b10`
- name: `?FromCbor@WebAuthnAccountCredential@NgcPasskeys@@SA?AU12@AEAVDecoder@SimpleCbor@@@Z`
- size: `1812`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180134b18`

## callees

- `0x18001d5e4`
- `0x18001d5fc`
- `0x18001df88`
- `0x180023bc8`
- `0x1800350b4`
- `0x18003649c`
- `0x180037f6c`
- `0x18008e458`
- `0x180090c44`
- `0x180091034`
- `0x1800910c0`
- `0x1800912f4`
- `0x1800c1e48`
- `0x1800c1e84`
- `0x1800c3688`
- `0x1800c3718`
- `0x180134308`
- `0x1801343fc`
- `0x18013c090`

## string_xrefs

- `0x1801344c4`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013452e`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134557`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801345c4`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013460d`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013462f`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134678`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013469a`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801346e3`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134705`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013474e`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013476c`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134796`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801347b8`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134801`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013485a`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134879`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134898`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801348c8`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801348f6`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x18013494b`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134979`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801349ce`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x1801349f9`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134a4a`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134a71`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`
- `0x180134a9e`: `onecore\ds\security\ngc\lockbox\common\lib\passkeyproperties.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall NgcPasskeys::WebAuthnAccountCredential::FromCbor(char *a1, __int64 a2)
{
  __int64 v2; // rdi
  char *v3; // rsi
  int v4; // ebx
  int v5; // r12d
  int v6; // r13d
  int v7; // edi
  int v8; // esi
  int v9; // r14d
  int v10; // r15d
  __int64 v11; // rax
  int *v12; // rdx
  __int64 v13; // rax
  __int64 TextWString; // rax
  __int64 v15; // rax
  __int64 ByteString; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh]
  const char *v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh]
  const char *v27; // [rsp+58h] [rbp-A8h]
  char *Uint; // [rsp+60h] [rbp-A0h]
  char *v29; // [rsp+78h] [rbp-88h]
  _DWORD v30[2]; // [rsp+80h] [rbp-80h] BYREF
  const char *v31; // [rsp+88h] [rbp-78h]
  _DWORD v32[2]; // [rsp+90h] [rbp-70h] BYREF
  const char *v33; // [rsp+98h] [rbp-68h]
  _DWORD v34[2]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v35; // [rsp+A8h] [rbp-58h]
  _DWORD v36[2]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v37; // [rsp+B8h] [rbp-48h]
  _DWORD v38[2]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v39; // [rsp+C8h] [rbp-38h]
  _DWORD v40[2]; // [rsp+D0h] [rbp-30h] BYREF
  const char *v41; // [rsp+D8h] [rbp-28h]
  _DWORD v42[2]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v43; // [rsp+E8h] [rbp-18h]
  _DWORD v44[2]; // [rsp+F0h] [rbp-10h] BYREF
  const char *v45; // [rsp+F8h] [rbp-8h]
  _DWORD v46[2]; // [rsp+100h] [rbp+0h] BYREF
  const char *v47; // [rsp+108h] [rbp+8h]
  _DWORD v48[2]; // [rsp+110h] [rbp+10h] BYREF
  const char *v49; // [rsp+118h] [rbp+18h]
  _DWORD v50[2]; // [rsp+120h] [rbp+20h] BYREF
  const char *v51; // [rsp+128h] [rbp+28h]
  _DWORD v52[2]; // [rsp+130h] [rbp+30h] BYREF
  const char *v53; // [rsp+138h] [rbp+38h]
  _DWORD v54[2]; // [rsp+140h] [rbp+40h] BYREF
  const char *v55; // [rsp+148h] [rbp+48h]
  _DWORD v56[2]; // [rsp+150h] [rbp+50h] BYREF
  const char *v57; // [rsp+158h] [rbp+58h]
  _DWORD v58[2]; // [rsp+160h] [rbp+60h] BYREF
  const char *v59; // [rsp+168h] [rbp+68h]
  _DWORD v60[2]; // [rsp+170h] [rbp+70h] BYREF
  const char *v61; // [rsp+178h] [rbp+78h]
  _DWORD v62[2]; // [rsp+180h] [rbp+80h] BYREF
  const char *v63; // [rsp+188h] [rbp+88h]
  _DWORD v64[2]; // [rsp+190h] [rbp+90h] BYREF
  const char *v65; // [rsp+198h] [rbp+98h]
  _DWORD v66[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  const char *v67; // [rsp+1A8h] [rbp+A8h]
  _DWORD v68[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  const char *v69; // [rsp+1B8h] [rbp+B8h]
  _DWORD v70[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  const char *v71; // [rsp+1C8h] [rbp+C8h]
  _DWORD v72[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  const char *v73; // [rsp+1D8h] [rbp+D8h]
  _BYTE v74[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v75; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v76[24]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v77[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v78[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v79[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v80[24]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v81[32]; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v82[32]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v83[32]; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v84; // [rsp+2F8h] [rbp+1F8h]
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v2 = a2;
  v3 = a1;
  v29 = a1;
  Uint = a1;
  v75 = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v76);
  std::wstring::wstring(v77);
  std::wstring::wstring(v78);
  std::wstring::wstring(v79);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v80);
  std::wstring::wstring(v81);
  std::wstring::wstring(v82);
  std::wstring::wstring(v83);
  v84 = 0;
  v25 = 436;
  v26 = v23;
  v27 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
  SimpleCbor::Decoder::EnterMap(v2, &v25);
  v25 = 437;
  v4 = v23;
  v26 = v23;
  v27 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v2, &v25) )
  {
    v5 = v23;
    v6 = v23;
    v7 = v23;
    v8 = v23;
    v9 = v23;
    v10 = v23;
    while ( 1 )
    {
      v30[0] = 439;
      v30[1] = v5;
      v31 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      Uint = (char *)SimpleCbor::Decoder::GetUint(a2, v30);
      v32[0] = 440;
      v32[1] = v6;
      v33 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      SimpleCbor::Decoder::NextItem(a2, v32);
      if ( (unsigned __int64)Uint > 6 )
        break;
      if ( Uint == (char *)6 )
      {
        v54[0] = 464;
        v54[1] = v23;
        v55 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        ByteString = SimpleCbor::Decoder::GetByteString(a2, v74, v54);
        std::vector<unsigned char>::operator=(v80, ByteString);
        std::vector<unsigned char>::_Tidy(v74);
        v56[0] = 465;
        v56[1] = v23;
        v57 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v12 = v56;
      }
      else if ( Uint == (char *)1 )
      {
        v50[0] = 444;
        v50[1] = v7;
        v51 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v75 = SimpleCbor::Decoder::GetUint(a2, v50);
        v52[0] = 445;
        v52[1] = v8;
        v53 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v12 = v52;
      }
      else if ( Uint == (char *)2 )
      {
        v46[0] = 448;
        v46[1] = v23;
        v47 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v15 = SimpleCbor::Decoder::GetByteString(a2, v74, v46);
        std::vector<unsigned char>::operator=(v76, v15);
        std::vector<unsigned char>::_Tidy(v74);
        v48[0] = 449;
        v48[1] = v23;
        v49 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v12 = v48;
      }
      else if ( Uint == (char *)3 )
      {
        v42[0] = 452;
        v42[1] = v23;
        v43 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        TextWString = SimpleCbor::Decoder::GetTextWString(a2, v74, v42);
        std::wstring::operator=(v77, TextWString);
        std::wstring::_Tidy_deallocate(v74);
        v44[0] = 453;
        v44[1] = v23;
        v45 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v12 = v44;
      }
      else if ( Uint == (char *)4 )
      {
        v38[0] = 456;
        v38[1] = v23;
        v39 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v13 = SimpleCbor::Decoder::GetTextWString(a2, v74, v38);
        std::wstring::operator=(v78, v13);
        std::wstring::_Tidy_deallocate(v74);
        v40[0] = 457;
        v40[1] = v23;
        v41 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v12 = v40;
      }
      else
      {
        if ( Uint != (char *)5 )
          goto LABEL_20;
        v34[0] = 460;
        v34[1] = v23;
        v35 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v11 = SimpleCbor::Decoder::GetTextWString(a2, v74, v34);
        std::wstring::operator=(v79, v11);
        std::wstring::_Tidy_deallocate(v74);
        v36[0] = 461;
        v36[1] = v23;
        v37 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
        v12 = v36;
      }
LABEL_25:
      SimpleCbor::Decoder::NextItem(a2, v12);
      v25 = 437;
      v26 = v4;
      v27 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      if ( (unsigned __int8)SimpleCbor::Decoder::EndOfContainer(a2, &v25) )
      {
        v2 = a2;
        v3 = v29;
        goto LABEL_27;
      }
    }
    if ( Uint == (char *)7 )
    {
      v72[0] = 468;
      v72[1] = v23;
      v73 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      v19 = SimpleCbor::Decoder::GetTextWString(a2, v74, v72);
      std::wstring::operator=(v81, v19);
      std::wstring::_Tidy_deallocate(v74);
      v22 = 469;
      v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      v12 = &v22;
      goto LABEL_25;
    }
    if ( Uint == (char *)8 )
    {
      v68[0] = 472;
      v68[1] = v23;
      v69 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      v18 = SimpleCbor::Decoder::GetTextWString(a2, v74, v68);
      std::wstring::operator=(v82, v18);
      std::wstring::_Tidy_deallocate(v74);
      v70[0] = 473;
      v70[1] = v23;
      v71 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      v12 = v70;
      goto LABEL_25;
    }
    if ( Uint == (char *)9 )
    {
      v64[0] = 476;
      v64[1] = v23;
      v65 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      v17 = SimpleCbor::Decoder::GetTextWString(a2, v74, v64);
      std::wstring::operator=(v83, v17);
      std::wstring::_Tidy_deallocate(v74);
      v66[0] = 477;
      v66[1] = v23;
      v67 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      v12 = v66;
      goto LABEL_25;
    }
    if ( Uint == (char *)10 )
    {
      v60[0] = 480;
      v60[1] = v9;
      v61 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      LOBYTE(v84) = SimpleCbor::Decoder::GetBool(a2, v60);
      v62[0] = 481;
      v62[1] = v10;
      v63 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
      v12 = v62;
      goto LABEL_25;
    }
LABEL_20:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Unknown item in WebAuthnAccountCredential: %llu",
      Uint);
    v58[0] = 486;
    v58[1] = v23;
    v59 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
    v12 = v58;
    goto LABEL_25;
  }
LABEL_27:
  v22 = 489;
  v24 = "onecore\\ds\\security\\ngc\\lockbox\\common\\lib\\passkeyproperties.cpp";
  SimpleCbor::Decoder::LeaveContainer(v2, &v22);
  NgcPasskeys::WebAuthnAccountCredential::WebAuthnAccountCredential(v3, &v75);
  NgcPasskeys::WebAuthnAccountCredential::~WebAuthnAccountCredential((NgcPasskeys::WebAuthnAccountCredential *)&v75);
  return v3;
}

```

## disassembly

```asm
0x1801343fc  mov     [rsp-8+arg_10], rbx
0x180134401  push    rbp
0x180134402  push    rsi
0x180134403  push    rdi
0x180134404  push    r12
0x180134406  push    r13
0x180134408  push    r14
0x18013440a  push    r15
0x18013440c  lea     rbp, [rsp-210h]
0x180134414  sub     rsp, 310h
0x18013441b  mov     rax, cs:__security_cookie
0x180134422  xor     rax, rsp
0x180134425  mov     [rbp+240h+var_40], rax
0x18013442c  mov     rdi, rdx
0x18013442f  mov     [rsp+340h+var_310], rdx
0x180134434  mov     rsi, rcx
0x180134437  mov     [rsp+340h+var_2C8], rcx
0x18013443c  mov     [rsp+340h+var_2E0], rcx
0x180134441  xor     eax, eax
0x180134443  mov     [rbp+240h+var_140], rax
0x18013444a  lea     rcx, [rbp+240h+var_138]
0x180134451  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180134456  lea     rcx, [rbp+240h+var_120]
0x18013445d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180134462  lea     rcx, [rbp+240h+var_100]
0x180134469  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013446e  lea     rcx, [rbp+240h+var_E0]
0x180134475  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013447a  lea     rcx, [rbp+240h+var_C0]
0x180134481  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180134486  lea     rcx, [rbp+240h+var_A8]
0x18013448d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180134492  lea     rcx, [rbp+240h+var_88]
0x180134499  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013449e  lea     rcx, [rbp+240h+var_68]
0x1801344a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801344aa  nop
0x1801344ab  xor     eax, eax
0x1801344ad  mov     [rbp+240h+var_48], rax
0x1801344b4  mov     [rsp+340h+var_2F0], 1B4h
0x1801344bc  mov     eax, [rsp+340h+var_2FC]
0x1801344c0  mov     [rsp+340h+var_2EC], eax
0x1801344c4  lea     r14, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801344cb  mov     [rsp+340h+var_2E8], r14
0x1801344d0  lea     rdx, [rsp+340h+var_2F0]
0x1801344d5  mov     rcx, rdi
0x1801344d8  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x1801344dd  mov     [rsp+340h+var_2F0], 1B5h
0x1801344e5  mov     ebx, [rsp+340h+var_2FC]
0x1801344e9  mov     [rsp+340h+var_2EC], ebx
0x1801344ed  mov     [rsp+340h+var_2E8], r14
0x1801344f2  lea     rdx, [rsp+340h+var_2F0]
0x1801344f7  mov     rcx, rdi
0x1801344fa  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x1801344ff  test    al, al
0x180134501  jnz     loc_180134AA5
0x180134507  mov     r12d, [rsp+340h+var_2FC]
0x18013450c  mov     r13d, [rsp+340h+var_2FC]
0x180134511  mov     edi, [rsp+340h+var_2FC]
0x180134515  mov     esi, [rsp+340h+var_2FC]
0x180134519  mov     r14d, [rsp+340h+var_2FC]
0x18013451e  mov     r15d, [rsp+340h+var_2FC]
0x180134523  mov     [rbp+240h+var_2C0], 1B7h
0x18013452a  mov     [rbp+240h+var_2BC], r12d
0x18013452e  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134535  mov     [rbp+240h+var_2B8], rax
0x180134539  lea     rdx, [rbp+240h+var_2C0]
0x18013453d  mov     rcx, [rsp+340h+var_310]
0x180134542  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180134547  mov     [rsp+340h+var_2E0], rax
0x18013454c  mov     [rbp+240h+var_2B0], 1B8h
0x180134553  mov     [rbp+240h+var_2AC], r13d
0x180134557  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013455e  mov     [rbp+240h+var_2A8], rax
0x180134562  lea     rdx, [rbp+240h+var_2B0]
0x180134566  mov     rcx, [rsp+340h+var_310]
0x18013456b  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180134570  mov     rdx, [rsp+340h+var_2E0]
0x180134575  cmp     rdx, 6
0x180134579  ja      loc_180134815
0x18013457f  jz      loc_1801347AA
0x180134585  mov     rcx, rdx
0x180134588  sub     rcx, 1
0x18013458c  jz      loc_180134762
0x180134592  sub     rcx, 1
0x180134596  jz      loc_1801346F7
0x18013459c  sub     rcx, 1
0x1801345a0  jz      loc_18013468C
0x1801345a6  sub     rcx, 1
0x1801345aa  jz      short loc_180134621
0x1801345ac  cmp     rcx, 1
0x1801345b0  jnz     loc_18013483C
0x1801345b6  mov     [rbp+240h+var_2A0], 1CCh
0x1801345bd  mov     eax, [rsp+340h+var_2FC]
0x1801345c1  mov     [rbp+240h+var_29C], eax
0x1801345c4  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801345cb  mov     [rbp+240h+var_298], rax
0x1801345cf  lea     r8, [rbp+240h+var_2A0]
0x1801345d3  lea     rdx, [rbp+240h+var_160]
0x1801345da  mov     rcx, [rsp+340h+var_310]
0x1801345df  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x1801345e4  mov     rdx, rax
0x1801345e7  lea     rcx, [rbp+240h+var_E0]
0x1801345ee  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801345f3  lea     rcx, [rbp+240h+var_160]
0x1801345fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801345ff  mov     [rbp+240h+var_290], 1CDh
0x180134606  mov     eax, [rsp+340h+var_2FC]
0x18013460a  mov     [rbp+240h+var_28C], eax
0x18013460d  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134614  mov     [rbp+240h+var_288], rax
0x180134618  lea     rdx, [rbp+240h+var_290]
0x18013461c  jmp     loc_180134A5B
0x180134621  mov     [rbp+240h+var_280], 1C8h
0x180134628  mov     eax, [rsp+340h+var_2FC]
0x18013462c  mov     [rbp+240h+var_27C], eax
0x18013462f  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134636  mov     [rbp+240h+var_278], rax
0x18013463a  lea     r8, [rbp+240h+var_280]
0x18013463e  lea     rdx, [rbp+240h+var_160]
0x180134645  mov     rcx, [rsp+340h+var_310]
0x18013464a  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x18013464f  mov     rdx, rax
0x180134652  lea     rcx, [rbp+240h+var_100]
0x180134659  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18013465e  lea     rcx, [rbp+240h+var_160]
0x180134665  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013466a  mov     [rbp+240h+var_270], 1C9h
0x180134671  mov     eax, [rsp+340h+var_2FC]
0x180134675  mov     [rbp+240h+var_26C], eax
0x180134678  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013467f  mov     [rbp+240h+var_268], rax
0x180134683  lea     rdx, [rbp+240h+var_270]
0x180134687  jmp     loc_180134A5B
0x18013468c  mov     [rbp+240h+var_260], 1C4h
0x180134693  mov     eax, [rsp+340h+var_2FC]
0x180134697  mov     [rbp+240h+var_25C], eax
0x18013469a  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801346a1  mov     [rbp+240h+var_258], rax
0x1801346a5  lea     r8, [rbp+240h+var_260]
0x1801346a9  lea     rdx, [rbp+240h+var_160]
0x1801346b0  mov     rcx, [rsp+340h+var_310]
0x1801346b5  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x1801346ba  mov     rdx, rax
0x1801346bd  lea     rcx, [rbp+240h+var_120]
0x1801346c4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801346c9  lea     rcx, [rbp+240h+var_160]
0x1801346d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801346d5  mov     [rbp+240h+var_250], 1C5h
0x1801346dc  mov     eax, [rsp+340h+var_2FC]
0x1801346e0  mov     [rbp+240h+var_24C], eax
0x1801346e3  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801346ea  mov     [rbp+240h+var_248], rax
0x1801346ee  lea     rdx, [rbp+240h+var_250]
0x1801346f2  jmp     loc_180134A5B
0x1801346f7  mov     [rbp+240h+var_240], 1C0h
0x1801346fe  mov     eax, [rsp+340h+var_2FC]
0x180134702  mov     [rbp+240h+var_23C], eax
0x180134705  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013470c  mov     [rbp+240h+var_238], rax
0x180134710  lea     r8, [rbp+240h+var_240]
0x180134714  lea     rdx, [rbp+240h+var_160]
0x18013471b  mov     rcx, [rsp+340h+var_310]
0x180134720  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180134725  mov     rdx, rax
0x180134728  lea     rcx, [rbp+240h+var_138]
0x18013472f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180134734  lea     rcx, [rbp+240h+var_160]
0x18013473b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180134740  mov     [rbp+240h+var_230], 1C1h
0x180134747  mov     eax, [rsp+340h+var_2FC]
0x18013474b  mov     [rbp+240h+var_22C], eax
0x18013474e  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134755  mov     [rbp+240h+var_228], rax
0x180134759  lea     rdx, [rbp+240h+var_230]
0x18013475d  jmp     loc_180134A5B
0x180134762  mov     [rbp+240h+var_220], 1BCh
0x180134769  mov     [rbp+240h+var_21C], edi
0x18013476c  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134773  mov     [rbp+240h+var_218], rax
0x180134777  lea     rdx, [rbp+240h+var_220]
0x18013477b  mov     rcx, [rsp+340h+var_310]
0x180134780  call    ?GetUint@Decoder@SimpleCbor@@QEAA_KUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetUint(SimpleCbor::impl::slim_source_location)
0x180134785  mov     [rbp+240h+var_140], rax
0x18013478c  mov     [rbp+240h+var_210], 1BDh
0x180134793  mov     [rbp+240h+var_20C], esi
0x180134796  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013479d  mov     [rbp+240h+var_208], rax
0x1801347a1  lea     rdx, [rbp+240h+var_210]
0x1801347a5  jmp     loc_180134A5B
0x1801347aa  mov     [rbp+240h+var_200], 1D0h
0x1801347b1  mov     eax, [rsp+340h+var_2FC]
0x1801347b5  mov     [rbp+240h+var_1FC], eax
0x1801347b8  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801347bf  mov     [rbp+240h+var_1F8], rax
0x1801347c3  lea     r8, [rbp+240h+var_200]
0x1801347c7  lea     rdx, [rbp+240h+var_160]
0x1801347ce  mov     rcx, [rsp+340h+var_310]
0x1801347d3  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x1801347d8  mov     rdx, rax
0x1801347db  lea     rcx, [rbp+240h+var_C0]
0x1801347e2  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1801347e7  lea     rcx, [rbp+240h+var_160]
0x1801347ee  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801347f3  mov     [rbp+240h+var_1F0], 1D1h
0x1801347fa  mov     eax, [rsp+340h+var_2FC]
0x1801347fe  mov     [rbp+240h+var_1EC], eax
0x180134801  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134808  mov     [rbp+240h+var_1E8], rax
0x18013480c  lea     rdx, [rbp+240h+var_1F0]
0x180134810  jmp     loc_180134A5B
0x180134815  mov     rax, rdx
0x180134818  sub     rax, 7
0x18013481c  jz      loc_1801349E5
0x180134822  sub     rax, 1
0x180134826  jz      loc_180134965
0x18013482c  sub     rax, 1
0x180134830  jz      loc_1801348E2
0x180134836  cmp     rax, 1
0x18013483a  jz      short loc_18013488D
0x18013483c  mov     rcx, [rbp+248h]; this
0x180134843  mov     [rsp+340h+var_318], rdx; char *
0x180134848  lea     rax, aUnknownItemInW_0; "Unknown item in WebAuthnAccountCredenti"...
0x18013484f  mov     qword ptr [rsp+340h+var_320], rax; int
0x180134854  mov     r9d, 8000FFFFh; char *
0x18013485a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134861  mov     edx, 1E5h; void *
0x180134866  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18013486b  mov     [rbp+240h+var_1E0], 1E6h
0x180134872  mov     eax, [rsp+340h+var_2FC]
0x180134876  mov     [rbp+240h+var_1DC], eax
0x180134879  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134880  mov     [rbp+240h+var_1D8], rax
0x180134884  lea     rdx, [rbp+240h+var_1E0]
0x180134888  jmp     loc_180134A5B
0x18013488d  mov     [rbp+240h+var_1D0], 1E0h
0x180134894  mov     [rbp+240h+var_1CC], r14d
0x180134898  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x18013489f  mov     [rbp+240h+var_1C8], rax
0x1801348a3  lea     rdx, [rbp+240h+var_1D0]
0x1801348a7  mov     rcx, [rsp+340h+var_310]
0x1801348ac  call    ?GetBool@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetBool(SimpleCbor::impl::slim_source_location)
0x1801348b1  mov     byte ptr [rbp+240h+var_48], al
0x1801348b7  mov     [rbp+240h+var_1C0], 1E1h
0x1801348c1  mov     [rbp+240h+var_1BC], r15d
0x1801348c8  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801348cf  mov     [rbp+240h+var_1B8], rax
0x1801348d6  lea     rdx, [rbp+240h+var_1C0]
0x1801348dd  jmp     loc_180134A5B
0x1801348e2  mov     [rbp+240h+var_1B0], 1DCh
0x1801348ec  mov     eax, [rsp+340h+var_2FC]
0x1801348f0  mov     [rbp+240h+var_1AC], eax
0x1801348f6  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801348fd  mov     [rbp+240h+var_1A8], rax
0x180134904  lea     r8, [rbp+240h+var_1B0]
0x18013490b  lea     rdx, [rbp+240h+var_160]
0x180134912  mov     rcx, [rsp+340h+var_310]
0x180134917  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x18013491c  mov     rdx, rax
0x18013491f  lea     rcx, [rbp+240h+var_68]
0x180134926  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18013492b  lea     rcx, [rbp+240h+var_160]
0x180134932  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180134937  mov     [rbp+240h+var_1A0], 1DDh
0x180134941  mov     eax, [rsp+340h+var_2FC]
0x180134945  mov     [rbp+240h+var_19C], eax
0x18013494b  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134952  mov     [rbp+240h+var_198], rax
0x180134959  lea     rdx, [rbp+240h+var_1A0]
0x180134960  jmp     loc_180134A5B
0x180134965  mov     [rbp+240h+var_190], 1D8h
0x18013496f  mov     eax, [rsp+340h+var_2FC]
0x180134973  mov     [rbp+240h+var_18C], eax
0x180134979  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134980  mov     [rbp+240h+var_188], rax
0x180134987  lea     r8, [rbp+240h+var_190]
0x18013498e  lea     rdx, [rbp+240h+var_160]
0x180134995  mov     rcx, [rsp+340h+var_310]
0x18013499a  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
0x18013499f  mov     rdx, rax
0x1801349a2  lea     rcx, [rbp+240h+var_88]
0x1801349a9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801349ae  lea     rcx, [rbp+240h+var_160]
0x1801349b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801349ba  mov     [rbp+240h+var_180], 1D9h
0x1801349c4  mov     eax, [rsp+340h+var_2FC]
0x1801349c8  mov     [rbp+240h+var_17C], eax
0x1801349ce  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x1801349d5  mov     [rbp+240h+var_178], rax
0x1801349dc  lea     rdx, [rbp+240h+var_180]
0x1801349e3  jmp     short loc_180134A5B
0x1801349e5  mov     [rbp+240h+var_170], 1D4h
0x1801349ef  mov     eax, [rsp+340h+var_2FC]
0x1801349f3  mov     [rbp+240h+var_16C], eax
0x1801349f9  lea     rax, aOnecoreDsSecur_30; "onecore\\ds\\security\\ngc\\lockbox\\co"...
0x180134a00  mov     [rbp+240h+var_168], rax
0x180134a07  lea     r8, [rbp+240h+var_170]
0x180134a0e  lea     rdx, [rbp+240h+var_160]
0x180134a15  mov     rcx, [rsp+340h+var_310]
0x180134a1a  call    ?GetTextWString@Decoder@SimpleCbor@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetTextWString(SimpleCbor::impl::slim_source_location)
  ... truncated ...
```
