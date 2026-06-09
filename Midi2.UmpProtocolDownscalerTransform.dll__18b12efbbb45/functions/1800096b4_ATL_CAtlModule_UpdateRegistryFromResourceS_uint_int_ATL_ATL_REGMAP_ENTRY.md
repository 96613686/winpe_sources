# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800096b4`
- end: `0x18000995c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800096a0`
- `0x18000af40`
- `0x18000b030`

## callees

- `0x180002e70`
- `0x180002eb0`
- `0x1800039a6`
- `0x180003a08`
- `0x1800047cc`
- `0x180004f28`
- `0x18000599c`
- `0x180007c0c`
- `0x1800096b4`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000990a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000990a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800097e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800097e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000976d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000976d`

## string_xrefs

- `0x180009928`: `REGISTRY`

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
0x1800096b4  mov     [rsp-8+arg_0], rbx
0x1800096b9  mov     [rsp-8+arg_8], rsi
0x1800096be  push    rbp
0x1800096bf  push    rdi
0x1800096c0  push    r14
0x1800096c2  lea     rbp, [rsp-9B0h]
0x1800096ca  sub     rsp, 0AB0h
0x1800096d1  mov     rax, cs:__security_cookie
0x1800096d8  xor     rax, rsp
0x1800096db  mov     [rbp+9C0h+var_20], rax
0x1800096e2  mov     rbx, r9
0x1800096e5  mov     esi, r8d
0x1800096e8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800096ef  mov     [rsp+0AC0h+var_A90], rax
0x1800096f4  xorps   xmm0, xmm0
0x1800096f7  movdqu  [rsp+0AC0h+var_A88], xmm0
0x1800096fd  xor     r14d, r14d
0x180009700  mov     [rsp+0AC0h+var_A78], r14d
0x180009705  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000970c  test    r9, r9
0x18000970f  jz      short loc_180009738
0x180009711  mov     rax, [r9]
0x180009714  jmp     short loc_180009733
0x180009716  mov     r8, [rbx+8]; unsigned __int16 *
0x18000971a  test    r8, r8
0x18000971d  jz      short loc_18000972C
0x18000971f  mov     rdx, rax; unsigned __int16 *
0x180009722  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180009727  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000972c  add     rbx, 10h
0x180009730  mov     rax, [rbx]
0x180009733  test    rax, rax
0x180009736  jnz     short loc_180009716
0x180009738  mov     rax, [rdi]
0x18000973b  lea     rdx, [rsp+0AC0h+var_A90]
0x180009740  mov     rcx, rdi
0x180009743  mov     rax, [rax+28h]
0x180009747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000974c  mov     ebx, eax
0x18000974e  test    eax, eax
0x180009750  js      loc_1800098D7
0x180009756  mov     rbx, cs:hModule
0x18000975d  mov     edi, 104h
0x180009762  mov     r8d, edi; nSize
0x180009765  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x18000976a  mov     rcx, rbx; hModule
0x18000976d  call    cs:__imp_GetModuleFileNameW
0x180009773  test    eax, eax
0x180009775  jnz     short loc_180009783
0x180009777  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000977c  mov     ebx, eax
0x18000977e  jmp     loc_1800098D7
0x180009783  cmp     eax, edi
0x180009785  jnz     short loc_180009791
0x180009787  mov     ebx, 8007007Ah
0x18000978c  jmp     loc_1800098D7
0x180009791  lea     rdx, [rsp+0AC0h+Filename]
0x180009796  mov     ecx, r14d
0x180009799  mov     r9d, 27h ; '''
0x18000979f  movzx   r8d, word ptr [rdx]
0x1800097a3  test    r8w, r8w
0x1800097a7  jz      short loc_1800097D9
0x1800097a9  mov     [rbp+rcx*2+9C0h+Src], r8w
0x1800097b2  cmp     r8w, r9w
0x1800097b6  jnz     short loc_1800097CB
0x1800097b8  cmp     ecx, 206h
0x1800097be  jnb     short loc_1800097CB
0x1800097c0  inc     ecx
0x1800097c2  mov     [rbp+rcx*2+9C0h+Src], r9w
0x1800097cb  add     rdx, 2
0x1800097cf  inc     ecx
0x1800097d1  cmp     ecx, 207h
0x1800097d7  jb      short loc_18000979F
0x1800097d9  mov     [rbp+rcx*2+9C0h+Src], r14w
0x1800097e2  test    rbx, rbx
0x1800097e5  jz      short loc_180009800
0x1800097e7  xor     ecx, ecx; lpModuleName
0x1800097e9  call    cs:__imp_GetModuleHandleW
0x1800097ef  cmp     rbx, rax
0x1800097f2  jz      short loc_180009800
0x1800097f4  lea     r8, [rbp+9C0h+Src]
0x1800097fb  jmp     loc_18000988F
0x180009800  mov     edi, 22h ; '"'
0x180009805  mov     [rbp+9C0h+var_440], di
0x18000980c  lea     rcx, [rbp+9C0h+Src]
0x180009813  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009817  mov     rax, rbx
0x18000981a  inc     rax
0x18000981d  cmp     [rcx+rax*2], r14w
0x180009822  jnz     short loc_18000981A
0x180009824  inc     eax
0x180009826  movsxd  r8, eax
0x180009829  add     r8, r8; Size
0x18000982c  jz      short loc_18000984E
0x18000982e  cmp     r8, 414h
0x180009835  ja      loc_18000990A
0x18000983b  lea     rdx, [rbp+9C0h+Src]; Src
0x180009842  lea     rcx, [rbp+9C0h+var_43E]; void *
0x180009849  call    memcpy_0
0x18000984e  lea     rax, [rbp+9C0h+var_440]
0x180009855  inc     rbx
0x180009858  cmp     [rax+rbx*2], r14w
0x18000985d  jnz     short loc_180009855
0x18000985f  movsxd  rax, ebx
0x180009862  mov     [rbp+rax*2+9C0h+var_440], di
0x18000986a  lea     rcx, ds:2[rax*2]
0x180009872  cmp     rcx, 418h
0x180009879  jnb     loc_180009956
0x18000987f  mov     [rbp+rcx+9C0h+var_440], r14w
0x180009888  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x18000988f  lea     rdx, aModule; "Module"
0x180009896  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000989b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800098a0  neg     eax
0x1800098a2  sbb     ebx, ebx
0x1800098a4  mov     edi, 8007000Eh
0x1800098a9  not     ebx
0x1800098ab  and     ebx, edi
0x1800098ad  test    ebx, ebx
0x1800098af  js      short loc_1800098D7
0x1800098b1  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x1800098b8  lea     rdx, aModuleRaw; "Module_Raw"
0x1800098bf  lea     rcx, [rsp+0AC0h+var_A88]; this
0x1800098c4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800098c9  mov     ecx, eax
0x1800098cb  neg     ecx
0x1800098cd  sbb     ebx, ebx
0x1800098cf  not     ebx
0x1800098d1  and     ebx, edi
0x1800098d3  test    eax, eax
0x1800098d5  jnz     short loc_180009928
0x1800098d7  lea     rcx, [rsp+0AC0h+var_A90]; this
0x1800098dc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800098e1  mov     eax, ebx
0x1800098e3  mov     rcx, [rbp+9C0h+var_20]
0x1800098ea  xor     rcx, rsp; StackCookie
0x1800098ed  call    __security_check_cookie
0x1800098f2  lea     r11, [rsp+0AC0h+var_10]
0x1800098fa  mov     rbx, [r11+20h]
0x1800098fe  mov     rsi, [r11+28h]
0x180009902  mov     rsp, r11
0x180009905  pop     r14
0x180009907  pop     rdi
0x180009908  pop     rbp
0x180009909  retn
0x18000990a  call    cs:__imp__o__errno
0x180009910  mov     [rax], edi
0x180009912  call    _invalid_parameter_noinfo
0x180009917  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000991c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009921  mov     eax, 80004005h
0x180009926  jmp     short loc_1800098E3
0x180009928  lea     r9, aRegistry; "REGISTRY"
0x18000992f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x180009934  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180009939  test    esi, esi
0x18000993b  jz      short loc_180009947
0x18000993d  mov     [rsp+0AC0h+var_AA0], 1
0x180009945  jmp     short loc_18000994C
0x180009947  mov     [rsp+0AC0h+var_AA0], r14d; int
0x18000994c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009951  jmp     loc_18000977C
0x180009956  call    __report_rangecheckfailure
```
