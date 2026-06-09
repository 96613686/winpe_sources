# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800222c4`
- end: `0x180022607`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180022620`

## callees

- `0x1800018f0`
- `0x180001930`
- `0x180002202`
- `0x18001b024`
- `0x18001ee9c`
- `0x18001f0bc`
- `0x18001fc74`
- `0x1800207fc`
- `0x180021228`
- `0x1800222c4`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022578`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022578`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022365`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002244f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800224ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002252f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022365`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002244f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800224ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002252f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022380`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022513`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022554`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022380`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022513`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022554`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800223c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800223c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002243f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002243f`

## string_xrefs

- `0x1800225aa`: `REGISTRY`

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
0x1800222c4  mov     [rsp-8+arg_10], rbx
0x1800222c9  push    rbp
0x1800222ca  push    rsi
0x1800222cb  push    rdi
0x1800222cc  push    r12
0x1800222ce  push    r13
0x1800222d0  push    r14
0x1800222d2  push    r15
0x1800222d4  lea     rbp, [rsp-9D0h]
0x1800222dc  sub     rsp, 0AD0h
0x1800222e3  mov     rax, cs:__security_cookie
0x1800222ea  xor     rax, rsp
0x1800222ed  mov     [rbp+0A00h+var_40], rax
0x1800222f4  mov     rbx, r9
0x1800222f7  mov     r12d, r8d
0x1800222fa  mov     r14, rdx
0x1800222fd  mov     r15, rcx
0x180022300  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180022307  mov     [rsp+0B00h+var_AD0], rax
0x18002230c  xor     r13d, r13d
0x18002230f  mov     [rsp+0B00h+var_AC8], r13
0x180022314  mov     [rsp+0B00h+var_AC0], r13
0x180022319  mov     [rsp+0B00h+var_AB8], r13d
0x18002231e  xorps   xmm0, xmm0
0x180022321  xor     eax, eax
0x180022323  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180022328  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18002232d  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180022332  mov     [rsp+0B00h+var_A88], r13b
0x180022337  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18002233c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180022341  mov     edi, eax
0x180022343  test    eax, eax
0x180022345  js      loc_1800225CB
0x18002234b  mov     [rsp+0B00h+var_A88], 1
0x180022350  test    rbx, rbx
0x180022353  jz      short loc_180022392
0x180022355  jmp     short loc_18002238A
0x180022357  mov     rsi, [rbx+8]
0x18002235b  test    rsi, rsi
0x18002235e  jz      short loc_180022386
0x180022360  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180022365  call    cs:__imp_EnterCriticalSection
0x18002236b  mov     r8, rsi; unsigned __int16 *
0x18002236e  mov     rdx, rdi; unsigned __int16 *
0x180022371  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180022376  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18002237b  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180022380  call    cs:__imp_LeaveCriticalSection
0x180022386  add     rbx, 10h
0x18002238a  mov     rdi, [rbx]
0x18002238d  test    rdi, rdi
0x180022390  jnz     short loc_180022357
0x180022392  mov     rax, [r15]
0x180022395  lea     rdx, [rsp+0B00h+var_AD0]
0x18002239a  mov     rcx, r15
0x18002239d  mov     rax, [rax+28h]
0x1800223a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a6  mov     ebx, eax
0x1800223a8  test    eax, eax
0x1800223aa  js      loc_18002256A
0x1800223b0  mov     rbx, cs:hModule
0x1800223b7  mov     edi, 104h
0x1800223bc  mov     r8d, edi; nSize
0x1800223bf  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800223c3  mov     rcx, rbx; hModule
0x1800223c6  call    cs:__imp_GetModuleFileNameW
0x1800223cc  test    eax, eax
0x1800223ce  jnz     short loc_1800223DA
0x1800223d0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800223d5  jmp     loc_180022568
0x1800223da  cmp     eax, edi
0x1800223dc  jnz     short loc_1800223E8
0x1800223de  mov     ebx, 8007007Ah
0x1800223e3  jmp     loc_18002256A
0x1800223e8  lea     rdx, [rbp+0A00h+Filename]
0x1800223ec  mov     ecx, r13d
0x1800223ef  mov     r9d, 27h ; '''
0x1800223f5  movzx   r8d, word ptr [rdx]
0x1800223f9  test    r8w, r8w
0x1800223fd  jz      short loc_18002242F
0x1800223ff  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180022408  cmp     r8w, r9w
0x18002240c  jnz     short loc_180022421
0x18002240e  cmp     ecx, 206h
0x180022414  jnb     short loc_180022421
0x180022416  inc     ecx
0x180022418  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180022421  add     rdx, 2
0x180022425  inc     ecx
0x180022427  cmp     ecx, 207h
0x18002242d  jb      short loc_1800223F5
0x18002242f  mov     [rbp+rcx*2+0A00h+Src], r13w
0x180022438  test    rbx, rbx
0x18002243b  jz      short loc_180022461
0x18002243d  xor     ecx, ecx; lpModuleName
0x18002243f  call    cs:__imp_GetModuleHandleW
0x180022445  cmp     rbx, rax
0x180022448  jz      short loc_180022461
0x18002244a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18002244f  call    cs:__imp_EnterCriticalSection
0x180022455  lea     r8, [rbp+0A00h+Src]
0x18002245c  jmp     loc_1800224FB
0x180022461  mov     edi, 22h ; '"'
0x180022466  mov     [rbp+0A00h+var_460], di
0x18002246d  lea     rcx, [rbp+0A00h+Src]
0x180022474  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022478  mov     rax, rbx
0x18002247b  inc     rax
0x18002247e  cmp     [rcx+rax*2], r13w
0x180022483  jnz     short loc_18002247B
0x180022485  inc     eax
0x180022487  movsxd  r8, eax
0x18002248a  add     r8, r8; Size
0x18002248d  jz      short loc_1800224AF
0x18002248f  cmp     r8, 414h
0x180022496  ja      loc_180022578
0x18002249c  lea     rdx, [rbp+0A00h+Src]; Src
0x1800224a3  lea     rcx, [rbp+0A00h+var_45E]; void *
0x1800224aa  call    memcpy_0
0x1800224af  lea     rax, [rbp+0A00h+var_460]
0x1800224b6  inc     rbx
0x1800224b9  cmp     [rax+rbx*2], r13w
0x1800224be  jnz     short loc_1800224B6
0x1800224c0  movsxd  rax, ebx
0x1800224c3  mov     [rbp+rax*2+0A00h+var_460], di
0x1800224cb  lea     rcx, ds:2[rax*2]
0x1800224d3  cmp     rcx, 418h
0x1800224da  jnb     loc_180022601
0x1800224e0  mov     [rbp+rcx+0A00h+var_460], r13w
0x1800224e9  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800224ee  call    cs:__imp_EnterCriticalSection
0x1800224f4  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800224fb  lea     rdx, aModule; "Module"
0x180022502  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180022507  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18002250c  mov     ebx, eax
0x18002250e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180022513  call    cs:__imp_LeaveCriticalSection
0x180022519  neg     ebx
0x18002251b  sbb     ebx, ebx
0x18002251d  mov     edi, 8007000Eh
0x180022522  not     ebx
0x180022524  and     ebx, edi
0x180022526  test    ebx, ebx
0x180022528  js      short loc_18002256A
0x18002252a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18002252f  call    cs:__imp_EnterCriticalSection
0x180022535  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x18002253c  lea     rdx, aModuleRaw; "Module_Raw"
0x180022543  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180022548  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18002254d  mov     ebx, eax
0x18002254f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180022554  call    cs:__imp_LeaveCriticalSection
0x18002255a  mov     ecx, ebx
0x18002255c  neg     ecx
0x18002255e  sbb     eax, eax
0x180022560  not     eax
0x180022562  and     eax, edi
0x180022564  test    ebx, ebx
0x180022566  jnz     short loc_18002258C
0x180022568  mov     ebx, eax
0x18002256a  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18002256f  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180022574  mov     eax, ebx
0x180022576  jmp     short loc_1800225D7
0x180022578  call    cs:__imp__o__errno
0x18002257e  mov     [rax], edi
0x180022580  call    _invalid_parameter_noinfo
0x180022585  mov     ebx, 80004005h
0x18002258a  jmp     short loc_18002256A
0x18002258c  test    r12d, r12d
0x18002258f  jz      short loc_1800225A0
0x180022591  test    r14, r14
0x180022594  jz      short loc_1800225C4
0x180022596  mov     [rsp+0B00h+var_AE0], 1
0x18002259e  jmp     short loc_1800225AA
0x1800225a0  test    r14, r14
0x1800225a3  jz      short loc_1800225C4
0x1800225a5  mov     [rsp+0B00h+var_AE0], r13d; int
0x1800225aa  lea     r9, aRegistry; "REGISTRY"
0x1800225b1  mov     r8, r14; unsigned __int16 *
0x1800225b4  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800225b8  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800225bd  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800225c2  jmp     short loc_180022568
0x1800225c4  mov     ebx, 80070057h
0x1800225c9  jmp     short loc_18002256A
0x1800225cb  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800225d0  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800225d5  mov     eax, edi
0x1800225d7  mov     rcx, [rbp+0A00h+var_40]
0x1800225de  xor     rcx, rsp; StackCookie
0x1800225e1  call    __security_check_cookie
0x1800225e6  mov     rbx, [rsp+0B00h+arg_10]
0x1800225ee  add     rsp, 0AD0h
0x1800225f5  pop     r15
0x1800225f7  pop     r14
0x1800225f9  pop     r13
0x1800225fb  pop     r12
0x1800225fd  pop     rdi
0x1800225fe  pop     rsi
0x1800225ff  pop     rbp
0x180022600  retn
0x180022601  call    __report_rangecheckfailure
```
