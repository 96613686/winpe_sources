# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180019e50`
- end: `0x18001a0d4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `644`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180019d40`
- `0x180019d60`
- `0x180019d80`
- `0x180019da0`
- `0x180019dc0`
- `0x180019de0`
- `0x180019e00`
- `0x180019e20`
- `0x18001a390`

## callees

- `0x180006bd0`
- `0x1800126c4`
- `0x180013f48`
- `0x1800145d4`
- `0x180014ed0`
- `0x180015774`
- `0x180017574`
- `0x180018d1c`
- `0x180019e50`
- `0x18001a6f0`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019f5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019f5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019faa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019faa`

## string_xrefs

- `0x18001a097`: `REGISTRY`

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
          _report_rangecheckfailure(&v28);
        *(unsigned __int16 *)((char *)&v29[-1] + v17) = 0;
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
0x180019e50  push    rbp
0x180019e52  push    rbx
0x180019e53  push    rsi
0x180019e54  push    rdi
0x180019e55  push    r12
0x180019e57  push    r14
0x180019e59  push    r15
0x180019e5b  lea     rbp, [rsp-9F0h]
0x180019e63  sub     rsp, 0AF0h
0x180019e6a  mov     [rbp+0A20h+var_A90], 0FFFFFFFFFFFFFFFEh
0x180019e72  mov     rax, cs:__security_cookie
0x180019e79  xor     rax, rsp
0x180019e7c  mov     [rbp+0A20h+var_40], rax
0x180019e83  mov     rbx, r9
0x180019e86  mov     r14d, r8d
0x180019e89  mov     r15d, edx
0x180019e8c  mov     rsi, rcx
0x180019e8f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180019e96  mov     [rsp+0B20h+var_AE0], rax
0x180019e9b  xor     r12d, r12d
0x180019e9e  mov     [rsp+0B20h+var_AD8], r12
0x180019ea3  mov     [rsp+0B20h+var_AD0], r12
0x180019ea8  mov     [rsp+0B20h+var_AC8], r12d
0x180019ead  xorps   xmm0, xmm0
0x180019eb0  xor     eax, eax
0x180019eb2  movups  [rsp+0B20h+var_AC0], xmm0
0x180019eb7  movups  [rsp+0B20h+var_AB0], xmm0
0x180019ebc  mov     [rbp+0A20h+var_AA0], rax
0x180019ec0  mov     [rbp+0A20h+var_A98], r12b
0x180019ec4  lea     rcx, [rsp+0B20h+var_AC0]; this
0x180019ec9  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180019ece  mov     edi, eax
0x180019ed0  test    eax, eax
0x180019ed2  jns     short loc_180019F02
0x180019ed4  lea     rcx, [rsp+0B20h+var_AE0]; this
0x180019ed9  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180019ede  mov     eax, edi
0x180019ee0  mov     rcx, [rbp+0A20h+var_40]
0x180019ee7  xor     rcx, rsp; StackCookie
0x180019eea  call    __security_check_cookie
0x180019eef  add     rsp, 0AF0h
0x180019ef6  pop     r15
0x180019ef8  pop     r14
0x180019efa  pop     r12
0x180019efc  pop     rdi
0x180019efd  pop     rsi
0x180019efe  pop     rbx
0x180019eff  pop     rbp
0x180019f00  retn
0x180019f02  test    rbx, rbx
0x180019f05  jz      short loc_180019F26
0x180019f07  jmp     short loc_180019F1E
0x180019f09  mov     r8, [rbx+8]; unsigned __int16 *
0x180019f0d  mov     rdx, rax; unsigned __int16 *
0x180019f10  lea     rcx, [rsp+0B20h+var_AE0]; this
0x180019f15  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180019f1a  lea     rbx, [rbx+10h]
0x180019f1e  mov     rax, [rbx]
0x180019f21  test    rax, rax
0x180019f24  jnz     short loc_180019F09
0x180019f26  mov     rax, [rsi]
0x180019f29  lea     rdx, [rsp+0B20h+var_AE0]
0x180019f2e  mov     rcx, rsi
0x180019f31  mov     rax, [rax+28h]
0x180019f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f3a  mov     ebx, eax
0x180019f3c  test    eax, eax
0x180019f3e  js      loc_18001A07D
0x180019f44  mov     [rsp+0B20h+var_AF0], r12
0x180019f49  mov     rbx, cs:hModule
0x180019f50  mov     edi, 104h
0x180019f55  mov     r8d, edi; nSize
0x180019f58  lea     rdx, [rbp+0A20h+Filename]; lpFilename
0x180019f5c  mov     rcx, rbx; hModule
0x180019f5f  call    cs:__imp_GetModuleFileNameW
0x180019f66  nop     dword ptr [rax+rax+00h]
0x180019f6b  test    eax, eax
0x180019f6d  jnz     short loc_180019F7B
0x180019f6f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019f74  mov     ebx, eax
0x180019f76  jmp     loc_18001A073
0x180019f7b  cmp     eax, edi
0x180019f7d  jnz     short loc_180019F93
0x180019f7f  lea     rcx, [rsp+0B20h+var_AF0]
0x180019f84  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019f89  mov     ebx, 8007007Ah
0x180019f8e  jmp     loc_18001A07D
0x180019f93  lea     r8, [rbp+0A20h+Filename]; unsigned __int16 *
0x180019f97  lea     rcx, [rbp+0A20h+var_450]; unsigned __int16 *
0x180019f9e  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180019fa3  test    rbx, rbx
0x180019fa6  jz      short loc_180019FC4
0x180019fa8  xor     ecx, ecx; lpModuleName
0x180019faa  call    cs:__imp_GetModuleHandleW
0x180019fb1  nop     dword ptr [rax+rax+00h]
0x180019fb6  cmp     rbx, rax
0x180019fb9  jz      short loc_180019FC4
0x180019fbb  lea     r8, [rbp+0A20h+var_450]
0x180019fc2  jmp     short loc_18001A03E
0x180019fc4  mov     ebx, 22h ; '"'
0x180019fc9  mov     [rbp+0A20h+var_870], bx
0x180019fd0  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x180019fd7  lea     rcx, [rbp+0A20h+var_86E]; unsigned __int16 *
0x180019fde  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180019fe3  test    al, al
0x180019fe5  jnz     short loc_180019FFB
0x180019fe7  lea     rcx, [rsp+0B20h+var_AF0]
0x180019fec  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019ff1  mov     ebx, 80004005h
0x180019ff6  jmp     loc_18001A07D
0x180019ffb  lea     rcx, [rbp+0A20h+var_870]
0x18001a002  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a006  inc     rax
0x18001a009  cmp     [rcx+rax*2], r12w
0x18001a00e  jnz     short loc_18001A006
0x18001a010  cdqe
0x18001a012  mov     [rbp+rax*2+0A20h+var_870], bx
0x18001a01a  lea     rax, ds:2[rax*2]
0x18001a022  cmp     rax, 418h
0x18001a028  jnb     loc_18001A0CE
0x18001a02e  mov     [rbp+rax+0A20h+var_870], r12w
0x18001a037  lea     r8, [rbp+0A20h+var_870]; unsigned __int16 *
0x18001a03e  lea     rdx, aModule; "Module"
0x18001a045  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a04a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a04f  mov     ebx, eax
0x18001a051  test    eax, eax
0x18001a053  js      short loc_18001A073
0x18001a055  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001a05c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001a063  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a068  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a06d  mov     ebx, eax
0x18001a06f  test    eax, eax
0x18001a071  jns     short loc_18001A08E
0x18001a073  lea     rcx, [rsp+0B20h+var_AF0]
0x18001a078  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a07d  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a082  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a087  mov     eax, ebx
0x18001a089  jmp     loc_180019EE0
0x18001a08e  movzx   r8d, r15w; unsigned __int16 *
0x18001a092  mov     [rsp+0B20h+var_AE8], r12
0x18001a097  lea     r9, aRegistry; "REGISTRY"
0x18001a09e  lea     rdx, [rbp+0A20h+Filename]; unsigned __int16 *
0x18001a0a2  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001a0a7  test    r14d, r14d
0x18001a0aa  jz      short loc_18001A0B6
0x18001a0ac  mov     [rsp+0B20h+var_B00], 1
0x18001a0b4  jmp     short loc_18001A0BB
0x18001a0b6  mov     [rsp+0B20h+var_B00], r12d; int
0x18001a0bb  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001a0c0  mov     ebx, eax
0x18001a0c2  lea     rcx, [rsp+0B20h+var_AE8]
0x18001a0c7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a0cc  jmp     short loc_18001A073
0x18001a0ce  call    __report_rangecheckfailure
```
