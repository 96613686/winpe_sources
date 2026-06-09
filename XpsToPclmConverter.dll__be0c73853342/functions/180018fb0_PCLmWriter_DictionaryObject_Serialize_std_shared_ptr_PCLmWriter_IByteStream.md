# PCLmWriter::DictionaryObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x180018fb0`
- end: `0x18001948f`
- name: `?Serialize@DictionaryObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `1247`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1800199e0`

## callees

- `0x1800015f0`
- `0x180001614`
- `0x180002154`
- `0x18000e7c8`
- `0x18000f3e0`
- `0x1800101cc`
- `0x1800105f4`
- `0x180010618`
- `0x180010718`
- `0x1800113c4`
- `0x180011600`
- `0x180013068`
- `0x18001496c`
- `0x1800185b0`
- `0x18001883c`
- `0x1800189c4`
- `0x180018b8c`
- `0x180018fb0`
- `0x1800196c0`
- `0x180019db0`
- `0x18001a0e8`
- `0x18001cc44`
- `0x18001f010`

## string_xrefs

- `0x180019089`: `/BitsPerComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall PCLmWriter::DictionaryObject::Serialize(_QWORD *a1, _QWORD *a2)
{
  std::_Ref_count_base **v4; // rbx
  std::_Ref_count_base *v5; // rax
  std::_Ref_count_base *v6; // rcx
  _BYTE *v7; // r8
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r9
  _BYTE *v13; // r8
  std::_Ref_count_base *v14; // rcx
  std::_Ref_count_base ***v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  void (__fastcall *v19)(__int64, __int64); // r8
  __int64 v20; // r9
  _QWORD *v21; // rax
  __int64 i; // rcx
  std::_Ref_count_base **v23; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-B0h]
  std::_Ref_count_base *v27[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v28; // [rsp+68h] [rbp-98h]
  char v29[8]; // [rsp+70h] [rbp-90h] BYREF
  char v30[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v31[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v32[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-48h]
  _BYTE v34[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v36[32]; // [rsp+140h] [rbp+40h] BYREF
  char v37[32]; // [rsp+160h] [rbp+60h] BYREF
  char v38[32]; // [rsp+180h] [rbp+80h] BYREF
  char v39[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v40[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v41[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v42[32]; // [rsp+200h] [rbp+100h] BYREF
  char v43[32]; // [rsp+220h] [rbp+120h] BYREF
  char v44[32]; // [rsp+240h] [rbp+140h] BYREF
  char v45[32]; // [rsp+260h] [rbp+160h] BYREF
  char v46[32]; // [rsp+280h] [rbp+180h] BYREF
  char v47[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v48[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _DWORD v49[2]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v28 = a2;
  qmemcpy(v49, "<<\n>> ", 6);
  std::string::string(v41, "/Width");
  std::string::string(v42, "/ColorSpace");
  std::string::string(v43, "/Height");
  std::string::string(v44, "/Filter");
  std::string::string(v45, "/Subtype");
  std::string::string(v46, "/Length");
  std::string::string(v47, "/Type");
  std::string::string(v48, "/BitsPerComponent");
  std::string::string(v36, "/Type");
  std::string::string(v37, "/Parent");
  std::string::string(v38, "/Resources");
  std::string::string(v39, "/MediaBox");
  std::string::string(v40, "/Contents");
  (*(void (__fastcall **)(_QWORD, _DWORD *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, v49, 2);
  std::string::string(v31, "/Type");
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::find(
    a1 + 3,
    &v23,
    v31);
  std::string::_Tidy_deallocate(v31);
  std::string::string(v32);
  *(_OWORD *)v27 = 0;
  v4 = v23;
  if ( v23 != (std::_Ref_count_base **)a1[3] )
  {
    v5 = (std::_Ref_count_base *)_RTDynamicCast_0(
                                   v23[8],
                                   0,
                                   &PCLmWriter::IObject `RTTI Type Descriptor',
                                   &PCLmWriter::INameObject `RTTI Type Descriptor',
                                   0);
    if ( v5 )
    {
      v6 = v4[9];
      if ( v6 )
        _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
      v24[0] = v5;
      v24[1] = v4[9];
    }
    else
    {
      *(_OWORD *)v24 = 0;
    }
    std::shared_ptr<PCLmWriter::IByteStream>::operator=(v27, v24);
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
    v7 = (_BYTE *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v27[0] + 40LL))(v27[0]);
    if ( v32 != v7 )
    {
      v8 = std::_String_val<std::_Simple_types<char>>::_Myptr(v7);
      std::string::assign(v32, v8, *(_QWORD *)(v9 + 16));
    }
  }
  v10 = std::_String_val<std::_Simple_types<char>>::_Myptr(v32);
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v10, v33, "/XObject", 8) )
  {
    v11 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v25, a2);
    v12 = 8;
    v13 = v41;
LABEL_15:
    PCLmWriter::DictionaryObject::SerializeInOrder(a1, v11, v13, v12);
    goto LABEL_16;
  }
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v10, v33, "/Page", 5) )
  {
    v11 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v25, a2);
    v12 = 5;
    v13 = v36;
    goto LABEL_15;
  }
  (*(void (__fastcall **)(_QWORD *, std::_Ref_count_base ***))(*a1 + 56LL))(a1, &v23);
  while ( 1 )
  {
    v15 = (std::_Ref_count_base ***)(*(__int64 (__fastcall **)(_QWORD *, char *))(*a1 + 64LL))(a1, v29);
    if ( v23 == *v15 )
      break;
    (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, (char *)v49 + 2, 1);
    PCLmWriter::NameObject::NameObject(v34, v23 + 4, 0, 0);
    v16 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v30, a2);
    PCLmWriter::NameObject::Serialize(v34, v16);
    (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, (char *)&v49[1] + 1, 1);
    std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v25, v23 + 8);
    if ( !v25 )
    {
      std::operator+<char>(v31, v17, v23 + 4);
      PCLmWriter::Exception::Exception((std::exception *)pExceptionObject);
      throw (PCLmWriter::Exception *)pExceptionObject;
    }
    v18 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v31, a2);
    v19(v20, v18);
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
    PCLmWriter::NameObject::~NameObject((PCLmWriter::NameObject *)v34);
    v21 = v23;
    if ( *((_BYTE *)v23[2] + 25) )
    {
      for ( i = (__int64)v23[1]; !*(_BYTE *)(i + 25) && v21 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
      {
        v21 = (_QWORD *)i;
        v23 = (std::_Ref_count_base **)i;
      }
    }
    else
    {
      i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min();
    }
    v23 = (std::_Ref_count_base **)i;
  }
LABEL_16:
  (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, (char *)v49 + 2, 3);
  if ( v27[1] )
    std::_Ref_count_base::_Decref(v27[1]);
  std::string::_Tidy_deallocate(v32);
  `eh vector destructor iterator'(v36, 0x20u, 5u, (void (*)(void *))PCLmWriter::PDFImageData::~PDFImageData);
  `eh vector destructor iterator'(v41, 0x20u, 8u, (void (*)(void *))PCLmWriter::PDFImageData::~PDFImageData);
  v14 = (std::_Ref_count_base *)a2[1];
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
}

```

