# ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000572c`
- end: `0x180006076`
- name: `?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `2378`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180002450`

## callees

- `0x180001f68`
- `0x180002238`
- `0x180003988`
- `0x180005538`
- `0x18000572c`
- `0x180007700`
- `0x180007a90`
- `0x180007bd4`
- `0x18000bb08`
- `0x18000be9c`
- `0x18000bfbc`
- `0x180024220`
- `0x1800245e0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005b2f`
- `KERNEL32!GetModuleHandleW` at `0x180005b2f`
- `KERNEL32!GetModuleFileNameW` at `0x1800058d7`
- `KERNEL32!GetModuleFileNameW` at `0x1800058d7`

## string_xrefs

- `0x180005f07`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResource(
        ATL::CAtlModule *this,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v4; // r14d
  unsigned int Error; // esi
  int v6; // ebx
  int v7; // ecx
  __int64 v8; // rdi
  void *v9; // rcx
  void *v10; // rax
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  int v14; // ebx
  int v15; // ecx
  __int64 v16; // rdi
  void *v17; // rcx
  void *v18; // rax
  int v19; // ebx
  int v20; // eax
  __int64 v21; // rdi
  void *v22; // rcx
  void *v23; // rax
  WCHAR *v24; // r8
  unsigned __int16 *v25; // rax
  unsigned int v26; // ecx
  __int64 v27; // r9
  __int64 v28; // rdx
  unsigned __int16 *v29; // r8
  unsigned __int16 *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  size_t v33; // r8
  unsigned __int64 v34; // rax
  int v35; // eax
  unsigned int v36; // ebx
  int v37; // edi
  int v38; // eax
  __int64 v39; // rsi
  void *v40; // rcx
  void *v41; // rax
  int v42; // edi
  int v43; // eax
  __int64 v44; // rbx
  void *v45; // rcx
  void *v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // r8
  int v49; // ebx
  int v50; // eax
  __int64 v51; // rdi
  void *v52; // rcx
  void *v53; // rax
  unsigned int v54; // eax
  int v55; // ebx
  int v56; // eax
  __int64 v57; // rdi
  void *v58; // rcx
  void *v59; // rax
  void **Block; // [rsp+38h] [rbp-D0h] BYREF
  void *Block_8[2]; // [rsp+40h] [rbp-C8h] BYREF
  int v62; // [rsp+50h] [rbp-B8h]
  __int64 v63; // [rsp+54h] [rbp-B4h]
  int v64; // [rsp+5Ch] [rbp-ACh]
  WCHAR Filename[264]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 v66; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v67[1054]; // [rsp+27Ah] [rbp+172h] BYREF
  unsigned __int16 Src[520]; // [rsp+698h] [rbp+590h] BYREF

  v4 = a3;
  v63 = 0;
  v64 = 0;
  Block = &ATL::CRegObject::`vftable';
  *(_OWORD *)Block_8 = 0;
  v62 = 0;
  Error = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***, __int64, struct ATL::_ATL_REGMAP_ENTRY *))(*(_QWORD *)ATL::_pAtlModule + 40LL))(
            ATL::_pAtlModule,
            &Block,
            a3,
            a4);
  if ( (Error & 0x80000000) != 0 )
  {
    Block = &ATL::CRegObject::`vftable';
    v6 = 0;
    v7 = v62;
    if ( v62 > 0 )
    {
      v8 = 0;
      do
      {
        if ( v8 < 0 || v6 >= v7 || (operator delete(*(void **)((char *)Block_8[0] + v8)), v6 >= v62) )
          ATL::AtlThrowImpl(-2147483637);
        operator delete(*(void **)((char *)Block_8[1] + v8));
        ++v6;
        v8 += 8;
        v7 = v62;
      }
      while ( v6 < v62 );
    }
    if ( Block_8[0] )
    {
      free(Block_8[0]);
      Block_8[0] = 0;
    }
    if ( Block_8[1] )
    {
      free(Block_8[1]);
      Block_8[1] = 0;
    }
    v62 = 0;
    _mm_lfence();
    v9 = Block_8[0];
    if ( Block_8[0] )
    {
      free(Block_8[0]);
      v9 = 0;
      Block_8[0] = 0;
    }
    v10 = Block_8[1];
    if ( Block_8[1] )
    {
      free(Block_8[1]);
      v10 = 0;
      Block_8[1] = 0;
      v9 = Block_8[0];
    }
    v62 = 0;
    if ( v9 )
    {
      free(v9);
      Block_8[0] = 0;
      v10 = Block_8[1];
    }
    if ( v10 )
      free(v10);
    return Error;
  }
  v12 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
    Block = &ATL::CRegObject::`vftable';
    v14 = 0;
    v15 = v62;
    if ( v62 > 0 )
    {
      v16 = 0;
      do
      {
        if ( v16 < 0 || v14 >= v15 || (operator delete(*(void **)((char *)Block_8[0] + v16)), v14 >= v62) )
          ATL::AtlThrowImpl(-2147483637);
        operator delete(*(void **)((char *)Block_8[1] + v16));
        ++v14;
        v16 += 8;
        v15 = v62;
      }
      while ( v14 < v62 );
    }
    v17 = Block_8[0];
    if ( Block_8[0] )
    {
      free(Block_8[0]);
      v17 = 0;
      Block_8[0] = 0;
    }
    v18 = Block_8[1];
    if ( Block_8[1] )
    {
      free(Block_8[1]);
      v18 = 0;
      Block_8[1] = 0;
      v17 = Block_8[0];
    }
    v62 = 0;
    if ( v17 )
    {
      free(v17);
      v17 = 0;
      Block_8[0] = 0;
      v18 = Block_8[1];
    }
    if ( v18 )
    {
      free(v18);
      v18 = 0;
      Block_8[1] = 0;
      v17 = Block_8[0];
    }
    v62 = 0;
    if ( v17 )
    {
      free(v17);
      Block_8[0] = 0;
      v18 = Block_8[1];
    }
    if ( v18 )
      free(v18);
    return Error;
  }
  if ( ModuleFileNameW == 260 )
  {
    Block = &ATL::CRegObject::`vftable';
    v19 = 0;
    v20 = v62;
    if ( v62 > 0 )
    {
      v21 = 0;
      do
      {
        if ( v21 < 0 || v19 >= v20 || (operator delete(*(void **)((char *)Block_8[0] + v21)), v19 >= v62) )
          ATL::AtlThrowImpl(-2147483637);
        operator delete(*(void **)((char *)Block_8[1] + v21));
        ++v19;
        v21 += 8;
        v20 = v62;
      }
      while ( v19 < v62 );
    }
    v22 = Block_8[0];
    if ( Block_8[0] )
    {
      free(Block_8[0]);
      v22 = 0;
      Block_8[0] = 0;
    }
    v23 = Block_8[1];
    if ( Block_8[1] )
    {
      free(Block_8[1]);
      v23 = 0;
      Block_8[1] = 0;
      v22 = Block_8[0];
    }
    v62 = 0;
    if ( v22 )
    {
      free(v22);
      v22 = 0;
      Block_8[0] = 0;
      v23 = Block_8[1];
    }
    if ( v23 )
    {
      free(v23);
      v23 = 0;
      Block_8[1] = 0;
      v22 = Block_8[0];
    }
    v62 = 0;
    if ( v22 )
    {
      free(v22);
      Block_8[0] = 0;
      v23 = Block_8[1];
    }
    if ( v23 )
      free(v23);
    return 2147942522LL;
  }
  v24 = Filename;
  v25 = Src;
  v26 = 0;
  v27 = 519;
  do
  {
    v28 = *v24;
    if ( !(_WORD)v28 )
      break;
    *v25++ = v28;
    if ( (_WORD)v28 == 39 && ++v26 < 0x207 )
      *v25++ = 39;
    ++v24;
    ++v26;
  }
  while ( v26 < 0x207 );
  *v25 = 0;
  if ( !v12 || v12 == GetModuleHandleW(0) )
  {
    v66 = 34;
    v30 = Src;
    v31 = -1;
    v32 = -1;
    do
      ++v32;
    while ( Src[v32] );
    v33 = 2LL * ((int)v32 + 1);
    if ( v33 )
    {
      if ( v33 > 0x416 )
      {
        memset(v67, 0, 0x416u);
        *errno() = 34;
        invalid_parameter_noinfo();
        Block = &ATL::CRegObject::`vftable';
        v42 = 0;
        v43 = v62;
        if ( v62 > 0 )
        {
          v44 = 0;
          do
          {
            if ( v44 < 0 || v42 >= v43 || (operator delete(*(void **)((char *)Block_8[0] + v44)), v42 >= v62) )
              ATL::AtlThrowImpl(-2147483637);
            operator delete(*(void **)((char *)Block_8[1] + v44));
            ++v42;
            v44 += 8;
            v43 = v62;
          }
          while ( v42 < v62 );
        }
        v45 = Block_8[0];
        if ( Block_8[0] )
        {
          free(Block_8[0]);
          v45 = 0;
          Block_8[0] = 0;
        }
        v46 = Block_8[1];
        if ( Block_8[1] )
        {
          free(Block_8[1]);
          v46 = 0;
          Block_8[1] = 0;
          v45 = Block_8[0];
        }
        v62 = 0;
        if ( v45 )
        {
          free(v45);
          v45 = 0;
          Block_8[0] = 0;
          v46 = Block_8[1];
        }
        if ( v46 )
        {
          free(v46);
          v46 = 0;
          Block_8[1] = 0;
          v45 = Block_8[0];
        }
        v62 = 0;
        if ( v45 )
        {
          free(v45);
          Block_8[0] = 0;
          v46 = Block_8[1];
        }
        if ( v46 )
          free(v46);
        return 2147500037LL;
      }
      memmove(v67, Src, v33);
    }
    do
      ++v31;
    while ( *(_WORD *)&v67[2 * v31 - 2] );
    *(_WORD *)&v67[2 * (int)v31 - 2] = 34;
    v34 = 2LL * (int)v31 + 2;
    if ( v34 >= 0x418 )
      _report_rangecheckfailure(v30, v28, v33, v27);
    *(_WORD *)&v67[v34 - 2] = 0;
    v29 = &v66;
  }
  else
  {
    v29 = Src;
  }
  v35 = -ATL::CExpansionVector::Add((ATL::CExpansionVector *)Block_8, L"Module", v29);
  v36 = v35 == 0 ? 0x8007000E : 0;
  if ( v35 )
  {
    v47 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)Block_8, L"Module_Raw", Src);
    Error = v47 == 0 ? 0x8007000E : 0;
    if ( v47 )
    {
      if ( v4 )
        v54 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&Block, Filename, v48, L"REGISTRY", 1);
      else
        v54 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&Block, Filename, v48, L"REGISTRY", 0);
      Error = v54;
      Block = &ATL::CRegObject::`vftable';
      v55 = 0;
      v56 = v62;
      if ( v62 > 0 )
      {
        v57 = 0;
        do
        {
          if ( v57 < 0 || v55 >= v56 || (operator delete(*(void **)((char *)Block_8[0] + v57)), v55 >= v62) )
            ATL::AtlThrowImpl(-2147483637);
          operator delete(*(void **)((char *)Block_8[1] + v57));
          ++v55;
          v57 += 8;
          v56 = v62;
        }
        while ( v55 < v62 );
      }
      v58 = Block_8[0];
      if ( Block_8[0] )
      {
        free(Block_8[0]);
        v58 = 0;
        Block_8[0] = 0;
      }
      v59 = Block_8[1];
      if ( Block_8[1] )
      {
        free(Block_8[1]);
        v59 = 0;
        Block_8[1] = 0;
        v58 = Block_8[0];
      }
      v62 = 0;
      if ( v58 )
      {
        free(v58);
        v58 = 0;
        Block_8[0] = 0;
        v59 = Block_8[1];
      }
      if ( v59 )
      {
        free(v59);
        v59 = 0;
        Block_8[1] = 0;
        v58 = Block_8[0];
      }
      v62 = 0;
      if ( v58 )
      {
        free(v58);
        Block_8[0] = 0;
        v59 = Block_8[1];
      }
      if ( v59 )
        free(v59);
    }
    else
    {
      Block = &ATL::CRegObject::`vftable';
      v49 = 0;
      v50 = v62;
      if ( v62 > 0 )
      {
        v51 = 0;
        do
        {
          if ( v51 < 0 || v49 >= v50 || (operator delete(*(void **)((char *)Block_8[0] + v51)), v49 >= v62) )
            ATL::AtlThrowImpl(-2147483637);
          operator delete(*(void **)((char *)Block_8[1] + v51));
          ++v49;
          v51 += 8;
          v50 = v62;
        }
        while ( v49 < v62 );
      }
      if ( Block_8[0] )
      {
        free(Block_8[0]);
        Block_8[0] = 0;
      }
      if ( Block_8[1] )
      {
        free(Block_8[1]);
        Block_8[1] = 0;
      }
      v62 = 0;
      _mm_lfence();
      v52 = Block_8[0];
      if ( Block_8[0] )
      {
        free(Block_8[0]);
        v52 = 0;
        Block_8[0] = 0;
      }
      v53 = Block_8[1];
      if ( Block_8[1] )
      {
        free(Block_8[1]);
        v53 = 0;
        Block_8[1] = 0;
        v52 = Block_8[0];
      }
      v62 = 0;
      if ( v52 )
      {
        free(v52);
        Block_8[0] = 0;
        v53 = Block_8[1];
      }
      if ( v53 )
        free(v53);
    }
    return Error;
  }
  Block = &ATL::CRegObject::`vftable';
  v37 = 0;
  v38 = v62;
  if ( v62 > 0 )
  {
    v39 = 0;
    do
    {
      if ( v39 < 0 || v37 >= v38 || (operator delete(*(void **)((char *)Block_8[0] + v39)), v37 >= v62) )
        ATL::AtlThrowImpl(-2147483637);
      operator delete(*(void **)((char *)Block_8[1] + v39));
      ++v37;
      v39 += 8;
      v38 = v62;
    }
    while ( v37 < v62 );
  }
  if ( Block_8[0] )
  {
    free(Block_8[0]);
    Block_8[0] = 0;
  }
  if ( Block_8[1] )
  {
    free(Block_8[1]);
    Block_8[1] = 0;
  }
  v62 = 0;
  _mm_lfence();
  v40 = Block_8[0];
  if ( Block_8[0] )
  {
    free(Block_8[0]);
    v40 = 0;
    Block_8[0] = 0;
  }
  v41 = Block_8[1];
  if ( Block_8[1] )
  {
    free(Block_8[1]);
    v41 = 0;
    Block_8[1] = 0;
    v40 = Block_8[0];
  }
  v62 = 0;
  if ( v40 )
  {
    free(v40);
    Block_8[0] = 0;
    v41 = Block_8[1];
  }
  if ( v41 )
    free(v41);
  return v36;
}

```

## disassembly

```asm
0x18000572c  mov     rax, rsp
0x18000572f  mov     [rax+8], rbx
0x180005733  mov     [rax+10h], rsi
0x180005737  mov     [rax+18h], rdi
0x18000573b  mov     [rax+20h], r12
0x18000573f  push    rbp
0x180005740  push    r14
0x180005742  push    r15
0x180005744  lea     rbp, [rax-9C8h]
0x18000574b  sub     rsp, 0AB0h
0x180005752  mov     rax, cs:__security_cookie
0x180005759  xor     rax, rsp
0x18000575c  mov     [rbp+9C0h+var_20], rax
0x180005763  mov     r14d, r8d
0x180005766  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000576d  xor     r15d, r15d
0x180005770  mov     [rsp+0AC0h+var_A74], r15
0x180005775  mov     [rsp+0AC0h+var_A6C], r15d
0x18000577a  lea     r12, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005781  mov     [rsp+0AC0h+Block], r12
0x180005786  xorps   xmm0, xmm0
0x180005789  movdqu  xmmword ptr [rsp+0AC0h+Block+8], xmm0
0x18000578f  mov     [rsp+0AC0h+var_A78], r15d
0x180005794  mov     rax, [rcx]
0x180005797  lea     rdx, [rsp+0AC0h+Block]
0x18000579c  call    qword ptr [rax+28h]
0x18000579f  mov     esi, eax
0x1800057a1  test    eax, eax
0x1800057a3  jns     loc_1800058C0
0x1800057a9  mov     [rsp+0AC0h+Block], r12
0x1800057ae  mov     ebx, r15d
0x1800057b1  mov     ecx, [rsp+0AC0h+var_A78]
0x1800057b5  test    ecx, ecx
0x1800057b7  jle     short loc_180005801
0x1800057b9  mov     edi, r15d
0x1800057bc  test    rdi, rdi
0x1800057bf  js      loc_180006034
0x1800057c5  cmp     ebx, ecx
0x1800057c7  jge     loc_180006034
0x1800057cd  mov     rax, [rsp+0AC0h+Block+8]
0x1800057d2  mov     rcx, [rax+rdi]; Block
0x1800057d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800057db  cmp     ebx, [rsp+0AC0h+var_A78]
0x1800057df  jge     loc_180006034
0x1800057e5  mov     rax, [rsp+0AC0h+var_A80]
0x1800057ea  mov     rcx, [rax+rdi]; Block
0x1800057ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800057f3  inc     ebx
0x1800057f5  add     rdi, 8
0x1800057f9  mov     ecx, [rsp+0AC0h+var_A78]
0x1800057fd  cmp     ebx, ecx
0x1800057ff  jl      short loc_1800057BC
0x180005801  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x180005806  test    rcx, rcx
0x180005809  jz      short loc_180005815
0x18000580b  call    free
0x180005810  mov     [rsp+0AC0h+Block+8], r15
0x180005815  mov     rcx, [rsp+0AC0h+var_A80]; Block
0x18000581a  test    rcx, rcx
0x18000581d  jz      short loc_180005829
0x18000581f  call    free
0x180005824  mov     [rsp+0AC0h+var_A80], r15
0x180005829  mov     [rsp+0AC0h+var_A78], r15d
0x18000582e  lfence
0x180005831  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x180005836  test    rcx, rcx
0x180005839  jz      short loc_180005848
0x18000583b  call    free
0x180005840  mov     rcx, r15
0x180005843  mov     [rsp+0AC0h+Block+8], rcx
0x180005848  mov     rax, [rsp+0AC0h+var_A80]
0x18000584d  test    rax, rax
0x180005850  jz      short loc_180005867
0x180005852  mov     rcx, rax; Block
0x180005855  call    free
0x18000585a  mov     rax, r15
0x18000585d  mov     [rsp+0AC0h+var_A80], rax
0x180005862  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x180005867  mov     [rsp+0AC0h+var_A78], r15d
0x18000586c  test    rcx, rcx
0x18000586f  jz      short loc_180005880
0x180005871  call    free
0x180005876  mov     [rsp+0AC0h+Block+8], r15
0x18000587b  mov     rax, [rsp+0AC0h+var_A80]
0x180005880  test    rax, rax
0x180005883  jz      short loc_18000588E
0x180005885  mov     rcx, rax; Block
0x180005888  call    free
0x18000588d  nop
0x18000588e  mov     eax, esi
0x180005890  mov     rcx, [rbp+9C0h+var_20]
0x180005897  xor     rcx, rsp; StackCookie
0x18000589a  call    __security_check_cookie
0x18000589f  lea     r11, [rsp+0AC0h+var_10]
0x1800058a7  mov     rbx, [r11+20h]
0x1800058ab  mov     rsi, [r11+28h]
0x1800058af  mov     rdi, [r11+30h]
0x1800058b3  mov     r12, [r11+38h]
0x1800058b7  mov     rsp, r11
0x1800058ba  pop     r15
0x1800058bc  pop     r14
0x1800058be  pop     rbp
0x1800058bf  retn
0x1800058c0  mov     rbx, cs:hModule
0x1800058c7  mov     edi, 104h
0x1800058cc  mov     r8d, edi; nSize
0x1800058cf  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x1800058d4  mov     rcx, rbx; hModule
0x1800058d7  call    cs:__imp_GetModuleFileNameW
0x1800058dd  test    eax, eax
0x1800058df  jnz     loc_1800059DC
0x1800058e5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800058ea  mov     esi, eax
0x1800058ec  mov     [rsp+0AC0h+Block], r12
0x1800058f1  mov     ebx, r15d
0x1800058f4  mov     ecx, [rsp+0AC0h+var_A78]
0x1800058f8  test    ecx, ecx
0x1800058fa  jle     short loc_180005944
0x1800058fc  mov     rdi, r15
0x1800058ff  test    rdi, rdi
0x180005902  js      loc_18000603F
0x180005908  cmp     ebx, ecx
0x18000590a  jge     loc_18000603F
0x180005910  mov     rax, [rsp+0AC0h+Block+8]
0x180005915  mov     rcx, [rdi+rax]; Block
0x180005919  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000591e  cmp     ebx, [rsp+0AC0h+var_A78]
0x180005922  jge     loc_18000603F
0x180005928  mov     rax, [rsp+0AC0h+var_A80]
0x18000592d  mov     rcx, [rax+rdi]; Block
0x180005931  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005936  inc     ebx
0x180005938  add     rdi, 8
0x18000593c  mov     ecx, [rsp+0AC0h+var_A78]
0x180005940  cmp     ebx, ecx
0x180005942  jl      short loc_1800058FF
0x180005944  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x180005949  test    rcx, rcx
0x18000594c  jz      short loc_18000595B
0x18000594e  call    free
0x180005953  mov     rcx, r15
0x180005956  mov     [rsp+0AC0h+Block+8], rcx
0x18000595b  mov     rax, [rsp+0AC0h+var_A80]
0x180005960  test    rax, rax
0x180005963  jz      short loc_18000597A
0x180005965  mov     rcx, rax; Block
0x180005968  call    free
0x18000596d  mov     rax, r15
0x180005970  mov     [rsp+0AC0h+var_A80], rax
0x180005975  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x18000597a  mov     [rsp+0AC0h+var_A78], r15d
0x18000597f  test    rcx, rcx
0x180005982  jz      short loc_180005996
0x180005984  call    free
0x180005989  mov     rcx, r15
0x18000598c  mov     [rsp+0AC0h+Block+8], rcx
0x180005991  mov     rax, [rsp+0AC0h+var_A80]
0x180005996  test    rax, rax
0x180005999  jz      short loc_1800059B0
0x18000599b  mov     rcx, rax; Block
0x18000599e  call    free
0x1800059a3  mov     rax, r15
0x1800059a6  mov     [rsp+0AC0h+var_A80], rax
0x1800059ab  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x1800059b0  mov     [rsp+0AC0h+var_A78], r15d
0x1800059b5  test    rcx, rcx
0x1800059b8  jz      short loc_1800059C9
0x1800059ba  call    free
0x1800059bf  mov     [rsp+0AC0h+Block+8], r15
0x1800059c4  mov     rax, [rsp+0AC0h+var_A80]
0x1800059c9  test    rax, rax
0x1800059cc  jz      short loc_1800059D7
0x1800059ce  mov     rcx, rax; Block
0x1800059d1  call    free
0x1800059d6  nop
0x1800059d7  jmp     loc_18000588E
0x1800059dc  cmp     eax, edi
0x1800059de  jnz     loc_180005AD9
0x1800059e4  mov     [rsp+0AC0h+Block], r12
0x1800059e9  mov     ebx, r15d
0x1800059ec  mov     eax, [rsp+0AC0h+var_A78]
0x1800059f0  test    eax, eax
0x1800059f2  jle     short loc_180005A3C
0x1800059f4  mov     rdi, r15
0x1800059f7  test    rdi, rdi
0x1800059fa  js      loc_18000604A
0x180005a00  cmp     ebx, eax
0x180005a02  jge     loc_18000604A
0x180005a08  mov     rax, [rsp+0AC0h+Block+8]
0x180005a0d  mov     rcx, [rdi+rax]; Block
0x180005a11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005a16  cmp     ebx, [rsp+0AC0h+var_A78]
0x180005a1a  jge     loc_18000604A
0x180005a20  mov     rax, [rsp+0AC0h+var_A80]
0x180005a25  mov     rcx, [rdi+rax]; Block
0x180005a29  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005a2e  inc     ebx
0x180005a30  add     rdi, 8
0x180005a34  mov     eax, [rsp+0AC0h+var_A78]
0x180005a38  cmp     ebx, eax
0x180005a3a  jl      short loc_1800059F7
0x180005a3c  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x180005a41  test    rcx, rcx
0x180005a44  jz      short loc_180005A53
0x180005a46  call    free
0x180005a4b  mov     rcx, r15
0x180005a4e  mov     [rsp+0AC0h+Block+8], rcx
0x180005a53  mov     rax, [rsp+0AC0h+var_A80]
0x180005a58  test    rax, rax
0x180005a5b  jz      short loc_180005A72
0x180005a5d  mov     rcx, rax; Block
0x180005a60  call    free
0x180005a65  mov     rax, r15
0x180005a68  mov     [rsp+0AC0h+var_A80], rax
0x180005a6d  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x180005a72  mov     [rsp+0AC0h+var_A78], r15d
0x180005a77  test    rcx, rcx
0x180005a7a  jz      short loc_180005A8E
0x180005a7c  call    free
0x180005a81  mov     rcx, r15
0x180005a84  mov     [rsp+0AC0h+Block+8], rcx
0x180005a89  mov     rax, [rsp+0AC0h+var_A80]
0x180005a8e  test    rax, rax
0x180005a91  jz      short loc_180005AA8
0x180005a93  mov     rcx, rax; Block
0x180005a96  call    free
0x180005a9b  mov     rax, r15
0x180005a9e  mov     [rsp+0AC0h+var_A80], rax
0x180005aa3  mov     rcx, [rsp+0AC0h+Block+8]; Block
0x180005aa8  mov     [rsp+0AC0h+var_A78], r15d
0x180005aad  test    rcx, rcx
0x180005ab0  jz      short loc_180005AC1
0x180005ab2  call    free
0x180005ab7  mov     [rsp+0AC0h+Block+8], r15
0x180005abc  mov     rax, [rsp+0AC0h+var_A80]
0x180005ac1  test    rax, rax
0x180005ac4  jz      short loc_180005ACF
0x180005ac6  mov     rcx, rax; Block
0x180005ac9  call    free
0x180005ace  nop
0x180005acf  mov     eax, 8007007Ah
0x180005ad4  jmp     loc_180005890
0x180005ad9  lea     r8, [rsp+0AC0h+Filename]
0x180005ade  lea     rax, [rbp+9C0h+Src]
0x180005ae5  mov     ecx, r15d
0x180005ae8  mov     r10d, 27h ; '''
0x180005aee  mov     r9d, 207h
0x180005af4  movzx   edx, word ptr [r8]
0x180005af8  test    dx, dx
0x180005afb  jz      short loc_180005B24
0x180005afd  mov     [rax], dx
0x180005b00  add     rax, 2
0x180005b04  cmp     dx, r10w
0x180005b08  jnz     short loc_180005B19
0x180005b0a  inc     ecx
0x180005b0c  cmp     ecx, r9d
0x180005b0f  jnb     short loc_180005B19
0x180005b11  mov     [rax], r10w
0x180005b15  add     rax, 2
0x180005b19  add     r8, 2
0x180005b1d  inc     ecx
0x180005b1f  cmp     ecx, r9d
0x180005b22  jb      short loc_180005AF4
0x180005b24  mov     [rax], r15w
0x180005b28  test    rbx, rbx
0x180005b2b  jz      short loc_180005B46
0x180005b2d  xor     ecx, ecx; lpModuleName
0x180005b2f  call    cs:__imp_GetModuleHandleW
0x180005b35  cmp     rbx, rax
0x180005b38  jz      short loc_180005B46
0x180005b3a  lea     r8, [rbp+9C0h+Src]
0x180005b41  jmp     loc_180005BD5
0x180005b46  mov     edi, 22h ; '"'
0x180005b4b  mov     [rbp+9C0h+var_850], di
0x180005b52  lea     rcx, [rbp+9C0h+Src]
0x180005b59  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005b5d  mov     rax, rbx
0x180005b60  inc     rax
0x180005b63  cmp     [rcx+rax*2], r15w
0x180005b68  jnz     short loc_180005B60
0x180005b6a  inc     eax
0x180005b6c  movsxd  r8, eax
0x180005b6f  add     r8, r8; Size
0x180005b72  jz      short loc_180005B95
0x180005b74  mov     eax, 416h
0x180005b79  lea     rcx, [rbp+9C0h+var_84E]; void *
0x180005b80  cmp     r8, rax
0x180005b83  ja      loc_180005CE7
0x180005b89  lea     rdx, [rbp+9C0h+Src]; Src
0x180005b90  call    memmove
0x180005b95  lea     rax, [rbp+9C0h+var_850]
0x180005b9c  inc     rbx
0x180005b9f  cmp     [rax+rbx*2], r15w
0x180005ba4  jnz     short loc_180005B9C
0x180005ba6  movsxd  rax, ebx
0x180005ba9  mov     [rbp+rax*2+9C0h+var_850], di
0x180005bb1  lea     rax, ds:2[rax*2]
0x180005bb9  cmp     rax, 418h
0x180005bbf  jnb     loc_18000602E
0x180005bc5  mov     [rbp+rax+9C0h+var_850], r15w
  ... truncated ...
```
