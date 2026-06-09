# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000b684`
- end: `0x18000b92c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000b670`
- `0x18000e390`
- `0x18000e480`

## callees

- `0x180004410`
- `0x180004450`
- `0x1800051e6`
- `0x180005254`
- `0x1800061c4`
- `0x180006a8c`
- `0x1800074fc`
- `0x180009ae4`
- `0x18000b684`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8da`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b8da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b7b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b7b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000b73d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000b73d`

## string_xrefs

- `0x18000b8f8`: `REGISTRY`

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
0x18000b684  mov     [rsp-8+arg_0], rbx
0x18000b689  mov     [rsp-8+arg_8], rsi
0x18000b68e  push    rbp
0x18000b68f  push    rdi
0x18000b690  push    r14
0x18000b692  lea     rbp, [rsp-9B0h]
0x18000b69a  sub     rsp, 0AB0h
0x18000b6a1  mov     rax, cs:__security_cookie
0x18000b6a8  xor     rax, rsp
0x18000b6ab  mov     [rbp+9C0h+var_20], rax
0x18000b6b2  mov     rbx, r9
0x18000b6b5  mov     esi, r8d
0x18000b6b8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000b6bf  mov     [rsp+0AC0h+var_A90], rax
0x18000b6c4  xorps   xmm0, xmm0
0x18000b6c7  movdqu  [rsp+0AC0h+var_A88], xmm0
0x18000b6cd  xor     r14d, r14d
0x18000b6d0  mov     [rsp+0AC0h+var_A78], r14d
0x18000b6d5  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b6dc  test    r9, r9
0x18000b6df  jz      short loc_18000B708
0x18000b6e1  mov     rax, [r9]
0x18000b6e4  jmp     short loc_18000B703
0x18000b6e6  mov     r8, [rbx+8]; unsigned __int16 *
0x18000b6ea  test    r8, r8
0x18000b6ed  jz      short loc_18000B6FC
0x18000b6ef  mov     rdx, rax; unsigned __int16 *
0x18000b6f2  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000b6f7  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000b6fc  add     rbx, 10h
0x18000b700  mov     rax, [rbx]
0x18000b703  test    rax, rax
0x18000b706  jnz     short loc_18000B6E6
0x18000b708  mov     rax, [rdi]
0x18000b70b  lea     rdx, [rsp+0AC0h+var_A90]
0x18000b710  mov     rcx, rdi
0x18000b713  mov     rax, [rax+28h]
0x18000b717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b71c  mov     ebx, eax
0x18000b71e  test    eax, eax
0x18000b720  js      loc_18000B8A7
0x18000b726  mov     rbx, cs:hModule
0x18000b72d  mov     edi, 104h
0x18000b732  mov     r8d, edi; nSize
0x18000b735  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x18000b73a  mov     rcx, rbx; hModule
0x18000b73d  call    cs:__imp_GetModuleFileNameW
0x18000b743  test    eax, eax
0x18000b745  jnz     short loc_18000B753
0x18000b747  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b74c  mov     ebx, eax
0x18000b74e  jmp     loc_18000B8A7
0x18000b753  cmp     eax, edi
0x18000b755  jnz     short loc_18000B761
0x18000b757  mov     ebx, 8007007Ah
0x18000b75c  jmp     loc_18000B8A7
0x18000b761  lea     rdx, [rsp+0AC0h+Filename]
0x18000b766  mov     ecx, r14d
0x18000b769  mov     r9d, 27h ; '''
0x18000b76f  movzx   r8d, word ptr [rdx]
0x18000b773  test    r8w, r8w
0x18000b777  jz      short loc_18000B7A9
0x18000b779  mov     [rbp+rcx*2+9C0h+Src], r8w
0x18000b782  cmp     r8w, r9w
0x18000b786  jnz     short loc_18000B79B
0x18000b788  cmp     ecx, 206h
0x18000b78e  jnb     short loc_18000B79B
0x18000b790  inc     ecx
0x18000b792  mov     [rbp+rcx*2+9C0h+Src], r9w
0x18000b79b  add     rdx, 2
0x18000b79f  inc     ecx
0x18000b7a1  cmp     ecx, 207h
0x18000b7a7  jb      short loc_18000B76F
0x18000b7a9  mov     [rbp+rcx*2+9C0h+Src], r14w
0x18000b7b2  test    rbx, rbx
0x18000b7b5  jz      short loc_18000B7D0
0x18000b7b7  xor     ecx, ecx; lpModuleName
0x18000b7b9  call    cs:__imp_GetModuleHandleW
0x18000b7bf  cmp     rbx, rax
0x18000b7c2  jz      short loc_18000B7D0
0x18000b7c4  lea     r8, [rbp+9C0h+Src]
0x18000b7cb  jmp     loc_18000B85F
0x18000b7d0  mov     edi, 22h ; '"'
0x18000b7d5  mov     [rbp+9C0h+var_440], di
0x18000b7dc  lea     rcx, [rbp+9C0h+Src]
0x18000b7e3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000b7e7  mov     rax, rbx
0x18000b7ea  inc     rax
0x18000b7ed  cmp     [rcx+rax*2], r14w
0x18000b7f2  jnz     short loc_18000B7EA
0x18000b7f4  inc     eax
0x18000b7f6  movsxd  r8, eax
0x18000b7f9  add     r8, r8; Size
0x18000b7fc  jz      short loc_18000B81E
0x18000b7fe  cmp     r8, 414h
0x18000b805  ja      loc_18000B8DA
0x18000b80b  lea     rdx, [rbp+9C0h+Src]; Src
0x18000b812  lea     rcx, [rbp+9C0h+var_43E]; void *
0x18000b819  call    memcpy_0
0x18000b81e  lea     rax, [rbp+9C0h+var_440]
0x18000b825  inc     rbx
0x18000b828  cmp     [rax+rbx*2], r14w
0x18000b82d  jnz     short loc_18000B825
0x18000b82f  movsxd  rax, ebx
0x18000b832  mov     [rbp+rax*2+9C0h+var_440], di
0x18000b83a  lea     rcx, ds:2[rax*2]
0x18000b842  cmp     rcx, 418h
0x18000b849  jnb     loc_18000B926
0x18000b84f  mov     [rbp+rcx+9C0h+var_440], r14w
0x18000b858  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x18000b85f  lea     rdx, aModule; "Module"
0x18000b866  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000b86b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000b870  neg     eax
0x18000b872  sbb     ebx, ebx
0x18000b874  mov     edi, 8007000Eh
0x18000b879  not     ebx
0x18000b87b  and     ebx, edi
0x18000b87d  test    ebx, ebx
0x18000b87f  js      short loc_18000B8A7
0x18000b881  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x18000b888  lea     rdx, aModuleRaw; "Module_Raw"
0x18000b88f  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000b894  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000b899  mov     ecx, eax
0x18000b89b  neg     ecx
0x18000b89d  sbb     ebx, ebx
0x18000b89f  not     ebx
0x18000b8a1  and     ebx, edi
0x18000b8a3  test    eax, eax
0x18000b8a5  jnz     short loc_18000B8F8
0x18000b8a7  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000b8ac  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000b8b1  mov     eax, ebx
0x18000b8b3  mov     rcx, [rbp+9C0h+var_20]
0x18000b8ba  xor     rcx, rsp; StackCookie
0x18000b8bd  call    __security_check_cookie
0x18000b8c2  lea     r11, [rsp+0AC0h+var_10]
0x18000b8ca  mov     rbx, [r11+20h]
0x18000b8ce  mov     rsi, [r11+28h]
0x18000b8d2  mov     rsp, r11
0x18000b8d5  pop     r14
0x18000b8d7  pop     rdi
0x18000b8d8  pop     rbp
0x18000b8d9  retn
0x18000b8da  call    cs:__imp__o__errno
0x18000b8e0  mov     [rax], edi
0x18000b8e2  call    _invalid_parameter_noinfo
0x18000b8e7  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000b8ec  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000b8f1  mov     eax, 80004005h
0x18000b8f6  jmp     short loc_18000B8B3
0x18000b8f8  lea     r9, aRegistry; "REGISTRY"
0x18000b8ff  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x18000b904  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000b909  test    esi, esi
0x18000b90b  jz      short loc_18000B917
0x18000b90d  mov     [rsp+0AC0h+var_AA0], 1
0x18000b915  jmp     short loc_18000B91C
0x18000b917  mov     [rsp+0AC0h+var_AA0], r14d; int
0x18000b91c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000b921  jmp     loc_18000B74C
0x18000b926  call    __report_rangecheckfailure
```
