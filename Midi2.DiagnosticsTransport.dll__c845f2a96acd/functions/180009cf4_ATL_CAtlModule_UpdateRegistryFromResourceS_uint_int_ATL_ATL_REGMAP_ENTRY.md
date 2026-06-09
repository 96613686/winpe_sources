# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180009cf4`
- end: `0x180009f9c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180009ce0`
- `0x18000b580`
- `0x18000b670`

## callees

- `0x1800033d0`
- `0x180003410`
- `0x1800040f6`
- `0x180004158`
- `0x180004e08`
- `0x180005568`
- `0x180005fdc`
- `0x18000824c`
- `0x180009cf4`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009f4a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009f4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009dad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009dad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e29`

## string_xrefs

- `0x180009f68`: `REGISTRY`

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
0x180009cf4  mov     [rsp-8+arg_0], rbx
0x180009cf9  mov     [rsp-8+arg_8], rsi
0x180009cfe  push    rbp
0x180009cff  push    rdi
0x180009d00  push    r14
0x180009d02  lea     rbp, [rsp-9B0h]
0x180009d0a  sub     rsp, 0AB0h
0x180009d11  mov     rax, cs:__security_cookie
0x180009d18  xor     rax, rsp
0x180009d1b  mov     [rbp+9C0h+var_20], rax
0x180009d22  mov     rbx, r9
0x180009d25  mov     esi, r8d
0x180009d28  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009d2f  mov     [rsp+0AC0h+var_A90], rax
0x180009d34  xorps   xmm0, xmm0
0x180009d37  movdqu  [rsp+0AC0h+var_A88], xmm0
0x180009d3d  xor     r14d, r14d
0x180009d40  mov     [rsp+0AC0h+var_A78], r14d
0x180009d45  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009d4c  test    r9, r9
0x180009d4f  jz      short loc_180009D78
0x180009d51  mov     rax, [r9]
0x180009d54  jmp     short loc_180009D73
0x180009d56  mov     r8, [rbx+8]; unsigned __int16 *
0x180009d5a  test    r8, r8
0x180009d5d  jz      short loc_180009D6C
0x180009d5f  mov     rdx, rax; unsigned __int16 *
0x180009d62  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180009d67  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009d6c  add     rbx, 10h
0x180009d70  mov     rax, [rbx]
0x180009d73  test    rax, rax
0x180009d76  jnz     short loc_180009D56
0x180009d78  mov     rax, [rdi]
0x180009d7b  lea     rdx, [rsp+0AC0h+var_A90]
0x180009d80  mov     rcx, rdi
0x180009d83  mov     rax, [rax+28h]
0x180009d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8c  mov     ebx, eax
0x180009d8e  test    eax, eax
0x180009d90  js      loc_180009F17
0x180009d96  mov     rbx, cs:hModule
0x180009d9d  mov     edi, 104h
0x180009da2  mov     r8d, edi; nSize
0x180009da5  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x180009daa  mov     rcx, rbx; hModule
0x180009dad  call    cs:__imp_GetModuleFileNameW
0x180009db3  test    eax, eax
0x180009db5  jnz     short loc_180009DC3
0x180009db7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009dbc  mov     ebx, eax
0x180009dbe  jmp     loc_180009F17
0x180009dc3  cmp     eax, edi
0x180009dc5  jnz     short loc_180009DD1
0x180009dc7  mov     ebx, 8007007Ah
0x180009dcc  jmp     loc_180009F17
0x180009dd1  lea     rdx, [rsp+0AC0h+Filename]
0x180009dd6  mov     ecx, r14d
0x180009dd9  mov     r9d, 27h ; '''
0x180009ddf  movzx   r8d, word ptr [rdx]
0x180009de3  test    r8w, r8w
0x180009de7  jz      short loc_180009E19
0x180009de9  mov     [rbp+rcx*2+9C0h+Src], r8w
0x180009df2  cmp     r8w, r9w
0x180009df6  jnz     short loc_180009E0B
0x180009df8  cmp     ecx, 206h
0x180009dfe  jnb     short loc_180009E0B
0x180009e00  inc     ecx
0x180009e02  mov     [rbp+rcx*2+9C0h+Src], r9w
0x180009e0b  add     rdx, 2
0x180009e0f  inc     ecx
0x180009e11  cmp     ecx, 207h
0x180009e17  jb      short loc_180009DDF
0x180009e19  mov     [rbp+rcx*2+9C0h+Src], r14w
0x180009e22  test    rbx, rbx
0x180009e25  jz      short loc_180009E40
0x180009e27  xor     ecx, ecx; lpModuleName
0x180009e29  call    cs:__imp_GetModuleHandleW
0x180009e2f  cmp     rbx, rax
0x180009e32  jz      short loc_180009E40
0x180009e34  lea     r8, [rbp+9C0h+Src]
0x180009e3b  jmp     loc_180009ECF
0x180009e40  mov     edi, 22h ; '"'
0x180009e45  mov     [rbp+9C0h+var_440], di
0x180009e4c  lea     rcx, [rbp+9C0h+Src]
0x180009e53  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009e57  mov     rax, rbx
0x180009e5a  inc     rax
0x180009e5d  cmp     [rcx+rax*2], r14w
0x180009e62  jnz     short loc_180009E5A
0x180009e64  inc     eax
0x180009e66  movsxd  r8, eax
0x180009e69  add     r8, r8; Size
0x180009e6c  jz      short loc_180009E8E
0x180009e6e  cmp     r8, 414h
0x180009e75  ja      loc_180009F4A
0x180009e7b  lea     rdx, [rbp+9C0h+Src]; Src
0x180009e82  lea     rcx, [rbp+9C0h+var_43E]; void *
0x180009e89  call    memcpy_0
0x180009e8e  lea     rax, [rbp+9C0h+var_440]
0x180009e95  inc     rbx
0x180009e98  cmp     [rax+rbx*2], r14w
0x180009e9d  jnz     short loc_180009E95
0x180009e9f  movsxd  rax, ebx
0x180009ea2  mov     [rbp+rax*2+9C0h+var_440], di
0x180009eaa  lea     rcx, ds:2[rax*2]
0x180009eb2  cmp     rcx, 418h
0x180009eb9  jnb     loc_180009F96
0x180009ebf  mov     [rbp+rcx+9C0h+var_440], r14w
0x180009ec8  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x180009ecf  lea     rdx, aModule; "Module"
0x180009ed6  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180009edb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009ee0  neg     eax
0x180009ee2  sbb     ebx, ebx
0x180009ee4  mov     edi, 8007000Eh
0x180009ee9  not     ebx
0x180009eeb  and     ebx, edi
0x180009eed  test    ebx, ebx
0x180009eef  js      short loc_180009F17
0x180009ef1  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x180009ef8  lea     rdx, aModuleRaw; "Module_Raw"
0x180009eff  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180009f04  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009f09  mov     ecx, eax
0x180009f0b  neg     ecx
0x180009f0d  sbb     ebx, ebx
0x180009f0f  not     ebx
0x180009f11  and     ebx, edi
0x180009f13  test    eax, eax
0x180009f15  jnz     short loc_180009F68
0x180009f17  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180009f1c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009f21  mov     eax, ebx
0x180009f23  mov     rcx, [rbp+9C0h+var_20]
0x180009f2a  xor     rcx, rsp; StackCookie
0x180009f2d  call    __security_check_cookie
0x180009f32  lea     r11, [rsp+0AC0h+var_10]
0x180009f3a  mov     rbx, [r11+20h]
0x180009f3e  mov     rsi, [r11+28h]
0x180009f42  mov     rsp, r11
0x180009f45  pop     r14
0x180009f47  pop     rdi
0x180009f48  pop     rbp
0x180009f49  retn
0x180009f4a  call    cs:__imp__o__errno
0x180009f50  mov     [rax], edi
0x180009f52  call    _invalid_parameter_noinfo
0x180009f57  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180009f5c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009f61  mov     eax, 80004005h
0x180009f66  jmp     short loc_180009F23
0x180009f68  lea     r9, aRegistry; "REGISTRY"
0x180009f6f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x180009f74  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180009f79  test    esi, esi
0x180009f7b  jz      short loc_180009F87
0x180009f7d  mov     [rsp+0AC0h+var_AA0], 1
0x180009f85  jmp     short loc_180009F8C
0x180009f87  mov     [rsp+0AC0h+var_AA0], r14d; int
0x180009f8c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009f91  jmp     loc_180009DBC
0x180009f96  call    __report_rangecheckfailure
```
