# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180008bf4`
- end: `0x180008e9c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180008be0`
- `0x18000a470`
- `0x18000a560`

## callees

- `0x180002470`
- `0x1800024b0`
- `0x180002f96`
- `0x180003ca8`
- `0x18000440c`
- `0x180004e7c`
- `0x1800070fc`
- `0x180008bf4`
- `0x180014080`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e4a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008cad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008cad`

## string_xrefs

- `0x180008e68`: `REGISTRY`

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
0x180008bf4  mov     [rsp-8+arg_0], rbx
0x180008bf9  mov     [rsp-8+arg_8], rsi
0x180008bfe  push    rbp
0x180008bff  push    rdi
0x180008c00  push    r14
0x180008c02  lea     rbp, [rsp-9B0h]
0x180008c0a  sub     rsp, 0AB0h
0x180008c11  mov     rax, cs:__security_cookie
0x180008c18  xor     rax, rsp
0x180008c1b  mov     [rbp+9C0h+var_20], rax
0x180008c22  mov     rbx, r9
0x180008c25  mov     esi, r8d
0x180008c28  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008c2f  mov     [rsp+0AC0h+var_A90], rax
0x180008c34  xorps   xmm0, xmm0
0x180008c37  movdqu  [rsp+0AC0h+var_A88], xmm0
0x180008c3d  xor     r14d, r14d
0x180008c40  mov     [rsp+0AC0h+var_A78], r14d
0x180008c45  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008c4c  test    r9, r9
0x180008c4f  jz      short loc_180008C78
0x180008c51  mov     rax, [r9]
0x180008c54  jmp     short loc_180008C73
0x180008c56  mov     r8, [rbx+8]; unsigned __int16 *
0x180008c5a  test    r8, r8
0x180008c5d  jz      short loc_180008C6C
0x180008c5f  mov     rdx, rax; unsigned __int16 *
0x180008c62  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180008c67  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008c6c  add     rbx, 10h
0x180008c70  mov     rax, [rbx]
0x180008c73  test    rax, rax
0x180008c76  jnz     short loc_180008C56
0x180008c78  mov     rax, [rdi]
0x180008c7b  lea     rdx, [rsp+0AC0h+var_A90]
0x180008c80  mov     rcx, rdi
0x180008c83  mov     rax, [rax+28h]
0x180008c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c8c  mov     ebx, eax
0x180008c8e  test    eax, eax
0x180008c90  js      loc_180008E17
0x180008c96  mov     rbx, cs:hModule
0x180008c9d  mov     edi, 104h
0x180008ca2  mov     r8d, edi; nSize
0x180008ca5  lea     rdx, [rsp+0AC0h+Filename]; lpFilename
0x180008caa  mov     rcx, rbx; hModule
0x180008cad  call    cs:__imp_GetModuleFileNameW
0x180008cb3  test    eax, eax
0x180008cb5  jnz     short loc_180008CC3
0x180008cb7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008cbc  mov     ebx, eax
0x180008cbe  jmp     loc_180008E17
0x180008cc3  cmp     eax, edi
0x180008cc5  jnz     short loc_180008CD1
0x180008cc7  mov     ebx, 8007007Ah
0x180008ccc  jmp     loc_180008E17
0x180008cd1  lea     rdx, [rsp+0AC0h+Filename]
0x180008cd6  mov     ecx, r14d
0x180008cd9  mov     r9d, 27h ; '''
0x180008cdf  movzx   r8d, word ptr [rdx]
0x180008ce3  test    r8w, r8w
0x180008ce7  jz      short loc_180008D19
0x180008ce9  mov     [rbp+rcx*2+9C0h+Src], r8w
0x180008cf2  cmp     r8w, r9w
0x180008cf6  jnz     short loc_180008D0B
0x180008cf8  cmp     ecx, 206h
0x180008cfe  jnb     short loc_180008D0B
0x180008d00  inc     ecx
0x180008d02  mov     [rbp+rcx*2+9C0h+Src], r9w
0x180008d0b  add     rdx, 2
0x180008d0f  inc     ecx
0x180008d11  cmp     ecx, 207h
0x180008d17  jb      short loc_180008CDF
0x180008d19  mov     [rbp+rcx*2+9C0h+Src], r14w
0x180008d22  test    rbx, rbx
0x180008d25  jz      short loc_180008D40
0x180008d27  xor     ecx, ecx; lpModuleName
0x180008d29  call    cs:__imp_GetModuleHandleW
0x180008d2f  cmp     rbx, rax
0x180008d32  jz      short loc_180008D40
0x180008d34  lea     r8, [rbp+9C0h+Src]
0x180008d3b  jmp     loc_180008DCF
0x180008d40  mov     edi, 22h ; '"'
0x180008d45  mov     [rbp+9C0h+var_440], di
0x180008d4c  lea     rcx, [rbp+9C0h+Src]
0x180008d53  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008d57  mov     rax, rbx
0x180008d5a  inc     rax
0x180008d5d  cmp     [rcx+rax*2], r14w
0x180008d62  jnz     short loc_180008D5A
0x180008d64  inc     eax
0x180008d66  movsxd  r8, eax
0x180008d69  add     r8, r8; Size
0x180008d6c  jz      short loc_180008D8E
0x180008d6e  cmp     r8, 414h
0x180008d75  ja      loc_180008E4A
0x180008d7b  lea     rdx, [rbp+9C0h+Src]; Src
0x180008d82  lea     rcx, [rbp+9C0h+var_43E]; void *
0x180008d89  call    memcpy_0
0x180008d8e  lea     rax, [rbp+9C0h+var_440]
0x180008d95  inc     rbx
0x180008d98  cmp     [rax+rbx*2], r14w
0x180008d9d  jnz     short loc_180008D95
0x180008d9f  movsxd  rax, ebx
0x180008da2  mov     [rbp+rax*2+9C0h+var_440], di
0x180008daa  lea     rcx, ds:2[rax*2]
0x180008db2  cmp     rcx, 418h
0x180008db9  jnb     loc_180008E96
0x180008dbf  mov     [rbp+rcx+9C0h+var_440], r14w
0x180008dc8  lea     r8, [rbp+9C0h+var_440]; unsigned __int16 *
0x180008dcf  lea     rdx, aModule; "Module"
0x180008dd6  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180008ddb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008de0  neg     eax
0x180008de2  sbb     ebx, ebx
0x180008de4  mov     edi, 8007000Eh
0x180008de9  not     ebx
0x180008deb  and     ebx, edi
0x180008ded  test    ebx, ebx
0x180008def  js      short loc_180008E17
0x180008df1  lea     r8, [rbp+9C0h+Src]; unsigned __int16 *
0x180008df8  lea     rdx, aModuleRaw; "Module_Raw"
0x180008dff  lea     rcx, [rsp+0AC0h+var_A88]; this
0x180008e04  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008e09  mov     ecx, eax
0x180008e0b  neg     ecx
0x180008e0d  sbb     ebx, ebx
0x180008e0f  not     ebx
0x180008e11  and     ebx, edi
0x180008e13  test    eax, eax
0x180008e15  jnz     short loc_180008E68
0x180008e17  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180008e1c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008e21  mov     eax, ebx
0x180008e23  mov     rcx, [rbp+9C0h+var_20]
0x180008e2a  xor     rcx, rsp; StackCookie
0x180008e2d  call    __security_check_cookie
0x180008e32  lea     r11, [rsp+0AC0h+var_10]
0x180008e3a  mov     rbx, [r11+20h]
0x180008e3e  mov     rsi, [r11+28h]
0x180008e42  mov     rsp, r11
0x180008e45  pop     r14
0x180008e47  pop     rdi
0x180008e48  pop     rbp
0x180008e49  retn
0x180008e4a  call    cs:__imp__o__errno
0x180008e50  mov     [rax], edi
0x180008e52  call    _invalid_parameter_noinfo
0x180008e57  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180008e5c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008e61  mov     eax, 80004005h
0x180008e66  jmp     short loc_180008E23
0x180008e68  lea     r9, aRegistry; "REGISTRY"
0x180008e6f  lea     rdx, [rsp+0AC0h+Filename]; unsigned __int16 *
0x180008e74  lea     rcx, [rsp+0AC0h+var_A90]; this
0x180008e79  test    esi, esi
0x180008e7b  jz      short loc_180008E87
0x180008e7d  mov     [rsp+0AC0h+var_AA0], 1
0x180008e85  jmp     short loc_180008E8C
0x180008e87  mov     [rsp+0AC0h+var_AA0], r14d; int
0x180008e8c  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008e91  jmp     loc_180008CBC
0x180008e96  call    __report_rangecheckfailure
```
