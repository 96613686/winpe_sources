# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800065d0`
- end: `0x18000687b`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `683`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800068a0`

## callees

- `0x1800021b8`
- `0x180002c18`
- `0x180002e98`
- `0x180003a98`
- `0x180005588`
- `0x1800065d0`
- `0x18000a9d0`
- `0x18000c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006758`
- `msvcrt!memcpy_s` at `0x180006758`
- `KERNEL32!GetModuleHandleW` at `0x180006702`
- `KERNEL32!GetModuleHandleW` at `0x180006702`
- `KERNEL32!GetModuleFileNameW` at `0x180006686`
- `KERNEL32!GetModuleFileNameW` at `0x180006686`

## string_xrefs

- `0x18000681b`: `REGISTRY`

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
  int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  void **v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+48h] [rbp-B8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Source[520]; // [rsp+270h] [rbp+170h] BYREF
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
    goto LABEL_30;
  v11 = hInstance;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v10 = Error;
LABEL_30:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
    return (unsigned int)v10;
  }
  if ( ModuleFileNameW == 260 )
  {
    v10 = -2147024774;
    goto LABEL_30;
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
    goto LABEL_28;
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
LABEL_28:
    v21 = -ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module", v17);
    v10 = v21 == 0 ? 0x8007000E : 0;
    if ( !v21 )
      goto LABEL_30;
    v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module_Raw", Source);
    v10 = v22 == 0 ? 0x8007000E : 0;
    if ( !v22 )
      goto LABEL_30;
    if ( a3 )
    {
      if ( a2 )
      {
        Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v24, Filename, a2, L"REGISTRY", 1);
        goto LABEL_10;
      }
    }
    else if ( a2 )
    {
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v24, Filename, a2, L"REGISTRY", 0);
      goto LABEL_10;
    }
    v10 = -2147024809;
    goto LABEL_30;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800065d0  mov     [rsp-8+arg_10], rbx
0x1800065d5  push    rbp
0x1800065d6  push    rsi
0x1800065d7  push    rdi
0x1800065d8  push    r14
0x1800065da  push    r15
0x1800065dc  lea     rbp, [rsp-9B0h]
0x1800065e4  sub     rsp, 0AB0h
0x1800065eb  mov     rax, cs:__security_cookie
0x1800065f2  xor     rax, rsp
0x1800065f5  mov     [rbp+9D0h+var_30], rax
0x1800065fc  mov     rbx, r9
0x1800065ff  mov     r14d, r8d
0x180006602  mov     rsi, rdx
0x180006605  mov     rdi, rcx
0x180006608  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000660f  mov     [rsp+0AD0h+var_AA0], rax
0x180006614  xorps   xmm0, xmm0
0x180006617  movdqu  [rsp+0AD0h+var_A98], xmm0
0x18000661d  xor     r15d, r15d
0x180006620  mov     [rsp+0AD0h+var_A88], r15d
0x180006625  test    r9, r9
0x180006628  jz      short loc_180006651
0x18000662a  mov     rax, [r9]
0x18000662d  jmp     short loc_18000664C
0x18000662f  mov     r8, [rbx+8]; unsigned __int16 *
0x180006633  test    r8, r8
0x180006636  jz      short loc_180006645
0x180006638  mov     rdx, rax; unsigned __int16 *
0x18000663b  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180006640  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006645  add     rbx, 10h
0x180006649  mov     rax, [rbx]
0x18000664c  test    rax, rax
0x18000664f  jnz     short loc_18000662F
0x180006651  mov     rax, [rdi]
0x180006654  lea     rdx, [rsp+0AD0h+var_AA0]
0x180006659  mov     rcx, rdi
0x18000665c  mov     rax, [rax+28h]
0x180006660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006665  mov     ebx, eax
0x180006667  test    eax, eax
0x180006669  js      loc_1800067EF
0x18000666f  mov     rbx, cs:hInstance
0x180006676  mov     edi, 104h
0x18000667b  mov     r8d, edi; nSize
0x18000667e  lea     rdx, [rsp+0AD0h+Filename]; lpFilename
0x180006683  mov     rcx, rbx; hModule
0x180006686  call    cs:__imp_GetModuleFileNameW
0x18000668c  test    eax, eax
0x18000668e  jnz     short loc_18000669C
0x180006690  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006695  mov     ebx, eax
0x180006697  jmp     loc_1800067EF
0x18000669c  cmp     eax, edi
0x18000669e  jnz     short loc_1800066AA
0x1800066a0  mov     ebx, 8007007Ah
0x1800066a5  jmp     loc_1800067EF
0x1800066aa  lea     rdx, [rsp+0AD0h+Filename]
0x1800066af  mov     ecx, r15d
0x1800066b2  mov     r9d, 27h ; '''
0x1800066b8  movzx   r8d, word ptr [rdx]
0x1800066bc  test    r8w, r8w
0x1800066c0  jz      short loc_1800066F2
0x1800066c2  mov     [rbp+rcx*2+9D0h+Source], r8w
0x1800066cb  cmp     r8w, r9w
0x1800066cf  jnz     short loc_1800066E4
0x1800066d1  cmp     ecx, 206h
0x1800066d7  jnb     short loc_1800066E4
0x1800066d9  inc     ecx
0x1800066db  mov     [rbp+rcx*2+9D0h+Source], r9w
0x1800066e4  add     rdx, 2
0x1800066e8  inc     ecx
0x1800066ea  cmp     ecx, 207h
0x1800066f0  jb      short loc_1800066B8
0x1800066f2  mov     [rbp+rcx*2+9D0h+Source], r15w
0x1800066fb  test    rbx, rbx
0x1800066fe  jz      short loc_180006719
0x180006700  xor     ecx, ecx; lpModuleName
0x180006702  call    cs:__imp_GetModuleHandleW
0x180006708  cmp     rbx, rax
0x18000670b  jz      short loc_180006719
0x18000670d  lea     r8, [rbp+9D0h+Source]
0x180006714  jmp     loc_1800067A7
0x180006719  mov     edi, 22h ; '"'
0x18000671e  mov     [rbp+9D0h+var_450], di
0x180006725  lea     rcx, [rbp+9D0h+Source]
0x18000672c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006730  mov     rax, rbx
0x180006733  inc     rax
0x180006736  cmp     [rcx+rax*2], r15w
0x18000673b  jnz     short loc_180006733
0x18000673d  inc     eax
0x18000673f  movsxd  r9, eax
0x180006742  add     r9, r9; SourceSize
0x180006745  lea     r8, [rbp+9D0h+Source]; Source
0x18000674c  mov     edx, 414h; DestinationSize
0x180006751  lea     rcx, [rbp+9D0h+Destination]; Destination
0x180006758  call    cs:__imp_memcpy_s
0x18000675e  test    eax, eax
0x180006760  jnz     loc_180006840
0x180006766  lea     rax, [rbp+9D0h+var_450]
0x18000676d  inc     rbx
0x180006770  cmp     [rax+rbx*2], r15w
0x180006775  jnz     short loc_18000676D
0x180006777  movsxd  rax, ebx
0x18000677a  mov     [rbp+rax*2+9D0h+var_450], di
0x180006782  lea     rcx, ds:2[rax*2]
0x18000678a  cmp     rcx, 418h
0x180006791  jnb     loc_180006875
0x180006797  mov     [rbp+rcx+9D0h+var_450], r15w
0x1800067a0  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x1800067a7  lea     rdx, aModule; "Module"
0x1800067ae  lea     rcx, [rsp+0AD0h+var_A98]; this
0x1800067b3  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800067b8  neg     eax
0x1800067ba  sbb     ebx, ebx
0x1800067bc  mov     edi, 8007000Eh
0x1800067c1  not     ebx
0x1800067c3  and     ebx, edi
0x1800067c5  test    ebx, ebx
0x1800067c7  js      short loc_1800067EF
0x1800067c9  lea     r8, [rbp+9D0h+Source]; unsigned __int16 *
0x1800067d0  lea     rdx, aModuleRaw; "Module_Raw"
0x1800067d7  lea     rcx, [rsp+0AD0h+var_A98]; this
0x1800067dc  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800067e1  mov     ecx, eax
0x1800067e3  neg     ecx
0x1800067e5  sbb     ebx, ebx
0x1800067e7  not     ebx
0x1800067e9  and     ebx, edi
0x1800067eb  test    eax, eax
0x1800067ed  jnz     short loc_1800067FD
0x1800067ef  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x1800067f4  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800067f9  mov     eax, ebx
0x1800067fb  jmp     short loc_18000684F
0x1800067fd  test    r14d, r14d
0x180006800  jz      short loc_180006811
0x180006802  test    rsi, rsi
0x180006805  jz      short loc_180006839
0x180006807  mov     [rsp+0AD0h+var_AB0], 1
0x18000680f  jmp     short loc_18000681B
0x180006811  test    rsi, rsi
0x180006814  jz      short loc_180006839
0x180006816  mov     [rsp+0AD0h+var_AB0], r15d; int
0x18000681b  lea     r9, aRegistry; "REGISTRY"
0x180006822  mov     r8, rsi; unsigned __int16 *
0x180006825  lea     rdx, [rsp+0AD0h+Filename]; unsigned __int16 *
0x18000682a  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x18000682f  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180006834  jmp     loc_180006695
0x180006839  mov     ebx, 80070057h
0x18000683e  jmp     short loc_1800067EF
0x180006840  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180006845  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000684a  mov     eax, 80004005h
0x18000684f  mov     rcx, [rbp+9D0h+var_30]
0x180006856  xor     rcx, rsp; StackCookie
0x180006859  call    __security_check_cookie
0x18000685e  mov     rbx, [rsp+0AD0h+arg_10]
0x180006866  add     rsp, 0AB0h
0x18000686d  pop     r15
0x18000686f  pop     r14
0x180006871  pop     rdi
0x180006872  pop     rsi
0x180006873  pop     rbp
0x180006874  retn
0x180006875  call    __report_rangecheckfailure
```
