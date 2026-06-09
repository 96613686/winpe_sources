# asg::SemanticRegistry::from_json(nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar,std::allocator<uchar>>> const &,asg::SemanticRegistry::TextPreprocessorOptionsSchema &)

- ea: `0x180099cd0`
- end: `0x180099edd`
- name: `?from_json@SemanticRegistry@asg@@YAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@AEAUTextPreprocessorOptionsSchema@12@@Z`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config`

## callers

- `0x180099960`

## callees

- `0x180007ce0`
- `0x180075ad0`
- `0x180075ba0`
- `0x1800760d0`
- `0x1800761b0`
- `0x1800770b0`
- `0x1800952a0`
- `0x180097080`
- `0x1800971d0`
- `0x180099cd0`
- `0x1801f97e0`
- `0x180242ca0`

## string_xrefs

- `0x180099d4c`: `removePunctuationAndCoalesceBlanks`
- `0x180099daf`: `removePunctuationAndCoalesceBlanks`
- `0x180099e82`: `removePunctuationAndCoalesceBlanks`
- `0x180099e01`: `maxTokenCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall asg::SemanticRegistry::from_json(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 **v9; // rax
  __int64 *v10; // r14
  __int64 *v11; // rbx
  __int64 *v12; // rsi
  unsigned __int64 v13; // rdi
  _QWORD *v14; // rcx
  size_t v15; // r8
  int v16; // eax
  char v17; // cl
  __int64 *v18; // rax
  _QWORD *v19; // rcx
  unsigned __int64 v20; // rbx
  size_t v21; // r8
  int v22; // eax
  __int64 v23; // r8
  __int64 *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 *v27; // rax
  __int64 v28; // r8
  _QWORD *v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rax
  __int64 v33; // [rsp+20h] [rbp-C8h] BYREF
  _QWORD Src[4]; // [rsp+28h] [rbp-C0h] BYREF
  _QWORD pExceptionObject[7]; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v36[64]; // [rsp+80h] [rbp-68h] BYREF

  v5 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::at<char const (&)[23],0>(
         a1,
         (__int64)"normalizeCase",
         a3);
  nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::get_to<bool,0>(
    v5,
    (_BYTE *)a2,
    v6);
  if ( *(_BYTE *)a1 != 1 )
  {
    v33 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::type_name(
            a1,
            v7,
            v8);
    v30 = nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[51],char const *>(
            Src,
            (__int64)"cannot use at() with ",
            &v33);
    nlohmann::json_abi_v3_11_2::detail::type_error::create<std::nullptr_t,0>(
      (__int64)pExceptionObject,
      304,
      (__int64)v30);
    throw (nlohmann::json_abi_v3_11_2::detail::type_error *)pExceptionObject;
  }
  v9 = *(__int64 ***)(a1 + 8);
  v10 = *v9;
  v11 = (__int64 *)(*v9)[1];
  v12 = *v9;
  if ( !*((_BYTE *)v11 + 25) )
  {
    do
    {
      v13 = v11[6];
      v14 = v11 + 4;
      if ( (unsigned __int64)v11[7] > 0xF )
        v14 = (_QWORD *)*v14;
      v15 = v11[6];
      if ( v13 > 0x22 )
        v15 = 34;
      v16 = memcmp(v14, "removePunctuationAndCoalesceBlanks", v15);
      if ( v16 )
      {
        if ( v16 >= 0 )
          goto LABEL_13;
        v17 = -1;
      }
      else
      {
        if ( v13 >= 0x22 )
        {
          if ( v13 <= 0x22 )
            v17 = 0;
          else
LABEL_13:
            v17 = 1;
          v12 = v11;
          goto LABEL_16;
        }
        v17 = -1;
      }
LABEL_16:
      v18 = v11 + 2;
      if ( v17 >= 0 )
        v18 = v11;
      v11 = (__int64 *)*v18;
    }
    while ( !*(_BYTE *)(*v18 + 25) );
  }
  if ( *((_BYTE *)v12 + 25) )
    goto LABEL_31;
  v19 = v12 + 4;
  v20 = v12[6];
  if ( (unsigned __int64)v12[7] > 0xF )
    v19 = (_QWORD *)*v19;
  v21 = v12[6];
  if ( v20 > 0x22 )
    v21 = 34;
  v22 = memcmp(v19, "removePunctuationAndCoalesceBlanks", v21);
  if ( v22 )
  {
    if ( v22 >= 0 )
      goto LABEL_31;
  }
  else if ( v20 > 0x22 )
  {
    goto LABEL_31;
  }
  if ( v12 == v10 )
  {
LABEL_31:
    v31 = std::string::string(Src, "removePunctuationAndCoalesceBlanks", v8);
    v32 = nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[6],std::string,char const (&)[12]>(
            pExceptionObject,
            (__int64)"key '",
            v31,
            (__int64)"' not found");
    nlohmann::json_abi_v3_11_2::detail::out_of_range::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> const *,0>(
      (__int64)v36,
      403,
      (__int64)v32);
    throw (nlohmann::json_abi_v3_11_2::detail::out_of_range *)v36;
  }
  nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::get_to<bool,0>(
    (_BYTE *)v12 + 64,
    (_BYTE *)(a2 + 1),
    v8);
  v24 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::at<char const (&)[23],0>(
          a1,
          (__int64)"trimBlanks",
          v23);
  nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::get_to<bool,0>(
    v24,
    (_BYTE *)(a2 + 2),
    v25);
  v27 = nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::at<char const (&)[23],0>(
          a1,
          (__int64)"maxTokenCount",
          v26);
  return nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>>::get_to<unsigned __int64,0>(
           v27,
           (_QWORD *)(a2 + 8),
           v28);
}

