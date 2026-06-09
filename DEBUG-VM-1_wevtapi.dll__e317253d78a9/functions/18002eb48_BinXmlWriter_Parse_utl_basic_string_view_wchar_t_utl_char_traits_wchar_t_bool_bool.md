# BinXmlWriter::Parse(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,bool)

- ea: `0x18002eb48`
- end: `0x18002ee53`
- name: `?Parse@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N1@Z`
- size: `779`
- prototype: `__int64 __fastcall(BinXmlWriter *this)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x180027510`
- `0x18002e034`

## callees

- `0x18000a4b4`
- `0x180018468`
- `0x18001ab4c`
- `0x18001d000`
- `0x18001fc00`
- `0x1800210b0`
- `0x180023c8c`
- `0x180024388`
- `0x18002e4e4`
- `0x18002e5f0`
- `0x18002e628`
- `0x18002e660`
- `0x18002e89c`
- `0x18002e8d0`
- `0x18002e908`
- `0x18002e944`
- `0x18002eab4`
- `0x18002eafc`
- `0x18002eb48`
- `0x18002ee5c`
- `0x18002f3c0`
- `0x18002fce8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BinXmlWriter::Parse(BinXmlWriter *this, __int128 *a2, char a3)
{
  int Token; // esi
  __int128 v5; // xmm0
  BinXmlWriter *v6; // rcx
  bool v7; // dl
  __int64 v8; // rax
  wchar_t v9; // di
  int v10; // edx
  __int64 v11; // r8
  char *v12; // rcx
  __int64 v13; // rdx
  int v14; // ecx
  __int64 v15; // r8
  int v17; // [rsp+28h] [rbp-69h]
  __int128 v18; // [rsp+38h] [rbp-59h] BYREF
  void *v19; // [rsp+48h] [rbp-49h] BYREF
  int v20; // [rsp+50h] [rbp-41h]
  char v21; // [rsp+54h] [rbp-3Dh]
  __int128 v22; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v23[24]; // [rsp+68h] [rbp-29h] BYREF
  _BYTE v24[40]; // [rsp+80h] [rbp-11h] BYREF
  int v25; // [rsp+A8h] [rbp+17h]
  char v26; // [rsp+B8h] [rbp+27h] BYREF
  char v27; // [rsp+C8h] [rbp+37h] BYREF
  unsigned int v28; // [rsp+108h] [rbp+77h] BYREF

  LOBYTE(v28) = a3;
  v22 = *a2;
  WevtXMLParser::WevtXMLParser(v23, &v22);
  do
  {
    v19 = &unk_180040824;
    v20 = 0;
    v21 = 1;
    Token = (unsigned __int8)WevtXMLParser::NextToken(v23);
    GenericLexer::GetTokenText(v24, &v22);
    if ( (unsigned __int8)Token > 7u )
    {
      switch ( Token )
      {
        case 9:
          v18 = v22;
          BinXmlWriter::CDATA(this, &v18);
          break;
        case 11:
          v18 = v22;
          BinXmlString::SetString(&v19, &v18);
          BinXmlWriter::EntityRef(this, (const struct BinXmlString *)&v19);
          break;
        case 12:
          v9 = 126;
          v10 = v22;
          v11 = v22 + 2LL * *((_QWORD *)&v22 + 1);
          if ( (_QWORD)v22 == v11 || *(_WORD *)v22 != 120 )
          {
            v17 = 10;
            v12 = &v27;
          }
          else
          {
            v10 = v22 + 2;
            v17 = 16;
            v12 = &v26;
          }
          v28 = 0;
          v14 = *(_DWORD *)(utl::_FromCharsImpl<utl::from_wchars_result,unsigned int,wchar_t>(
                              (_DWORD)v12,
                              v10,
                              v11,
                              (unsigned int)&v28,
                              v17,
                              0)
                          + 8);
          if ( v14 || (v28 <= 0xFFFF ? (v9 = v28) : (v14 = 34), v14) )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v15, &v22);
            }
          }
          BinXmlWriter::CharRef(this, v9);
          break;
        case 13:
          v18 = v22;
          BinXmlString::SetString(&v19, &v18);
          BinXmlWriter::PITarget(this, (const struct BinXmlString *)&v19);
          break;
        case 14:
          v18 = v22;
          BinXmlWriter::PIData(this, &v18);
          break;
        case 15:
          BinXmlWriter::EndOfFile(this);
          break;
      }
    }
    else
    {
      v5 = v22;
      if ( (_BYTE)Token == 7 )
      {
        v8 = *((_QWORD *)this + 7);
        if ( *((_QWORD *)this + 6) != v8 && (*((_BYTE *)this + 104) || *(_BYTE *)(v8 - 4)) )
          goto LABEL_23;
        v18 = v22;
        if ( !(unsigned __int8)IsStringWhitespace(&v18) )
          goto LABEL_23;
      }
      else
      {
        switch ( Token )
        {
          case 1:
            v18 = v22;
            BinXmlString::SetString(&v19, &v18);
            BinXmlWriter::OpenStartElementTag(this, (const struct BinXmlString *)&v19);
            break;
          case 2:
            goto LABEL_16;
          case 3:
            v7 = 0;
            v6 = this;
            goto LABEL_14;
          case 4:
            v6 = this;
            if ( v25 <= 0 )
            {
              BinXmlWriter::CloseStartElementTag(this, 0);
LABEL_16:
              BinXmlWriter::EndElementTag(this);
              break;
            }
            v7 = 1;
LABEL_14:
            BinXmlWriter::CloseStartElementTag(v6, v7);
            break;
          case 5:
            v18 = v22;
            BinXmlString::SetString(&v19, &v18);
            BinXmlWriter::Attribute(this, (const struct BinXmlString *)&v19);
            break;
          case 6:
LABEL_23:
            v18 = v5;
            if ( *((_BYTE *)this + 105) )
              BinXmlWriter::ParseTemplateString(this);
            else
              BinXmlWriter::StrLenValue(this);
            break;
        }
      }
    }
    BinXmlString::~BinXmlString((BinXmlString *)&v19);
  }
  while ( (_BYTE)Token != 15 );
  return utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v23);
}

```

