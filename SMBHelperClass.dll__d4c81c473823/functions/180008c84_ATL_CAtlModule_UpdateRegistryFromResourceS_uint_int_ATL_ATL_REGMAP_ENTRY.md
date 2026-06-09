# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180008c84`
- end: `0x180008fae`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `810`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008c70`
- `0x180009e20`
- `0x180009f30`

## callees

- `0x180002338`
- `0x180003744`
- `0x180003ba8`
- `0x180004648`
- `0x1800058dc`
- `0x18000766c`
- `0x180008c84`
- `0x18000fc30`
- `0x180012010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008e65`
- `msvcrt!memcpy_s` at `0x180008e65`
- `KERNEL32!GetModuleHandleW` at `0x180008e04`
- `KERNEL32!GetModuleHandleW` at `0x180008e04`
- `KERNEL32!LeaveCriticalSection` at `0x180008d43`
- `KERNEL32!LeaveCriticalSection` at `0x180008ed7`
- `KERNEL32!LeaveCriticalSection` at `0x180008f18`
- `KERNEL32!LeaveCriticalSection` at `0x180008d43`
- `KERNEL32!LeaveCriticalSection` at `0x180008ed7`
- `KERNEL32!LeaveCriticalSection` at `0x180008f18`
- `KERNEL32!EnterCriticalSection` at `0x180008d28`
- `KERNEL32!EnterCriticalSection` at `0x180008e14`
- `KERNEL32!EnterCriticalSection` at `0x180008eb2`
- `KERNEL32!EnterCriticalSection` at `0x180008ef3`
- `KERNEL32!EnterCriticalSection` at `0x180008d28`
- `KERNEL32!EnterCriticalSection` at `0x180008e14`
- `KERNEL32!EnterCriticalSection` at `0x180008eb2`
- `KERNEL32!EnterCriticalSection` at `0x180008ef3`
- `KERNEL32!GetModuleFileNameW` at `0x180008d89`
- `KERNEL32!GetModuleFileNameW` at `0x180008d89`

## string_xrefs

- `0x180008f30`: `REGISTRY`

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
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
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
  v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
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
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, v23, L"REGISTRY", 1);
        else
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, v23, L"REGISTRY", 0);
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
0x180008c84  mov     [rsp-8+arg_0], rbx
0x180008c89  mov     [rsp-8+arg_8], rsi
0x180008c8e  push    rbp
0x180008c8f  push    rdi
0x180008c90  push    r12
0x180008c92  push    r14
0x180008c94  push    r15
0x180008c96  lea     rbp, [rsp-9D0h]
0x180008c9e  sub     rsp, 0AD0h
0x180008ca5  mov     rax, cs:__security_cookie
0x180008cac  xor     rax, rsp
0x180008caf  mov     [rbp+9F0h+var_30], rax
0x180008cb6  mov     rbx, r9
0x180008cb9  mov     r15d, r8d
0x180008cbc  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008cc3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008cca  mov     [rsp+0AF0h+var_AC0], rax
0x180008ccf  xor     r12d, r12d
0x180008cd2  mov     [rsp+0AF0h+var_AB8], r12
0x180008cd7  mov     [rsp+0AF0h+var_AB0], r12
0x180008cdc  mov     [rsp+0AF0h+var_AA8], r12d
0x180008ce1  xorps   xmm0, xmm0
0x180008ce4  xor     eax, eax
0x180008ce6  movups  xmmword ptr [rsp+0AF0h+CriticalSection.DebugInfo], xmm0
0x180008ceb  movups  xmmword ptr [rsp+0AF0h+CriticalSection.OwningThread], xmm0
0x180008cf0  mov     [rsp+0AF0h+CriticalSection.SpinCount], rax
0x180008cf5  mov     [rsp+0AF0h+var_A78], r12b
0x180008cfa  lea     rcx, [rsp+0AF0h+CriticalSection]; this
0x180008cff  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008d04  mov     edi, eax
0x180008d06  test    eax, eax
0x180008d08  js      loc_180008F71
0x180008d0e  mov     [rsp+0AF0h+var_A78], 1
0x180008d13  test    rbx, rbx
0x180008d16  jz      short loc_180008D55
0x180008d18  jmp     short loc_180008D4D
0x180008d1a  mov     rsi, [rbx+8]
0x180008d1e  test    rsi, rsi
0x180008d21  jz      short loc_180008D49
0x180008d23  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180008d28  call    cs:__imp_EnterCriticalSection
0x180008d2e  mov     r8, rsi; unsigned __int16 *
0x180008d31  mov     rdx, rdi; unsigned __int16 *
0x180008d34  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x180008d39  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008d3e  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180008d43  call    cs:__imp_LeaveCriticalSection
0x180008d49  add     rbx, 10h
0x180008d4d  mov     rdi, [rbx]
0x180008d50  test    rdi, rdi
0x180008d53  jnz     short loc_180008D1A
0x180008d55  mov     rax, [r14]
0x180008d58  lea     rdx, [rsp+0AF0h+var_AC0]
0x180008d5d  mov     rcx, r14
0x180008d60  mov     rax, [rax+28h]
0x180008d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d69  mov     ebx, eax
0x180008d6b  test    eax, eax
0x180008d6d  js      loc_180008F63
0x180008d73  mov     rbx, cs:hInstance
0x180008d7a  mov     edi, 104h
0x180008d7f  mov     r8d, edi; nSize
0x180008d82  lea     rdx, [rbp+9F0h+Filename]; lpFilename
0x180008d86  mov     rcx, rbx; hModule
0x180008d89  call    cs:__imp_GetModuleFileNameW
0x180008d8f  test    eax, eax
0x180008d91  jnz     short loc_180008D9F
0x180008d93  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008d98  mov     ebx, eax
0x180008d9a  jmp     loc_180008F63
0x180008d9f  cmp     eax, edi
0x180008da1  jnz     short loc_180008DAD
0x180008da3  mov     ebx, 8007007Ah
0x180008da8  jmp     loc_180008F63
0x180008dad  lea     rdx, [rbp+9F0h+Filename]
0x180008db1  mov     ecx, r12d
0x180008db4  mov     r9d, 27h ; '''
0x180008dba  movzx   r8d, word ptr [rdx]
0x180008dbe  test    r8w, r8w
0x180008dc2  jz      short loc_180008DF4
0x180008dc4  mov     [rbp+rcx*2+9F0h+Source], r8w
0x180008dcd  cmp     r8w, r9w
0x180008dd1  jnz     short loc_180008DE6
0x180008dd3  cmp     ecx, 206h
0x180008dd9  jnb     short loc_180008DE6
0x180008ddb  inc     ecx
0x180008ddd  mov     [rbp+rcx*2+9F0h+Source], r9w
0x180008de6  add     rdx, 2
0x180008dea  inc     ecx
0x180008dec  cmp     ecx, 207h
0x180008df2  jb      short loc_180008DBA
0x180008df4  mov     [rbp+rcx*2+9F0h+Source], r12w
0x180008dfd  test    rbx, rbx
0x180008e00  jz      short loc_180008E26
0x180008e02  xor     ecx, ecx; lpModuleName
0x180008e04  call    cs:__imp_GetModuleHandleW
0x180008e0a  cmp     rbx, rax
0x180008e0d  jz      short loc_180008E26
0x180008e0f  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180008e14  call    cs:__imp_EnterCriticalSection
0x180008e1a  lea     r8, [rbp+9F0h+Source]
0x180008e21  jmp     loc_180008EBF
0x180008e26  mov     edi, 22h ; '"'
0x180008e2b  mov     [rbp+9F0h+var_450], di
0x180008e32  lea     rcx, [rbp+9F0h+Source]
0x180008e39  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008e3d  mov     rax, rbx
0x180008e40  inc     rax
0x180008e43  cmp     [rcx+rax*2], r12w
0x180008e48  jnz     short loc_180008E40
0x180008e4a  inc     eax
0x180008e4c  movsxd  r9, eax
0x180008e4f  add     r9, r9; SourceSize
0x180008e52  lea     r8, [rbp+9F0h+Source]; Source
0x180008e59  mov     edx, 414h; DestinationSize
0x180008e5e  lea     rcx, [rbp+9F0h+Destination]; Destination
0x180008e65  call    cs:__imp_memcpy_s
0x180008e6b  test    eax, eax
0x180008e6d  jnz     loc_180008F5E
0x180008e73  lea     rax, [rbp+9F0h+var_450]
0x180008e7a  inc     rbx
0x180008e7d  cmp     [rax+rbx*2], r12w
0x180008e82  jnz     short loc_180008E7A
0x180008e84  movsxd  rax, ebx
0x180008e87  mov     [rbp+rax*2+9F0h+var_450], di
0x180008e8f  lea     rcx, ds:2[rax*2]
0x180008e97  cmp     rcx, 418h
0x180008e9e  jnb     loc_180008FA8
0x180008ea4  mov     [rbp+rcx+9F0h+var_450], r12w
0x180008ead  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180008eb2  call    cs:__imp_EnterCriticalSection
0x180008eb8  lea     r8, [rbp+9F0h+var_450]; unsigned __int16 *
0x180008ebf  lea     rdx, aModule; "Module"
0x180008ec6  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x180008ecb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008ed0  mov     ebx, eax
0x180008ed2  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180008ed7  call    cs:__imp_LeaveCriticalSection
0x180008edd  neg     ebx
0x180008edf  sbb     ebx, ebx
0x180008ee1  mov     edi, 8007000Eh
0x180008ee6  not     ebx
0x180008ee8  and     ebx, edi
0x180008eea  test    ebx, ebx
0x180008eec  js      short loc_180008F63
0x180008eee  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180008ef3  call    cs:__imp_EnterCriticalSection
0x180008ef9  lea     r8, [rbp+9F0h+Source]; unsigned __int16 *
0x180008f00  lea     rdx, aModuleRaw; "Module_Raw"
0x180008f07  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x180008f0c  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008f11  mov     ebx, eax
0x180008f13  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180008f18  call    cs:__imp_LeaveCriticalSection
0x180008f1e  mov     ecx, ebx
0x180008f20  neg     ecx
0x180008f22  sbb     eax, eax
0x180008f24  not     eax
0x180008f26  and     eax, edi
0x180008f28  test    ebx, ebx
0x180008f2a  jz      loc_180008D98
0x180008f30  lea     r9, aRegistry; "REGISTRY"
0x180008f37  lea     rdx, [rbp+9F0h+Filename]; unsigned __int16 *
0x180008f3b  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180008f40  test    r15d, r15d
0x180008f43  jz      short loc_180008F4F
0x180008f45  mov     [rsp+0AF0h+var_AD0], 1
0x180008f4d  jmp     short loc_180008F54
0x180008f4f  mov     [rsp+0AF0h+var_AD0], r12d; int
0x180008f54  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008f59  jmp     loc_180008D98
0x180008f5e  mov     ebx, 80004005h
0x180008f63  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180008f68  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008f6d  mov     eax, ebx
0x180008f6f  jmp     short loc_180008F7D
0x180008f71  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180008f76  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008f7b  mov     eax, edi
0x180008f7d  mov     rcx, [rbp+9F0h+var_30]
0x180008f84  xor     rcx, rsp; StackCookie
0x180008f87  call    __security_check_cookie
0x180008f8c  lea     r11, [rsp+0AF0h+var_20]
0x180008f94  mov     rbx, [r11+30h]
0x180008f98  mov     rsi, [r11+38h]
0x180008f9c  mov     rsp, r11
0x180008f9f  pop     r15
0x180008fa1  pop     r14
0x180008fa3  pop     r12
0x180008fa5  pop     rdi
0x180008fa6  pop     rbp
0x180008fa7  retn
0x180008fa8  call    __report_rangecheckfailure
```
