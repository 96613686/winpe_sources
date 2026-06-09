# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001a0dc`
- end: `0x18001a381`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `677`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a3a0`

## callees

- `0x180006bd0`
- `0x1800126c4`
- `0x180013f48`
- `0x1800145d4`
- `0x180014ed0`
- `0x180015774`
- `0x180017574`
- `0x180018d1c`
- `0x18001a0dc`
- `0x18001a6f0`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a1eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a1eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a236`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a236`

## string_xrefs

- `0x18001a344`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int16 *v15; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+90h] [rbp-70h]
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v29[527]; // [rsp+2B2h] [rbp+1B2h] BYREF
  unsigned __int16 v30[520]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v26 = -2;
  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v23);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v21,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_24;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_24;
    }
    ATL::CAtlModule::EscapeSingleQuote(v30, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v28 = 34;
      if ( !ocscpy_s(v29, v14, v30) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_24;
      }
      v16 = -1;
      do
        ++v16;
      while ( v29[v16 - 1] );
      v29[(int)v16 - 1] = 34;
      v17 = 2LL * (int)v16 + 2;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure(&v28);
      *(unsigned __int16 *)((char *)&v29[-1] + v17) = 0;
      v15 = &v28;
    }
    else
    {
      v15 = v30;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v30);
    if ( Error < 0 )
      goto LABEL_23;
    v20 = 0;
    if ( a3 )
    {
      if ( !a2 )
      {
        Error = -2147024809;
LABEL_32:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_23;
      }
      v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
    }
    else
    {
      if ( !a2 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        Error = -2147024809;
        goto LABEL_23;
      }
      v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 0);
    }
    Error = v18;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001a0dc  push    rbp
0x18001a0de  push    rbx
0x18001a0df  push    rsi
0x18001a0e0  push    rdi
0x18001a0e1  push    r12
0x18001a0e3  push    r14
0x18001a0e5  push    r15
0x18001a0e7  lea     rbp, [rsp-9F0h]
0x18001a0ef  sub     rsp, 0AF0h
0x18001a0f6  mov     [rbp+0A20h+var_A90], 0FFFFFFFFFFFFFFFEh
0x18001a0fe  mov     rax, cs:__security_cookie
0x18001a105  xor     rax, rsp
0x18001a108  mov     [rbp+0A20h+var_40], rax
0x18001a10f  mov     rbx, r9
0x18001a112  mov     r15d, r8d
0x18001a115  mov     rdi, rdx
0x18001a118  mov     r14, rcx
0x18001a11b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001a122  mov     [rsp+0B20h+var_AE0], rax
0x18001a127  xor     r12d, r12d
0x18001a12a  mov     [rsp+0B20h+var_AD8], r12
0x18001a12f  mov     [rsp+0B20h+var_AD0], r12
0x18001a134  mov     [rsp+0B20h+var_AC8], r12d
0x18001a139  xorps   xmm0, xmm0
0x18001a13c  xor     eax, eax
0x18001a13e  movups  [rsp+0B20h+var_AC0], xmm0
0x18001a143  movups  [rsp+0B20h+var_AB0], xmm0
0x18001a148  mov     [rbp+0A20h+var_AA0], rax
0x18001a14c  mov     [rbp+0A20h+var_A98], r12b
0x18001a150  lea     rcx, [rsp+0B20h+var_AC0]; this
0x18001a155  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001a15a  mov     esi, eax
0x18001a15c  test    eax, eax
0x18001a15e  jns     short loc_18001A18E
0x18001a160  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a165  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a16a  mov     eax, esi
0x18001a16c  mov     rcx, [rbp+0A20h+var_40]
0x18001a173  xor     rcx, rsp; StackCookie
0x18001a176  call    __security_check_cookie
0x18001a17b  add     rsp, 0AF0h
0x18001a182  pop     r15
0x18001a184  pop     r14
0x18001a186  pop     r12
0x18001a188  pop     rdi
0x18001a189  pop     rsi
0x18001a18a  pop     rbx
0x18001a18b  pop     rbp
0x18001a18c  retn
0x18001a18e  test    rbx, rbx
0x18001a191  jz      short loc_18001A1B2
0x18001a193  jmp     short loc_18001A1AA
0x18001a195  mov     r8, [rbx+8]; unsigned __int16 *
0x18001a199  mov     rdx, rax; unsigned __int16 *
0x18001a19c  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a1a1  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a1a6  lea     rbx, [rbx+10h]
0x18001a1aa  mov     rax, [rbx]
0x18001a1ad  test    rax, rax
0x18001a1b0  jnz     short loc_18001A195
0x18001a1b2  mov     rax, [r14]
0x18001a1b5  lea     rdx, [rsp+0B20h+var_AE0]
0x18001a1ba  mov     rcx, r14
0x18001a1bd  mov     rax, [rax+28h]
0x18001a1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1c6  mov     ebx, eax
0x18001a1c8  test    eax, eax
0x18001a1ca  js      loc_18001A309
0x18001a1d0  mov     [rsp+0B20h+var_AF0], r12
0x18001a1d5  mov     rbx, cs:hModule
0x18001a1dc  mov     esi, 104h
0x18001a1e1  mov     r8d, esi; nSize
0x18001a1e4  lea     rdx, [rbp+0A20h+Filename]; lpFilename
0x18001a1e8  mov     rcx, rbx; hModule
0x18001a1eb  call    cs:__imp_GetModuleFileNameW
0x18001a1f2  nop     dword ptr [rax+rax+00h]
0x18001a1f7  test    eax, eax
0x18001a1f9  jnz     short loc_18001A207
0x18001a1fb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a200  mov     ebx, eax
0x18001a202  jmp     loc_18001A2FF
0x18001a207  cmp     eax, esi
0x18001a209  jnz     short loc_18001A21F
0x18001a20b  lea     rcx, [rsp+0B20h+var_AF0]
0x18001a210  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a215  mov     ebx, 8007007Ah
0x18001a21a  jmp     loc_18001A309
0x18001a21f  lea     r8, [rbp+0A20h+Filename]; unsigned __int16 *
0x18001a223  lea     rcx, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001a22a  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001a22f  test    rbx, rbx
0x18001a232  jz      short loc_18001A250
0x18001a234  xor     ecx, ecx; lpModuleName
0x18001a236  call    cs:__imp_GetModuleHandleW
0x18001a23d  nop     dword ptr [rax+rax+00h]
0x18001a242  cmp     rbx, rax
0x18001a245  jz      short loc_18001A250
0x18001a247  lea     r8, [rbp+0A20h+var_450]
0x18001a24e  jmp     short loc_18001A2CA
0x18001a250  mov     ebx, 22h ; '"'
0x18001a255  mov     [rbp+0A20h+var_870], bx
0x18001a25c  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001a263  lea     rcx, [rbp+0A20h+var_86E]; unsigned __int16 *
0x18001a26a  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001a26f  test    al, al
0x18001a271  jnz     short loc_18001A287
0x18001a273  lea     rcx, [rsp+0B20h+var_AF0]
0x18001a278  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a27d  mov     ebx, 80004005h
0x18001a282  jmp     loc_18001A309
0x18001a287  lea     rcx, [rbp+0A20h+var_870]
0x18001a28e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a292  inc     rax
0x18001a295  cmp     [rcx+rax*2], r12w
0x18001a29a  jnz     short loc_18001A292
0x18001a29c  cdqe
0x18001a29e  mov     [rbp+rax*2+0A20h+var_870], bx
0x18001a2a6  lea     rax, ds:2[rax*2]
0x18001a2ae  cmp     rax, 418h
0x18001a2b4  jnb     loc_18001A37B
0x18001a2ba  mov     [rbp+rax+0A20h+var_870], r12w
0x18001a2c3  lea     r8, [rbp+0A20h+var_870]; unsigned __int16 *
0x18001a2ca  lea     rdx, aModule; "Module"
0x18001a2d1  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a2d6  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a2db  mov     ebx, eax
0x18001a2dd  test    eax, eax
0x18001a2df  js      short loc_18001A2FF
0x18001a2e1  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001a2e8  lea     rdx, aModuleRaw; "Module_Raw"
0x18001a2ef  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a2f4  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a2f9  mov     ebx, eax
0x18001a2fb  test    eax, eax
0x18001a2fd  jns     short loc_18001A31A
0x18001a2ff  lea     rcx, [rsp+0B20h+var_AF0]
0x18001a304  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a309  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a30e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a313  mov     eax, ebx
0x18001a315  jmp     loc_18001A16C
0x18001a31a  mov     [rsp+0B20h+var_AE8], r12
0x18001a31f  test    r15d, r15d
0x18001a322  jz      short loc_18001A33A
0x18001a324  test    rdi, rdi
0x18001a327  jz      short loc_18001A333
0x18001a329  mov     [rsp+0B20h+var_B00], 1
0x18001a331  jmp     short loc_18001A344
0x18001a333  mov     ebx, 80070057h
0x18001a338  jmp     short loc_18001A35E
0x18001a33a  test    rdi, rdi
0x18001a33d  jz      short loc_18001A36A
0x18001a33f  mov     [rsp+0B20h+var_B00], r12d; int
0x18001a344  lea     r9, aRegistry; "REGISTRY"
0x18001a34b  mov     r8, rdi; unsigned __int16 *
0x18001a34e  lea     rdx, [rbp+0A20h+Filename]; unsigned __int16 *
0x18001a352  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a357  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001a35c  mov     ebx, eax
0x18001a35e  lea     rcx, [rsp+0B20h+var_AE8]
0x18001a363  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a368  jmp     short loc_18001A2FF
0x18001a36a  lea     rcx, [rsp+0B20h+var_AE8]
0x18001a36f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a374  mov     ebx, 80070057h
0x18001a379  jmp     short loc_18001A2FF
0x18001a37b  call    __report_rangecheckfailure
```
