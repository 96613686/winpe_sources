# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140005f04`
- end: `0x14000622e`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `810`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, __int64, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004210`

## callees

- `0x140001f38`
- `0x140002768`
- `0x1400028c0`
- `0x1400032f8`
- `0x140003dfc`
- `0x140004eb8`
- `0x140005f04`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400060e5`
- `msvcrt!memcpy_s` at `0x1400060e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006084`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006084`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140006009`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140006009`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005fc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006198`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005fc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140006198`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005fa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006094`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005fa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006094`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006173`

## string_xrefs

- `0x1400061b0`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v6; // r14
  int v7; // edi
  const unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // rdi
  signed int v10; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v21; // ebx
  int v22; // ebx
  const unsigned __int16 *v23; // r8
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Source[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v6 = ATL::_pAtlModule;
  v25 = &ATL::CRegObject::`vftable';
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v29 = 0;
  v7 = ATL::CComCriticalSection::Init(&CriticalSection);
  if ( v7 >= 0 )
  {
    v29 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v9 = *(const unsigned __int16 **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v8 = (const unsigned __int16 *)*((_QWORD *)a4 + 1);
        if ( v8 )
        {
          EnterCriticalSection(&CriticalSection);
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, v9, v8);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v10 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v6 + 40LL))(v6, &v25);
    if ( v10 < 0 )
      goto LABEL_36;
    v11 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v10 = -2147024774;
        goto LABEL_36;
      }
      v14 = Filename;
      v15 = 0;
      do
      {
        v16 = *v14;
        if ( !*v14 )
          break;
        Source[v15] = v16;
        if ( v16 == 39 && (unsigned int)v15 < 0x206 )
        {
          LODWORD(v15) = v15 + 1;
          Source[(unsigned int)v15] = 39;
        }
        ++v14;
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < 0x207 );
      Source[v15] = 0;
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v32 = 34;
        v18 = -1;
        v19 = -1;
        do
          ++v19;
        while ( Source[v19] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v19 + 1)) )
        {
          v10 = -2147467259;
          goto LABEL_36;
        }
        do
          ++v18;
        while ( *(_WORD *)&Destination[2 * v18 - 2] );
        *(_WORD *)&Destination[2 * (int)v18 - 2] = 34;
        v20 = 2LL * (int)v18 + 2;
        if ( v20 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v20 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v17 = &v32;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v17 = Source;
      }
      v21 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module", v17);
      LeaveCriticalSection(&CriticalSection);
      v10 = v21 == 0 ? 0x8007000E : 0;
      if ( v10 < 0 )
      {
LABEL_36:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v10;
      }
      EnterCriticalSection(&CriticalSection);
      v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v22 == 0 ? 0x8007000E : 0;
      if ( v22 )
      {
        if ( a3 )
          Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v25, Filename, v23, L"REGISTRY", 1);
        else
          Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v25, Filename, v23, L"REGISTRY", 0);
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v10 = Error;
    goto LABEL_36;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140005f04  mov     [rsp-8+arg_0], rbx
0x140005f09  mov     [rsp-8+arg_8], rsi
0x140005f0e  push    rbp
0x140005f0f  push    rdi
0x140005f10  push    r12
0x140005f12  push    r14
0x140005f14  push    r15
0x140005f16  lea     rbp, [rsp-9D0h]
0x140005f1e  sub     rsp, 0AD0h
0x140005f25  mov     rax, cs:__security_cookie
0x140005f2c  xor     rax, rsp
0x140005f2f  mov     [rbp+9F0h+var_30], rax
0x140005f36  mov     rbx, r9
0x140005f39  mov     r15d, r8d
0x140005f3c  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005f43  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140005f4a  mov     [rsp+0AF0h+var_AC0], rax
0x140005f4f  xor     r12d, r12d
0x140005f52  mov     [rsp+0AF0h+var_AB8], r12
0x140005f57  mov     [rsp+0AF0h+var_AB0], r12
0x140005f5c  mov     [rsp+0AF0h+var_AA8], r12d
0x140005f61  xorps   xmm0, xmm0
0x140005f64  xor     eax, eax
0x140005f66  movups  xmmword ptr [rsp+0AF0h+CriticalSection.DebugInfo], xmm0
0x140005f6b  movups  xmmword ptr [rsp+0AF0h+CriticalSection.OwningThread], xmm0
0x140005f70  mov     [rsp+0AF0h+CriticalSection.SpinCount], rax
0x140005f75  mov     [rsp+0AF0h+var_A78], r12b
0x140005f7a  lea     rcx, [rsp+0AF0h+CriticalSection]; this
0x140005f7f  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140005f84  mov     edi, eax
0x140005f86  test    eax, eax
0x140005f88  js      loc_1400061F1
0x140005f8e  mov     [rsp+0AF0h+var_A78], 1
0x140005f93  test    rbx, rbx
0x140005f96  jz      short loc_140005FD5
0x140005f98  jmp     short loc_140005FCD
0x140005f9a  mov     rsi, [rbx+8]
0x140005f9e  test    rsi, rsi
0x140005fa1  jz      short loc_140005FC9
0x140005fa3  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x140005fa8  call    cs:__imp_EnterCriticalSection
0x140005fae  mov     r8, rsi; unsigned __int16 *
0x140005fb1  mov     rdx, rdi; unsigned __int16 *
0x140005fb4  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x140005fb9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140005fbe  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x140005fc3  call    cs:__imp_LeaveCriticalSection
0x140005fc9  add     rbx, 10h
0x140005fcd  mov     rdi, [rbx]
0x140005fd0  test    rdi, rdi
0x140005fd3  jnz     short loc_140005F9A
0x140005fd5  mov     rax, [r14]
0x140005fd8  lea     rdx, [rsp+0AF0h+var_AC0]
0x140005fdd  mov     rcx, r14
0x140005fe0  mov     rax, [rax+28h]
0x140005fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fe9  mov     ebx, eax
0x140005feb  test    eax, eax
0x140005fed  js      loc_1400061E3
0x140005ff3  mov     rbx, cs:hInstance
0x140005ffa  mov     edi, 104h
0x140005fff  mov     r8d, edi; nSize
0x140006002  lea     rdx, [rbp+9F0h+Filename]; lpFilename
0x140006006  mov     rcx, rbx; hModule
0x140006009  call    cs:__imp_GetModuleFileNameW
0x14000600f  test    eax, eax
0x140006011  jnz     short loc_14000601F
0x140006013  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140006018  mov     ebx, eax
0x14000601a  jmp     loc_1400061E3
0x14000601f  cmp     eax, edi
0x140006021  jnz     short loc_14000602D
0x140006023  mov     ebx, 8007007Ah
0x140006028  jmp     loc_1400061E3
0x14000602d  lea     rdx, [rbp+9F0h+Filename]
0x140006031  mov     ecx, r12d
0x140006034  mov     r9d, 27h ; '''
0x14000603a  movzx   r8d, word ptr [rdx]
0x14000603e  test    r8w, r8w
0x140006042  jz      short loc_140006074
0x140006044  mov     [rbp+rcx*2+9F0h+Source], r8w
0x14000604d  cmp     r8w, r9w
0x140006051  jnz     short loc_140006066
0x140006053  cmp     ecx, 206h
0x140006059  jnb     short loc_140006066
0x14000605b  inc     ecx
0x14000605d  mov     [rbp+rcx*2+9F0h+Source], r9w
0x140006066  add     rdx, 2
0x14000606a  inc     ecx
0x14000606c  cmp     ecx, 207h
0x140006072  jb      short loc_14000603A
0x140006074  mov     [rbp+rcx*2+9F0h+Source], r12w
0x14000607d  test    rbx, rbx
0x140006080  jz      short loc_1400060A6
0x140006082  xor     ecx, ecx; lpModuleName
0x140006084  call    cs:__imp_GetModuleHandleW
0x14000608a  cmp     rbx, rax
0x14000608d  jz      short loc_1400060A6
0x14000608f  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x140006094  call    cs:__imp_EnterCriticalSection
0x14000609a  lea     r8, [rbp+9F0h+Source]
0x1400060a1  jmp     loc_14000613F
0x1400060a6  mov     edi, 22h ; '"'
0x1400060ab  mov     [rbp+9F0h+var_450], di
0x1400060b2  lea     rcx, [rbp+9F0h+Source]
0x1400060b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400060bd  mov     rax, rbx
0x1400060c0  inc     rax
0x1400060c3  cmp     [rcx+rax*2], r12w
0x1400060c8  jnz     short loc_1400060C0
0x1400060ca  inc     eax
0x1400060cc  movsxd  r9, eax
0x1400060cf  add     r9, r9; SourceSize
0x1400060d2  lea     r8, [rbp+9F0h+Source]; Source
0x1400060d9  mov     edx, 414h; DestinationSize
0x1400060de  lea     rcx, [rbp+9F0h+Destination]; Destination
0x1400060e5  call    cs:__imp_memcpy_s
0x1400060eb  test    eax, eax
0x1400060ed  jnz     loc_1400061DE
0x1400060f3  lea     rax, [rbp+9F0h+var_450]
0x1400060fa  inc     rbx
0x1400060fd  cmp     [rax+rbx*2], r12w
0x140006102  jnz     short loc_1400060FA
0x140006104  movsxd  rax, ebx
0x140006107  mov     [rbp+rax*2+9F0h+var_450], di
0x14000610f  lea     rcx, ds:2[rax*2]
0x140006117  cmp     rcx, 418h
0x14000611e  jnb     loc_140006228
0x140006124  mov     [rbp+rcx+9F0h+var_450], r12w
0x14000612d  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x140006132  call    cs:__imp_EnterCriticalSection
0x140006138  lea     r8, [rbp+9F0h+var_450]; unsigned __int16 *
0x14000613f  lea     rdx, aModule; "Module"
0x140006146  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x14000614b  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140006150  mov     ebx, eax
0x140006152  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x140006157  call    cs:__imp_LeaveCriticalSection
0x14000615d  neg     ebx
0x14000615f  sbb     ebx, ebx
0x140006161  mov     edi, 8007000Eh
0x140006166  not     ebx
0x140006168  and     ebx, edi
0x14000616a  test    ebx, ebx
0x14000616c  js      short loc_1400061E3
0x14000616e  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x140006173  call    cs:__imp_EnterCriticalSection
0x140006179  lea     r8, [rbp+9F0h+Source]; unsigned __int16 *
0x140006180  lea     rdx, aModuleRaw; "Module_Raw"
0x140006187  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x14000618c  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140006191  mov     ebx, eax
0x140006193  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x140006198  call    cs:__imp_LeaveCriticalSection
0x14000619e  mov     ecx, ebx
0x1400061a0  neg     ecx
0x1400061a2  sbb     eax, eax
0x1400061a4  not     eax
0x1400061a6  and     eax, edi
0x1400061a8  test    ebx, ebx
0x1400061aa  jz      loc_140006018
0x1400061b0  lea     r9, aRegistry; "REGISTRY"
0x1400061b7  lea     rdx, [rbp+9F0h+Filename]; unsigned __int16 *
0x1400061bb  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x1400061c0  test    r15d, r15d
0x1400061c3  jz      short loc_1400061CF
0x1400061c5  mov     [rsp+0AF0h+var_AD0], 1
0x1400061cd  jmp     short loc_1400061D4
0x1400061cf  mov     [rsp+0AF0h+var_AD0], r12d; int
0x1400061d4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1400061d9  jmp     loc_140006018
0x1400061de  mov     ebx, 80004005h
0x1400061e3  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x1400061e8  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1400061ed  mov     eax, ebx
0x1400061ef  jmp     short loc_1400061FD
0x1400061f1  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x1400061f6  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1400061fb  mov     eax, edi
0x1400061fd  mov     rcx, [rbp+9F0h+var_30]
0x140006204  xor     rcx, rsp; StackCookie
0x140006207  call    __security_check_cookie
0x14000620c  lea     r11, [rsp+0AF0h+var_20]
0x140006214  mov     rbx, [r11+30h]
0x140006218  mov     rsi, [r11+38h]
0x14000621c  mov     rsp, r11
0x14000621f  pop     r15
0x140006221  pop     r14
0x140006223  pop     r12
0x140006225  pop     rdi
0x140006226  pop     rbp
0x140006227  retn
0x140006228  call    __report_rangecheckfailure
```
