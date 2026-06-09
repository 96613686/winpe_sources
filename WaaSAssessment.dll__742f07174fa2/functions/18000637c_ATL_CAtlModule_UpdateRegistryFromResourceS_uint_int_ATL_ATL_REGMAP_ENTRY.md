# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000637c`
- end: `0x180006693`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800069e0`

## callees

- `0x1800028d8`
- `0x180003190`
- `0x1800032f8`
- `0x180003eb4`
- `0x180004d6c`
- `0x1800056b8`
- `0x18000637c`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000654e`
- `msvcrt!memcpy_s` at `0x18000654e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006481`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006481`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006438`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006438`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000641d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006506`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000659b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000641d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006506`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000659b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065dc`

## string_xrefs

- `0x180006627`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
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
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  int v22; // ebx
  int v23; // ebx
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  unsigned __int16 Source[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v25 = &ATL::CRegObject::`vftable';
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v29 = 0;
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 >= 0 )
  {
    v29 = 1;
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
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v25);
    if ( v11 < 0 )
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v11 = -2147024774;
        goto LABEL_33;
      }
      v15 = Filename;
      v16 = 0;
      do
      {
        v17 = *v15;
        if ( !*v15 )
          break;
        Source[v16] = v17;
        if ( v17 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Source[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Source[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
        v32 = 34;
        v19 = -1;
        v20 = -1;
        do
          ++v20;
        while ( Source[v20] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v20 + 1)) )
        {
          v11 = -2147467259;
          goto LABEL_33;
        }
        do
          ++v19;
        while ( *(_WORD *)&Destination[2 * v19 - 2] );
        *(_WORD *)&Destination[2 * (int)v19 - 2] = 34;
        v21 = 2LL * (int)v19 + 2;
        if ( v21 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v21 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v18 = &v32;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v18 = Source;
      }
      v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module", v18);
      LeaveCriticalSection(&CriticalSection);
      v11 = v22 == 0 ? 0x8007000E : 0;
      if ( v11 < 0 )
      {
LABEL_33:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v23 == 0 ? 0x8007000E : 0;
      if ( v23 )
        Error = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v25,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  a3 != 0);
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v11 = Error;
    goto LABEL_33;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000637c  mov     [rsp-8+arg_10], rbx
0x180006381  push    rbp
0x180006382  push    rsi
0x180006383  push    rdi
0x180006384  push    r12
0x180006386  push    r13
0x180006388  push    r14
0x18000638a  push    r15
0x18000638c  lea     rbp, [rsp-9D0h]
0x180006394  sub     rsp, 0AD0h
0x18000639b  mov     rax, cs:__security_cookie
0x1800063a2  xor     rax, rsp
0x1800063a5  mov     [rbp+0A00h+var_40], rax
0x1800063ac  mov     rbx, r9
0x1800063af  mov     r15d, r8d
0x1800063b2  mov     r12d, edx
0x1800063b5  mov     r14, rcx
0x1800063b8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800063bf  mov     [rsp+0B00h+var_AD0], rax
0x1800063c4  xor     r13d, r13d
0x1800063c7  mov     [rsp+0B00h+var_AC8], r13
0x1800063cc  mov     [rsp+0B00h+var_AC0], r13
0x1800063d1  mov     [rsp+0B00h+var_AB8], r13d
0x1800063d6  xorps   xmm0, xmm0
0x1800063d9  xor     eax, eax
0x1800063db  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1800063e0  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1800063e5  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800063ea  mov     [rsp+0B00h+var_A88], r13b
0x1800063ef  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800063f4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800063f9  mov     edi, eax
0x1800063fb  test    eax, eax
0x1800063fd  js      loc_180006657
0x180006403  mov     [rsp+0B00h+var_A88], 1
0x180006408  test    rbx, rbx
0x18000640b  jz      short loc_18000644A
0x18000640d  jmp     short loc_180006442
0x18000640f  mov     rsi, [rbx+8]
0x180006413  test    rsi, rsi
0x180006416  jz      short loc_18000643E
0x180006418  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000641d  call    cs:__imp_EnterCriticalSection
0x180006423  mov     r8, rsi; unsigned __int16 *
0x180006426  mov     rdx, rdi; unsigned __int16 *
0x180006429  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000642e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006433  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006438  call    cs:__imp_LeaveCriticalSection
0x18000643e  add     rbx, 10h
0x180006442  mov     rdi, [rbx]
0x180006445  test    rdi, rdi
0x180006448  jnz     short loc_18000640F
0x18000644a  mov     rax, [r14]
0x18000644d  lea     rdx, [rsp+0B00h+var_AD0]
0x180006452  mov     rcx, r14
0x180006455  mov     rax, [rax+28h]
0x180006459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645e  mov     ebx, eax
0x180006460  test    eax, eax
0x180006462  js      loc_180006649
0x180006468  mov     rbx, cs:hModule
0x18000646f  mov     edi, 104h
0x180006474  mov     r8d, edi; nSize
0x180006477  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000647e  mov     rcx, rbx; hModule
0x180006481  call    cs:__imp_GetModuleFileNameW
0x180006487  test    eax, eax
0x180006489  jnz     short loc_180006497
0x18000648b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006490  mov     ebx, eax
0x180006492  jmp     loc_180006649
0x180006497  cmp     eax, edi
0x180006499  jnz     short loc_1800064A5
0x18000649b  mov     ebx, 8007007Ah
0x1800064a0  jmp     loc_180006649
0x1800064a5  lea     rdx, [rbp+0A00h+Filename]
0x1800064ac  mov     ecx, r13d
0x1800064af  mov     r9d, 27h ; '''
0x1800064b5  movzx   r8d, word ptr [rdx]
0x1800064b9  test    r8w, r8w
0x1800064bd  jz      short loc_1800064E9
0x1800064bf  mov     [rbp+rcx*2+0A00h+Source], r8w
0x1800064c5  cmp     r8w, r9w
0x1800064c9  jnz     short loc_1800064DB
0x1800064cb  cmp     ecx, 206h
0x1800064d1  jnb     short loc_1800064DB
0x1800064d3  inc     ecx
0x1800064d5  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1800064db  add     rdx, 2
0x1800064df  inc     ecx
0x1800064e1  cmp     ecx, 207h
0x1800064e7  jb      short loc_1800064B5
0x1800064e9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x1800064ef  test    rbx, rbx
0x1800064f2  jz      short loc_180006515
0x1800064f4  xor     ecx, ecx; lpModuleName
0x1800064f6  call    cs:__imp_GetModuleHandleW
0x1800064fc  cmp     rbx, rax
0x1800064ff  jz      short loc_180006515
0x180006501  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006506  call    cs:__imp_EnterCriticalSection
0x18000650c  lea     r8, [rbp+0A00h+Source]
0x180006510  jmp     loc_1800065A8
0x180006515  mov     edi, 22h ; '"'
0x18000651a  mov     [rbp+0A00h+var_460], di
0x180006521  lea     rcx, [rbp+0A00h+Source]
0x180006525  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006529  mov     rax, rbx
0x18000652c  inc     rax
0x18000652f  cmp     [rcx+rax*2], r13w
0x180006534  jnz     short loc_18000652C
0x180006536  inc     eax
0x180006538  movsxd  r9, eax
0x18000653b  add     r9, r9; SourceSize
0x18000653e  lea     r8, [rbp+0A00h+Source]; Source
0x180006542  mov     edx, 414h; DestinationSize
0x180006547  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000654e  call    cs:__imp_memcpy_s
0x180006554  test    eax, eax
0x180006556  jnz     loc_180006644
0x18000655c  lea     rax, [rbp+0A00h+var_460]
0x180006563  inc     rbx
0x180006566  cmp     [rax+rbx*2], r13w
0x18000656b  jnz     short loc_180006563
0x18000656d  movsxd  rax, ebx
0x180006570  mov     [rbp+rax*2+0A00h+var_460], di
0x180006578  lea     rcx, ds:2[rax*2]
0x180006580  cmp     rcx, 418h
0x180006587  jnb     loc_18000668D
0x18000658d  mov     [rbp+rcx+0A00h+var_460], r13w
0x180006596  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000659b  call    cs:__imp_EnterCriticalSection
0x1800065a1  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800065a8  lea     rdx, aModule; "Module"
0x1800065af  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800065b4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800065b9  mov     ebx, eax
0x1800065bb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800065c0  call    cs:__imp_LeaveCriticalSection
0x1800065c6  neg     ebx
0x1800065c8  sbb     ebx, ebx
0x1800065ca  mov     edi, 8007000Eh
0x1800065cf  not     ebx
0x1800065d1  and     ebx, edi
0x1800065d3  test    ebx, ebx
0x1800065d5  js      short loc_180006649
0x1800065d7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800065dc  call    cs:__imp_EnterCriticalSection
0x1800065e2  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x1800065e6  lea     rdx, aModuleRaw; "Module_Raw"
0x1800065ed  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800065f2  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800065f7  mov     ebx, eax
0x1800065f9  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800065fe  call    cs:__imp_LeaveCriticalSection
0x180006604  mov     ecx, ebx
0x180006606  neg     ecx
0x180006608  sbb     eax, eax
0x18000660a  not     eax
0x18000660c  and     eax, edi
0x18000660e  test    ebx, ebx
0x180006610  jz      loc_180006490
0x180006616  mov     eax, r13d
0x180006619  test    r15d, r15d
0x18000661c  setnz   al
0x18000661f  movzx   r8d, r12w; unsigned __int16 *
0x180006623  mov     [rsp+0B00h+var_AE0], eax; int
0x180006627  lea     r9, aRegistry; "REGISTRY"
0x18000662e  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006635  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000663a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000663f  jmp     loc_180006490
0x180006644  mov     ebx, 80004005h
0x180006649  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000664e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006653  mov     eax, ebx
0x180006655  jmp     short loc_180006663
0x180006657  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000665c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006661  mov     eax, edi
0x180006663  mov     rcx, [rbp+0A00h+var_40]
0x18000666a  xor     rcx, rsp; StackCookie
0x18000666d  call    __security_check_cookie
0x180006672  mov     rbx, [rsp+0B00h+arg_10]
0x18000667a  add     rsp, 0AD0h
0x180006681  pop     r15
0x180006683  pop     r14
0x180006685  pop     r13
0x180006687  pop     r12
0x180006689  pop     rdi
0x18000668a  pop     rsi
0x18000668b  pop     rbp
0x18000668c  retn
0x18000668d  call    __report_rangecheckfailure
```
