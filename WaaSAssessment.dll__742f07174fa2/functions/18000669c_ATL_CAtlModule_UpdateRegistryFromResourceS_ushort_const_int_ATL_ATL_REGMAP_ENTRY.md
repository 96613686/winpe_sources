# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000669c`
- end: `0x1800069da`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800069f0`

## callees

- `0x1800028d8`
- `0x180003190`
- `0x1800032f8`
- `0x180003eb4`
- `0x180004d6c`
- `0x1800056b8`
- `0x18000669c`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000687a`
- `msvcrt!memcpy_s` at `0x18000687a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000679e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000679e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006819`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006758`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006931`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006758`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006931`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000673d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006829`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800068c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000690c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000673d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006829`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800068c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000690c`

## string_xrefs

- `0x180006967`: `REGISTRY`

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
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Source[520]; // [rsp+290h] [rbp+190h] BYREF
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
      goto LABEL_39;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v11 = -2147024774;
        goto LABEL_39;
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
          goto LABEL_39;
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
LABEL_39:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v23 == 0 ? 0x8007000E : 0;
      if ( v23 )
      {
        if ( a3 )
        {
          if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 1);
            goto LABEL_11;
          }
        }
        else if ( a2 )
        {
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 0);
          goto LABEL_11;
        }
        v11 = -2147024809;
        goto LABEL_39;
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
LABEL_11:
    v11 = Error;
    goto LABEL_39;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000669c  mov     [rsp-8+arg_10], rbx
0x1800066a1  push    rbp
0x1800066a2  push    rsi
0x1800066a3  push    rdi
0x1800066a4  push    r12
0x1800066a6  push    r13
0x1800066a8  push    r14
0x1800066aa  push    r15
0x1800066ac  lea     rbp, [rsp-9D0h]
0x1800066b4  sub     rsp, 0AD0h
0x1800066bb  mov     rax, cs:__security_cookie
0x1800066c2  xor     rax, rsp
0x1800066c5  mov     [rbp+0A00h+var_40], rax
0x1800066cc  mov     rbx, r9
0x1800066cf  mov     r12d, r8d
0x1800066d2  mov     r14, rdx
0x1800066d5  mov     r15, rcx
0x1800066d8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800066df  mov     [rsp+0B00h+var_AD0], rax
0x1800066e4  xor     r13d, r13d
0x1800066e7  mov     [rsp+0B00h+var_AC8], r13
0x1800066ec  mov     [rsp+0B00h+var_AC0], r13
0x1800066f1  mov     [rsp+0B00h+var_AB8], r13d
0x1800066f6  xorps   xmm0, xmm0
0x1800066f9  xor     eax, eax
0x1800066fb  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180006700  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180006705  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000670a  mov     [rsp+0B00h+var_A88], r13b
0x18000670f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180006714  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006719  mov     edi, eax
0x18000671b  test    eax, eax
0x18000671d  js      loc_18000699E
0x180006723  mov     [rsp+0B00h+var_A88], 1
0x180006728  test    rbx, rbx
0x18000672b  jz      short loc_18000676A
0x18000672d  jmp     short loc_180006762
0x18000672f  mov     rsi, [rbx+8]
0x180006733  test    rsi, rsi
0x180006736  jz      short loc_18000675E
0x180006738  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000673d  call    cs:__imp_EnterCriticalSection
0x180006743  mov     r8, rsi; unsigned __int16 *
0x180006746  mov     rdx, rdi; unsigned __int16 *
0x180006749  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000674e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006753  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006758  call    cs:__imp_LeaveCriticalSection
0x18000675e  add     rbx, 10h
0x180006762  mov     rdi, [rbx]
0x180006765  test    rdi, rdi
0x180006768  jnz     short loc_18000672F
0x18000676a  mov     rax, [r15]
0x18000676d  lea     rdx, [rsp+0B00h+var_AD0]
0x180006772  mov     rcx, r15
0x180006775  mov     rax, [rax+28h]
0x180006779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677e  mov     ebx, eax
0x180006780  test    eax, eax
0x180006782  js      loc_180006990
0x180006788  mov     rbx, cs:hModule
0x18000678f  mov     edi, 104h
0x180006794  mov     r8d, edi; nSize
0x180006797  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000679b  mov     rcx, rbx; hModule
0x18000679e  call    cs:__imp_GetModuleFileNameW
0x1800067a4  test    eax, eax
0x1800067a6  jnz     short loc_1800067B4
0x1800067a8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800067ad  mov     ebx, eax
0x1800067af  jmp     loc_180006990
0x1800067b4  cmp     eax, edi
0x1800067b6  jnz     short loc_1800067C2
0x1800067b8  mov     ebx, 8007007Ah
0x1800067bd  jmp     loc_180006990
0x1800067c2  lea     rdx, [rbp+0A00h+Filename]
0x1800067c6  mov     ecx, r13d
0x1800067c9  mov     r9d, 27h ; '''
0x1800067cf  movzx   r8d, word ptr [rdx]
0x1800067d3  test    r8w, r8w
0x1800067d7  jz      short loc_180006809
0x1800067d9  mov     [rbp+rcx*2+0A00h+Source], r8w
0x1800067e2  cmp     r8w, r9w
0x1800067e6  jnz     short loc_1800067FB
0x1800067e8  cmp     ecx, 206h
0x1800067ee  jnb     short loc_1800067FB
0x1800067f0  inc     ecx
0x1800067f2  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1800067fb  add     rdx, 2
0x1800067ff  inc     ecx
0x180006801  cmp     ecx, 207h
0x180006807  jb      short loc_1800067CF
0x180006809  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180006812  test    rbx, rbx
0x180006815  jz      short loc_18000683B
0x180006817  xor     ecx, ecx; lpModuleName
0x180006819  call    cs:__imp_GetModuleHandleW
0x18000681f  cmp     rbx, rax
0x180006822  jz      short loc_18000683B
0x180006824  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006829  call    cs:__imp_EnterCriticalSection
0x18000682f  lea     r8, [rbp+0A00h+Source]
0x180006836  jmp     loc_1800068D4
0x18000683b  mov     edi, 22h ; '"'
0x180006840  mov     [rbp+0A00h+var_460], di
0x180006847  lea     rcx, [rbp+0A00h+Source]
0x18000684e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006852  mov     rax, rbx
0x180006855  inc     rax
0x180006858  cmp     [rcx+rax*2], r13w
0x18000685d  jnz     short loc_180006855
0x18000685f  inc     eax
0x180006861  movsxd  r9, eax
0x180006864  add     r9, r9; SourceSize
0x180006867  lea     r8, [rbp+0A00h+Source]; Source
0x18000686e  mov     edx, 414h; DestinationSize
0x180006873  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000687a  call    cs:__imp_memcpy_s
0x180006880  test    eax, eax
0x180006882  jnz     loc_18000698B
0x180006888  lea     rax, [rbp+0A00h+var_460]
0x18000688f  inc     rbx
0x180006892  cmp     [rax+rbx*2], r13w
0x180006897  jnz     short loc_18000688F
0x180006899  movsxd  rax, ebx
0x18000689c  mov     [rbp+rax*2+0A00h+var_460], di
0x1800068a4  lea     rcx, ds:2[rax*2]
0x1800068ac  cmp     rcx, 418h
0x1800068b3  jnb     loc_1800069D4
0x1800068b9  mov     [rbp+rcx+0A00h+var_460], r13w
0x1800068c2  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800068c7  call    cs:__imp_EnterCriticalSection
0x1800068cd  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800068d4  lea     rdx, aModule; "Module"
0x1800068db  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800068e0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800068e5  mov     ebx, eax
0x1800068e7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800068ec  call    cs:__imp_LeaveCriticalSection
0x1800068f2  neg     ebx
0x1800068f4  sbb     ebx, ebx
0x1800068f6  mov     edi, 8007000Eh
0x1800068fb  not     ebx
0x1800068fd  and     ebx, edi
0x1800068ff  test    ebx, ebx
0x180006901  js      loc_180006990
0x180006907  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000690c  call    cs:__imp_EnterCriticalSection
0x180006912  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180006919  lea     rdx, aModuleRaw; "Module_Raw"
0x180006920  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006925  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000692a  mov     ebx, eax
0x18000692c  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006931  call    cs:__imp_LeaveCriticalSection
0x180006937  mov     ecx, ebx
0x180006939  neg     ecx
0x18000693b  sbb     eax, eax
0x18000693d  not     eax
0x18000693f  and     eax, edi
0x180006941  test    ebx, ebx
0x180006943  jz      loc_1800067AD
0x180006949  test    r12d, r12d
0x18000694c  jz      short loc_18000695D
0x18000694e  test    r14, r14
0x180006951  jz      short loc_180006984
0x180006953  mov     [rsp+0B00h+var_AE0], 1
0x18000695b  jmp     short loc_180006967
0x18000695d  test    r14, r14
0x180006960  jz      short loc_180006984
0x180006962  mov     [rsp+0B00h+var_AE0], r13d; int
0x180006967  lea     r9, aRegistry; "REGISTRY"
0x18000696e  mov     r8, r14; unsigned __int16 *
0x180006971  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006975  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000697a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000697f  jmp     loc_1800067AD
0x180006984  mov     ebx, 80070057h
0x180006989  jmp     short loc_180006990
0x18000698b  mov     ebx, 80004005h
0x180006990  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006995  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000699a  mov     eax, ebx
0x18000699c  jmp     short loc_1800069AA
0x18000699e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800069a3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800069a8  mov     eax, edi
0x1800069aa  mov     rcx, [rbp+0A00h+var_40]
0x1800069b1  xor     rcx, rsp; StackCookie
0x1800069b4  call    __security_check_cookie
0x1800069b9  mov     rbx, [rsp+0B00h+arg_10]
0x1800069c1  add     rsp, 0AD0h
0x1800069c8  pop     r15
0x1800069ca  pop     r14
0x1800069cc  pop     r13
0x1800069ce  pop     r12
0x1800069d0  pop     rdi
0x1800069d1  pop     rsi
0x1800069d2  pop     rbp
0x1800069d3  retn
0x1800069d4  call    __report_rangecheckfailure
```
