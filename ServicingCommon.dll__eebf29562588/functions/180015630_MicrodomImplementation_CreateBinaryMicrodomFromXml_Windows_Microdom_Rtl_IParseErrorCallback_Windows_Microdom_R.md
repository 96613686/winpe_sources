# MicrodomImplementation::CreateBinaryMicrodomFromXml(Windows::Microdom::Rtl::IParseErrorCallback *,Windows::Microdom::Rtl::IEntityResolver *,_LBLOB const *,Windows::Auto<_LBLOB> *)

- ea: `0x180015630`
- end: `0x180015bf2`
- name: `?CreateBinaryMicrodomFromXml@MicrodomImplementation@@YAJPEAUIParseErrorCallback@Rtl@Microdom@Windows@@PEAUIEntityResolver@345@PEBU_LBLOB@@PEAV?$Auto@U_LBLOB@@@5@@Z`
- size: `1474`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058630`

## callees

- `0x180002034`
- `0x180002084`
- `0x1800031e0`
- `0x1800033e0`
- `0x180003550`
- `0x18000a8d0`
- `0x1800152ec`
- `0x180015630`
- `0x180017380`
- `0x18001e850`
- `0x18001eb80`
- `0x18001fcf4`
- `0x18001fd10`
- `0x18001fdbc`
- `0x180022eb0`
- `0x180022f08`
- `0x1800293a0`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180015984`
- `ntdll!RtlRaiseStatus` at `0x1800159dd`
- `ntdll!RtlRaiseStatus` at `0x180015984`
- `ntdll!RtlRaiseStatus` at `0x1800159dd`

## string_xrefs

