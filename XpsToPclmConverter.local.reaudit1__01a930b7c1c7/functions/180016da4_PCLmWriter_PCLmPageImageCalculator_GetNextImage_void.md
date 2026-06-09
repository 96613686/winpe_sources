# PCLmWriter::PCLmPageImageCalculator::GetNextImage(void)

- ea: `0x180016da4`
- end: `0x18001734a`
- name: `?GetNextImage@PCLmPageImageCalculator@PCLmWriter@@QEAA?AV?$shared_ptr@$$CBVIStreamObject@PCLmWriter@@@std@@XZ`
- size: `1446`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010290`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x18000efa8`
- `0x18000f3e0`
- `0x18000f41c`
- `0x18000f448`
- `0x1800101cc`
- `0x180010718`
- `0x180010f34`
- `0x180012cc0`
- `0x180013028`
- `0x180013780`
- `0x18001496c`
- `0x1800149b0`
- `0x180016da4`
- `0x18001f010`

## string_xrefs

- `0x18001707b`: `/BitsPerComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_QWORD *__fastcall PCLmWriter::PCLmPageImageCalculator::GetNextImage(__int64 *a1, _QWORD *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // r14d
  char *v8; // rdi
  char *v9; // rax
  size_t v10; // rbx
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, char *, char *, _QWORD, _DWORD); // rbx
  __int64 v13; // rax
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, char *, std::_Ref_count_base **, _QWORD, _DWORD); // rbx
  __int64 v16; // rax
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, char *, _QWORD, _QWORD, _DWORD); // rbx
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, char *, _BYTE *, _QWORD, _DWORD); // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  int v31; // [rsp+20h] [rbp-E0h]
  _BYTE v32[16]; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+60h] [rbp-A0h]
  __int64 v36; // [rsp+68h] [rbp-98h]
  char v37[8]; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v38; // [rsp+78h] [rbp-88h]
  char v39[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v40; // [rsp+88h] [rbp-78h]
  char v41[8]; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v42; // [rsp+98h] [rbp-68h]
  char v43[8]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v44; // [rsp+A8h] [rbp-58h]
  char v45[8]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v46; // [rsp+B8h] [rbp-48h]
  char v47[8]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v48; // [rsp+C8h] [rbp-38h]
  char v49[8]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v50; // [rsp+D8h] [rbp-28h]
  _QWORD *v51; // [rsp+E0h] [rbp-20h]
  char v52[8]; // [rsp+E8h] [rbp-18h] BYREF
  std::_Ref_count_base *v53; // [rsp+F0h] [rbp-10h]
  std::_Ref_count_base *v54[2]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v55[32]; // [rsp+128h] [rbp+28h] BYREF

  v51 = a2;
  v33 = 0;
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(&v34);
  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v32);
  v4 = 9LL * *((unsigned int *)a1 + 21);
  v5 = *a1;
  v6 = *((_DWORD *)a1 + 22)
     * *(_DWORD *)(v5 + 8 * v4 + 68)
     * (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1[3] + 32LL))(a1[3]);
  v7 = v6;
  v8 = (char *)v35;
  if ( (char *)(unsigned int)v6 >= (char *)v35 - v34 )
  {
    if ( (char *)(unsigned int)v6 <= (char *)v35 - v34 )
      goto LABEL_8;
    if ( (unsigned int)v6 > (unsigned __int64)(v36 - v34) )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v34, (unsigned int)v6);
      goto LABEL_8;
    }
    v10 = (unsigned int)v6 - ((unsigned __int64)v35 - v34);
    memset_0(v35, 0, v10);
    v9 = &v8[v10];
  }
  else
  {
    v9 = (char *)(v34 + v6);
  }
  v35 = v9;
LABEL_8:
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a1[3] + 24LL))(
    a1[3],
    *(unsigned int *)(*a1 + 72LL * *((unsigned int *)a1 + 21) + 68),
    v7,
    v34);
  v11 = a1[12];
  v12 = *(void (__fastcall **)(__int64, char *, char *, _QWORD, _DWORD))(*(_QWORD *)v11 + 24LL);
  std::string::string(v52, "/XObject");
  v12(v11, v49, v52, 0, 0);
  std::string::_Tidy_deallocate(v52);
  std::string::string(v54, "/Type");
  v13 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v32, v54);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v13, v49);
  std::string::_Tidy_deallocate(v54);
  v14 = a1[12];
  v15 = *(void (__fastcall **)(__int64, char *, std::_Ref_count_base **, _QWORD, _DWORD))(*(_QWORD *)v14 + 24LL);
  std::string::string(v54, "/Image");
  v15(v14, v47, v54, 0, 0);
  std::string::_Tidy_deallocate(v54);
  std::string::string(v52, "/Subtype");
  v16 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v32, v52);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v16, v47);
  std::string::_Tidy_deallocate(v52);
  v17 = a1[12];
  v18 = *(void (__fastcall **)(__int64, char *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v17 + 16LL);
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1[3] + 32LL))(a1[3]);
  v18(v17, v45, v19, 0, 0);
  std::string::string(v52, "/Width");
  v20 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v32, v52);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v20, v45);
  std::string::_Tidy_deallocate(v52);
  (*(void (__fastcall **)(__int64, char *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)a1[12] + 16LL))(
    a1[12],
    v43,
    *(unsigned int *)(*a1 + 72LL * *((unsigned int *)a1 + 21) + 68),
    0,
    0);
  std::string::string(v52, "/Height");
  v21 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v32, v52);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v21, v43);
  std::string::_Tidy_deallocate(v52);
  (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)a1[12] + 16LL))(a1[12], v41, 8);
  std::string::string(v52, "/BitsPerComponent");
  v22 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v32, v52);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v22, v41);
  std::string::_Tidy_deallocate(v52);
  if ( v7 > 0x7FFFFFFF )
    PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow();
  (*(void (__fastcall **)(__int64, char *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)a1[12] + 16LL))(a1[12], v39, v7, 0, 0);
  std::string::string(v52, "/Length");
  v23 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v32, v52);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v23, v39);
  std::string::_Tidy_deallocate(v52);
  *(_OWORD *)v54 = 0;
  v24 = a1[12];
  v25 = *(__int64 (__fastcall **)(__int64, char *, _BYTE *, _QWORD, _DWORD))(*(_QWORD *)v24 + 24LL);
  if ( *((_DWORD *)a1 + 22) == 1 )
  {
    std::string::string(v55, "/DeviceGray");
    v26 = v25(v24, v52, v55, 0, 0);
    std::shared_ptr<PCLmWriter::IByteStream>::operator=(v54, v26);
    if ( v53 )
      std::_Ref_count_base::_Decref(v53);
  }
  else
  {
    std::string::string(v55, "/DeviceRGB");
    v27 = v25(v24, v52, v55, 0, 0);
    std::shared_ptr<PCLmWriter::IByteStream>::operator=(v54, v27);
    if ( v53 )
      std::_Ref_count_base::_Decref(v53);
  }
  std::string::_Tidy_deallocate(v55);
  std::string::string(v55, "/ColorSpace");
  v28 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](v32, v55);
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(v28, v54);
  std::string::_Tidy_deallocate(v55);
  *a2 = 0;
  a2[1] = 0;
  v33 = 1;
  (*(void (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)a1[12] + 80LL))(a1[12], v37, &v34);
  LOBYTE(v31) = 1;
  v29 = (*(__int64 (__fastcall **)(__int64, char *, _BYTE *, char *, int, _DWORD, _DWORD))(*(_QWORD *)a1[12] + 48LL))(
          a1[12],
          v52,
          v32,
          v37,
          v31,
          *(_DWORD *)(*a1 + 72LL * *((unsigned int *)a1 + 21) + 32),
          *(_DWORD *)(*a1 + 72LL * *((unsigned int *)a1 + 21) + 36));
  std::shared_ptr<PCLmWriter::IByteStream>::operator=(a2, v29);
  if ( v53 )
    std::_Ref_count_base::_Decref(v53);
  ++*((_DWORD *)a1 + 21);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  if ( v54[1] )
    std::_Ref_count_base::_Decref(v54[1]);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
  if ( v44 )
    std::_Ref_count_base::_Decref(v44);
  if ( v46 )
    std::_Ref_count_base::_Decref(v46);
  if ( v48 )
    std::_Ref_count_base::_Decref(v48);
  if ( v50 )
    std::_Ref_count_base::_Decref(v50);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    v32,
    v32);
  std::vector<unsigned char>::_Tidy(&v34);
  return a2;
}

```

