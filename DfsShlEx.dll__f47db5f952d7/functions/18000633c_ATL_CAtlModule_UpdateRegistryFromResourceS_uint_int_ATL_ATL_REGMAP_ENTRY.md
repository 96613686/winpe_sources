# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000633c`
- end: `0x1800065c8`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `652`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180006310`
- `0x180006890`

## callees

- `0x1800021b8`
- `0x180002c18`
- `0x180002e98`
- `0x180003a98`
- `0x180005588`
- `0x18000633c`
- `0x18000a9d0`
- `0x18000c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800064b9`
- `msvcrt!memcpy_s` at `0x1800064b9`
- `KERNEL32!GetModuleHandleW` at `0x180006469`
- `KERNEL32!GetModuleHandleW` at `0x180006469`
- `KERNEL32!GetModuleFileNameW` at `0x1800063f4`
- `KERNEL32!GetModuleFileNameW` at `0x1800063f4`

## string_xrefs

- `0x180006570`: `REGISTRY`

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
  int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v22; // eax
  void **v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+48h] [rbp-B8h]
  unsigned __int16 Source[520]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v29; // [rsp+680h] [rbp+580h] BYREF
  _BYTE Destination[1054]; // [rsp+682h] [rbp+582h] BYREF

  v4 = a4;
  v24 = &ATL::CRegObject::`vftable';
  v25 = 0;
  v26 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      v9 = v4[1];
      if ( v9 )
        ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, i, v9);
      v4 += 2;
    }
  }
  v10 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v24);
  if ( v10 < 0 )
    goto LABEL_31;
  v11 = hInstance;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v10 = Error;
