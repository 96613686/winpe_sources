# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001a56c`
- end: `0x18001a7c4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `600`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a7e0`

## callees

- `0x180002bf8`
- `0x180017324`
- `0x180017530`
- `0x180017648`
- `0x180017b10`
- `0x1800180ec`
- `0x1800183d0`
- `0x180018ba4`
- `0x180019688`
- `0x18001a56c`
- `0x18001a920`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a68f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a68f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a64a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a64a`

## string_xrefs

- `0x18001a791`: `REGISTRY`

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
  unsigned __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v21[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[48]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v25[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v26[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  ATL::CRegObject::CRegObject((ATL::CRegObject *)v21);
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v22);
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
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _BYTE *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v11 = hModule;
    v19 = 0;
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
    ATL::CAtlModule::EscapeSingleQuote(v26, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v24 = 34;
      if ( !ocscpy_s(v25, v14, v26) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_24;
      }
      v16 = -1;
      do
        ++v16;
      while ( v25[v16 - 1] );
      v17 = 2LL * (int)v16 + 2;
      v25[(int)v16 - 1] = 34;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v25[-1] + v17) = 0;
      v15 = &v24;
    }
    else
    {
      v15 = v26;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v26);
    if ( Error < 0 )
      goto LABEL_23;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_30:
        Error = v18;
LABEL_32:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_23;
      }
    }
    else if ( a2 )
    {
      v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_30;
    }
    Error = -2147024809;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001a56c  push    rbp
0x18001a56e  push    rbx
0x18001a56f  push    rsi
0x18001a570  push    rdi
0x18001a571  push    r12
0x18001a573  push    r14
0x18001a575  push    r15
0x18001a577  lea     rbp, [rsp-9E0h]
0x18001a57f  sub     rsp, 0AE0h
0x18001a586  mov     rax, cs:__security_cookie
0x18001a58d  xor     rax, rsp
0x18001a590  mov     [rbp+0A10h+var_40], rax
0x18001a597  mov     r14, rcx
0x18001a59a  mov     rbx, r9
0x18001a59d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a5a2  mov     r15d, r8d
0x18001a5a5  mov     rdi, rdx
0x18001a5a8  call    ??0CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::CRegObject(void)
0x18001a5ad  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001a5b2  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001a5b7  xor     r12d, r12d
0x18001a5ba  mov     esi, eax
0x18001a5bc  test    eax, eax
0x18001a5be  jns     short loc_18001A5ED
0x18001a5c0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a5c5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a5ca  mov     eax, esi
0x18001a5cc  mov     rcx, [rbp+0A10h+var_40]
0x18001a5d3  xor     rcx, rsp; StackCookie
0x18001a5d6  call    __security_check_cookie
0x18001a5db  add     rsp, 0AE0h
0x18001a5e2  pop     r15
0x18001a5e4  pop     r14
0x18001a5e6  pop     r12
0x18001a5e8  pop     rdi
0x18001a5e9  pop     rsi
0x18001a5ea  pop     rbx
0x18001a5eb  pop     rbp
0x18001a5ec  retn
0x18001a5ed  test    rbx, rbx
0x18001a5f0  jz      short loc_18001A611
0x18001a5f2  jmp     short loc_18001A609
0x18001a5f4  mov     r8, [rbx+8]; unsigned __int16 *
0x18001a5f8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a5fd  mov     rdx, rax; unsigned __int16 *
0x18001a600  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a605  lea     rbx, [rbx+10h]
0x18001a609  mov     rax, [rbx]
0x18001a60c  test    rax, rax
0x18001a60f  jnz     short loc_18001A5F4
0x18001a611  mov     rax, [r14]
0x18001a614  lea     rdx, [rsp+0B10h+var_AD0]
0x18001a619  mov     rcx, r14
0x18001a61c  mov     rax, [rax+28h]
0x18001a620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a625  mov     ebx, eax
0x18001a627  test    eax, eax
0x18001a629  js      loc_18001A75D
0x18001a62f  mov     rbx, cs:hModule
0x18001a636  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001a63a  mov     esi, 104h
0x18001a63f  mov     [rsp+0B10h+var_AE0], r12
0x18001a644  mov     r8d, esi; nSize
0x18001a647  mov     rcx, rbx; hModule
0x18001a64a  call    cs:__imp_GetModuleFileNameW
0x18001a650  test    eax, eax
0x18001a652  jnz     short loc_18001A660
0x18001a654  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a659  mov     ebx, eax
0x18001a65b  jmp     loc_18001A753
0x18001a660  cmp     eax, esi
0x18001a662  jnz     short loc_18001A678
0x18001a664  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a669  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a66e  mov     ebx, 8007007Ah
0x18001a673  jmp     loc_18001A75D
0x18001a678  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001a67c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a683  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001a688  test    rbx, rbx
0x18001a68b  jz      short loc_18001A6A3
0x18001a68d  xor     ecx, ecx; lpModuleName
0x18001a68f  call    cs:__imp_GetModuleHandleW
0x18001a695  cmp     rbx, rax
0x18001a698  jz      short loc_18001A6A3
0x18001a69a  lea     r8, [rbp+0A10h+var_450]
0x18001a6a1  jmp     short loc_18001A71E
0x18001a6a3  mov     ebx, 22h ; '"'
0x18001a6a8  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a6af  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001a6b6  mov     [rbp+0A10h+var_870], bx
0x18001a6bd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001a6c2  test    al, al
0x18001a6c4  jnz     short loc_18001A6DA
0x18001a6c6  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a6cb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a6d0  mov     ebx, 80004005h
0x18001a6d5  jmp     loc_18001A75D
0x18001a6da  lea     rcx, [rbp+0A10h+var_870]
0x18001a6e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a6e5  inc     rax
0x18001a6e8  cmp     [rcx+rax*2], r12w
0x18001a6ed  jnz     short loc_18001A6E5
0x18001a6ef  cdqe
0x18001a6f1  lea     rcx, ds:2[rax*2]
0x18001a6f9  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001a701  cmp     rcx, 418h
0x18001a708  jnb     loc_18001A7BE
0x18001a70e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001a717  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001a71e  lea     rdx, aModule; "Module"
0x18001a725  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a72a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a72f  mov     ebx, eax
0x18001a731  test    eax, eax
0x18001a733  js      short loc_18001A753
0x18001a735  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a73c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001a743  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a748  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a74d  mov     ebx, eax
0x18001a74f  test    eax, eax
0x18001a751  jns     short loc_18001A76E
0x18001a753  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a758  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a75d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a762  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a767  mov     eax, ebx
0x18001a769  jmp     loc_18001A5CC
0x18001a76e  mov     [rsp+0B10h+var_AD8], r12
0x18001a773  test    r15d, r15d
0x18001a776  jz      short loc_18001A787
0x18001a778  test    rdi, rdi
0x18001a77b  jz      short loc_18001A7AD
0x18001a77d  mov     [rsp+0B10h+var_AF0], 1
0x18001a785  jmp     short loc_18001A791
0x18001a787  test    rdi, rdi
0x18001a78a  jz      short loc_18001A7AD
0x18001a78c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001a791  lea     r9, aRegistry; "REGISTRY"
0x18001a798  mov     r8, rdi; unsigned __int16 *
0x18001a79b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001a79f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a7a4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001a7a9  mov     ebx, eax
0x18001a7ab  jmp     short loc_18001A7B2
0x18001a7ad  mov     ebx, 80070057h
0x18001a7b2  lea     rcx, [rsp+0B10h+var_AD8]
0x18001a7b7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a7bc  jmp     short loc_18001A753
0x18001a7be  call    __report_rangecheckfailure
```
