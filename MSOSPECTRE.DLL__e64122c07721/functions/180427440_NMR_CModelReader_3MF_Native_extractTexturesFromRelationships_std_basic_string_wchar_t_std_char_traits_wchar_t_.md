# NMR::CModelReader_3MF_Native::extractTexturesFromRelationships(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,NMR::COpcPackagePart *)

- ea: `0x180427440`
- end: `0x180427b4e`
- name: `?extractTexturesFromRelationships@CModelReader_3MF_Native@NMR@@IEAAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVCOpcPackagePart@2@@Z`
- size: `1806`
- prototype: `__int64 __fastcall(_QWORD *, void *, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180425a00`

## callees

- `0x180014a60`
- `0x180016350`
- `0x180184da0`
- `0x18039e5b0`
- `0x18039ebb0`
- `0x18039f890`
- `0x18039f8e0`
- `0x18039f8f0`
- `0x1804169c0`
- `0x18041f9a0`
- `0x180421380`
- `0x1804221c0`
- `0x180424bf0`
- `0x180425720`
- `0x180425910`
- `0x180427440`
- `0x18042a0b0`
- `0x180430fd0`
- `0x180431030`
- `0x180431df0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180427b02`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180427b09`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180427b10`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180427b02`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180427b09`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180427b10`

## string_xrefs

- `0x1804274a3`: `http://schemas.microsoft.com/3dmanufacturing/2013/01/3dtexture`
- `0x180427a79`: `http://schemas.microsoft.com/3dmanufacturing/2013/01/3dtexture`
- `0x1804274aa`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail`
- `0x180427a72`: `http://schemas.openxmlformats.org/package/2006/relationships/metadata/thumbnail`

## pseudocode

