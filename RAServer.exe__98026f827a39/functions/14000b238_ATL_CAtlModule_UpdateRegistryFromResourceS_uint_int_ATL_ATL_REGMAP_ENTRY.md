# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14000b238`
- end: `0x14000b52e`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `758`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000b1c0`
- `0x14000b1e0`
- `0x14000b200`
- `0x14000b220`
- `0x14000dc74`

## callees

- `0x140001b48`
- `0x140003340`
- `0x140003a44`
- `0x140004630`
- `0x140004d7c`
- `0x140007304`
- `0x1400095a4`
- `0x14000b238`
- `0x140015aa0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14000b32d`
- `KERNEL32!GetModuleFileNameW` at `0x14000b32d`
- `KERNEL32!GetModuleHandleW` at `0x14000b3b2`
- `KERNEL32!GetModuleHandleW` at `0x14000b3b2`
- `msvcrt!memcpy_s` at `0x14000b408`
- `msvcrt!memcpy_s` at `0x14000b408`

## string_xrefs

- `0x14000b4ad`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v7; // rsi
  int v8; // edi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 v15; // r8
  unsigned __int16 *v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  int v20; // eax
  _QWORD *v21; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  struct _RTL_CRITICAL_SECTION v25; // [rsp+60h] [rbp-A0h] BYREF
  char v26; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 Source[520]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v29; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE Destination[1054]; // [rsp+6B2h] [rbp+5B2h] BYREF

  v7 = ATL::_pAtlModule;
  v23[0] = &ATL::CRegObject::`vftable';
  v23[1] = 0;
  v23[2] = 0;
  v24 = 0;
  memset(&v25, 0, sizeof(v25));
  v26 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init(&v25);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v23,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, _QWORD *))(*(_QWORD *)v7 + 40LL))(v7, v23);
  if ( Error < 0 )
    goto LABEL_30;
  v21 = 0;
  v11 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_29:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    goto LABEL_30;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    Error = -2147024774;
LABEL_30:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
    return (unsigned int)Error;
  }
  v13 = Filename;
  v14 = 0;
  do
  {
    v15 = *v13;
    if ( !*v13 )
      break;
    Source[v14] = v15;
    if ( v15 == 39 && (unsigned int)v14 < 0x206 )
    {
      LODWORD(v14) = v14 + 1;
      Source[(unsigned int)v14] = 39;
    }
    ++v13;
    v14 = (unsigned int)(v14 + 1);
  }
  while ( (unsigned int)v14 < 0x207 );
  Source[v14] = 0;
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v16 = Source;
LABEL_27:
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v23, L"Module", v16);
    if ( Error >= 0 )
    {
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v23, L"Module_Raw", Source);
      if ( Error >= 0 )
      {
        v22 = 0;
        if ( a3 )
          v20 = ATL::CRegObject::RegisterFromResource(
                  (const wchar_t *)v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  1);
        else
          v20 = ATL::CRegObject::RegisterFromResource(
                  (const wchar_t *)v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  0);
        Error = v20;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v22);
      }
    }
    goto LABEL_29;
  }
  v29 = 34;
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( Source[v18] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v18 + 1)) )
  {
    do
      ++v17;
    while ( *(_WORD *)&Destination[2 * v17 - 2] );
    *(_WORD *)&Destination[2 * (int)v17 - 2] = 34;
    v19 = 2LL * (int)v17 + 2;
    if ( v19 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v19 - 2] = 0;
    v16 = &v29;
    goto LABEL_27;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
  return 2147500037LL;
}