## disassembly

```asm
0x18002eb48  mov     rax, rsp
0x18002eb4b  mov     [rax+8], rbx
0x18002eb4f  mov     [rax+10h], rsi
0x18002eb53  mov     [rax+18h], r8b
0x18002eb57  push    rbp
0x18002eb58  push    rdi
0x18002eb59  push    r14
0x18002eb5b  lea     rbp, [rax-5Fh]
0x18002eb5f  sub     rsp, 0D0h
0x18002eb66  mov     r14b, r9b
0x18002eb69  mov     rbx, rcx
0x18002eb6c  movaps  xmm0, xmmword ptr [rdx]
0x18002eb6f  movdqa  [rbp+57h+var_90], xmm0
0x18002eb74  lea     rdx, [rbp+57h+var_90]
0x18002eb78  lea     rcx, [rbp+57h+var_80]
0x18002eb7c  call    ??0WevtXMLParser@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; WevtXMLParser::WevtXMLParser(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002eb81  nop
0x18002eb82  lea     rax, unk_180040824
0x18002eb89  mov     [rbp+57h+var_A0], rax
0x18002eb8d  xor     eax, eax
0x18002eb8f  mov     [rbp+57h+var_98], eax
0x18002eb92  mov     [rbp+57h+var_94], 1
0x18002eb96  lea     rcx, [rbp+57h+var_80]
0x18002eb9a  call    ?NextToken@WevtXMLParser@@QEAA?AW4XmlTokenType@@XZ; WevtXMLParser::NextToken(void)
0x18002eb9f  movzx   esi, al
0x18002eba2  lea     rdx, [rbp+57h+var_90]
0x18002eba6  lea     rcx, [rbp+57h+var_68]
0x18002ebaa  call    ?GetTokenText@GenericLexer@@QEAA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@XZ; GenericLexer::GetTokenText(void)
0x18002ebaf  cmp     sil, 7
0x18002ebb3  ja      loc_18002ECB7
0x18002ebb9  movaps  xmm0, [rbp+57h+var_90]
0x18002ebbd  jz      loc_18002EC62
0x18002ebc3  mov     edx, esi
0x18002ebc5  sub     edx, 1
0x18002ebc8  jz      short loc_18002EC3F
0x18002ebca  sub     edx, 1
0x18002ebcd  jz      short loc_18002EC2B
0x18002ebcf  sub     edx, 1
0x18002ebd2  jz      short loc_18002EC38
0x18002ebd4  sub     edx, 1
0x18002ebd7  jz      short loc_18002EC0F
0x18002ebd9  sub     edx, 1
0x18002ebdc  jz      short loc_18002EBEC
0x18002ebde  cmp     edx, 1
0x18002ebe1  jz      loc_18002EC8E
0x18002ebe7  jmp     loc_18002EE1F
0x18002ebec  movdqa  [rbp+57h+var_B0], xmm0
0x18002ebf1  lea     rdx, [rbp+57h+var_B0]
0x18002ebf5  lea     rcx, [rbp+57h+var_A0]
0x18002ebf9  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ebfe  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002ec02  mov     rcx, rbx; this
0x18002ec05  call    ?Attribute@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::Attribute(BinXmlString const &)
0x18002ec0a  jmp     loc_18002EE1F
0x18002ec0f  mov     rcx, rbx; this
0x18002ec12  cmp     [rbp+57h+var_40], 0
0x18002ec16  jle     short loc_18002EC24
0x18002ec18  mov     dl, 1; bool
0x18002ec1a  call    ?CloseStartElementTag@BinXmlWriter@@QEAAX_N@Z; BinXmlWriter::CloseStartElementTag(bool)
0x18002ec1f  jmp     loc_18002EE1F
0x18002ec24  xor     edx, edx; bool
0x18002ec26  call    ?CloseStartElementTag@BinXmlWriter@@QEAAX_N@Z; BinXmlWriter::CloseStartElementTag(bool)
0x18002ec2b  mov     rcx, rbx; this
0x18002ec2e  call    ?EndElementTag@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndElementTag(void)
0x18002ec33  jmp     loc_18002EE1F
0x18002ec38  xor     edx, edx
0x18002ec3a  mov     rcx, rbx
0x18002ec3d  jmp     short loc_18002EC1A
0x18002ec3f  movdqa  [rbp+57h+var_B0], xmm0
0x18002ec44  lea     rdx, [rbp+57h+var_B0]
0x18002ec48  lea     rcx, [rbp+57h+var_A0]
0x18002ec4c  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ec51  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002ec55  mov     rcx, rbx; this
0x18002ec58  call    ?OpenStartElementTag@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::OpenStartElementTag(BinXmlString const &)
0x18002ec5d  jmp     loc_18002EE1F
0x18002ec62  mov     rax, [rbx+38h]
0x18002ec66  cmp     [rbx+30h], rax
0x18002ec6a  jz      short loc_18002EC78
0x18002ec6c  cmp     byte ptr [rbx+68h], 0
0x18002ec70  jnz     short loc_18002EC8E
0x18002ec72  cmp     byte ptr [rax-4], 0
0x18002ec76  jnz     short loc_18002EC8E
0x18002ec78  movdqa  [rbp+57h+var_B0], xmm0
0x18002ec7d  lea     rcx, [rbp+57h+var_B0]
0x18002ec81  call    IsStringWhitespace
0x18002ec86  test    al, al
0x18002ec88  jnz     loc_18002EE1F
0x18002ec8e  movdqa  [rbp+57h+var_B0], xmm0
0x18002ec93  lea     rdx, [rbp+57h+var_B0]
0x18002ec97  mov     rcx, rbx; this
0x18002ec9a  cmp     byte ptr [rbx+69h], 0
0x18002ec9e  jnz     short loc_18002ECAA
0x18002eca0  call    ?StrLenValue@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::StrLenValue(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002eca5  jmp     loc_18002EE1F
0x18002ecaa  mov     r8b, r14b
0x18002ecad  call    ?ParseTemplateString@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z; BinXmlWriter::ParseTemplateString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)
0x18002ecb2  jmp     loc_18002EE1F
0x18002ecb7  mov     ecx, esi
0x18002ecb9  sub     ecx, 9
0x18002ecbc  jz      loc_18002EE09
0x18002ecc2  sub     ecx, 2
0x18002ecc5  jz      loc_18002EDE5
0x18002eccb  sub     ecx, 1
0x18002ecce  jz      short loc_18002ED31
0x18002ecd0  sub     ecx, 1
0x18002ecd3  jz      short loc_18002ED0A
0x18002ecd5  sub     ecx, 1
0x18002ecd8  jz      short loc_18002ECF0
0x18002ecda  cmp     ecx, 1
0x18002ecdd  jnz     loc_18002EE1F
0x18002ece3  mov     rcx, rbx; this
0x18002ece6  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x18002eceb  jmp     loc_18002EE1F
0x18002ecf0  movaps  xmm0, [rbp+57h+var_90]
0x18002ecf4  movdqa  [rbp+57h+var_B0], xmm0
0x18002ecf9  lea     rdx, [rbp+57h+var_B0]
0x18002ecfd  mov     rcx, rbx
0x18002ed00  call    ?PIData@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::PIData(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ed05  jmp     loc_18002EE1F
0x18002ed0a  movaps  xmm0, [rbp+57h+var_90]
0x18002ed0e  movdqa  [rbp+57h+var_B0], xmm0
0x18002ed13  lea     rdx, [rbp+57h+var_B0]
0x18002ed17  lea     rcx, [rbp+57h+var_A0]
0x18002ed1b  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ed20  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002ed24  mov     rcx, rbx; this
0x18002ed27  call    ?PITarget@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::PITarget(BinXmlString const &)
0x18002ed2c  jmp     loc_18002EE1F
0x18002ed31  mov     edi, 7Eh ; '~'
0x18002ed36  mov     rdx, qword ptr [rbp+57h+var_90]
0x18002ed3a  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18002ed3e  lea     r8, [rdx+rax*2]
0x18002ed42  cmp     rdx, r8
0x18002ed45  jz      short loc_18002ED68
0x18002ed47  cmp     word ptr [rdx], 78h ; 'x'
0x18002ed4b  jnz     short loc_18002ED68
0x18002ed4d  add     rdx, 2
0x18002ed51  mov     [rsp+0E0h+var_B8], 0
0x18002ed5a  mov     dword ptr [rsp+0E0h+var_C0], 10h
0x18002ed62  lea     rcx, [rbp+57h+var_30]
0x18002ed66  jmp     short loc_18002ED7D
0x18002ed68  mov     [rsp+0E0h+var_B8], 0
0x18002ed71  mov     dword ptr [rsp+0E0h+var_C0], 0Ah
0x18002ed79  lea     rcx, [rbp+57h+var_20]
0x18002ed7d  mov     [rbp+57h+arg_10], 0
0x18002ed84  lea     r9, [rbp+57h+arg_10]
0x18002ed88  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@I_W@utl@@YA?AUfrom_wchars_result@0@PEB_W0AEAIHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,uint,wchar_t>(wchar_t const *,wchar_t const *,uint &,int,bool *)
0x18002ed8d  mov     ecx, [rax+8]
0x18002ed90  test    ecx, ecx
0x18002ed92  jnz     short loc_18002EDAC
0x18002ed94  cmp     [rbp+57h+arg_10], 0FFFFh
0x18002ed9b  jbe     short loc_18002EDA4
0x18002ed9d  mov     ecx, 22h ; '"'
0x18002eda2  jmp     short loc_18002EDA8
0x18002eda4  movzx   edi, word ptr [rbp+57h+arg_10]
0x18002eda8  test    ecx, ecx
0x18002edaa  jz      short loc_18002EDD8
0x18002edac  lea     rax, WPP_GLOBAL_Control
0x18002edb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edba  cmp     rcx, rax
0x18002edbd  jz      short loc_18002EDD8
0x18002edbf  test    byte ptr [rcx+1Ch], 2
0x18002edc3  jz      short loc_18002EDD8
0x18002edc5  cmp     byte ptr [rcx+19h], 3
0x18002edc9  jb      short loc_18002EDD8
0x18002edcb  lea     r9, [rbp+57h+var_90]
0x18002edcf  mov     rcx, [rcx+10h]
0x18002edd3  call    WPP_SF__utlwsv_
0x18002edd8  movzx   edx, di; wchar_t
0x18002eddb  mov     rcx, rbx; this
0x18002edde  call    ?CharRef@BinXmlWriter@@QEAAX_W@Z; BinXmlWriter::CharRef(wchar_t)
0x18002ede3  jmp     short loc_18002EE1F
0x18002ede5  movaps  xmm0, [rbp+57h+var_90]
0x18002ede9  movdqa  [rbp+57h+var_B0], xmm0
0x18002edee  lea     rdx, [rbp+57h+var_B0]
0x18002edf2  lea     rcx, [rbp+57h+var_A0]
0x18002edf6  call    ?SetString@BinXmlString@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlString::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002edfb  lea     rdx, [rbp+57h+var_A0]; struct BinXmlString *
0x18002edff  mov     rcx, rbx; this
0x18002ee02  call    ?EntityRef@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::EntityRef(BinXmlString const &)
0x18002ee07  jmp     short loc_18002EE1F
0x18002ee09  movaps  xmm0, [rbp+57h+var_90]
0x18002ee0d  movdqa  [rbp+57h+var_B0], xmm0
0x18002ee12  lea     rdx, [rbp+57h+var_B0]
0x18002ee16  mov     rcx, rbx
0x18002ee19  call    ?CDATA@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::CDATA(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ee1e  nop
0x18002ee1f  lea     rcx, [rbp+57h+var_A0]; this
0x18002ee23  call    ??1BinXmlString@@QEAA@XZ; BinXmlString::~BinXmlString(void)
0x18002ee28  cmp     sil, 0Fh
0x18002ee2c  jnz     loc_18002EB82
0x18002ee32  lea     rcx, [rbp+57h+var_80]
0x18002ee36  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002ee3b  lea     r11, [rsp+0E0h+var_10]
0x18002ee43  mov     rbx, [r11+20h]
0x18002ee47  mov     rsi, [r11+28h]
0x18002ee4b  mov     rsp, r11
0x18002ee4e  pop     r14
0x18002ee50  pop     rdi
0x18002ee51  pop     rbp
0x18002ee52  retn
```
