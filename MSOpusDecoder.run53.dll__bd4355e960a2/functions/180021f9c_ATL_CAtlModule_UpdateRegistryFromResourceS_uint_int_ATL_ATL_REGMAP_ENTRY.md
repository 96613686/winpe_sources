# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180021f9c`
- end: `0x1800222bc`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180021f70`
- `0x180022610`

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
- `0x180021f9c`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022241`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180022241`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002203d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800221ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800221fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002203d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800221ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800221fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022058`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800221df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002221d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022058`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800221df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002221d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800220a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800220a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022114`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022114`

## string_xrefs

- `0x180022266`: `REGISTRY`

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
0x180021f9c  mov     [rsp-8+arg_10], rbx
0x180021fa1  push    rbp
0x180021fa2  push    rsi
0x180021fa3  push    rdi
0x180021fa4  push    r12
0x180021fa6  push    r13
0x180021fa8  push    r14
0x180021faa  push    r15
0x180021fac  lea     rbp, [rsp-9D0h]
0x180021fb4  sub     rsp, 0AD0h
0x180021fbb  mov     rax, cs:__security_cookie
0x180021fc2  xor     rax, rsp
0x180021fc5  mov     [rbp+0A00h+var_40], rax
0x180021fcc  mov     rbx, r9
0x180021fcf  mov     r15d, r8d
0x180021fd2  mov     r12d, edx
0x180021fd5  mov     r14, rcx
0x180021fd8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180021fdf  mov     [rsp+0B00h+var_AD0], rax
0x180021fe4  xor     r13d, r13d
0x180021fe7  mov     [rsp+0B00h+var_AC8], r13
0x180021fec  mov     [rsp+0B00h+var_AC0], r13
0x180021ff1  mov     [rsp+0B00h+var_AB8], r13d
0x180021ff6  xorps   xmm0, xmm0
0x180021ff9  xor     eax, eax
0x180021ffb  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180022000  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180022005  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18002200a  mov     [rsp+0B00h+var_A88], r13b
0x18002200f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180022014  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180022019  mov     edi, eax
0x18002201b  test    eax, eax
0x18002201d  js      loc_180022280
0x180022023  mov     [rsp+0B00h+var_A88], 1
0x180022028  test    rbx, rbx
0x18002202b  jz      short loc_18002206A
0x18002202d  jmp     short loc_180022062
0x18002202f  mov     rsi, [rbx+8]
0x180022033  test    rsi, rsi
0x180022036  jz      short loc_18002205E
0x180022038  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18002203d  call    cs:__imp_EnterCriticalSection
0x180022043  mov     r8, rsi; unsigned __int16 *
0x180022046  mov     rdx, rdi; unsigned __int16 *
0x180022049  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18002204e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180022053  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180022058  call    cs:__imp_LeaveCriticalSection
0x18002205e  add     rbx, 10h
0x180022062  mov     rdi, [rbx]
0x180022065  test    rdi, rdi
0x180022068  jnz     short loc_18002202F
0x18002206a  mov     rax, [r14]
0x18002206d  lea     rdx, [rsp+0B00h+var_AD0]
0x180022072  mov     rcx, r14
0x180022075  mov     rax, [rax+28h]
0x180022079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002207e  mov     ebx, eax
0x180022080  test    eax, eax
0x180022082  js      loc_180022233
0x180022088  mov     rbx, cs:hModule
0x18002208f  mov     edi, 104h
0x180022094  mov     r8d, edi; nSize
0x180022097  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18002209e  mov     rcx, rbx; hModule
0x1800220a1  call    cs:__imp_GetModuleFileNameW
0x1800220a7  test    eax, eax
0x1800220a9  jnz     short loc_1800220B5
0x1800220ab  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800220b0  jmp     loc_180022231
0x1800220b5  cmp     eax, edi
0x1800220b7  jnz     short loc_1800220C3
0x1800220b9  mov     ebx, 8007007Ah
0x1800220be  jmp     loc_180022233
0x1800220c3  lea     rdx, [rbp+0A00h+Filename]
0x1800220ca  mov     ecx, r13d
0x1800220cd  mov     r9d, 27h ; '''
0x1800220d3  movzx   r8d, word ptr [rdx]
0x1800220d7  test    r8w, r8w
0x1800220db  jz      short loc_180022107
0x1800220dd  mov     [rbp+rcx*2+0A00h+Src], r8w
0x1800220e3  cmp     r8w, r9w
0x1800220e7  jnz     short loc_1800220F9
0x1800220e9  cmp     ecx, 206h
0x1800220ef  jnb     short loc_1800220F9
0x1800220f1  inc     ecx
0x1800220f3  mov     [rbp+rcx*2+0A00h+Src], r9w
0x1800220f9  add     rdx, 2
0x1800220fd  inc     ecx
0x1800220ff  cmp     ecx, 207h
0x180022105  jb      short loc_1800220D3
0x180022107  mov     [rbp+rcx*2+0A00h+Src], r13w
0x18002210d  test    rbx, rbx
0x180022110  jz      short loc_180022133
0x180022112  xor     ecx, ecx; lpModuleName
0x180022114  call    cs:__imp_GetModuleHandleW
0x18002211a  cmp     rbx, rax
0x18002211d  jz      short loc_180022133
0x18002211f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180022124  call    cs:__imp_EnterCriticalSection
0x18002212a  lea     r8, [rbp+0A00h+Src]
0x18002212e  jmp     loc_1800221C7
0x180022133  mov     edi, 22h ; '"'
0x180022138  mov     [rbp+0A00h+var_460], di
0x18002213f  lea     rcx, [rbp+0A00h+Src]
0x180022143  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180022147  mov     rax, rbx
0x18002214a  inc     rax
0x18002214d  cmp     [rcx+rax*2], r13w
0x180022152  jnz     short loc_18002214A
0x180022154  inc     eax
0x180022156  movsxd  r8, eax
0x180022159  add     r8, r8; Size
0x18002215c  jz      short loc_18002217B
0x18002215e  cmp     r8, 414h
0x180022165  ja      loc_180022241
0x18002216b  lea     rdx, [rbp+0A00h+Src]; Src
0x18002216f  lea     rcx, [rbp+0A00h+var_45E]; void *
0x180022176  call    memcpy_0
0x18002217b  lea     rax, [rbp+0A00h+var_460]
0x180022182  inc     rbx
0x180022185  cmp     [rax+rbx*2], r13w
0x18002218a  jnz     short loc_180022182
0x18002218c  movsxd  rax, ebx
0x18002218f  mov     [rbp+rax*2+0A00h+var_460], di
0x180022197  lea     rcx, ds:2[rax*2]
0x18002219f  cmp     rcx, 418h
0x1800221a6  jnb     loc_1800222B6
0x1800221ac  mov     [rbp+rcx+0A00h+var_460], r13w
0x1800221b5  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800221ba  call    cs:__imp_EnterCriticalSection
0x1800221c0  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800221c7  lea     rdx, aModule; "Module"
0x1800221ce  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800221d3  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800221d8  mov     ebx, eax
0x1800221da  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800221df  call    cs:__imp_LeaveCriticalSection
0x1800221e5  neg     ebx
0x1800221e7  sbb     ebx, ebx
0x1800221e9  mov     edi, 8007000Eh
0x1800221ee  not     ebx
0x1800221f0  and     ebx, edi
0x1800221f2  test    ebx, ebx
0x1800221f4  js      short loc_180022233
0x1800221f6  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800221fb  call    cs:__imp_EnterCriticalSection
0x180022201  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x180022205  lea     rdx, aModuleRaw; "Module_Raw"
0x18002220c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180022211  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180022216  mov     ebx, eax
0x180022218  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18002221d  call    cs:__imp_LeaveCriticalSection
0x180022223  mov     ecx, ebx
0x180022225  neg     ecx
0x180022227  sbb     eax, eax
0x180022229  not     eax
0x18002222b  and     eax, edi
0x18002222d  test    ebx, ebx
0x18002222f  jnz     short loc_180022255
0x180022231  mov     ebx, eax
0x180022233  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180022238  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002223d  mov     eax, ebx
0x18002223f  jmp     short loc_18002228C
0x180022241  call    cs:__imp__o__errno
0x180022247  mov     [rax], edi
0x180022249  call    _invalid_parameter_noinfo
0x18002224e  mov     ebx, 80004005h
0x180022253  jmp     short loc_180022233
0x180022255  mov     eax, r13d
0x180022258  test    r15d, r15d
0x18002225b  setnz   al
0x18002225e  movzx   r8d, r12w; unsigned __int16 *
0x180022262  mov     [rsp+0B00h+var_AE0], eax; int
0x180022266  lea     r9, aRegistry; "REGISTRY"
0x18002226d  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180022274  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180022279  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18002227e  jmp     short loc_180022231
0x180022280  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180022285  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002228a  mov     eax, edi
0x18002228c  mov     rcx, [rbp+0A00h+var_40]
0x180022293  xor     rcx, rsp; StackCookie
0x180022296  call    __security_check_cookie
0x18002229b  mov     rbx, [rsp+0B00h+arg_10]
0x1800222a3  add     rsp, 0AD0h
0x1800222aa  pop     r15
0x1800222ac  pop     r14
0x1800222ae  pop     r13
0x1800222b0  pop     r12
0x1800222b2  pop     rdi
0x1800222b3  pop     rsi
0x1800222b4  pop     rbp
0x1800222b5  retn
0x1800222b6  call    __report_rangecheckfailure
```
