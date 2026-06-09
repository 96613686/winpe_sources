# Json::OurReader::readValue(void)

- ea: `0x180039080`
- end: `0x180039527`
- name: `?readValue@OurReader@Json@@AEAA_NXZ`
- size: `1191`
- prototype: `bool __fastcall(Json::OurReader *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800381b8`
- `0x180038504`
- `0x180038984`

## callees

- `0x1800094a0`
- `0x18000c354`
- `0x18000c3ac`
- `0x18000c850`
- `0x18002ccd0`
- `0x180034324`
- `0x180034538`
- `0x180035f40`
- `0x180036128`
- `0x180036ea0`
- `0x1800370ec`
- `0x1800372cc`
- `0x1800374ac`
- `0x180038504`
- `0x180038984`
- `0x180039080`
- `0x180039958`

## string_xrefs

- `0x1800390b0`: `Exceeded stackLimit in readValue().`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Json::OurReader::readValue(Json::OurReader *this)
{
  int v2; // eax
  char v3; // di
  struct Json::Value *v4; // rax
  bool v5; // al
  bool Object; // al
  struct Json::Value *v7; // rax
  __int64 v8; // r9
  struct Json::Value *v9; // rax
  unsigned __int8 v10; // dl
  unsigned int v11; // r8d
  __int64 v12; // rdx
  int v13; // ecx
  struct Json::Value *v14; // rax
  Json::OurReader *v15; // rcx
  __int64 v16; // r9
  struct Json::Value *v17; // rax
  struct Json::Value *v18; // rax
  char v19; // bl
  struct Json::Value *v21; // rax
  int v22; // ecx
  int v23; // r9d
  unsigned int v24; // edx
  double v25; // rcx
  int v26; // ecx
  struct Json::Value *v27; // r10
  int v28; // ecx
  int v29; // r9d
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // ecx
  int v33; // r9d
  struct Json::Value *v34; // rax
  unsigned __int8 v35; // dl
  unsigned int v36; // r8d
  __int64 v37; // rdx
  int v38; // ecx
  int v39; // ecx
  struct Json::Value *v40; // rax
  int v41; // r9d
  struct Json::Value *v42; // rax
  __int64 v43; // r9
  struct Json::Value *v44; // rax
  __int64 v45; // r9
  __int128 v46; // [rsp+30h] [rbp-19h] BYREF
  __int64 v47; // [rsp+40h] [rbp-9h]
  __int64 v48; // [rsp+48h] [rbp-1h] BYREF
  int v49; // [rsp+50h] [rbp+7h]
  __int128 v50; // [rsp+58h] [rbp+Fh]
  __int64 v51; // [rsp+68h] [rbp+1Fh]

  v2 = *((_DWORD *)this + 46);
  if ( v2 >= *((_DWORD *)this + 49) )
  {
    std::string::string((__int64)&v48, (__int64)"Exceeded stackLimit in readValue().");
    Json::throwRuntimeError(&v48);
  }
  *((_DWORD *)this + 46) = v2 + 1;
  v46 = 0;
  v47 = 0;
  Json::OurReader::skipCommentTokens(this, (struct Json::OurReader::Token *)&v46);
  v3 = 1;
  if ( *((_BYTE *)this + 200) && *((_QWORD *)this + 21) )
  {
    v4 = Json::OurReader::currentValue(this);
    Json::Value::setComment(v4, (char *)this + 152, 0);
    std::wstring::assign((char *)this + 152, &qword_180048C70);
  }
  if ( (int)v46 > 7 )
  {
    if ( (_DWORD)v46 != 8 )
    {
      switch ( (_DWORD)v46 )
      {
        case 9:
          Json::Value::Value((__int64)&v48, 0);
          v34 = Json::OurReader::currentValue(this);
          v35 = *((_BYTE *)v34 + 8);
          *((_BYTE *)v34 + 8) = v49;
          v36 = v49 & 0xFFFFFF00 | v35;
          v37 = *(_QWORD *)v34;
          *(_QWORD *)v34 = v48;
          v48 = v37;
          v38 = ((unsigned __int16)v36 ^ (unsigned __int16)*((_DWORD *)v34 + 2)) & 0x100;
          *((_DWORD *)v34 + 2) ^= v38;
          v39 = v36 ^ v38;
LABEL_38:
          v49 = v39;
          v42 = Json::OurReader::currentValue(this);
          *((_QWORD *)v42 + 3) = v43;
          goto LABEL_39;
        case 0xA:
          v50 = 0;
          v51 = 0;
          v27 = Json::OurReader::currentValue(this);
          v32 = *((char *)v27 + 8);
          *((_BYTE *)v27 + 8) = v33;
          v24 = v32 ^ (v33 ^ v32) & 0xFFFFFF00;
          v30 = *(_QWORD *)v27;
          v31 = 0x7FF8000000000000LL;
          break;
        case 0xB:
          v50 = 0;
          v51 = 0;
          v27 = Json::OurReader::currentValue(this);
          v28 = *((char *)v27 + 8);
          *((_BYTE *)v27 + 8) = v29;
          v24 = v28 ^ (v29 ^ v28) & 0xFFFFFF00;
          v30 = *(_QWORD *)v27;
          v31 = 0x7FF0000000000000LL;
          break;
        case 0xC:
          v50 = 0;
          v51 = 0;
          v21 = Json::OurReader::currentValue(this);
          v22 = *((char *)v21 + 8);
          *((_BYTE *)v21 + 8) = v23;
          v24 = v22 ^ (v23 ^ v22) & 0xFFFFFF00;
          v25 = *(double *)v21;
          *(double *)v21 = DOUBLE_NInf;
          v48 = *(_QWORD *)&v25;
          v26 = ((unsigned __int16)v24 ^ (unsigned __int16)*((_DWORD *)v21 + 2)) & 0x100;
          *((_DWORD *)v21 + 2) ^= v26;
          goto LABEL_37;
        case 0xD:
          goto LABEL_27;
        default:
          goto LABEL_29;
      }
LABEL_36:
      v48 = v30;
      *(_QWORD *)v27 = v31;
      v26 = ((unsigned __int16)v24 ^ (unsigned __int16)*((_DWORD *)v27 + 2)) & 0x100;
      *((_DWORD *)v27 + 2) ^= v26;
LABEL_37:
      v39 = v24 ^ v26;
      goto LABEL_38;
    }
    LOBYTE(v48) = 0;
LABEL_35:
    v51 = 0;
    v50 = 0;
    v40 = Json::OurReader::currentValue(this);
    v24 = *((char *)v40 + 8) ^ (v41 ^ *((char *)v40 + 8)) & 0xFFFFFF00;
    *((_BYTE *)v40 + 8) = v41;
    v27 = v40;
    v30 = *(_QWORD *)v40;
    v31 = v48;
    goto LABEL_36;
  }
  switch ( (_DWORD)v46 )
  {
    case 7:
      LOBYTE(v48) = 1;
      goto LABEL_35;
    case 1:
      Object = Json::OurReader::readObject(this, (struct Json::OurReader::Token *)&v46);
      goto LABEL_19;
    case 2:
LABEL_27:
      if ( !*((_BYTE *)this + 190) )
        goto LABEL_29;
      *((_QWORD *)this + 16) -= 2LL;
      Json::Value::Value((__int64)&v48, 0);
      v9 = Json::OurReader::currentValue(this);
      v10 = *((_BYTE *)v9 + 8);
      *((_BYTE *)v9 + 8) = v49;
      v11 = v10 | v49 & 0xFFFFFF00;
      v12 = *(_QWORD *)v9;
      *(_QWORD *)v9 = v48;
      v48 = v12;
      v13 = ((unsigned __int16)v11 ^ (unsigned __int16)*((_DWORD *)v9 + 2)) & 0x100;
      *((_DWORD *)v9 + 2) ^= v13;
      v49 = v11 ^ v13;
      v14 = Json::OurReader::currentValue(this);
      *((_QWORD *)v14 + 3) = v16;
LABEL_39:
      v44 = Json::OurReader::currentValue(v15);
      *((_QWORD *)v44 + 4) = v45;
      Json::Value::~Value((Json::Value *)&v48);
      goto LABEL_40;
    case 3:
      Object = Json::OurReader::readArray(this, (struct Json::OurReader::Token *)&v46);
LABEL_19:
      v3 = Object;
      v7 = Json::OurReader::currentValue(this);
      *((_QWORD *)v7 + 4) = v8;
      goto LABEL_40;
    case 4:
      goto LABEL_27;
    case 5:
      v5 = Json::OurReader::decodeString(this, (struct Json::OurReader::Token *)&v46);
      goto LABEL_15;
  }
  if ( (_DWORD)v46 != 6 )
  {
LABEL_29:
    v17 = Json::OurReader::currentValue(this);
    *((_QWORD *)v17 + 3) = (__int64)(*((_QWORD *)&v46 + 1) - *((_QWORD *)this + 14)) >> 1;
    v18 = Json::OurReader::currentValue(this);
    *((_QWORD *)v18 + 4) = (v47 - *((_QWORD *)this + 14)) >> 1;
    std::wstring::wstring((__int64)&v48, (__int64)L"Syntax error: value, object or array expected.");
    v19 = Json::OurReader::addError((_DWORD)this, 1, (unsigned int)&v48, (unsigned int)&v46, 0);
    std::wstring::_Tidy_deallocate(&v48);
    return v19;
  }
  v5 = Json::OurReader::decodeNumber(this, (struct Json::OurReader::Token *)&v46);
LABEL_15:
  v3 = v5;
LABEL_40:
  if ( *((_BYTE *)this + 200) )
  {
    *((_QWORD *)this + 17) = *((_QWORD *)this + 16);
    *((_QWORD *)this + 18) = Json::OurReader::currentValue(this);
  }
  --*((_DWORD *)this + 46);
  return v3;
}

