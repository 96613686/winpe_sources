# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800254dc`
- end: `0x180025753`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `631`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800259f0`

## callees

- `0x18001a8c0`
- `0x18001d8e0`
- `0x18001d930`
- `0x1800234bc`
- `0x180023594`
- `0x1800238f0`
- `0x1800240b4`
- `0x18002430c`
- `0x180024ba0`
- `0x1800254dc`
- `0x180025a0c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800255bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800255bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002560b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002560b`

## string_xrefs

- `0x1800256e0`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // eax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v17; // eax
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
  v8 = ATL::CComCriticalSection::Init(&v23);
  if ( v8 < 0 )
  {
    Error = v8;
    goto LABEL_29;
  }
  v24 = 1;
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
    v10 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147024774;
        goto LABEL_29;
      }
      ATL::CAtlModule::EscapeSingleQuote(v28, v12, Filename);
      if ( !v10 || v10 == GetModuleHandleW(0) )
      {
        v26 = 34;
        if ( !ocscpy_s(v27, v13, v28) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_29;
        }
        v15 = -1;
        do
          ++v15;
        while ( v27[v15 - 1] );
        v27[(int)v15 - 1] = 34;
        v16 = 2LL * (int)v15 + 2;
        if ( v16 >= 0x418 )
          _report_rangecheckfailure();
        *(unsigned __int16 *)((char *)&v27[-1] + v16) = 0;
        v14 = &v26;
      }
      else
      {
        v14 = v28;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v14);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v28);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v17;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  }
LABEL_29:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800254dc  mov     [rsp-8+arg_10], rbx
0x1800254e1  push    rbp
0x1800254e2  push    rsi
0x1800254e3  push    rdi
0x1800254e4  push    r14
0x1800254e6  push    r15
0x1800254e8  lea     rbp, [rsp-9E0h]
0x1800254f0  sub     rsp, 0AE0h
0x1800254f7  mov     rax, cs:__security_cookie
0x1800254fe  xor     rax, rsp
0x180025501  mov     [rbp+0A00h+var_30], rax
0x180025508  mov     rbx, r9
0x18002550b  mov     esi, r8d
0x18002550e  mov     r14d, edx
0x180025511  mov     rdi, rcx
0x180025514  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002551b  mov     [rsp+0B00h+var_AC0], rax
0x180025520  xor     r15d, r15d
0x180025523  mov     [rsp+0B00h+var_AB8], r15
0x180025528  mov     [rsp+0B00h+var_AB0], r15
0x18002552d  mov     [rsp+0B00h+var_AA8], r15d
0x180025532  xorps   xmm0, xmm0
0x180025535  xor     eax, eax
0x180025537  movups  [rsp+0B00h+var_AA0], xmm0
0x18002553c  movups  [rsp+0B00h+var_A90], xmm0
0x180025541  mov     [rbp+0A00h+var_A80], rax
0x180025545  mov     [rbp+0A00h+var_A78], r15b
0x180025549  lea     rcx, [rsp+0B00h+var_AA0]; this
0x18002554e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180025553  test    eax, eax
0x180025555  js      loc_18002571F
0x18002555b  mov     [rbp+0A00h+var_A78], 1
0x18002555f  test    rbx, rbx
0x180025562  jz      short loc_180025583
0x180025564  jmp     short loc_18002557B
0x180025566  mov     r8, [rbx+8]; unsigned __int16 *
0x18002556a  mov     rdx, rax; unsigned __int16 *
0x18002556d  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180025572  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180025577  lea     rbx, [rbx+10h]
0x18002557b  mov     rax, [rbx]
0x18002557e  test    rax, rax
0x180025581  jnz     short loc_180025566
0x180025583  mov     rax, [rdi]
0x180025586  lea     rdx, [rsp+0B00h+var_AC0]
0x18002558b  mov     rcx, rdi
0x18002558e  mov     rax, [rax+28h]
0x180025592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025597  mov     ebx, eax
0x180025599  test    eax, eax
0x18002559b  js      loc_180025721
0x1800255a1  mov     [rsp+0B00h+var_AD0], r15
0x1800255a6  mov     rbx, cs:hModule
0x1800255ad  mov     edi, 104h
0x1800255b2  mov     r8d, edi; nSize
0x1800255b5  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800255b9  mov     rcx, rbx; hModule
0x1800255bc  call    cs:__imp_GetModuleFileNameW
0x1800255c2  test    eax, eax
0x1800255c4  jnz     short loc_1800255DC
0x1800255c6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800255cb  mov     ebx, eax
0x1800255cd  lea     rcx, [rsp+0B00h+var_AD0]
0x1800255d2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800255d7  jmp     loc_180025721
0x1800255dc  cmp     eax, edi
0x1800255de  jnz     short loc_1800255F4
0x1800255e0  lea     rcx, [rsp+0B00h+var_AD0]
0x1800255e5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800255ea  mov     ebx, 8007007Ah
0x1800255ef  jmp     loc_180025721
0x1800255f4  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800255f8  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800255ff  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180025604  test    rbx, rbx
0x180025607  jz      short loc_18002561F
0x180025609  xor     ecx, ecx; lpModuleName
0x18002560b  call    cs:__imp_GetModuleHandleW
0x180025611  cmp     rbx, rax
0x180025614  jz      short loc_18002561F
0x180025616  lea     r8, [rbp+0A00h+var_440]
0x18002561d  jmp     short loc_18002569A
0x18002561f  mov     ebx, 22h ; '"'
0x180025624  mov     [rbp+0A00h+var_860], bx
0x18002562b  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x180025632  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x180025639  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18002563e  test    al, al
0x180025640  jnz     short loc_180025656
0x180025642  lea     rcx, [rsp+0B00h+var_AD0]
0x180025647  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002564c  mov     ebx, 80004005h
0x180025651  jmp     loc_180025721
0x180025656  lea     rcx, [rbp+0A00h+var_860]
0x18002565d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025661  inc     rax
0x180025664  cmp     [rcx+rax*2], r15w
0x180025669  jnz     short loc_180025661
0x18002566b  cdqe
0x18002566d  mov     [rbp+rax*2+0A00h+var_860], bx
0x180025675  lea     rcx, ds:2[rax*2]
0x18002567d  cmp     rcx, 418h
0x180025684  jnb     loc_180025719
0x18002568a  mov     [rbp+rcx+0A00h+var_860], r15w
0x180025693  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x18002569a  lea     rdx, aModule; "Module"
0x1800256a1  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800256a6  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800256ab  mov     ebx, eax
0x1800256ad  test    eax, eax
0x1800256af  js      loc_1800255CD
0x1800256b5  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800256bc  lea     rdx, aModuleRaw; "Module_Raw"
0x1800256c3  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800256c8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800256cd  mov     ebx, eax
0x1800256cf  test    eax, eax
0x1800256d1  js      loc_1800255CD
0x1800256d7  movzx   r8d, r14w; unsigned __int16 *
0x1800256db  mov     [rsp+0B00h+var_AC8], r15
0x1800256e0  lea     r9, aRegistry; "REGISTRY"
0x1800256e7  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800256eb  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800256f0  test    esi, esi
0x1800256f2  jz      short loc_1800256FE
0x1800256f4  mov     [rsp+0B00h+var_AE0], 1
0x1800256fc  jmp     short loc_180025703
0x1800256fe  mov     [rsp+0B00h+var_AE0], r15d; int
0x180025703  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180025708  mov     ebx, eax
0x18002570a  lea     rcx, [rsp+0B00h+var_AC8]
0x18002570f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180025714  jmp     loc_1800255CD
0x180025719  call    __report_rangecheckfailure
0x18002571f  mov     ebx, eax
0x180025721  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180025726  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002572b  mov     eax, ebx
0x18002572d  mov     rcx, [rbp+0A00h+var_30]
0x180025734  xor     rcx, rsp; StackCookie
0x180025737  call    __security_check_cookie
0x18002573c  mov     rbx, [rsp+0B00h+arg_10]
0x180025744  add     rsp, 0AE0h
0x18002574b  pop     r15
0x18002574d  pop     r14
0x18002574f  pop     rdi
0x180025750  pop     rsi
0x180025751  pop     rbp
0x180025752  retn
```