```c
__int64 __fastcall NMR::CModelReader_3MF_Native::extractTexturesFromRelationships(_QWORD *a1, void *a2, __int64 a3)
{
  _QWORD *i; // rbx
  void **v6; // rdx
  char *v7; // r8
  unsigned __int64 v8; // r9
  __int64 v9; // rcx
  void **v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rsi
  void **v13; // r14
  __int64 v14; // rdi
  __int64 v15; // rdi
  _BYTE *v16; // rcx
  __int64 v17; // rsi
  void **v18; // r14
  __int64 v19; // rdi
  __int64 v20; // rsi
  void **v21; // r14
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rsi
  void **v25; // r14
  __int64 v26; // rdi
  volatile signed __int32 *v27; // rdi
  volatile signed __int32 *v28; // rdi
  volatile signed __int32 *v29; // rdi
  volatile signed __int32 *v30; // rdi
  void *v31; // rcx
  char *v32; // rax
  __int128 v34; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h]
  __int64 v36; // [rsp+40h] [rbp-C0h]
  __int128 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h]
  __int64 v39; // [rsp+60h] [rbp-A0h]
  __int128 v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int128 v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  __int128 v46; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v47; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v48; // [rsp+D8h] [rbp-28h]
  void **v49; // [rsp+E0h] [rbp-20h] BYREF
  char v50[24]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+100h] [rbp+0h] BYREF
  void *Src[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v53; // [rsp+130h] [rbp+30h]
  __int128 v54; // [rsp+140h] [rbp+40h] BYREF
  __int128 v55; // [rsp+150h] [rbp+50h] BYREF
  void *Block[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v57; // [rsp+178h] [rbp+78h]
  __int128 v58; // [rsp+180h] [rbp+80h] BYREF
  __int128 v59; // [rsp+190h] [rbp+90h] BYREF
  __int128 v60; // [rsp+1A0h] [rbp+A0h] BYREF

  if ( !a3 )
  {
    NMR::CNMRException::CNMRException((NMR::CNMRException *)pExceptionObject, 4097);
    throw (NMR::CNMRException *)pExceptionObject;
  }
  v55 = 0;
  NMR::COpcPackagePart::getRelationShips(a3, &v55);
  for ( i = *(_QWORD **)v55; i != (_QWORD *)v55; i = (_QWORD *)*i )
  {
    NMR::COpcPackageRelationship::getType(i[2], Block);
    v6 = Block;
    v7 = (char *)Block[0];
    v8 = v57;
    if ( v57 >= 8 )
      v6 = (void **)Block[0];
    v9 = -1;
    do
    {
      if ( *((_WORD *)v6 + v9 + 1) != aHttpSchemasMic_3[v9 + 1] )
        break;
      v9 += 2;
      if ( v9 == 63 )
      {
LABEL_15:
        NMR::CModelObject::getPartNumber(i[2], Src);
        *(_QWORD *)&v34 = 0;
        v35 = 0;
        v36 = 0;
        v12 = v53;
        v13 = Src;
        if ( *((_QWORD *)&v53 + 1) >= 8u )
          v13 = (void **)Src[0];
        if ( (unsigned __int64)v53 >= 8 )
        {
          v14 = v53 | 7;
          if ( ((unsigned __int64)v53 | 7) > 0x7FFFFFFFFFFFFFFELL )
            v14 = 0x7FFFFFFFFFFFFFFELL;
          if ( (unsigned __int64)(v14 + 1) > 0x7FFFFFFFFFFFFFFFLL )
            __scrt_throw_std_bad_array_new_length();
          _mm_lfence();
          *(_QWORD *)&v34 = std::_Allocate<16,std::_Default_allocate_traits,0>(2 * (v14 + 1));
          memcpy_0((void *)v34, v13, 2 * v12 + 2);
          v36 = v14;
        }
        else
        {
          v34 = *(_OWORD *)v13;
          v36 = 7;
        }
        v35 = v12;
        if ( !(unsigned __int8)NMR::fnStartsWithPathDelimiter(&v34) )
        {
          v15 = std::operator+<wchar_t>(&v47, a2, Src);
          if ( Src != (void **)v15 )
          {
            std::wstring::_Tidy_deallocate(Src);
            *(_OWORD *)Src = *(_OWORD *)v15;
            v53 = *(_OWORD *)(v15 + 16);
            *(_QWORD *)(v15 + 16) = 0;
            *(_QWORD *)(v15 + 24) = 7;
            *(_WORD *)v15 = 0;
          }
          if ( v48 >= 8 )
          {
            v16 = v47;
            if ( 2 * v48 + 2 >= 0x1000 )
            {
              v16 = (_BYTE *)*((_QWORD *)v47 - 1);
              if ( (unsigned __int64)(v47 - v16 - 8) > 0x1F )
                _invalid_parameter_noinfo_noreturn();
            }
            operator delete(v16);
          }
          LOWORD(v47) = 0;
        }
        v60 = 0;
        *(_QWORD *)&v37 = 0;
        v38 = 0;
        v39 = 0;
        v17 = v53;
        v18 = Src;
        if ( *((_QWORD *)&v53 + 1) >= 8u )
          v18 = (void **)Src[0];
        if ( (unsigned __int64)v53 >= 8 )
        {
          v19 = v53 | 7;
          if ( ((unsigned __int64)v53 | 7) > 0x7FFFFFFFFFFFFFFELL )
            v19 = 0x7FFFFFFFFFFFFFFELL;
          if ( (unsigned __int64)(v19 + 1) > 0x7FFFFFFFFFFFFFFFLL )
            __scrt_throw_std_bad_array_new_length();
          _mm_lfence();
          *(_QWORD *)&v37 = std::_Allocate<16,std::_Default_allocate_traits,0>(2 * (v19 + 1));
          memcpy_0((void *)v37, v18, 2 * v17 + 2);
          v39 = v19;
        }
        else
        {
          v37 = *(_OWORD *)v18;
          v39 = 7;
        }
        v38 = v17;
        NMR::CModel::findModelAttachment(a1[1], &v60, &v37);
        if ( !(_QWORD)v60 )
        {
          v59 = 0;
          *(_QWORD *)&v40 = 0;
          v41 = 0;
          v42 = 0;
          v20 = v53;
          v21 = Src;
          if ( *((_QWORD *)&v53 + 1) >= 8u )
            v21 = (void **)Src[0];
          if ( (unsigned __int64)v53 >= 8 )
          {
            v22 = v53 | 7;
            if ( ((unsigned __int64)v53 | 7) > 0x7FFFFFFFFFFFFFFELL )
              v22 = 0x7FFFFFFFFFFFFFFELL;
            if ( (unsigned __int64)(v22 + 1) > 0x7FFFFFFFFFFFFFFFLL )
              __scrt_throw_std_bad_array_new_length();
            _mm_lfence();
            *(_QWORD *)&v40 = std::_Allocate<16,std::_Default_allocate_traits,0>(2 * (v22 + 1));
            memcpy_0((void *)v40, v21, 2 * v20 + 2);
            v42 = v22;
          }
          else
          {
            v40 = *(_OWORD *)v21;
            v42 = 7;
          }
          v41 = v20;
          NMR::COpcPackageReader::createPart(a1[15], &v59, &v40);
          v58 = 0;
          NMR::COpcPackagePart::getImportStream(v59, &v58);
          v54 = 0;
          (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v58 + 48LL))(v58, &v54);
          if ( !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v54 + 32LL))(v54) )
          {
            v23 = NMR::CNMRException::CNMRException((NMR::CNMRException *)&v49, 4168);
            NMR::CModelReaderWarnings::addException(a1[11], v23, 2);
            v49 = &std::exception::`vftable';
            _std_exception_destroy_0(v50);
          }
          v46 = 0;
          if ( *((_QWORD *)&v54 + 1) )
            _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 8LL));
          v46 = v54;
          *(_QWORD *)&v43 = 0;
          v44 = 0;
          v45 = 0;
          v24 = v53;
          v25 = Src;
          if ( *((_QWORD *)&v53 + 1) >= 8u )
            v25 = (void **)Src[0];
          if ( (unsigned __int64)v53 >= 8 )
          {
            v26 = v53 | 7;
            if ( ((unsigned __int64)v53 | 7) > 0x7FFFFFFFFFFFFFFELL )
              v26 = 0x7FFFFFFFFFFFFFFELL;
            if ( (unsigned __int64)(v26 + 1) > 0x7FFFFFFFFFFFFFFFLL )
              __scrt_throw_std_bad_array_new_length();
            _mm_lfence();
            *(_QWORD *)&v43 = std::_Allocate<16,std::_Default_allocate_traits,0>(2 * (v26 + 1));
            memcpy_0((void *)v43, v25, 2 * v24 + 2);
            v45 = v26;
          }
          else
          {
            v43 = *(_OWORD *)v25;
            v45 = 7;
          }
          v44 = v24;
          (*(void (__fastcall **)(_QWORD *, __int128 *, __int128 *))(*a1 + 24LL))(a1, &v43, &v46);
          v27 = (volatile signed __int32 *)*((_QWORD *)&v54 + 1);
          if ( *((_QWORD *)&v54 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
              if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
            }
          }
          v28 = (volatile signed __int32 *)*((_QWORD *)&v58 + 1);
          if ( *((_QWORD *)&v58 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
              if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
            }
          }
          v29 = (volatile signed __int32 *)*((_QWORD *)&v59 + 1);
          if ( *((_QWORD *)&v59 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v59 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
              if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
            }
          }
        }
        v30 = (volatile signed __int32 *)*((_QWORD *)&v60 + 1);
        if ( *((_QWORD *)&v60 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v60 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
            if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
        if ( *((_QWORD *)&v53 + 1) >= 8u )
        {
          v31 = Src[0];
          if ( (unsigned __int64)(2LL * *((_QWORD *)&v53 + 1) + 2) >= 0x1000 )
          {
            v31 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v31 - 8) > 0x1F )
              _invalid_parameter_noinfo_noreturn();
          }
          operator delete(v31);
        }
        v7 = (char *)Block[0];
        v8 = v57;
        goto LABEL_81;
      }
    }
    while ( *((_WORD *)v6 + v9) == aHttpSchemasMic_3[v9] );
    v10 = Block;
    if ( v57 >= 8 )
      v10 = (void **)Block[0];
    v11 = 0;
    while ( *((_WORD *)v10 + v11) == aHttpSchemasOpe_0[v11] && *((_WORD *)v10 + v11 + 1) == aHttpSchemasOpe_0[v11 + 1] )
    {
      v11 += 2;
      if ( v11 == 80 )
        goto LABEL_15;
    }
