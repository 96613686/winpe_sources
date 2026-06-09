# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800085f4`
- end: `0x18000889c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800085e0`
- `0x180009e80`
- `0x180009f70`

## callees

- `0x180002000`
- `0x180002040`
- `0x180002a06`
- `0x1800036f4`
- `0x180003e5c`
- `0x1800048cc`
- `0x180006b3c`
- `0x1800085f4`
- `0x18000cc60`
- `0x18000e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000884a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000884a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800086ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800086ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008729`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008729`

## string_xrefs

- `0x180008868`: `REGISTRY`

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
0x1800085f4  mov     [rsp-8+arg_0], rbx
0x1800085f9  mov     [rsp-8+arg_8], rsi
0x1800085fe  push    rbp
0x1800085ff  push    rdi
0x180008600  push    r14
0x180008602  lea     rbp, [rsp-9B0h]
0x18000860a  sub     rsp, 0AB0h
0x180008611  mov     rax, cs:__security_cookie
0x180008618  xor     rax, rsp
0x18000861b  mov     [rbp+9C0h+var_20], rax
0x180008622  mov     rbx, r9
0x180008625  mov     esi, r8d
0x180008628  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000862f  mov     [rsp+0AC0h+var_A90], rax
0x180008634  xorps   xmm0, xmm0
0x180008637  movdqu  [rsp+0AC0h+var_A88], xmm0
0x18000863d  xor     r14d, r14d
0x180008640  mov     [rsp+0AC0h+var_A78], r14d
0x180008645  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000864c  test    r9, r9
0x18000864f  jz      short loc_180008678
0x180008651  mov     rax, [r9]
0x180008654  jmp     short loc_180008673
0x180008656  mov     r8, [rbx+8]; unsigned __int16 *
0x18000865a  test    r8, r8
0x18000865d  jz      short loc_18000866C
0x18000865f  mov     rdx, rax; unsigned __int16 *
0x180008662  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180008667  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000866c  add     rbx, 10h
0x180008670  mov     rax, [rbx]
0x180008673  test    rax, rax
0x180008676  jnz     short loc_180008656
0x180008678  mov     rax, [rdi]
0x18000867b  lea     rdx, [rsp+0AC0h+var_A90]
0x180008680  mov     rcx, rdi
0x180008683  mov     rax, [rax+28h]
0x180008687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000868c  mov     ebx, eax
0x18000868e  test    eax, eax
0x180008690  js      loc_180008817
0x180008696  mov     rbx, cs:hModule
0x18000869d  mov     edi, 104h
0x1800086a2  mov     r8d, edi; nSize
0x1800086a5  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x1800086aa  mov     rcx, rbx; hModule
0x1800086ad  call    cs:__imp_GetModuleFileNameW
0x1800086b3  test    eax, eax
0x1800086b5  jnz     short loc_1800086C3
0x1800086b7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800086bc  mov     ebx, eax
0x1800086be  jmp     loc_180008817
0x1800086c3  cmp     eax, edi
0x1800086c5  jnz     short loc_1800086D1
0x1800086c7  mov     ebx, 8007007Ah
0x1800086cc  jmp     loc_180008817
0x1800086d1  lea     rdx, [rsp+0AC0h+Filename]
0x1800086d6  mov     ecx, r14d
0x1800086d9  mov     r9d, 27h ; '''
0x1800086df  movzx   r8d, word ptr [rdx]
0x1800086e3  test    r8w, r8w
0x1800086e7  jz      short loc_180008719
0x1800086e9  mov     [rbp+rcx*2+9C0h+Src], r8w
0x1800086f2  cmp     r8w, r9w
0x1800086f6  jnz     short loc_18000870B
0x1800086f8  cmp     ecx, 206h
0x1800086fe  jnb     short loc_18000870B
0x180008700  inc     ecx
0x180008702  mov     [rbp+rcx*2+9C0h+Src], r9w
0x18000870b  add     rdx, 2
0x18000870f  inc     ecx
0x180008711  cmp     ecx, 207h
0x180008717  jb      short loc_1800086DF
0x180008719  mov     [rbp+rcx*2+9C0h+Src], r14w
0x180008722  test    rbx, rbx
0x180008725  jz      short loc_180008740
0x180008727  xor     ecx, ecx; lpModuleName
0x180008729  call    cs:__imp_GetModuleHandleW
0x18000872f  cmp     rbx, rax
0x180008732  jz      short loc_180008740
0x180008734  lea     r8, [rbp+9C0h+Src]
0x18000873b  jmp     loc_1800087CF
0x180008740  mov     edi, 22h ; '"'
0x180008745  mov     [rbp+9C0h+var_440], di
0x18000874c  lea     rcx, [rbp+9C0h+Src]
0x180008753  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008757  mov     rax, rbx
0x18000875a  inc     rax
0x18000875d  cmp     [rcx+rax*2], r14w
0x180008762  jnz     short loc_18000875A
0x180008764  inc     eax
0x180008766  movsxd  r8, eax
0x180008769  add     r8, r8; Size
0x18000876c  jz      short loc_18000878E
0x18000876e  cmp     r8, 414h
0x180008775  ja      loc_18000884A
0x18000877b  lea     rdx, [rbp+9C0h+Src]; Src
0x180008782  lea     rcx, [rbp+9C0h+var_43E]; void *
0x180008789  call    memcpy_0
0x18000878e  lea     rax, [rbp+9C0h+var_440]
0x180008795  inc     rbx
0x180008798  cmp     [rax+rbx*2], r14w
0x18000879d  jnz     short loc_180008795
0x18000879f  movsxd  rax, ebx
0x1800087a2  mov     [rbp+rax*2+9C0h+var_440], di
0x1800087aa  lea     rcx, ds:2[rax*2]
0x1800087b2  cmp     rcx, 418h
0x1800087b9  jnb     loc_180008896
0x1800087bf  mov     [rbp+rcx+9C0h+var_440], r14w
0x1800087c8  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x1800087cf  lea     rdx, aModule; "Module"
0x1800087d6  lea     rcx, [rsp+0AC0h+var_A88]; this
0x1800087db  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800087e0  neg     eax
0x1800087e2  sbb     ebx, ebx
0x1800087e4  mov     edi, 8007000Eh
0x1800087e9  not     ebx
0x1800087eb  and     ebx, edi
0x1800087ed  test    ebx, ebx
0x1800087ef  js      short loc_180008817
0x1800087f1  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x1800087f8  lea     rdx, aModuleRaw; "Module_Raw"
0x1800087ff  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180008804  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008809  mov     ecx, eax
0x18000880b  neg     ecx
0x18000880d  sbb     ebx, ebx
0x18000880f  not     ebx
0x180008811  and     ebx, edi
0x180008813  test    eax, eax
0x180008815  jnz     short loc_180008868
0x180008817  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000881c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008821  mov     eax, ebx
0x180008823  mov     rcx, [rbp+9C0h+var_20]
0x18000882a  xor     rcx, rsp; StackCookie
0x18000882d  call    __security_check_cookie
0x180008832  lea     r11, [rsp+0AC0h+var_10]
0x18000883a  mov     rbx, [r11+20h]
0x18000883e  mov     rsi, [r11+28h]
0x180008842  mov     rsp, r11
0x180008845  pop     r14
0x180008847  pop     rdi
0x180008848  pop     rbp
0x180008849  retn
0x18000884a  call    cs:__imp__o__errno
0x180008850  mov     [rax], edi
0x180008852  call    _invalid_parameter_noinfo
0x180008857  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000885c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008861  mov     eax, 80004005h
0x180008866  jmp     short loc_180008823
0x180008868  lea     r9, aRegistry; "REGISTRY"
0x18000886f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x180008874  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180008879  test    esi, esi
0x18000887b  jz      short loc_180008887
0x18000887d  mov     [rsp+0AC0h+var_AA0], 1
0x180008885  jmp     short loc_18000888C
0x180008887  mov     [rsp+0AC0h+var_AA0], r14d; int
0x18000888c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008891  jmp     loc_1800086BC
0x180008896  call    __report_rangecheckfailure
```
