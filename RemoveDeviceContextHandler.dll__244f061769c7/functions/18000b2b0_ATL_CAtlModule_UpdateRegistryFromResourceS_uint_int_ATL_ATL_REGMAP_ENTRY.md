# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000b2b0`
- end: `0x18000b50b`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `603`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, __int64, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18000b2a0`

## callees

- `0x180002458`
- `0x180005bd0`
- `0x180006468`
- `0x180006db8`
- `0x1800096c8`
- `0x18000b2b0`
- `0x18000c990`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b402`
- `msvcrt!memcpy_s` at `0x18000b402`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000b330`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000b330`

## string_xrefs

- `0x18000b4ab`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v4; // esi
  __int64 v5; // rax
  signed int v6; // ebx
  HMODULE v7; // rbx
  DWORD ModuleFileNameW; // eax
  int Error; // eax
  WCHAR *v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // r8
  unsigned __int16 *v13; // r8
  __int64 v14; // rbx
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  BOOL v18; // eax
  const unsigned __int16 *v19; // r8
  void **v21; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v22; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Source[520]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v26; // [rsp+680h] [rbp+580h] BYREF
  _BYTE Destination[1054]; // [rsp+682h] [rbp+582h] BYREF

  v21 = &ATL::CRegObject::`vftable';
  v4 = a3;
  v23 = 0;
  v5 = *(_QWORD *)ATL::_pAtlModule;
  v22 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***, __int64, struct ATL::_ATL_REGMAP_ENTRY *))(v5 + 40))(
         ATL::_pAtlModule,
         &v21,
         a3,
         a4);
  if ( v6 < 0 )
    goto LABEL_25;
  v7 = hInstance;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_4:
    v6 = Error;
LABEL_25:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v21);
    return (unsigned int)v6;
  }
  if ( ModuleFileNameW == 260 )
  {
    v6 = -2147024774;
    goto LABEL_25;
  }
  v10 = Filename;
  v11 = 0;
  do
  {
    v12 = *v10;
    if ( !*v10 )
      break;
    Source[v11] = v12;
    if ( v12 == 39 && (unsigned int)v11 < 0x206 )
    {
      LODWORD(v11) = v11 + 1;
      Source[(unsigned int)v11] = 39;
    }
    ++v10;
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < 0x207 );
  Source[v11] = 0;
  if ( v7 && v7 != GetModuleHandleW(0) )
  {
    v13 = Source;
LABEL_22:
    if ( !-ATL::CExpansionVector::Add((void **)&v22, L"Module", v13) )
    {
      v6 = -2147024882;
      goto LABEL_25;
    }
    v18 = ATL::CExpansionVector::Add((void **)&v22, L"Module_Raw", Source);
    v6 = !v18 ? 0x8007000E : 0;
    if ( !v18 )
      goto LABEL_25;
    if ( v4 )
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v21, Filename, v19, L"REGISTRY", 1);
    else
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v21, Filename, v19, L"REGISTRY", 0);
    goto LABEL_4;
  }
  v14 = -1;
  v26 = 34;
  v15 = -1;
  do
    ++v15;
  while ( Source[v15] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v15 + 1)) )
  {
    do
      ++v14;
    while ( *(_WORD *)&Destination[2 * v14 - 2] );
    v16 = 2LL * (int)v14 + 2;
    *(_WORD *)&Destination[2 * (int)v14 - 2] = 34;
    if ( v16 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v16 - 2] = 0;
    v13 = &v26;
    goto LABEL_22;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v21);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000b2b0  push    rbp
0x18000b2b2  push    rbx
0x18000b2b3  push    rsi
0x18000b2b4  push    rdi
0x18000b2b5  push    r14
0x18000b2b7  lea     rbp, [rsp-9B0h]
0x18000b2bf  sub     rsp, 0AB0h
0x18000b2c6  mov     rax, cs:__security_cookie
0x18000b2cd  xor     rax, rsp
0x18000b2d0  mov     [rbp+9D0h+var_30], rax
0x18000b2d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b2de  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000b2e5  mov     [rsp+0AD0h+var_AA0], rax
0x18000b2ea  lea     rdx, [rsp+0AD0h+var_AA0]
0x18000b2ef  xorps   xmm0, xmm0
0x18000b2f2  xor     r14d, r14d
0x18000b2f5  mov     esi, r8d
0x18000b2f8  mov     [rsp+0AD0h+var_A88], r14d
0x18000b2fd  mov     rax, [rcx]
0x18000b300  movdqu  [rsp+0AD0h+var_A98], xmm0
0x18000b306  mov     rax, [rax+28h]
0x18000b30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b30f  mov     ebx, eax
0x18000b311  test    eax, eax
0x18000b313  js      loc_18000B49D
0x18000b319  mov     rbx, cs:hInstance
0x18000b320  lea     rdx, [rsp+0AD0h+Filename]; lpFilename
0x18000b325  mov     edi, 104h
0x18000b32a  mov     rcx, rbx; hModule
0x18000b32d  mov     r8d, edi; nSize
0x18000b330  call    cs:__imp_GetModuleFileNameW
0x18000b336  test    eax, eax
0x18000b338  jnz     short loc_18000B346
0x18000b33a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b33f  mov     ebx, eax
0x18000b341  jmp     loc_18000B49D
0x18000b346  cmp     eax, edi
0x18000b348  jnz     short loc_18000B354
0x18000b34a  mov     ebx, 8007007Ah
0x18000b34f  jmp     loc_18000B49D
0x18000b354  lea     rdx, [rsp+0AD0h+Filename]
0x18000b359  mov     ecx, r14d
0x18000b35c  mov     r9d, 27h ; '''
0x18000b362  movzx   r8d, word ptr [rdx]
0x18000b366  test    r8w, r8w
0x18000b36a  jz      short loc_18000B39C
0x18000b36c  mov     [rbp+rcx*2+9D0h+Source], r8w
0x18000b375  cmp     r8w, r9w
0x18000b379  jnz     short loc_18000B38E
0x18000b37b  cmp     ecx, 206h
0x18000b381  jnb     short loc_18000B38E
0x18000b383  inc     ecx
0x18000b385  mov     [rbp+rcx*2+9D0h+Source], r9w
0x18000b38e  add     rdx, 2
0x18000b392  inc     ecx
0x18000b394  cmp     ecx, 207h
0x18000b39a  jb      short loc_18000B362
0x18000b39c  mov     [rbp+rcx*2+9D0h+Source], r14w
0x18000b3a5  test    rbx, rbx
0x18000b3a8  jz      short loc_18000B3C3
0x18000b3aa  xor     ecx, ecx; lpModuleName
0x18000b3ac  call    cs:__imp_GetModuleHandleW
0x18000b3b2  cmp     rbx, rax
0x18000b3b5  jz      short loc_18000B3C3
0x18000b3b7  lea     r8, [rbp+9D0h+Source]
0x18000b3be  jmp     loc_18000B451
0x18000b3c3  mov     edi, 22h ; '"'
0x18000b3c8  lea     rcx, [rbp+9D0h+Source]
0x18000b3cf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000b3d3  mov     [rbp+9D0h+var_450], di
0x18000b3da  mov     rax, rbx
0x18000b3dd  inc     rax
0x18000b3e0  cmp     [rcx+rax*2], r14w
0x18000b3e5  jnz     short loc_18000B3DD
0x18000b3e7  inc     eax
0x18000b3e9  lea     r8, [rbp+9D0h+Source]; Source
0x18000b3f0  movsxd  r9, eax
0x18000b3f3  lea     rcx, [rbp+9D0h+Destination]; Destination
0x18000b3fa  add     r9, r9; SourceSize
0x18000b3fd  mov     edx, 414h; DestinationSize
0x18000b402  call    cs:__imp_memcpy_s
0x18000b408  test    eax, eax
0x18000b40a  jnz     loc_18000B4D9
0x18000b410  lea     rax, [rbp+9D0h+var_450]
0x18000b417  inc     rbx
0x18000b41a  cmp     [rax+rbx*2], r14w
0x18000b41f  jnz     short loc_18000B417
0x18000b421  movsxd  rax, ebx
0x18000b424  lea     rcx, ds:2[rax*2]
0x18000b42c  mov     [rbp+rax*2+9D0h+var_450], di
0x18000b434  cmp     rcx, 418h
0x18000b43b  jnb     loc_18000B505
0x18000b441  mov     [rbp+rcx+9D0h+var_450], r14w
0x18000b44a  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x18000b451  lea     rdx, aModule; "Module"
0x18000b458  lea     rcx, [rsp+0AD0h+var_A98]; this
0x18000b45d  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000b462  neg     eax
0x18000b464  mov     edi, 8007000Eh
0x18000b469  sbb     ecx, ecx
0x18000b46b  not     ecx
0x18000b46d  and     ecx, edi
0x18000b46f  test    ecx, ecx
0x18000b471  jns     short loc_18000B477
0x18000b473  mov     ebx, ecx
0x18000b475  jmp     short loc_18000B49D
0x18000b477  lea     r8, [rbp+9D0h+Source]; unsigned __int16 *
0x18000b47e  lea     rdx, aModuleRaw; "Module_Raw"
0x18000b485  lea     rcx, [rsp+0AD0h+var_A98]; this
0x18000b48a  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000b48f  mov     ecx, eax
0x18000b491  neg     ecx
0x18000b493  sbb     ebx, ebx
0x18000b495  not     ebx
0x18000b497  and     ebx, edi
0x18000b499  test    eax, eax
0x18000b49b  jnz     short loc_18000B4AB
0x18000b49d  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x18000b4a2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000b4a7  mov     eax, ebx
0x18000b4a9  jmp     short loc_18000B4E8
0x18000b4ab  lea     r9, aRegistry; "REGISTRY"
0x18000b4b2  lea     rdx, [rsp+0AD0h+Filename]; unsigned __int16 *
0x18000b4b7  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x18000b4bc  test    esi, esi
0x18000b4be  jz      short loc_18000B4CA
0x18000b4c0  mov     [rsp+0AD0h+var_AB0], 1
0x18000b4c8  jmp     short loc_18000B4CF
0x18000b4ca  mov     [rsp+0AD0h+var_AB0], r14d; int
0x18000b4cf  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000b4d4  jmp     loc_18000B33F
0x18000b4d9  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x18000b4de  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000b4e3  mov     eax, 80004005h
0x18000b4e8  mov     rcx, [rbp+9D0h+var_30]
0x18000b4ef  xor     rcx, rsp; StackCookie
0x18000b4f2  call    __security_check_cookie
0x18000b4f7  add     rsp, 0AB0h
0x18000b4fe  pop     r14
0x18000b500  pop     rdi
0x18000b501  pop     rsi
0x18000b502  pop     rbx
0x18000b503  pop     rbp
0x18000b504  retn
0x18000b505  call    __report_rangecheckfailure
```