- `0x180015a12`: `onecore\base\xml\udom_xmlwalker.h`
- `0x180015a2c`: `CXmlLogicalState::{dtor}::<lambda_06baf61e643ec405d0310e05aef13cd9>::operator ()`
- `0x180015a3d`: `RtlXmlDestroyNextLogicalThing(this)`
- `0x180015ad9`: `onecore\base\xml\udom_builder.cpp`
- `0x180015b33`: `onecore\base\xml\udom_builder.cpp`
- `0x180015b8a`: `onecore\base\xml\udom_builder.cpp`
- `0x180015b4d`: `MicrodomImplementation::CreateBinaryMicrodomFromXml`
- `0x180015ba4`: `MicrodomImplementation::CreateBinaryMicrodomFromXml`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CreateBinaryMicrodomFromXml(
        void (__fastcall ***a1)(_QWORD, _QWORD, _QWORD, _QWORD, int, __int128 *),
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rbx
  __int64 v10; // rsi
  signed int v11; // ebx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  void (__fastcall *v15)(_QWORD, _QWORD, _QWORD, _QWORD, int, __int128 *); // rax
  __int128 v16; // xmm2
  __int64 v17; // xmm3_8
  __int64 v18; // xmm1_8
  NTSTATUS v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // r8d
  void *v22; // r9
  NTSTATUS v23; // ebx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  int NtStatus; // eax
  int v35; // [rsp+40h] [rbp-29h] BYREF
  __int128 v36; // [rsp+48h] [rbp-21h] BYREF
  __int64 v37; // [rsp+58h] [rbp-11h]
  const char *v38; // [rsp+60h] [rbp-9h]
  __int128 v39; // [rsp+68h] [rbp-1h] BYREF
  __int64 v40; // [rsp+78h] [rbp+Fh]

  v40 = 0;
  v39 = 0;
  if ( a3 && (a3[2] || !*a3) && *a3 <= (unsigned __int64)a3[1] )
  {
    v7 = operator new(0x2B08u);
    v8 = v7;
    if ( v7 )
    {
      v9 = v7 + 7;
      v10 = 37;
      *(_DWORD *)v7 = 0;
      v7[3] = 0;
      v7[5] = 0;
      v7[2] = v7 + 7;
      v7[4] = 37;
      v7[6] = 185;
      do
      {
        BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v9);
        v9 += 4;
        --v10;
      }
      while ( v10 );
      v8[156] = 0;
      v8[157] = 0;
      v8[161] = 0;
      v8[158] = v8 + 158;
      v8[159] = v8 + 158;
      v8[160] = v8 + 158;
      v8[162] = 0;
      v8[164] = v8 + 169;
      v8[165] = 0;
      v8[166] = 7;
      v8[167] = 0;
      v8[168] = 35;
      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v8 + 169);
      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v8 + 173);
      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v8 + 177);
      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v8 + 181);
      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v8 + 185);
      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v8 + 189);
      BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(v8 + 193);
      *((_OWORD *)v8 + 99) = 0;
      v8[200] = 0;
      *((_BYTE *)v8 + 3832) = 0;
      memset(v8 + 201, 0, 0x8B0u);
      *((_BYTE *)v8 + 5056) = 0;
      memset(v8 + 480, 0, 0x4C0u);
      *(_OWORD *)(v8 + 633) = 0;
      *(_OWORD *)(v8 + 635) = 0;
      *(_OWORD *)(v8 + 637) = 0;
      *(_OWORD *)(v8 + 639) = 0;
      v8[641] = 0;
      *((_BYTE *)v8 + 10984) = 0;
      v8[1370] = CXmlCursor::XmlAlloc;
      v8[1371] = CXmlCursor::XmlFree;
      v8[1372] = 0;
      v8[1374] = v8;
      *((_BYTE *)v8 + 11000) = 0;
      v8[1376] = 0;
      if ( (_QWORD *)v8[164] != v8 + 169 )
      {
        __debugbreak();
        v11 = -1073741595;
        goto LABEL_42;
      }
      v12 = v8[166];
      v13 = HIDWORD(v12);
      if ( HIDWORD(v12) )
      {
        if ( ((5 * v13) & 0xFFFFFFFF00000000uLL) != 0 )
        {
          v11 = -1073741675;
          v8[168] = -1;
          goto LABEL_42;
        }
        v14 = 5LL * (unsigned int)v12;
        v8[168] = 0x500000000LL * v13 + v14;
        v11 = 0x500000000LL * v13 + v14 < v14 ? 0xC0000095 : 0;
        if ( 0x500000000LL * v13 + v14 < v14 )
        {
LABEL_42:
          v37 = 757;
          *(_QWORD *)&v36 = "onecore\\base\\xml\\udom_builder.cpp";
          *((_QWORD *)&v36 + 1) = "CMicrodomBuilder::Initialize";
          v38 = "m_AttdefListTable.Initialize()";
          RtlReportErrorOrigination(&v36, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v11);
          goto LABEL_43;
        }
      }
      else
      {
        v8[168] = 5LL * (unsigned int)v12;
      }
      v8[1376] = a1;
      v11 = CBaseXmlWalker<CMicrodomXmlWalker>::WalkDocument((struct CXmlCursor *)(v8 + 201), a3[2], *a3);
      if ( v11 >= 0 )
      {
        if ( !*((_BYTE *)v8 + 11000) )
        {
          if ( a1 )
          {
            v37 = 0;
            v15 = **a1;
            v36 = 0;
            v15(a1, 0, 0, 0, -1073741811, &v36);
          }
          goto LABEL_19;
        }
        v11 = CMicrodomBuilder::ConstructAndWriteMicrodom((CMicrodomBuilder *)v8, 0, &v39);
        if ( v11 >= 0 )
        {
LABEL_19:
          v16 = *(_OWORD *)a4;
          v17 = *(_QWORD *)(a4 + 16);
          v18 = v40;
          *(_OWORD *)a4 = v39;
          *(_QWORD *)(a4 + 16) = v18;
          v39 = v16;
          v40 = v17;
          v19 = RtlDestroyGrowingList(v8 + 633);
          if ( v19 < 0 )
            RtlRaiseStatus(v19);
          if ( *((_BYTE *)v8 + 5056) )
          {
            if ( v8 == (_QWORD *)-3840LL )
            {
              v23 = RtlXmlReportErrorFunction(-1073741811, v20, v21, v22);
            }
            else
            {
              v23 = 0;
              v24 = RtlDestroyGrowingList(v8 + 481);
              if ( v24 < 0 )
                v23 = v24;
              v25 = RtlDestroyGrowingList(v8 + 491);
              if ( v25 < 0 && !v23 )
                v23 = v25;
            }
            if ( v23 < 0 )
              RtlRaiseStatus(v23);
            *((_BYTE *)v8 + 5056) = 0;
          }
          v35 = 0;
          if ( *((_BYTE *)v8 + 3832) )
          {
            v26 = RtlDestroyGrowingList(v8 + 246);
            if ( v26 >= 0 )
            {
              *((_BYTE *)v8 + 3832) = 0;
              if ( v35 < 0 )
              {
                NtStatus = Windows::ErrorHandling::Rtl::CBaseNtStatusCarryingFrame<Windows::ErrorHandling::Rtl::CVoidRaiseFrame,void>::GetNtStatus(&v35);
                INTERNAL_ERROR_ACTION(NtStatus);
                JUMPOUT(0x180015BF1LL);
              }
            }
            else
            {
              v37 = 160;
              *(_QWORD *)&v36 = "onecore\\base\\xml\\udom_xmlwalker.h";
              v35 = v26;
              *((_QWORD *)&v36 + 1) = "CXmlLogicalState::{dtor}::<lambda_06baf61e643ec405d0310e05aef13cd9>::operator ()";
              v38 = "RtlXmlDestroyNextLogicalThing(this)";
              RtlReportErrorOrigination(&v36, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v26);
              Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn((Windows::ErrorHandling::Rtl::CVoidRaiseFrame *)&v35);
            }
          }
          CMicrodomBuilder::~CMicrodomBuilder((CMicrodomBuilder *)v8);
          operator delete(v8);
          if ( v40 )
            anonymous_namespace_::OurRtlFreeStringRoutine(v40, v27, v28);
          return 0;
        }
      }
