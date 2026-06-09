# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140024c4c`
- end: `0x140024ed4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `648`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140024ef0`

## callees

- `0x1400030a0`
- `0x1400034f0`
- `0x14001b6ec`
- `0x14001bf90`
- `0x14001cd00`
- `0x14001d4e8`
- `0x14001e558`
- `0x140021444`
- `0x140022c44`
- `0x140024c4c`
- `0x140026a94`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140024d5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140024d5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024d9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024d9f`

## string_xrefs

- `0x140024ea1`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const wchar_t *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  wchar_t *v15; // r8
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
  __int64 v26; // [rsp+90h] [rbp-70h]
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v28; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t v29[527]; // [rsp+2B2h] [rbp+1B2h] BYREF
  wchar_t v30[520]; // [rsp+6D0h] [rbp+5D0h] BYREF

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
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, *(const wchar_t **)a4, *((const wchar_t **)a4 + 1));
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
      Error = ResultFromLastError();
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
        _report_rangecheckfailure();
      *(wchar_t *)((char *)&v29[-1] + v17) = 0;
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
0x140024c4c  push    rbp
0x140024c4e  push    rbx
0x140024c4f  push    rsi
0x140024c50  push    rdi
0x140024c51  push    r12
0x140024c53  push    r14
0x140024c55  push    r15
0x140024c57  lea     rbp, [rsp-9F0h]
0x140024c5f  sub     rsp, 0AF0h
0x140024c66  mov     [rbp+0A20h+var_A90], 0FFFFFFFFFFFFFFFEh
0x140024c6e  mov     rax, cs:__security_cookie
0x140024c75  xor     rax, rsp
0x140024c78  mov     [rbp+0A20h+var_40], rax
0x140024c7f  mov     rbx, r9
0x140024c82  mov     r15d, r8d
0x140024c85  mov     rdi, rdx
0x140024c88  mov     r14, rcx
0x140024c8b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140024c92  mov     [rsp+0B20h+var_AE0], rax
0x140024c97  xor     r12d, r12d
0x140024c9a  mov     [rsp+0B20h+var_AD8], r12
0x140024c9f  mov     [rsp+0B20h+var_AD0], r12
0x140024ca4  mov     [rsp+0B20h+var_AC8], r12d
0x140024ca9  xorps   xmm0, xmm0
0x140024cac  xor     eax, eax
0x140024cae  movups  [rsp+0B20h+var_AC0], xmm0
0x140024cb3  movups  [rsp+0B20h+var_AB0], xmm0
0x140024cb8  mov     [rbp+0A20h+var_AA0], rax
0x140024cbc  mov     [rbp+0A20h+var_A98], r12b
0x140024cc0  lea     rcx, [rsp+0B20h+var_AC0]; this
0x140024cc5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x140024cca  mov     esi, eax
0x140024ccc  test    eax, eax
0x140024cce  jns     short loc_140024CFD
0x140024cd0  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024cd5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140024cda  mov     eax, esi
0x140024cdc  mov     rcx, [rbp+0A20h+var_40]
0x140024ce3  xor     rcx, rsp; StackCookie
0x140024ce6  call    __security_check_cookie
0x140024ceb  add     rsp, 0AF0h
0x140024cf2  pop     r15
0x140024cf4  pop     r14
0x140024cf6  pop     r12
0x140024cf8  pop     rdi
0x140024cf9  pop     rsi
0x140024cfa  pop     rbx
0x140024cfb  pop     rbp
0x140024cfc  retn
0x140024cfd  test    rbx, rbx
0x140024d00  jz      short loc_140024D21
0x140024d02  jmp     short loc_140024D19
0x140024d04  mov     r8, [rbx+8]; wchar_t *
0x140024d08  mov     rdx, rax; wchar_t *
0x140024d0b  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024d10  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140024d15  lea     rbx, [rbx+10h]
0x140024d19  mov     rax, [rbx]
0x140024d1c  test    rax, rax
0x140024d1f  jnz     short loc_140024D04
0x140024d21  mov     rax, [r14]
0x140024d24  lea     rdx, [rsp+0B20h+var_AE0]
0x140024d29  mov     rcx, r14
0x140024d2c  mov     rax, [rax+28h]
0x140024d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024d35  mov     ebx, eax
0x140024d37  test    eax, eax
0x140024d39  js      loc_140024E6D
0x140024d3f  mov     [rsp+0B20h+var_AF0], r12
0x140024d44  mov     rbx, cs:hModule
0x140024d4b  mov     esi, 104h
0x140024d50  mov     r8d, esi; nSize
0x140024d53  lea     rdx, [rbp+0A20h+Filename]; lpFilename
0x140024d57  mov     rcx, rbx; hModule
0x140024d5a  call    cs:__imp_GetModuleFileNameW
0x140024d60  test    eax, eax
0x140024d62  jnz     short loc_140024D70
0x140024d64  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140024d69  mov     ebx, eax
0x140024d6b  jmp     loc_140024E63
0x140024d70  cmp     eax, esi
0x140024d72  jnz     short loc_140024D88
0x140024d74  lea     rcx, [rsp+0B20h+var_AF0]
0x140024d79  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024d7e  mov     ebx, 8007007Ah
0x140024d83  jmp     loc_140024E6D
0x140024d88  lea     r8, [rbp+0A20h+Filename]; wchar_t *
0x140024d8c  lea     rcx, [rbp+0A20h+var_450]; wchar_t *
0x140024d93  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x140024d98  test    rbx, rbx
0x140024d9b  jz      short loc_140024DB3
0x140024d9d  xor     ecx, ecx; lpModuleName
0x140024d9f  call    cs:__imp_GetModuleHandleW
0x140024da5  cmp     rbx, rax
0x140024da8  jz      short loc_140024DB3
0x140024daa  lea     r8, [rbp+0A20h+var_450]
0x140024db1  jmp     short loc_140024E2E
0x140024db3  mov     ebx, 22h ; '"'
0x140024db8  mov     [rbp+0A20h+var_870], bx
0x140024dbf  lea     r8, [rbp+0A20h+var_450]; wchar_t *
0x140024dc6  lea     rcx, [rbp+0A20h+var_86E]; wchar_t *
0x140024dcd  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x140024dd2  test    al, al
0x140024dd4  jnz     short loc_140024DEA
0x140024dd6  lea     rcx, [rsp+0B20h+var_AF0]
0x140024ddb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024de0  mov     ebx, 80004005h
0x140024de5  jmp     loc_140024E6D
0x140024dea  lea     rcx, [rbp+0A20h+var_870]
0x140024df1  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024df5  inc     rax
0x140024df8  cmp     [rcx+rax*2], r12w
0x140024dfd  jnz     short loc_140024DF5
0x140024dff  cdqe
0x140024e01  mov     [rbp+rax*2+0A20h+var_870], bx
0x140024e09  lea     rcx, ds:2[rax*2]
0x140024e11  cmp     rcx, 418h
0x140024e18  jnb     loc_140024ECE
0x140024e1e  mov     [rbp+rcx+0A20h+var_870], r12w
0x140024e27  lea     r8, [rbp+0A20h+var_870]; wchar_t *
0x140024e2e  lea     rdx, aModule_0; "Module"
0x140024e35  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024e3a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140024e3f  mov     ebx, eax
0x140024e41  test    eax, eax
0x140024e43  js      short loc_140024E63
0x140024e45  lea     r8, [rbp+0A20h+var_450]; wchar_t *
0x140024e4c  lea     rdx, aModuleRaw; "Module_Raw"
0x140024e53  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024e58  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140024e5d  mov     ebx, eax
0x140024e5f  test    eax, eax
0x140024e61  jns     short loc_140024E7E
0x140024e63  lea     rcx, [rsp+0B20h+var_AF0]
0x140024e68  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024e6d  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024e72  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140024e77  mov     eax, ebx
0x140024e79  jmp     loc_140024CDC
0x140024e7e  mov     [rsp+0B20h+var_AE8], r12
0x140024e83  test    r15d, r15d
0x140024e86  jz      short loc_140024E97
0x140024e88  test    rdi, rdi
0x140024e8b  jz      short loc_140024EBD
0x140024e8d  mov     [rsp+0B20h+var_B00], 1
0x140024e95  jmp     short loc_140024EA1
0x140024e97  test    rdi, rdi
0x140024e9a  jz      short loc_140024EBD
0x140024e9c  mov     [rsp+0B20h+var_B00], r12d; int
0x140024ea1  lea     r9, aRegistry; "REGISTRY"
0x140024ea8  mov     r8, rdi; wchar_t *
0x140024eab  lea     rdx, [rbp+0A20h+Filename]; wchar_t *
0x140024eaf  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024eb4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x140024eb9  mov     ebx, eax
0x140024ebb  jmp     short loc_140024EC2
0x140024ebd  mov     ebx, 80070057h
0x140024ec2  lea     rcx, [rsp+0B20h+var_AE8]
0x140024ec7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024ecc  jmp     short loc_140024E63
0x140024ece  call    __report_rangecheckfailure
```
