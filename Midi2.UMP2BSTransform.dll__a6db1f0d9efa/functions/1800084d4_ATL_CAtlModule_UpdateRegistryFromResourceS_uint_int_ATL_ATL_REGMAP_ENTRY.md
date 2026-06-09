# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800084d4`
- end: `0x18000877c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800084c0`
- `0x180009d60`
- `0x180009e50`

## callees

- `0x180001ef0`
- `0x180001f30`
- `0x1800028f6`
- `0x1800035e4`
- `0x180003d48`
- `0x1800047bc`
- `0x180006a2c`
- `0x1800084d4`
- `0x18000e8f0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000872a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000872a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008609`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008609`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000858d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000858d`

## string_xrefs

- `0x180008748`: `REGISTRY`

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
0x1800084d4  mov     [rsp-8+arg_0], rbx
0x1800084d9  mov     [rsp-8+arg_8], rsi
0x1800084de  push    rbp
0x1800084df  push    rdi
0x1800084e0  push    r14
0x1800084e2  lea     rbp, [rsp-9B0h]
0x1800084ea  sub     rsp, 0AB0h
0x1800084f1  mov     rax, cs:__security_cookie
0x1800084f8  xor     rax, rsp
0x1800084fb  mov     [rbp+9C0h+var_20], rax
0x180008502  mov     rbx, r9
0x180008505  mov     esi, r8d
0x180008508  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000850f  mov     [rsp+0AC0h+var_A90], rax
0x180008514  xorps   xmm0, xmm0
0x180008517  movdqu  [rsp+0AC0h+var_A88], xmm0
0x18000851d  xor     r14d, r14d
0x180008520  mov     [rsp+0AC0h+var_A78], r14d
0x180008525  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000852c  test    r9, r9
0x18000852f  jz      short loc_180008558
0x180008531  mov     rax, [r9]
0x180008534  jmp     short loc_180008553
0x180008536  mov     r8, [rbx+8]; unsigned __int16 *
0x18000853a  test    r8, r8
0x18000853d  jz      short loc_18000854C
0x18000853f  mov     rdx, rax; unsigned __int16 *
0x180008542  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180008547  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000854c  add     rbx, 10h
0x180008550  mov     rax, [rbx]
0x180008553  test    rax, rax
0x180008556  jnz     short loc_180008536
0x180008558  mov     rax, [rdi]
0x18000855b  lea     rdx, [rsp+0AC0h+var_A90]
0x180008560  mov     rcx, rdi
0x180008563  mov     rax, [rax+28h]
0x180008567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000856c  mov     ebx, eax
0x18000856e  test    eax, eax
0x180008570  js      loc_1800086F7
0x180008576  mov     rbx, cs:hModule
0x18000857d  mov     edi, 104h
0x180008582  mov     r8d, edi; nSize
0x180008585  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x18000858a  mov     rcx, rbx; hModule
0x18000858d  call    cs:__imp_GetModuleFileNameW
0x180008593  test    eax, eax
0x180008595  jnz     short loc_1800085A3
0x180008597  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000859c  mov     ebx, eax
0x18000859e  jmp     loc_1800086F7
0x1800085a3  cmp     eax, edi
0x1800085a5  jnz     short loc_1800085B1
0x1800085a7  mov     ebx, 8007007Ah
0x1800085ac  jmp     loc_1800086F7
0x1800085b1  lea     rdx, [rsp+0AC0h+Filename]
0x1800085b6  mov     ecx, r14d
0x1800085b9  mov     r9d, 27h ; '''
0x1800085bf  movzx   r8d, word ptr [rdx]
0x1800085c3  test    r8w, r8w
0x1800085c7  jz      short loc_1800085F9
0x1800085c9  mov     [rbp+rcx*2+9C0h+Src], r8w
0x1800085d2  cmp     r8w, r9w
0x1800085d6  jnz     short loc_1800085EB
0x1800085d8  cmp     ecx, 206h
0x1800085de  jnb     short loc_1800085EB
0x1800085e0  inc     ecx
0x1800085e2  mov     [rbp+rcx*2+9C0h+Src], r9w
0x1800085eb  add     rdx, 2
0x1800085ef  inc     ecx
0x1800085f1  cmp     ecx, 207h
0x1800085f7  jb      short loc_1800085BF
0x1800085f9  mov     [rbp+rcx*2+9C0h+Src], r14w
0x180008602  test    rbx, rbx
0x180008605  jz      short loc_180008620
0x180008607  xor     ecx, ecx; lpModuleName
0x180008609  call    cs:__imp_GetModuleHandleW
0x18000860f  cmp     rbx, rax
0x180008612  jz      short loc_180008620
0x180008614  lea     r8, [rbp+9C0h+Src]
0x18000861b  jmp     loc_1800086AF
0x180008620  mov     edi, 22h ; '"'
0x180008625  mov     [rbp+9C0h+var_440], di
0x18000862c  lea     rcx, [rbp+9C0h+Src]
0x180008633  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008637  mov     rax, rbx
0x18000863a  inc     rax
0x18000863d  cmp     [rcx+rax*2], r14w
0x180008642  jnz     short loc_18000863A
0x180008644  inc     eax
0x180008646  movsxd  r8, eax
0x180008649  add     r8, r8; Size
0x18000864c  jz      short loc_18000866E
0x18000864e  cmp     r8, 414h
0x180008655  ja      loc_18000872A
0x18000865b  lea     rdx, [rbp+9C0h+Src]; Src
0x180008662  lea     rcx, [rbp+9C0h+var_43E]; void *
0x180008669  call    memcpy_0
0x18000866e  lea     rax, [rbp+9C0h+var_440]
0x180008675  inc     rbx
0x180008678  cmp     [rax+rbx*2], r14w
0x18000867d  jnz     short loc_180008675
0x18000867f  movsxd  rax, ebx
0x180008682  mov     [rbp+rax*2+9C0h+var_440], di
0x18000868a  lea     rcx, ds:2[rax*2]
0x180008692  cmp     rcx, 418h
0x180008699  jnb     loc_180008776
0x18000869f  mov     [rbp+rcx+9C0h+var_440], r14w
0x1800086a8  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x1800086af  lea     rdx, aModule; "Module"
0x1800086b6  lea     rcx, [rsp+0AC0h+var_A88]; this
0x1800086bb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800086c0  neg     eax
0x1800086c2  sbb     ebx, ebx
0x1800086c4  mov     edi, 8007000Eh
0x1800086c9  not     ebx
0x1800086cb  and     ebx, edi
0x1800086cd  test    ebx, ebx
0x1800086cf  js      short loc_1800086F7
0x1800086d1  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x1800086d8  lea     rdx, aModuleRaw; "Module_Raw"
0x1800086df  lea     rcx, [rsp+0AC0h+var_A88]; this
0x1800086e4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800086e9  mov     ecx, eax
0x1800086eb  neg     ecx
0x1800086ed  sbb     ebx, ebx
0x1800086ef  not     ebx
0x1800086f1  and     ebx, edi
0x1800086f3  test    eax, eax
0x1800086f5  jnz     short loc_180008748
0x1800086f7  lea     rcx, [rsp+0AC0h+var_A90]; this
0x1800086fc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008701  mov     eax, ebx
0x180008703  mov     rcx, [rbp+9C0h+var_20]
0x18000870a  xor     rcx, rsp; StackCookie
0x18000870d  call    __security_check_cookie
0x180008712  lea     r11, [rsp+0AC0h+var_10]
0x18000871a  mov     rbx, [r11+20h]
0x18000871e  mov     rsi, [r11+28h]
0x180008722  mov     rsp, r11
0x180008725  pop     r14
0x180008727  pop     rdi
0x180008728  pop     rbp
0x180008729  retn
0x18000872a  call    cs:__imp__o__errno
0x180008730  mov     [rax], edi
0x180008732  call    _invalid_parameter_noinfo
0x180008737  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000873c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008741  mov     eax, 80004005h
0x180008746  jmp     short loc_180008703
0x180008748  lea     r9, aRegistry; "REGISTRY"
0x18000874f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x180008754  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180008759  test    esi, esi
0x18000875b  jz      short loc_180008767
0x18000875d  mov     [rsp+0AC0h+var_AA0], 1
0x180008765  jmp     short loc_18000876C
0x180008767  mov     [rsp+0AC0h+var_AA0], r14d; int
0x18000876c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008771  jmp     loc_18000859C
0x180008776  call    __report_rangecheckfailure
```
