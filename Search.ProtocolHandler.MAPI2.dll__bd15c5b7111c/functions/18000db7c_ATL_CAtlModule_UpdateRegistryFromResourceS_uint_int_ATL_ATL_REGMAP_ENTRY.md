# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000db7c`
- end: `0x18000ddec`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e080`

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
- `0x18000db7c`
- `0x18000e09c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000dc82`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000dc82`

## string_xrefs

- `0x18000ddaf`: `REGISTRY`

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
        *(wchar_t *)((char *)&v28[-1] + v17) = 0;
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
0x18000db7c  push    rbp
0x18000db7e  push    rbx
0x18000db7f  push    rsi
0x18000db80  push    rdi
0x18000db81  push    r12
0x18000db83  push    r14
0x18000db85  push    r15
0x18000db87  lea     rbp, [rsp-9E0h]
0x18000db8f  sub     rsp, 0AE0h
0x18000db96  mov     rax, cs:__security_cookie
0x18000db9d  xor     rax, rsp
0x18000dba0  mov     [rbp+0A10h+var_40], rax
0x18000dba7  mov     rbx, r9
0x18000dbaa  mov     r14d, r8d
0x18000dbad  mov     r15d, edx
0x18000dbb0  mov     rsi, rcx
0x18000dbb3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000dbba  mov     [rsp+0B10h+var_AD0], rax
0x18000dbbf  xor     r12d, r12d
0x18000dbc2  mov     [rsp+0B10h+var_AC8], r12
0x18000dbc7  mov     [rsp+0B10h+var_AC0], r12
0x18000dbcc  mov     [rsp+0B10h+var_AB8], r12d
0x18000dbd1  xorps   xmm0, xmm0
0x18000dbd4  xor     eax, eax
0x18000dbd6  movups  [rsp+0B10h+var_AB0], xmm0
0x18000dbdb  movups  [rsp+0B10h+var_AA0], xmm0
0x18000dbe0  mov     [rbp+0A10h+var_A90], rax
0x18000dbe4  mov     [rbp+0A10h+var_A88], r12b
0x18000dbe8  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000dbed  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000dbf2  mov     edi, eax
0x18000dbf4  test    eax, eax
0x18000dbf6  jns     short loc_18000DC25
0x18000dbf8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000dbfd  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000dc02  mov     eax, edi
0x18000dc04  mov     rcx, [rbp+0A10h+var_40]
0x18000dc0b  xor     rcx, rsp; StackCookie
0x18000dc0e  call    __security_check_cookie
0x18000dc13  add     rsp, 0AE0h
0x18000dc1a  pop     r15
0x18000dc1c  pop     r14
0x18000dc1e  pop     r12
0x18000dc20  pop     rdi
0x18000dc21  pop     rsi
0x18000dc22  pop     rbx
0x18000dc23  pop     rbp
0x18000dc24  retn
0x18000dc25  test    rbx, rbx
0x18000dc28  jz      short loc_18000DC49
0x18000dc2a  jmp     short loc_18000DC41
0x18000dc2c  mov     r8, [rbx+8]; wchar_t *
0x18000dc30  mov     rdx, rax; wchar_t *
0x18000dc33  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000dc38  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18000dc3d  lea     rbx, [rbx+10h]
0x18000dc41  mov     rax, [rbx]
0x18000dc44  test    rax, rax
0x18000dc47  jnz     short loc_18000DC2C
0x18000dc49  mov     rax, [rsi]
0x18000dc4c  lea     rdx, [rsp+0B10h+var_AD0]
0x18000dc51  mov     rcx, rsi
0x18000dc54  mov     rax, [rax+28h]
0x18000dc58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc5d  mov     ebx, eax
0x18000dc5f  test    eax, eax
0x18000dc61  js      loc_18000DD95
0x18000dc67  mov     [rsp+0B10h+var_AE0], r12
0x18000dc6c  mov     rbx, cs:hModule
0x18000dc73  mov     edi, 104h
0x18000dc78  mov     r8d, edi; nSize
0x18000dc7b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000dc7f  mov     rcx, rbx; hModule
0x18000dc82  call    cs:__imp_GetModuleFileNameW
0x18000dc88  test    eax, eax
0x18000dc8a  jnz     short loc_18000DC98
0x18000dc8c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000dc91  mov     ebx, eax
0x18000dc93  jmp     loc_18000DD8B
0x18000dc98  cmp     eax, edi
0x18000dc9a  jnz     short loc_18000DCB0
0x18000dc9c  lea     rcx, [rsp+0B10h+var_AE0]
0x18000dca1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000dca6  mov     ebx, 8007007Ah
0x18000dcab  jmp     loc_18000DD95
0x18000dcb0  lea     r8, [rbp+0A10h+Filename]; wchar_t *
0x18000dcb4  lea     rcx, [rbp+0A10h+var_450]; wchar_t *
0x18000dcbb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEA_W_KPEB_W@Z; ATL::CAtlModule::EscapeSingleQuote(wchar_t *,unsigned __int64,wchar_t const *)
0x18000dcc0  test    rbx, rbx
0x18000dcc3  jz      short loc_18000DCDB
0x18000dcc5  xor     ecx, ecx; lpModuleName
0x18000dcc7  call    cs:__imp_GetModuleHandleW
0x18000dccd  cmp     rbx, rax
0x18000dcd0  jz      short loc_18000DCDB
0x18000dcd2  lea     r8, [rbp+0A10h+var_450]
0x18000dcd9  jmp     short loc_18000DD56
0x18000dcdb  mov     ebx, 22h ; '"'
0x18000dce0  mov     [rbp+0A10h+var_870], bx
0x18000dce7  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18000dcee  lea     rcx, [rbp+0A10h+var_86E]; wchar_t *
0x18000dcf5  call    ?ocscpy_s@@YA_NPEA_W_KPEB_W@Z; ocscpy_s(wchar_t *,unsigned __int64,wchar_t const *)
0x18000dcfa  test    al, al
0x18000dcfc  jnz     short loc_18000DD12
0x18000dcfe  lea     rcx, [rsp+0B10h+var_AE0]
0x18000dd03  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000dd08  mov     ebx, 80004005h
0x18000dd0d  jmp     loc_18000DD95
0x18000dd12  lea     rcx, [rbp+0A10h+var_870]
0x18000dd19  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dd1d  inc     rax
0x18000dd20  cmp     [rcx+rax*2], r12w
0x18000dd25  jnz     short loc_18000DD1D
0x18000dd27  cdqe
0x18000dd29  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000dd31  lea     rcx, ds:2[rax*2]
0x18000dd39  cmp     rcx, 418h
0x18000dd40  jnb     loc_18000DDE6
0x18000dd46  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000dd4f  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x18000dd56  lea     rdx, aModule; "Module"
0x18000dd5d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000dd62  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18000dd67  mov     ebx, eax
0x18000dd69  test    eax, eax
0x18000dd6b  js      short loc_18000DD8B
0x18000dd6d  lea     r8, [rbp+0A10h+var_450]; wchar_t *
0x18000dd74  lea     rdx, aModuleRaw; "Module_Raw"
0x18000dd7b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000dd80  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x18000dd85  mov     ebx, eax
0x18000dd87  test    eax, eax
0x18000dd89  jns     short loc_18000DDA6
0x18000dd8b  lea     rcx, [rsp+0B10h+var_AE0]
0x18000dd90  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000dd95  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000dd9a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000dd9f  mov     eax, ebx
0x18000dda1  jmp     loc_18000DC04
0x18000dda6  movzx   r8d, r15w; wchar_t *
0x18000ddaa  mov     [rsp+0B10h+var_AD8], r12
0x18000ddaf  lea     r9, aRegistry; "REGISTRY"
0x18000ddb6  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x18000ddba  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000ddbf  test    r14d, r14d
0x18000ddc2  jz      short loc_18000DDCE
0x18000ddc4  mov     [rsp+0B10h+var_AF0], 1
0x18000ddcc  jmp     short loc_18000DDD3
0x18000ddce  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000ddd3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18000ddd8  mov     ebx, eax
0x18000ddda  lea     rcx, [rsp+0B10h+var_AD8]
0x18000dddf  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000dde4  jmp     short loc_18000DD8B
0x18000dde6  call    __report_rangecheckfailure
```
