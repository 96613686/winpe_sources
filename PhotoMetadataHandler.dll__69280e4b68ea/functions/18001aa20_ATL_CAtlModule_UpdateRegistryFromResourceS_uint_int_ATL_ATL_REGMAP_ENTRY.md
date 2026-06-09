# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001aa20`
- end: `0x18001ac9d`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `637`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001af40`

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
- `0x18001aa20`
- `0x18001af78`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ab27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ab27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ab72`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ab72`

## string_xrefs

- `0x18001ac60`: `REGISTRY`

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
0x18001aa20  push    rbp
0x18001aa22  push    rbx
0x18001aa23  push    rsi
0x18001aa24  push    rdi
0x18001aa25  push    r12
0x18001aa27  push    r14
0x18001aa29  push    r15
0x18001aa2b  lea     rbp, [rsp-9E0h]
0x18001aa33  sub     rsp, 0AE0h
0x18001aa3a  mov     rax, cs:__security_cookie
0x18001aa41  xor     rax, rsp
0x18001aa44  mov     [rbp+0A10h+var_40], rax
0x18001aa4b  mov     rbx, r9
0x18001aa4e  mov     r14d, r8d
0x18001aa51  mov     r15d, edx
0x18001aa54  mov     rsi, rcx
0x18001aa57  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001aa5e  mov     [rsp+0B10h+var_AD0], rax
0x18001aa63  xor     r12d, r12d
0x18001aa66  mov     [rsp+0B10h+var_AC8], r12
0x18001aa6b  mov     [rsp+0B10h+var_AC0], r12
0x18001aa70  mov     [rsp+0B10h+var_AB8], r12d
0x18001aa75  xorps   xmm0, xmm0
0x18001aa78  xor     eax, eax
0x18001aa7a  movups  [rsp+0B10h+var_AB0], xmm0
0x18001aa7f  movups  [rsp+0B10h+var_AA0], xmm0
0x18001aa84  mov     [rbp+0A10h+var_A90], rax
0x18001aa88  mov     [rbp+0A10h+var_A88], r12b
0x18001aa8c  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001aa91  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001aa96  mov     edi, eax
0x18001aa98  test    eax, eax
0x18001aa9a  jns     short loc_18001AACA
0x18001aa9c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001aaa1  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001aaa6  mov     eax, edi
0x18001aaa8  mov     rcx, [rbp+0A10h+var_40]
0x18001aaaf  xor     rcx, rsp; StackCookie
0x18001aab2  call    __security_check_cookie
0x18001aab7  add     rsp, 0AE0h
0x18001aabe  pop     r15
0x18001aac0  pop     r14
0x18001aac2  pop     r12
0x18001aac4  pop     rdi
0x18001aac5  pop     rsi
0x18001aac6  pop     rbx
0x18001aac7  pop     rbp
0x18001aac8  retn
0x18001aaca  test    rbx, rbx
0x18001aacd  jz      short loc_18001AAEE
0x18001aacf  jmp     short loc_18001AAE6
0x18001aad1  mov     r8, [rbx+8]; unsigned __int16 *
0x18001aad5  mov     rdx, rax; unsigned __int16 *
0x18001aad8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001aadd  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001aae2  lea     rbx, [rbx+10h]
0x18001aae6  mov     rax, [rbx]
0x18001aae9  test    rax, rax
0x18001aaec  jnz     short loc_18001AAD1
0x18001aaee  mov     rax, [rsi]
0x18001aaf1  lea     rdx, [rsp+0B10h+var_AD0]
0x18001aaf6  mov     rcx, rsi
0x18001aaf9  mov     rax, [rax+28h]
0x18001aafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab02  mov     ebx, eax
0x18001ab04  test    eax, eax
0x18001ab06  js      loc_18001AC46
0x18001ab0c  mov     [rsp+0B10h+var_AE0], r12
0x18001ab11  mov     rbx, cs:hModule
0x18001ab18  mov     edi, 104h
0x18001ab1d  mov     r8d, edi; nSize
0x18001ab20  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001ab24  mov     rcx, rbx; hModule
0x18001ab27  call    cs:__imp_GetModuleFileNameW
0x18001ab2e  nop     dword ptr [rax+rax+00h]
0x18001ab33  test    eax, eax
0x18001ab35  jnz     short loc_18001AB43
0x18001ab37  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ab3c  mov     ebx, eax
0x18001ab3e  jmp     loc_18001AC3C
0x18001ab43  cmp     eax, edi
0x18001ab45  jnz     short loc_18001AB5B
0x18001ab47  lea     rcx, [rsp+0B10h+var_AE0]
0x18001ab4c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ab51  mov     ebx, 8007007Ah
0x18001ab56  jmp     loc_18001AC46
0x18001ab5b  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001ab5f  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001ab66  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001ab6b  test    rbx, rbx
0x18001ab6e  jz      short loc_18001AB8C
0x18001ab70  xor     ecx, ecx; lpModuleName
0x18001ab72  call    cs:__imp_GetModuleHandleW
0x18001ab79  nop     dword ptr [rax+rax+00h]
0x18001ab7e  cmp     rbx, rax
0x18001ab81  jz      short loc_18001AB8C
0x18001ab83  lea     r8, [rbp+0A10h+var_450]
0x18001ab8a  jmp     short loc_18001AC07
0x18001ab8c  mov     ebx, 22h ; '"'
0x18001ab91  mov     [rbp+0A10h+var_870], bx
0x18001ab98  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001ab9f  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001aba6  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001abab  test    al, al
0x18001abad  jnz     short loc_18001ABC3
0x18001abaf  lea     rcx, [rsp+0B10h+var_AE0]
0x18001abb4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001abb9  mov     ebx, 80004005h
0x18001abbe  jmp     loc_18001AC46
0x18001abc3  lea     rcx, [rbp+0A10h+var_870]
0x18001abca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001abce  inc     rax
0x18001abd1  cmp     [rcx+rax*2], r12w
0x18001abd6  jnz     short loc_18001ABCE
0x18001abd8  cdqe
0x18001abda  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001abe2  lea     rcx, ds:2[rax*2]
0x18001abea  cmp     rcx, 418h
0x18001abf1  jnb     loc_18001AC97
0x18001abf7  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001ac00  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001ac07  lea     rdx, aModule; "Module"
0x18001ac0e  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ac13  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ac18  mov     ebx, eax
0x18001ac1a  test    eax, eax
0x18001ac1c  js      short loc_18001AC3C
0x18001ac1e  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001ac25  lea     rdx, aModuleRaw; "Module_Raw"
0x18001ac2c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ac31  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ac36  mov     ebx, eax
0x18001ac38  test    eax, eax
0x18001ac3a  jns     short loc_18001AC57
0x18001ac3c  lea     rcx, [rsp+0B10h+var_AE0]
0x18001ac41  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ac46  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ac4b  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001ac50  mov     eax, ebx
0x18001ac52  jmp     loc_18001AAA8
0x18001ac57  movzx   r8d, r15w; unsigned __int16 *
0x18001ac5b  mov     [rsp+0B10h+var_AD8], r12
0x18001ac60  lea     r9, aRegistry; "REGISTRY"
0x18001ac67  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001ac6b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ac70  test    r14d, r14d
0x18001ac73  jz      short loc_18001AC7F
0x18001ac75  mov     [rsp+0B10h+var_AF0], 1
0x18001ac7d  jmp     short loc_18001AC84
0x18001ac7f  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001ac84  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001ac89  mov     ebx, eax
0x18001ac8b  lea     rcx, [rsp+0B10h+var_AD8]
0x18001ac90  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ac95  jmp     short loc_18001AC3C
0x18001ac97  call    __report_rangecheckfailure
```
