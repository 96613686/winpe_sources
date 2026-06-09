# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180010834`
- end: `0x180010ab4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010ad0`

## callees

- `0x180001720`
- `0x180001800`
- `0x1800082ec`
- `0x1800088f8`
- `0x180009650`
- `0x180009df4`
- `0x18000ad00`
- `0x18000bf48`
- `0x18000e660`
- `0x180010834`
- `0x1800110d0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001097f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001097f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001093a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001093a`

## string_xrefs

- `0x180010a81`: `REGISTRY`

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
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  struct _RTL_CRITICAL_SECTION v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v27[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v28[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(&v23, 0, sizeof(v23));
  v24 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init(&v23);
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
    ATL::CAtlModule::EscapeSingleQuote(v28, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v26 = 34;
      if ( !ocscpy_s(v27, v14, v28) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_24;
      }
      v16 = -1;
      do
        ++v16;
      while ( v27[v16 - 1] );
      v27[(int)v16 - 1] = 34;
      v17 = 2LL * (int)v16 + 2;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v27[-1] + v17) = 0;
      v15 = &v26;
    }
    else
    {
      v15 = v28;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v28);
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
0x180010834  push    rbp
0x180010836  push    rbx
0x180010837  push    rsi
0x180010838  push    rdi
0x180010839  push    r12
0x18001083b  push    r14
0x18001083d  push    r15
0x18001083f  lea     rbp, [rsp-9E0h]
0x180010847  sub     rsp, 0AE0h
0x18001084e  mov     rax, cs:__security_cookie
0x180010855  xor     rax, rsp
0x180010858  mov     [rbp+0A10h+var_40], rax
0x18001085f  mov     rbx, r9
0x180010862  mov     r15d, r8d
0x180010865  mov     rdi, rdx
0x180010868  mov     r14, rcx
0x18001086b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180010872  mov     [rsp+0B10h+var_AD0], rax
0x180010877  xor     r12d, r12d
0x18001087a  mov     [rsp+0B10h+var_AC8], r12
0x18001087f  mov     [rsp+0B10h+var_AC0], r12
0x180010884  mov     [rsp+0B10h+var_AB8], r12d
0x180010889  xorps   xmm0, xmm0
0x18001088c  xor     eax, eax
0x18001088e  movups  [rsp+0B10h+var_AB0], xmm0
0x180010893  movups  [rsp+0B10h+var_AA0], xmm0
0x180010898  mov     [rbp+0A10h+var_A90], rax
0x18001089c  mov     [rbp+0A10h+var_A88], r12b
0x1800108a0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x1800108a5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800108aa  mov     esi, eax
0x1800108ac  test    eax, eax
0x1800108ae  jns     short loc_1800108DD
0x1800108b0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800108b5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800108ba  mov     eax, esi
0x1800108bc  mov     rcx, [rbp+0A10h+var_40]
0x1800108c3  xor     rcx, rsp; StackCookie
0x1800108c6  call    __security_check_cookie
0x1800108cb  add     rsp, 0AE0h
0x1800108d2  pop     r15
0x1800108d4  pop     r14
0x1800108d6  pop     r12
0x1800108d8  pop     rdi
0x1800108d9  pop     rsi
0x1800108da  pop     rbx
0x1800108db  pop     rbp
0x1800108dc  retn
0x1800108dd  test    rbx, rbx
0x1800108e0  jz      short loc_180010901
0x1800108e2  jmp     short loc_1800108F9
0x1800108e4  mov     r8, [rbx+8]; unsigned __int16 *
0x1800108e8  mov     rdx, rax; unsigned __int16 *
0x1800108eb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800108f0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800108f5  lea     rbx, [rbx+10h]
0x1800108f9  mov     rax, [rbx]
0x1800108fc  test    rax, rax
0x1800108ff  jnz     short loc_1800108E4
0x180010901  mov     rax, [r14]
0x180010904  lea     rdx, [rsp+0B10h+var_AD0]
0x180010909  mov     rcx, r14
0x18001090c  mov     rax, [rax+28h]
0x180010910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010915  mov     ebx, eax
0x180010917  test    eax, eax
0x180010919  js      loc_180010A4D
0x18001091f  mov     [rsp+0B10h+var_AE0], r12
0x180010924  mov     rbx, cs:hModule
0x18001092b  mov     esi, 104h
0x180010930  mov     r8d, esi; nSize
0x180010933  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180010937  mov     rcx, rbx; hModule
0x18001093a  call    cs:__imp_GetModuleFileNameW
0x180010940  test    eax, eax
0x180010942  jnz     short loc_180010950
0x180010944  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010949  mov     ebx, eax
0x18001094b  jmp     loc_180010A43
0x180010950  cmp     eax, esi
0x180010952  jnz     short loc_180010968
0x180010954  lea     rcx, [rsp+0B10h+var_AE0]
0x180010959  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001095e  mov     ebx, 8007007Ah
0x180010963  jmp     loc_180010A4D
0x180010968  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001096c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180010973  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180010978  test    rbx, rbx
0x18001097b  jz      short loc_180010993
0x18001097d  xor     ecx, ecx; lpModuleName
0x18001097f  call    cs:__imp_GetModuleHandleW
0x180010985  cmp     rbx, rax
0x180010988  jz      short loc_180010993
0x18001098a  lea     r8, [rbp+0A10h+var_450]
0x180010991  jmp     short loc_180010A0E
0x180010993  mov     ebx, 22h ; '"'
0x180010998  mov     [rbp+0A10h+var_870], bx
0x18001099f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800109a6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x1800109ad  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800109b2  test    al, al
0x1800109b4  jnz     short loc_1800109CA
0x1800109b6  lea     rcx, [rsp+0B10h+var_AE0]
0x1800109bb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800109c0  mov     ebx, 80004005h
0x1800109c5  jmp     loc_180010A4D
0x1800109ca  lea     rcx, [rbp+0A10h+var_870]
0x1800109d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800109d5  inc     rax
0x1800109d8  cmp     [rcx+rax*2], r12w
0x1800109dd  jnz     short loc_1800109D5
0x1800109df  cdqe
0x1800109e1  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800109e9  lea     rcx, ds:2[rax*2]
0x1800109f1  cmp     rcx, 418h
0x1800109f8  jnb     loc_180010AAE
0x1800109fe  mov     [rbp+rcx+0A10h+var_870], r12w
0x180010a07  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180010a0e  lea     rdx, aModule; "Module"
0x180010a15  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010a1a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180010a1f  mov     ebx, eax
0x180010a21  test    eax, eax
0x180010a23  js      short loc_180010A43
0x180010a25  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180010a2c  lea     rdx, aModuleRaw; "Module_Raw"
0x180010a33  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010a38  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180010a3d  mov     ebx, eax
0x180010a3f  test    eax, eax
0x180010a41  jns     short loc_180010A5E
0x180010a43  lea     rcx, [rsp+0B10h+var_AE0]
0x180010a48  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010a4d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010a52  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180010a57  mov     eax, ebx
0x180010a59  jmp     loc_1800108BC
0x180010a5e  mov     [rsp+0B10h+var_AD8], r12
0x180010a63  test    r15d, r15d
0x180010a66  jz      short loc_180010A77
0x180010a68  test    rdi, rdi
0x180010a6b  jz      short loc_180010A9D
0x180010a6d  mov     [rsp+0B10h+var_AF0], 1
0x180010a75  jmp     short loc_180010A81
0x180010a77  test    rdi, rdi
0x180010a7a  jz      short loc_180010A9D
0x180010a7c  mov     [rsp+0B10h+var_AF0], r12d; int
0x180010a81  lea     r9, aRegistry; "REGISTRY"
0x180010a88  mov     r8, rdi; unsigned __int16 *
0x180010a8b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180010a8f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010a94  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180010a99  mov     ebx, eax
0x180010a9b  jmp     short loc_180010AA2
0x180010a9d  mov     ebx, 80070057h
0x180010aa2  lea     rcx, [rsp+0B10h+var_AD8]
0x180010aa7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010aac  jmp     short loc_180010A43
0x180010aae  call    __report_rangecheckfailure
```
