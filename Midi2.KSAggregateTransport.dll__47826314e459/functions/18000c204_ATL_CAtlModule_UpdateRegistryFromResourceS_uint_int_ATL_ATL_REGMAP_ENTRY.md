# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000c204`
- end: `0x18000c4ac`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000c1f0`
- `0x180012050`
- `0x180012140`

## callees

- `0x180005020`
- `0x180005060`
- `0x180005e16`
- `0x180005e84`
- `0x180006d44`
- `0x18000760c`
- `0x18000807c`
- `0x18000a664`
- `0x18000c204`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c45a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c45a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c339`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c339`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c2bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c2bd`

## string_xrefs

- `0x18000c478`: `REGISTRY`

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
0x18000c204  mov     [rsp-8+arg_0], rbx
0x18000c209  mov     [rsp-8+arg_8], rsi
0x18000c20e  push    rbp
0x18000c20f  push    rdi
0x18000c210  push    r14
0x18000c212  lea     rbp, [rsp-9B0h]
0x18000c21a  sub     rsp, 0AB0h
0x18000c221  mov     rax, cs:__security_cookie
0x18000c228  xor     rax, rsp
0x18000c22b  mov     [rbp+9C0h+var_20], rax
0x18000c232  mov     rbx, r9
0x18000c235  mov     esi, r8d
0x18000c238  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000c23f  mov     [rsp+0AC0h+var_A90], rax
0x18000c244  xorps   xmm0, xmm0
0x18000c247  movdqu  [rsp+0AC0h+var_A88], xmm0
0x18000c24d  xor     r14d, r14d
0x18000c250  mov     [rsp+0AC0h+var_A78], r14d
0x18000c255  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c25c  test    r9, r9
0x18000c25f  jz      short loc_18000C288
0x18000c261  mov     rax, [r9]
0x18000c264  jmp     short loc_18000C283
0x18000c266  mov     r8, [rbx+8]; unsigned __int16 *
0x18000c26a  test    r8, r8
0x18000c26d  jz      short loc_18000C27C
0x18000c26f  mov     rdx, rax; unsigned __int16 *
0x18000c272  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000c277  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000c27c  add     rbx, 10h
0x18000c280  mov     rax, [rbx]
0x18000c283  test    rax, rax
0x18000c286  jnz     short loc_18000C266
0x18000c288  mov     rax, [rdi]
0x18000c28b  lea     rdx, [rsp+0AC0h+var_A90]
0x18000c290  mov     rcx, rdi
0x18000c293  mov     rax, [rax+28h]
0x18000c297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29c  mov     ebx, eax
0x18000c29e  test    eax, eax
0x18000c2a0  js      loc_18000C427
0x18000c2a6  mov     rbx, cs:hModule
0x18000c2ad  mov     edi, 104h
0x18000c2b2  mov     r8d, edi; nSize
0x18000c2b5  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x18000c2ba  mov     rcx, rbx; hModule
0x18000c2bd  call    cs:__imp_GetModuleFileNameW
0x18000c2c3  test    eax, eax
0x18000c2c5  jnz     short loc_18000C2D3
0x18000c2c7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c2cc  mov     ebx, eax
0x18000c2ce  jmp     loc_18000C427
0x18000c2d3  cmp     eax, edi
0x18000c2d5  jnz     short loc_18000C2E1
0x18000c2d7  mov     ebx, 8007007Ah
0x18000c2dc  jmp     loc_18000C427
0x18000c2e1  lea     rdx, [rsp+0AC0h+Filename]
0x18000c2e6  mov     ecx, r14d
0x18000c2e9  mov     r9d, 27h ; '''
0x18000c2ef  movzx   r8d, word ptr [rdx]
0x18000c2f3  test    r8w, r8w
0x18000c2f7  jz      short loc_18000C329
0x18000c2f9  mov     [rbp+rcx*2+9C0h+Src], r8w
0x18000c302  cmp     r8w, r9w
0x18000c306  jnz     short loc_18000C31B
0x18000c308  cmp     ecx, 206h
0x18000c30e  jnb     short loc_18000C31B
0x18000c310  inc     ecx
0x18000c312  mov     [rbp+rcx*2+9C0h+Src], r9w
0x18000c31b  add     rdx, 2
0x18000c31f  inc     ecx
0x18000c321  cmp     ecx, 207h
0x18000c327  jb      short loc_18000C2EF
0x18000c329  mov     [rbp+rcx*2+9C0h+Src], r14w
0x18000c332  test    rbx, rbx
0x18000c335  jz      short loc_18000C350
0x18000c337  xor     ecx, ecx; lpModuleName
0x18000c339  call    cs:__imp_GetModuleHandleW
0x18000c33f  cmp     rbx, rax
0x18000c342  jz      short loc_18000C350
0x18000c344  lea     r8, [rbp+9C0h+Src]
0x18000c34b  jmp     loc_18000C3DF
0x18000c350  mov     edi, 22h ; '"'
0x18000c355  mov     [rbp+9C0h+var_440], di
0x18000c35c  lea     rcx, [rbp+9C0h+Src]
0x18000c363  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c367  mov     rax, rbx
0x18000c36a  inc     rax
0x18000c36d  cmp     [rcx+rax*2], r14w
0x18000c372  jnz     short loc_18000C36A
0x18000c374  inc     eax
0x18000c376  movsxd  r8, eax
0x18000c379  add     r8, r8; Size
0x18000c37c  jz      short loc_18000C39E
0x18000c37e  cmp     r8, 414h
0x18000c385  ja      loc_18000C45A
0x18000c38b  lea     rdx, [rbp+9C0h+Src]; Src
0x18000c392  lea     rcx, [rbp+9C0h+var_43E]; void *
0x18000c399  call    memcpy_0
0x18000c39e  lea     rax, [rbp+9C0h+var_440]
0x18000c3a5  inc     rbx
0x18000c3a8  cmp     [rax+rbx*2], r14w
0x18000c3ad  jnz     short loc_18000C3A5
0x18000c3af  movsxd  rax, ebx
0x18000c3b2  mov     [rbp+rax*2+9C0h+var_440], di
0x18000c3ba  lea     rcx, ds:2[rax*2]
0x18000c3c2  cmp     rcx, 418h
0x18000c3c9  jnb     loc_18000C4A6
0x18000c3cf  mov     [rbp+rcx+9C0h+var_440], r14w
0x18000c3d8  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x18000c3df  lea     rdx, aModule; "Module"
0x18000c3e6  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000c3eb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000c3f0  neg     eax
0x18000c3f2  sbb     ebx, ebx
0x18000c3f4  mov     edi, 8007000Eh
0x18000c3f9  not     ebx
0x18000c3fb  and     ebx, edi
0x18000c3fd  test    ebx, ebx
0x18000c3ff  js      short loc_18000C427
0x18000c401  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x18000c408  lea     rdx, aModuleRaw; "Module_Raw"
0x18000c40f  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000c414  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000c419  mov     ecx, eax
0x18000c41b  neg     ecx
0x18000c41d  sbb     ebx, ebx
0x18000c41f  not     ebx
0x18000c421  and     ebx, edi
0x18000c423  test    eax, eax
0x18000c425  jnz     short loc_18000C478
0x18000c427  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000c42c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c431  mov     eax, ebx
0x18000c433  mov     rcx, [rbp+9C0h+var_20]
0x18000c43a  xor     rcx, rsp; StackCookie
0x18000c43d  call    __security_check_cookie
0x18000c442  lea     r11, [rsp+0AC0h+var_10]
0x18000c44a  mov     rbx, [r11+20h]
0x18000c44e  mov     rsi, [r11+28h]
0x18000c452  mov     rsp, r11
0x18000c455  pop     r14
0x18000c457  pop     rdi
0x18000c458  pop     rbp
0x18000c459  retn
0x18000c45a  call    cs:__imp__o__errno
0x18000c460  mov     [rax], edi
0x18000c462  call    _invalid_parameter_noinfo
0x18000c467  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000c46c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c471  mov     eax, 80004005h
0x18000c476  jmp     short loc_18000C433
0x18000c478  lea     r9, aRegistry; "REGISTRY"
0x18000c47f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x18000c484  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000c489  test    esi, esi
0x18000c48b  jz      short loc_18000C497
0x18000c48d  mov     [rsp+0AC0h+var_AA0], 1
0x18000c495  jmp     short loc_18000C49C
0x18000c497  mov     [rsp+0AC0h+var_AA0], r14d; int
0x18000c49c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000c4a1  jmp     loc_18000C2CC
0x18000c4a6  call    __report_rangecheckfailure
```
