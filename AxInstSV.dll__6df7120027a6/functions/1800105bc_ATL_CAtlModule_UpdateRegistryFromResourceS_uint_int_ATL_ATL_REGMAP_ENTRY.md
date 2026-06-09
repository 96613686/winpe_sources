# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800105bc`
- end: `0x18001082c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010ac0`

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
- `0x1800105bc`
- `0x1800110d0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010707`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010707`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800106c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800106c2`

## string_xrefs

- `0x1800107ef`: `REGISTRY`

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
    if ( ModuleFileNameW != 260 )
    {
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
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v28);
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
0x1800105bc  push    rbp
0x1800105be  push    rbx
0x1800105bf  push    rsi
0x1800105c0  push    rdi
0x1800105c1  push    r12
0x1800105c3  push    r14
0x1800105c5  push    r15
0x1800105c7  lea     rbp, [rsp-9E0h]
0x1800105cf  sub     rsp, 0AE0h
0x1800105d6  mov     rax, cs:__security_cookie
0x1800105dd  xor     rax, rsp
0x1800105e0  mov     [rbp+0A10h+var_40], rax
0x1800105e7  mov     rbx, r9
0x1800105ea  mov     r14d, r8d
0x1800105ed  mov     r15d, edx
0x1800105f0  mov     rsi, rcx
0x1800105f3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800105fa  mov     [rsp+0B10h+var_AD0], rax
0x1800105ff  xor     r12d, r12d
0x180010602  mov     [rsp+0B10h+var_AC8], r12
0x180010607  mov     [rsp+0B10h+var_AC0], r12
0x18001060c  mov     [rsp+0B10h+var_AB8], r12d
0x180010611  xorps   xmm0, xmm0
0x180010614  xor     eax, eax
0x180010616  movups  [rsp+0B10h+var_AB0], xmm0
0x18001061b  movups  [rsp+0B10h+var_AA0], xmm0
0x180010620  mov     [rbp+0A10h+var_A90], rax
0x180010624  mov     [rbp+0A10h+var_A88], r12b
0x180010628  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001062d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180010632  mov     edi, eax
0x180010634  test    eax, eax
0x180010636  jns     short loc_180010665
0x180010638  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001063d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180010642  mov     eax, edi
0x180010644  mov     rcx, [rbp+0A10h+var_40]
0x18001064b  xor     rcx, rsp; StackCookie
0x18001064e  call    __security_check_cookie
0x180010653  add     rsp, 0AE0h
0x18001065a  pop     r15
0x18001065c  pop     r14
0x18001065e  pop     r12
0x180010660  pop     rdi
0x180010661  pop     rsi
0x180010662  pop     rbx
0x180010663  pop     rbp
0x180010664  retn
0x180010665  test    rbx, rbx
0x180010668  jz      short loc_180010689
0x18001066a  jmp     short loc_180010681
0x18001066c  mov     r8, [rbx+8]; unsigned __int16 *
0x180010670  mov     rdx, rax; unsigned __int16 *
0x180010673  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010678  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001067d  lea     rbx, [rbx+10h]
0x180010681  mov     rax, [rbx]
0x180010684  test    rax, rax
0x180010687  jnz     short loc_18001066C
0x180010689  mov     rax, [rsi]
0x18001068c  lea     rdx, [rsp+0B10h+var_AD0]
0x180010691  mov     rcx, rsi
0x180010694  mov     rax, [rax+28h]
0x180010698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001069d  mov     ebx, eax
0x18001069f  test    eax, eax
0x1800106a1  js      loc_1800107D5
0x1800106a7  mov     [rsp+0B10h+var_AE0], r12
0x1800106ac  mov     rbx, cs:hModule
0x1800106b3  mov     edi, 104h
0x1800106b8  mov     r8d, edi; nSize
0x1800106bb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800106bf  mov     rcx, rbx; hModule
0x1800106c2  call    cs:__imp_GetModuleFileNameW
0x1800106c8  test    eax, eax
0x1800106ca  jnz     short loc_1800106D8
0x1800106cc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800106d1  mov     ebx, eax
0x1800106d3  jmp     loc_1800107CB
0x1800106d8  cmp     eax, edi
0x1800106da  jnz     short loc_1800106F0
0x1800106dc  lea     rcx, [rsp+0B10h+var_AE0]
0x1800106e1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800106e6  mov     ebx, 8007007Ah
0x1800106eb  jmp     loc_1800107D5
0x1800106f0  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800106f4  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800106fb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180010700  test    rbx, rbx
0x180010703  jz      short loc_18001071B
0x180010705  xor     ecx, ecx; lpModuleName
0x180010707  call    cs:__imp_GetModuleHandleW
0x18001070d  cmp     rbx, rax
0x180010710  jz      short loc_18001071B
0x180010712  lea     r8, [rbp+0A10h+var_450]
0x180010719  jmp     short loc_180010796
0x18001071b  mov     ebx, 22h ; '"'
0x180010720  mov     [rbp+0A10h+var_870], bx
0x180010727  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001072e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180010735  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001073a  test    al, al
0x18001073c  jnz     short loc_180010752
0x18001073e  lea     rcx, [rsp+0B10h+var_AE0]
0x180010743  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010748  mov     ebx, 80004005h
0x18001074d  jmp     loc_1800107D5
0x180010752  lea     rcx, [rbp+0A10h+var_870]
0x180010759  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001075d  inc     rax
0x180010760  cmp     [rcx+rax*2], r12w
0x180010765  jnz     short loc_18001075D
0x180010767  cdqe
0x180010769  mov     [rbp+rax*2+0A10h+var_870], bx
0x180010771  lea     rcx, ds:2[rax*2]
0x180010779  cmp     rcx, 418h
0x180010780  jnb     loc_180010826
0x180010786  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001078f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180010796  lea     rdx, aModule; "Module"
0x18001079d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800107a2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800107a7  mov     ebx, eax
0x1800107a9  test    eax, eax
0x1800107ab  js      short loc_1800107CB
0x1800107ad  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800107b4  lea     rdx, aModuleRaw; "Module_Raw"
0x1800107bb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800107c0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800107c5  mov     ebx, eax
0x1800107c7  test    eax, eax
0x1800107c9  jns     short loc_1800107E6
0x1800107cb  lea     rcx, [rsp+0B10h+var_AE0]
0x1800107d0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800107d5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800107da  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800107df  mov     eax, ebx
0x1800107e1  jmp     loc_180010644
0x1800107e6  movzx   r8d, r15w; unsigned __int16 *
0x1800107ea  mov     [rsp+0B10h+var_AD8], r12
0x1800107ef  lea     r9, aRegistry; "REGISTRY"
0x1800107f6  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800107fa  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800107ff  test    r14d, r14d
0x180010802  jz      short loc_18001080E
0x180010804  mov     [rsp+0B10h+var_AF0], 1
0x18001080c  jmp     short loc_180010813
0x18001080e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180010813  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180010818  mov     ebx, eax
0x18001081a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001081f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010824  jmp     short loc_1800107CB
0x180010826  call    __report_rangecheckfailure
```
