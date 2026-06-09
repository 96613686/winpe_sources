# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001aca4`
- end: `0x18001af31`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `653`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001af50`

## callees

- `0x180002920`
- `0x180016a40`
- `0x180016a80`
- `0x180018078`
- `0x180018174`
- `0x180018530`
- `0x180018d38`
- `0x18001954c`
- `0x180019e6c`
- `0x18001aca4`
- `0x18001af78`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001adab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001adab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001adf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001adf6`

## string_xrefs

- `0x18001aefe`: `REGISTRY`

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
0x18001aca4  push    rbp
0x18001aca6  push    rbx
0x18001aca7  push    rsi
0x18001aca8  push    rdi
0x18001aca9  push    r12
0x18001acab  push    r14
0x18001acad  push    r15
0x18001acaf  lea     rbp, [rsp-9E0h]
0x18001acb7  sub     rsp, 0AE0h
0x18001acbe  mov     rax, cs:__security_cookie
0x18001acc5  xor     rax, rsp
0x18001acc8  mov     [rbp+0A10h+var_40], rax
0x18001accf  mov     rbx, r9
0x18001acd2  mov     r15d, r8d
0x18001acd5  mov     rdi, rdx
0x18001acd8  mov     r14, rcx
0x18001acdb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001ace2  mov     [rsp+0B10h+var_AD0], rax
0x18001ace7  xor     r12d, r12d
0x18001acea  mov     [rsp+0B10h+var_AC8], r12
0x18001acef  mov     [rsp+0B10h+var_AC0], r12
0x18001acf4  mov     [rsp+0B10h+var_AB8], r12d
0x18001acf9  xorps   xmm0, xmm0
0x18001acfc  xor     eax, eax
0x18001acfe  movups  [rsp+0B10h+var_AB0], xmm0
0x18001ad03  movups  [rsp+0B10h+var_AA0], xmm0
0x18001ad08  mov     [rbp+0A10h+var_A90], rax
0x18001ad0c  mov     [rbp+0A10h+var_A88], r12b
0x18001ad10  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001ad15  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001ad1a  mov     esi, eax
0x18001ad1c  test    eax, eax
0x18001ad1e  jns     short loc_18001AD4E
0x18001ad20  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ad25  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001ad2a  mov     eax, esi
0x18001ad2c  mov     rcx, [rbp+0A10h+var_40]
0x18001ad33  xor     rcx, rsp; StackCookie
0x18001ad36  call    __security_check_cookie
0x18001ad3b  add     rsp, 0AE0h
0x18001ad42  pop     r15
0x18001ad44  pop     r14
0x18001ad46  pop     r12
0x18001ad48  pop     rdi
0x18001ad49  pop     rsi
0x18001ad4a  pop     rbx
0x18001ad4b  pop     rbp
0x18001ad4c  retn
0x18001ad4e  test    rbx, rbx
0x18001ad51  jz      short loc_18001AD72
0x18001ad53  jmp     short loc_18001AD6A
0x18001ad55  mov     r8, [rbx+8]; unsigned __int16 *
0x18001ad59  mov     rdx, rax; unsigned __int16 *
0x18001ad5c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ad61  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ad66  lea     rbx, [rbx+10h]
0x18001ad6a  mov     rax, [rbx]
0x18001ad6d  test    rax, rax
0x18001ad70  jnz     short loc_18001AD55
0x18001ad72  mov     rax, [r14]
0x18001ad75  lea     rdx, [rsp+0B10h+var_AD0]
0x18001ad7a  mov     rcx, r14
0x18001ad7d  mov     rax, [rax+28h]
0x18001ad81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad86  mov     ebx, eax
0x18001ad88  test    eax, eax
0x18001ad8a  js      loc_18001AECA
0x18001ad90  mov     [rsp+0B10h+var_AE0], r12
0x18001ad95  mov     rbx, cs:hModule
0x18001ad9c  mov     esi, 104h
0x18001ada1  mov     r8d, esi; nSize
0x18001ada4  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001ada8  mov     rcx, rbx; hModule
0x18001adab  call    cs:__imp_GetModuleFileNameW
0x18001adb2  nop     dword ptr [rax+rax+00h]
0x18001adb7  test    eax, eax
0x18001adb9  jnz     short loc_18001ADC7
0x18001adbb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001adc0  mov     ebx, eax
0x18001adc2  jmp     loc_18001AEC0
0x18001adc7  cmp     eax, esi
0x18001adc9  jnz     short loc_18001ADDF
0x18001adcb  lea     rcx, [rsp+0B10h+var_AE0]
0x18001add0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001add5  mov     ebx, 8007007Ah
0x18001adda  jmp     loc_18001AECA
0x18001addf  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001ade3  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001adea  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001adef  test    rbx, rbx
0x18001adf2  jz      short loc_18001AE10
0x18001adf4  xor     ecx, ecx; lpModuleName
0x18001adf6  call    cs:__imp_GetModuleHandleW
0x18001adfd  nop     dword ptr [rax+rax+00h]
0x18001ae02  cmp     rbx, rax
0x18001ae05  jz      short loc_18001AE10
0x18001ae07  lea     r8, [rbp+0A10h+var_450]
0x18001ae0e  jmp     short loc_18001AE8B
0x18001ae10  mov     ebx, 22h ; '"'
0x18001ae15  mov     [rbp+0A10h+var_870], bx
0x18001ae1c  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001ae23  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001ae2a  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001ae2f  test    al, al
0x18001ae31  jnz     short loc_18001AE47
0x18001ae33  lea     rcx, [rsp+0B10h+var_AE0]
0x18001ae38  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ae3d  mov     ebx, 80004005h
0x18001ae42  jmp     loc_18001AECA
0x18001ae47  lea     rcx, [rbp+0A10h+var_870]
0x18001ae4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ae52  inc     rax
0x18001ae55  cmp     [rcx+rax*2], r12w
0x18001ae5a  jnz     short loc_18001AE52
0x18001ae5c  cdqe
0x18001ae5e  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001ae66  lea     rcx, ds:2[rax*2]
0x18001ae6e  cmp     rcx, 418h
0x18001ae75  jnb     loc_18001AF2B
0x18001ae7b  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001ae84  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001ae8b  lea     rdx, aModule; "Module"
0x18001ae92  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ae97  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ae9c  mov     ebx, eax
0x18001ae9e  test    eax, eax
0x18001aea0  js      short loc_18001AEC0
0x18001aea2  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001aea9  lea     rdx, aModuleRaw; "Module_Raw"
0x18001aeb0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001aeb5  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001aeba  mov     ebx, eax
0x18001aebc  test    eax, eax
0x18001aebe  jns     short loc_18001AEDB
0x18001aec0  lea     rcx, [rsp+0B10h+var_AE0]
0x18001aec5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001aeca  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001aecf  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001aed4  mov     eax, ebx
0x18001aed6  jmp     loc_18001AD2C
0x18001aedb  mov     [rsp+0B10h+var_AD8], r12
0x18001aee0  test    r15d, r15d
0x18001aee3  jz      short loc_18001AEF4
0x18001aee5  test    rdi, rdi
0x18001aee8  jz      short loc_18001AF1A
0x18001aeea  mov     [rsp+0B10h+var_AF0], 1
0x18001aef2  jmp     short loc_18001AEFE
0x18001aef4  test    rdi, rdi
0x18001aef7  jz      short loc_18001AF1A
0x18001aef9  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001aefe  lea     r9, aRegistry; "REGISTRY"
0x18001af05  mov     r8, rdi; unsigned __int16 *
0x18001af08  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001af0c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001af11  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001af16  mov     ebx, eax
0x18001af18  jmp     short loc_18001AF1F
0x18001af1a  mov     ebx, 80070057h
0x18001af1f  lea     rcx, [rsp+0B10h+var_AD8]
0x18001af24  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001af29  jmp     short loc_18001AEC0
0x18001af2b  call    __report_rangecheckfailure
```
