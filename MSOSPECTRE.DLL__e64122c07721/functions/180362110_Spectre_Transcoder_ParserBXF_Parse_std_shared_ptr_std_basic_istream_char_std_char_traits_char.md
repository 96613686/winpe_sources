# Spectre::Transcoder::ParserBXF::Parse(std::shared_ptr<std::basic_istream<char,std::char_traits<char>>>)

- ea: `0x180362110`
- end: `0x1803623b9`
- name: `?Parse@ParserBXF@Transcoder@Spectre@@QEAA?AV?$shared_ptr@VAsset3D@Transcoder@Spectre@@@std@@V?$shared_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@@5@@Z`
- size: `681`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180347010`
- `0x180347280`

## callees

- `0x180014a60`
- `0x180040860`
- `0x180362110`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f910`
- `0x1804c1790`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180362261`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x180362261`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180362163`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180362184`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180362163`
- `MSVCP140!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x180362184`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180362173`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x180362173`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1803621ae`
- `MSVCP140!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z` at `0x1803621ae`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036231f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18036231f`

## pseudocode

```c
_QWORD *__fastcall Spectre::Transcoder::ParserBXF::Parse(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  void *v10; // rax
  void *v11; // rcx
  _QWORD *v12; // rax
  char *v13; // rbx
  __int64 v14; // rax
  void *v15; // rcx
  volatile signed __int32 *v16; // rbx
  std::exception *v18; // [rsp+50h] [rbp-118h] BYREF
  __int128 v19; // [rsp+60h] [rbp-108h] BYREF
  __int64 v20; // [rsp+70h] [rbp-F8h]
  _BYTE v21[24]; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v22[8]; // [rsp+98h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+D8h] [rbp-90h]
  char *v24; // [rsp+E8h] [rbp-80h]
  __int64 v25; // [rsp+F0h] [rbp-78h] BYREF
  unsigned int v26[2]; // [rsp+F8h] [rbp-70h] BYREF
  __int128 v27; // [rsp+100h] [rbp-68h] BYREF
  __int64 v28; // [rsp+110h] [rbp-58h]
  __int64 v29; // [rsp+118h] [rbp-50h] BYREF
  __int64 v30; // [rsp+120h] [rbp-48h]

  v26[1] = HIDWORD(a2);
  v26[0] = 0;
  LODWORD(v25) = 0;
  v6 = *a3;
  std::istream::tellg(*a3, &v27);
  std::istream::seekg(v6, 0, 2);
  std::istream::tellg(v6, &v29);
  v19 = v27;
  v20 = v28;
  std::istream::seekg(v6, &v19);
  *(_OWORD *)Block = 0;
  v24 = 0;
  v9 = v30 + v29;
  if ( v30 + v29 )
  {
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(v8, v7);
    if ( v9 < 0x1000 )
    {
      v12 = operator new(v30 + v29);
    }
    else
    {
      if ( v9 + 39 < v9 )
        __scrt_throw_std_bad_array_new_length();
      v10 = operator new(v9 + 39);
      v11 = v10;
      if ( !v10 )
LABEL_15:
        _invalid_parameter_noinfo_noreturn();
      v12 = (_QWORD *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v12 - 1) = v11;
    }
    Block[0] = v12;
    v13 = (char *)v12 + v9;
    v24 = (char *)v12 + v9;
    memset_0(v12, 0, v9);
    Block[1] = v13;
  }
  std::istream::read(*a3, Block[0], v9);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v22[0] = (__int64)&std::_Func_impl_no_alloc<_lambda_feecbc445f6261a9a9106351bb6dd527_,void,enum Spectre::Framework::EFrameType,enum Spectre::Framework::EFrameQuality>::`vftable';
    v22[7] = (__int64)v22;
    Spectre::Engine::Parser::Parse(
      *(Spectre::Engine::Parser **)(a1 + 80),
      (__int64)Block[0],
      v9,
      v26,
      &v25,
      0,
      (__int64)v22);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v18) )
    {
      std::exception::exception((std::exception *)v21, v18);
      throw (std::exception *)v21;
    }
  }
  *a2 = 0;
  a2[1] = 0;
  v14 = *(_QWORD *)(a1 + 96);
  if ( v14 )
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
  *a2 = *(_QWORD *)(a1 + 88);
  a2[1] = *(_QWORD *)(a1 + 96);
  v15 = Block[0];
  if ( Block[0] )
  {
    if ( (unsigned __int64)(v24 - (char *)Block[0]) >= 0x1000 )
    {
      v15 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v15 - 8) > 0x1F )
        goto LABEL_15;
    }
    operator delete(v15);
    *(_OWORD *)Block = 0;
    v24 = 0;
  }
  v16 = (volatile signed __int32 *)a3[1];
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180362110  mov     r11, rsp
0x180362113  mov     [r11+20h], rbx
0x180362117  push    rsi
0x180362118  push    rdi
0x180362119  push    r12
0x18036211b  push    r14
0x18036211d  push    r15
0x18036211f  sub     rsp, 140h
0x180362126  mov     rax, cs:__security_cookie
0x18036212d  xor     rax, rsp
0x180362130  mov     [rsp+168h+var_38], rax
0x180362138  mov     r15, r8
0x18036213b  mov     rsi, rdx
0x18036213e  mov     r14, rcx
0x180362141  mov     [rsp+168h+var_70], rdx
0x180362149  mov     [rsp+168h+var_128], r8
0x18036214e  xor     r12d, r12d
0x180362151  mov     [r11-70h], r12d
0x180362155  mov     [r11-78h], r12d
0x180362159  mov     rbx, [r8]
0x18036215c  lea     rdx, [r11-68h]
0x180362160  mov     rcx, rbx
0x180362163  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x180362169  xor     edx, edx
0x18036216b  lea     r8d, [r12+2]
0x180362170  mov     rcx, rbx
0x180362173  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z; std::istream::seekg(__int64,int)
0x180362179  lea     rdx, [rsp+168h+var_50]
0x180362181  mov     rcx, rbx
0x180362184  call    cs:__imp_?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::istream::tellg(void)
0x18036218a  movups  xmm0, [rsp+168h+var_68]
0x180362192  movaps  [rsp+168h+var_108], xmm0
0x180362197  movsd   xmm1, [rsp+168h+var_58]
0x1803621a0  movsd   [rsp+168h+var_F8], xmm1
0x1803621a6  lea     rdx, [rsp+168h+var_108]
0x1803621ab  mov     rcx, rbx
0x1803621ae  call    cs:__imp_?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@V?$fpos@U_Mbstatet@@@2@@Z; std::istream::seekg(std::fpos<_Mbstatet>)
0x1803621b4  mov     rdi, [rsp+168h+var_50]
0x1803621bc  xorps   xmm1, xmm1
0x1803621bf  movdqu  xmmword ptr [rsp+168h+Block], xmm1
0x1803621c8  mov     [rsp+168h+var_80], r12
0x1803621d0  add     rdi, [rsp+168h+var_48]
0x1803621d8  jz      short loc_180362253
0x1803621da  mov     rax, 7FFFFFFFFFFFFFFFh
0x1803621e4  cmp     rdi, rax
0x1803621e7  ja      loc_1803623AD
0x1803621ed  cmp     rdi, 1000h
0x1803621f4  jb      short loc_180362222
0x1803621f6  lea     rcx, [rdi+27h]; Size
0x1803621fa  cmp     rcx, rdi
0x1803621fd  jbe     loc_1803623B3
0x180362203  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180362208  mov     rcx, rax
0x18036220b  test    rax, rax
0x18036220e  jz      loc_18036231F
0x180362214  add     rax, 27h ; '''
0x180362218  and     rax, 0FFFFFFFFFFFFFFE0h
0x18036221c  mov     [rax-8], rcx
0x180362220  jmp     short loc_18036222A
0x180362222  mov     rcx, rdi; Size
0x180362225  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18036222a  mov     [rsp+168h+Block], rax
0x180362232  lea     rbx, [rax+rdi]
0x180362236  mov     [rsp+168h+var_80], rbx
0x18036223e  mov     r8, rdi; Size
0x180362241  xor     edx, edx; Val
0x180362243  mov     rcx, rax; void *
0x180362246  call    memset_0
0x18036224b  mov     [rsp+168h+Block+8], rbx
0x180362253  mov     r8, rdi
0x180362256  mov     rdx, [rsp+168h+Block]
0x18036225e  mov     rcx, [r15]
0x180362261  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x180362267  nop
0x180362268  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_feecbc445f6261a9a9106351bb6dd527_@@XW4EFrameType@Framework@Spectre@@W4EFrameQuality@34@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_feecbc445f6261a9a9106351bb6dd527_,void,Spectre::Framework::EFrameType,Spectre::Framework::EFrameQuality>::`vftable'
0x18036226f  mov     [rsp+168h+var_D0], rax
0x180362277  lea     rax, [rsp+168h+var_D0]
0x18036227f  mov     [rsp+168h+var_98], rax
0x180362287  lea     rax, [rsp+168h+var_D0]
0x18036228f  mov     [rsp+168h+var_138], rax; __int64
0x180362294  mov     [rsp+168h+var_140], r12; __int64
0x180362299  lea     rax, [rsp+168h+var_78]
0x1803622a1  mov     [rsp+168h+var_148], rax; __int64
0x1803622a6  lea     r9, [rsp+168h+var_70]
0x1803622ae  mov     r8d, edi
0x1803622b1  mov     rdx, [rsp+168h+Block]
0x1803622b9  mov     rcx, [r14+50h]; this
0x1803622bd  call    ?Parse@Parser@Engine@Spectre@@QEAAXPEBXIAEAI1PEAXV?$function@$$A6AXW4EFrameType@Framework@Spectre@@W4EFrameQuality@23@@Z@std@@@Z; Spectre::Engine::Parser::Parse(void const *,uint,uint &,uint &,void *,std::function<void (Spectre::Framework::EFrameType,Spectre::Framework::EFrameQuality)>)
0x1803622c2  nop
0x1803622c3  mov     [rsi], r12
0x1803622c6  mov     [rsi+8], r12
0x1803622ca  mov     rax, [r14+60h]
0x1803622ce  test    rax, rax
0x1803622d1  jz      short loc_1803622D7
0x1803622d3  lock inc dword ptr [rax+8]
0x1803622d7  mov     rax, [r14+58h]
0x1803622db  mov     [rsi], rax
0x1803622de  mov     rax, [r14+60h]
0x1803622e2  mov     [rsi+8], rax
0x1803622e6  mov     rcx, [rsp+168h+Block]; Block
0x1803622ee  test    rcx, rcx
0x1803622f1  jz      short loc_18036233F
0x1803622f3  mov     rdx, [rsp+168h+var_80]
0x1803622fb  sub     rdx, rcx
0x1803622fe  mov     rax, rcx
0x180362301  cmp     rdx, 1000h
0x180362308  jb      short loc_180362326
0x18036230a  add     rdx, 27h ; '''
0x18036230e  mov     rcx, [rcx-8]
0x180362312  sub     rax, rcx
0x180362315  add     rax, 0FFFFFFFFFFFFFFF8h
0x180362319  cmp     rax, 1Fh
0x18036231d  jbe     short loc_180362326
0x18036231f  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180362326  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18036232b  xorps   xmm0, xmm0
0x18036232e  movdqu  xmmword ptr [rsp+168h+Block], xmm0
0x180362337  mov     [rsp+168h+var_80], r12
0x18036233f  mov     rbx, [r15+8]
0x180362343  test    rbx, rbx
0x180362346  jz      short loc_180362382
0x180362348  mov     edi, 0FFFFFFFFh
0x18036234d  mov     eax, edi
0x18036234f  lock xadd [rbx+8], eax
0x180362354  cmp     eax, 1
0x180362357  jnz     short loc_180362382
0x180362359  mov     rax, [rbx]
0x18036235c  mov     rcx, rbx
0x18036235f  mov     rax, [rax]
0x180362362  call    cs:__guard_dispatch_icall_fptr
0x180362368  lock xadd [rbx+0Ch], edi
0x18036236d  cmp     edi, 1
0x180362370  jnz     short loc_180362382
0x180362372  mov     rdx, [rbx]
0x180362375  mov     rcx, rbx
0x180362378  mov     rax, [rdx+8]
0x18036237c  call    cs:__guard_dispatch_icall_fptr
0x180362382  mov     rax, rsi
0x180362385  mov     rcx, [rsp+168h+var_38]
0x18036238d  xor     rcx, rsp; StackCookie
0x180362390  call    __security_check_cookie
0x180362395  mov     rbx, [rsp+168h+arg_18]
0x18036239d  add     rsp, 140h
0x1803623a4  pop     r15
0x1803623a6  pop     r14
0x1803623a8  pop     r12
0x1803623aa  pop     rdi
0x1803623ab  pop     rsi
0x1803623ac  retn
0x1803623ad  call    ?_Xlength@?$vector@UD3D11_SUBRESOURCE_DATA@@V?$allocator@UD3D11_SUBRESOURCE_DATA@@@std@@@std@@CAXXZ; std::vector<D3D11_SUBRESOURCE_DATA>::_Xlength(void)
0x1803623b3  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
