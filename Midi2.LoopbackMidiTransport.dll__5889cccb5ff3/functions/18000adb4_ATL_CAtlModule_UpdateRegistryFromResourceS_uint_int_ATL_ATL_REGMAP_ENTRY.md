# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000adb4`
- end: `0x18000b05c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000ada0`
- `0x18000d480`
- `0x18000d570`

## callees

- `0x180004180`
- `0x1800041c0`
- `0x180004f86`
- `0x180004ff4`
- `0x180005e6c`
- `0x180006608`
- `0x18000707c`
- `0x18000930c`
- `0x18000adb4`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b00a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b00a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aee9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aee9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ae6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ae6d`

## string_xrefs

- `0x18000b028`: `REGISTRY`

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
0x18000adb4  mov     [rsp-8+arg_0], rbx
0x18000adb9  mov     [rsp-8+arg_8], rsi
0x18000adbe  push    rbp
0x18000adbf  push    rdi
0x18000adc0  push    r14
0x18000adc2  lea     rbp, [rsp-9B0h]
0x18000adca  sub     rsp, 0AB0h
0x18000add1  mov     rax, cs:__security_cookie
0x18000add8  xor     rax, rsp
0x18000addb  mov     [rbp+9C0h+var_20], rax
0x18000ade2  mov     rbx, r9
0x18000ade5  mov     esi, r8d
0x18000ade8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000adef  mov     [rsp+0AC0h+var_A90], rax
0x18000adf4  xorps   xmm0, xmm0
0x18000adf7  movdqu  [rsp+0AC0h+var_A88], xmm0
0x18000adfd  xor     r14d, r14d
0x18000ae00  mov     [rsp+0AC0h+var_A78], r14d
0x18000ae05  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ae0c  test    r9, r9
0x18000ae0f  jz      short loc_18000AE38
0x18000ae11  mov     rax, [r9]
0x18000ae14  jmp     short loc_18000AE33
0x18000ae16  mov     r8, [rbx+8]; unsigned __int16 *
0x18000ae1a  test    r8, r8
0x18000ae1d  jz      short loc_18000AE2C
0x18000ae1f  mov     rdx, rax; unsigned __int16 *
0x18000ae22  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000ae27  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000ae2c  add     rbx, 10h
0x18000ae30  mov     rax, [rbx]
0x18000ae33  test    rax, rax
0x18000ae36  jnz     short loc_18000AE16
0x18000ae38  mov     rax, [rdi]
0x18000ae3b  lea     rdx, [rsp+0AC0h+var_A90]
0x18000ae40  mov     rcx, rdi
0x18000ae43  mov     rax, [rax+28h]
0x18000ae47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4c  mov     ebx, eax
0x18000ae4e  test    eax, eax
0x18000ae50  js      loc_18000AFD7
0x18000ae56  mov     rbx, cs:hModule
0x18000ae5d  mov     edi, 104h
0x18000ae62  mov     r8d, edi; nSize
0x18000ae65  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x18000ae6a  mov     rcx, rbx; hModule
0x18000ae6d  call    cs:__imp_GetModuleFileNameW
0x18000ae73  test    eax, eax
0x18000ae75  jnz     short loc_18000AE83
0x18000ae77  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000ae7c  mov     ebx, eax
0x18000ae7e  jmp     loc_18000AFD7
0x18000ae83  cmp     eax, edi
0x18000ae85  jnz     short loc_18000AE91
0x18000ae87  mov     ebx, 8007007Ah
0x18000ae8c  jmp     loc_18000AFD7
0x18000ae91  lea     rdx, [rsp+0AC0h+Filename]
0x18000ae96  mov     ecx, r14d
0x18000ae99  mov     r9d, 27h ; '''
0x18000ae9f  movzx   r8d, word ptr [rdx]
0x18000aea3  test    r8w, r8w
0x18000aea7  jz      short loc_18000AED9
0x18000aea9  mov     [rbp+rcx*2+9C0h+Src], r8w
0x18000aeb2  cmp     r8w, r9w
0x18000aeb6  jnz     short loc_18000AECB
0x18000aeb8  cmp     ecx, 206h
0x18000aebe  jnb     short loc_18000AECB
0x18000aec0  inc     ecx
0x18000aec2  mov     [rbp+rcx*2+9C0h+Src], r9w
0x18000aecb  add     rdx, 2
0x18000aecf  inc     ecx
0x18000aed1  cmp     ecx, 207h
0x18000aed7  jb      short loc_18000AE9F
0x18000aed9  mov     [rbp+rcx*2+9C0h+Src], r14w
0x18000aee2  test    rbx, rbx
0x18000aee5  jz      short loc_18000AF00
0x18000aee7  xor     ecx, ecx; lpModuleName
0x18000aee9  call    cs:__imp_GetModuleHandleW
0x18000aeef  cmp     rbx, rax
0x18000aef2  jz      short loc_18000AF00
0x18000aef4  lea     r8, [rbp+9C0h+Src]
0x18000aefb  jmp     loc_18000AF8F
0x18000af00  mov     edi, 22h ; '"'
0x18000af05  mov     [rbp+9C0h+var_440], di
0x18000af0c  lea     rcx, [rbp+9C0h+Src]
0x18000af13  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000af17  mov     rax, rbx
0x18000af1a  inc     rax
0x18000af1d  cmp     [rcx+rax*2], r14w
0x18000af22  jnz     short loc_18000AF1A
0x18000af24  inc     eax
0x18000af26  movsxd  r8, eax
0x18000af29  add     r8, r8; Size
0x18000af2c  jz      short loc_18000AF4E
0x18000af2e  cmp     r8, 414h
0x18000af35  ja      loc_18000B00A
0x18000af3b  lea     rdx, [rbp+9C0h+Src]; Src
0x18000af42  lea     rcx, [rbp+9C0h+var_43E]; void *
0x18000af49  call    memcpy_0
0x18000af4e  lea     rax, [rbp+9C0h+var_440]
0x18000af55  inc     rbx
0x18000af58  cmp     [rax+rbx*2], r14w
0x18000af5d  jnz     short loc_18000AF55
0x18000af5f  movsxd  rax, ebx
0x18000af62  mov     [rbp+rax*2+9C0h+var_440], di
0x18000af6a  lea     rcx, ds:2[rax*2]
0x18000af72  cmp     rcx, 418h
0x18000af79  jnb     loc_18000B056
0x18000af7f  mov     [rbp+rcx+9C0h+var_440], r14w
0x18000af88  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x18000af8f  lea     rdx, aModule; "Module"
0x18000af96  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000af9b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000afa0  neg     eax
0x18000afa2  sbb     ebx, ebx
0x18000afa4  mov     edi, 8007000Eh
0x18000afa9  not     ebx
0x18000afab  and     ebx, edi
0x18000afad  test    ebx, ebx
0x18000afaf  js      short loc_18000AFD7
0x18000afb1  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x18000afb8  lea     rdx, aModuleRaw; "Module_Raw"
0x18000afbf  lea     rcx, [rsp+0AC0h+var_A88]; this
0x18000afc4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000afc9  mov     ecx, eax
0x18000afcb  neg     ecx
0x18000afcd  sbb     ebx, ebx
0x18000afcf  not     ebx
0x18000afd1  and     ebx, edi
0x18000afd3  test    eax, eax
0x18000afd5  jnz     short loc_18000B028
0x18000afd7  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000afdc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000afe1  mov     eax, ebx
0x18000afe3  mov     rcx, [rbp+9C0h+var_20]
0x18000afea  xor     rcx, rsp; StackCookie
0x18000afed  call    __security_check_cookie
0x18000aff2  lea     r11, [rsp+0AC0h+var_10]
0x18000affa  mov     rbx, [r11+20h]
0x18000affe  mov     rsi, [r11+28h]
0x18000b002  mov     rsp, r11
0x18000b005  pop     r14
0x18000b007  pop     rdi
0x18000b008  pop     rbp
0x18000b009  retn
0x18000b00a  call    cs:__imp__o__errno
0x18000b010  mov     [rax], edi
0x18000b012  call    _invalid_parameter_noinfo
0x18000b017  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000b01c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000b021  mov     eax, 80004005h
0x18000b026  jmp     short loc_18000AFE3
0x18000b028  lea     r9, aRegistry; "REGISTRY"
0x18000b02f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x18000b034  lea     rcx, [rsp+0AC0h+var_A90]; this
0x18000b039  test    esi, esi
0x18000b03b  jz      short loc_18000B047
0x18000b03d  mov     [rsp+0AC0h+var_AA0], 1
0x18000b045  jmp     short loc_18000B04C
0x18000b047  mov     [rsp+0AC0h+var_AA0], r14d; int
0x18000b04c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000b051  jmp     loc_18000AE7C
0x18000b056  call    __report_rangecheckfailure
```
