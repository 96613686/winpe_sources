# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006ef4`
- end: `0x180007237`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007250`

## callees

- `0x180001550`
- `0x180001590`
- `0x180001e62`
- `0x18000407c`
- `0x18000428c`
- `0x180004e04`
- `0x1800054ac`
- `0x180005e98`
- `0x180006ef4`
- `0x180009f88`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800071a8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800071a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007143`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007184`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007143`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007184`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000707f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000711e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000715f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000707f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000711e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000715f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006ff6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006ff6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000706f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000706f`

## string_xrefs

- `0x1800071da`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  const unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // rdi
  signed int v11; // ebx
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned __int16 v18; // r8
  unsigned __int16 *v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  size_t v22; // r8
  unsigned __int64 v23; // rcx
  int v24; // ebx
  int v25; // ebx
  void **v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Src[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 >= 0 )
  {
    v31 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = *(const unsigned __int16 **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v9 = (const unsigned __int16 *)*((_QWORD *)a4 + 1);
        if ( v9 )
        {
          EnterCriticalSection(&CriticalSection);
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v27);
    if ( v11 < 0 )
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_32;
    }
    if ( ModuleFileNameW == 260 )
    {
      v11 = -2147024774;
    }
    else
    {
      v15 = Filename;
      v16 = 0;
      v17 = 39;
      do
      {
        v18 = *v15;
        if ( !*v15 )
          break;
        Src[v16] = v18;
        if ( v18 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Src[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Src[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
        v34 = 34;
        v20 = -1;
        v21 = -1;
        do
          ++v21;
        while ( Src[v21] );
        v22 = 2LL * ((int)v21 + 1);
        if ( v22 )
        {
          if ( v22 > 0x414 )
          {
            *(_DWORD *)_o__errno(Src, v15, v22, v17) = 34;
            invalid_parameter_noinfo();
            v11 = -2147467259;
            goto LABEL_33;
          }
          memcpy_0(v35, Src, v22);
        }
        do
          ++v20;
        while ( *(_WORD *)&v35[2 * v20 - 2] );
        *(_WORD *)&v35[2 * (int)v20 - 2] = 34;
        v23 = 2LL * (int)v20 + 2;
        if ( v23 >= 0x418 )
          _report_rangecheckfailure(v23, v15, v22, v17);
        *(_WORD *)&v35[v23 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v19 = &v34;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v19 = Src;
      }
      v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module", v19);
      LeaveCriticalSection(&CriticalSection);
      v11 = v24 == 0 ? 0x8007000E : 0;
      if ( v11 >= 0 )
      {
        EnterCriticalSection(&CriticalSection);
        v25 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module_Raw", Src);
        LeaveCriticalSection(&CriticalSection);
        Error = v25 == 0 ? 0x8007000E : 0;
        if ( v25 )
        {
          if ( a3 )
          {
            if ( a2 )
            {
              Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 1);
              goto LABEL_32;
            }
          }
          else if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 0);
            goto LABEL_32;
          }
          v11 = -2147024809;
          goto LABEL_33;
        }
LABEL_32:
        v11 = Error;
      }
    }
LABEL_33:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006ef4  mov     [rsp-8+arg_10], rbx
0x180006ef9  push    rbp
0x180006efa  push    rsi
0x180006efb  push    rdi
0x180006efc  push    r12
0x180006efe  push    r13
0x180006f00  push    r14
0x180006f02  push    r15
0x180006f04  lea     rbp, [rsp-9D0h]
0x180006f0c  sub     rsp, 0AD0h
0x180006f13  mov     rax, cs:__security_cookie
0x180006f1a  xor     rax, rsp
0x180006f1d  mov     [rbp+0A00h+var_40], rax
0x180006f24  mov     rbx, r9
0x180006f27  mov     r12d, r8d
0x180006f2a  mov     r14, rdx
0x180006f2d  mov     r15, rcx
0x180006f30  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180006f37  mov     [rsp+0B00h+var_AD0], rax
0x180006f3c  xor     r13d, r13d
0x180006f3f  mov     [rsp+0B00h+var_AC8], r13
0x180006f44  mov     [rsp+0B00h+var_AC0], r13
0x180006f49  mov     [rsp+0B00h+var_AB8], r13d
0x180006f4e  xorps   xmm0, xmm0
0x180006f51  xor     eax, eax
0x180006f53  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180006f58  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180006f5d  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180006f62  mov     [rsp+0B00h+var_A88], r13b
0x180006f67  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180006f6c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006f71  mov     edi, eax
0x180006f73  test    eax, eax
0x180006f75  js      loc_1800071FB
0x180006f7b  mov     [rsp+0B00h+var_A88], 1
0x180006f80  test    rbx, rbx
0x180006f83  jz      short loc_180006FC2
0x180006f85  jmp     short loc_180006FBA
0x180006f87  mov     rsi, [rbx+8]
0x180006f8b  test    rsi, rsi
0x180006f8e  jz      short loc_180006FB6
0x180006f90  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006f95  call    cs:__imp_EnterCriticalSection
0x180006f9b  mov     r8, rsi; unsigned __int16 *
0x180006f9e  mov     rdx, rdi; unsigned __int16 *
0x180006fa1  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006fa6  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006fab  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006fb0  call    cs:__imp_LeaveCriticalSection
0x180006fb6  add     rbx, 10h
0x180006fba  mov     rdi, [rbx]
0x180006fbd  test    rdi, rdi
0x180006fc0  jnz     short loc_180006F87
0x180006fc2  mov     rax, [r15]
0x180006fc5  lea     rdx, [rsp+0B00h+var_AD0]
0x180006fca  mov     rcx, r15
0x180006fcd  mov     rax, [rax+28h]
0x180006fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd6  mov     ebx, eax
0x180006fd8  test    eax, eax
0x180006fda  js      loc_18000719A
0x180006fe0  mov     rbx, cs:hModule
0x180006fe7  mov     edi, 104h
0x180006fec  mov     r8d, edi; nSize
0x180006fef  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180006ff3  mov     rcx, rbx; hModule
0x180006ff6  call    cs:__imp_GetModuleFileNameW
0x180006ffc  test    eax, eax
0x180006ffe  jnz     short loc_18000700A
0x180007000  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180007005  jmp     loc_180007198
0x18000700a  cmp     eax, edi
0x18000700c  jnz     short loc_180007018
0x18000700e  mov     ebx, 8007007Ah
0x180007013  jmp     loc_18000719A
0x180007018  lea     rdx, [rbp+0A00h+Filename]
0x18000701c  mov     ecx, r13d
0x18000701f  mov     r9d, 27h ; '''
0x180007025  movzx   r8d, word ptr [rdx]
0x180007029  test    r8w, r8w
0x18000702d  jz      short loc_18000705F
0x18000702f  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180007038  cmp     r8w, r9w
0x18000703c  jnz     short loc_180007051
0x18000703e  cmp     ecx, 206h
0x180007044  jnb     short loc_180007051
0x180007046  inc     ecx
0x180007048  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180007051  add     rdx, 2
0x180007055  inc     ecx
0x180007057  cmp     ecx, 207h
0x18000705d  jb      short loc_180007025
0x18000705f  mov     [rbp+rcx*2+0A00h+Src], r13w
0x180007068  test    rbx, rbx
0x18000706b  jz      short loc_180007091
0x18000706d  xor     ecx, ecx; lpModuleName
0x18000706f  call    cs:__imp_GetModuleHandleW
0x180007075  cmp     rbx, rax
0x180007078  jz      short loc_180007091
0x18000707a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000707f  call    cs:__imp_EnterCriticalSection
0x180007085  lea     r8, [rbp+0A00h+Src]
0x18000708c  jmp     loc_18000712B
0x180007091  mov     edi, 22h ; '"'
0x180007096  mov     [rbp+0A00h+var_460], di
0x18000709d  lea     rcx, [rbp+0A00h+Src]
0x1800070a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800070a8  mov     rax, rbx
0x1800070ab  inc     rax
0x1800070ae  cmp     [rcx+rax*2], r13w
0x1800070b3  jnz     short loc_1800070AB
0x1800070b5  inc     eax
0x1800070b7  movsxd  r8, eax
0x1800070ba  add     r8, r8; Size
0x1800070bd  jz      short loc_1800070DF
0x1800070bf  cmp     r8, 414h
0x1800070c6  ja      loc_1800071A8
0x1800070cc  lea     rdx, [rbp+0A00h+Src]; Src
0x1800070d3  lea     rcx, [rbp+0A00h+var_45E]; void *
0x1800070da  call    memcpy_0
0x1800070df  lea     rax, [rbp+0A00h+var_460]
0x1800070e6  inc     rbx
0x1800070e9  cmp     [rax+rbx*2], r13w
0x1800070ee  jnz     short loc_1800070E6
0x1800070f0  movsxd  rax, ebx
0x1800070f3  mov     [rbp+rax*2+0A00h+var_460], di
0x1800070fb  lea     rcx, ds:2[rax*2]
0x180007103  cmp     rcx, 418h
0x18000710a  jnb     loc_180007231
0x180007110  mov     [rbp+rcx+0A00h+var_460], r13w
0x180007119  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000711e  call    cs:__imp_EnterCriticalSection
0x180007124  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000712b  lea     rdx, aModule; "Module"
0x180007132  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180007137  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000713c  mov     ebx, eax
0x18000713e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180007143  call    cs:__imp_LeaveCriticalSection
0x180007149  neg     ebx
0x18000714b  sbb     ebx, ebx
0x18000714d  mov     edi, 8007000Eh
0x180007152  not     ebx
0x180007154  and     ebx, edi
0x180007156  test    ebx, ebx
0x180007158  js      short loc_18000719A
0x18000715a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000715f  call    cs:__imp_EnterCriticalSection
0x180007165  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x18000716c  lea     rdx, aModuleRaw; "Module_Raw"
0x180007173  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180007178  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000717d  mov     ebx, eax
0x18000717f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180007184  call    cs:__imp_LeaveCriticalSection
0x18000718a  mov     ecx, ebx
0x18000718c  neg     ecx
0x18000718e  sbb     eax, eax
0x180007190  not     eax
0x180007192  and     eax, edi
0x180007194  test    ebx, ebx
0x180007196  jnz     short loc_1800071BC
0x180007198  mov     ebx, eax
0x18000719a  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000719f  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800071a4  mov     eax, ebx
0x1800071a6  jmp     short loc_180007207
0x1800071a8  call    cs:__imp__o__errno
0x1800071ae  mov     [rax], edi
0x1800071b0  call    _invalid_parameter_noinfo
0x1800071b5  mov     ebx, 80004005h
0x1800071ba  jmp     short loc_18000719A
0x1800071bc  test    r12d, r12d
0x1800071bf  jz      short loc_1800071D0
0x1800071c1  test    r14, r14
0x1800071c4  jz      short loc_1800071F4
0x1800071c6  mov     [rsp+0B00h+var_AE0], 1
0x1800071ce  jmp     short loc_1800071DA
0x1800071d0  test    r14, r14
0x1800071d3  jz      short loc_1800071F4
0x1800071d5  mov     [rsp+0B00h+var_AE0], r13d; int
0x1800071da  lea     r9, aRegistry; "REGISTRY"
0x1800071e1  mov     r8, r14; unsigned __int16 *
0x1800071e4  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800071e8  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800071ed  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800071f2  jmp     short loc_180007198
0x1800071f4  mov     ebx, 80070057h
0x1800071f9  jmp     short loc_18000719A
0x1800071fb  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180007200  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180007205  mov     eax, edi
0x180007207  mov     rcx, [rbp+0A00h+var_40]
0x18000720e  xor     rcx, rsp; StackCookie
0x180007211  call    __security_check_cookie
0x180007216  mov     rbx, [rsp+0B00h+arg_10]
0x18000721e  add     rsp, 0AD0h
0x180007225  pop     r15
0x180007227  pop     r14
0x180007229  pop     r13
0x18000722b  pop     r12
0x18000722d  pop     rdi
0x18000722e  pop     rsi
0x18000722f  pop     rbp
0x180007230  retn
0x180007231  call    __report_rangecheckfailure
```
