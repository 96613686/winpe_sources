# Cose::RsaKey::FromCbor(SimpleCbor::Decoder &)

- ea: `0x180138d1c`
- end: `0x180139444`
- name: `?FromCbor@RsaKey@Cose@@SA?AU12@AEAVDecoder@SimpleCbor@@@Z`
- size: `1832`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180138924`

## callees

- `0x1800350b4`
- `0x1800815ac`
- `0x180090c44`
- `0x180090dc0`
- `0x1800912f4`
- `0x1800c1e48`
- `0x1800c1e84`
- `0x1800c3718`
- `0x180137518`
- `0x180137f40`
- `0x180138d1c`

## string_xrefs

- `0x180138dae`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138e1a`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138e4b`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138e9a`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138ec7`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138ee9`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138f30`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138f4f`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138fa6`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138fc8`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013900f`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180139031`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180139078`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013909a`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801390e1`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180139103`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013914a`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013916c`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801391b3`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801391db`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013922e`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013925c`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801392af`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801392dd`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180139330`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180139353`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013937c`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801393af`: `onecore\ds\security\cbor\lib\common\cose.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Cose::RsaKey::FromCbor(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int v4; // ebx
  int v5; // r15d
  int v6; // r12d
  int v7; // esi
  int v8; // r14d
  int v9; // r13d
  int v10; // edi
  int *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 ByteString; // rax
  int v22; // [rsp+28h] [rbp-E0h] BYREF
  int v23; // [rsp+2Ch] [rbp-DCh]
  const char *v24; // [rsp+30h] [rbp-D8h]
  int v25; // [rsp+38h] [rbp-D0h] BYREF
  int v26; // [rsp+3Ch] [rbp-CCh]
  const char *v27; // [rsp+40h] [rbp-C8h]
  _BYTE v28[24]; // [rsp+48h] [rbp-C0h] BYREF
  _DWORD v29[2]; // [rsp+68h] [rbp-A0h] BYREF
  const char *v30; // [rsp+70h] [rbp-98h]
  _DWORD v31[2]; // [rsp+78h] [rbp-90h] BYREF
  const char *v32; // [rsp+80h] [rbp-88h]
  _DWORD v33[2]; // [rsp+88h] [rbp-80h] BYREF
  const char *v34; // [rsp+90h] [rbp-78h]
  _DWORD v35[2]; // [rsp+98h] [rbp-70h] BYREF
  const char *v36; // [rsp+A0h] [rbp-68h]
  _DWORD v37[2]; // [rsp+A8h] [rbp-60h] BYREF
  const char *v38; // [rsp+B0h] [rbp-58h]
  _DWORD v39[2]; // [rsp+B8h] [rbp-50h] BYREF
  const char *v40; // [rsp+C0h] [rbp-48h]
  _DWORD v41[2]; // [rsp+C8h] [rbp-40h] BYREF
  const char *v42; // [rsp+D0h] [rbp-38h]
  _DWORD v43[2]; // [rsp+D8h] [rbp-30h] BYREF
  const char *v44; // [rsp+E0h] [rbp-28h]
  _DWORD v45[2]; // [rsp+E8h] [rbp-20h] BYREF
  const char *v46; // [rsp+F0h] [rbp-18h]
  _DWORD v47[2]; // [rsp+F8h] [rbp-10h] BYREF
  const char *v48; // [rsp+100h] [rbp-8h]
  _DWORD v49[2]; // [rsp+108h] [rbp+0h] BYREF
  const char *v50; // [rsp+110h] [rbp+8h]
  _DWORD v51[2]; // [rsp+118h] [rbp+10h] BYREF
  const char *v52; // [rsp+120h] [rbp+18h]
  _DWORD v53[2]; // [rsp+128h] [rbp+20h] BYREF
  const char *v54; // [rsp+130h] [rbp+28h]
  _DWORD v55[2]; // [rsp+138h] [rbp+30h] BYREF
  const char *v56; // [rsp+140h] [rbp+38h]
  _DWORD v57[2]; // [rsp+148h] [rbp+40h] BYREF
  const char *v58; // [rsp+150h] [rbp+48h]
  _DWORD v59[2]; // [rsp+158h] [rbp+50h] BYREF
  const char *v60; // [rsp+160h] [rbp+58h]
  _DWORD v61[2]; // [rsp+168h] [rbp+60h] BYREF
  const char *v62; // [rsp+170h] [rbp+68h]
  _DWORD v63[2]; // [rsp+178h] [rbp+70h] BYREF
  const char *v64; // [rsp+180h] [rbp+78h]
  _DWORD v65[2]; // [rsp+188h] [rbp+80h] BYREF
  const char *v66; // [rsp+190h] [rbp+88h]
  _DWORD v67[2]; // [rsp+198h] [rbp+90h] BYREF
  const char *v68; // [rsp+1A0h] [rbp+98h]
  _DWORD v69[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  const char *v70; // [rsp+1B0h] [rbp+A8h]
  _DWORD v71[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  const char *v72; // [rsp+1C0h] [rbp+B8h]
  _DWORD v73[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  const char *v74; // [rsp+1D0h] [rbp+C8h]
  _DWORD v75[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  const char *v76; // [rsp+1E0h] [rbp+D8h]
  __int64 v77; // [rsp+1E8h] [rbp+E0h] BYREF
  _BYTE v78[32]; // [rsp+1F0h] [rbp+E8h] BYREF
  __int64 v79; // [rsp+210h] [rbp+108h]
  char v80; // [rsp+218h] [rbp+110h]
  int v81; // [rsp+219h] [rbp+111h]
  __int16 v82; // [rsp+21Dh] [rbp+115h]
  char v83; // [rsp+21Fh] [rbp+117h]
  _BYTE v84[32]; // [rsp+220h] [rbp+118h] BYREF
  _BYTE v85[32]; // [rsp+240h] [rbp+138h] BYREF
  _BYTE v86[32]; // [rsp+260h] [rbp+158h] BYREF
  _BYTE v87[32]; // [rsp+280h] [rbp+178h] BYREF
  _BYTE v88[32]; // [rsp+2A0h] [rbp+198h] BYREF
  _BYTE v89[32]; // [rsp+2C0h] [rbp+1B8h] BYREF
  _BYTE v90[32]; // [rsp+2E0h] [rbp+1D8h] BYREF
  _BYTE v91[88]; // [rsp+300h] [rbp+1F8h] BYREF
  __int64 Int; // [rsp+378h] [rbp+270h]

  v2 = a2;
  v3 = a1;
  v77 = 3;
  v78[24] = 0;
  v80 = 0;
  v84[24] = 0;
  v85[24] = 0;
  v86[24] = 0;
  v87[24] = 0;
  v88[24] = 0;
  v89[24] = 0;
  v90[24] = 0;
  v91[24] = 0;
  v25 = 284;
  v26 = v23;
  v27 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
  SimpleCbor::Decoder::EnterMap(a2, &v25);
  v25 = 285;
  v4 = v23;
  v26 = v23;
  v27 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v2, &v25) )
  {
    v5 = v23;
    v6 = v23;
    v7 = v23;
    v8 = v23;
    v9 = v23;
    v10 = v23;
    do
    {
      v29[0] = 287;
      v29[1] = v5;
      v30 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
      Int = SimpleCbor::Decoder::GetInt(a2, v29);
      v31[0] = 288;
      v31[1] = v6;
      v32 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
      SimpleCbor::Decoder::NextItem(a2, v31);
      switch ( Int )
      {
        case -8LL:
          v73[0] = 332;
          v73[1] = v23;
          v74 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          ByteString = SimpleCbor::Decoder::GetByteString(a2, v28, v73);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(
            v91,
            ByteString);
          std::vector<unsigned char>::_Tidy(v28);
          v75[0] = 333;
          v75[1] = v23;
          v76 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v75;
          break;
        case -7LL:
          v69[0] = 328;
          v69[1] = v23;
          v70 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v19 = SimpleCbor::Decoder::GetByteString(a2, v28, v69);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v90, v19);
          std::vector<unsigned char>::_Tidy(v28);
          v71[0] = 329;
          v71[1] = v23;
          v72 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v71;
          break;
        case -6LL:
          v65[0] = 324;
          v65[1] = v23;
          v66 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v18 = SimpleCbor::Decoder::GetByteString(a2, v28, v65);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v89, v18);
          std::vector<unsigned char>::_Tidy(v28);
          v67[0] = 325;
          v67[1] = v23;
          v68 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v67;
          break;
        case -5LL:
          v61[0] = 320;
          v61[1] = v23;
          v62 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v17 = SimpleCbor::Decoder::GetByteString(a2, v28, v61);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v88, v17);
          std::vector<unsigned char>::_Tidy(v28);
          v63[0] = 321;
          v63[1] = v23;
          v64 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v63;
          break;
        case -4LL:
          v57[0] = 316;
          v57[1] = v23;
          v58 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v16 = SimpleCbor::Decoder::GetByteString(a2, v28, v57);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v87, v16);
          std::vector<unsigned char>::_Tidy(v28);
          v59[0] = 317;
          v59[1] = v23;
          v60 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v59;
          break;
        case -3LL:
          v53[0] = 312;
          v53[1] = v23;
          v54 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v15 = SimpleCbor::Decoder::GetByteString(a2, v28, v53);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v86, v15);
          std::vector<unsigned char>::_Tidy(v28);
          v55[0] = 313;
          v55[1] = v23;
          v56 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v55;
          break;
        case -2LL:
          v49[0] = 308;
          v49[1] = v23;
          v50 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v14 = SimpleCbor::Decoder::GetByteString(a2, v28, v49);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v85, v14);
          std::vector<unsigned char>::_Tidy(v28);
          v51[0] = 309;
          v51[1] = v23;
          v52 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v51;
          break;
        case -1LL:
          v45[0] = 304;
          v45[1] = v23;
          v46 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v13 = SimpleCbor::Decoder::GetByteString(a2, v28, v45);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v84, v13);
          std::vector<unsigned char>::_Tidy(v28);
          v47[0] = 305;
          v47[1] = v23;
          v48 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v47;
          break;
        case 1LL:
          v33[0] = 292;
          v33[1] = v7;
          v34 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v77 = SimpleCbor::Decoder::GetInt(a2, v33);
          v35[0] = 293;
          v35[1] = v8;
          v36 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v35;
          break;
        case 2LL:
          v37[0] = 296;
          v37[1] = v23;
          v38 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v12 = SimpleCbor::Decoder::GetByteString(a2, v28, v37);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v78, v12);
          std::vector<unsigned char>::_Tidy(v28);
          v39[0] = 297;
          v39[1] = v23;
          v40 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v39;
          break;
        case 3LL:
          v41[0] = 300;
          v41[1] = v9;
          v42 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v79 = SimpleCbor::Decoder::GetInt(a2, v41);
          v80 = 1;
          v81 = *(_DWORD *)((char *)&v24 + 1);
          v82 = *(_WORD *)((char *)&v24 + 5);
          v83 = HIBYTE(v24);
          v43[0] = 301;
          v43[1] = v23;
          v44 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = v43;
          break;
        default:
          v22 = 337;
          v23 = v10;
          v24 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v11 = &v22;
          break;
      }
      SimpleCbor::Decoder::NextItem(a2, v11);
      v25 = 285;
      v26 = v4;
      v27 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
    }
    while ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(a2, &v25) );
    v2 = a2;
    v3 = a1;
  }
  v22 = 340;
  v24 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
  SimpleCbor::Decoder::LeaveContainer(v2, &v22);
  Cose::RsaKey::RsaKey(v3, &v77);
  Cose::RsaKey::~RsaKey((Cose::RsaKey *)&v77);
  return v3;
}

```

