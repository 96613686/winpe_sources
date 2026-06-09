# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180017500`
- end: `0x180017796`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180017a60`

## callees

- `0x180001800`
- `0x180002050`
- `0x1800025f2`
- `0x180005e44`
- `0x180012474`
- `0x18001277c`
- `0x180015c5c`
- `0x180017500`
- `0x180032ac8`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017745`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017745`
- `KERNEL32!GetModuleFileNameW` at `0x1800175b8`
- `KERNEL32!GetModuleFileNameW` at `0x1800175b8`
- `KERNEL32!GetModuleHandleW` at `0x18001762d`
- `KERNEL32!GetModuleHandleW` at `0x18001762d`

## string_xrefs

- `0x180017773`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
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
  unsigned __int16 Src[520]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+470h] [rbp+370h] BYREF
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
LABEL_30:
    v23 = -ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module", v18);
    v10 = v23 == 0 ? 0x8007000E : 0;
    if ( !v23 )
      goto LABEL_32;
    v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module_Raw", Src);
    v10 = v24 == 0 ? 0x8007000E : 0;
    if ( !v24 )
      goto LABEL_32;
    Error = ATL::CRegObject::RegisterFromResource(
              (ATL::CRegObject *)&v26,
              Filename,
              (const unsigned __int16 *)a2,
              L"REGISTRY",
              a3 != 0);
    goto LABEL_10;
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
    goto LABEL_30;
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
0x180017500  mov     [rsp-8+arg_10], rbx
0x180017505  push    rbp
0x180017506  push    rsi
0x180017507  push    rdi
0x180017508  push    r14
0x18001750a  push    r15
0x18001750c  lea     rbp, [rsp-9B0h]
0x180017514  sub     rsp, 0AB0h
0x18001751b  mov     rax, cs:__security_cookie
0x180017522  xor     rax, rsp
0x180017525  mov     [rbp+9D0h+var_30], rax
0x18001752c  mov     rbx, r9
0x18001752f  mov     esi, r8d
0x180017532  mov     r14d, edx
0x180017535  mov     rdi, rcx
0x180017538  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001753f  mov     [rsp+0AD0h+var_AA0], rax
0x180017544  xorps   xmm0, xmm0
0x180017547  movdqu  [rsp+0AD0h+var_A98], xmm0
0x18001754d  xor     r15d, r15d
0x180017550  mov     [rsp+0AD0h+var_A88], r15d
0x180017555  test    r9, r9
0x180017558  jz      short loc_180017581
0x18001755a  mov     rax, [r9]
0x18001755d  jmp     short loc_18001757C
0x18001755f  mov     r8, [rbx+8]; unsigned __int16 *
0x180017563  test    r8, r8
0x180017566  jz      short loc_180017575
0x180017568  mov     rdx, rax; unsigned __int16 *
0x18001756b  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180017570  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180017575  add     rbx, 10h
0x180017579  mov     rax, [rbx]
0x18001757c  test    rax, rax
0x18001757f  jnz     short loc_18001755F
0x180017581  mov     rax, [rdi]
0x180017584  lea     rdx, [rsp+0AD0h+var_AA0]
0x180017589  mov     rcx, rdi
0x18001758c  mov     rax, [rax+28h]
0x180017590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017595  mov     ebx, eax
0x180017597  test    eax, eax
0x180017599  js      loc_180017713
0x18001759f  mov     rbx, cs:hInst
0x1800175a6  mov     edi, 104h
0x1800175ab  mov     r8d, edi; nSize
0x1800175ae  lea     rdx, [rbp+9D0h+Filename]; lpFilename
0x1800175b5  mov     rcx, rbx; hModule
0x1800175b8  call    cs:__imp_GetModuleFileNameW
0x1800175be  test    eax, eax
0x1800175c0  jnz     short loc_1800175CE
0x1800175c2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800175c7  mov     ebx, eax
0x1800175c9  jmp     loc_180017713
0x1800175ce  cmp     eax, edi
0x1800175d0  jnz     short loc_1800175DC
0x1800175d2  mov     ebx, 8007007Ah
0x1800175d7  jmp     loc_180017713
0x1800175dc  lea     rdx, [rbp+9D0h+Filename]
0x1800175e3  mov     ecx, r15d
0x1800175e6  mov     r9d, 27h ; '''
0x1800175ec  movzx   r8d, word ptr [rdx]
0x1800175f0  test    r8w, r8w
0x1800175f4  jz      short loc_180017620
0x1800175f6  mov     [rsp+rcx*2+0AD0h+Src], r8w
0x1800175fc  cmp     r8w, r9w
0x180017600  jnz     short loc_180017612
0x180017602  cmp     ecx, 206h
0x180017608  jnb     short loc_180017612
0x18001760a  inc     ecx
0x18001760c  mov     [rsp+rcx*2+0AD0h+Src], r9w
0x180017612  add     rdx, 2
0x180017616  inc     ecx
0x180017618  cmp     ecx, 207h
0x18001761e  jb      short loc_1800175EC
0x180017620  mov     [rsp+rcx*2+0AD0h+Src], r15w
0x180017626  test    rbx, rbx
0x180017629  jz      short loc_180017642
0x18001762b  xor     ecx, ecx; lpModuleName
0x18001762d  call    cs:__imp_GetModuleHandleW
0x180017633  cmp     rbx, rax
0x180017636  jz      short loc_180017642
0x180017638  lea     r8, [rsp+0AD0h+Src]
0x18001763d  jmp     loc_1800176CD
0x180017642  mov     edi, 22h ; '"'
0x180017647  mov     [rbp+9D0h+var_450], di
0x18001764e  lea     rcx, [rsp+0AD0h+Src]
0x180017653  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017657  mov     rax, rbx
0x18001765a  inc     rax
0x18001765d  cmp     [rcx+rax*2], r15w
0x180017662  jnz     short loc_18001765A
0x180017664  inc     eax
0x180017666  movsxd  r8, eax
0x180017669  add     r8, r8; Size
0x18001766c  jz      short loc_18001768C
0x18001766e  cmp     r8, 414h
0x180017675  ja      loc_180017745
0x18001767b  lea     rdx, [rsp+0AD0h+Src]; Src
0x180017680  lea     rcx, [rbp+9D0h+var_44E]; void *
0x180017687  call    memcpy_0
0x18001768c  lea     rax, [rbp+9D0h+var_450]
0x180017693  inc     rbx
0x180017696  cmp     [rax+rbx*2], r15w
0x18001769b  jnz     short loc_180017693
0x18001769d  movsxd  rax, ebx
0x1800176a0  mov     [rbp+rax*2+9D0h+var_450], di
0x1800176a8  lea     rcx, ds:2[rax*2]
0x1800176b0  cmp     rcx, 418h
0x1800176b7  jnb     loc_180017790
0x1800176bd  mov     [rbp+rcx+9D0h+var_450], r15w
0x1800176c6  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x1800176cd  lea     rdx, aModule; "Module"
0x1800176d4  lea     rcx, [rsp+0AD0h+var_A98]; this
0x1800176d9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800176de  neg     eax
0x1800176e0  sbb     ebx, ebx
0x1800176e2  mov     edi, 8007000Eh
0x1800176e7  not     ebx
0x1800176e9  and     ebx, edi
0x1800176eb  test    ebx, ebx
0x1800176ed  js      short loc_180017713
0x1800176ef  lea     r8, [rsp+0AD0h+Src]; unsigned __int16 *
0x1800176f4  lea     rdx, aModuleRaw; "Module_Raw"
0x1800176fb  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180017700  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180017705  mov     ecx, eax
0x180017707  neg     ecx
0x180017709  sbb     ebx, ebx
0x18001770b  not     ebx
0x18001770d  and     ebx, edi
0x18001770f  test    eax, eax
0x180017711  jnz     short loc_180017763
0x180017713  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180017718  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001771d  mov     eax, ebx
0x18001771f  mov     rcx, [rbp+9D0h+var_30]
0x180017726  xor     rcx, rsp; StackCookie
0x180017729  call    __security_check_cookie
0x18001772e  mov     rbx, [rsp+0AD0h+arg_10]
0x180017736  add     rsp, 0AB0h
0x18001773d  pop     r15
0x18001773f  pop     r14
0x180017741  pop     rdi
0x180017742  pop     rsi
0x180017743  pop     rbp
0x180017744  retn
0x180017745  call    cs:__imp__o__errno
0x18001774b  mov     [rax], edi
0x18001774d  call    _invalid_parameter_noinfo
0x180017752  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180017757  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001775c  mov     eax, 80004005h
0x180017761  jmp     short loc_18001771F
0x180017763  mov     eax, r15d
0x180017766  test    esi, esi
0x180017768  setnz   al
0x18001776b  movzx   r8d, r14w; unsigned __int16 *
0x18001776f  mov     [rsp+0AD0h+var_AB0], eax; int
0x180017773  lea     r9, aRegistry; "REGISTRY"
0x18001777a  lea     rdx, [rbp+9D0h+Filename]; unsigned __int16 *
0x180017781  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180017786  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001778b  jmp     loc_1800175C7
0x180017790  call    __report_rangecheckfailure
```
