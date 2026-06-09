# PCLmWriter::StreamObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x1800199e0`
- end: `0x180019da9`
- name: `?Serialize@StreamObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `969`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: ``

## callees

- `0x1800015f0`
- `0x180001f6c`
- `0x18000e7c8`
- `0x18000e87c`
- `0x18000efa8`
- `0x18000f1b8`
- `0x18000f3e0`
- `0x18000f41c`
- `0x18000f8d4`
- `0x1800101cc`
- `0x1800105f4`
- `0x180010718`
- `0x180011538`
- `0x180011a00`
- `0x18001496c`
- `0x1800149b0`
- `0x1800184f0`
- `0x180018640`
- `0x1800188c0`
- `0x180018fb0`
- `0x1800199e0`
- `0x180019fbc`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall PCLmWriter::StreamObject::Serialize(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64, std::_Ref_count_base **, __int64); // r9
  __int64 v7; // r10
  __int64 v8; // rax
  std::_Ref_count_base *v9; // rdi
  _QWORD *v10; // rax
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  std::_Ref_count_base **v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rbx
  _QWORD *v20; // rax
  __int64 i; // rax
  _QWORD *v22; // rax
  __int64 v23; // rsi
  void (__fastcall *v24)(__int64, __int64, _QWORD); // rdi
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 ByteStreamBuffer; // rax
  std::_Ref_count_base *v28; // rcx
  std::_Ref_count_base *v29; // [rsp+20h] [rbp-99h] BYREF
  std::_Ref_count_base *v30; // [rsp+28h] [rbp-91h]
  _DWORD *v31; // [rsp+30h] [rbp-89h] BYREF
  std::_Ref_count_base *v32; // [rsp+38h] [rbp-81h]
  _BYTE v33[16]; // [rsp+40h] [rbp-79h] BYREF
  std::_Ref_count_base *v34[2]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD *v35; // [rsp+60h] [rbp-59h]
  _QWORD v36[7]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v37[32]; // [rsp+A0h] [rbp-19h] BYREF
  char v38[16]; // [rsp+C0h] [rbp+7h] BYREF
  char v39[16]; // [rsp+D0h] [rbp+17h] BYREF

  v35 = a2;
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v33);
  strcpy(v38, "\nstream\n");
  strcpy(v39, "\nendstream");
  *(_OWORD *)v34 = 0;
  v4 = a1 + 24;
  if ( *(_BYTE *)(a1 + 88) )
  {
    v5 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v31, v4);
    v8 = v6(v7, &v29, v5);
    std::shared_ptr<PCLmWriter::IByteStream>::operator=(v34, v8);
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
    v9 = (std::_Ref_count_base *)operator new(0x48u);
    v29 = v9;
    *(_OWORD *)v9 = 0;
    *((_DWORD *)v9 + 2) = 1;
    *((_DWORD *)v9 + 3) = 1;
    *(_QWORD *)v9 = &std::_Ref_count_obj2<PCLmWriter::NameObject>::`vftable';
    std::_Construct_in_place<PCLmWriter::NameObject,char const (&)[13]>((char *)v9 + 16, "/FlateDecode");
    v31 = (_DWORD *)((char *)v9 + 16);
    v32 = v9;
    std::string::string(v37, "/Filter");
    v10 = (_QWORD *)std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v33, v37);
    *v10 = (char *)v9 + 16;
    v11 = (std::_Ref_count_base *)v10[1];
    v10[1] = v9;
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
    std::string::_Tidy_deallocate(v37);
    v12 = v34[0];
    LODWORD(v29) = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v34[0] + 16LL))(v34[0]);
    v13 = std::make_shared<PCLmWriter::IntegerNumberObject,unsigned int>(&v31, &v29);
    std::string::string(v37, "/Length");
    v14 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v33, v37);
    std::shared_ptr<PCLmWriter::IByteStream>::operator=(v14, v13);
    std::string::_Tidy_deallocate(v37);
  }
  else
  {
    std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(v34, v4);
    v12 = v34[0];
    LODWORD(v29) = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v34[0] + 16LL))(v34[0]) + 1;
    v15 = std::make_shared<PCLmWriter::IntegerNumberObject,unsigned int>(&v31, &v29);
    std::string::string(v37, "/Length");
    v16 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v33, v37);
    std::shared_ptr<PCLmWriter::IByteStream>::operator=(v16, v15);
    std::string::_Tidy_deallocate(v37);
  }
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  (*(void (__fastcall **)(_QWORD, std::_Ref_count_base **))(**(_QWORD **)(a1 + 56) + 56LL))(*(_QWORD *)(a1 + 56), &v29);
  while ( 1 )
  {
    v17 = (std::_Ref_count_base **)(*(__int64 (__fastcall **)(_QWORD, _DWORD **))(**(_QWORD **)(a1 + 56) + 64LL))(
                                     *(_QWORD *)(a1 + 56),
                                     &v31);
    v19 = (__int64)v29;
    if ( v29 == *v17 )
      break;
    if ( !(unsigned __int8)PCLmWriter::StreamObject::_IsStreamObjectDictionaryKey(v18, (char *)v29 + 32) )
    {
      v20 = (_QWORD *)std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(
                        v33,
                        v37,
                        v19 + 32);
      std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(
        *v20 + 64LL,
        v19 + 64);
      v19 = (__int64)v29;
    }
    if ( *(_BYTE *)(*(_QWORD *)(v19 + 16) + 25LL) )
    {
      for ( i = *(_QWORD *)(v19 + 8); !*(_BYTE *)(i + 25) && v19 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
      {
        v19 = i;
        v29 = (std::_Ref_count_base *)i;
      }
    }
    else
    {
      i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min();
    }
    v29 = (std::_Ref_count_base *)i;
  }
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(
    &v29,
    v33);
  PCLmWriter::DictionaryObject::DictionaryObject(v36, &v29, 0, 0);
  v22 = (_QWORD *)std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(&v31, a2);
  PCLmWriter::DictionaryObject::Serialize(v36, v22);
  (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, v38, 8);
  v23 = *a2;
  v24 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)*a2 + 24LL);
  v25 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v12 + 16LL))(v12);
  v26 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v37, v34);
  ByteStreamBuffer = PCLmWriter::GetByteStreamBuffer(v26);
  v24(v23, ByteStreamBuffer, v25);
  (*(void (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, v39, 10);
  PCLmWriter::DictionaryObject::~DictionaryObject((PCLmWriter::DictionaryObject *)v36);
  if ( v34[1] )
    std::_Ref_count_base::_Decref(v34[1]);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v33,
    v33);
  v28 = (std::_Ref_count_base *)a2[1];
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
}

