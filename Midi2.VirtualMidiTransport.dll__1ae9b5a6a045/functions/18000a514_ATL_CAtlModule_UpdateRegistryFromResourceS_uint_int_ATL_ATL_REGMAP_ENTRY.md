# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000a514`
- end: `0x18000a7bc`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000a500`
- `0x18000bda0`
- `0x18000be90`

## callees

- `0x1800038f0`
- `0x180003930`
- `0x180004626`
- `0x180004688`
- `0x18000549c`
- `0x180005bf8`
- `0x18000666c`
- `0x18000891c`
- `0x18000a514`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a76a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a76a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a5cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a5cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a649`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a649`

## string_xrefs

- `0x18000a788`: `REGISTRY`

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
0x18000a514  mov     [rsp-8+arg_0], rbx
0x18000a519  mov     [rsp-8+arg_8], rsi
0x18000a51e  push    rbp
0x18000a51f  push    rdi
0x18000a520  push    r14
0x18000a522  lea     rbp, [rsp-9B0h]
0x18000a52a  sub     rsp, 0AB0h
0x18000a531  mov     rax, cs:__security_cookie
0x18000a538  xor     rax, rsp
0x18000a53b  mov     [rbp+9C0h+var_20], rax
0x18000a542  mov     rbx, r9
0x18000a545  mov     esi, r8d
0x18000a548  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000a54f  mov     [rsp+0AC0h+var_A90], rax
0x18000a554  xorps   xmm0, xmm0
0x18000a557  movdqu  [rsp+0AC0h+var_A88], xmm0
0x18000a55d  xor     r14d, r14d
0x18000a560  mov     [rsp+0AC0h+var_A78], r14d
0x18000a565  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a56c  test    r9, r9
0x18000a56f  jz      short loc_18000A598
0x18000a571  mov     rax, [r9]
0x18000a574  jmp     short loc_18000A593
0x18000a576  mov     r8, [rbx+8]; unsigned __int16 *
0x18000a57a  test    r8, r8
0x18000a57d  jz      short loc_18000A58C
0x18000a57f  mov     rdx, rax; unsigned __int16 *
0x18000a582  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000a587  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000a58c  add     rbx, 10h
0x18000a590  mov     rax, [rbx]
0x18000a593  test    rax, rax
0x18000a596  jnz     short loc_18000A576
0x18000a598  mov     rax, [rdi]
0x18000a59b  lea     rdx, [rsp+0AC0h+var_A90]
0x18000a5a0  mov     rcx, rdi
0x18000a5a3  mov     rax, [rax+28h]
0x18000a5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ac  mov     ebx, eax
0x18000a5ae  test    eax, eax
0x18000a5b0  js      loc_18000A737
0x18000a5b6  mov     rbx, cs:hModule
0x18000a5bd  mov     edi, 104h
0x18000a5c2  mov     r8d, edi; nSize
0x18000a5c5  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x18000a5ca  mov     rcx, rbx; hModule
0x18000a5cd  call    cs:__imp_GetModuleFileNameW
0x18000a5d3  test    eax, eax
0x18000a5d5  jnz     short loc_18000A5E3
0x18000a5d7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a5dc  mov     ebx, eax
0x18000a5de  jmp     loc_18000A737
0x18000a5e3  cmp     eax, edi
0x18000a5e5  jnz     short loc_18000A5F1
0x18000a5e7  mov     ebx, 8007007Ah
0x18000a5ec  jmp     loc_18000A737
0x18000a5f1  lea     rdx, [rsp+0AC0h+Filename]
0x18000a5f6  mov     ecx, r14d
0x18000a5f9  mov     r9d, 27h ; '''
0x18000a5ff  movzx   r8d, word ptr [rdx]
0x18000a603  test    r8w, r8w
0x18000a607  jz      short loc_18000A639
0x18000a609  mov     [rbp+rcx*2+9C0h+Src], r8w
0x18000a612  cmp     r8w, r9w
0x18000a616  jnz     short loc_18000A62B
0x18000a618  cmp     ecx, 206h
0x18000a61e  jnb     short loc_18000A62B
0x18000a620  inc     ecx
0x18000a622  mov     [rbp+rcx*2+9C0h+Src], r9w
0x18000a62b  add     rdx, 2
0x18000a62f  inc     ecx
0x18000a631  cmp     ecx, 207h
0x18000a637  jb      short loc_18000A5FF
0x18000a639  mov     [rbp+rcx*2+9C0h+Src], r14w
0x18000a642  test    rbx, rbx
0x18000a645  jz      short loc_18000A660
0x18000a647  xor     ecx, ecx; lpModuleName
0x18000a649  call    cs:__imp_GetModuleHandleW
0x18000a64f  cmp     rbx, rax
0x18000a652  jz      short loc_18000A660
0x18000a654  lea     r8, [rbp+9C0h+Src]
0x18000a65b  jmp     loc_18000A6EF
0x18000a660  mov     edi, 22h ; '"'
0x18000a665  mov     [rbp+9C0h+var_440], di
0x18000a66c  lea     rcx, [rbp+9C0h+Src]
0x18000a673  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a677  mov     rax, rbx
0x18000a67a  inc     rax
0x18000a67d  cmp     [rcx+rax*2], r14w
0x18000a682  jnz     short loc_18000A67A
0x18000a684  inc     eax
0x18000a686  movsxd  r8, eax
0x18000a689  add     r8, r8; Size
0x18000a68c  jz      short loc_18000A6AE
0x18000a68e  cmp     r8, 414h
0x18000a695  ja      loc_18000A76A
0x18000a69b  lea     rdx, [rbp+9C0h+Src]; Src
0x18000a6a2  lea     rcx, [rbp+9C0h+var_43E]; void *
0x18000a6a9  call    memcpy_0
0x18000a6ae  lea     rax, [rbp+9C0h+var_440]
0x18000a6b5  inc     rbx
0x18000a6b8  cmp     [rax+rbx*2], r14w
0x18000a6bd  jnz     short loc_18000A6B5
0x18000a6bf  movsxd  rax, ebx
0x18000a6c2  mov     [rbp+rax*2+9C0h+var_440], di
0x18000a6ca  lea     rcx, ds:2[rax*2]
0x18000a6d2  cmp     rcx, 418h
0x18000a6d9  jnb     loc_18000A7B6
0x18000a6df  mov     [rbp+rcx+9C0h+var_440], r14w
0x18000a6e8  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x18000a6ef  lea     rdx, aModule; "Module"
0x18000a6f6  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000a6fb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000a700  neg     eax
0x18000a702  sbb     ebx, ebx
0x18000a704  mov     edi, 8007000Eh
0x18000a709  not     ebx
0x18000a70b  and     ebx, edi
0x18000a70d  test    ebx, ebx
0x18000a70f  js      short loc_18000A737
0x18000a711  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x18000a718  lea     rdx, aModuleRaw; "Module_Raw"
0x18000a71f  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000a724  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000a729  mov     ecx, eax
0x18000a72b  neg     ecx
0x18000a72d  sbb     ebx, ebx
0x18000a72f  not     ebx
0x18000a731  and     ebx, edi
0x18000a733  test    eax, eax
0x18000a735  jnz     short loc_18000A788
0x18000a737  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000a73c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000a741  mov     eax, ebx
0x18000a743  mov     rcx, [rbp+9C0h+var_20]
0x18000a74a  xor     rcx, rsp; StackCookie
0x18000a74d  call    __security_check_cookie
0x18000a752  lea     r11, [rsp+0AC0h+var_10]
0x18000a75a  mov     rbx, [r11+20h]
0x18000a75e  mov     rsi, [r11+28h]
0x18000a762  mov     rsp, r11
0x18000a765  pop     r14
0x18000a767  pop     rdi
0x18000a768  pop     rbp
0x18000a769  retn
0x18000a76a  call    cs:__imp__o__errno
0x18000a770  mov     [rax], edi
0x18000a772  call    _invalid_parameter_noinfo
0x18000a777  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000a77c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000a781  mov     eax, 80004005h
0x18000a786  jmp     short loc_18000A743
0x18000a788  lea     r9, aRegistry; "REGISTRY"
0x18000a78f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x18000a794  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000a799  test    esi, esi
0x18000a79b  jz      short loc_18000A7A7
0x18000a79d  mov     [rsp+0AC0h+var_AA0], 1
0x18000a7a5  jmp     short loc_18000A7AC
0x18000a7a7  mov     [rsp+0AC0h+var_AA0], r14d; int
0x18000a7ac  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000a7b1  jmp     loc_18000A5DC
0x18000a7b6  call    __report_rangecheckfailure
```
