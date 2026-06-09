# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006bcc`
- end: `0x180006eec`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006ba0`
- `0x180007240`

## callees

- `0x180001550`
- `0x180001590`
- `0x180001e62`
- `0x18000407c`
- `0x18000428c`
- `0x180004e04`
- `0x1800054ac`
- `0x180005e98`
- `0x180006bcc`
- `0x180009f88`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006e71`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006e71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006d54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006dea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006d54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006dea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006cd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006cd1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006d44`

## string_xrefs

- `0x180006e96`: `REGISTRY`

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
  unsigned __int16 Src[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
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
      goto LABEL_34;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_33:
      v11 = Error;
      goto LABEL_34;
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
            goto LABEL_34;
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
          Error = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v27,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    a3 != 0);
        goto LABEL_33;
      }
    }
LABEL_34:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006bcc  mov     [rsp-8+arg_10], rbx
0x180006bd1  push    rbp
0x180006bd2  push    rsi
0x180006bd3  push    rdi
0x180006bd4  push    r12
0x180006bd6  push    r13
0x180006bd8  push    r14
0x180006bda  push    r15
0x180006bdc  lea     rbp, [rsp-9D0h]
0x180006be4  sub     rsp, 0AD0h
0x180006beb  mov     rax, cs:__security_cookie
0x180006bf2  xor     rax, rsp
0x180006bf5  mov     [rbp+0A00h+var_40], rax
0x180006bfc  mov     rbx, r9
0x180006bff  mov     r15d, r8d
0x180006c02  mov     r12d, edx
0x180006c05  mov     r14, rcx
0x180006c08  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180006c0f  mov     [rsp+0B00h+var_AD0], rax
0x180006c14  xor     r13d, r13d
0x180006c17  mov     [rsp+0B00h+var_AC8], r13
0x180006c1c  mov     [rsp+0B00h+var_AC0], r13
0x180006c21  mov     [rsp+0B00h+var_AB8], r13d
0x180006c26  xorps   xmm0, xmm0
0x180006c29  xor     eax, eax
0x180006c2b  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180006c30  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180006c35  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180006c3a  mov     [rsp+0B00h+var_A88], r13b
0x180006c3f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180006c44  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006c49  mov     edi, eax
0x180006c4b  test    eax, eax
0x180006c4d  js      loc_180006EB0
0x180006c53  mov     [rsp+0B00h+var_A88], 1
0x180006c58  test    rbx, rbx
0x180006c5b  jz      short loc_180006C9A
0x180006c5d  jmp     short loc_180006C92
0x180006c5f  mov     rsi, [rbx+8]
0x180006c63  test    rsi, rsi
0x180006c66  jz      short loc_180006C8E
0x180006c68  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006c6d  call    cs:__imp_EnterCriticalSection
0x180006c73  mov     r8, rsi; unsigned __int16 *
0x180006c76  mov     rdx, rdi; unsigned __int16 *
0x180006c79  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006c7e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006c83  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006c88  call    cs:__imp_LeaveCriticalSection
0x180006c8e  add     rbx, 10h
0x180006c92  mov     rdi, [rbx]
0x180006c95  test    rdi, rdi
0x180006c98  jnz     short loc_180006C5F
0x180006c9a  mov     rax, [r14]
0x180006c9d  lea     rdx, [rsp+0B00h+var_AD0]
0x180006ca2  mov     rcx, r14
0x180006ca5  mov     rax, [rax+28h]
0x180006ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cae  mov     ebx, eax
0x180006cb0  test    eax, eax
0x180006cb2  js      loc_180006E63
0x180006cb8  mov     rbx, cs:hModule
0x180006cbf  mov     edi, 104h
0x180006cc4  mov     r8d, edi; nSize
0x180006cc7  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180006cce  mov     rcx, rbx; hModule
0x180006cd1  call    cs:__imp_GetModuleFileNameW
0x180006cd7  test    eax, eax
0x180006cd9  jnz     short loc_180006CE5
0x180006cdb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006ce0  jmp     loc_180006E61
0x180006ce5  cmp     eax, edi
0x180006ce7  jnz     short loc_180006CF3
0x180006ce9  mov     ebx, 8007007Ah
0x180006cee  jmp     loc_180006E63
0x180006cf3  lea     rdx, [rbp+0A00h+Filename]
0x180006cfa  mov     ecx, r13d
0x180006cfd  mov     r9d, 27h ; '''
0x180006d03  movzx   r8d, word ptr [rdx]
0x180006d07  test    r8w, r8w
0x180006d0b  jz      short loc_180006D37
0x180006d0d  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180006d13  cmp     r8w, r9w
0x180006d17  jnz     short loc_180006D29
0x180006d19  cmp     ecx, 206h
0x180006d1f  jnb     short loc_180006D29
0x180006d21  inc     ecx
0x180006d23  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180006d29  add     rdx, 2
0x180006d2d  inc     ecx
0x180006d2f  cmp     ecx, 207h
0x180006d35  jb      short loc_180006D03
0x180006d37  mov     [rbp+rcx*2+0A00h+Src], r13w
0x180006d3d  test    rbx, rbx
0x180006d40  jz      short loc_180006D63
0x180006d42  xor     ecx, ecx; lpModuleName
0x180006d44  call    cs:__imp_GetModuleHandleW
0x180006d4a  cmp     rbx, rax
0x180006d4d  jz      short loc_180006D63
0x180006d4f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006d54  call    cs:__imp_EnterCriticalSection
0x180006d5a  lea     r8, [rbp+0A00h+Src]
0x180006d5e  jmp     loc_180006DF7
0x180006d63  mov     edi, 22h ; '"'
0x180006d68  mov     [rbp+0A00h+var_460], di
0x180006d6f  lea     rcx, [rbp+0A00h+Src]
0x180006d73  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006d77  mov     rax, rbx
0x180006d7a  inc     rax
0x180006d7d  cmp     [rcx+rax*2], r13w
0x180006d82  jnz     short loc_180006D7A
0x180006d84  inc     eax
0x180006d86  movsxd  r8, eax
0x180006d89  add     r8, r8; Size
0x180006d8c  jz      short loc_180006DAB
0x180006d8e  cmp     r8, 414h
0x180006d95  ja      loc_180006E71
0x180006d9b  lea     rdx, [rbp+0A00h+Src]; Src
0x180006d9f  lea     rcx, [rbp+0A00h+var_45E]; void *
0x180006da6  call    memcpy_0
0x180006dab  lea     rax, [rbp+0A00h+var_460]
0x180006db2  inc     rbx
0x180006db5  cmp     [rax+rbx*2], r13w
0x180006dba  jnz     short loc_180006DB2
0x180006dbc  movsxd  rax, ebx
0x180006dbf  mov     [rbp+rax*2+0A00h+var_460], di
0x180006dc7  lea     rcx, ds:2[rax*2]
0x180006dcf  cmp     rcx, 418h
0x180006dd6  jnb     loc_180006EE6
0x180006ddc  mov     [rbp+rcx+0A00h+var_460], r13w
0x180006de5  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006dea  call    cs:__imp_EnterCriticalSection
0x180006df0  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180006df7  lea     rdx, aModule; "Module"
0x180006dfe  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006e03  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006e08  mov     ebx, eax
0x180006e0a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006e0f  call    cs:__imp_LeaveCriticalSection
0x180006e15  neg     ebx
0x180006e17  sbb     ebx, ebx
0x180006e19  mov     edi, 8007000Eh
0x180006e1e  not     ebx
0x180006e20  and     ebx, edi
0x180006e22  test    ebx, ebx
0x180006e24  js      short loc_180006E63
0x180006e26  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006e2b  call    cs:__imp_EnterCriticalSection
0x180006e31  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x180006e35  lea     rdx, aModuleRaw; "Module_Raw"
0x180006e3c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006e41  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006e46  mov     ebx, eax
0x180006e48  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006e4d  call    cs:__imp_LeaveCriticalSection
0x180006e53  mov     ecx, ebx
0x180006e55  neg     ecx
0x180006e57  sbb     eax, eax
0x180006e59  not     eax
0x180006e5b  and     eax, edi
0x180006e5d  test    ebx, ebx
0x180006e5f  jnz     short loc_180006E85
0x180006e61  mov     ebx, eax
0x180006e63  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006e68  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006e6d  mov     eax, ebx
0x180006e6f  jmp     short loc_180006EBC
0x180006e71  call    cs:__imp__o__errno
0x180006e77  mov     [rax], edi
0x180006e79  call    _invalid_parameter_noinfo
0x180006e7e  mov     ebx, 80004005h
0x180006e83  jmp     short loc_180006E63
0x180006e85  mov     eax, r13d
0x180006e88  test    r15d, r15d
0x180006e8b  setnz   al
0x180006e8e  movzx   r8d, r12w; unsigned __int16 *
0x180006e92  mov     [rsp+0B00h+var_AE0], eax; int
0x180006e96  lea     r9, aRegistry; "REGISTRY"
0x180006e9d  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006ea4  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006ea9  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180006eae  jmp     short loc_180006E61
0x180006eb0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006eb5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006eba  mov     eax, edi
0x180006ebc  mov     rcx, [rbp+0A00h+var_40]
0x180006ec3  xor     rcx, rsp; StackCookie
0x180006ec6  call    __security_check_cookie
0x180006ecb  mov     rbx, [rsp+0B00h+arg_10]
0x180006ed3  add     rsp, 0AD0h
0x180006eda  pop     r15
0x180006edc  pop     r14
0x180006ede  pop     r13
0x180006ee0  pop     r12
0x180006ee2  pop     rdi
0x180006ee3  pop     rsi
0x180006ee4  pop     rbp
0x180006ee5  retn
0x180006ee6  call    __report_rangecheckfailure
```