## disassembly

```asm
0x180138d1c  mov     rax, rsp
0x180138d1f  mov     [rax+20h], rbx
0x180138d23  mov     [rax+10h], rdx
0x180138d27  mov     [rax+8], rcx
0x180138d2b  push    rbp
0x180138d2c  push    rsi
0x180138d2d  push    rdi
0x180138d2e  push    r12
0x180138d30  push    r13
0x180138d32  push    r14
0x180138d34  push    r15
0x180138d36  lea     rbp, [rax-258h]
0x180138d3d  sub     rsp, 320h
0x180138d44  mov     rdi, rdx
0x180138d47  mov     rsi, rcx
0x180138d4a  xor     r14d, r14d
0x180138d4d  mov     [rbp+250h+var_170], 3
0x180138d58  mov     [rbp+250h+var_150], r14b
0x180138d5f  mov     [rbp+250h+var_140], r14b
0x180138d66  mov     [rbp+250h+var_120], r14b
0x180138d6d  mov     [rbp+250h+var_100], r14b
0x180138d74  mov     [rbp+250h+var_E0], r14b
0x180138d7b  mov     [rbp+250h+var_C0], r14b
0x180138d82  mov     [rbp+250h+var_A0], r14b
0x180138d89  mov     [rbp+250h+var_80], r14b
0x180138d90  mov     [rbp+250h+var_60], r14b
0x180138d97  mov     [rbp+250h+var_40], r14b
0x180138d9e  mov     dword ptr [rsp+350h+var_320], 11Ch
0x180138da6  mov     eax, [rsp+350h+var_32F+3]
0x180138daa  mov     dword ptr [rsp+350h+var_320+4], eax
0x180138dae  lea     r15, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138db5  mov     [rsp+350h+var_318], r15
0x180138dba  lea     rdx, [rsp+350h+var_320]
0x180138dbf  mov     rcx, rdi
0x180138dc2  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x180138dc7  mov     dword ptr [rsp+350h+var_320], 11Dh
0x180138dcf  mov     ebx, [rsp+350h+var_32F+3]
0x180138dd3  mov     dword ptr [rsp+350h+var_320+4], ebx
0x180138dd7  mov     [rsp+350h+var_318], r15
0x180138ddc  lea     rdx, [rsp+350h+var_320]
0x180138de1  mov     rcx, rdi
0x180138de4  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x180138de9  test    al, al
0x180138deb  jnz     loc_1801393B6
0x180138df1  mov     r15d, [rsp+350h+var_32F+3]
0x180138df6  mov     r12d, [rsp+350h+var_32F+3]
0x180138dfb  mov     esi, [rsp+350h+var_32F+3]
0x180138dff  mov     r14d, [rsp+350h+var_32F+3]
0x180138e04  mov     r13d, [rsp+350h+var_32F+3]
0x180138e09  mov     edi, [rsp+350h+var_32F+3]
0x180138e0d  mov     dword ptr [rsp+350h+var_2F0], 11Fh
0x180138e15  mov     dword ptr [rsp+350h+var_2F0+4], r15d
0x180138e1a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138e21  mov     qword ptr [rsp+350h+var_2E8], rax
0x180138e26  lea     rdx, [rsp+350h+var_2F0]
0x180138e2b  mov     rcx, [rbp+250h+arg_8]
0x180138e32  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x180138e37  mov     [rbp+250h+arg_10], rax
0x180138e3e  mov     dword ptr [rsp+350h+var_2E0], 120h
0x180138e46  mov     dword ptr [rsp+350h+var_2E0+4], r12d
0x180138e4b  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138e52  mov     [rsp+350h+var_2D8], rax
0x180138e57  lea     rdx, [rsp+350h+var_2E0]
0x180138e5c  mov     rcx, [rbp+250h+arg_8]
0x180138e63  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180138e68  mov     rax, [rbp+250h+arg_10]
0x180138e6f  add     rax, 8; switch 12 cases
0x180138e73  cmp     rax, 0Bh
0x180138e77  ja      def_180138E8E; jumptable 0000000180138E8E default case, case 0
0x180138e7d  lea     rcx, __ImageBase
0x180138e84  mov     eax, ds:(jpt_180138E8E - 180000000h)[rcx+rax*4]
0x180138e8b  add     rax, rcx
0x180138e8e  jmp     rax; switch jump
0x180138e90  mov     [rbp+250h+var_2D0], 124h; jumptable 0000000180138E8E case 1
0x180138e97  mov     [rbp+250h+var_2CC], esi
0x180138e9a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138ea1  mov     [rbp+250h+var_2C8], rax
0x180138ea5  lea     rdx, [rbp+250h+var_2D0]
0x180138ea9  mov     rcx, [rbp+250h+arg_8]
0x180138eb0  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x180138eb5  mov     [rbp+250h+var_170], rax
0x180138ebc  mov     [rbp+250h+var_2C0], 125h
0x180138ec3  mov     [rbp+250h+var_2BC], r14d
0x180138ec7  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138ece  mov     [rbp+250h+var_2B8], rax
0x180138ed2  lea     rdx, [rbp+250h+var_2C0]
0x180138ed6  jmp     loc_180139364
0x180138edb  mov     [rbp+250h+var_2B0], 128h; jumptable 0000000180138E8E case 2
0x180138ee2  mov     eax, [rsp+350h+var_32F+3]
0x180138ee6  mov     [rbp+250h+var_2AC], eax
0x180138ee9  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138ef0  mov     [rbp+250h+var_2A8], rax
0x180138ef4  lea     r8, [rbp+250h+var_2B0]
0x180138ef8  lea     rdx, [rsp+40h]
0x180138efd  mov     rcx, [rbp+250h+arg_8]
0x180138f04  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180138f09  mov     rdx, rax
0x180138f0c  lea     rcx, [rbp+250h+var_168]
0x180138f13  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180138f18  lea     rcx, [rsp+40h]
0x180138f1d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180138f22  mov     [rbp+250h+var_2A0], 129h
0x180138f29  mov     eax, [rsp+350h+var_32F+3]
0x180138f2d  mov     [rbp+250h+var_29C], eax
0x180138f30  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138f37  mov     [rbp+250h+var_298], rax
0x180138f3b  lea     rdx, [rbp+250h+var_2A0]
0x180138f3f  jmp     loc_180139364
0x180138f44  mov     [rbp+250h+var_290], 12Ch; jumptable 0000000180138E8E case 3
0x180138f4b  mov     [rbp+250h+var_28C], r13d
0x180138f4f  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138f56  mov     [rbp+250h+var_288], rax
0x180138f5a  lea     rdx, [rbp+250h+var_290]
0x180138f5e  mov     rcx, [rbp+250h+arg_8]
0x180138f65  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x180138f6a  mov     [rbp+250h+var_148], rax
0x180138f71  mov     [rbp+250h+var_140], 1
0x180138f78  mov     eax, dword ptr [rsp+350h+var_328+1]
0x180138f7c  mov     [rbp+250h+var_13F], eax
0x180138f82  movzx   eax, word ptr [rsp+350h+var_328+5]
0x180138f87  mov     [rbp+250h+var_13B], ax
0x180138f8e  mov     al, byte ptr [rsp+350h+var_328+7]
0x180138f92  mov     [rbp+250h+var_139], al
0x180138f98  mov     [rbp+250h+var_280], 12Dh
0x180138f9f  mov     eax, [rsp+350h+var_32F+3]
0x180138fa3  mov     [rbp+250h+var_27C], eax
0x180138fa6  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138fad  mov     [rbp+250h+var_278], rax
0x180138fb1  lea     rdx, [rbp+250h+var_280]
0x180138fb5  jmp     loc_180139364
0x180138fba  mov     [rbp+250h+var_270], 130h; jumptable 0000000180138E8E case -1
0x180138fc1  mov     eax, [rsp+350h+var_32F+3]
0x180138fc5  mov     [rbp+250h+var_26C], eax
0x180138fc8  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138fcf  mov     [rbp+250h+var_268], rax
0x180138fd3  lea     r8, [rbp+250h+var_270]
0x180138fd7  lea     rdx, [rsp+40h]
0x180138fdc  mov     rcx, [rbp+250h+arg_8]
0x180138fe3  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180138fe8  mov     rdx, rax
0x180138feb  lea     rcx, [rbp+250h+var_138]
0x180138ff2  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180138ff7  lea     rcx, [rsp+40h]
0x180138ffc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180139001  mov     [rbp+250h+var_260], 131h
0x180139008  mov     eax, [rsp+350h+var_32F+3]
0x18013900c  mov     [rbp+250h+var_25C], eax
0x18013900f  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180139016  mov     [rbp+250h+var_258], rax
0x18013901a  lea     rdx, [rbp+250h+var_260]
0x18013901e  jmp     loc_180139364
0x180139023  mov     [rbp+250h+var_250], 134h; jumptable 0000000180138E8E case -2
0x18013902a  mov     eax, [rsp+350h+var_32F+3]
0x18013902e  mov     [rbp+250h+var_24C], eax
0x180139031  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180139038  mov     [rbp+250h+var_248], rax
0x18013903c  lea     r8, [rbp+250h+var_250]
0x180139040  lea     rdx, [rsp+40h]
0x180139045  mov     rcx, [rbp+250h+arg_8]
0x18013904c  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180139051  mov     rdx, rax
0x180139054  lea     rcx, [rbp+250h+var_118]
0x18013905b  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180139060  lea     rcx, [rsp+40h]
0x180139065  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18013906a  mov     [rbp+250h+var_240], 135h
0x180139071  mov     eax, [rsp+350h+var_32F+3]
0x180139075  mov     [rbp+250h+var_23C], eax
0x180139078  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x18013907f  mov     [rbp+250h+var_238], rax
0x180139083  lea     rdx, [rbp+250h+var_240]
0x180139087  jmp     loc_180139364
0x18013908c  mov     [rbp+250h+var_230], 138h; jumptable 0000000180138E8E case -3
0x180139093  mov     eax, [rsp+350h+var_32F+3]
0x180139097  mov     [rbp+250h+var_22C], eax
0x18013909a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801390a1  mov     [rbp+250h+var_228], rax
0x1801390a5  lea     r8, [rbp+250h+var_230]
0x1801390a9  lea     rdx, [rsp+40h]
0x1801390ae  mov     rcx, [rbp+250h+arg_8]
0x1801390b5  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x1801390ba  mov     rdx, rax
0x1801390bd  lea     rcx, [rbp+250h+var_F8]
0x1801390c4  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x1801390c9  lea     rcx, [rsp+40h]
0x1801390ce  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801390d3  mov     [rbp+250h+var_220], 139h
0x1801390da  mov     eax, [rsp+350h+var_32F+3]
0x1801390de  mov     [rbp+250h+var_21C], eax
0x1801390e1  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801390e8  mov     [rbp+250h+var_218], rax
0x1801390ec  lea     rdx, [rbp+250h+var_220]
0x1801390f0  jmp     loc_180139364
0x1801390f5  mov     [rbp+250h+var_210], 13Ch; jumptable 0000000180138E8E case -4
0x1801390fc  mov     eax, [rsp+350h+var_32F+3]
0x180139100  mov     [rbp+250h+var_20C], eax
0x180139103  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x18013910a  mov     [rbp+250h+var_208], rax
0x18013910e  lea     r8, [rbp+250h+var_210]
0x180139112  lea     rdx, [rsp+40h]
0x180139117  mov     rcx, [rbp+250h+arg_8]
0x18013911e  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180139123  mov     rdx, rax
0x180139126  lea     rcx, [rbp+250h+var_D8]
0x18013912d  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180139132  lea     rcx, [rsp+40h]
0x180139137  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18013913c  mov     [rbp+250h+var_200], 13Dh
0x180139143  mov     eax, [rsp+350h+var_32F+3]
0x180139147  mov     [rbp+250h+var_1FC], eax
0x18013914a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180139151  mov     [rbp+250h+var_1F8], rax
0x180139155  lea     rdx, [rbp+250h+var_200]
0x180139159  jmp     loc_180139364
0x18013915e  mov     [rbp+250h+var_1F0], 140h; jumptable 0000000180138E8E case -5
0x180139165  mov     eax, [rsp+350h+var_32F+3]
0x180139169  mov     [rbp+250h+var_1EC], eax
0x18013916c  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180139173  mov     [rbp+250h+var_1E8], rax
0x180139177  lea     r8, [rbp+250h+var_1F0]
0x18013917b  lea     rdx, [rsp+40h]
0x180139180  mov     rcx, [rbp+250h+arg_8]
0x180139187  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x18013918c  mov     rdx, rax
0x18013918f  lea     rcx, [rbp+250h+var_B8]
0x180139196  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x18013919b  lea     rcx, [rsp+40h]
0x1801391a0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801391a5  mov     [rbp+250h+var_1E0], 141h
0x1801391ac  mov     eax, [rsp+350h+var_32F+3]
0x1801391b0  mov     [rbp+250h+var_1DC], eax
0x1801391b3  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801391ba  mov     [rbp+250h+var_1D8], rax
0x1801391be  lea     rdx, [rbp+250h+var_1E0]
0x1801391c2  jmp     loc_180139364
0x1801391c7  mov     [rbp+250h+var_1D0], 144h; jumptable 0000000180138E8E case -6
0x1801391d1  mov     eax, [rsp+350h+var_32F+3]
0x1801391d5  mov     [rbp+250h+var_1CC], eax
0x1801391db  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801391e2  mov     [rbp+250h+var_1C8], rax
0x1801391e9  lea     r8, [rbp+250h+var_1D0]
0x1801391f0  lea     rdx, [rsp+40h]
0x1801391f5  mov     rcx, [rbp+250h+arg_8]
0x1801391fc  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180139201  mov     rdx, rax
0x180139204  lea     rcx, [rbp+250h+var_98]
0x18013920b  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180139210  lea     rcx, [rsp+40h]
0x180139215  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18013921a  mov     [rbp+250h+var_1C0], 145h
0x180139224  mov     eax, [rsp+350h+var_32F+3]
0x180139228  mov     [rbp+250h+var_1BC], eax
0x18013922e  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180139235  mov     [rbp+250h+var_1B8], rax
0x18013923c  lea     rdx, [rbp+250h+var_1C0]
0x180139243  jmp     loc_180139364
0x180139248  mov     [rbp+250h+var_1B0], 148h; jumptable 0000000180138E8E case -7
0x180139252  mov     eax, [rsp+350h+var_32F+3]
0x180139256  mov     [rbp+250h+var_1AC], eax
0x18013925c  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180139263  mov     [rbp+250h+var_1A8], rax
0x18013926a  lea     r8, [rbp+250h+var_1B0]
0x180139271  lea     rdx, [rsp+40h]
0x180139276  mov     rcx, [rbp+250h+arg_8]
0x18013927d  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180139282  mov     rdx, rax
0x180139285  lea     rcx, [rbp+250h+var_78]
0x18013928c  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180139291  lea     rcx, [rsp+40h]
0x180139296  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18013929b  mov     [rbp+250h+var_1A0], 149h
0x1801392a5  mov     eax, [rsp+350h+var_32F+3]
0x1801392a9  mov     [rbp+250h+var_19C], eax
0x1801392af  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801392b6  mov     [rbp+250h+var_198], rax
0x1801392bd  lea     rdx, [rbp+250h+var_1A0]
0x1801392c4  jmp     loc_180139364
0x1801392c9  mov     [rbp+250h+var_190], 14Ch; jumptable 0000000180138E8E case -8
0x1801392d3  mov     eax, [rsp+350h+var_32F+3]
0x1801392d7  mov     [rbp+250h+var_18C], eax
0x1801392dd  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801392e4  mov     [rbp+250h+var_188], rax
0x1801392eb  lea     r8, [rbp+250h+var_190]
0x1801392f2  lea     rdx, [rsp+40h]
0x1801392f7  mov     rcx, [rbp+250h+arg_8]
0x1801392fe  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180139303  mov     rdx, rax
0x180139306  lea     rcx, [rbp+250h+var_58]
0x18013930d  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180139312  lea     rcx, [rsp+40h]
0x180139317  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18013931c  mov     [rbp+250h+var_180], 14Dh
0x180139326  mov     eax, [rsp+350h+var_32F+3]
0x18013932a  mov     [rbp+250h+var_17C], eax
0x180139330  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180139337  mov     [rbp+250h+var_178], rax
0x18013933e  lea     rdx, [rbp+250h+var_180]
0x180139345  jmp     short loc_180139364
0x180139347  mov     dword ptr [rsp+20h], 151h; jumptable 0000000180138E8E default case, case 0
0x18013934f  mov     [rsp+350h+var_32F+3], edi
  ... truncated ...
```
