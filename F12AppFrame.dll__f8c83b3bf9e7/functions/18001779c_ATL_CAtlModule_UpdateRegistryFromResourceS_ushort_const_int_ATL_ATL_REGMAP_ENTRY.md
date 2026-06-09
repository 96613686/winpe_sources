# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001779c`
- end: `0x180017a58`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `700`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180017a70`

## callees

- `0x180001800`
- `0x180002050`
- `0x1800025f2`
- `0x180005e44`
- `0x180012474`
- `0x18001277c`
- `0x180015c5c`
- `0x18001779c`
- `0x180032ac8`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800179ee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800179ee`
- `KERNEL32!GetModuleFileNameW` at `0x180017852`
- `KERNEL32!GetModuleFileNameW` at `0x180017852`
- `KERNEL32!GetModuleHandleW` at `0x1800178ce`
- `KERNEL32!GetModuleHandleW` at `0x1800178ce`

## string_xrefs

- `0x180017a2a`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v9; // r8
  signed int v10; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  signed int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  size_t v21; // r8
  unsigned __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
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
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      v9 = v4[1];
      if ( v9 )
        ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, i, v9);
      v4 += 2;
    }
  }
  v10 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v26);
  if ( v10 < 0 )
    goto LABEL_32;
  v11 = hInst;
  ModuleFileNameW = GetModuleFileNameW(hInst, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v10 = Error;
LABEL_32:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v26);
    return (unsigned int)v10;
  }
  if ( ModuleFileNameW == 260 )
  {
    v10 = -2147024774;
    goto LABEL_32;
  }
  v14 = Filename;
  v15 = 0;
  v16 = 39;
  do
  {
    v17 = *v14;
    if ( !*v14 )
      break;
    Src[v15] = v17;
    if ( v17 == 39 && (unsigned int)v15 < 0x206 )
    {
      LODWORD(v15) = v15 + 1;
      Src[(unsigned int)v15] = 39;
    }
    ++v14;
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < 0x207 );
  Src[v15] = 0;
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v18 = Src;
    goto LABEL_30;
  }
  v31 = 34;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( Src[v20] );
  v21 = 2LL * ((int)v20 + 1);
  if ( !v21 )
  {
    do
LABEL_27:
      ++v19;
    while ( *(_WORD *)&v32[2 * v19 - 2] );
    *(_WORD *)&v32[2 * (int)v19 - 2] = 34;
    v22 = 2LL * (int)v19 + 2;
    if ( v22 >= 0x418 )
      _report_rangecheckfailure(v22, v14, v21, v16);
    *(_WORD *)&v32[v22 - 2] = 0;
    v18 = &v31;
LABEL_30:
    v23 = -ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module", v18);
    v10 = v23 == 0 ? 0x8007000E : 0;
    if ( !v23 )
      goto LABEL_32;
    v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module_Raw", Src);
    v10 = v24 == 0 ? 0x8007000E : 0;
    if ( !v24 )
      goto LABEL_32;
    if ( a3 )
    {
      if ( a2 )
      {
        Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v26, Filename, a2, L"REGISTRY", 1);
        goto LABEL_10;
      }
    }
    else if ( a2 )
    {
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v26, Filename, a2, L"REGISTRY", 0);
      goto LABEL_10;
    }
    v10 = -2147024809;
    goto LABEL_32;
  }
  if ( v21 <= 0x414 )
  {
    memcpy_0(v32, Src, v21);
    goto LABEL_27;
  }
  *(_DWORD *)_o__errno(Src, v14, v21, v16) = 34;
  invalid_parameter_noinfo();
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v26);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001779c  mov     [rsp-8+arg_10], rbx
0x1800177a1  push    rbp
0x1800177a2  push    rsi
0x1800177a3  push    rdi
0x1800177a4  push    r14
0x1800177a6  push    r15
0x1800177a8  lea     rbp, [rsp-9B0h]
0x1800177b0  sub     rsp, 0AB0h
0x1800177b7  mov     rax, cs:__security_cookie
0x1800177be  xor     rax, rsp
0x1800177c1  mov     [rbp+9D0h+var_30], rax
0x1800177c8  mov     rbx, r9
0x1800177cb  mov     r14d, r8d
0x1800177ce  mov     rsi, rdx
0x1800177d1  mov     rdi, rcx
0x1800177d4  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800177db  mov     [rsp+0AD0h+var_AA0], rax
0x1800177e0  xorps   xmm0, xmm0
0x1800177e3  movdqu  [rsp+0AD0h+var_A98], xmm0
0x1800177e9  xor     r15d, r15d
0x1800177ec  mov     [rsp+0AD0h+var_A88], r15d
0x1800177f1  test    r9, r9
0x1800177f4  jz      short loc_18001781D
0x1800177f6  mov     rax, [r9]
0x1800177f9  jmp     short loc_180017818
0x1800177fb  mov     r8, [rbx+8]; unsigned __int16 *
0x1800177ff  test    r8, r8
0x180017802  jz      short loc_180017811
0x180017804  mov     rdx, rax; unsigned __int16 *
0x180017807  lea     rcx, [rsp+0AD0h+var_A98]; this
0x18001780c  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180017811  add     rbx, 10h
0x180017815  mov     rax, [rbx]
0x180017818  test    rax, rax
0x18001781b  jnz     short loc_1800177FB
0x18001781d  mov     rax, [rdi]
0x180017820  lea     rdx, [rsp+0AD0h+var_AA0]
0x180017825  mov     rcx, rdi
0x180017828  mov     rax, [rax+28h]
0x18001782c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017831  mov     ebx, eax
0x180017833  test    eax, eax
0x180017835  js      loc_1800179BC
0x18001783b  mov     rbx, cs:hInst
0x180017842  mov     edi, 104h
0x180017847  mov     r8d, edi; nSize
0x18001784a  lea     rdx, [rsp+0AD0h+Filename]; lpFilename
0x18001784f  mov     rcx, rbx; hModule
0x180017852  call    cs:__imp_GetModuleFileNameW
0x180017858  test    eax, eax
0x18001785a  jnz     short loc_180017868
0x18001785c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180017861  mov     ebx, eax
0x180017863  jmp     loc_1800179BC
0x180017868  cmp     eax, edi
0x18001786a  jnz     short loc_180017876
0x18001786c  mov     ebx, 8007007Ah
0x180017871  jmp     loc_1800179BC
0x180017876  lea     rdx, [rsp+0AD0h+Filename]
0x18001787b  mov     ecx, r15d
0x18001787e  mov     r9d, 27h ; '''
0x180017884  movzx   r8d, word ptr [rdx]
0x180017888  test    r8w, r8w
0x18001788c  jz      short loc_1800178BE
0x18001788e  mov     [rbp+rcx*2+9D0h+Src], r8w
0x180017897  cmp     r8w, r9w
0x18001789b  jnz     short loc_1800178B0
0x18001789d  cmp     ecx, 206h
0x1800178a3  jnb     short loc_1800178B0
0x1800178a5  inc     ecx
0x1800178a7  mov     [rbp+rcx*2+9D0h+Src], r9w
0x1800178b0  add     rdx, 2
0x1800178b4  inc     ecx
0x1800178b6  cmp     ecx, 207h
0x1800178bc  jb      short loc_180017884
0x1800178be  mov     [rbp+rcx*2+9D0h+Src], r15w
0x1800178c7  test    rbx, rbx
0x1800178ca  jz      short loc_1800178E5
0x1800178cc  xor     ecx, ecx; lpModuleName
0x1800178ce  call    cs:__imp_GetModuleHandleW
0x1800178d4  cmp     rbx, rax
0x1800178d7  jz      short loc_1800178E5
0x1800178d9  lea     r8, [rbp+9D0h+Src]
0x1800178e0  jmp     loc_180017974
0x1800178e5  mov     edi, 22h ; '"'
0x1800178ea  mov     [rbp+9D0h+var_450], di
0x1800178f1  lea     rcx, [rbp+9D0h+Src]
0x1800178f8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800178fc  mov     rax, rbx
0x1800178ff  inc     rax
0x180017902  cmp     [rcx+rax*2], r15w
0x180017907  jnz     short loc_1800178FF
0x180017909  inc     eax
0x18001790b  movsxd  r8, eax
0x18001790e  add     r8, r8; Size
0x180017911  jz      short loc_180017933
0x180017913  cmp     r8, 414h
0x18001791a  ja      loc_1800179EE
0x180017920  lea     rdx, [rbp+9D0h+Src]; Src
0x180017927  lea     rcx, [rbp+9D0h+var_44E]; void *
0x18001792e  call    memcpy_0
0x180017933  lea     rax, [rbp+9D0h+var_450]
0x18001793a  inc     rbx
0x18001793d  cmp     [rax+rbx*2], r15w
0x180017942  jnz     short loc_18001793A
0x180017944  movsxd  rax, ebx
0x180017947  mov     [rbp+rax*2+9D0h+var_450], di
0x18001794f  lea     rcx, ds:2[rax*2]
0x180017957  cmp     rcx, 418h
0x18001795e  jnb     loc_180017A52
0x180017964  mov     [rbp+rcx+9D0h+var_450], r15w
0x18001796d  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x180017974  lea     rdx, aModule; "Module"
0x18001797b  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180017980  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180017985  neg     eax
0x180017987  sbb     ebx, ebx
0x180017989  mov     edi, 8007000Eh
0x18001798e  not     ebx
0x180017990  and     ebx, edi
0x180017992  test    ebx, ebx
0x180017994  js      short loc_1800179BC
0x180017996  lea     r8, [rbp+9D0h+Src]; unsigned __int16 *
0x18001799d  lea     rdx, aModuleRaw; "Module_Raw"
0x1800179a4  lea     rcx, [rsp+0AD0h+var_A98]; this
0x1800179a9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800179ae  mov     ecx, eax
0x1800179b0  neg     ecx
0x1800179b2  sbb     ebx, ebx
0x1800179b4  not     ebx
0x1800179b6  and     ebx, edi
0x1800179b8  test    eax, eax
0x1800179ba  jnz     short loc_180017A0C
0x1800179bc  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x1800179c1  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800179c6  mov     eax, ebx
0x1800179c8  mov     rcx, [rbp+9D0h+var_30]
0x1800179cf  xor     rcx, rsp; StackCookie
0x1800179d2  call    __security_check_cookie
0x1800179d7  mov     rbx, [rsp+0AD0h+arg_10]
0x1800179df  add     rsp, 0AB0h
0x1800179e6  pop     r15
0x1800179e8  pop     r14
0x1800179ea  pop     rdi
0x1800179eb  pop     rsi
0x1800179ec  pop     rbp
0x1800179ed  retn
0x1800179ee  call    cs:__imp__o__errno
0x1800179f4  mov     [rax], edi
0x1800179f6  call    _invalid_parameter_noinfo
0x1800179fb  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180017a00  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180017a05  mov     eax, 80004005h
0x180017a0a  jmp     short loc_1800179C8
0x180017a0c  test    r14d, r14d
0x180017a0f  jz      short loc_180017A20
0x180017a11  test    rsi, rsi
0x180017a14  jz      short loc_180017A48
0x180017a16  mov     [rsp+0AD0h+var_AB0], 1
0x180017a1e  jmp     short loc_180017A2A
0x180017a20  test    rsi, rsi
0x180017a23  jz      short loc_180017A48
0x180017a25  mov     [rsp+0AD0h+var_AB0], r15d; int
0x180017a2a  lea     r9, aRegistry; "REGISTRY"
0x180017a31  mov     r8, rsi; unsigned __int16 *
0x180017a34  lea     rdx, [rsp+0AD0h+Filename]; unsigned __int16 *
0x180017a39  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180017a3e  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180017a43  jmp     loc_180017861
0x180017a48  mov     ebx, 80070057h
0x180017a4d  jmp     loc_1800179BC
0x180017a52  call    __report_rangecheckfailure
```
