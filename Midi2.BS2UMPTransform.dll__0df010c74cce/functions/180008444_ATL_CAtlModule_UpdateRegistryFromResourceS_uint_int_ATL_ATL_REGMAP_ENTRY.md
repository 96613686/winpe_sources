# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180008444`
- end: `0x1800086ec`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180008430`
- `0x180009cd0`
- `0x180009dc0`

## callees

- `0x180001e60`
- `0x180001ea0`
- `0x180002866`
- `0x180003554`
- `0x180003cb8`
- `0x18000472c`
- `0x18000699c`
- `0x180008444`
- `0x18000b3f0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000869a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000869a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008579`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008579`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800084fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800084fd`

## string_xrefs

- `0x1800086b8`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  struct ATL::CAtlModule *v6; // rdi
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v8; // r8
  signed int v9; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  signed int Error; // eax
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  size_t v20; // r8
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  const unsigned __int16 *v24; // r8
  void **v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+38h] [rbp-C8h] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Src[520]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v31; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v32[1054]; // [rsp+682h] [rbp+582h] BYREF

  v4 = a4;
  v26 = &ATL::CRegObject::`vftable';
  v27 = 0;
  v28 = 0;
  v6 = ATL::_pAtlModule;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      v8 = v4[1];
      if ( v8 )
        ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, i, v8);
      v4 += 2;
    }
  }
  v9 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v6 + 40LL))(v6, &v26);
  if ( v9 < 0 )
    goto LABEL_32;
  v10 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v9 = Error;
