# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180019e1c`
- end: `0x18001a08c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a320`

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
- `0x180019e1c`
- `0x18001a33c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019f22`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019f22`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019f67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019f67`

## string_xrefs

- `0x18001a04f`: `REGISTRY`

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
    if ( ModuleFileNameW != 260 )
    {
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
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
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
0x180019e1c  push    rbp
0x180019e1e  push    rbx
0x180019e1f  push    rsi
0x180019e20  push    rdi
0x180019e21  push    r12
0x180019e23  push    r14
0x180019e25  push    r15
0x180019e27  lea     rbp, [rsp-9E0h]
0x180019e2f  sub     rsp, 0AE0h
0x180019e36  mov     rax, cs:__security_cookie
0x180019e3d  xor     rax, rsp
0x180019e40  mov     [rbp+0A10h+var_40], rax
0x180019e47  mov     rbx, r9
0x180019e4a  mov     r14d, r8d
0x180019e4d  mov     r15d, edx
0x180019e50  mov     rsi, rcx
0x180019e53  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180019e5a  mov     [rsp+0B10h+var_AD0], rax
0x180019e5f  xor     r12d, r12d
0x180019e62  mov     [rsp+0B10h+var_AC8], r12
0x180019e67  mov     [rsp+0B10h+var_AC0], r12
0x180019e6c  mov     [rsp+0B10h+var_AB8], r12d
0x180019e71  xorps   xmm0, xmm0
0x180019e74  xor     eax, eax
0x180019e76  movups  [rsp+0B10h+var_AB0], xmm0
0x180019e7b  movups  [rsp+0B10h+var_AA0], xmm0
0x180019e80  mov     [rbp+0A10h+var_A90], rax
0x180019e84  mov     [rbp+0A10h+var_A88], r12b
0x180019e88  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180019e8d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180019e92  mov     edi, eax
0x180019e94  test    eax, eax
0x180019e96  jns     short loc_180019EC5
0x180019e98  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180019e9d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180019ea2  mov     eax, edi
0x180019ea4  mov     rcx, [rbp+0A10h+var_40]
0x180019eab  xor     rcx, rsp; StackCookie
0x180019eae  call    __security_check_cookie
0x180019eb3  add     rsp, 0AE0h
0x180019eba  pop     r15
0x180019ebc  pop     r14
0x180019ebe  pop     r12
0x180019ec0  pop     rdi
0x180019ec1  pop     rsi
0x180019ec2  pop     rbx
0x180019ec3  pop     rbp
0x180019ec4  retn
0x180019ec5  test    rbx, rbx
0x180019ec8  jz      short loc_180019EE9
0x180019eca  jmp     short loc_180019EE1
0x180019ecc  mov     r8, [rbx+8]; unsigned __int16 *
0x180019ed0  mov     rdx, rax; unsigned __int16 *
0x180019ed3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180019ed8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180019edd  lea     rbx, [rbx+10h]
0x180019ee1  mov     rax, [rbx]
0x180019ee4  test    rax, rax
0x180019ee7  jnz     short loc_180019ECC
0x180019ee9  mov     rax, [rsi]
0x180019eec  lea     rdx, [rsp+0B10h+var_AD0]
0x180019ef1  mov     rcx, rsi
0x180019ef4  mov     rax, [rax+28h]
0x180019ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019efd  mov     ebx, eax
0x180019eff  test    eax, eax
0x180019f01  js      loc_18001A035
0x180019f07  mov     [rsp+0B10h+var_AE0], r12
0x180019f0c  mov     rbx, cs:hModule
0x180019f13  mov     edi, 104h
0x180019f18  mov     r8d, edi; nSize
0x180019f1b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180019f1f  mov     rcx, rbx; hModule
0x180019f22  call    cs:__imp_GetModuleFileNameW
0x180019f28  test    eax, eax
0x180019f2a  jnz     short loc_180019F38
0x180019f2c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019f31  mov     ebx, eax
0x180019f33  jmp     loc_18001A02B
0x180019f38  cmp     eax, edi
0x180019f3a  jnz     short loc_180019F50
0x180019f3c  lea     rcx, [rsp+0B10h+var_AE0]
0x180019f41  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019f46  mov     ebx, 8007007Ah
0x180019f4b  jmp     loc_18001A035
0x180019f50  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180019f54  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180019f5b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180019f60  test    rbx, rbx
0x180019f63  jz      short loc_180019F7B
0x180019f65  xor     ecx, ecx; lpModuleName
0x180019f67  call    cs:__imp_GetModuleHandleW
0x180019f6d  cmp     rbx, rax
0x180019f70  jz      short loc_180019F7B
0x180019f72  lea     r8, [rbp+0A10h+var_450]
0x180019f79  jmp     short loc_180019FF6
0x180019f7b  mov     ebx, 22h ; '"'
0x180019f80  mov     [rbp+0A10h+var_870], bx
0x180019f87  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180019f8e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180019f95  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180019f9a  test    al, al
0x180019f9c  jnz     short loc_180019FB2
0x180019f9e  lea     rcx, [rsp+0B10h+var_AE0]
0x180019fa3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019fa8  mov     ebx, 80004005h
0x180019fad  jmp     loc_18001A035
0x180019fb2  lea     rcx, [rbp+0A10h+var_870]
0x180019fb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019fbd  inc     rax
0x180019fc0  cmp     [rcx+rax*2], r12w
0x180019fc5  jnz     short loc_180019FBD
0x180019fc7  cdqe
0x180019fc9  mov     [rbp+rax*2+0A10h+var_870], bx
0x180019fd1  lea     rcx, ds:2[rax*2]
0x180019fd9  cmp     rcx, 418h
0x180019fe0  jnb     loc_18001A086
0x180019fe6  mov     [rbp+rcx+0A10h+var_870], r12w
0x180019fef  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180019ff6  lea     rdx, aModule; "Module"
0x180019ffd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a002  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a007  mov     ebx, eax
0x18001a009  test    eax, eax
0x18001a00b  js      short loc_18001A02B
0x18001a00d  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a014  lea     rdx, aModuleRaw; "Module_Raw"
0x18001a01b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a020  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a025  mov     ebx, eax
0x18001a027  test    eax, eax
0x18001a029  jns     short loc_18001A046
0x18001a02b  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a030  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a035  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a03a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a03f  mov     eax, ebx
0x18001a041  jmp     loc_180019EA4
0x18001a046  movzx   r8d, r15w; unsigned __int16 *
0x18001a04a  mov     [rsp+0B10h+var_AD8], r12
0x18001a04f  lea     r9, aRegistry; "REGISTRY"
0x18001a056  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001a05a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a05f  test    r14d, r14d
0x18001a062  jz      short loc_18001A06E
0x18001a064  mov     [rsp+0B10h+var_AF0], 1
0x18001a06c  jmp     short loc_18001A073
0x18001a06e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001a073  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001a078  mov     ebx, eax
0x18001a07a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001a07f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a084  jmp     short loc_18001A02B
0x18001a086  call    __report_rangecheckfailure
```