```

## disassembly

```asm
0x180039080  push    rbp
0x180039082  push    rbx
0x180039083  push    rsi
0x180039084  push    rdi
0x180039085  lea     rbp, [rsp-3Fh]
0x18003908a  sub     rsp, 88h
0x180039091  mov     rax, cs:__security_cookie
0x180039098  xor     rax, rsp
0x18003909b  mov     [rbp+57h+var_30], rax
0x18003909f  mov     rbx, rcx
0x1800390a2  mov     eax, [rcx+0B8h]
0x1800390a8  cmp     eax, [rcx+0C4h]
0x1800390ae  jl      short loc_1800390CB
0x1800390b0  lea     rdx, aExceededStackl; "Exceeded stackLimit in readValue()."
0x1800390b7  lea     rcx, [rbp+57h+var_58]
0x1800390bb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800390c0  nop
0x1800390c1  lea     rcx, [rbp+57h+var_58]
0x1800390c5  call    ?throwRuntimeError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwRuntimeError(std::string const &)
0x1800390cb  inc     eax
0x1800390cd  mov     [rcx+0B8h], eax
0x1800390d3  xorps   xmm0, xmm0
0x1800390d6  xor     eax, eax
0x1800390d8  movups  [rbp+57h+var_70], xmm0
0x1800390dc  mov     [rbp+57h+var_60], rax
0x1800390e0  lea     rdx, [rbp+57h+var_70]; struct Json::OurReader::Token *
0x1800390e4  call    ?skipCommentTokens@OurReader@Json@@AEAAXAEAVToken@12@@Z; Json::OurReader::skipCommentTokens(Json::OurReader::Token &)
0x1800390e9  mov     edi, 1
0x1800390ee  cmp     byte ptr [rbx+0C8h], 0
0x1800390f5  jz      short loc_18003912A
0x1800390f7  lea     rsi, [rbx+98h]
0x1800390fe  cmp     qword ptr [rsi+10h], 0
0x180039103  jz      short loc_18003912A
0x180039105  mov     rcx, rbx; this
0x180039108  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x18003910d  xor     r8d, r8d
0x180039110  mov     rdx, rsi
0x180039113  mov     rcx, rax
0x180039116  call    ?setComment@Value@Json@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CommentPlacement@2@@Z; Json::Value::setComment(std::wstring const &,Json::CommentPlacement)
0x18003911b  lea     rdx, qword_180048C70
0x180039122  mov     rcx, rsi
0x180039125  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18003912a  mov     ecx, dword ptr [rbp+57h+var_70]
0x18003912d  cmp     ecx, 7
0x180039130  jg      loc_1800391C7
0x180039136  jz      loc_1800391BE
0x18003913c  sub     ecx, edi
0x18003913e  jz      short loc_180039190
0x180039140  sub     ecx, edi
0x180039142  jz      loc_1800391F8
0x180039148  sub     ecx, edi
0x18003914a  jz      short loc_180039182
0x18003914c  sub     ecx, edi
0x18003914e  jz      loc_1800391F8
0x180039154  sub     ecx, edi
0x180039156  jz      short loc_180039174
0x180039158  cmp     ecx, edi
0x18003915a  jnz     loc_180039287
0x180039160  lea     rdx, [rbp+57h+var_70]; struct Json::OurReader::Token *
0x180039164  mov     rcx, rbx; this
0x180039167  call    ?decodeNumber@OurReader@Json@@AEAA_NAEAVToken@12@@Z; Json::OurReader::decodeNumber(Json::OurReader::Token &)
0x18003916c  mov     dil, al
0x18003916f  jmp     loc_1800394E0
0x180039174  lea     rdx, [rbp+57h+var_70]; struct Json::OurReader::Token *
0x180039178  mov     rcx, rbx; this
0x18003917b  call    ?decodeString@OurReader@Json@@AEAA_NAEAVToken@12@@Z; Json::OurReader::decodeString(Json::OurReader::Token &)
0x180039180  jmp     short loc_18003916C
0x180039182  lea     rdx, [rbp+57h+var_70]; struct Json::OurReader::Token *
0x180039186  mov     rcx, rbx; this
0x180039189  call    ?readArray@OurReader@Json@@AEAA_NAEAVToken@12@@Z; Json::OurReader::readArray(Json::OurReader::Token &)
0x18003918e  jmp     short loc_18003919C
0x180039190  lea     rdx, [rbp+57h+var_70]; struct Json::OurReader::Token *
0x180039194  mov     rcx, rbx; this
0x180039197  call    ?readObject@OurReader@Json@@AEAA_NAEAVToken@12@@Z; Json::OurReader::readObject(Json::OurReader::Token &)
0x18003919c  mov     dil, al
0x18003919f  mov     r9, [rbx+80h]
0x1800391a6  sub     r9, [rbx+70h]
0x1800391aa  sar     r9, 1
0x1800391ad  mov     rcx, rbx; this
0x1800391b0  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x1800391b5  mov     [rax+20h], r9
0x1800391b9  jmp     loc_1800394E0
0x1800391be  mov     byte ptr [rbp+57h+var_58], dil
0x1800391c2  jmp     loc_18003944A
0x1800391c7  sub     ecx, 8
0x1800391ca  jz      loc_180039446
0x1800391d0  sub     ecx, edi
0x1800391d2  jz      loc_1800393F7
0x1800391d8  sub     ecx, edi
0x1800391da  jz      loc_1800393A6
0x1800391e0  sub     ecx, edi
0x1800391e2  jz      loc_180039355
0x1800391e8  sub     ecx, edi
0x1800391ea  jz      loc_1800392F3
0x1800391f0  cmp     ecx, edi
0x1800391f2  jnz     loc_180039287
0x1800391f8  cmp     byte ptr [rbx+0BEh], 0
0x1800391ff  jz      loc_180039287
0x180039205  add     qword ptr [rbx+80h], 0FFFFFFFFFFFFFFFEh
0x18003920d  xor     edx, edx
0x18003920f  lea     rcx, [rbp+57h+var_58]
0x180039213  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180039218  mov     rcx, rbx; this
0x18003921b  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x180039220  movsx   edx, byte ptr [rax+8]
0x180039224  mov     cl, byte ptr [rbp+57h+var_50]
0x180039227  mov     [rax+8], cl
0x18003922a  mov     r8d, [rbp+57h+var_50]
0x18003922e  and     r8d, 0FFFFFF00h
0x180039235  movzx   ecx, dl
0x180039238  or      r8d, ecx
0x18003923b  mov     rdx, [rax]
0x18003923e  mov     rcx, [rbp+57h+var_58]
0x180039242  mov     [rax], rcx
0x180039245  mov     [rbp+57h+var_58], rdx
0x180039249  mov     ecx, [rax+8]
0x18003924c  xor     ecx, r8d
0x18003924f  and     ecx, 100h
0x180039255  xor     [rax+8], ecx
0x180039258  xor     ecx, r8d
0x18003925b  mov     [rbp+57h+var_50], ecx
0x18003925e  mov     r9, [rbx+80h]
0x180039265  sub     r9, [rbx+70h]
0x180039269  sar     r9, 1
0x18003926c  sub     r9, rdi
0x18003926f  mov     rcx, rbx; this
0x180039272  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x180039277  mov     [rax+18h], r9
0x18003927b  mov     r9, [rbx+80h]
0x180039282  jmp     loc_1800394C7
0x180039287  mov     rcx, rbx; this
0x18003928a  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x18003928f  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x180039293  sub     rcx, [rbx+70h]
0x180039297  sar     rcx, 1
0x18003929a  mov     [rax+18h], rcx
0x18003929e  mov     rcx, rbx; this
0x1800392a1  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x1800392a6  mov     r8, [rbp+57h+var_60]
0x1800392aa  sub     r8, [rbx+70h]
0x1800392ae  sar     r8, 1
0x1800392b1  mov     [rax+20h], r8
0x1800392b5  lea     rdx, aSyntaxErrorVal; "Syntax error: value, object or array ex"...
0x1800392bc  lea     rcx, [rbp+57h+var_58]
0x1800392c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800392c5  nop
0x1800392c6  mov     [rsp+0A0h+var_80], 0
0x1800392cf  lea     r9, [rbp+57h+var_70]
0x1800392d3  lea     r8, [rbp+57h+var_58]
0x1800392d7  mov     edx, edi
0x1800392d9  mov     rcx, rbx
0x1800392dc  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x1800392e1  mov     bl, al
0x1800392e3  lea     rcx, [rbp+57h+var_58]
0x1800392e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800392ec  mov     al, bl
0x1800392ee  jmp     loc_18003950F
0x1800392f3  mov     r9d, [rbp+57h+var_50]
0x1800392f7  and     r9d, 0FFFFFE03h
0x1800392fe  or      r9d, 3
0x180039302  xorps   xmm0, xmm0
0x180039305  movdqu  [rbp+57h+var_48], xmm0
0x18003930a  mov     [rbp+57h+var_38], 0
0x180039312  movsd   xmm1, cs:__real@fff0000000000000
0x18003931a  mov     rcx, rbx; this
0x18003931d  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x180039322  movsx   ecx, byte ptr [rax+8]
0x180039326  mov     [rax+8], r9b
0x18003932a  mov     edx, ecx
0x18003932c  xor     edx, r9d
0x18003932f  and     edx, 0FFFFFF00h
0x180039335  xor     edx, ecx
0x180039337  mov     rcx, [rax]
0x18003933a  movsd   qword ptr [rax], xmm1
0x18003933e  mov     [rbp+57h+var_58], rcx
0x180039342  mov     ecx, [rax+8]
0x180039345  xor     ecx, edx
0x180039347  and     ecx, 100h
0x18003934d  xor     [rax+8], ecx
0x180039350  jmp     loc_1800394A7
0x180039355  mov     r9d, [rbp+57h+var_50]
0x180039359  and     r9d, 0FFFFFE03h
0x180039360  or      r9d, 3
0x180039364  xorps   xmm0, xmm0
0x180039367  movdqu  [rbp+57h+var_48], xmm0
0x18003936c  mov     [rbp+57h+var_38], 0
0x180039374  mov     rcx, rbx; this
0x180039377  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x18003937c  mov     r10, rax
0x18003937f  movsx   ecx, byte ptr [rax+8]
0x180039383  mov     [rax+8], r9b
0x180039387  mov     edx, ecx
0x180039389  xor     edx, r9d
0x18003938c  and     edx, 0FFFFFF00h
0x180039392  xor     edx, ecx
0x180039394  mov     rcx, [rax]
0x180039397  mov     rax, 7FF0000000000000h
0x1800393a1  jmp     loc_180039490
0x1800393a6  mov     r9d, [rbp+57h+var_50]
0x1800393aa  and     r9d, 0FFFFFE03h
0x1800393b1  or      r9d, 3
0x1800393b5  xorps   xmm0, xmm0
0x1800393b8  movdqu  [rbp+57h+var_48], xmm0
0x1800393bd  mov     [rbp+57h+var_38], 0
0x1800393c5  mov     rcx, rbx; this
0x1800393c8  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x1800393cd  mov     r10, rax
0x1800393d0  movsx   ecx, byte ptr [rax+8]
0x1800393d4  mov     [rax+8], r9b
0x1800393d8  mov     edx, ecx
0x1800393da  xor     edx, r9d
0x1800393dd  and     edx, 0FFFFFF00h
0x1800393e3  xor     edx, ecx
0x1800393e5  mov     rcx, [rax]
0x1800393e8  mov     rax, 7FF8000000000000h
0x1800393f2  jmp     loc_180039490
0x1800393f7  xor     edx, edx
0x1800393f9  lea     rcx, [rbp+57h+var_58]
0x1800393fd  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180039402  mov     rcx, rbx; this
0x180039405  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x18003940a  movsx   edx, byte ptr [rax+8]
0x18003940e  mov     cl, byte ptr [rbp+57h+var_50]
0x180039411  mov     [rax+8], cl
0x180039414  movzx   r8d, dl
0x180039418  mov     ecx, [rbp+57h+var_50]
0x18003941b  and     ecx, 0FFFFFF00h
0x180039421  or      r8d, ecx
0x180039424  mov     rdx, [rax]
0x180039427  mov     rcx, [rbp+57h+var_58]
0x18003942b  mov     [rax], rcx
0x18003942e  mov     [rbp+57h+var_58], rdx
0x180039432  mov     ecx, [rax+8]
0x180039435  xor     ecx, r8d
0x180039438  and     ecx, 100h
0x18003943e  xor     [rax+8], ecx
0x180039441  xor     ecx, r8d
0x180039444  jmp     short loc_1800394A9
0x180039446  mov     byte ptr [rbp+57h+var_58], 0
0x18003944a  mov     r9d, [rbp+57h+var_50]
0x18003944e  xorps   xmm0, xmm0
0x180039451  and     r9d, 0FFFFFE05h
0x180039458  mov     [rbp+57h+var_38], 0
0x180039460  movdqu  [rbp+57h+var_48], xmm0
0x180039465  or      r9d, 5
0x180039469  mov     rcx, rbx; this
0x18003946c  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x180039471  movsx   ecx, byte ptr [rax+8]
0x180039475  mov     edx, ecx
0x180039477  xor     edx, r9d
0x18003947a  and     edx, 0FFFFFF00h
0x180039480  xor     edx, ecx
0x180039482  mov     [rax+8], r9b
0x180039486  mov     r10, rax
0x180039489  mov     rcx, [rax]
0x18003948c  mov     rax, [rbp+57h+var_58]
0x180039490  mov     [rbp+57h+var_58], rcx
0x180039494  mov     [r10], rax
0x180039497  mov     ecx, [r10+8]
0x18003949b  xor     ecx, edx
0x18003949d  and     ecx, 100h
0x1800394a3  xor     [r10+8], ecx
0x1800394a7  xor     ecx, edx
0x1800394a9  mov     r9, qword ptr [rbp+57h+var_70+8]
0x1800394ad  sub     r9, [rbx+70h]
0x1800394b1  mov     [rbp+57h+var_50], ecx
0x1800394b4  sar     r9, 1
0x1800394b7  mov     rcx, rbx; this
0x1800394ba  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x1800394bf  mov     [rax+18h], r9
0x1800394c3  mov     r9, [rbp+57h+var_60]
0x1800394c7  sub     r9, [rbx+70h]
0x1800394cb  sar     r9, 1
0x1800394ce  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x1800394d3  mov     [rax+20h], r9
0x1800394d7  lea     rcx, [rbp+57h+var_58]; this
0x1800394db  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x1800394e0  cmp     byte ptr [rbx+0C8h], 0
0x1800394e7  jz      short loc_180039506
0x1800394e9  mov     rax, [rbx+80h]
0x1800394f0  mov     [rbx+88h], rax
0x1800394f7  mov     rcx, rbx; this
0x1800394fa  call    ?currentValue@OurReader@Json@@AEAAAEAVValue@2@XZ; Json::OurReader::currentValue(void)
0x1800394ff  mov     [rbx+90h], rax
0x180039506  dec     dword ptr [rbx+0B8h]
0x18003950c  mov     al, dil
0x18003950f  mov     rcx, [rbp+57h+var_30]
0x180039513  xor     rcx, rsp; StackCookie
0x180039516  call    __security_check_cookie
0x18003951b  add     rsp, 88h
0x180039522  pop     rdi
0x180039523  pop     rsi
0x180039524  pop     rbx
0x180039525  pop     rbp
0x180039526  retn
```