LABEL_81:
    if ( v8 >= 8 )
    {
      v32 = v7;
      if ( 2 * v8 + 2 >= 0x1000 )
      {
        v7 = (char *)*((_QWORD *)v7 - 1);
        if ( (unsigned __int64)(v32 - v7 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v7);
    }
  }
  return std::list<std::shared_ptr<NMR::CPortableZIPWriterEntry>>::~list<std::shared_ptr<NMR::CPortableZIPWriterEntry>>(&v55);
}

```

## disassembly

```asm
0x180427440  mov     [rsp-8+arg_18], rbx
0x180427445  push    rbp
0x180427446  push    rsi
0x180427447  push    rdi
0x180427448  push    r12
0x18042744a  push    r13
0x18042744c  push    r14
0x18042744e  push    r15
0x180427450  lea     rbp, [rsp-0C0h]
0x180427458  sub     rsp, 1C0h
0x18042745f  mov     rax, cs:__security_cookie
0x180427466  xor     rax, rsp
0x180427469  mov     [rbp+0F0h+var_40], rax
0x180427470  mov     r12, rdx
0x180427473  mov     r15, rcx
0x180427476  test    r8, r8
0x180427479  jz      loc_180427B1D
0x18042747f  xorps   xmm0, xmm0
0x180427482  movups  [rbp+0F0h+var_A0], xmm0
0x180427486  lea     rdx, [rbp+0F0h+var_A0]
0x18042748a  mov     rcx, r8
0x18042748d  call    ?getRelationShips@COpcPackagePart@NMR@@QEAA?AV?$list@V?$shared_ptr@VCOpcPackageRelationship@NMR@@@std@@V?$allocator@V?$shared_ptr@VCOpcPackageRelationship@NMR@@@std@@@2@@std@@XZ; NMR::COpcPackagePart::getRelationShips(void)
0x180427492  nop
0x180427493  mov     rax, qword ptr [rbp+0F0h+var_A0]
0x180427497  mov     rbx, [rax]
0x18042749a  cmp     rbx, rax
0x18042749d  jz      loc_180427ACF
0x1804274a3  lea     rdi, aHttpSchemasMic_3; "http://schemas.microsoft.com/3dmanufact"...
0x1804274aa  lea     rsi, aHttpSchemasOpe_0; "http://schemas.openxmlformats.org/packa"...
0x1804274b1  xor     r13d, r13d
0x1804274b4  nop     dword ptr [rax+00h]
0x1804274b8  nop     dword ptr [rax+rax+00000000h]
0x1804274c0  lea     rdx, [rbp+0F0h+Block]
0x1804274c4  mov     rcx, [rbx+10h]
0x1804274c8  call    ?getType@COpcPackageRelationship@NMR@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NMR::COpcPackageRelationship::getType(void)
0x1804274cd  nop
0x1804274ce  lea     rdx, [rbp+0F0h+Block]
0x1804274d2  mov     r8, [rbp+0F0h+Block]
0x1804274d6  mov     r9, [rbp+0F0h+var_78]
0x1804274da  cmp     r9, 8
0x1804274de  cmovnb  rdx, r8
0x1804274e2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1804274e9  nop     dword ptr [rax+00000000h]
0x1804274f0  movzx   eax, word ptr [rdx+rcx*2+2]
0x1804274f5  cmp     ax, [rdi+rcx*2+2]
0x1804274fa  jnz     short loc_180427510
0x1804274fc  add     rcx, 2
0x180427500  cmp     rcx, 3Fh ; '?'
0x180427504  jz      short loc_180427548
0x180427506  movzx   eax, word ptr [rdx+rcx*2]
0x18042750a  cmp     ax, [rdi+rcx*2]
0x18042750e  jz      short loc_1804274F0
0x180427510  lea     rdx, [rbp+0F0h+Block]
0x180427514  cmp     r9, 8
0x180427518  cmovnb  rdx, r8
0x18042751c  mov     rax, r13
0x18042751f  nop
0x180427520  movzx   ecx, word ptr [rdx+rax*2]
0x180427524  cmp     cx, [rsi+rax*2]
0x180427528  jnz     loc_180427A88
0x18042752e  movzx   ecx, word ptr [rdx+rax*2+2]
0x180427533  cmp     cx, [rsi+rax*2+2]
0x180427538  jnz     loc_180427A88
0x18042753e  add     rax, 2
0x180427542  cmp     rax, 50h ; 'P'
0x180427546  jnz     short loc_180427520
0x180427548  lea     rdx, [rbp+0F0h+Src]
0x18042754c  mov     rcx, [rbx+10h]
0x180427550  call    ?getPartNumber@CModelObject@NMR@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NMR::CModelObject::getPartNumber(void)
0x180427555  nop
0x180427556  mov     qword ptr [rsp+1F0h+var_1C8], r13
0x18042755b  mov     [rsp+1F0h+var_1B8], r13
0x180427560  mov     [rsp+1F0h+var_1B0], r13
0x180427565  mov     rsi, qword ptr [rbp+0F0h+var_C0]
0x180427569  lea     r14, [rbp+0F0h+Src]
0x18042756d  cmp     qword ptr [rbp+0F0h+var_C0+8], 8
0x180427572  cmovnb  r14, [rbp+0F0h+Src]
0x180427577  cmp     rsi, 8
0x18042757b  jnb     short loc_180427591
0x18042757d  movups  xmm0, xmmword ptr [r14]
0x180427581  movups  [rsp+1F0h+var_1C8], xmm0
0x180427586  mov     [rsp+1F0h+var_1B0], 7
0x18042758f  jmp     short loc_1804275E8
0x180427591  mov     rdi, rsi
0x180427594  or      rdi, 7
0x180427598  mov     rax, 7FFFFFFFFFFFFFFEh
0x1804275a2  cmp     rdi, rax
0x1804275a5  cmova   rdi, rax
0x1804275a9  lea     rcx, [rdi+1]
0x1804275ad  mov     rax, 7FFFFFFFFFFFFFFFh
0x1804275b7  cmp     rcx, rax
0x1804275ba  ja      loc_180427B17
0x1804275c0  lfence
0x1804275c3  add     rcx, rcx
0x1804275c6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x1804275cb  mov     qword ptr [rsp+1F0h+var_1C8], rax
0x1804275d0  lea     r8, ds:2[rsi*2]; Size
0x1804275d8  mov     rdx, r14; Src
0x1804275db  mov     rcx, rax; void *
0x1804275de  call    memcpy_0
0x1804275e3  mov     [rsp+1F0h+var_1B0], rdi
0x1804275e8  mov     [rsp+1F0h+var_1B8], rsi
0x1804275ed  lea     rcx, [rsp+1F0h+var_1C8]
0x1804275f2  call    ?fnStartsWithPathDelimiter@NMR@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NMR::fnStartsWithPathDelimiter(std::wstring)
0x1804275f7  test    al, al
0x1804275f9  jnz     loc_180427688
0x1804275ff  lea     r8, [rbp+0F0h+Src]; void *
0x180427603  mov     rdx, r12; Src
0x180427606  lea     rcx, [rbp+0F0h+var_130]; void *
0x18042760a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@0@Z; std::operator+<wchar_t>(std::wstring const &,std::wstring const &)
0x18042760f  mov     rdi, rax
0x180427612  lea     rax, [rbp+0F0h+Src]
0x180427616  cmp     rax, rdi
0x180427619  jz      short loc_180427643
0x18042761b  lea     rcx, [rbp+0F0h+Src]
0x18042761f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180427624  movups  xmm0, xmmword ptr [rdi]
0x180427627  movups  xmmword ptr [rbp+0F0h+Src], xmm0
0x18042762b  movups  xmm1, xmmword ptr [rdi+10h]
0x18042762f  movups  [rbp+0F0h+var_C0], xmm1
0x180427633  mov     [rdi+10h], r13
0x180427637  mov     qword ptr [rdi+18h], 7
0x18042763f  mov     [rdi], r13w
0x180427643  mov     rdx, [rbp+0F0h+var_118]
0x180427647  cmp     rdx, 8
0x18042764b  jb      short loc_180427683
0x18042764d  lea     rdx, ds:2[rdx*2]
0x180427655  mov     rcx, [rbp+0F0h+var_130]
0x180427659  mov     rax, rcx
0x18042765c  cmp     rdx, 1000h
0x180427663  jb      short loc_18042767E
0x180427665  add     rdx, 27h ; '''
0x180427669  mov     rcx, [rcx-8]; Block
0x18042766d  sub     rax, rcx
0x180427670  add     rax, 0FFFFFFFFFFFFFFF8h
0x180427674  cmp     rax, 1Fh
0x180427678  ja      loc_180427B02
0x18042767e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180427683  mov     word ptr [rbp+0F0h+var_130], r13w
0x180427688  xorps   xmm0, xmm0
0x18042768b  movups  [rbp+0F0h+var_50], xmm0
0x180427692  mov     qword ptr [rsp+1F0h+var_1A8], r13
0x180427697  mov     [rsp+1F0h+var_198], r13
0x18042769c  mov     [rsp+1F0h+var_190], r13
0x1804276a1  mov     rsi, qword ptr [rbp+0F0h+var_C0]
0x1804276a5  lea     r14, [rbp+0F0h+Src]
0x1804276a9  cmp     qword ptr [rbp+0F0h+var_C0+8], 8
0x1804276ae  cmovnb  r14, [rbp+0F0h+Src]
0x1804276b3  cmp     rsi, 8
0x1804276b7  jnb     short loc_1804276CD
0x1804276b9  movups  xmm0, xmmword ptr [r14]
0x1804276bd  movups  [rsp+1F0h+var_1A8], xmm0
0x1804276c2  mov     [rsp+1F0h+var_190], 7
0x1804276cb  jmp     short loc_180427724
0x1804276cd  mov     rdi, rsi
0x1804276d0  or      rdi, 7
0x1804276d4  mov     rax, 7FFFFFFFFFFFFFFEh
0x1804276de  cmp     rdi, rax
0x1804276e1  cmova   rdi, rax
0x1804276e5  lea     rcx, [rdi+1]
0x1804276e9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1804276f3  cmp     rcx, rax
0x1804276f6  ja      loc_180427B48
0x1804276fc  lfence
0x1804276ff  add     rcx, rcx
0x180427702  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x180427707  mov     qword ptr [rsp+1F0h+var_1A8], rax
0x18042770c  lea     r8, ds:2[rsi*2]; Size
0x180427714  mov     rdx, r14; Src
0x180427717  mov     rcx, rax; void *
0x18042771a  call    memcpy_0
0x18042771f  mov     [rsp+1F0h+var_190], rdi
0x180427724  mov     [rsp+1F0h+var_198], rsi
0x180427729  lea     r8, [rsp+1F0h+var_1A8]
0x18042772e  lea     rdx, [rbp+0F0h+var_50]
0x180427735  mov     rcx, [r15+8]
0x180427739  call    ?findModelAttachment@CModel@NMR@@QEAA?AV?$shared_ptr@VCModelAttachment@NMR@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; NMR::CModel::findModelAttachment(std::wstring)
0x18042773e  nop
0x18042773f  cmp     qword ptr [rbp+0F0h+var_50], 0
0x180427747  jnz     loc_1804279F6
0x18042774d  xorps   xmm0, xmm0
0x180427750  movups  [rbp+0F0h+var_60], xmm0
0x180427757  mov     qword ptr [rsp+1F0h+var_188], r13
0x18042775c  mov     [rsp+1F0h+var_178], r13
0x180427761  mov     [rbp+0F0h+var_170], r13
0x180427765  mov     rsi, qword ptr [rbp+0F0h+var_C0]
0x180427769  lea     r14, [rbp+0F0h+Src]
0x18042776d  cmp     qword ptr [rbp+0F0h+var_C0+8], 8
0x180427772  cmovnb  r14, [rbp+0F0h+Src]
0x180427777  cmp     rsi, 8
0x18042777b  jnb     short loc_180427790
0x18042777d  movups  xmm0, xmmword ptr [r14]
0x180427781  movups  [rsp+1F0h+var_188], xmm0
0x180427786  mov     [rbp+0F0h+var_170], 7
0x18042778e  jmp     short loc_1804277E6
0x180427790  mov     rdi, rsi
0x180427793  or      rdi, 7
0x180427797  mov     rax, 7FFFFFFFFFFFFFFEh
0x1804277a1  cmp     rdi, rax
0x1804277a4  cmova   rdi, rax
0x1804277a8  lea     rcx, [rdi+1]
0x1804277ac  mov     rax, 7FFFFFFFFFFFFFFFh
0x1804277b6  cmp     rcx, rax
0x1804277b9  ja      loc_180427B42
0x1804277bf  lfence
0x1804277c2  add     rcx, rcx
0x1804277c5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x1804277ca  mov     qword ptr [rsp+1F0h+var_188], rax
0x1804277cf  lea     r8, ds:2[rsi*2]; Size
0x1804277d7  mov     rdx, r14; Src
0x1804277da  mov     rcx, rax; void *
0x1804277dd  call    memcpy_0
0x1804277e2  mov     [rbp+0F0h+var_170], rdi
0x1804277e6  mov     [rsp+1F0h+var_178], rsi
0x1804277eb  lea     r8, [rsp+1F0h+var_188]
0x1804277f0  lea     rdx, [rbp+0F0h+var_60]
0x1804277f7  mov     rcx, [r15+78h]
0x1804277fb  call    ?createPart@COpcPackageReader@NMR@@QEAA?AV?$shared_ptr@VCOpcPackagePart@NMR@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; NMR::COpcPackageReader::createPart(std::wstring)
0x180427800  nop
0x180427801  xorps   xmm0, xmm0
0x180427804  movups  [rbp+0F0h+var_70], xmm0
0x18042780b  lea     rdx, [rbp+0F0h+var_70]
0x180427812  mov     rcx, qword ptr [rbp+0F0h+var_60]
0x180427819  call    ?getImportStream@COpcPackagePart@NMR@@QEAA?AV?$shared_ptr@VCImportStream@NMR@@@std@@XZ; NMR::COpcPackagePart::getImportStream(void)
0x18042781e  nop
0x18042781f  xorps   xmm0, xmm0
0x180427822  movups  [rbp+0F0h+var_B0], xmm0
0x180427826  mov     rcx, qword ptr [rbp+0F0h+var_70]
0x18042782d  mov     rax, [rcx]
0x180427830  lea     rdx, [rbp+0F0h+var_B0]
0x180427834  call    qword ptr [rax+30h]
0x180427837  nop
0x180427838  mov     rcx, qword ptr [rbp+0F0h+var_B0]
0x18042783c  mov     rax, [rcx]
0x18042783f  call    qword ptr [rax+20h]
0x180427842  test    rax, rax
0x180427845  jnz     short loc_18042787D
0x180427847  mov     edx, 1048h; int
0x18042784c  lea     rcx, [rbp+0F0h+var_110]; this
0x180427850  call    ??0CNMRException@NMR@@QEAA@H@Z; NMR::CNMRException::CNMRException(int)
0x180427855  nop
0x180427856  mov     r8d, 2
0x18042785c  mov     rdx, rax
0x18042785f  mov     rcx, [r15+58h]
0x180427863  call    ?addException@CModelReaderWarnings@NMR@@QEAAXAEBVCNMRException@2@W4_eModelReaderWarningLevel@2@@Z; NMR::CModelReaderWarnings::addException(NMR::CNMRException const &,NMR::_eModelReaderWarningLevel)
0x180427868  nop
0x180427869  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180427870  mov     [rbp+0F0h+var_110], rax
0x180427874  lea     rcx, [rbp+0F0h+var_108]
0x180427878  call    __std_exception_destroy_0
0x18042787d  lea     rax, [rbp+0F0h+var_140]
0x180427881  mov     [rsp+1F0h+var_1D0], rax
0x180427886  xorps   xmm0, xmm0
0x180427889  movdqa  [rbp+0F0h+var_140], xmm0
0x18042788e  mov     rax, qword ptr [rbp+0F0h+var_B0+8]
0x180427892  test    rax, rax
0x180427895  jz      short loc_18042789B
0x180427897  lock inc dword ptr [rax+8]
0x18042789b  movaps  xmm0, [rbp+0F0h+var_B0]
0x18042789f  movdqa  [rbp+0F0h+var_140], xmm0
0x1804278a4  mov     qword ptr [rbp+0F0h+var_168], r13
0x1804278a8  mov     [rbp+0F0h+var_158], r13
0x1804278ac  mov     [rbp+0F0h+var_150], r13
0x1804278b0  mov     rsi, qword ptr [rbp+0F0h+var_C0]
0x1804278b4  lea     r14, [rbp+0F0h+Src]
0x1804278b8  cmp     qword ptr [rbp+0F0h+var_C0+8], 8
0x1804278bd  cmovnb  r14, [rbp+0F0h+Src]
0x1804278c2  cmp     rsi, 8
0x1804278c6  jnb     short loc_1804278DA
0x1804278c8  movups  xmm0, xmmword ptr [r14]
0x1804278cc  movups  [rbp+0F0h+var_168], xmm0
0x1804278d0  mov     [rbp+0F0h+var_150], 7
0x1804278d8  jmp     short loc_18042792F
0x1804278da  mov     rdi, rsi
0x1804278dd  or      rdi, 7
0x1804278e1  mov     rax, 7FFFFFFFFFFFFFFEh
0x1804278eb  cmp     rdi, rax
0x1804278ee  cmova   rdi, rax
0x1804278f2  lea     rcx, [rdi+1]
0x1804278f6  mov     rax, 7FFFFFFFFFFFFFFFh
0x180427900  cmp     rcx, rax
0x180427903  ja      loc_180427B3C
0x180427909  lfence
0x18042790c  add     rcx, rcx
0x18042790f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x180427914  mov     qword ptr [rbp+0F0h+var_168], rax
0x180427918  lea     r8, ds:2[rsi*2]; Size
0x180427920  mov     rdx, r14; Src
0x180427923  mov     rcx, rax; void *
0x180427926  call    memcpy_0
0x18042792b  mov     [rbp+0F0h+var_150], rdi
0x18042792f  mov     [rbp+0F0h+var_158], rsi
0x180427933  mov     rax, [r15]
0x180427936  lea     r8, [rbp+0F0h+var_140]
0x18042793a  lea     rdx, [rbp+0F0h+var_168]
0x18042793e  mov     rcx, r15
0x180427941  call    qword ptr [rax+18h]
0x180427944  nop
0x180427945  mov     rdi, qword ptr [rbp+0F0h+var_B0+8]
0x180427949  test    rdi, rdi
  ... truncated ...
```
