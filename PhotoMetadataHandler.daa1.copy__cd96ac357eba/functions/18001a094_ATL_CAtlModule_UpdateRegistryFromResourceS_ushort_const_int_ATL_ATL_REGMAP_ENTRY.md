# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001a094`
- end: `0x18001a314`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a330`

## callees

- `0x180002800`
- `0x180016020`
- `0x180016060`
- `0x1800175c0`
- `0x1800176ac`
- `0x180017a60`
- `0x180018300`
- `0x180018a54`
- `0x1800192e0`
- `0x18001a094`
- `0x18001a33c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a19a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a19a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a1df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a1df`

## string_xrefs

- `0x18001a2e1`: `REGISTRY`

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
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v28[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v29[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

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
    ATL::CAtlModule::EscapeSingleQuote(v29, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v27 = 34;
      if ( !ocscpy_s(v28, v14, v29) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_24;
      }
      v16 = -1;
      do
        ++v16;
      while ( v28[v16 - 1] );
      v28[(int)v16 - 1] = 34;
      v17 = 2LL * (int)v16 + 2;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v28[-1] + v17) = 0;
      v15 = &v27;
    }
    else
    {
      v15 = v29;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
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
0x18001a094  push    rbp
0x18001a096  push    rbx
0x18001a097  push    rsi
0x18001a098  push    rdi
0x18001a099  push    r12
0x18001a09b  push    r14
0x18001a09d  push    r15
0x18001a09f  lea     rbp, [rsp-9E0h]
0x18001a0a7  sub     rsp, 0AE0h
0x18001a0ae  mov     rax, cs:__security_cookie
0x18001a0b5  xor     rax, rsp
0x18001a0b8  mov     [rbp+0A10h+var_40], rax
0x18001a0bf  mov     rbx, r9
0x18001a0c2  mov     r15d, r8d
0x18001a0c5  mov     rdi, rdx
0x18001a0c8  mov     r14, rcx
0x18001a0cb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001a0d2  mov     [rsp+0B10h+var_AD0], rax
0x18001a0d7  xor     r12d, r12d
0x18001a0da  mov     [rsp+0B10h+var_AC8], r12
0x18001a0df  mov     [rsp+0B10h+var_AC0], r12
0x18001a0e4  mov     [rsp+0B10h+var_AB8], r12d
0x18001a0e9  xorps   xmm0, xmm0
0x18001a0ec  xor     eax, eax
0x18001a0ee  movups  [rsp+0B10h+var_AB0], xmm0
0x18001a0f3  movups  [rsp+0B10h+var_AA0], xmm0
0x18001a0f8  mov     [rbp+0A10h+var_A90], rax
0x18001a0fc  mov     [rbp+0A10h+var_A88], r12b
0x18001a100  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001a105  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001a10a  mov     esi, eax
0x18001a10c  test    eax, eax
0x18001a10e  jns     short loc_18001A13D
0x18001a110  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a115  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a11a  mov     eax, esi
0x18001a11c  mov     rcx, [rbp+0A10h+var_40]
0x18001a123  xor     rcx, rsp; StackCookie
0x18001a126  call    __security_check_cookie
0x18001a12b  add     rsp, 0AE0h
0x18001a132  pop     r15
0x18001a134  pop     r14
0x18001a136  pop     r12
0x18001a138  pop     rdi
0x18001a139  pop     rsi
0x18001a13a  pop     rbx
0x18001a13b  pop     rbp
0x18001a13c  retn
0x18001a13d  test    rbx, rbx
0x18001a140  jz      short loc_18001A161
0x18001a142  jmp     short loc_18001A159
0x18001a144  mov     r8, [rbx+8]; unsigned __int16 *
0x18001a148  mov     rdx, rax; unsigned __int16 *
0x18001a14b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a150  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a155  lea     rbx, [rbx+10h]
0x18001a159  mov     rax, [rbx]
0x18001a15c  test    rax, rax
0x18001a15f  jnz     short loc_18001A144
0x18001a161  mov     rax, [r14]
0x18001a164  lea     rdx, [rsp+0B10h+var_AD0]
0x18001a169  mov     rcx, r14
0x18001a16c  mov     rax, [rax+28h]
0x18001a170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a175  mov     ebx, eax
0x18001a177  test    eax, eax
0x18001a179  js      loc_18001A2AD
0x18001a17f  mov     [rsp+0B10h+var_AE0], r12
0x18001a184  mov     rbx, cs:hModule
0x18001a18b  mov     esi, 104h
0x18001a190  mov     r8d, esi; nSize
0x18001a193  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001a197  mov     rcx, rbx; hModule
0x18001a19a  call    cs:__imp_GetModuleFileNameW
0x18001a1a0  test    eax, eax
0x18001a1a2  jnz     short loc_18001A1B0
0x18001a1a4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a1a9  mov     ebx, eax
0x18001a1ab  jmp     loc_18001A2A3
0x18001a1b0  cmp     eax, esi
0x18001a1b2  jnz     short loc_18001A1C8
0x18001a1b4  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a1b9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a1be  mov     ebx, 8007007Ah
0x18001a1c3  jmp     loc_18001A2AD
0x18001a1c8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001a1cc  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a1d3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001a1d8  test    rbx, rbx
0x18001a1db  jz      short loc_18001A1F3
0x18001a1dd  xor     ecx, ecx; lpModuleName
0x18001a1df  call    cs:__imp_GetModuleHandleW
0x18001a1e5  cmp     rbx, rax
0x18001a1e8  jz      short loc_18001A1F3
0x18001a1ea  lea     r8, [rbp+0A10h+var_450]
0x18001a1f1  jmp     short loc_18001A26E
0x18001a1f3  mov     ebx, 22h ; '"'
0x18001a1f8  mov     [rbp+0A10h+var_870], bx
0x18001a1ff  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a206  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001a20d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001a212  test    al, al
0x18001a214  jnz     short loc_18001A22A
0x18001a216  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a21b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a220  mov     ebx, 80004005h
0x18001a225  jmp     loc_18001A2AD
0x18001a22a  lea     rcx, [rbp+0A10h+var_870]
0x18001a231  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a235  inc     rax
0x18001a238  cmp     [rcx+rax*2], r12w
0x18001a23d  jnz     short loc_18001A235
0x18001a23f  cdqe
0x18001a241  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001a249  lea     rcx, ds:2[rax*2]
0x18001a251  cmp     rcx, 418h
0x18001a258  jnb     loc_18001A30E
0x18001a25e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001a267  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001a26e  lea     rdx, aModule; "Module"
0x18001a275  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a27a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a27f  mov     ebx, eax
0x18001a281  test    eax, eax
0x18001a283  js      short loc_18001A2A3
0x18001a285  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a28c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001a293  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a298  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a29d  mov     ebx, eax
0x18001a29f  test    eax, eax
0x18001a2a1  jns     short loc_18001A2BE
0x18001a2a3  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a2a8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a2ad  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a2b2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a2b7  mov     eax, ebx
0x18001a2b9  jmp     loc_18001A11C
0x18001a2be  mov     [rsp+0B10h+var_AD8], r12
0x18001a2c3  test    r15d, r15d
0x18001a2c6  jz      short loc_18001A2D7
0x18001a2c8  test    rdi, rdi
0x18001a2cb  jz      short loc_18001A2FD
0x18001a2cd  mov     [rsp+0B10h+var_AF0], 1
0x18001a2d5  jmp     short loc_18001A2E1
0x18001a2d7  test    rdi, rdi
0x18001a2da  jz      short loc_18001A2FD
0x18001a2dc  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001a2e1  lea     r9, aRegistry; "REGISTRY"
0x18001a2e8  mov     r8, rdi; unsigned __int16 *
0x18001a2eb  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001a2ef  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a2f4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001a2f9  mov     ebx, eax
0x18001a2fb  jmp     short loc_18001A302
0x18001a2fd  mov     ebx, 80070057h
0x18001a302  lea     rcx, [rsp+0B10h+var_AD8]
0x18001a307  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a30c  jmp     short loc_18001A2A3
0x18001a30e  call    __report_rangecheckfailure
```