## disassembly

```asm
0x180016da4  mov     [rsp-8+arg_10], rbx
0x180016da9  push    rbp
0x180016daa  push    rsi
0x180016dab  push    rdi
0x180016dac  push    r14
0x180016dae  push    r15
0x180016db0  lea     rbp, [rsp-50h]
0x180016db5  sub     rsp, 150h
0x180016dbc  mov     rax, cs:__security_cookie
0x180016dc3  xor     rax, rsp
0x180016dc6  mov     [rbp+70h+var_28], rax
0x180016dca  mov     r15, rdx
0x180016dcd  mov     rsi, rcx
0x180016dd0  mov     [rbp+70h+var_90], rdx
0x180016dd4  mov     [rsp+170h+var_120], 0
0x180016ddc  lea     rcx, [rsp+170h+var_118]
0x180016de1  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x180016de6  nop
0x180016de7  lea     rcx, [rsp+170h+var_130]
0x180016dec  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x180016df1  nop
0x180016df2  mov     rcx, [rsi+18h]
0x180016df6  mov     eax, [rsi+54h]
0x180016df9  lea     rdi, [rax+rax*8]
0x180016dfd  mov     rbx, [rsi]
0x180016e00  mov     rax, [rcx]
0x180016e03  mov     rax, [rax+20h]
0x180016e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e0c  imul    eax, [rbx+rdi*8+44h]
0x180016e11  imul    eax, [rsi+58h]
0x180016e15  mov     r14d, eax
0x180016e18  mov     rdx, [rsp+170h+var_118]
0x180016e1d  mov     rdi, [rsp+170h+var_110]
0x180016e22  mov     rcx, rdi
0x180016e25  sub     rcx, rdx
0x180016e28  cmp     r14, rcx
0x180016e2b  jnb     short loc_180016E32
0x180016e2d  add     rax, rdx
0x180016e30  jmp     short loc_180016E67
0x180016e32  jbe     short loc_180016E6C
0x180016e34  mov     rax, [rsp+170h+var_108]
0x180016e39  sub     rax, rdx
0x180016e3c  cmp     r14, rax
0x180016e3f  jbe     short loc_180016E50
0x180016e41  mov     rdx, r14
0x180016e44  lea     rcx, [rsp+170h+var_118]
0x180016e49  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180016e4e  jmp     short loc_180016E6C
0x180016e50  mov     rbx, r14
0x180016e53  sub     rbx, rcx
0x180016e56  mov     r8, rbx; Size
0x180016e59  xor     edx, edx; Val
0x180016e5b  mov     rcx, rdi; void *
0x180016e5e  call    memset_0
0x180016e63  lea     rax, [rdi+rbx]
0x180016e67  mov     [rsp+170h+var_110], rax
0x180016e6c  mov     rcx, [rsi+18h]
0x180016e70  mov     r8, [rcx]
0x180016e73  mov     eax, [rsi+54h]
0x180016e76  lea     r10, [rax+rax*8]
0x180016e7a  mov     rdx, [rsi]
0x180016e7d  mov     rax, [r8+18h]
0x180016e81  mov     r9, [rsp+170h+var_118]
0x180016e86  mov     r8d, r14d
0x180016e89  mov     edx, [rdx+r10*8+44h]
0x180016e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e93  mov     rdi, [rsi+60h]
0x180016e97  mov     rax, [rdi]
0x180016e9a  mov     rbx, [rax+18h]
0x180016e9e  lea     rdx, aXobject; "/XObject"
0x180016ea5  lea     rcx, [rbp+70h+var_88]
0x180016ea9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016eae  nop
0x180016eaf  mov     [rsp+170h+var_150], 0
0x180016eb7  xor     r9d, r9d
0x180016eba  lea     r8, [rbp+70h+var_88]
0x180016ebe  lea     rdx, [rbp+70h+var_A0]
0x180016ec2  mov     rcx, rdi
0x180016ec5  mov     rax, rbx
0x180016ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ecd  nop
0x180016ece  lea     rcx, [rbp+70h+var_88]
0x180016ed2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016ed7  lea     rdx, aType; "/Type"
0x180016ede  lea     rcx, [rbp+70h+var_68]
0x180016ee2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016ee7  nop
0x180016ee8  lea     rdx, [rbp+70h+var_68]
0x180016eec  lea     rcx, [rsp+170h+var_130]
0x180016ef1  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180016ef6  mov     rcx, rax
0x180016ef9  lea     rdx, [rbp+70h+var_A0]
0x180016efd  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180016f02  nop
0x180016f03  lea     rcx, [rbp+70h+var_68]
0x180016f07  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016f0c  mov     rdi, [rsi+60h]
0x180016f10  mov     rax, [rdi]
0x180016f13  mov     rbx, [rax+18h]
0x180016f17  lea     rdx, aImage; "/Image"
0x180016f1e  lea     rcx, [rbp+70h+var_68]
0x180016f22  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016f27  nop
0x180016f28  mov     [rsp+170h+var_150], 0
0x180016f30  xor     r9d, r9d
0x180016f33  lea     r8, [rbp+70h+var_68]
0x180016f37  lea     rdx, [rbp+70h+var_B0]
0x180016f3b  mov     rcx, rdi
0x180016f3e  mov     rax, rbx
0x180016f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f46  nop
0x180016f47  lea     rcx, [rbp+70h+var_68]
0x180016f4b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016f50  lea     rdx, aSubtype; "/Subtype"
0x180016f57  lea     rcx, [rbp+70h+var_88]
0x180016f5b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016f60  nop
0x180016f61  lea     rdx, [rbp+70h+var_88]
0x180016f65  lea     rcx, [rsp+170h+var_130]
0x180016f6a  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180016f6f  mov     rcx, rax
0x180016f72  lea     rdx, [rbp+70h+var_B0]
0x180016f76  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180016f7b  nop
0x180016f7c  lea     rcx, [rbp+70h+var_88]
0x180016f80  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016f85  mov     rdi, [rsi+60h]
0x180016f89  mov     rax, [rdi]
0x180016f8c  mov     rbx, [rax+10h]
0x180016f90  mov     rcx, [rsi+18h]
0x180016f94  mov     rax, [rcx]
0x180016f97  mov     rax, [rax+20h]
0x180016f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fa0  mov     [rsp+170h+var_150], 0
0x180016fa8  xor     r9d, r9d
0x180016fab  mov     r8d, eax
0x180016fae  lea     rdx, [rbp+70h+var_C0]
0x180016fb2  mov     rcx, rdi
0x180016fb5  mov     rax, rbx
0x180016fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fbd  nop
0x180016fbe  lea     rdx, aWidth; "/Width"
0x180016fc5  lea     rcx, [rbp+70h+var_88]
0x180016fc9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016fce  nop
0x180016fcf  lea     rdx, [rbp+70h+var_88]
0x180016fd3  lea     rcx, [rsp+170h+var_130]
0x180016fd8  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180016fdd  mov     rcx, rax
0x180016fe0  lea     rdx, [rbp+70h+var_C0]
0x180016fe4  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x180016fe9  nop
0x180016fea  lea     rcx, [rbp+70h+var_88]
0x180016fee  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016ff3  mov     rcx, [rsi+60h]
0x180016ff7  mov     rdx, [rcx]
0x180016ffa  mov     eax, [rsi+54h]
0x180016ffd  lea     r10, [rax+rax*8]
0x180017001  mov     r8, [rsi]
0x180017004  mov     rax, [rdx+10h]
0x180017008  mov     [rsp+170h+var_150], 0
0x180017010  xor     r9d, r9d
0x180017013  mov     r8d, [r8+r10*8+44h]
0x180017018  lea     rdx, [rbp+70h+var_D0]
0x18001701c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017021  nop
0x180017022  lea     rdx, aHeight; "/Height"
0x180017029  lea     rcx, [rbp+70h+var_88]
0x18001702d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180017032  nop
0x180017033  lea     rdx, [rbp+70h+var_88]
0x180017037  lea     rcx, [rsp+170h+var_130]
0x18001703c  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180017041  mov     rcx, rax
0x180017044  lea     rdx, [rbp+70h+var_D0]
0x180017048  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x18001704d  nop
0x18001704e  lea     rcx, [rbp+70h+var_88]
0x180017052  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017057  mov     rcx, [rsi+60h]
0x18001705b  mov     rax, [rcx]
0x18001705e  mov     [rsp+170h+var_150], 0
0x180017066  xor     r9d, r9d
0x180017069  lea     r8d, [r9+8]
0x18001706d  lea     rdx, [rbp+70h+var_E0]
0x180017071  mov     rax, [rax+10h]
0x180017075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001707a  nop
0x18001707b  lea     rdx, aBitspercompone; "/BitsPerComponent"
0x180017082  lea     rcx, [rbp+70h+var_88]
0x180017086  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001708b  nop
0x18001708c  lea     rdx, [rbp+70h+var_88]
0x180017090  lea     rcx, [rsp+170h+var_130]
0x180017095  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x18001709a  mov     rcx, rax
0x18001709d  lea     rdx, [rbp+70h+var_E0]
0x1800170a1  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x1800170a6  nop
0x1800170a7  lea     rcx, [rbp+70h+var_88]
0x1800170ab  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800170b0  cmp     r14d, 7FFFFFFFh
0x1800170b7  jbe     short loc_1800170BF
0x1800170b9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@PCLmWriter@@@PCLmWriter@@SAXXZ; PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow(void)
0x1800170bf  mov     rcx, [rsi+60h]
0x1800170c3  mov     rax, [rcx]
0x1800170c6  mov     [rsp+170h+var_150], 0
0x1800170ce  xor     r9d, r9d
0x1800170d1  mov     r8d, r14d
0x1800170d4  lea     rdx, [rbp+70h+var_F0]
0x1800170d8  mov     rax, [rax+10h]
0x1800170dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e1  nop
0x1800170e2  lea     rdx, aLength; "/Length"
0x1800170e9  lea     rcx, [rbp+70h+var_88]
0x1800170ed  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800170f2  nop
0x1800170f3  lea     rdx, [rbp+70h+var_88]
0x1800170f7  lea     rcx, [rsp+170h+var_130]
0x1800170fc  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x180017101  mov     rcx, rax
0x180017104  lea     rdx, [rbp+70h+var_F0]
0x180017108  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x18001710d  nop
0x18001710e  lea     rcx, [rbp+70h+var_88]
0x180017112  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017117  xorps   xmm0, xmm0
0x18001711a  movdqu  xmmword ptr [rbp+70h+var_68], xmm0
0x18001711f  mov     rdi, [rsi+60h]
0x180017123  mov     rax, [rdi]
0x180017126  lea     rcx, [rbp+70h+var_48]
0x18001712a  mov     rbx, [rax+18h]
0x18001712e  cmp     dword ptr [rsi+58h], 1
0x180017132  jnz     short loc_18001717C
0x180017134  lea     rdx, aDevicegray; "/DeviceGray"
0x18001713b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180017140  nop
0x180017141  mov     [rsp+170h+var_150], 0
0x180017149  xor     r9d, r9d
0x18001714c  lea     r8, [rbp+70h+var_48]
0x180017150  lea     rdx, [rbp+70h+var_88]
0x180017154  mov     rcx, rdi
0x180017157  mov     rax, rbx
0x18001715a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001715f  mov     rdx, rax
0x180017162  lea     rcx, [rbp+70h+var_68]
0x180017166  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x18001716b  mov     rcx, [rbp+70h+var_80]; this
0x18001716f  test    rcx, rcx
0x180017172  jz      short loc_18001717A
0x180017174  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017179  nop
0x18001717a  jmp     short loc_1800171C2
0x18001717c  lea     rdx, aDevicergb; "/DeviceRGB"
0x180017183  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180017188  nop
0x180017189  mov     [rsp+170h+var_150], 0
0x180017191  xor     r9d, r9d
0x180017194  lea     r8, [rbp+70h+var_48]
0x180017198  lea     rdx, [rbp+70h+var_88]
0x18001719c  mov     rcx, rdi
0x18001719f  mov     rax, rbx
0x1800171a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171a7  mov     rdx, rax
0x1800171aa  lea     rcx, [rbp+70h+var_68]
0x1800171ae  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x1800171b3  mov     rcx, [rbp+70h+var_80]; this
0x1800171b7  test    rcx, rcx
0x1800171ba  jz      short loc_1800171C2
0x1800171bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800171c1  nop
0x1800171c2  lea     rcx, [rbp+70h+var_48]
0x1800171c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800171cb  lea     rdx, aColorspace; "/ColorSpace"
0x1800171d2  lea     rcx, [rbp+70h+var_48]
0x1800171d6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800171db  nop
0x1800171dc  lea     rdx, [rbp+70h+var_48]
0x1800171e0  lea     rcx, [rsp+170h+var_130]
0x1800171e5  call    ??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](std::string const &&)
0x1800171ea  mov     rcx, rax
0x1800171ed  lea     rdx, [rbp+70h+var_68]
0x1800171f1  call    ??$?4$$CBVIIntegerNumberObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIIntegerNumberObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IIntegerNumberObject const,0>(std::shared_ptr<PCLmWriter::IIntegerNumberObject const> const &)
0x1800171f6  nop
0x1800171f7  lea     rcx, [rbp+70h+var_48]
0x1800171fb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017200  mov     qword ptr [r15], 0
0x180017207  mov     qword ptr [r15+8], 0
0x18001720f  mov     [rsp+170h+var_120], 1
0x180017217  mov     rcx, [rsi+60h]
0x18001721b  mov     rax, [rcx]
0x18001721e  lea     r8, [rsp+170h+var_118]
0x180017223  lea     rdx, [rsp+170h+var_100]
0x180017228  mov     rax, [rax+50h]
0x18001722c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017231  nop
0x180017232  mov     rcx, [rsi+60h]
0x180017236  mov     eax, [rsi+54h]
0x180017239  lea     r8, [rax+rax*8]
0x18001723d  mov     rdx, [rsi]
  ... truncated ...
```
