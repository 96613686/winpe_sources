# Cose::EccKey::FromCbor(SimpleCbor::Decoder &)

- ea: `0x18013843c`
- end: `0x18013891b`
- name: `?FromCbor@EccKey@Cose@@SA?AU12@AEAVDecoder@SimpleCbor@@@Z`
- size: `1247`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180138924`

## callees

- `0x1800350b4`
- `0x18008152c`
- `0x180090c44`
- `0x180090dc0`
- `0x1800912f4`
- `0x1800c1e48`
- `0x1800c1e84`
- `0x1800c3718`
- `0x180137518`
- `0x180137e7c`
- `0x18013843c`

## string_xrefs

- `0x1801384af`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013851b`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013854c`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801385b7`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013862b`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013864d`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013868a`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801386a8`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801386cb`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801386ed`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013873d`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013875f`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013879f`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801387c1`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138801`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138820`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x180138862`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x18013888b`: `onecore\ds\security\cbor\lib\common\cose.cpp`
- `0x1801388be`: `onecore\ds\security\cbor\lib\common\cose.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Cose::EccKey::FromCbor(__int64 a1, __int64 a2)
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
  __int64 v11; // rcx
  int *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 ByteString; // rax
  int v18; // [rsp+28h] [rbp-E0h] BYREF
  int v19; // [rsp+2Ch] [rbp-DCh]
  const char *v20; // [rsp+30h] [rbp-D8h]
  int v21; // [rsp+38h] [rbp-D0h] BYREF
  int v22; // [rsp+3Ch] [rbp-CCh]
  const char *v23; // [rsp+40h] [rbp-C8h]
  _BYTE v24[24]; // [rsp+48h] [rbp-C0h] BYREF
  _DWORD v25[2]; // [rsp+68h] [rbp-A0h] BYREF
  const char *v26; // [rsp+70h] [rbp-98h]
  _DWORD v27[2]; // [rsp+78h] [rbp-90h] BYREF
  const char *v28; // [rsp+80h] [rbp-88h]
  _DWORD v29[2]; // [rsp+88h] [rbp-80h] BYREF
  const char *v30; // [rsp+90h] [rbp-78h]
  _DWORD v31[2]; // [rsp+98h] [rbp-70h] BYREF
  const char *v32; // [rsp+A0h] [rbp-68h]
  _DWORD v33[2]; // [rsp+A8h] [rbp-60h] BYREF
  const char *v34; // [rsp+B0h] [rbp-58h]
  _DWORD v35[2]; // [rsp+B8h] [rbp-50h] BYREF
  const char *v36; // [rsp+C0h] [rbp-48h]
  _DWORD v37[2]; // [rsp+C8h] [rbp-40h] BYREF
  const char *v38; // [rsp+D0h] [rbp-38h]
  _DWORD v39[2]; // [rsp+D8h] [rbp-30h] BYREF
  const char *v40; // [rsp+E0h] [rbp-28h]
  _DWORD v41[2]; // [rsp+E8h] [rbp-20h] BYREF
  const char *v42; // [rsp+F0h] [rbp-18h]
  _DWORD v43[2]; // [rsp+F8h] [rbp-10h] BYREF
  const char *v44; // [rsp+100h] [rbp-8h]
  _DWORD v45[2]; // [rsp+108h] [rbp+0h] BYREF
  const char *v46; // [rsp+110h] [rbp+8h]
  _DWORD v47[2]; // [rsp+118h] [rbp+10h] BYREF
  const char *v48; // [rsp+120h] [rbp+18h]
  _DWORD v49[2]; // [rsp+128h] [rbp+20h] BYREF
  const char *v50; // [rsp+130h] [rbp+28h]
  _DWORD v51[2]; // [rsp+138h] [rbp+30h] BYREF
  const char *v52; // [rsp+140h] [rbp+38h]
  _DWORD v53[2]; // [rsp+148h] [rbp+40h] BYREF
  const char *v54; // [rsp+150h] [rbp+48h]
  _DWORD v55[2]; // [rsp+158h] [rbp+50h] BYREF
  const char *v56; // [rsp+160h] [rbp+58h]
  __int64 v57; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v58[32]; // [rsp+170h] [rbp+68h] BYREF
  __int64 v59; // [rsp+190h] [rbp+88h]
  char v60; // [rsp+198h] [rbp+90h]
  int v61; // [rsp+199h] [rbp+91h]
  __int16 v62; // [rsp+19Dh] [rbp+95h]
  char v63; // [rsp+19Fh] [rbp+97h]
  __int64 v64; // [rsp+1A0h] [rbp+98h]
  char v65; // [rsp+1A8h] [rbp+A0h]
  int v66; // [rsp+1A9h] [rbp+A1h]
  __int16 v67; // [rsp+1ADh] [rbp+A5h]
  char v68; // [rsp+1AFh] [rbp+A7h]
  _BYTE v69[32]; // [rsp+1B0h] [rbp+A8h] BYREF
  _BYTE v70[32]; // [rsp+1D0h] [rbp+C8h] BYREF
  _BYTE v71[88]; // [rsp+1F0h] [rbp+E8h] BYREF
  __int64 Int; // [rsp+268h] [rbp+160h]

  v2 = a2;
  v3 = a1;
  v57 = 2;
  v58[24] = 0;
  v60 = 0;
  v65 = 0;
  v69[24] = 0;
  v70[24] = 0;
  v71[24] = 0;
  v21 = 100;
  v22 = v19;
  v23 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
  SimpleCbor::Decoder::EnterMap(a2, &v21);
  v21 = 101;
  v4 = v19;
  v22 = v19;
  v23 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
  if ( !(unsigned __int8)SimpleCbor::Decoder::EndOfContainer(v2, &v21) )
  {
    v5 = v19;
    v6 = v19;
    v7 = v19;
    v8 = v19;
    v9 = v19;
    v10 = v19;
    while ( 1 )
    {
      v25[0] = 103;
      v25[1] = v5;
      v26 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
      Int = SimpleCbor::Decoder::GetInt(a2, v25);
      v27[0] = 104;
      v27[1] = v6;
      v28 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
      SimpleCbor::Decoder::NextItem(a2, v27);
      v11 = a2;
      switch ( Int )
      {
        case -4LL:
          v55[0] = 132;
          v55[1] = v19;
          v56 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          ByteString = SimpleCbor::Decoder::GetByteString(a2, v24, v55);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(
            v71,
            ByteString);
          std::vector<unsigned char>::_Tidy(v24);
          v18 = 133;
          v20 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v12 = &v18;
          goto LABEL_18;
        case -3LL:
          v51[0] = 128;
          v51[1] = v19;
          v52 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v15 = SimpleCbor::Decoder::GetByteString(a2, v24, v51);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v70, v15);
          std::vector<unsigned char>::_Tidy(v24);
          v53[0] = 129;
          v53[1] = v19;
          v54 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v12 = v53;
          goto LABEL_18;
        case -2LL:
          v47[0] = 124;
          v47[1] = v19;
          v48 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v14 = SimpleCbor::Decoder::GetByteString(a2, v24, v47);
          std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v69, v14);
          std::vector<unsigned char>::_Tidy(v24);
          v49[0] = 125;
          v49[1] = v19;
          v50 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v12 = v49;
          goto LABEL_18;
        case -1LL:
          v43[0] = 120;
          v43[1] = v19;
          v44 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v64 = SimpleCbor::Decoder::GetInt(a2, v43);
          v65 = 1;
          v66 = *(_DWORD *)((char *)&v20 + 1);
          v67 = *(_WORD *)((char *)&v20 + 5);
          v68 = HIBYTE(v20);
          v45[0] = 121;
          v45[1] = v19;
          v46 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v12 = v45;
          goto LABEL_18;
        case 1LL:
          v39[0] = 108;
          v39[1] = v7;
          v40 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v57 = SimpleCbor::Decoder::GetInt(a2, v39);
          v41[0] = 109;
          v41[1] = v8;
          v42 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
          v12 = v41;
          goto LABEL_18;
      }
      if ( Int == 2 )
        break;
      if ( Int == 3 )
      {
        v31[0] = 116;
        v31[1] = v9;
        v32 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
        v59 = SimpleCbor::Decoder::GetInt(a2, v31);
        v60 = 1;
        v61 = *(_DWORD *)((char *)&v20 + 1);
        v62 = *(_WORD *)((char *)&v20 + 5);
        v63 = HIBYTE(v20);
        v33[0] = 117;
        v33[1] = v19;
        v34 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
        v12 = v33;
LABEL_18:
        v11 = a2;
        goto LABEL_19;
      }
      v29[0] = 137;
      v29[1] = v10;
      v30 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
      v12 = v29;
LABEL_19:
      SimpleCbor::Decoder::NextItem(v11, v12);
      v21 = 101;
      v22 = v4;
      v23 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
      if ( (unsigned __int8)SimpleCbor::Decoder::EndOfContainer(a2, &v21) )
      {
        v2 = a2;
        v3 = a1;
        goto LABEL_21;
      }
    }
    v35[0] = 112;
    v35[1] = v19;
    v36 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
    v13 = SimpleCbor::Decoder::GetByteString(a2, v24, v35);
    std::_Optional_construct_base<std::vector<unsigned char>>::_Assign<std::vector<unsigned char>>(v58, v13);
    std::vector<unsigned char>::_Tidy(v24);
    v37[0] = 113;
    v37[1] = v19;
    v38 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
    v12 = v37;
    goto LABEL_18;
  }
LABEL_21:
  v18 = 140;
  v20 = "onecore\\ds\\security\\cbor\\lib\\common\\cose.cpp";
  SimpleCbor::Decoder::LeaveContainer(v2, &v18);
  Cose::EccKey::EccKey(v3, &v57);
  Cose::EccKey::~EccKey((Cose::EccKey *)&v57);
  return v3;
}

```