```

## disassembly

```asm
0x1800199e0  mov     [rsp-8+arg_10], rbx
0x1800199e5  push    rbp
0x1800199e6  push    rsi
0x1800199e7  push    rdi
0x1800199e8  push    r14
0x1800199ea  push    r15
0x1800199ec  lea     rbp, [rsp-37h]
0x1800199f1  sub     rsp, 0F0h
0x1800199f8  mov     rax, cs:__security_cookie
0x1800199ff  xor     rax, rsp
0x180019a02  mov     [rbp+57h+var_30], rax
0x180019a06  mov     r15, rdx
0x180019a09  mov     rsi, rcx
0x180019a0c  mov     [rbp+57h+var_B0], rdx
0x180019a10  lea     rcx, [rbp+57h+var_D0]
0x180019a14  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x180019a19  nop
0x180019a1a  movsd   xmm0, qword ptr cs:aStream; "\nstream\n"
0x180019a22  movsd   qword ptr [rbp+57h+var_50], xmm0
0x180019a27  mov     al, byte ptr cs:aStream+8; ""
0x180019a2d  mov     [rbp+57h+var_50+8], al
0x180019a30  movsd   xmm0, qword ptr cs:aEndstream; "\nendstream"
0x180019a38  movsd   qword ptr [rbp+57h+var_40], xmm0
0x180019a3d  mov     eax, dword ptr cs:aEndstream+7; "eam"
0x180019a43  mov     dword ptr [rbp+57h+var_40+7], eax
0x180019a46  xorps   xmm0, xmm0
0x180019a49  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180019a4e  lea     rdx, [rsi+18h]
0x180019a52  cmp     byte ptr [rsi+58h], 0
0x180019a56  jz      loc_180019B8A
0x180019a5c  mov     r10, [rsi+28h]
0x180019a60  mov     rax, [r10]
0x180019a63  mov     r9, [rax+58h]
0x180019a67  lea     rcx, [rsp+110h+var_E0]
0x180019a6c  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019a71  mov     r8, rax
0x180019a74  lea     rdx, [rsp+110h+var_F0]
0x180019a79  mov     rcx, r10
0x180019a7c  mov     rax, r9
0x180019a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a84  mov     rdx, rax
0x180019a87  lea     rcx, [rbp+57h+var_C0]
0x180019a8b  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x180019a90  mov     rcx, [rsp+110h+var_E8]; this
0x180019a95  test    rcx, rcx
0x180019a98  jz      short loc_180019A9F
0x180019a9a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019a9f  mov     ecx, 48h ; 'H'; Size
0x180019aa4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019aa9  mov     rdi, rax
0x180019aac  mov     [rsp+110h+var_F0], rax
0x180019ab1  xorps   xmm0, xmm0
0x180019ab4  movups  xmmword ptr [rax], xmm0
0x180019ab7  mov     dword ptr [rax+8], 1
0x180019abe  mov     dword ptr [rax+0Ch], 1
0x180019ac5  lea     rax, ??_7?$_Ref_count_obj2@VNameObject@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::NameObject>::`vftable'
0x180019acc  mov     [rdi], rax
0x180019acf  lea     rbx, [rdi+10h]
0x180019ad3  lea     rdx, aFlatedecode; "/FlateDecode"
0x180019ada  mov     rcx, rbx
0x180019add  call    ??$_Construct_in_place@VNameObject@PCLmWriter@@AEAY0N@$$CBD@std@@YAXAEAVNameObject@PCLmWriter@@AEAY0N@$$CBD@Z; std::_Construct_in_place<PCLmWriter::NameObject,char const (&)[13]>(PCLmWriter::NameObject &,char const (&)[13])
0x180019ae2  nop
0x180019ae3  mov     [rsp+110h+var_E0], rbx
0x180019ae8  mov     [rsp+110h+var_D8], rdi
0x180019aed  lea     rdx, aFilter; "/Filter"
0x180019af4  lea     rcx, [rbp+57h+var_70]
0x180019af8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019afd  nop
0x180019afe  lea     rdx, [rbp+57h+var_70]
0x180019b02  lea     rcx, [rbp+57h+var_D0]
0x180019b06  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180019b0b  mov     [rax], rbx
0x180019b0e  mov     rcx, [rax+8]; this
0x180019b12  mov     [rax+8], rdi
0x180019b16  test    rcx, rcx
0x180019b19  jz      short loc_180019B21
0x180019b1b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019b20  nop
0x180019b21  lea     rcx, [rbp+57h+var_70]
0x180019b25  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019b2a  nop
0x180019b2b  mov     r14, [rbp+57h+var_C0]
0x180019b2f  mov     rax, [r14]
0x180019b32  mov     rcx, r14
0x180019b35  mov     rax, [rax+10h]
0x180019b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b3e  mov     dword ptr [rsp+110h+var_F0], eax
0x180019b42  lea     rdx, [rsp+110h+var_F0]
0x180019b47  lea     rcx, [rsp+110h+var_E0]
0x180019b4c  call    ??$make_shared@VIntegerNumberObject@PCLmWriter@@I@std@@YA?AV?$shared_ptr@VIntegerNumberObject@PCLmWriter@@@0@$$QEAI@Z; std::make_shared<PCLmWriter::IntegerNumberObject,uint>(uint &&)
0x180019b51  mov     rbx, rax
0x180019b54  lea     rdx, aLength; "/Length"
0x180019b5b  lea     rcx, [rbp+57h+var_70]
0x180019b5f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019b64  nop
0x180019b65  lea     rdx, [rbp+57h+var_70]
0x180019b69  lea     rcx, [rbp+57h+var_D0]
0x180019b6d  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180019b72  mov     rcx, rax
0x180019b75  mov     rdx, rbx
0x180019b78  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x180019b7d  nop
0x180019b7e  lea     rcx, [rbp+57h+var_70]
0x180019b82  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019b87  nop
0x180019b88  jmp     short loc_180019BF2
0x180019b8a  lea     rcx, [rbp+57h+var_C0]
0x180019b8e  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x180019b93  mov     r14, [rbp+57h+var_C0]
0x180019b97  mov     rax, [r14]
0x180019b9a  mov     rcx, r14
0x180019b9d  mov     rax, [rax+10h]
0x180019ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ba6  inc     eax
0x180019ba8  mov     dword ptr [rsp+110h+var_F0], eax
0x180019bac  lea     rdx, [rsp+110h+var_F0]
0x180019bb1  lea     rcx, [rsp+110h+var_E0]
0x180019bb6  call    ??$make_shared@VIntegerNumberObject@PCLmWriter@@I@std@@YA?AV?$shared_ptr@VIntegerNumberObject@PCLmWriter@@@0@$$QEAI@Z; std::make_shared<PCLmWriter::IntegerNumberObject,uint>(uint &&)
0x180019bbb  mov     rbx, rax
0x180019bbe  lea     rdx, aLength; "/Length"
0x180019bc5  lea     rcx, [rbp+57h+var_70]
0x180019bc9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180019bce  nop
0x180019bcf  lea     rdx, [rbp+57h+var_70]
0x180019bd3  lea     rcx, [rbp+57h+var_D0]
0x180019bd7  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180019bdc  mov     rcx, rax
0x180019bdf  mov     rdx, rbx
0x180019be2  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x180019be7  nop
0x180019be8  lea     rcx, [rbp+57h+var_70]
0x180019bec  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019bf1  nop
0x180019bf2  mov     rcx, [rsp+110h+var_D8]; this
0x180019bf7  test    rcx, rcx
0x180019bfa  jz      short loc_180019C01
0x180019bfc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019c01  mov     rcx, [rsi+38h]
0x180019c05  mov     rax, [rcx]
0x180019c08  lea     rdx, [rsp+110h+var_F0]
0x180019c0d  mov     rax, [rax+38h]
0x180019c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c16  mov     rcx, [rsi+38h]
0x180019c1a  mov     rax, [rcx]
0x180019c1d  lea     rdx, [rsp+110h+var_E0]
0x180019c22  mov     rax, [rax+40h]
0x180019c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c2b  mov     rbx, [rsp+110h+var_F0]
0x180019c30  cmp     rbx, [rax]
0x180019c33  jz      short loc_180019CA1
0x180019c35  lea     rdx, [rbx+20h]
0x180019c39  call    ?_IsStreamObjectDictionaryKey@StreamObject@PCLmWriter@@AEBA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; PCLmWriter::StreamObject::_IsStreamObjectDictionaryKey(std::string const &)
0x180019c3e  test    al, al
0x180019c40  jnz     short loc_180019C68
0x180019c42  lea     r8, [rbx+20h]
0x180019c46  lea     rdx, [rbp+57h+var_70]
0x180019c4a  lea     rcx, [rbp+57h+var_D0]
0x180019c4e  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(std::string const &)
0x180019c53  mov     rcx, [rax]
0x180019c56  add     rcx, 40h ; '@'
0x180019c5a  lea     rdx, [rbx+40h]
0x180019c5e  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x180019c63  mov     rbx, [rsp+110h+var_F0]
0x180019c68  mov     rcx, [rbx+10h]
0x180019c6c  cmp     byte ptr [rcx+19h], 0
0x180019c70  jz      short loc_180019C92
0x180019c72  mov     rax, [rbx+8]
0x180019c76  jmp     short loc_180019C8A
0x180019c78  cmp     rbx, [rax+10h]
0x180019c7c  jnz     short loc_180019C97
0x180019c7e  mov     rbx, rax
0x180019c81  mov     [rsp+110h+var_F0], rax
0x180019c86  mov     rax, [rax+8]
0x180019c8a  cmp     byte ptr [rax+19h], 0
0x180019c8e  jz      short loc_180019C78
0x180019c90  jmp     short loc_180019C97
0x180019c92  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)
0x180019c97  mov     [rsp+110h+var_F0], rax
0x180019c9c  jmp     loc_180019C16
0x180019ca1  lea     rdx, [rbp+57h+var_D0]
0x180019ca5  lea     rcx, [rsp+110h+var_F0]
0x180019caa  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &&)
0x180019caf  xor     r9d, r9d
0x180019cb2  xor     r8d, r8d
0x180019cb5  lea     rdx, [rsp+110h+var_F0]
0x180019cba  lea     rcx, [rbp+57h+var_A8]
0x180019cbe  call    ??0DictionaryObject@PCLmWriter@@QEAA@V?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@II@Z; PCLmWriter::DictionaryObject::DictionaryObject(std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,uint,uint)
0x180019cc3  nop
0x180019cc4  mov     rdx, r15
0x180019cc7  lea     rcx, [rsp+110h+var_E0]
0x180019ccc  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019cd1  mov     rdx, rax
0x180019cd4  lea     rcx, [rbp+57h+var_A8]
0x180019cd8  call    ?Serialize@DictionaryObject@PCLmWriter@@UEBAXV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z; PCLmWriter::DictionaryObject::Serialize(std::shared_ptr<PCLmWriter::IByteStream>)
0x180019cdd  mov     rcx, [r15]
0x180019ce0  mov     rax, [rcx]
0x180019ce3  mov     r8d, 8
0x180019ce9  lea     rdx, [rbp+57h+var_50]
0x180019ced  mov     rax, [rax+18h]
0x180019cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cf6  mov     rsi, [r15]
0x180019cf9  mov     rax, [rsi]
0x180019cfc  mov     rdi, [rax+18h]
0x180019d00  mov     rax, [r14]
0x180019d03  mov     rcx, r14
0x180019d06  mov     rax, [rax+10h]
0x180019d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d0f  mov     ebx, eax
0x180019d11  lea     rdx, [rbp+57h+var_C0]
0x180019d15  lea     rcx, [rbp+57h+var_70]
0x180019d19  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180019d1e  mov     rcx, rax
0x180019d21  call    ?GetByteStreamBuffer@PCLmWriter@@YAPEAEV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z; PCLmWriter::GetByteStreamBuffer(std::shared_ptr<PCLmWriter::IByteStream>)
0x180019d26  mov     r8d, ebx
0x180019d29  mov     rdx, rax
0x180019d2c  mov     rcx, rsi
0x180019d2f  mov     rax, rdi
0x180019d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d37  mov     rcx, [r15]
0x180019d3a  mov     rax, [rcx]
0x180019d3d  mov     r8d, 0Ah
0x180019d43  lea     rdx, [rbp+57h+var_40]
0x180019d47  mov     rax, [rax+18h]
0x180019d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d50  nop
0x180019d51  lea     rcx, [rbp+57h+var_A8]; this
0x180019d55  call    ??1DictionaryObject@PCLmWriter@@UEAA@XZ; PCLmWriter::DictionaryObject::~DictionaryObject(void)
0x180019d5a  nop
0x180019d5b  mov     rcx, [rbp+57h+var_C0+8]; this
0x180019d5f  test    rcx, rcx
0x180019d62  jz      short loc_180019D6A
0x180019d64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019d69  nop
0x180019d6a  lea     rdx, [rbp+57h+var_D0]
0x180019d6e  lea     rcx, [rbp+57h+var_D0]
0x180019d72  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x180019d77  nop
0x180019d78  mov     rcx, [r15+8]; this
0x180019d7c  test    rcx, rcx
0x180019d7f  jz      short loc_180019D86
0x180019d81  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019d86  mov     rcx, [rbp+57h+var_30]
0x180019d8a  xor     rcx, rsp; StackCookie
0x180019d8d  call    __security_check_cookie
0x180019d92  mov     rbx, [rsp+110h+arg_10]
0x180019d9a  add     rsp, 0F0h
0x180019da1  pop     r15
0x180019da3  pop     r14
0x180019da5  pop     rdi
0x180019da6  pop     rsi
0x180019da7  pop     rbp
0x180019da8  retn
```
