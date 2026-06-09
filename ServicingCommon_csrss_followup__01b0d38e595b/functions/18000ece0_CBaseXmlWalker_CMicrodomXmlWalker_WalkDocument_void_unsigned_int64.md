# CBaseXmlWalker<CMicrodomXmlWalker>::WalkDocument(void *,unsigned __int64)

- ea: `0x18000ece0`
- end: `0x18000f168`
- name: `?WalkDocument@?$CBaseXmlWalker@VCMicrodomXmlWalker@@@@QEAAJPEAX_K@Z`
- size: `1160`
- prototype: `__int64 __fastcall(struct CXmlCursor *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dcd0`

## callees

- `0x180003bb8`
- `0x180009820`
- `0x18000e030`
- `0x18000e924`
- `0x18000ece0`
- `0x18000f270`
- `0x18001a620`
- `0x18001b150`
- `0x18001f840`
- `0x1800209fc`
- `0x180025870`
- `0x18002d2b0`
- `0x180062a78`
- `0x180062c34`
- `0x180062dbc`
- `0x180062f98`
- `0x180063140`
- `0x180063234`
- `0x1800633cc`
- `0x18006350c`
- `0x180063724`
- `0x1800637c0`
- `0x180097e20`

## string_xrefs

- `0x18000ed68`: `CXmlLogicalState::Initialize`
- `0x18000ed7c`: `RtlXmlInitializeNextLogicalThing(this, &Init)`
- `0x18000ed4c`: `onecore\base\xml\udom_xmlwalker.h`
- `0x18000ee0c`: `onecore\base\xml\udom_xmlcursor.cpp`
- `0x18000ee13`: `CXmlCursor::Next`
- `0x18000efdf`: `RtlXmlNextLogicalThingEx( &m_State, &m_Namespaces, &m_CurrentThing, &m_AttributeList, skipXmlDeclDetect )`

## pseudocode