LABEL_31:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
    return (unsigned int)v10;
  }
  if ( ModuleFileNameW == 260 )
  {
    v10 = -2147024774;
    goto LABEL_31;
  }
  v14 = Filename;
  v15 = 0;
  do
  {
    v16 = *v14;
    if ( !*v14 )
      break;
    Source[v15] = v16;
    if ( v16 == 39 && (unsigned int)v15 < 0x206 )
    {
      LODWORD(v15) = v15 + 1;
      Source[(unsigned int)v15] = 39;
    }
    ++v14;
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < 0x207 );
  Source[v15] = 0;
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v17 = Source;
LABEL_28:
    if ( !-ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module", v17) )
    {
      v10 = -2147024882;
      goto LABEL_31;
    }
    v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module_Raw", Source);
    v10 = v22 == 0 ? 0x8007000E : 0;
    if ( !v22 )
      goto LABEL_31;
    Error = ATL::CRegObject::RegisterFromResource(
              (ATL::CRegObject *)&v24,
              Filename,
              (const unsigned __int16 *)a2,
              L"REGISTRY",
              a3 != 0);
    goto LABEL_10;
  }
  v29 = 34;
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( Source[v19] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v19 + 1)) )
  {
    do
      ++v18;
    while ( *(_WORD *)&Destination[2 * v18 - 2] );
    *(_WORD *)&Destination[2 * (int)v18 - 2] = 34;
    v20 = 2LL * (int)v18 + 2;
    if ( v20 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v20 - 2] = 0;
    v17 = &v29;
    goto LABEL_28;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000633c  mov     [rsp-8+arg_10], rbx
0x180006341  push    rbp
0x180006342  push    rsi
0x180006343  push    rdi
0x180006344  push    r14
0x180006346  push    r15
0x180006348  lea     rbp, [rsp-9B0h]
0x180006350  sub     rsp, 0AB0h
0x180006357  mov     rax, cs:__security_cookie
0x18000635e  xor     rax, rsp
0x180006361  mov     [rbp+9D0h+var_30], rax
0x180006368  mov     rbx, r9
0x18000636b  mov     esi, r8d
0x18000636e  mov     r14d, edx
0x180006371  mov     rdi, rcx
0x180006374  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000637b  mov     [rsp+0AD0h+var_AA0], rax
0x180006380  xorps   xmm0, xmm0
0x180006383  movdqu  [rsp+0AD0h+var_A98], xmm0
0x180006389  xor     r15d, r15d
0x18000638c  mov     [rsp+0AD0h+var_A88], r15d
0x180006391  test    r9, r9
0x180006394  jz      short loc_1800063BD
0x180006396  mov     rax, [r9]
0x180006399  jmp     short loc_1800063B8
0x18000639b  mov     r8, [rbx+8]; unsigned __int16 *
0x18000639f  test    r8, r8
0x1800063a2  jz      short loc_1800063B1
0x1800063a4  mov     rdx, rax; unsigned __int16 *
0x1800063a7  lea     rcx, [rsp+0AD0h+var_A98]; this
0x1800063ac  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800063b1  add     rbx, 10h
0x1800063b5  mov     rax, [rbx]
0x1800063b8  test    rax, rax
0x1800063bb  jnz     short loc_18000639B
0x1800063bd  mov     rax, [rdi]
0x1800063c0  lea     rdx, [rsp+0AD0h+var_AA0]
0x1800063c5  mov     rcx, rdi
0x1800063c8  mov     rax, [rax+28h]
0x1800063cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d1  mov     ebx, eax
0x1800063d3  test    eax, eax
0x1800063d5  js      loc_180006552
0x1800063db  mov     rbx, cs:hInstance
0x1800063e2  mov     edi, 104h
0x1800063e7  mov     r8d, edi; nSize
0x1800063ea  lea     rdx, [rbp+9D0h+Filename]; lpFilename
0x1800063f1  mov     rcx, rbx; hModule
0x1800063f4  call    cs:__imp_GetModuleFileNameW
0x1800063fa  test    eax, eax
0x1800063fc  jnz     short loc_18000640A
0x1800063fe  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006403  mov     ebx, eax
0x180006405  jmp     loc_180006552
0x18000640a  cmp     eax, edi
0x18000640c  jnz     short loc_180006418
0x18000640e  mov     ebx, 8007007Ah
0x180006413  jmp     loc_180006552
0x180006418  lea     rdx, [rbp+9D0h+Filename]
0x18000641f  mov     ecx, r15d
0x180006422  mov     r9d, 27h ; '''
0x180006428  movzx   r8d, word ptr [rdx]
0x18000642c  test    r8w, r8w
0x180006430  jz      short loc_18000645C
0x180006432  mov     [rsp+rcx*2+0AD0h+Source], r8w
0x180006438  cmp     r8w, r9w
0x18000643c  jnz     short loc_18000644E
0x18000643e  cmp     ecx, 206h
0x180006444  jnb     short loc_18000644E
0x180006446  inc     ecx
0x180006448  mov     [rsp+rcx*2+0AD0h+Source], r9w
0x18000644e  add     rdx, 2
0x180006452  inc     ecx
0x180006454  cmp     ecx, 207h
0x18000645a  jb      short loc_180006428
0x18000645c  mov     [rsp+rcx*2+0AD0h+Source], r15w
0x180006462  test    rbx, rbx
0x180006465  jz      short loc_18000647E
0x180006467  xor     ecx, ecx; lpModuleName
0x180006469  call    cs:__imp_GetModuleHandleW
0x18000646f  cmp     rbx, rax
0x180006472  jz      short loc_18000647E
0x180006474  lea     r8, [rsp+0AD0h+Source]
0x180006479  jmp     loc_180006508
0x18000647e  mov     edi, 22h ; '"'
0x180006483  mov     [rbp+9D0h+var_450], di
0x18000648a  lea     rcx, [rsp+0AD0h+Source]
0x18000648f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006493  mov     rax, rbx
0x180006496  inc     rax
0x180006499  cmp     [rcx+rax*2], r15w
0x18000649e  jnz     short loc_180006496
0x1800064a0  inc     eax
0x1800064a2  movsxd  r9, eax
0x1800064a5  add     r9, r9; SourceSize
0x1800064a8  lea     r8, [rsp+0AD0h+Source]; Source
0x1800064ad  mov     edx, 414h; DestinationSize
0x1800064b2  lea     rcx, [rbp+9D0h+Destination]; Destination
0x1800064b9  call    cs:__imp_memcpy_s
0x1800064bf  test    eax, eax
0x1800064c1  jnz     loc_18000658D
0x1800064c7  lea     rax, [rbp+9D0h+var_450]
0x1800064ce  inc     rbx
0x1800064d1  cmp     [rax+rbx*2], r15w
0x1800064d6  jnz     short loc_1800064CE
0x1800064d8  movsxd  rax, ebx
0x1800064db  mov     [rbp+rax*2+9D0h+var_450], di
0x1800064e3  lea     rcx, ds:2[rax*2]
0x1800064eb  cmp     rcx, 418h
0x1800064f2  jnb     loc_1800065C2
0x1800064f8  mov     [rbp+rcx+9D0h+var_450], r15w
0x180006501  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x180006508  lea     rdx, aModule; "Module"
0x18000650f  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180006514  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006519  neg     eax
0x18000651b  sbb     ecx, ecx
0x18000651d  mov     edi, 8007000Eh
0x180006522  not     ecx
0x180006524  and     ecx, edi
0x180006526  test    ecx, ecx
0x180006528  jns     short loc_18000652E
0x18000652a  mov     ebx, ecx
0x18000652c  jmp     short loc_180006552
0x18000652e  lea     r8, [rsp+0AD0h+Source]; unsigned __int16 *
0x180006533  lea     rdx, aModuleRaw; "Module_Raw"
0x18000653a  lea     rcx, [rsp+0AD0h+var_A98]; this
0x18000653f  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006544  mov     ecx, eax
0x180006546  neg     ecx
0x180006548  sbb     ebx, ebx
0x18000654a  not     ebx
0x18000654c  and     ebx, edi
0x18000654e  test    eax, eax
0x180006550  jnz     short loc_180006560
0x180006552  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180006557  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000655c  mov     eax, ebx
0x18000655e  jmp     short loc_18000659C
0x180006560  mov     eax, r15d
0x180006563  test    esi, esi
0x180006565  setnz   al
0x180006568  movzx   r8d, r14w; unsigned __int16 *
0x18000656c  mov     [rsp+0AD0h+var_AB0], eax; int
0x180006570  lea     r9, aRegistry; "REGISTRY"
0x180006577  lea     rdx, [rbp+9D0h+Filename]; unsigned __int16 *
0x18000657e  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180006583  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180006588  jmp     loc_180006403
0x18000658d  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180006592  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006597  mov     eax, 80004005h
0x18000659c  mov     rcx, [rbp+9D0h+var_30]
0x1800065a3  xor     rcx, rsp; StackCookie
0x1800065a6  call    __security_check_cookie
0x1800065ab  mov     rbx, [rsp+0AD0h+arg_10]
0x1800065b3  add     rsp, 0AB0h
0x1800065ba  pop     r15
0x1800065bc  pop     r14
0x1800065be  pop     rdi
0x1800065bf  pop     rsi
0x1800065c0  pop     rbp
0x1800065c1  retn
0x1800065c2  call    __report_rangecheckfailure
```
