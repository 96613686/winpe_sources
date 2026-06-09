# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001a31c`
- end: `0x18001a564`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `584`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001a7d0`

## callees

- `0x180002bf8`
- `0x180017324`
- `0x180017530`
- `0x180017648`
- `0x180017b10`
- `0x1800180ec`
- `0x1800183d0`
- `0x180018ba4`
- `0x180019688`
- `0x18001a31c`
- `0x18001a920`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a43f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a43f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a3fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001a3fa`

## string_xrefs

- `0x18001a522`: `REGISTRY`

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
  _BYTE v21[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[48]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v25[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v26[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  ATL::CRegObject::CRegObject((ATL::CRegObject *)v21);
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v22);
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
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _BYTE *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v11 = hModule;
    v19 = 0;
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
      ATL::CAtlModule::EscapeSingleQuote(v26, v13, Filename);
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v24 = 34;
        if ( !ocscpy_s(v25, v14, v26) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_24;
        }
        v16 = -1;
        do
          ++v16;
        while ( v25[v16 - 1] );
        v17 = 2LL * (int)v16 + 2;
        v25[(int)v16 - 1] = 34;
        if ( v17 >= 0x418 )
          _report_rangecheckfailure();
        *(unsigned __int16 *)((char *)&v25[-1] + v17) = 0;
        v15 = &v24;
      }
      else
      {
        v15 = v26;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v26);
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
0x18001a31c  push    rbp
0x18001a31e  push    rbx
0x18001a31f  push    rsi
0x18001a320  push    rdi
0x18001a321  push    r12
0x18001a323  push    r14
0x18001a325  push    r15
0x18001a327  lea     rbp, [rsp-9E0h]
0x18001a32f  sub     rsp, 0AE0h
0x18001a336  mov     rax, cs:__security_cookie
0x18001a33d  xor     rax, rsp
0x18001a340  mov     [rbp+0A10h+var_40], rax
0x18001a347  mov     rsi, rcx
0x18001a34a  mov     r15d, edx
0x18001a34d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a352  mov     rbx, r9
0x18001a355  mov     r14d, r8d
0x18001a358  call    ??0CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::CRegObject(void)
0x18001a35d  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001a362  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001a367  xor     r12d, r12d
0x18001a36a  mov     edi, eax
0x18001a36c  test    eax, eax
0x18001a36e  jns     short loc_18001A39D
0x18001a370  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a375  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a37a  mov     eax, edi
0x18001a37c  mov     rcx, [rbp+0A10h+var_40]
0x18001a383  xor     rcx, rsp; StackCookie
0x18001a386  call    __security_check_cookie
0x18001a38b  add     rsp, 0AE0h
0x18001a392  pop     r15
0x18001a394  pop     r14
0x18001a396  pop     r12
0x18001a398  pop     rdi
0x18001a399  pop     rsi
0x18001a39a  pop     rbx
0x18001a39b  pop     rbp
0x18001a39c  retn
0x18001a39d  test    rbx, rbx
0x18001a3a0  jz      short loc_18001A3C1
0x18001a3a2  jmp     short loc_18001A3B9
0x18001a3a4  mov     r8, [rbx+8]; unsigned __int16 *
0x18001a3a8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a3ad  mov     rdx, rax; unsigned __int16 *
0x18001a3b0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a3b5  lea     rbx, [rbx+10h]
0x18001a3b9  mov     rax, [rbx]
0x18001a3bc  test    rax, rax
0x18001a3bf  jnz     short loc_18001A3A4
0x18001a3c1  mov     rax, [rsi]
0x18001a3c4  lea     rdx, [rsp+0B10h+var_AD0]
0x18001a3c9  mov     rcx, rsi
0x18001a3cc  mov     rax, [rax+28h]
0x18001a3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3d5  mov     ebx, eax
0x18001a3d7  test    eax, eax
0x18001a3d9  js      loc_18001A50D
0x18001a3df  mov     rbx, cs:hModule
0x18001a3e6  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001a3ea  mov     edi, 104h
0x18001a3ef  mov     [rsp+0B10h+var_AE0], r12
0x18001a3f4  mov     r8d, edi; nSize
0x18001a3f7  mov     rcx, rbx; hModule
0x18001a3fa  call    cs:__imp_GetModuleFileNameW
0x18001a400  test    eax, eax
0x18001a402  jnz     short loc_18001A410
0x18001a404  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001a409  mov     ebx, eax
0x18001a40b  jmp     loc_18001A503
0x18001a410  cmp     eax, edi
0x18001a412  jnz     short loc_18001A428
0x18001a414  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a419  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a41e  mov     ebx, 8007007Ah
0x18001a423  jmp     loc_18001A50D
0x18001a428  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001a42c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a433  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001a438  test    rbx, rbx
0x18001a43b  jz      short loc_18001A453
0x18001a43d  xor     ecx, ecx; lpModuleName
0x18001a43f  call    cs:__imp_GetModuleHandleW
0x18001a445  cmp     rbx, rax
0x18001a448  jz      short loc_18001A453
0x18001a44a  lea     r8, [rbp+0A10h+var_450]
0x18001a451  jmp     short loc_18001A4CE
0x18001a453  mov     ebx, 22h ; '"'
0x18001a458  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a45f  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001a466  mov     [rbp+0A10h+var_870], bx
0x18001a46d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001a472  test    al, al
0x18001a474  jnz     short loc_18001A48A
0x18001a476  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a47b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a480  mov     ebx, 80004005h
0x18001a485  jmp     loc_18001A50D
0x18001a48a  lea     rcx, [rbp+0A10h+var_870]
0x18001a491  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a495  inc     rax
0x18001a498  cmp     [rcx+rax*2], r12w
0x18001a49d  jnz     short loc_18001A495
0x18001a49f  cdqe
0x18001a4a1  lea     rcx, ds:2[rax*2]
0x18001a4a9  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001a4b1  cmp     rcx, 418h
0x18001a4b8  jnb     loc_18001A55E
0x18001a4be  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001a4c7  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001a4ce  lea     rdx, aModule; "Module"
0x18001a4d5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a4da  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a4df  mov     ebx, eax
0x18001a4e1  test    eax, eax
0x18001a4e3  js      short loc_18001A503
0x18001a4e5  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001a4ec  lea     rdx, aModuleRaw; "Module_Raw"
0x18001a4f3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a4f8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001a4fd  mov     ebx, eax
0x18001a4ff  test    eax, eax
0x18001a501  jns     short loc_18001A51E
0x18001a503  lea     rcx, [rsp+0B10h+var_AE0]
0x18001a508  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a50d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a512  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001a517  mov     eax, ebx
0x18001a519  jmp     loc_18001A37C
0x18001a51e  movzx   r8d, r15w; unsigned __int16 *
0x18001a522  lea     r9, aRegistry; "REGISTRY"
0x18001a529  mov     [rsp+0B10h+var_AD8], r12
0x18001a52e  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001a532  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001a537  test    r14d, r14d
0x18001a53a  jz      short loc_18001A546
0x18001a53c  mov     [rsp+0B10h+var_AF0], 1
0x18001a544  jmp     short loc_18001A54B
0x18001a546  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001a54b  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001a550  lea     rcx, [rsp+0B10h+var_AD8]
0x18001a555  mov     ebx, eax
0x18001a557  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001a55c  jmp     short loc_18001A503
0x18001a55e  call    __report_rangecheckfailure
```
