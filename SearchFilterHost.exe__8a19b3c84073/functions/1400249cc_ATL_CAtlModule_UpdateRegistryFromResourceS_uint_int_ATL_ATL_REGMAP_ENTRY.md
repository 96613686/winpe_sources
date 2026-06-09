# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1400249cc`
- end: `0x140024c44`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `632`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140024ee0`

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
- `0x1400249cc`
- `0x140026a94`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140024ada`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140024ada`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024b1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024b1f`

## string_xrefs

- `0x140024c07`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
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
    if ( ModuleFileNameW != 260 )
    {
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
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v30);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const wchar_t *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const wchar_t *)a2,
                    L"REGISTRY",
                    0);
          Error = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1400249cc  push    rbp
0x1400249ce  push    rbx
0x1400249cf  push    rsi
0x1400249d0  push    rdi
0x1400249d1  push    r12
0x1400249d3  push    r14
0x1400249d5  push    r15
0x1400249d7  lea     rbp, [rsp-9F0h]
0x1400249df  sub     rsp, 0AF0h
0x1400249e6  mov     [rbp+0A20h+var_A90], 0FFFFFFFFFFFFFFFEh
0x1400249ee  mov     rax, cs:__security_cookie
0x1400249f5  xor     rax, rsp
0x1400249f8  mov     [rbp+0A20h+var_40], rax
0x1400249ff  mov     rbx, r9
0x140024a02  mov     r14d, r8d
0x140024a05  mov     r15d, edx
0x140024a08  mov     rsi, rcx
0x140024a0b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140024a12  mov     [rsp+0B20h+var_AE0], rax
0x140024a17  xor     r12d, r12d
0x140024a1a  mov     [rsp+0B20h+var_AD8], r12
0x140024a1f  mov     [rsp+0B20h+var_AD0], r12
0x140024a24  mov     [rsp+0B20h+var_AC8], r12d
0x140024a29  xorps   xmm0, xmm0
0x140024a2c  xor     eax, eax
0x140024a2e  movups  [rsp+0B20h+var_AC0], xmm0
0x140024a33  movups  [rsp+0B20h+var_AB0], xmm0
0x140024a38  mov     [rbp+0A20h+var_AA0], rax
0x140024a3c  mov     [rbp+0A20h+var_A98], r12b
0x140024a40  lea     rcx, [rsp+0B20h+var_AC0]; this
0x140024a45  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x140024a4a  mov     edi, eax
0x140024a4c  test    eax, eax
0x140024a4e  jns     short loc_140024A7D
0x140024a50  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024a55  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140024a5a  mov     eax, edi
0x140024a5c  mov     rcx, [rbp+0A20h+var_40]
0x140024a63  xor     rcx, rsp; StackCookie
0x140024a66  call    __security_check_cookie
0x140024a6b  add     rsp, 0AF0h
0x140024a72  pop     r15
0x140024a74  pop     r14
0x140024a76  pop     r12
0x140024a78  pop     rdi
0x140024a79  pop     rsi
0x140024a7a  pop     rbx
0x140024a7b  pop     rbp
0x140024a7c  retn
0x140024a7d  test    rbx, rbx
0x140024a80  jz      short loc_140024AA1
0x140024a82  jmp     short loc_140024A99
0x140024a84  mov     r8, [rbx+8]; wchar_t *
0x140024a88  mov     rdx, rax; wchar_t *
0x140024a8b  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024a90  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140024a95  lea     rbx, [rbx+10h]
0x140024a99  mov     rax, [rbx]
0x140024a9c  test    rax, rax
0x140024a9f  jnz     short loc_140024A84
0x140024aa1  mov     rax, [rsi]
0x140024aa4  lea     rdx, [rsp+0B20h+var_AE0]
0x140024aa9  mov     rcx, rsi
0x140024aac  mov     rax, [rax+28h]
0x140024ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024ab5  mov     ebx, eax
0x140024ab7  test    eax, eax
0x140024ab9  js      loc_140024BED
0x140024abf  mov     [rsp+0B20h+var_AF0], r12
0x140024ac4  mov     rbx, cs:hModule
0x140024acb  mov     edi, 104h
0x140024ad0  mov     r8d, edi; nSize
0x140024ad3  lea     rdx, [rbp+0A20h+Filename]; lpFilename
0x140024ad7  mov     rcx, rbx; hModule
0x140024ada  call    cs:__imp_GetModuleFileNameW
0x140024ae0  test    eax, eax
0x140024ae2  jnz     short loc_140024AF0
0x140024ae4  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140024ae9  mov     ebx, eax
0x140024aeb  jmp     loc_140024BE3
0x140024af0  cmp     eax, edi
0x140024af2  jnz     short loc_140024B08
0x140024af4  lea     rcx, [rsp+0B20h+var_AF0]
0x140024af9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024afe  mov     ebx, 8007007Ah
0x140024b03  jmp     loc_140024BED
0x140024b08  lea     r8, [rbp+0A20h+Filename]; wchar_t *
0x140024b0c  lea     rcx, [rbp+0A20h+var_450]; wchar_t *
0x140024b13  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x140024b18  test    rbx, rbx
0x140024b1b  jz      short loc_140024B33
0x140024b1d  xor     ecx, ecx; lpModuleName
0x140024b1f  call    cs:__imp_GetModuleHandleW
0x140024b25  cmp     rbx, rax
0x140024b28  jz      short loc_140024B33
0x140024b2a  lea     r8, [rbp+0A20h+var_450]
0x140024b31  jmp     short loc_140024BAE
0x140024b33  mov     ebx, 22h ; '"'
0x140024b38  mov     [rbp+0A20h+var_870], bx
0x140024b3f  lea     r8, [rbp+0A20h+var_450]; wchar_t *
0x140024b46  lea     rcx, [rbp+0A20h+var_86E]; wchar_t *
0x140024b4d  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x140024b52  test    al, al
0x140024b54  jnz     short loc_140024B6A
0x140024b56  lea     rcx, [rsp+0B20h+var_AF0]
0x140024b5b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024b60  mov     ebx, 80004005h
0x140024b65  jmp     loc_140024BED
0x140024b6a  lea     rcx, [rbp+0A20h+var_870]
0x140024b71  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024b75  inc     rax
0x140024b78  cmp     [rcx+rax*2], r12w
0x140024b7d  jnz     short loc_140024B75
0x140024b7f  cdqe
0x140024b81  mov     [rbp+rax*2+0A20h+var_870], bx
0x140024b89  lea     rcx, ds:2[rax*2]
0x140024b91  cmp     rcx, 418h
0x140024b98  jnb     loc_140024C3E
0x140024b9e  mov     [rbp+rcx+0A20h+var_870], r12w
0x140024ba7  lea     r8, [rbp+0A20h+var_870]; wchar_t *
0x140024bae  lea     rdx, aModule_0; "Module"
0x140024bb5  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024bba  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140024bbf  mov     ebx, eax
0x140024bc1  test    eax, eax
0x140024bc3  js      short loc_140024BE3
0x140024bc5  lea     r8, [rbp+0A20h+var_450]; wchar_t *
0x140024bcc  lea     rdx, aModuleRaw; "Module_Raw"
0x140024bd3  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024bd8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x140024bdd  mov     ebx, eax
0x140024bdf  test    eax, eax
0x140024be1  jns     short loc_140024BFE
0x140024be3  lea     rcx, [rsp+0B20h+var_AF0]
0x140024be8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024bed  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024bf2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140024bf7  mov     eax, ebx
0x140024bf9  jmp     loc_140024A5C
0x140024bfe  movzx   r8d, r15w; wchar_t *
0x140024c02  mov     [rsp+0B20h+var_AE8], r12
0x140024c07  lea     r9, aRegistry; "REGISTRY"
0x140024c0e  lea     rdx, [rbp+0A20h+Filename]; wchar_t *
0x140024c12  lea     rcx, [rsp+0B20h+var_AE0]; this
0x140024c17  test    r14d, r14d
0x140024c1a  jz      short loc_140024C26
0x140024c1c  mov     [rsp+0B20h+var_B00], 1
0x140024c24  jmp     short loc_140024C2B
0x140024c26  mov     [rsp+0B20h+var_B00], r12d; int
0x140024c2b  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x140024c30  mov     ebx, eax
0x140024c32  lea     rcx, [rsp+0B20h+var_AE8]
0x140024c37  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140024c3c  jmp     short loc_140024BE3
0x140024c3e  call    __report_rangecheckfailure
```