## disassembly

```asm
0x180018fb0  mov     [rsp-8+arg_10], rbx
0x180018fb5  push    rbp
0x180018fb6  push    rsi
0x180018fb7  push    rdi
0x180018fb8  push    r12
0x180018fba  push    r14
0x180018fbc  lea     rbp, [rsp-1F0h]
0x180018fc4  sub     rsp, 2F0h
0x180018fcb  mov     rax, cs:__security_cookie
0x180018fd2  xor     rax, rsp
0x180018fd5  mov     [rbp+210h+var_28], rax
0x180018fdc  mov     rsi, rdx
0x180018fdf  mov     r14, rcx
0x180018fe2  mov     [rsp+310h+var_2A8], rdx
0x180018fe7  mov     [rbp+210h+var_30], 3E0A3C3Ch
0x180018ff1  mov     [rbp+210h+var_2C], 203Eh
0x180018ffa  lea     rdx, aWidth; "/Width"
0x180019001  lea     rcx, [rbp+210h+var_130]
0x180019008  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001900d  nop
0x18001900e  lea     rdx, aColorspace; "/ColorSpace"
0x180019015  lea     rcx, [rbp+210h+var_110]
0x18001901c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019021  nop
0x180019022  lea     rdx, aHeight; "/Height"
0x180019029  lea     rcx, [rbp+210h+var_F0]
0x180019030  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019035  nop
0x180019036  lea     rdx, aFilter; "/Filter"
0x18001903d  lea     rcx, [rbp+210h+var_D0]
0x180019044  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019049  nop
0x18001904a  lea     rdx, aSubtype; "/Subtype"
0x180019051  lea     rcx, [rbp+210h+var_B0]
0x180019058  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001905d  nop
0x18001905e  lea     rdx, aLength; "/Length"
0x180019065  lea     rcx, [rbp+210h+var_90]
0x18001906c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019071  nop
0x180019072  lea     rbx, aType; "/Type"
0x180019079  mov     rdx, rbx
0x18001907c  lea     rcx, [rbp+210h+var_70]
0x180019083  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019088  nop
0x180019089  lea     rdx, aBitspercompone; "/BitsPerComponent"
0x180019090  lea     rcx, [rbp+210h+var_50]
0x180019097  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001909c  nop
0x18001909d  mov     rdx, rbx
0x1800190a0  lea     rcx, [rbp+210h+var_1D0]
0x1800190a4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800190a9  nop
0x1800190aa  lea     rdx, aParent; "/Parent"
0x1800190b1  lea     rcx, [rbp+210h+var_1B0]
0x1800190b5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800190ba  nop
0x1800190bb  lea     rdx, aResources; "/Resources"
0x1800190c2  lea     rcx, [rbp+210h+var_190]
0x1800190c9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800190ce  nop
0x1800190cf  lea     rdx, aMediabox; "/MediaBox"
0x1800190d6  lea     rcx, [rbp+210h+var_170]
0x1800190dd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800190e2  nop
0x1800190e3  lea     rdx, aContents; "/Contents"
0x1800190ea  lea     rcx, [rbp+210h+var_150]
0x1800190f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800190f6  nop
0x1800190f7  mov     rcx, [rsi]
0x1800190fa  mov     rax, [rcx]
0x1800190fd  mov     r8d, 2
0x180019103  lea     rdx, [rbp+210h+var_30]
0x18001910a  mov     rax, [rax+18h]
0x18001910e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019113  mov     rdx, rbx
0x180019116  lea     rcx, [rbp+210h+var_288]
0x18001911a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001911f  lea     r8, [rbp+210h+var_288]
0x180019123  lea     rdx, [rsp+310h+var_2E0]
0x180019128  lea     rcx, [r14+18h]
0x18001912c  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::find(std::string const &)
0x180019131  lea     rcx, [rbp+210h+var_288]
0x180019135  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001913a  lea     rcx, [rbp+210h+var_268]
0x18001913e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180019143  nop
0x180019144  xorps   xmm1, xmm1
0x180019147  movdqu  xmmword ptr [rsp+310h+var_2B8], xmm1
0x18001914d  mov     rbx, [rsp+310h+var_2E0]
0x180019152  cmp     rbx, [r14+18h]
0x180019156  jz      loc_1800191FB
0x18001915c  mov     [rsp+310h+var_2F0], 0
0x180019164  lea     r9, ??_R0?AVINameObject@PCLmWriter@@@8; PCLmWriter::INameObject `RTTI Type Descriptor'
0x18001916b  lea     r8, ??_R0?AVIObject@PCLmWriter@@@8; PCLmWriter::IObject `RTTI Type Descriptor'
0x180019172  xor     edx, edx
0x180019174  mov     rcx, [rbx+40h]
0x180019178  call    __RTDynamicCast_0
0x18001917d  test    rax, rax
0x180019180  jz      short loc_18001919F
0x180019182  mov     rcx, [rbx+48h]
0x180019186  test    rcx, rcx
0x180019189  jz      short loc_18001918F
0x18001918b  lock inc dword ptr [rcx+8]
0x18001918f  mov     [rsp+310h+var_2D8], rax
0x180019194  mov     rax, [rbx+48h]
0x180019198  mov     [rsp+310h+var_2D8+8], rax
0x18001919d  jmp     short loc_1800191A8
0x18001919f  xorps   xmm0, xmm0
0x1800191a2  movdqu  xmmword ptr [rsp+310h+var_2D8], xmm0
0x1800191a8  lea     rdx, [rsp+310h+var_2D8]
0x1800191ad  lea     rcx, [rsp+310h+var_2B8]
0x1800191b2  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x1800191b7  mov     rcx, [rsp+310h+var_2D8+8]; this
0x1800191bc  test    rcx, rcx
0x1800191bf  jz      short loc_1800191C6
0x1800191c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800191c6  mov     rcx, [rsp+310h+var_2B8]
0x1800191cb  mov     rax, [rcx]
0x1800191ce  mov     rax, [rax+28h]
0x1800191d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191d7  mov     r8, rax
0x1800191da  lea     rax, [rbp+210h+var_268]
0x1800191de  cmp     rax, r8
0x1800191e1  jz      short loc_1800191FB
0x1800191e3  mov     rcx, r8
0x1800191e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800191eb  mov     r8, [r8+10h]
0x1800191ef  mov     rdx, rax
0x1800191f2  lea     rcx, [rbp+210h+var_268]
0x1800191f6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800191fb  lea     rcx, [rbp+210h+var_268]
0x1800191ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180019204  mov     rbx, rax
0x180019207  mov     r12d, 8
0x18001920d  mov     r9d, r12d
0x180019210  lea     r8, aXobject; "/XObject"
0x180019217  mov     rdx, [rbp+210h+var_258]
0x18001921b  mov     rcx, rax
0x18001921e  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x180019223  lea     edi, [r12-3]
0x180019228  test    al, al
0x18001922a  jz      short loc_180019245
0x18001922c  mov     rdx, rsi
0x18001922f  lea     rcx, [rsp+310h+var_2C8]
0x180019234  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019239  mov     r9d, r12d
0x18001923c  lea     r8, [rbp+210h+var_130]
0x180019243  jmp     short loc_180019277
0x180019245  mov     r9, rdi
0x180019248  lea     r8, aPage; "/Page"
0x18001924f  mov     rdx, [rbp+210h+var_258]
0x180019253  mov     rcx, rbx
0x180019256  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18001925b  test    al, al
0x18001925d  jz      loc_180019321
0x180019263  mov     rdx, rsi
0x180019266  lea     rcx, [rsp+310h+var_2C8]
0x18001926b  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019270  mov     r9, rdi
0x180019273  lea     r8, [rbp+210h+var_1D0]
0x180019277  mov     rdx, rax
0x18001927a  mov     rcx, r14
0x18001927d  call    ?SerializeInOrder@DictionaryObject@PCLmWriter@@QEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@_K@Z; PCLmWriter::DictionaryObject::SerializeInOrder(std::shared_ptr<PCLmWriter::IByteStream>,std::string const * const,unsigned __int64)
0x180019282  mov     rcx, [rsi]
0x180019285  mov     rax, [rcx]
0x180019288  mov     r8d, 3
0x18001928e  lea     rdx, [rbp+210h+var_30+2]
0x180019295  mov     rax, [rax+18h]
0x180019299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001929e  nop
0x18001929f  mov     rcx, [rsp+310h+var_2B8+8]; this
0x1800192a4  test    rcx, rcx
0x1800192a7  jz      short loc_1800192AF
0x1800192a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800192ae  nop
0x1800192af  lea     rcx, [rbp+210h+var_268]
0x1800192b3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800192b8  nop
0x1800192b9  lea     r9, ??1PDFImageData@PCLmWriter@@QEAA@XZ; void (*)(void *)
0x1800192c0  mov     r8, rdi; unsigned __int64
0x1800192c3  mov     ebx, 20h ; ' '
0x1800192c8  mov     edx, ebx; unsigned __int64
0x1800192ca  lea     rcx, [rbp+210h+var_1D0]; void *
0x1800192ce  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800192d3  nop
0x1800192d4  lea     r9, ??1PDFImageData@PCLmWriter@@QEAA@XZ; void (*)(void *)
0x1800192db  mov     r8, r12; unsigned __int64
0x1800192de  mov     edx, ebx; unsigned __int64
0x1800192e0  lea     rcx, [rbp+210h+var_130]; void *
0x1800192e7  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800192ec  nop
0x1800192ed  mov     rcx, [rsi+8]; this
0x1800192f1  test    rcx, rcx
0x1800192f4  jz      short loc_1800192FB
0x1800192f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800192fb  mov     rcx, [rbp+210h+var_28]
0x180019302  xor     rcx, rsp; StackCookie
0x180019305  call    __security_check_cookie
0x18001930a  mov     rbx, [rsp+310h+arg_10]
0x180019312  add     rsp, 2F0h
0x180019319  pop     r14
0x18001931b  pop     r12
0x18001931d  pop     rdi
0x18001931e  pop     rsi
0x18001931f  pop     rbp
0x180019320  retn
0x180019321  mov     rax, [r14]
0x180019324  lea     rdx, [rsp+310h+var_2E0]
0x180019329  mov     rcx, r14
0x18001932c  mov     rax, [rax+38h]
0x180019330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019335  mov     rax, [r14]
0x180019338  lea     rdx, [rsp+310h+var_2A0]
0x18001933d  mov     rcx, r14
0x180019340  mov     rax, [rax+40h]
0x180019344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019349  mov     rcx, [rax]
0x18001934c  cmp     [rsp+310h+var_2E0], rcx
0x180019351  jz      loc_180019282
0x180019357  mov     rcx, [rsi]
0x18001935a  mov     rax, [rcx]
0x18001935d  mov     r8d, 1
0x180019363  lea     rdx, [rbp+210h+var_30+2]
0x18001936a  mov     rax, [rax+18h]
0x18001936e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019373  mov     rdx, [rsp+310h+var_2E0]
0x180019378  add     rdx, 20h ; ' '
0x18001937c  xor     r9d, r9d
0x18001937f  xor     r8d, r8d
0x180019382  lea     rcx, [rbp+210h+var_248]
0x180019386  call    ??0NameObject@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@II@Z; PCLmWriter::NameObject::NameObject(std::string const &,uint,uint)
0x18001938b  nop
0x18001938c  mov     rdx, rsi
0x18001938f  lea     rcx, [rsp+310h+var_298]
0x180019394  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019399  mov     rdx, rax
0x18001939c  lea     rcx, [rbp+210h+var_248]
0x1800193a0  call    ?Serialize@NameObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z; PCLmWriter::NameObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)
0x1800193a5  mov     rcx, [rsi]
0x1800193a8  mov     rax, [rcx]
0x1800193ab  mov     r8d, 1
0x1800193b1  lea     rdx, [rbp+210h+var_2C+1]
0x1800193b8  mov     rax, [rax+18h]
0x1800193bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193c1  mov     rdx, [rsp+310h+var_2E0]
0x1800193c6  add     rdx, 40h ; '@'
0x1800193ca  lea     rcx, [rsp+310h+var_2C8]
0x1800193cf  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x1800193d4  nop
0x1800193d5  mov     r9, [rsp+310h+var_2C8]
0x1800193da  test    r9, r9
0x1800193dd  jz      short loc_18001945B
0x1800193df  mov     rax, [r9]
0x1800193e2  mov     r8, [rax+20h]
0x1800193e6  mov     rdx, rsi
0x1800193e9  lea     rcx, [rbp+210h+var_288]
0x1800193ed  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x1800193f2  mov     rdx, rax
0x1800193f5  mov     rcx, r9
0x1800193f8  mov     rax, r8
0x1800193fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019400  nop
0x180019401  mov     rcx, [rsp+310h+var_2C0]; this
0x180019406  test    rcx, rcx
0x180019409  jz      short loc_180019411
0x18001940b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019410  nop
0x180019411  lea     rcx, [rbp+210h+var_248]; this
0x180019415  call    ??1NameObject@PCLmWriter@@UEAA@XZ; PCLmWriter::NameObject::~NameObject(void)
0x18001941a  mov     rax, [rsp+310h+var_2E0]
0x18001941f  mov     rcx, [rax+10h]
0x180019423  cmp     byte ptr [rcx+19h], 0
0x180019427  jz      short loc_180019449
0x180019429  mov     rcx, [rax+8]
0x18001942d  jmp     short loc_180019441
0x18001942f  cmp     rax, [rcx+10h]
0x180019433  jnz     short loc_180019451
0x180019435  mov     rax, rcx
0x180019438  mov     [rsp+310h+var_2E0], rcx
0x18001943d  mov     rcx, [rcx+8]
0x180019441  cmp     byte ptr [rcx+19h], 0
0x180019445  jz      short loc_18001942F
0x180019447  jmp     short loc_180019451
0x180019449  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)
0x18001944e  mov     rcx, rax
0x180019451  mov     [rsp+310h+var_2E0], rcx
0x180019456  jmp     loc_180019335
0x18001945b  mov     r8, [rsp+310h+var_2E0]
0x180019460  add     r8, 20h ; ' '
0x180019464  lea     rcx, [rbp+210h+var_288]
0x180019468  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18001946d  nop
0x18001946e  xor     r8d, r8d
0x180019471  lea     rdx, [rbp+210h+var_288]
0x180019475  lea     rcx, [rbp+210h+pExceptionObject]; this
0x180019479  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x18001947e  lea     rdx, _TI2?AVException@PCLmWriter@@; pThrowInfo
0x180019485  lea     rcx, [rbp+210h+pExceptionObject]; pExceptionObject
0x180019489  call    _CxxThrowException_0
  ... truncated ...
```
