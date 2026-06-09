# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800091d4`
- end: `0x180009458`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `644`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, __int64, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180009160`
- `0x180009180`
- `0x1800091a0`
- `0x1800091c0`
- `0x18000b2d0`

## callees

- `0x180004710`
- `0x1800065fc`
- `0x180006750`
- `0x1800072b8`
- `0x180007b04`
- `0x180007ed0`
- `0x1800091d4`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000933d`
- `msvcrt!memcpy_s` at `0x18000933d`
- `KERNEL32!GetModuleFileNameW` at `0x18000925e`
- `KERNEL32!GetModuleFileNameW` at `0x18000925e`
- `KERNEL32!GetModuleHandleW` at `0x1800092e5`
- `KERNEL32!GetModuleHandleW` at `0x1800092e5`

## string_xrefs

- `0x1800093e3`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        __int64 a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v4; // edi
  int Error; // ebx
  HMODULE v7; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v9; // rdx
  __int64 v10; // rcx
  unsigned __int16 v11; // r8
  unsigned __int16 *v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  int v17; // eax
  _QWORD *v18; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-C8h] BYREF
  void **v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 Source[520]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v25; // [rsp+690h] [rbp+590h] BYREF
  _BYTE Destination[1054]; // [rsp+692h] [rbp+592h] BYREF

  v4 = a3;
  v20 = &ATL::CRegObject::`vftable';
  v21 = 0;
  v22 = 0;
  Error = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***, __int64, struct ATL::_ATL_REGMAP_ENTRY *))(*(_QWORD *)ATL::_pAtlModule + 40LL))(
            ATL::_pAtlModule,
            &v20,
            a3,
            a4);
  if ( Error < 0 )
    goto LABEL_24;
  v18 = 0;
  v7 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_23:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
    goto LABEL_24;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
    Error = -2147024774;
LABEL_24:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v20);
    return (unsigned int)Error;
  }
  v9 = Filename;
  v10 = 0;
  do
  {
    v11 = *v9;
    if ( !*v9 )
      break;
    Source[v10] = v11;
    if ( v11 == 39 && (unsigned int)v10 < 0x206 )
    {
      LODWORD(v10) = v10 + 1;
      Source[(unsigned int)v10] = 39;
    }
    ++v9;
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (unsigned int)v10 < 0x207 );
  Source[v10] = 0;
  if ( v7 && v7 != GetModuleHandleW(0) )
  {
    v12 = Source;
LABEL_21:
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v20, L"Module", v12);
    if ( Error >= 0 )
    {
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v20, L"Module_Raw", Source);
      if ( Error >= 0 )
      {
        v19 = 0;
        if ( v4 )
          v17 = ATL::CRegObject::RegisterFromResource(
                  (const WCHAR *)&v20,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  1);
        else
          v17 = ATL::CRegObject::RegisterFromResource(
                  (const WCHAR *)&v20,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  0);
        Error = v17;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      }
    }
    goto LABEL_23;
  }
  v25 = 34;
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( Source[v14] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v14 + 1)) )
  {
    do
      ++v13;
    while ( *(_WORD *)&Destination[2 * v13 - 2] );
    *(_WORD *)&Destination[2 * (int)v13 - 2] = 34;
    v15 = 2LL * (int)v13 + 2;
    if ( v15 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v15 - 2] = 0;
    v12 = &v25;
    goto LABEL_21;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v18);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v20);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800091d4  push    rbp
0x1800091d6  push    rbx
0x1800091d7  push    rsi
0x1800091d8  push    rdi
0x1800091d9  push    r14
0x1800091db  push    r15
0x1800091dd  lea     rbp, [rsp-9C8h]
0x1800091e5  sub     rsp, 0AC8h
0x1800091ec  mov     rax, cs:__security_cookie
0x1800091f3  xor     rax, rsp
0x1800091f6  mov     [rbp+9F0h+var_40], rax
0x1800091fd  mov     edi, r8d
0x180009200  mov     esi, edx
0x180009202  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009209  mov     [rsp+0AF0h+var_AB0], rax
0x18000920e  xorps   xmm0, xmm0
0x180009211  movdqu  [rsp+0AF0h+var_AA8], xmm0
0x180009217  xor     r14d, r14d
0x18000921a  mov     [rsp+0AF0h+var_A98], r14d
0x18000921f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009226  mov     rax, [rcx]
0x180009229  lea     rdx, [rsp+0AF0h+var_AB0]
0x18000922e  mov     rax, [rax+28h]
0x180009232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009237  mov     ebx, eax
0x180009239  test    eax, eax
0x18000923b  js      loc_1800093CC
0x180009241  mov     [rsp+0AF0h+var_AC0], r14
0x180009246  mov     rbx, cs:hModule
0x18000924d  mov     r15d, 104h
0x180009253  mov     r8d, r15d; nSize
0x180009256  lea     rdx, [rsp+0AF0h+Filename]; lpFilename
0x18000925b  mov     rcx, rbx; hModule
0x18000925e  call    cs:__imp_GetModuleFileNameW
0x180009264  test    eax, eax
0x180009266  jnz     short loc_180009274
0x180009268  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000926d  mov     ebx, eax
0x18000926f  jmp     loc_1800093C2
0x180009274  cmp     eax, r15d
0x180009277  jnz     short loc_18000928D
0x180009279  lea     rcx, [rsp+0AF0h+var_AC0]
0x18000927e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009283  mov     ebx, 8007007Ah
0x180009288  jmp     loc_1800093CC
0x18000928d  lea     rdx, [rsp+0AF0h+Filename]
0x180009292  mov     ecx, r14d
0x180009295  mov     r9d, 27h ; '''
0x18000929b  movzx   r8d, word ptr [rdx]
0x18000929f  test    r8w, r8w
0x1800092a3  jz      short loc_1800092D5
0x1800092a5  mov     [rbp+rcx*2+9F0h+Source], r8w
0x1800092ae  cmp     r8w, r9w
0x1800092b2  jnz     short loc_1800092C7
0x1800092b4  cmp     ecx, 206h
0x1800092ba  jnb     short loc_1800092C7
0x1800092bc  inc     ecx
0x1800092be  mov     [rbp+rcx*2+9F0h+Source], r9w
0x1800092c7  add     rdx, 2
0x1800092cb  inc     ecx
0x1800092cd  cmp     ecx, 207h
0x1800092d3  jb      short loc_18000929B
0x1800092d5  mov     [rbp+rcx*2+9F0h+Source], r14w
0x1800092de  test    rbx, rbx
0x1800092e1  jz      short loc_1800092FC
0x1800092e3  xor     ecx, ecx; lpModuleName
0x1800092e5  call    cs:__imp_GetModuleHandleW
0x1800092eb  cmp     rbx, rax
0x1800092ee  jz      short loc_1800092FC
0x1800092f0  lea     r8, [rbp+9F0h+Source]
0x1800092f7  jmp     loc_18000938D
0x1800092fc  mov     r15d, 22h ; '"'
0x180009302  mov     [rbp+9F0h+var_460], r15w
0x18000930a  lea     rcx, [rbp+9F0h+Source]
0x180009311  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009315  mov     rax, rbx
0x180009318  inc     rax
0x18000931b  cmp     [rcx+rax*2], r14w
0x180009320  jnz     short loc_180009318
0x180009322  inc     eax
0x180009324  movsxd  r9, eax
0x180009327  add     r9, r9; SourceSize
0x18000932a  lea     r8, [rbp+9F0h+Source]; Source
0x180009331  mov     edx, 414h; DestinationSize
0x180009336  lea     rcx, [rbp+9F0h+Destination]; Destination
0x18000933d  call    cs:__imp_memcpy_s
0x180009343  test    eax, eax
0x180009345  jnz     loc_180009420
0x18000934b  lea     rax, [rbp+9F0h+var_460]
0x180009352  inc     rbx
0x180009355  cmp     [rax+rbx*2], r14w
0x18000935a  jnz     short loc_180009352
0x18000935c  movsxd  rax, ebx
0x18000935f  mov     [rbp+rax*2+9F0h+var_460], r15w
0x180009368  lea     rcx, ds:2[rax*2]
0x180009370  cmp     rcx, 418h
0x180009377  jnb     loc_18000941A
0x18000937d  mov     [rbp+rcx+9F0h+var_460], r14w
0x180009386  lea     r8, [rbp+9F0h+var_460]; unsigned __int16 *
0x18000938d  lea     rdx, aModule; "Module"
0x180009394  lea     rcx, [rsp+0AF0h+var_AB0]; this
0x180009399  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000939e  mov     ebx, eax
0x1800093a0  test    eax, eax
0x1800093a2  js      short loc_1800093C2
0x1800093a4  lea     r8, [rbp+9F0h+Source]; unsigned __int16 *
0x1800093ab  lea     rdx, aModuleRaw; "Module_Raw"
0x1800093b2  lea     rcx, [rsp+0AF0h+var_AB0]; this
0x1800093b7  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800093bc  mov     ebx, eax
0x1800093be  test    eax, eax
0x1800093c0  jns     short loc_1800093DA
0x1800093c2  lea     rcx, [rsp+0AF0h+var_AC0]
0x1800093c7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800093cc  lea     rcx, [rsp+0AF0h+var_AB0]; this
0x1800093d1  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800093d6  mov     eax, ebx
0x1800093d8  jmp     short loc_180009439
0x1800093da  movzx   r8d, si; unsigned __int16 *
0x1800093de  mov     [rsp+0AF0h+var_AB8], r14
0x1800093e3  lea     r9, aRegistry; "REGISTRY"
0x1800093ea  lea     rdx, [rsp+0AF0h+Filename]; unsigned __int16 *
0x1800093ef  lea     rcx, [rsp+0AF0h+var_AB0]; this
0x1800093f4  test    edi, edi
0x1800093f6  jz      short loc_180009402
0x1800093f8  mov     [rsp+0AF0h+var_AD0], 1
0x180009400  jmp     short loc_180009407
0x180009402  mov     [rsp+0AF0h+var_AD0], r14d; int
0x180009407  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000940c  mov     ebx, eax
0x18000940e  lea     rcx, [rsp+0AF0h+var_AB8]
0x180009413  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009418  jmp     short loc_1800093C2
0x18000941a  call    __report_rangecheckfailure
0x180009420  lea     rcx, [rsp+0AF0h+var_AC0]
0x180009425  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000942a  lea     rcx, [rsp+0AF0h+var_AB0]; this
0x18000942f  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009434  mov     eax, 80004005h
0x180009439  mov     rcx, [rbp+9F0h+var_40]
0x180009440  xor     rcx, rsp; StackCookie
0x180009443  call    __security_check_cookie
0x180009448  add     rsp, 0AC8h
0x18000944f  pop     r15
0x180009451  pop     r14
0x180009453  pop     rdi
0x180009454  pop     rsi
0x180009455  pop     rbx
0x180009456  pop     rbp
0x180009457  retn
```