## disassembly

```asm
0x18013843c  mov     rax, rsp
0x18013843f  mov     [rax+20h], rbx
0x180138443  mov     [rax+10h], rdx
0x180138447  mov     [rax+8], rcx
0x18013844b  push    rbp
0x18013844c  push    rsi
0x18013844d  push    rdi
0x18013844e  push    r12
0x180138450  push    r13
0x180138452  push    r14
0x180138454  push    r15
0x180138456  lea     rbp, [rax-148h]
0x18013845d  sub     rsp, 210h
0x180138464  mov     rdi, rdx
0x180138467  mov     rsi, rcx
0x18013846a  xor     r15d, r15d
0x18013846d  mov     [rbp+140h+var_E0], 2
0x180138475  mov     [rbp+140h+var_C0], r15b
0x18013847c  mov     [rbp+140h+var_B0], r15b
0x180138483  mov     [rbp+140h+var_A0], r15b
0x18013848a  mov     [rbp+140h+var_80], r15b
0x180138491  mov     [rbp+140h+var_60], r15b
0x180138498  mov     [rbp+140h+var_40], r15b
0x18013849f  mov     dword ptr [rsp+240h+var_210], 64h ; 'd'
0x1801384a7  mov     eax, [rsp+240h+var_21F+3]
0x1801384ab  mov     dword ptr [rsp+240h+var_210+4], eax
0x1801384af  lea     r14, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801384b6  mov     [rsp+240h+var_208], r14
0x1801384bb  lea     rdx, [rsp+240h+var_210]
0x1801384c0  mov     rcx, rdi
0x1801384c3  call    ?EnterMap@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EnterMap(SimpleCbor::impl::slim_source_location)
0x1801384c8  mov     dword ptr [rsp+240h+var_210], 65h ; 'e'
0x1801384d0  mov     ebx, [rsp+240h+var_21F+3]
0x1801384d4  mov     dword ptr [rsp+240h+var_210+4], ebx
0x1801384d8  mov     [rsp+240h+var_208], r14
0x1801384dd  lea     rdx, [rsp+240h+var_210]
0x1801384e2  mov     rcx, rdi
0x1801384e5  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x1801384ea  test    al, al
0x1801384ec  jnz     loc_1801388C5
0x1801384f2  mov     r15d, [rsp+240h+var_21F+3]
0x1801384f7  mov     r12d, [rsp+240h+var_21F+3]
0x1801384fc  mov     esi, [rsp+240h+var_21F+3]
0x180138500  mov     r14d, [rsp+240h+var_21F+3]
0x180138505  mov     r13d, [rsp+240h+var_21F+3]
0x18013850a  mov     edi, [rsp+240h+var_21F+3]
0x18013850e  mov     dword ptr [rsp+240h+var_1E0], 67h ; 'g'
0x180138516  mov     dword ptr [rsp+240h+var_1E0+4], r15d
0x18013851b  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138522  mov     qword ptr [rsp+240h+var_1D8], rax
0x180138527  lea     rdx, [rsp+240h+var_1E0]
0x18013852c  mov     rcx, [rbp+140h+arg_8]
0x180138533  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x180138538  mov     [rbp+140h+arg_10], rax
0x18013853f  mov     dword ptr [rsp+240h+var_1D0], 68h ; 'h'
0x180138547  mov     dword ptr [rsp+240h+var_1D0+4], r12d
0x18013854c  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138553  mov     [rsp+240h+var_1C8], rax
0x180138558  lea     rdx, [rsp+240h+var_1D0]
0x18013855d  mov     rcx, [rbp+140h+arg_8]
0x180138564  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x180138569  mov     rax, [rbp+140h+arg_10]
0x180138570  mov     rcx, [rbp+140h+arg_8]
0x180138577  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x18013857b  jz      loc_180138812
0x180138581  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180138585  jz      loc_1801387B3
0x18013858b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18013858f  jz      loc_180138751
0x180138595  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180138599  jz      loc_1801386DF
0x18013859f  cmp     rax, 1
0x1801385a3  jz      loc_18013869E
0x1801385a9  cmp     rax, 2
0x1801385ad  jz      loc_18013863F
0x1801385b3  cmp     rax, 3
0x1801385b7  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801385be  jz      short loc_1801385D7
0x1801385c0  mov     [rbp+140h+var_1C0], 89h
0x1801385c7  mov     [rbp+140h+var_1BC], edi
0x1801385ca  mov     [rbp+140h+var_1B8], rax
0x1801385ce  lea     rdx, [rbp+140h+var_1C0]
0x1801385d2  jmp     loc_18013887A
0x1801385d7  mov     [rbp+140h+var_1B0], 74h ; 't'
0x1801385de  mov     [rbp+140h+var_1AC], r13d
0x1801385e2  mov     [rbp+140h+var_1A8], rax
0x1801385e6  lea     rdx, [rbp+140h+var_1B0]
0x1801385ea  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x1801385ef  mov     [rbp+140h+var_B8], rax
0x1801385f6  mov     [rbp+140h+var_B0], 1
0x1801385fd  mov     eax, dword ptr [rsp+240h+var_218+1]
0x180138601  mov     [rbp+140h+var_AF], eax
0x180138607  movzx   eax, word ptr [rsp+240h+var_218+5]
0x18013860c  mov     [rbp+140h+var_AB], ax
0x180138613  mov     al, byte ptr [rsp+240h+var_218+7]
0x180138617  mov     [rbp+140h+var_A9], al
0x18013861d  mov     [rbp+140h+var_1A0], 75h ; 'u'
0x180138624  mov     eax, [rsp+240h+var_21F+3]
0x180138628  mov     [rbp+140h+var_19C], eax
0x18013862b  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138632  mov     [rbp+140h+var_198], rax
0x180138636  lea     rdx, [rbp+140h+var_1A0]
0x18013863a  jmp     loc_180138873
0x18013863f  mov     [rbp+140h+var_190], 70h ; 'p'
0x180138646  mov     eax, [rsp+240h+var_21F+3]
0x18013864a  mov     [rbp+140h+var_18C], eax
0x18013864d  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138654  mov     [rbp+140h+var_188], rax
0x180138658  lea     r8, [rbp+140h+var_190]
0x18013865c  lea     rdx, [rsp+40h]
0x180138661  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180138666  mov     rdx, rax
0x180138669  lea     rcx, [rbp+140h+var_D8]
0x18013866d  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180138672  lea     rcx, [rsp+40h]
0x180138677  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18013867c  mov     [rbp+140h+var_180], 71h ; 'q'
0x180138683  mov     eax, [rsp+240h+var_21F+3]
0x180138687  mov     [rbp+140h+var_17C], eax
0x18013868a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138691  mov     [rbp+140h+var_178], rax
0x180138695  lea     rdx, [rbp+140h+var_180]
0x180138699  jmp     loc_180138873
0x18013869e  mov     [rbp+140h+var_170], 6Ch ; 'l'
0x1801386a5  mov     [rbp+140h+var_16C], esi
0x1801386a8  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801386af  mov     [rbp+140h+var_168], rax
0x1801386b3  lea     rdx, [rbp+140h+var_170]
0x1801386b7  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x1801386bc  mov     [rbp+140h+var_E0], rax
0x1801386c0  mov     [rbp+140h+var_160], 6Dh ; 'm'
0x1801386c7  mov     [rbp+140h+var_15C], r14d
0x1801386cb  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801386d2  mov     [rbp+140h+var_158], rax
0x1801386d6  lea     rdx, [rbp+140h+var_160]
0x1801386da  jmp     loc_180138873
0x1801386df  mov     [rbp+140h+var_150], 78h ; 'x'
0x1801386e6  mov     eax, [rsp+240h+var_21F+3]
0x1801386ea  mov     [rbp+140h+var_14C], eax
0x1801386ed  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801386f4  mov     [rbp+140h+var_148], rax
0x1801386f8  lea     rdx, [rbp+140h+var_150]
0x1801386fc  call    ?GetInt@Decoder@SimpleCbor@@QEAA_JUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetInt(SimpleCbor::impl::slim_source_location)
0x180138701  mov     [rbp+140h+var_A8], rax
0x180138708  mov     [rbp+140h+var_A0], 1
0x18013870f  mov     eax, dword ptr [rsp+240h+var_218+1]
0x180138713  mov     [rbp+140h+var_9F], eax
0x180138719  movzx   eax, word ptr [rsp+240h+var_218+5]
0x18013871e  mov     [rbp+140h+var_9B], ax
0x180138725  mov     al, byte ptr [rsp+240h+var_218+7]
0x180138729  mov     [rbp+140h+var_99], al
0x18013872f  mov     [rbp+140h+var_140], 79h ; 'y'
0x180138736  mov     eax, [rsp+240h+var_21F+3]
0x18013873a  mov     [rbp+140h+var_13C], eax
0x18013873d  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138744  mov     [rbp+140h+var_138], rax
0x180138748  lea     rdx, [rbp+140h+var_140]
0x18013874c  jmp     loc_180138873
0x180138751  mov     [rbp+140h+var_130], 7Ch ; '|'
0x180138758  mov     eax, [rsp+240h+var_21F+3]
0x18013875c  mov     [rbp+140h+var_12C], eax
0x18013875f  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138766  mov     [rbp+140h+var_128], rax
0x18013876a  lea     r8, [rbp+140h+var_130]
0x18013876e  lea     rdx, [rsp+40h]
0x180138773  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180138778  mov     rdx, rax
0x18013877b  lea     rcx, [rbp+140h+var_98]
0x180138782  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180138787  lea     rcx, [rsp+40h]
0x18013878c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180138791  mov     [rbp+140h+var_120], 7Dh ; '}'
0x180138798  mov     eax, [rsp+240h+var_21F+3]
0x18013879c  mov     [rbp+140h+var_11C], eax
0x18013879f  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801387a6  mov     [rbp+140h+var_118], rax
0x1801387aa  lea     rdx, [rbp+140h+var_120]
0x1801387ae  jmp     loc_180138873
0x1801387b3  mov     [rbp+140h+var_110], 80h
0x1801387ba  mov     eax, [rsp+240h+var_21F+3]
0x1801387be  mov     [rbp+140h+var_10C], eax
0x1801387c1  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801387c8  mov     [rbp+140h+var_108], rax
0x1801387cc  lea     r8, [rbp+140h+var_110]
0x1801387d0  lea     rdx, [rsp+40h]
0x1801387d5  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x1801387da  mov     rdx, rax
0x1801387dd  lea     rcx, [rbp+140h+var_78]
0x1801387e4  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x1801387e9  lea     rcx, [rsp+40h]
0x1801387ee  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801387f3  mov     [rbp+140h+var_100], 81h
0x1801387fa  mov     eax, [rsp+240h+var_21F+3]
0x1801387fe  mov     [rbp+140h+var_FC], eax
0x180138801  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138808  mov     [rbp+140h+var_F8], rax
0x18013880c  lea     rdx, [rbp+140h+var_100]
0x180138810  jmp     short loc_180138873
0x180138812  mov     [rbp+140h+var_F0], 84h
0x180138819  mov     eax, [rsp+240h+var_21F+3]
0x18013881d  mov     [rbp+140h+var_EC], eax
0x180138820  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138827  mov     [rbp+140h+var_E8], rax
0x18013882b  lea     r8, [rbp+140h+var_F0]
0x18013882f  lea     rdx, [rsp+40h]
0x180138834  call    ?GetByteString@Decoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Decoder::GetByteString(SimpleCbor::impl::slim_source_location)
0x180138839  mov     rdx, rax
0x18013883c  lea     rcx, [rbp+140h+var_58]
0x180138843  call    ??$_Assign@V?$vector@EV?$allocator@E@std@@@std@@@?$_Optional_construct_base@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAX$$QEAV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Optional_construct_base<std::vector<uchar>>::_Assign<std::vector<uchar>>(std::vector<uchar> &&)
0x180138848  lea     rcx, [rsp+40h]
0x18013884d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180138852  mov     dword ptr [rsp+20h], 85h
0x18013885a  mov     eax, [rsp+240h+var_21F+3]
0x18013885e  mov     [rsp+240h+var_21F+3], eax
0x180138862  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138869  mov     [rsp+240h+var_218], rax
0x18013886e  lea     rdx, [rsp+20h]
0x180138873  mov     rcx, [rbp+140h+arg_8]
0x18013887a  call    ?NextItem@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::NextItem(SimpleCbor::impl::slim_source_location)
0x18013887f  mov     dword ptr [rsp+240h+var_210], 65h ; 'e'
0x180138887  mov     dword ptr [rsp+240h+var_210+4], ebx
0x18013888b  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x180138892  mov     [rsp+240h+var_208], rax
0x180138897  lea     rdx, [rsp+240h+var_210]
0x18013889c  mov     rcx, [rbp+140h+arg_8]
0x1801388a3  call    ?EndOfContainer@Decoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::EndOfContainer(SimpleCbor::impl::slim_source_location)
0x1801388a8  test    al, al
0x1801388aa  jz      loc_18013850E
0x1801388b0  mov     rdi, [rbp+140h+arg_8]
0x1801388b7  mov     rsi, [rbp+140h+arg_0]
0x1801388be  lea     r14, aOnecoreDsSecur_8; "onecore\\ds\\security\\cbor\\lib\\commo"...
0x1801388c5  mov     dword ptr [rsp+20h], 8Ch
0x1801388cd  mov     eax, [rsp+240h+var_21F+3]
0x1801388d1  mov     [rsp+240h+var_21F+3], eax
0x1801388d5  mov     [rsp+240h+var_218], r14
0x1801388da  lea     rdx, [rsp+20h]
0x1801388df  mov     rcx, rdi
0x1801388e2  call    ?LeaveContainer@Decoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Decoder::LeaveContainer(SimpleCbor::impl::slim_source_location)
0x1801388e7  lea     rdx, [rbp+140h+var_E0]
0x1801388eb  mov     rcx, rsi
0x1801388ee  call    ??0EccKey@Cose@@QEAA@$$QEAU01@@Z; Cose::EccKey::EccKey(Cose::EccKey &&)
0x1801388f3  nop
0x1801388f4  lea     rcx, [rbp+140h+var_E0]; this
0x1801388f8  call    ??1EccKey@Cose@@QEAA@XZ; Cose::EccKey::~EccKey(void)
0x1801388fd  mov     rax, rsi
0x180138900  mov     rbx, [rsp+240h+arg_18]
0x180138908  add     rsp, 210h
0x18013890f  pop     r15
0x180138911  pop     r14
0x180138913  pop     r13
0x180138915  pop     r12
0x180138917  pop     rdi
0x180138918  pop     rsi
0x180138919  pop     rbp
0x18013891a  retn
```
