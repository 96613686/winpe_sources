# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000ddf4`
- end: `0x18000e074`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e090`

## callees

- `0x180002300`
- `0x180002770`
- `0x18000ac10`
- `0x18000adbc`
- `0x18000b220`
- `0x18000b9f0`
- `0x18000c378`
- `0x18000c674`
- `0x18000ce70`
- `0x18000ddf4`
- `0x18000e09c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000defa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000defa`

## string_xrefs

- `0x18000e041`: `REGISTRY`

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
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  wchar_t v28[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  wchar_t v29[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

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
      *(wchar_t *)((char *)&v28[-1] + v17) = 0;
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
0x18000ddf4  push    rbp
0x18000ddf6  push    rbx
0x18000ddf7  push    rsi
0x18000ddf8  push    rdi
0x18000ddf9  push    r12
0x18000ddfb  push    r14
0x18000ddfd  push    r15
0x18000ddff  lea     rbp, [rsp-9E0h]
0x18000de07  sub     rsp, 0AE0h
0x18000de0e  mov     rax, cs:__security_cookie
0x18000de15  xor     rax, rsp
0x18000de18  mov     [rbp+0A10h+var_40], rax
0x18000de1f  mov     rbx, r9
0x18000de22  mov     r15d, r8d
0x18000de25  mov     rdi, rdx
0x18000de28  mov     r14, rcx
0x18000de2b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000de32  mov     [rsp+0B10h+var_AD0], rax
0x18000de37  xor     r12d, r12d
0x18000de3a  mov     [rsp+0B10h+var_AC8], r12
0x18000de3f  mov     [rsp+0B10h+var_AC0], r12
0x18000de44  mov     [rsp+0B10h+var_AB8], r12d
0x18000de49  xorps   xmm0, xmm0
0x18000de4c  xor     eax, eax
0x18000de4e  movups  [rsp+0B10h+var_AB0], xmm0
0x18000de53  movups  [rsp+0B10h+var_AA0], xmm0
0x18000de58  mov     [rbp+0A10h+var_A90], rax
0x18000de5c  mov     [rbp+0A10h+var_A88], r12b
0x18000de60  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000de65  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000de6a  mov     esi, eax
0x18000de6c  test    eax, eax
0x18000de6e  jns     short loc_18000DE9D
0x18000de70  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000de75  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000de7a  mov     eax, esi
0x18000de7c  mov     rcx, [rbp+0A10h+var_40]
0x18000de83  xor     rcx, rsp; StackCookie
0x18000de86  call    __security_check_cookie
0x18000de8b  add     rsp, 0AE0h
0x18000de92  pop     r15
0x18000de94  pop     r14
0x18000de96  pop     r12
0x18000de98  pop     rdi
0x18000de99  pop     rsi
0x18000de9a  pop     rbx
0x18000de9b  pop     rbp
0x18000de9c  retn
0x18000de9d  test    rbx, rbx
0x18000dea0  jz      short loc_18000DEC1
0x18000dea2  jmp     short loc_18000DEB9
0x18000dea4  mov     r8, [rbx+8]; wchar_t *
0x18000dea8  mov     rdx, rax; wchar_t *
0x18000deab  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000deb0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18000deb5  lea     rbx, [rbx+10h]
0x18000deb9  mov     rax, [rbx]
0x18000debc  test    rax, rax
0x18000debf  jnz     short loc_18000DEA4
0x18000dec1  mov     rax, [r14]
0x18000dec4  lea     rdx, [rsp+0B10h+var_AD0]
0x18000dec9  mov     rcx, r14
0x18000decc  mov     rax, [rax+28h]
0x18000ded0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded5  mov     ebx, eax
0x18000ded7  test    eax, eax
0x18000ded9  js      loc_18000E00D
0x18000dedf  mov     [rsp+0B10h+var_AE0], r12
0x18000dee4  mov     rbx, cs:hModule
0x18000deeb  mov     esi, 104h
0x18000def0  mov     r8d, esi; nSize
0x18000def3  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000def7  mov     rcx, rbx; hModule
0x18000defa  call    cs:__imp_GetModuleFileNameW
0x18000df00  test    eax, eax
0x18000df02  jnz     short loc_18000DF10
0x18000df04  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000df09  mov     ebx, eax
0x18000df0b  jmp     loc_18000E003
0x18000df10  cmp     eax, esi
0x18000df12  jnz     short loc_18000DF28
0x18000df14  lea     rcx, [rsp+0B10h+var_AE0]
0x18000df19  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000df1e  mov     ebx, 8007007Ah
0x18000df23  jmp     loc_18000E00D
0x18000df28  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x18000df2c  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x18000df33  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x18000df38  test    rbx, rbx
0x18000df3b  jz      short loc_18000DF53
0x18000df3d  xor     ecx, ecx; lpModuleName
0x18000df3f  call    cs:__imp_GetModuleHandleW
0x18000df45  cmp     rbx, rax
0x18000df48  jz      short loc_18000DF53
0x18000df4a  lea     r8, [rbp+0A10h+var_450]
0x18000df51  jmp     short loc_18000DFCE
0x18000df53  mov     ebx, 22h ; '"'
0x18000df58  mov     [rbp+0A10h+var_870], bx
0x18000df5f  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18000df66  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18000df6d  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x18000df72  test    al, al
0x18000df74  jnz     short loc_18000DF8A
0x18000df76  lea     rcx, [rsp+0B10h+var_AE0]
0x18000df7b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000df80  mov     ebx, 80004005h
0x18000df85  jmp     loc_18000E00D
0x18000df8a  lea     rcx, [rbp+0A10h+var_870]
0x18000df91  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000df95  inc     rax
0x18000df98  cmp     [rcx+rax*2], r12w
0x18000df9d  jnz     short loc_18000DF95
0x18000df9f  cdqe
0x18000dfa1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000dfa9  lea     rcx, ds:2[rax*2]
0x18000dfb1  cmp     rcx, 418h
0x18000dfb8  jnb     loc_18000E06E
0x18000dfbe  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000dfc7  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x18000dfce  lea     rdx, aModule; "Module"
0x18000dfd5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000dfda  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18000dfdf  mov     ebx, eax
0x18000dfe1  test    eax, eax
0x18000dfe3  js      short loc_18000E003
0x18000dfe5  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18000dfec  lea     rdx, aModuleRaw; "Module_Raw"
0x18000dff3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000dff8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18000dffd  mov     ebx, eax
0x18000dfff  test    eax, eax
0x18000e001  jns     short loc_18000E01E
0x18000e003  lea     rcx, [rsp+0B10h+var_AE0]
0x18000e008  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e00d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000e012  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000e017  mov     eax, ebx
0x18000e019  jmp     loc_18000DE7C
0x18000e01e  mov     [rsp+0B10h+var_AD8], r12
0x18000e023  test    r15d, r15d
0x18000e026  jz      short loc_18000E037
0x18000e028  test    rdi, rdi
0x18000e02b  jz      short loc_18000E05D
0x18000e02d  mov     [rsp+0B10h+var_AF0], 1
0x18000e035  jmp     short loc_18000E041
0x18000e037  test    rdi, rdi
0x18000e03a  jz      short loc_18000E05D
0x18000e03c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000e041  lea     r9, aRegistry; "REGISTRY"
0x18000e048  mov     r8, rdi; wchar_t *
0x18000e04b  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18000e04f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000e054  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18000e059  mov     ebx, eax
0x18000e05b  jmp     short loc_18000E062
0x18000e05d  mov     ebx, 80070057h
0x18000e062  lea     rcx, [rsp+0B10h+var_AD8]
0x18000e067  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000e06c  jmp     short loc_18000E003
0x18000e06e  call    __report_rangecheckfailure
```