```

## disassembly

```asm
0x14000b238  mov     [rsp-8+arg_0], rbx
0x14000b23d  mov     [rsp-8+arg_10], rsi
0x14000b242  push    rbp
0x14000b243  push    rdi
0x14000b244  push    r12
0x14000b246  push    r14
0x14000b248  push    r15
0x14000b24a  lea     rbp, [rsp-9E0h]
0x14000b252  sub     rsp, 0AE0h
0x14000b259  mov     rax, cs:__security_cookie
0x14000b260  xor     rax, rsp
0x14000b263  mov     [rbp+0A00h+var_30], rax
0x14000b26a  mov     rbx, r9
0x14000b26d  mov     r14d, r8d
0x14000b270  mov     r15d, edx
0x14000b273  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000b27a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000b281  mov     [rsp+0B00h+var_AC0], rax
0x14000b286  xor     r12d, r12d
0x14000b289  mov     [rsp+0B00h+var_AB8], r12
0x14000b28e  mov     [rsp+0B00h+var_AB0], r12
0x14000b293  mov     [rsp+0B00h+var_AA8], r12d
0x14000b298  xorps   xmm0, xmm0
0x14000b29b  xor     eax, eax
0x14000b29d  movups  [rsp+0B00h+var_AA0], xmm0
0x14000b2a2  movups  [rsp+0B00h+var_A90], xmm0
0x14000b2a7  mov     [rbp+0A00h+var_A80], rax
0x14000b2ab  mov     [rbp+0A00h+var_A78], r12b
0x14000b2af  lea     rcx, [rsp+0B00h+var_AA0]; this
0x14000b2b4  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x14000b2b9  mov     edi, eax
0x14000b2bb  test    eax, eax
0x14000b2bd  jns     short loc_14000B2D0
0x14000b2bf  lea     rcx, [rsp+0B00h+var_AC0]; this
0x14000b2c4  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000b2c9  mov     eax, edi
0x14000b2cb  jmp     loc_14000B503
0x14000b2d0  test    rbx, rbx
0x14000b2d3  jz      short loc_14000B2F4
0x14000b2d5  jmp     short loc_14000B2EC
0x14000b2d7  mov     r8, [rbx+8]; unsigned __int16 *
0x14000b2db  mov     rdx, rax; unsigned __int16 *
0x14000b2de  lea     rcx, [rsp+0B00h+var_AC0]; this
0x14000b2e3  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x14000b2e8  lea     rbx, [rbx+10h]
0x14000b2ec  mov     rax, [rbx]
0x14000b2ef  test    rax, rax
0x14000b2f2  jnz     short loc_14000B2D7
0x14000b2f4  mov     rax, [rsi]
0x14000b2f7  lea     rdx, [rsp+0B00h+var_AC0]
0x14000b2fc  mov     rcx, rsi
0x14000b2ff  mov     rax, [rax+28h]
0x14000b303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b308  mov     ebx, eax
0x14000b30a  test    eax, eax
0x14000b30c  js      loc_14000B496
0x14000b312  mov     [rsp+0B00h+var_AD0], r12
0x14000b317  mov     rbx, cs:hModule
0x14000b31e  mov     edi, 104h
0x14000b323  mov     r8d, edi; nSize
0x14000b326  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x14000b32a  mov     rcx, rbx; hModule
0x14000b32d  call    cs:__imp_GetModuleFileNameW
0x14000b333  test    eax, eax
0x14000b335  jnz     short loc_14000B343
0x14000b337  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000b33c  mov     ebx, eax
0x14000b33e  jmp     loc_14000B48C
0x14000b343  cmp     eax, edi
0x14000b345  jnz     short loc_14000B35B
0x14000b347  lea     rcx, [rsp+0B00h+var_AD0]
0x14000b34c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000b351  mov     ebx, 8007007Ah
0x14000b356  jmp     loc_14000B496
0x14000b35b  lea     rdx, [rbp+0A00h+Filename]
0x14000b35f  mov     ecx, r12d
0x14000b362  mov     r9d, 27h ; '''
0x14000b368  movzx   r8d, word ptr [rdx]
0x14000b36c  test    r8w, r8w
0x14000b370  jz      short loc_14000B3A2
0x14000b372  mov     [rbp+rcx*2+0A00h+Source], r8w
0x14000b37b  cmp     r8w, r9w
0x14000b37f  jnz     short loc_14000B394
0x14000b381  cmp     ecx, 206h
0x14000b387  jnb     short loc_14000B394
0x14000b389  inc     ecx
0x14000b38b  mov     [rbp+rcx*2+0A00h+Source], r9w
0x14000b394  add     rdx, 2
0x14000b398  inc     ecx
0x14000b39a  cmp     ecx, 207h
0x14000b3a0  jb      short loc_14000B368
0x14000b3a2  mov     [rbp+rcx*2+0A00h+Source], r12w
0x14000b3ab  test    rbx, rbx
0x14000b3ae  jz      short loc_14000B3C9
0x14000b3b0  xor     ecx, ecx; lpModuleName
0x14000b3b2  call    cs:__imp_GetModuleHandleW
0x14000b3b8  cmp     rbx, rax
0x14000b3bb  jz      short loc_14000B3C9
0x14000b3bd  lea     r8, [rbp+0A00h+Source]
0x14000b3c4  jmp     loc_14000B457
0x14000b3c9  mov     edi, 22h ; '"'
0x14000b3ce  mov     [rbp+0A00h+var_450], di
0x14000b3d5  lea     rcx, [rbp+0A00h+Source]
0x14000b3dc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b3e0  mov     rax, rbx
0x14000b3e3  inc     rax
0x14000b3e6  cmp     [rcx+rax*2], r12w
0x14000b3eb  jnz     short loc_14000B3E3
0x14000b3ed  inc     eax
0x14000b3ef  movsxd  r9, eax
0x14000b3f2  add     r9, r9; SourceSize
0x14000b3f5  lea     r8, [rbp+0A00h+Source]; Source
0x14000b3fc  mov     edx, 414h; DestinationSize
0x14000b401  lea     rcx, [rbp+0A00h+Destination]; Destination
0x14000b408  call    cs:__imp_memcpy_s
0x14000b40e  test    eax, eax
0x14000b410  jnz     loc_14000B4EA
0x14000b416  lea     rax, [rbp+0A00h+var_450]
0x14000b41d  inc     rbx
0x14000b420  cmp     [rax+rbx*2], r12w
0x14000b425  jnz     short loc_14000B41D
0x14000b427  movsxd  rax, ebx
0x14000b42a  mov     [rbp+rax*2+0A00h+var_450], di
0x14000b432  lea     rcx, ds:2[rax*2]
0x14000b43a  cmp     rcx, 418h
0x14000b441  jnb     loc_14000B4E4
0x14000b447  mov     [rbp+rcx+0A00h+var_450], r12w
0x14000b450  lea     r8, [rbp+0A00h+var_450]; unsigned __int16 *
0x14000b457  lea     rdx, aModule; "Module"
0x14000b45e  lea     rcx, [rsp+0B00h+var_AC0]; this
0x14000b463  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x14000b468  mov     ebx, eax
0x14000b46a  test    eax, eax
0x14000b46c  js      short loc_14000B48C
0x14000b46e  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x14000b475  lea     rdx, aModuleRaw; "Module_Raw"
0x14000b47c  lea     rcx, [rsp+0B00h+var_AC0]; this
0x14000b481  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x14000b486  mov     ebx, eax
0x14000b488  test    eax, eax
0x14000b48a  jns     short loc_14000B4A4
0x14000b48c  lea     rcx, [rsp+0B00h+var_AD0]
0x14000b491  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000b496  lea     rcx, [rsp+0B00h+var_AC0]; this
0x14000b49b  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000b4a0  mov     eax, ebx
0x14000b4a2  jmp     short loc_14000B503
0x14000b4a4  movzx   r8d, r15w; unsigned __int16 *
0x14000b4a8  mov     [rsp+0B00h+var_AC8], r12
0x14000b4ad  lea     r9, aRegistry; "REGISTRY"
0x14000b4b4  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x14000b4b8  lea     rcx, [rsp+0B00h+var_AC0]; this
0x14000b4bd  test    r14d, r14d
0x14000b4c0  jz      short loc_14000B4CC
0x14000b4c2  mov     [rsp+0B00h+var_AE0], 1
0x14000b4ca  jmp     short loc_14000B4D1
0x14000b4cc  mov     [rsp+0B00h+var_AE0], r12d; int
0x14000b4d1  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x14000b4d6  mov     ebx, eax
0x14000b4d8  lea     rcx, [rsp+0B00h+var_AC8]
0x14000b4dd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000b4e2  jmp     short loc_14000B48C
0x14000b4e4  call    __report_rangecheckfailure
0x14000b4ea  lea     rcx, [rsp+0B00h+var_AD0]
0x14000b4ef  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x14000b4f4  lea     rcx, [rsp+0B00h+var_AC0]; this
0x14000b4f9  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000b4fe  mov     eax, 80004005h
0x14000b503  mov     rcx, [rbp+0A00h+var_30]
0x14000b50a  xor     rcx, rsp; StackCookie
0x14000b50d  call    __security_check_cookie
0x14000b512  lea     r11, [rsp+0B00h+var_20]
0x14000b51a  mov     rbx, [r11+30h]
0x14000b51e  mov     rsi, [r11+40h]
0x14000b522  mov     rsp, r11
0x14000b525  pop     r15
0x14000b527  pop     r14
0x14000b529  pop     r12
0x14000b52b  pop     rdi
0x14000b52c  pop     rbp
0x14000b52d  retn
```