LABEL_32:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v26);
    return (unsigned int)v9;
  }
  if ( ModuleFileNameW == 260 )
  {
    v9 = -2147024774;
    goto LABEL_32;
  }
  v13 = Filename;
  v14 = 0;
  v15 = 39;
  do
  {
    v16 = *v13;
    if ( !*v13 )
      break;
    Src[v14] = v16;
    if ( v16 == 39 && (unsigned int)v14 < 0x206 )
    {
      LODWORD(v14) = v14 + 1;
      Src[(unsigned int)v14] = 39;
    }
    ++v13;
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (unsigned int)v14 < 0x207 );
  Src[v14] = 0;
  if ( v10 && v10 != GetModuleHandleW(0) )
  {
    v17 = Src;
LABEL_30:
    v22 = -ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module", v17);
    v9 = v22 == 0 ? 0x8007000E : 0;
    if ( !v22 )
      goto LABEL_32;
    v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module_Raw", Src);
    v9 = v23 == 0 ? 0x8007000E : 0;
    if ( !v23 )
      goto LABEL_32;
    if ( a3 )
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v26, Filename, v24, L"REGISTRY", 1);
    else
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v26, Filename, v24, L"REGISTRY", 0);
    goto LABEL_10;
  }
  v31 = 34;
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( Src[v19] );
  v20 = 2LL * ((int)v19 + 1);
  if ( !v20 )
  {
    do
LABEL_27:
      ++v18;
    while ( *(_WORD *)&v32[2 * v18 - 2] );
    *(_WORD *)&v32[2 * (int)v18 - 2] = 34;
    v21 = 2LL * (int)v18 + 2;
    if ( v21 >= 0x418 )
      _report_rangecheckfailure(v21, v13, v20, v15);
    *(_WORD *)&v32[v21 - 2] = 0;
    v17 = &v31;
    goto LABEL_30;
  }
  if ( v20 <= 0x414 )
  {
    memcpy_0(v32, Src, v20);
    goto LABEL_27;
  }
  *(_DWORD *)_o__errno(Src, v13, v20, v15) = 34;
  invalid_parameter_noinfo();
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v26);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180008444  mov     [rsp-8+arg_0], rbx
0x180008449  mov     [rsp-8+arg_8], rsi
0x18000844e  push    rbp
0x18000844f  push    rdi
0x180008450  push    r14
0x180008452  lea     rbp, [rsp-9B0h]
0x18000845a  sub     rsp, 0AB0h
0x180008461  mov     rax, cs:__security_cookie
0x180008468  xor     rax, rsp
0x18000846b  mov     [rbp+9C0h+var_20], rax
0x180008472  mov     rbx, r9
0x180008475  mov     esi, r8d
0x180008478  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000847f  mov     [rsp+0AC0h+var_A90], rax
0x180008484  xorps   xmm0, xmm0
0x180008487  movdqu  [rsp+0AC0h+var_A88], xmm0
0x18000848d  xor     r14d, r14d
0x180008490  mov     [rsp+0AC0h+var_A78], r14d
0x180008495  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000849c  test    r9, r9
0x18000849f  jz      short loc_1800084C8
0x1800084a1  mov     rax, [r9]
0x1800084a4  jmp     short loc_1800084C3
0x1800084a6  mov     r8, [rbx+8]; unsigned __int16 *
0x1800084aa  test    r8, r8
0x1800084ad  jz      short loc_1800084BC
0x1800084af  mov     rdx, rax; unsigned __int16 *
0x1800084b2  lea     rcx, [rsp+0AC0h+var_A88]; this
0x1800084b7  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800084bc  add     rbx, 10h
0x1800084c0  mov     rax, [rbx]
0x1800084c3  test    rax, rax
0x1800084c6  jnz     short loc_1800084A6
0x1800084c8  mov     rax, [rdi]
0x1800084cb  lea     rdx, [rsp+0AC0h+var_A90]
0x1800084d0  mov     rcx, rdi
0x1800084d3  mov     rax, [rax+28h]
0x1800084d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084dc  mov     ebx, eax
0x1800084de  test    eax, eax
0x1800084e0  js      loc_180008667
0x1800084e6  mov     rbx, cs:hModule
0x1800084ed  mov     edi, 104h
0x1800084f2  mov     r8d, edi; nSize
0x1800084f5  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x1800084fa  mov     rcx, rbx; hModule
0x1800084fd  call    cs:__imp_GetModuleFileNameW
0x180008503  test    eax, eax
0x180008505  jnz     short loc_180008513
0x180008507  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000850c  mov     ebx, eax
0x18000850e  jmp     loc_180008667
0x180008513  cmp     eax, edi
0x180008515  jnz     short loc_180008521
0x180008517  mov     ebx, 8007007Ah
0x18000851c  jmp     loc_180008667
0x180008521  lea     rdx, [rsp+0AC0h+Filename]
0x180008526  mov     ecx, r14d
0x180008529  mov     r9d, 27h ; '''
0x18000852f  movzx   r8d, word ptr [rdx]
0x180008533  test    r8w, r8w
0x180008537  jz      short loc_180008569
0x180008539  mov     [rbp+rcx*2+9C0h+Src], r8w
0x180008542  cmp     r8w, r9w
0x180008546  jnz     short loc_18000855B
0x180008548  cmp     ecx, 206h
0x18000854e  jnb     short loc_18000855B
0x180008550  inc     ecx
0x180008552  mov     [rbp+rcx*2+9C0h+Src], r9w
0x18000855b  add     rdx, 2
0x18000855f  inc     ecx
0x180008561  cmp     ecx, 207h
0x180008567  jb      short loc_18000852F
0x180008569  mov     [rbp+rcx*2+9C0h+Src], r14w
0x180008572  test    rbx, rbx
0x180008575  jz      short loc_180008590
0x180008577  xor     ecx, ecx; lpModuleName
0x180008579  call    cs:__imp_GetModuleHandleW
0x18000857f  cmp     rbx, rax
0x180008582  jz      short loc_180008590
0x180008584  lea     r8, [rbp+9C0h+Src]
0x18000858b  jmp     loc_18000861F
0x180008590  mov     edi, 22h ; '"'
0x180008595  mov     [rbp+9C0h+var_440], di
0x18000859c  lea     rcx, [rbp+9C0h+Src]
0x1800085a3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800085a7  mov     rax, rbx
0x1800085aa  inc     rax
0x1800085ad  cmp     [rcx+rax*2], r14w
0x1800085b2  jnz     short loc_1800085AA
0x1800085b4  inc     eax
0x1800085b6  movsxd  r8, eax
0x1800085b9  add     r8, r8; Size
0x1800085bc  jz      short loc_1800085DE
0x1800085be  cmp     r8, 414h
0x1800085c5  ja      loc_18000869A
0x1800085cb  lea     rdx, [rbp+9C0h+Src]; Src
0x1800085d2  lea     rcx, [rbp+9C0h+var_43E]; void *
0x1800085d9  call    memcpy_0
0x1800085de  lea     rax, [rbp+9C0h+var_440]
0x1800085e5  inc     rbx
0x1800085e8  cmp     [rax+rbx*2], r14w
0x1800085ed  jnz     short loc_1800085E5
0x1800085ef  movsxd  rax, ebx
0x1800085f2  mov     [rbp+rax*2+9C0h+var_440], di
0x1800085fa  lea     rcx, ds:2[rax*2]
0x180008602  cmp     rcx, 418h
0x180008609  jnb     loc_1800086E6
0x18000860f  mov     [rbp+rcx+9C0h+var_440], r14w
0x180008618  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x18000861f  lea     rdx, aModule; "Module"
0x180008626  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000862b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008630  neg     eax
0x180008632  sbb     ebx, ebx
0x180008634  mov     edi, 8007000Eh
0x180008639  not     ebx
0x18000863b  and     ebx, edi
0x18000863d  test    ebx, ebx
0x18000863f  js      short loc_180008667
0x180008641  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x180008648  lea     rdx, aModuleRaw; "Module_Raw"
0x18000864f  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180008654  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008659  mov     ecx, eax
0x18000865b  neg     ecx
0x18000865d  sbb     ebx, ebx
0x18000865f  not     ebx
0x180008661  and     ebx, edi
0x180008663  test    eax, eax
0x180008665  jnz     short loc_1800086B8
0x180008667  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000866c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008671  mov     eax, ebx
0x180008673  mov     rcx, [rbp+9C0h+var_20]
0x18000867a  xor     rcx, rsp; StackCookie
0x18000867d  call    __security_check_cookie
0x180008682  lea     r11, [rsp+0AC0h+var_10]
0x18000868a  mov     rbx, [r11+20h]
0x18000868e  mov     rsi, [r11+28h]
0x180008692  mov     rsp, r11
0x180008695  pop     r14
0x180008697  pop     rdi
0x180008698  pop     rbp
0x180008699  retn
0x18000869a  call    cs:__imp__o__errno
0x1800086a0  mov     [rax], edi
0x1800086a2  call    _invalid_parameter_noinfo
0x1800086a7  lea     rcx, [rsp+0AC0h+var_A90]; this
0x1800086ac  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800086b1  mov     eax, 80004005h
0x1800086b6  jmp     short loc_180008673
0x1800086b8  lea     r9, aRegistry; "REGISTRY"
0x1800086bf  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x1800086c4  lea     rcx, [rsp+0AC0h+var_A90]; this
0x1800086c9  test    esi, esi
0x1800086cb  jz      short loc_1800086D7
0x1800086cd  mov     [rsp+0AC0h+var_AA0], 1
0x1800086d5  jmp     short loc_1800086DC
0x1800086d7  mov     [rsp+0AC0h+var_AA0], r14d; int
0x1800086dc  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800086e1  jmp     loc_18000850C
0x1800086e6  call    __report_rangecheckfailure
```