```c
__int64 __fastcall CBaseXmlWalker<CMicrodomXmlWalker>::WalkDocument(
        CMicrodomBuilder **a1,
        CMicrodomBuilder *a2,
        CMicrodomBuilder *a3)
{
  unsigned int v6; // edx
  unsigned int v7; // r8d
  void *v8; // r9
  int (*v9)(void *, const struct _XML_EXTENT *, const struct _XML_EXTENT *, enum XML_STRING_COMPARE *); // rdx
  int v10; // ebx
  __int64 result; // rax
  struct CXmlCursor *v12; // rdx
  int LogicalThing; // eax
  int v14; // eax
  CMicrodomBuilder *v15; // rcx
  __int64 v16; // r8
  const char *v17; // [rsp+30h] [rbp-C8h] BYREF
  const char *v18; // [rsp+38h] [rbp-C0h]
  __int64 v19; // [rsp+40h] [rbp-B8h]
  const char *v20; // [rsp+48h] [rbp-B0h]
  _QWORD v21[10]; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-48h] BYREF

  memset(v21, 0, sizeof(v21));
  v22 = 0;
  if ( a1 )
  {
    memset(a1, 0, 0x8B0u);
    memset(a1, 0, 0x160u);
    *a1 = a2;
    a1[3] = (CMicrodomBuilder *)((char *)a2 + (_QWORD)a3);
    a1[1] = a3;
    a1[4] = a2;
    a1[5] = 0;
    a1[40] = (CMicrodomBuilder *)RtlXmlDefaultSpecialStringCompare;
    a1[38] = (CMicrodomBuilder *)RtlXmlDefaultCompareStrings;
    a1[39] = (CMicrodomBuilder *)v21[8];
    a1[41] = (CMicrodomBuilder *)v21[5];
    *((_DWORD *)a1 + 26) = 3;
    *((_DWORD *)a1 + 86) = 1;
    *((_DWORD *)a1 + 87) = 1;
    *((_BYTE *)a1 + 340) = 1;
    v10 = RtlInitializeGrowingList((int)a1 + 360, 224, 40, (int)a1 + 432, 1792, (__int64)(a1 + 1169));
    if ( v10 < 0 )
      goto LABEL_3;
    v10 = RtlXmlDetermineStreamEncoding(a1, &v22, v16);
    if ( v10 < 0 )
      goto LABEL_3;
    a1[4] = (CMicrodomBuilder *)((char *)a1[4] + v22);
  }
  else
  {
    v10 = RtlXmlReportErrorFunction(-1073741811, v6, v7, v8);
    if ( v10 < 0 )
    {
LABEL_3:
      v19 = 150;
      v17 = "onecore\\base\\xml\\udom_xmlwalker.h";
      v18 = "CXmlLogicalState::Initialize";
      v20 = "RtlXmlInitializeNextLogicalThing(this, &Init)";
      RtlReportErrorOrigination(&v17, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
      return (unsigned int)v10;
    }
  }
  *((_BYTE *)a1 + 2224) = 1;
  v10 = CXmlNamespaceManager::Initialize(
          (CXmlNamespaceManager *)(a1 + 279),
          v9,
          a1,
          (struct _RTL_ALLOCATOR *)(a1 + 1169));
  if ( v10 < 0 )
    return (unsigned int)v10;
  v10 = CRtlGrowingList<_XMLDOC_ATTRIBUTE,50,4>::Initialize(a1 + 432, a1 + 1169);
  if ( v10 < 0 )
    return (unsigned int)v10;
  memset(a1 + 1141, 0, 0xE0u);
  *((_BYTE *)a1 + 9376) = *((_DWORD *)a1 + 12) == 5;
  result = CMicrodomBuilder::StartDocument(a1[1173], v12);
  if ( (int)result >= 0 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_8:
        if ( *((_DWORD *)a1 + 2282) == 1 )
          return 0;
        LODWORD(v22) = 0;
        LogicalThing = RtlXmlNextLogicalThingEx(
                         (struct _XML_TOKENIZATION_STATE *)a1,
                         (struct _NS_MANAGER *)(a1 + 279),
                         a1 + 1141,
                         (struct _RTL_GROWING_LIST *)(a1 + 432));
        if ( LogicalThing < 0 )
        {
          v17 = "onecore\\base\\xml\\udom_xmlcursor.cpp";
          v20 = "RtlXmlNextLogicalThingEx( &m_State, &m_Namespaces, &m_CurrentThing, &m_AttributeList, skipXmlDeclDetect )";
          v18 = "CXmlCursor::Next";
          v19 = 64;
          result = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                     &v22,
                     &v17,
                     (unsigned int)LogicalThing);
          if ( (int)result < 0 )
            return result;
        }
        v14 = *((_DWORD *)a1 + 2282);
        if ( v14 != 7 )
          break;
        result = CMicrodomBuilder::ConsumePCData(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result < 0 )
          return result;
      }
      if ( v14 != 3 )
        break;
      v15 = a1[1173];
      *((_BYTE *)a1 + 9392) = 1;
      result = CMicrodomBuilder::StartElement(v15, (struct CXmlCursor *)a1);
      if ( (int)result < 0 )
        return result;
    }
    switch ( v14 )
    {
      case 0:
        result = CMicrodomXmlWalker::XmlError((CMicrodomXmlWalker *)a1, (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          return 0;
        break;
      case 4:
        result = CMicrodomBuilder::EndElement(a1[1173]);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      case 5:
        result = CMicrodomBuilder::ConsumeProcessingInstruction(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      case 8:
        result = CMicrodomBuilder::ConsumeCData(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      case 9:
        result = CMicrodomBuilder::ConsumeEntityDecl(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      case 10:
        result = CMicrodomBuilder::StartAttlist(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      case 11:
        result = CMicrodomBuilder::ConsumeAttdef(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      case 12:
        result = CMicrodomBuilder::EndAttlist(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      case 13:
        result = CMicrodomBuilder::ConsumeComment(a1[1173], (struct CXmlCursor *)a1);
        if ( (int)result >= 0 )
          goto LABEL_8;
        break;
      default:
        goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ece0  push    rbx
0x18000ece2  push    rbp
0x18000ece3  push    rsi
0x18000ece4  push    rdi
0x18000ece5  push    r14
0x18000ece7  push    r15
0x18000ece9  sub     rsp, 0C8h
0x18000ecf0  mov     rax, cs:__security_cookie
0x18000ecf7  xor     rax, rsp
0x18000ecfa  mov     [rsp+0F8h+var_40], rax
0x18000ed02  mov     rsi, r8
0x18000ed05  mov     rbx, rdx
0x18000ed08  mov     rdi, rcx
0x18000ed0b  xor     edx, edx; Val
0x18000ed0d  mov     r8d, 50h ; 'P'; Size
0x18000ed13  lea     rcx, [rsp+0F8h+var_A0]; void *
0x18000ed18  call    memset
0x18000ed1d  xor     r15d, r15d
0x18000ed20  lea     r14, [rdi+2488h]
0x18000ed27  mov     [rsp+0F8h+var_48], r15
0x18000ed2f  test    rdi, rdi
0x18000ed32  jnz     loc_18000EEAF
0x18000ed38  mov     ecx, 0C000000Dh; int
0x18000ed3d  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x18000ed42  mov     ebx, eax
0x18000ed44  test    eax, eax
0x18000ed46  jns     loc_18000EF9E
0x18000ed4c  lea     rax, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_xmlwalker.h"
0x18000ed53  mov     [rsp+0F8h+var_B8], 96h
0x18000ed5c  mov     [rsp+0F8h+var_C8], rax
0x18000ed61  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000ed68  lea     rax, aCxmllogicalsta_0; "CXmlLogicalState::Initialize"
0x18000ed6f  mov     r8d, ebx
0x18000ed72  mov     [rsp+0F8h+var_C0], rax
0x18000ed77  lea     rcx, [rsp+0F8h+var_C8]
0x18000ed7c  lea     rax, aRtlxmlinitiali_1; "RtlXmlInitializeNextLogicalThing(this, "...
0x18000ed83  mov     [rsp+0F8h+var_B0], rax
0x18000ed88  call    RtlReportErrorOrigination
0x18000ed8d  mov     eax, ebx
0x18000ed8f  jmp     short loc_18000EDA3
0x18000ed91  xor     eax, eax
0x18000ed93  mov     r12, [rsp+0F8h+arg_18]
0x18000ed9b  mov     r13, [rsp+0F8h+var_38]
0x18000eda3  mov     rcx, [rsp+0F8h+var_40]
0x18000edab  xor     rcx, rsp; StackCookie
0x18000edae  call    __security_check_cookie
0x18000edb3  add     rsp, 0C8h
0x18000edba  pop     r15
0x18000edbc  pop     r14
0x18000edbe  pop     rdi
0x18000edbf  pop     rsi
0x18000edc0  pop     rbp
0x18000edc1  pop     rbx
0x18000edc2  retn
0x18000edc4  lea     rcx, [rdi+23A8h]; void *
0x18000edcb  xor     edx, edx; Val
0x18000edcd  mov     r8d, 0E0h; Size
0x18000edd3  call    memset
0x18000edd8  cmp     dword ptr [rdi+30h], 5
0x18000eddc  setz    al
0x18000eddf  mov     [rdi+24A0h], al
0x18000ede5  mov     rcx, [rdi+24A8h]; this
0x18000edec  call    ?StartDocument@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::StartDocument(CXmlCursor *)
0x18000edf1  test    eax, eax
0x18000edf3  js      short loc_18000EDA3
0x18000edf5  mov     [rsp+0F8h+arg_18], r12
0x18000edfd  lea     r14, __ImageBase
0x18000ee04  mov     [rsp+0F8h+var_38], r13
0x18000ee0c  lea     r12, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_xmlcursor.cpp"
0x18000ee13  lea     r13, aCxmlcursorNext; "CXmlCursor::Next"
0x18000ee1a  nop     word ptr [rax+rax+00h]
0x18000ee20  cmp     dword ptr [rdi+23A8h], 1; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000ee27  jz      loc_18000ED91
0x18000ee2d  lea     r9, [rdi+0D80h]; struct _RTL_GROWING_LIST *
0x18000ee34  mov     dword ptr [rsp+0F8h+var_48], r15d
0x18000ee3c  lea     r8, [rdi+23A8h]; void *
0x18000ee43  mov     byte ptr [rsp+0F8h+var_D8], r15b
0x18000ee48  lea     rdx, [rdi+8B8h]; struct _NS_MANAGER *
0x18000ee4f  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18000ee52  call    RtlXmlNextLogicalThingEx
0x18000ee57  test    eax, eax
0x18000ee59  js      loc_18000EFDF
0x18000ee5f  movsxd  rax, dword ptr [rdi+23A8h]
0x18000ee66  cmp     eax, 7
0x18000ee69  jnz     short loc_18000EE83
0x18000ee6b  mov     rcx, [rdi+24A8h]; this
0x18000ee72  mov     rdx, rdi; struct CXmlCursor *
0x18000ee75  call    ?ConsumePCData@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::ConsumePCData(CXmlCursor *)
0x18000ee7a  test    eax, eax
0x18000ee7c  jns     short def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000ee7e  jmp     loc_18000ED93
0x18000ee83  cmp     eax, 3
0x18000ee86  jnz     loc_18000F020
0x18000ee8c  mov     rcx, [rdi+24A8h]; this
0x18000ee93  mov     rdx, rdi; struct CXmlCursor *
0x18000ee96  mov     byte ptr [rdi+24B0h], 1
0x18000ee9d  call    ?StartElement@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::StartElement(CXmlCursor *)
0x18000eea2  test    eax, eax
0x18000eea4  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000eeaa  jmp     loc_18000ED93
0x18000eeaf  xor     edx, edx; Val
0x18000eeb1  mov     r8d, 8B0h; Size
0x18000eeb7  mov     rcx, rdi; void *
0x18000eeba  call    memset
0x18000eebf  xor     edx, edx; Val
0x18000eec1  mov     r8d, 160h; Size
0x18000eec7  mov     rcx, rdi; void *
0x18000eeca  call    memset
0x18000eecf  mov     [rdi], rbx
0x18000eed2  lea     rax, [rsi+rbx]
0x18000eed6  mov     [rdi+18h], rax
0x18000eeda  lea     r9, [rdi+1B0h]
0x18000eee1  mov     [rdi+8], rsi
0x18000eee5  lea     rax, ?RtlXmlDefaultSpecialStringCompare@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_EXTENT@@PEBU_XML_SIMPLE_STRING@@PEAW4XML_STRING_COMPARE@@P6AKK@Z@Z; RtlXmlDefaultSpecialStringCompare(_XML_TOKENIZATION_STATE *,_XML_EXTENT const *,_XML_SIMPLE_STRING const *,XML_STRING_COMPARE *,ulong (*)(ulong))
0x18000eeec  mov     [rdi+20h], rbx
0x18000eef0  lea     rcx, [rdi+168h]
0x18000eef7  mov     [rdi+28h], r15
0x18000eefb  mov     edx, 0E0h
0x18000ef00  mov     [rdi+140h], rax
0x18000ef07  mov     r8d, 28h ; '('
0x18000ef0d  lea     rax, RtlXmlDefaultCompareStrings
0x18000ef14  mov     [rsp+0F8h+var_D0], r14
0x18000ef19  mov     [rdi+130h], rax
0x18000ef20  mov     rax, [rsp+0F8h+var_60]
0x18000ef28  mov     [rdi+138h], rax
0x18000ef2f  mov     rax, [rsp+0F8h+var_78]
0x18000ef37  mov     [rdi+148h], rax
0x18000ef3e  mov     dword ptr [rdi+68h], 3
0x18000ef45  mov     dword ptr [rdi+158h], 1
0x18000ef4f  mov     dword ptr [rdi+15Ch], 1
0x18000ef59  mov     byte ptr [rdi+154h], 1
0x18000ef60  mov     [rsp+0F8h+var_D8], 700h
0x18000ef69  call    RtlInitializeGrowingList
0x18000ef6e  mov     ebx, eax
0x18000ef70  test    eax, eax
0x18000ef72  js      loc_18000ED4C
0x18000ef78  lea     rdx, [rsp+0F8h+var_48]
0x18000ef80  mov     rcx, rdi
0x18000ef83  call    RtlXmlDetermineStreamEncoding
0x18000ef88  mov     ebx, eax
0x18000ef8a  test    eax, eax
0x18000ef8c  js      loc_18000ED4C
0x18000ef92  mov     rax, [rsp+0F8h+var_48]
0x18000ef9a  add     [rdi+20h], rax
0x18000ef9e  mov     r9, r14; struct _RTL_ALLOCATOR *
0x18000efa1  mov     byte ptr [rdi+8B0h], 1
0x18000efa8  mov     r8, rdi; void *
0x18000efab  lea     rcx, [rdi+8B8h]; this
0x18000efb2  call    ?Initialize@CXmlNamespaceManager@@QEAAJP6AJPEAXPEBU_XML_EXTENT@@1PEAW4XML_STRING_COMPARE@@@Z0PEAU_RTL_ALLOCATOR@@@Z; CXmlNamespaceManager::Initialize(long (*)(void *,_XML_EXTENT const *,_XML_EXTENT const *,XML_STRING_COMPARE *),void *,_RTL_ALLOCATOR *)
0x18000efb7  mov     ebx, eax
0x18000efb9  test    eax, eax
0x18000efbb  js      loc_18000ED8D
0x18000efc1  mov     rdx, r14
0x18000efc4  lea     rcx, [rdi+0D80h]
0x18000efcb  call    ?Initialize@?$CRtlGrowingList@U_XMLDOC_ATTRIBUTE@@$0DC@$03@@QEAAJPEAU_RTL_ALLOCATOR@@@Z; CRtlGrowingList<_XMLDOC_ATTRIBUTE,50,4>::Initialize(_RTL_ALLOCATOR *)
0x18000efd0  mov     ebx, eax
0x18000efd2  test    eax, eax
0x18000efd4  jns     loc_18000EDC4
0x18000efda  jmp     loc_18000ED8D
0x18000efdf  lea     rcx, aRtlxmlnextlogi_0; "RtlXmlNextLogicalThingEx( &m_State, &m_"...
0x18000efe6  mov     [rsp+0F8h+var_C8], r12
0x18000efeb  mov     [rsp+0F8h+var_B0], rcx
0x18000eff0  lea     rdx, [rsp+0F8h+var_C8]
0x18000eff5  lea     rcx, [rsp+0F8h+var_48]
0x18000effd  mov     [rsp+0F8h+var_C0], r13
0x18000f002  mov     r8d, eax
0x18000f005  mov     [rsp+0F8h+var_B8], 40h ; '@'
0x18000f00e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18000f013  test    eax, eax
0x18000f015  js      loc_18000ED93
0x18000f01b  jmp     loc_18000EE5F
0x18000f020  cmp     eax, 0Dh; switch 14 cases
0x18000f023  ja      def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f029  mov     ecx, ds:(jpt_18000F034 - 180000000h)[r14+rax*4]
0x18000f031  add     rcx, r14
0x18000f034  jmp     rcx; switch jump
0x18000f03a  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 4
0x18000f041  call    ?EndElement@CMicrodomBuilder@@AEAAJXZ; CMicrodomBuilder::EndElement(void)
0x18000f046  test    eax, eax
0x18000f048  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f04e  jmp     loc_18000ED93
0x18000f053  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 8
0x18000f05a  mov     rdx, rdi; struct CXmlCursor *
0x18000f05d  call    ?ConsumeCData@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::ConsumeCData(CXmlCursor *)
0x18000f062  test    eax, eax
0x18000f064  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f06a  jmp     loc_18000ED93
0x18000f06f  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 9
0x18000f076  mov     rdx, rdi; struct CXmlCursor *
0x18000f079  call    ?ConsumeEntityDecl@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::ConsumeEntityDecl(CXmlCursor *)
0x18000f07e  test    eax, eax
0x18000f080  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f086  jmp     loc_18000ED93
0x18000f08b  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 10
0x18000f092  mov     rdx, rdi; struct CXmlCursor *
0x18000f095  call    ?StartAttlist@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::StartAttlist(CXmlCursor *)
0x18000f09a  test    eax, eax
0x18000f09c  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f0a2  jmp     loc_18000ED93
0x18000f0a7  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 11
0x18000f0ae  mov     rdx, rdi; struct CXmlCursor *
0x18000f0b1  call    ?ConsumeAttdef@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::ConsumeAttdef(CXmlCursor *)
0x18000f0b6  test    eax, eax
0x18000f0b8  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f0be  jmp     loc_18000ED93
0x18000f0c3  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 12
0x18000f0ca  mov     rdx, rdi; struct CXmlCursor *
0x18000f0cd  call    ?EndAttlist@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::EndAttlist(CXmlCursor *)
0x18000f0d2  test    eax, eax
0x18000f0d4  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f0da  jmp     loc_18000ED93
0x18000f0df  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 5
0x18000f0e6  mov     rdx, rdi; struct CXmlCursor *
0x18000f0e9  call    ?ConsumeProcessingInstruction@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::ConsumeProcessingInstruction(CXmlCursor *)
0x18000f0ee  test    eax, eax
0x18000f0f0  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f0f6  jmp     loc_18000ED93
0x18000f0fb  mov     rcx, [rdi+24A8h]; jumptable 000000018000F034 case 13
0x18000f102  mov     rdx, rdi; struct CXmlCursor *
0x18000f105  call    ?ConsumeComment@CMicrodomBuilder@@AEAAJPEAVCXmlCursor@@@Z; CMicrodomBuilder::ConsumeComment(CXmlCursor *)
0x18000f10a  test    eax, eax
0x18000f10c  jns     def_18000F034; jumptable 000000018000F034 default case, cases 1-3,6,7
0x18000f112  jmp     loc_18000ED93
0x18000f117  mov     rdx, rdi; jumptable 000000018000F034 case 0
0x18000f11a  mov     rcx, rdi; this
0x18000f11d  call    ?XmlError@CMicrodomXmlWalker@@QEAAJPEAVCXmlCursor@@@Z; CMicrodomXmlWalker::XmlError(CXmlCursor *)
0x18000f122  test    eax, eax
0x18000f124  js      loc_18000ED93
0x18000f12a  jmp     loc_18000ED91
```
