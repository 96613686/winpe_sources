# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18002575c`
- end: `0x1800259e4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `648`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180025a00`

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
- `0x18002575c`
- `0x180025a0c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002583c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002583c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002588b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002588b`

## string_xrefs

- `0x18002597a`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
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
    goto LABEL_33;
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
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_9:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_33;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_33;
    }
    ATL::CAtlModule::EscapeSingleQuote(v28, v12, Filename);
    if ( !v10 || v10 == GetModuleHandleW(0) )
    {
      v26 = 34;
      if ( !ocscpy_s(v27, v13, v28) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_33;
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
    if ( Error < 0 )
      goto LABEL_9;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v28);
    if ( Error < 0 )
      goto LABEL_9;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_28:
        Error = v17;
LABEL_30:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_9;
      }
    }
    else if ( a2 )
    {
      v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_28;
    }
    Error = -2147024809;
    goto LABEL_30;
  }
LABEL_33:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002575c  mov     [rsp-8+arg_10], rbx
0x180025761  push    rbp
0x180025762  push    rsi
0x180025763  push    rdi
0x180025764  push    r14
0x180025766  push    r15
0x180025768  lea     rbp, [rsp-9E0h]
0x180025770  sub     rsp, 0AE0h
0x180025777  mov     rax, cs:__security_cookie
0x18002577e  xor     rax, rsp
0x180025781  mov     [rbp+0A00h+var_30], rax
0x180025788  mov     rbx, r9
0x18002578b  mov     r14d, r8d
0x18002578e  mov     rdi, rdx
0x180025791  mov     rsi, rcx
0x180025794  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002579b  mov     [rsp+0B00h+var_AC0], rax
0x1800257a0  xor     r15d, r15d
0x1800257a3  mov     [rsp+0B00h+var_AB8], r15
0x1800257a8  mov     [rsp+0B00h+var_AB0], r15
0x1800257ad  mov     [rsp+0B00h+var_AA8], r15d
0x1800257b2  xorps   xmm0, xmm0
0x1800257b5  xor     eax, eax
0x1800257b7  movups  [rsp+0B00h+var_AA0], xmm0
0x1800257bc  movups  [rsp+0B00h+var_A90], xmm0
0x1800257c1  mov     [rbp+0A00h+var_A80], rax
0x1800257c5  mov     [rbp+0A00h+var_A78], r15b
0x1800257c9  lea     rcx, [rsp+0B00h+var_AA0]; this
0x1800257ce  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800257d3  test    eax, eax
0x1800257d5  js      loc_1800259B0
0x1800257db  mov     [rbp+0A00h+var_A78], 1
0x1800257df  test    rbx, rbx
0x1800257e2  jz      short loc_180025803
0x1800257e4  jmp     short loc_1800257FB
0x1800257e6  mov     r8, [rbx+8]; unsigned __int16 *
0x1800257ea  mov     rdx, rax; unsigned __int16 *
0x1800257ed  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800257f2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800257f7  lea     rbx, [rbx+10h]
0x1800257fb  mov     rax, [rbx]
0x1800257fe  test    rax, rax
0x180025801  jnz     short loc_1800257E6
0x180025803  mov     rax, [rsi]
0x180025806  lea     rdx, [rsp+0B00h+var_AC0]
0x18002580b  mov     rcx, rsi
0x18002580e  mov     rax, [rax+28h]
0x180025812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025817  mov     ebx, eax
0x180025819  test    eax, eax
0x18002581b  js      loc_1800259B2
0x180025821  mov     [rsp+0B00h+var_AD0], r15
0x180025826  mov     rbx, cs:hModule
0x18002582d  mov     esi, 104h
0x180025832  mov     r8d, esi; nSize
0x180025835  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180025839  mov     rcx, rbx; hModule
0x18002583c  call    cs:__imp_GetModuleFileNameW
0x180025842  test    eax, eax
0x180025844  jnz     short loc_18002585C
0x180025846  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002584b  mov     ebx, eax
0x18002584d  lea     rcx, [rsp+0B00h+var_AD0]
0x180025852  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180025857  jmp     loc_1800259B2
0x18002585c  cmp     eax, esi
0x18002585e  jnz     short loc_180025874
0x180025860  lea     rcx, [rsp+0B00h+var_AD0]
0x180025865  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002586a  mov     ebx, 8007007Ah
0x18002586f  jmp     loc_1800259B2
0x180025874  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x180025878  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x18002587f  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180025884  test    rbx, rbx
0x180025887  jz      short loc_18002589F
0x180025889  xor     ecx, ecx; lpModuleName
0x18002588b  call    cs:__imp_GetModuleHandleW
0x180025891  cmp     rbx, rax
0x180025894  jz      short loc_18002589F
0x180025896  lea     r8, [rbp+0A00h+var_440]
0x18002589d  jmp     short loc_18002591A
0x18002589f  mov     ebx, 22h ; '"'
0x1800258a4  mov     [rbp+0A00h+var_860], bx
0x1800258ab  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800258b2  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x1800258b9  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800258be  test    al, al
0x1800258c0  jnz     short loc_1800258D6
0x1800258c2  lea     rcx, [rsp+0B00h+var_AD0]
0x1800258c7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800258cc  mov     ebx, 80004005h
0x1800258d1  jmp     loc_1800259B2
0x1800258d6  lea     rcx, [rbp+0A00h+var_860]
0x1800258dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800258e1  inc     rax
0x1800258e4  cmp     [rcx+rax*2], r15w
0x1800258e9  jnz     short loc_1800258E1
0x1800258eb  cdqe
0x1800258ed  mov     [rbp+rax*2+0A00h+var_860], bx
0x1800258f5  lea     rcx, ds:2[rax*2]
0x1800258fd  cmp     rcx, 418h
0x180025904  jnb     loc_1800259AA
0x18002590a  mov     [rbp+rcx+0A00h+var_860], r15w
0x180025913  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x18002591a  lea     rdx, aModule; "Module"
0x180025921  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180025926  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002592b  mov     ebx, eax
0x18002592d  test    eax, eax
0x18002592f  js      loc_18002584D
0x180025935  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x18002593c  lea     rdx, aModuleRaw; "Module_Raw"
0x180025943  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180025948  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002594d  mov     ebx, eax
0x18002594f  test    eax, eax
0x180025951  js      loc_18002584D
0x180025957  mov     [rsp+0B00h+var_AC8], r15
0x18002595c  test    r14d, r14d
0x18002595f  jz      short loc_180025970
0x180025961  test    rdi, rdi
0x180025964  jz      short loc_180025996
0x180025966  mov     [rsp+0B00h+var_AE0], 1
0x18002596e  jmp     short loc_18002597A
0x180025970  test    rdi, rdi
0x180025973  jz      short loc_180025996
0x180025975  mov     [rsp+0B00h+var_AE0], r15d; int
0x18002597a  lea     r9, aRegistry; "REGISTRY"
0x180025981  mov     r8, rdi; unsigned __int16 *
0x180025984  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180025988  lea     rcx, [rsp+0B00h+var_AC0]; this
0x18002598d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180025992  mov     ebx, eax
0x180025994  jmp     short loc_18002599B
0x180025996  mov     ebx, 80070057h
0x18002599b  lea     rcx, [rsp+0B00h+var_AC8]
0x1800259a0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800259a5  jmp     loc_18002584D
0x1800259aa  call    __report_rangecheckfailure
0x1800259b0  mov     ebx, eax
0x1800259b2  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800259b7  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800259bc  mov     eax, ebx
0x1800259be  mov     rcx, [rbp+0A00h+var_30]
0x1800259c5  xor     rcx, rsp; StackCookie
0x1800259c8  call    __security_check_cookie
0x1800259cd  mov     rbx, [rsp+0B00h+arg_10]
0x1800259d5  add     rsp, 0AE0h
0x1800259dc  pop     r15
0x1800259de  pop     r14
0x1800259e0  pop     rdi
0x1800259e1  pop     rsi
0x1800259e2  pop     rbp
0x1800259e3  retn
```