LABEL_43:
      Windows::AutoNewPtr<MicrodomImplementation::CMicrodomCreationLocals>::DeleteInstance(v8);
      if ( v40 )
        RtlFreeLUtf8String(&v39);
      return (unsigned int)v11;
    }
    v37 = 3198;
    *(_QWORD *)&v36 = "onecore\\base\\xml\\udom_builder.cpp";
    *((_QWORD *)&v36 + 1) = "MicrodomImplementation::CreateBinaryMicrodomFromXml";
    v38 = "Locals.Allocate()";
    RtlReportErrorOrigination(&v36, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
    if ( v40 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v40, v30, v31);
    return 3221225495LL;
  }
  else
  {
    v37 = 3196;
    *(_QWORD *)&v36 = "onecore\\base\\xml\\udom_builder.cpp";
    *((_QWORD *)&v36 + 1) = "MicrodomImplementation::CreateBinaryMicrodomFromXml";
    v38 = "RtlIsLBlobValid(BinaryData)";
    RtlReportErrorOrigination(&v36, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    if ( v40 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v40, v32, v33);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180015630  push    rbp
0x180015632  push    r12
0x180015634  push    r14
0x180015636  push    r15
0x180015638  lea     rbp, [rsp-3Fh]
0x18001563d  sub     rsp, 0A8h
0x180015644  mov     rax, cs:__security_cookie
0x18001564b  xor     rax, rsp
0x18001564e  mov     [rbp+57h+var_40], rax
0x180015652  xor     eax, eax
0x180015654  xorps   xmm0, xmm0
0x180015657  mov     [rbp+57h+var_48], rax
0x18001565b  mov     r12, r9
0x18001565e  mov     r14, r8
0x180015661  mov     r15, rcx
0x180015664  movups  [rbp+57h+var_58], xmm0
0x180015668  test    r8, r8
0x18001566b  jz      loc_180015B8A
0x180015671  cmp     [r8+10h], rax
0x180015675  jnz     short loc_180015680
0x180015677  cmp     [r8], rax
0x18001567a  jnz     loc_180015B8A
0x180015680  mov     rax, [r8+8]
0x180015684  cmp     [r8], rax
0x180015687  ja      loc_180015B8A
0x18001568d  mov     ecx, 2B08h; Size
0x180015692  mov     [rsp+0C0h+var_28], rdi
0x18001569a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001569f  mov     rdi, rax
0x1800156a2  test    rax, rax
0x1800156a5  jz      loc_180015B33
0x1800156ab  mov     [rsp+0C0h+arg_8], rbx
0x1800156b3  lea     rbx, [rax+38h]
0x1800156b7  mov     [rsp+0C0h+var_20], rsi
0x1800156bf  mov     esi, 25h ; '%'
0x1800156c4  mov     [rsp+0C0h+var_30], r13
0x1800156cc  xor     r13d, r13d
0x1800156cf  mov     [rax], r13d
0x1800156d2  mov     [rax+18h], r13
0x1800156d6  mov     [rax+28h], r13
0x1800156da  mov     [rax+10h], rbx
0x1800156de  mov     [rax+20h], rsi
0x1800156e2  mov     qword ptr [rax+30h], 0B9h
0x1800156ea  nop     word ptr [rax+rax+00h]
0x1800156f0  mov     rcx, rbx; void *
0x1800156f3  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800156f8  add     rbx, 20h ; ' '
0x1800156fc  sub     rsi, 1
0x180015700  jnz     short loc_1800156F0
0x180015702  lea     rax, [rdi+4F0h]
0x180015709  mov     [rdi+4E0h], r13
0x180015710  lea     rbx, [rdi+548h]
0x180015717  mov     [rdi+4E8h], r13
0x18001571e  mov     rcx, rbx; void *
0x180015721  mov     [rax+18h], r13
0x180015725  mov     [rax], rax
0x180015728  mov     [rax+8], rax
0x18001572c  mov     [rax+10h], rax
0x180015730  mov     [rdi+510h], r13
0x180015737  mov     [rdi+520h], rbx
0x18001573e  mov     [rdi+528h], r13
0x180015745  mov     qword ptr [rdi+530h], 7
0x180015750  mov     [rdi+538h], r13
0x180015757  mov     qword ptr [rdi+540h], 23h ; '#'
0x180015762  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180015767  lea     rcx, [rbx+20h]; void *
0x18001576b  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180015770  lea     rcx, [rbx+40h]; void *
0x180015774  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180015779  lea     rcx, [rbx+60h]; void *
0x18001577d  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x180015782  lea     rcx, [rbx+80h]; void *
0x180015789  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x18001578e  lea     rcx, [rbx+0A0h]; void *
0x180015795  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x18001579a  lea     rcx, [rbx+0C0h]; void *
0x1800157a1  call    ??0CBucketChain@?$CTable@VCPrefixTableTraits@MicrodomWriterImplementation@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<MicrodomWriterImplementation::CPrefixTableTraits>::CBucketChain::CBucketChain(void)
0x1800157a6  xor     eax, eax
0x1800157a8  lea     rsi, [rdi+648h]
0x1800157af  xorps   xmm0, xmm0
0x1800157b2  xor     edx, edx; Val
0x1800157b4  movups  xmmword ptr [rdi+630h], xmm0
0x1800157bb  mov     [rdi+640h], rax
0x1800157c2  mov     r8d, 8B0h; Size
0x1800157c8  mov     rcx, rsi; void *
0x1800157cb  mov     [rsi+8B0h], al
0x1800157d1  call    memset
0x1800157d6  lea     rcx, [rsi+8B8h]; void *
0x1800157dd  xor     edx, edx; Val
0x1800157df  mov     r8d, 4C0h; Size
0x1800157e5  mov     [rcx+4C0h], r13b
0x1800157ec  call    memset
0x1800157f1  xor     eax, eax
0x1800157f3  xorps   xmm0, xmm0
0x1800157f6  movups  xmmword ptr [rsi+0D80h], xmm0
0x1800157fd  movups  xmmword ptr [rsi+0D90h], xmm0
0x180015804  movups  xmmword ptr [rsi+0DA0h], xmm0
0x18001580b  movups  xmmword ptr [rsi+0DB0h], xmm0
0x180015812  mov     [rsi+0DC0h], rax
0x180015819  mov     [rsi+24A0h], al
0x18001581f  lea     rax, ?XmlAlloc@CXmlCursor@@KAJ_KPEAPEAXPEAX@Z; CXmlCursor::XmlAlloc(unsigned __int64,void * *,void *)
0x180015826  mov     [rsi+2488h], rax
0x18001582d  lea     rax, ?XmlFree@CXmlCursor@@KAJPEAX0@Z; CXmlCursor::XmlFree(void *,void *)
0x180015834  mov     [rsi+2490h], rax
0x18001583b  mov     [rsi+2498h], r13
0x180015842  mov     [rsi+24A8h], rdi
0x180015849  mov     [rsi+24B0h], r13b
0x180015850  mov     [rsi+24B8h], r13
0x180015857  cmp     [rdi+520h], rbx
0x18001585e  jz      short loc_18001586B
0x180015860  int     3; Trap to Debugger
0x180015861  mov     ebx, 0C00000E5h
0x180015866  jmp     loc_180015AD9
0x18001586b  mov     rcx, [rdi+530h]
0x180015872  mov     rax, rcx
0x180015875  shr     rax, 20h
0x180015879  test    eax, eax
0x18001587b  jnz     short loc_18001588C
0x18001587d  mov     eax, ecx
0x18001587f  lea     rcx, [rax+rax*4]
0x180015883  mov     [rdi+540h], rcx
0x18001588a  jmp     short loc_1800158CC
0x18001588c  lea     rdx, [rax+rax*4]
0x180015890  mov     rax, 0FFFFFFFF00000000h
0x18001589a  test    rax, rdx
0x18001589d  jnz     loc_180015AC9
0x1800158a3  shl     rdx, 20h
0x1800158a7  mov     eax, ecx
0x1800158a9  lea     rcx, [rax+rax*4]
0x1800158ad  lea     rax, [rdx+rcx]
0x1800158b1  cmp     rax, rcx
0x1800158b4  mov     [rdi+540h], rax
0x1800158bb  sbb     ebx, ebx
0x1800158bd  and     ebx, 0C0000095h
0x1800158c3  cmp     rax, rcx
0x1800158c6  jb      loc_180015AD9
0x1800158cc  mov     [rsi+24B8h], r15
0x1800158d3  mov     rcx, rsi; struct CXmlCursor *
0x1800158d6  mov     r8, [r14]
0x1800158d9  mov     rdx, [r14+10h]
0x1800158dd  call    ?WalkDocument@?$CBaseXmlWalker@VCMicrodomXmlWalker@@@@QEAAJPEAX_K@Z; CBaseXmlWalker<CMicrodomXmlWalker>::WalkDocument(void *,unsigned __int64)
0x1800158e2  mov     ebx, eax
0x1800158e4  test    eax, eax
0x1800158e6  js      loc_180015B15
0x1800158ec  cmp     [rdi+2AF8h], r13b
0x1800158f3  jnz     short loc_180015930
0x1800158f5  test    r15, r15
0x1800158f8  jz      short loc_180015948
0x1800158fa  xor     eax, eax
0x1800158fc  lea     rcx, [rbp+57h+var_78]
0x180015900  mov     [rbp+57h+var_68], rax
0x180015904  xorps   xmm0, xmm0
0x180015907  mov     rax, [r15]
0x18001590a  xor     r9d, r9d
0x18001590d  mov     [rsp+0C0h+var_98], rcx
0x180015912  xor     r8d, r8d
0x180015915  xor     edx, edx
0x180015917  mov     [rsp+0C0h+var_A0], 0C000000Dh
0x18001591f  mov     rcx, r15
0x180015922  mov     rax, [rax]
0x180015925  movups  [rbp+57h+var_78], xmm0
0x180015929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001592e  jmp     short loc_180015948
0x180015930  lea     r8, [rbp+57h+var_58]
0x180015934  xor     edx, edx
0x180015936  mov     rcx, rdi; this
0x180015939  call    ?ConstructAndWriteMicrodom@CMicrodomBuilder@@QEAAJKPEAV?$Auto@U_LBLOB@@@Windows@@@Z; CMicrodomBuilder::ConstructAndWriteMicrodom(ulong,Windows::Auto<_LBLOB> *)
0x18001593e  mov     ebx, eax
0x180015940  test    eax, eax
0x180015942  js      loc_180015B15
0x180015948  movups  xmm2, xmmword ptr [r12]
0x18001594d  lea     rcx, [rdi+13C8h]
0x180015954  movsd   xmm3, qword ptr [r12+10h]
0x18001595b  movups  xmm0, [rbp+57h+var_58]
0x18001595f  movsd   xmm1, [rbp+57h+var_48]
0x180015964  movups  xmmword ptr [r12], xmm0
0x180015969  movsd   qword ptr [r12+10h], xmm1
0x180015970  movups  [rbp+57h+var_58], xmm2
0x180015974  movsd   [rbp+57h+var_48], xmm3
0x180015979  call    RtlDestroyGrowingList
0x18001597e  test    eax, eax
0x180015980  jns     short loc_180015991
0x180015982  mov     ecx, eax; Status
0x180015984  call    cs:__imp_RtlRaiseStatus
0x18001598b  nop     dword ptr [rax+rax+00h]
0x180015990  int     3; Trap to Debugger
0x180015991  cmp     [rdi+13C0h], r13b
0x180015998  lea     rsi, [rdi+0F00h]
0x18001599f  jz      short loc_1800159F1
0x1800159a1  test    rsi, rsi
0x1800159a4  jnz     short loc_1800159B4
0x1800159a6  mov     ecx, 0C000000Dh; int
0x1800159ab  call    ?RtlXmlReportErrorFunction@@YAJJKKPEAX@Z; RtlXmlReportErrorFunction(long,ulong,ulong,void *)
0x1800159b0  mov     ebx, eax
0x1800159b2  jmp     short loc_1800159D7
0x1800159b4  lea     rcx, [rsi+8]
0x1800159b8  mov     ebx, r13d
0x1800159bb  call    RtlDestroyGrowingList
0x1800159c0  test    eax, eax
0x1800159c2  lea     rcx, [rsi+58h]
0x1800159c6  cmovs   ebx, eax
0x1800159c9  call    RtlDestroyGrowingList
0x1800159ce  test    eax, eax
0x1800159d0  jns     short loc_1800159D7
0x1800159d2  test    ebx, ebx
0x1800159d4  cmovz   ebx, eax
0x1800159d7  test    ebx, ebx
0x1800159d9  jns     short loc_1800159EA
0x1800159db  mov     ecx, ebx; Status
0x1800159dd  call    cs:__imp_RtlRaiseStatus
0x1800159e4  nop     dword ptr [rax+rax+00h]
0x1800159e9  int     3; Trap to Debugger
0x1800159ea  mov     [rsi+4C0h], r13b
0x1800159f1  mov     [rbp+57h+var_80], r13d
0x1800159f5  cmp     [rdi+0EF8h], r13b
0x1800159fc  jz      short loc_180015A5A
0x1800159fe  lea     rcx, [rdi+7B0h]
0x180015a05  call    RtlDestroyGrowingList
0x180015a0a  test    eax, eax
0x180015a0c  jns     loc_180015AB6
0x180015a12  lea     rcx, aOnecoreBaseXml_2; "onecore\\base\\xml\\udom_xmlwalker.h"
0x180015a19  mov     [rbp+57h+var_68], 0A0h
0x180015a21  mov     qword ptr [rbp+57h+var_78], rcx
0x180015a25  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180015a2c  lea     rcx, aCxmllogicalsta_0; "CXmlLogicalState::{dtor}::<lambda_06baf"...
0x180015a33  mov     [rbp+57h+var_80], eax
0x180015a36  mov     qword ptr [rbp+57h+var_78+8], rcx
0x180015a3a  mov     r8d, eax
0x180015a3d  lea     rcx, aRtlxmldestroyn_0; "RtlXmlDestroyNextLogicalThing(this)"
0x180015a44  mov     [rbp+57h+var_60], rcx
0x180015a48  lea     rcx, [rbp+57h+var_78]
0x180015a4c  call    RtlReportErrorOrigination
0x180015a51  lea     rcx, [rbp+57h+var_80]; this
0x180015a55  call    ?ExitReturn@CVoidRaiseFrame@Rtl@ErrorHandling@Windows@@QEBAXXZ; Windows::ErrorHandling::Rtl::CVoidRaiseFrame::ExitReturn(void)
0x180015a5a  mov     rcx, rdi; this
0x180015a5d  call    ??1CMicrodomBuilder@@QEAA@XZ; CMicrodomBuilder::~CMicrodomBuilder(void)
0x180015a62  mov     rcx, rdi; Block
0x180015a65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015a6a  mov     rcx, [rbp+57h+var_48]
0x180015a6e  test    rcx, rcx
0x180015a71  jz      short loc_180015A78
0x180015a73  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180015a78  xor     eax, eax
0x180015a7a  mov     rbx, [rsp+0C0h+arg_8]
0x180015a82  mov     rsi, [rsp+0C0h+var_20]
0x180015a8a  mov     r13, [rsp+0C0h+var_30]
0x180015a92  mov     rdi, [rsp+0C0h+var_28]
0x180015a9a  mov     rcx, [rbp+57h+var_40]
0x180015a9e  xor     rcx, rsp; StackCookie
0x180015aa1  call    __security_check_cookie
0x180015aa6  add     rsp, 0A8h
0x180015aad  pop     r15
0x180015aaf  pop     r14
0x180015ab1  pop     r12
0x180015ab3  pop     rbp
0x180015ab4  retn
0x180015ab6  mov     [rdi+0EF8h], r13b
0x180015abd  cmp     [rbp+57h+var_80], r13d
0x180015ac1  jl      loc_180015BE1
0x180015ac7  jmp     short loc_180015A5A
0x180015ac9  mov     ebx, 0C0000095h
0x180015ace  mov     qword ptr [rdi+540h], 0FFFFFFFFFFFFFFFFh
0x180015ad9  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015ae0  mov     [rbp+57h+var_68], 2F5h
0x180015ae8  mov     qword ptr [rbp+57h+var_78], rax
0x180015aec  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180015af3  lea     rax, aCmicrodombuild_14; "CMicrodomBuilder::Initialize"
0x180015afa  mov     r8d, ebx
0x180015afd  mov     qword ptr [rbp+57h+var_78+8], rax
0x180015b01  lea     rcx, [rbp+57h+var_78]
0x180015b05  lea     rax, aMAttdeflisttab; "m_AttdefListTable.Initialize()"
0x180015b0c  mov     [rbp+57h+var_60], rax
0x180015b10  call    RtlReportErrorOrigination
0x180015b15  mov     rcx, rdi; Block
0x180015b18  call    ?DeleteInstance@?$AutoNewPtr@VCMicrodomCreationLocals@MicrodomImplementation@@@Windows@@SAXPEAVCMicrodomCreationLocals@MicrodomImplementation@@@Z; Windows::AutoNewPtr<MicrodomImplementation::CMicrodomCreationLocals>::DeleteInstance(MicrodomImplementation::CMicrodomCreationLocals *)
0x180015b1d  cmp     [rbp+57h+var_48], r13
0x180015b21  jz      short loc_180015B2C
0x180015b23  lea     rcx, [rbp+57h+var_58]
0x180015b27  call    RtlFreeLUtf8String
0x180015b2c  mov     eax, ebx
0x180015b2e  jmp     loc_180015A7A
0x180015b33  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015b3a  mov     [rbp+57h+var_68], 0C7Eh
0x180015b42  mov     qword ptr [rbp+57h+var_78], rax
0x180015b46  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180015b4d  lea     rax, aMicrodomimplem_22; "MicrodomImplementation::CreateBinaryMic"...
0x180015b54  mov     r8d, 0C0000017h
0x180015b5a  mov     qword ptr [rbp+57h+var_78+8], rax
0x180015b5e  lea     rcx, [rbp+57h+var_78]
0x180015b62  lea     rax, aLocalsAllocate; "Locals.Allocate()"
0x180015b69  mov     [rbp+57h+var_60], rax
0x180015b6d  call    RtlReportErrorOrigination
0x180015b72  mov     rcx, [rbp+57h+var_48]
0x180015b76  test    rcx, rcx
0x180015b79  jz      short loc_180015B80
0x180015b7b  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180015b80  mov     eax, 0C0000017h
0x180015b85  jmp     loc_180015A92
0x180015b8a  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015b91  mov     [rbp+57h+var_68], 0C7Ch
  ... truncated ...
```