```

## disassembly

```asm
0x180099cd0  mov     [rsp+arg_10], rbx
0x180099cd5  mov     [rsp+arg_18], rbp
0x180099cda  push    rsi
0x180099cdb  push    rdi
0x180099cdc  push    r12
0x180099cde  push    r14
0x180099ce0  push    r15
0x180099ce2  sub     rsp, 0C0h
0x180099ce9  mov     r15, rdx
0x180099cec  mov     rbp, rcx
0x180099cef  lea     rdx, aNormalizecase; "normalizeCase"
0x180099cf6  call    ??$at@AEAY0BH@$$CBD$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAAEBV012@AEAY0BH@$$CBD@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::at<char const (&)[23],0>(char const (&)[23])
0x180099cfb  mov     rdx, r15
0x180099cfe  mov     rcx, rax
0x180099d01  call    ??$get_to@_N$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAAEA_NAEA_N@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::get_to<bool,0>(bool &)
0x180099d06  cmp     byte ptr [rbp+0], 1
0x180099d0a  jnz     loc_180099E37
0x180099d10  mov     rax, [rbp+8]
0x180099d14  mov     r14, [rax]
0x180099d17  mov     rbx, [r14+8]
0x180099d1b  mov     rsi, r14
0x180099d1e  mov     r12d, 22h ; '"'
0x180099d24  cmp     byte ptr [rbx+19h], 0
0x180099d28  jnz     short loc_180099D89
0x180099d2a  nop     word ptr [rax+rax+00h]
0x180099d30  mov     rdi, [rbx+30h]
0x180099d34  lea     rcx, [rbx+20h]
0x180099d38  cmp     qword ptr [rbx+38h], 0Fh
0x180099d3d  jbe     short loc_180099D42
0x180099d3f  mov     rcx, [rcx]; Buf1
0x180099d42  mov     r8, rdi
0x180099d45  cmp     rdi, r12
0x180099d48  cmova   r8, r12; Size
0x180099d4c  lea     rdx, aRemovepunctuat; "removePunctuationAndCoalesceBlanks"
0x180099d53  call    memcmp
0x180099d58  test    eax, eax
0x180099d5a  jz      short loc_180099D62
0x180099d5c  jns     short loc_180099D6D
0x180099d5e  mov     cl, 0FFh
0x180099d60  jmp     short loc_180099D76
0x180099d62  cmp     rdi, r12
0x180099d65  jnb     short loc_180099D6B
0x180099d67  mov     cl, 0FFh
0x180099d69  jmp     short loc_180099D76
0x180099d6b  jbe     short loc_180099D71
0x180099d6d  mov     cl, 1
0x180099d6f  jmp     short loc_180099D73
0x180099d71  xor     ecx, ecx
0x180099d73  mov     rsi, rbx
0x180099d76  lea     rax, [rbx+10h]
0x180099d7a  test    cl, cl
0x180099d7c  cmovns  rax, rbx
0x180099d80  mov     rbx, [rax]
0x180099d83  cmp     byte ptr [rbx+19h], 0
0x180099d87  jz      short loc_180099D30
0x180099d89  cmp     byte ptr [rsi+19h], 0
0x180099d8d  jnz     loc_180099E82
0x180099d93  lea     rcx, [rsi+20h]
0x180099d97  mov     rbx, [rcx+10h]
0x180099d9b  cmp     qword ptr [rcx+18h], 0Fh
0x180099da0  jbe     short loc_180099DA5
0x180099da2  mov     rcx, [rcx]; Buf1
0x180099da5  mov     r8, rbx
0x180099da8  cmp     rbx, r12
0x180099dab  cmova   r8, r12; Size
0x180099daf  lea     rdx, aRemovepunctuat; "removePunctuationAndCoalesceBlanks"
0x180099db6  call    memcmp
0x180099dbb  test    eax, eax
0x180099dbd  jz      short loc_180099DC7
0x180099dbf  jns     loc_180099E82
0x180099dc5  jmp     short loc_180099DD0
0x180099dc7  cmp     rbx, r12
0x180099dca  ja      loc_180099E82
0x180099dd0  cmp     rsi, r14
0x180099dd3  jz      loc_180099E82
0x180099dd9  lea     rdx, [r15+1]
0x180099ddd  lea     rcx, [rsi+40h]
0x180099de1  call    ??$get_to@_N$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAAEA_NAEA_N@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::get_to<bool,0>(bool &)
0x180099de6  lea     rdx, aTrimblanks; "trimBlanks"
0x180099ded  mov     rcx, rbp
0x180099df0  call    ??$at@AEAY0BH@$$CBD$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAAEBV012@AEAY0BH@$$CBD@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::at<char const (&)[23],0>(char const (&)[23])
0x180099df5  lea     rdx, [r15+2]
0x180099df9  mov     rcx, rax
0x180099dfc  call    ??$get_to@_N$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAAEA_NAEA_N@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::get_to<bool,0>(bool &)
0x180099e01  lea     rdx, aMaxtokencount; "maxTokenCount"
0x180099e08  mov     rcx, rbp
0x180099e0b  call    ??$at@AEAY0BH@$$CBD$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAAEBV012@AEAY0BH@$$CBD@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::at<char const (&)[23],0>(char const (&)[23])
0x180099e10  lea     rdx, [r15+8]
0x180099e14  mov     rcx, rax
0x180099e17  lea     r11, [rsp+0E8h+var_28]
0x180099e1f  mov     rbx, [r11+40h]
0x180099e23  mov     rbp, [r11+48h]
0x180099e27  mov     rsp, r11
0x180099e2a  pop     r15
0x180099e2c  pop     r14
0x180099e2e  pop     r12
0x180099e30  pop     rdi
0x180099e31  pop     rsi
0x180099e32  jmp     ??$get_to@_K$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAAEA_KAEA_K@Z; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::get_to<unsigned __int64,0>(unsigned __int64 &)
0x180099e37  mov     rcx, rbp
0x180099e3a  call    ?type_name@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@QEBAPEBDXZ; nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>>::type_name(void)
0x180099e3f  mov     [rsp+0E8h+var_C8], rax
0x180099e44  lea     r8, [rsp+0E8h+var_C8]
0x180099e49  lea     rdx, aCannotUseAtWit; "cannot use at() with "
0x180099e50  lea     rcx, [rsp+0E8h+Src]; Src
0x180099e55  call    ??$concat@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0DD@$$CBDPEBD@detail@json_abi_v3_11_2@nlohmann@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0DD@$$CBD$$QEAPEBD@Z; nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[51],char const *>(char const (&)[51],char const * &&)
0x180099e5a  nop
0x180099e5b  mov     r9, rbp
0x180099e5e  mov     r8, rax
0x180099e61  mov     edx, 130h
0x180099e66  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180099e6b  call    ??$create@$$T$0A@@type_error@detail@json_abi_v3_11_2@nlohmann@@SA?AV0123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$T@Z; nlohmann::json_abi_v3_11_2::detail::type_error::create<std::nullptr_t,0>(int,std::string const &,std::nullptr_t)
0x180099e70  lea     rdx, _TI3?AVtype_error@detail@json_abi_v3_11_2@nlohmann@@; pThrowInfo
0x180099e77  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180099e7c  call    _CxxThrowException
0x180099e82  lea     rdx, aRemovepunctuat; "removePunctuationAndCoalesceBlanks"
0x180099e89  lea     rcx, [rsp+0E8h+Src]
0x180099e8e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180099e93  nop
0x180099e94  lea     r9, aNotFound; "' not found"
0x180099e9b  mov     r8, rax
0x180099e9e  lea     rdx, aKey_0; "key '"
0x180099ea5  lea     rcx, [rsp+0E8h+pExceptionObject]; Src
0x180099eaa  call    ??$concat@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY05$$CBDV12@AEAY0M@$$CBD@detail@json_abi_v3_11_2@nlohmann@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY05$$CBD$$QEAV34@AEAY0M@$$CBD@Z; nlohmann::json_abi_v3_11_2::detail::concat<std::string,char const (&)[6],std::string,char const (&)[12]>(char const (&)[6],std::string &&,char const (&)[12])
0x180099eaf  nop
0x180099eb0  mov     r9, rbp
0x180099eb3  mov     r8, rax
0x180099eb6  mov     edx, 193h
0x180099ebb  lea     rcx, [rsp+0E8h+var_68]
0x180099ec3  call    ??$create@PEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@$0A@@out_of_range@detail@json_abi_v3_11_2@nlohmann@@SA?AV0123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@23@@Z; nlohmann::json_abi_v3_11_2::detail::out_of_range::create<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const *,0>(int,std::string const &,nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> const *)
0x180099ec8  lea     rdx, _TI3?AVout_of_range@detail@json_abi_v3_11_2@nlohmann@@; pThrowInfo
0x180099ecf  lea     rcx, [rsp+0E8h+var_68]; pExceptionObject
0x180099ed7  call    _CxxThrowException
```
