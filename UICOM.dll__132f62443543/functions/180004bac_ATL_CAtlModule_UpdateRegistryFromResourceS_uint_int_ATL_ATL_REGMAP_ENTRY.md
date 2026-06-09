# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180004bac`
- end: `0x180004e3c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `656`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180004f60`
- `0x1800050a0`
- `0x180005990`
- `0x180005da0`

## callees

- `0x180001898`
- `0x180002318`
- `0x180002448`
- `0x180002cd8`
- `0x180004038`
- `0x180004bac`
- `0x180005f60`
- `0x180007010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004d2d`
- `msvcrt!memcpy_s` at `0x180004d2d`
- `KERNEL32!GetModuleHandleW` at `0x180004cdd`
- `KERNEL32!GetModuleHandleW` at `0x180004cdd`
- `KERNEL32!GetModuleFileNameW` at `0x180004c68`
- `KERNEL32!GetModuleFileNameW` at `0x180004c68`

## string_xrefs

- `0x180004ddd`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        const unsigned __int16 **a4)
{
  struct ATL::CAtlModule *v4; // rdi
  const unsigned __int16 **v6; // rbx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v9; // r8
  signed int v10; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  signed int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v22; // eax
  void **v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+48h] [rbp-B8h]
  unsigned __int16 Source[520]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v29; // [rsp+680h] [rbp+580h] BYREF
  _BYTE Destination[1054]; // [rsp+682h] [rbp+582h] BYREF

  v4 = ATL::_pAtlModule;
  v24 = &ATL::CRegObject::`vftable';
  v26 = 0;
  v6 = a4;
  v25 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v6 )
    {
      v9 = v6[1];
      if ( v9 )
        ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, i, v9);
      v6 += 2;
    }
  }
  v10 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v4 + 40LL))(v4, &v24);
  if ( v10 < 0 )
    goto LABEL_31;
  v11 = hInstance;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v10 = Error;
LABEL_31:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
    return (unsigned int)v10;
  }
  if ( ModuleFileNameW == 260 )
  {
    v10 = -2147024774;
    goto LABEL_31;
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
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v17 = Source;
LABEL_28:
    if ( !-ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module", v17) )
    {
      v10 = -2147024882;
      goto LABEL_31;
    }
    v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v25, L"Module_Raw", Source);
    v10 = v22 == 0 ? 0x8007000E : 0;
    if ( !v22 )
      goto LABEL_31;
    Error = ATL::CRegObject::RegisterFromResource(
              (ATL::CRegObject *)&v24,
              Filename,
              (const unsigned __int16 *)a2,
              L"REGISTRY",
              a3 != 0);
    goto LABEL_10;
  }
  v18 = -1;
  v29 = 34;
  v19 = -1;
  do
    ++v19;
  while ( Source[v19] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v19 + 1)) )
  {
    do
      ++v18;
    while ( *(_WORD *)&Destination[2 * v18 - 2] );
    v20 = 2LL * (int)v18 + 2;
    *(_WORD *)&Destination[2 * (int)v18 - 2] = 34;
    if ( v20 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v20 - 2] = 0;
    v17 = &v29;
    goto LABEL_28;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v24);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180004bac  mov     [rsp-8+arg_0], rbx
0x180004bb1  push    rbp
0x180004bb2  push    rsi
0x180004bb3  push    rdi
0x180004bb4  push    r14
0x180004bb6  push    r15
0x180004bb8  lea     rbp, [rsp-9B0h]
0x180004bc0  sub     rsp, 0AB0h
0x180004bc7  mov     rax, cs:__security_cookie
0x180004bce  xor     rax, rsp
0x180004bd1  mov     [rbp+9D0h+var_30], rax
0x180004bd8  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004bdf  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180004be6  xor     r15d, r15d
0x180004be9  mov     r14d, edx
0x180004bec  mov     [rsp+0AD0h+var_AA0], rax
0x180004bf1  xorps   xmm0, xmm0
0x180004bf4  mov     [rsp+0AD0h+var_A88], r15d
0x180004bf9  mov     rbx, r9
0x180004bfc  mov     esi, r8d
0x180004bff  movdqu  [rsp+0AD0h+var_A98], xmm0
0x180004c05  test    r9, r9
0x180004c08  jz      short loc_180004C31
0x180004c0a  mov     rax, [r9]
0x180004c0d  jmp     short loc_180004C2C
0x180004c0f  mov     r8, [rbx+8]; unsigned __int16 *
0x180004c13  test    r8, r8
0x180004c16  jz      short loc_180004C25
0x180004c18  mov     rdx, rax; unsigned __int16 *
0x180004c1b  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180004c20  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004c25  add     rbx, 10h
0x180004c29  mov     rax, [rbx]
0x180004c2c  test    rax, rax
0x180004c2f  jnz     short loc_180004C0F
0x180004c31  mov     rax, [rdi]
0x180004c34  lea     rdx, [rsp+0AD0h+var_AA0]
0x180004c39  mov     rcx, rdi
0x180004c3c  mov     rax, [rax+28h]
0x180004c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c45  mov     ebx, eax
0x180004c47  test    eax, eax
0x180004c49  js      loc_180004DC6
0x180004c4f  mov     rbx, cs:hInstance
0x180004c56  lea     rdx, [rbp+9D0h+Filename]; lpFilename
0x180004c5d  mov     edi, 104h
0x180004c62  mov     rcx, rbx; hModule
0x180004c65  mov     r8d, edi; nSize
0x180004c68  call    cs:__imp_GetModuleFileNameW
0x180004c6e  test    eax, eax
0x180004c70  jnz     short loc_180004C7E
0x180004c72  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004c77  mov     ebx, eax
0x180004c79  jmp     loc_180004DC6
0x180004c7e  cmp     eax, edi
0x180004c80  jnz     short loc_180004C8C
0x180004c82  mov     ebx, 8007007Ah
0x180004c87  jmp     loc_180004DC6
0x180004c8c  lea     rdx, [rbp+9D0h+Filename]
0x180004c93  mov     ecx, r15d
0x180004c96  mov     r9d, 27h ; '''
0x180004c9c  movzx   r8d, word ptr [rdx]
0x180004ca0  test    r8w, r8w
0x180004ca4  jz      short loc_180004CD0
0x180004ca6  mov     [rsp+rcx*2+0AD0h+Source], r8w
0x180004cac  cmp     r8w, r9w
0x180004cb0  jnz     short loc_180004CC2
0x180004cb2  cmp     ecx, 206h
0x180004cb8  jnb     short loc_180004CC2
0x180004cba  inc     ecx
0x180004cbc  mov     [rsp+rcx*2+0AD0h+Source], r9w
0x180004cc2  add     rdx, 2
0x180004cc6  inc     ecx
0x180004cc8  cmp     ecx, 207h
0x180004cce  jb      short loc_180004C9C
0x180004cd0  mov     [rsp+rcx*2+0AD0h+Source], r15w
0x180004cd6  test    rbx, rbx
0x180004cd9  jz      short loc_180004CF2
0x180004cdb  xor     ecx, ecx; lpModuleName
0x180004cdd  call    cs:__imp_GetModuleHandleW
0x180004ce3  cmp     rbx, rax
0x180004ce6  jz      short loc_180004CF2
0x180004ce8  lea     r8, [rsp+0AD0h+Source]
0x180004ced  jmp     loc_180004D7C
0x180004cf2  mov     edi, 22h ; '"'
0x180004cf7  lea     rcx, [rsp+0AD0h+Source]
0x180004cfc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004d00  mov     [rbp+9D0h+var_450], di
0x180004d07  mov     rax, rbx
0x180004d0a  inc     rax
0x180004d0d  cmp     [rcx+rax*2], r15w
0x180004d12  jnz     short loc_180004D0A
0x180004d14  inc     eax
0x180004d16  lea     r8, [rsp+0AD0h+Source]; Source
0x180004d1b  movsxd  r9, eax
0x180004d1e  lea     rcx, [rbp+9D0h+Destination]; Destination
0x180004d25  add     r9, r9; SourceSize
0x180004d28  mov     edx, 414h; DestinationSize
0x180004d2d  call    cs:__imp_memcpy_s
0x180004d33  test    eax, eax
0x180004d35  jnz     loc_180004E01
0x180004d3b  lea     rax, [rbp+9D0h+var_450]
0x180004d42  inc     rbx
0x180004d45  cmp     [rax+rbx*2], r15w
0x180004d4a  jnz     short loc_180004D42
0x180004d4c  movsxd  rax, ebx
0x180004d4f  lea     rcx, ds:2[rax*2]
0x180004d57  mov     [rbp+rax*2+9D0h+var_450], di
0x180004d5f  cmp     rcx, 418h
0x180004d66  jnb     loc_180004E36
0x180004d6c  mov     [rbp+rcx+9D0h+var_450], r15w
0x180004d75  lea     r8, [rbp+9D0h+var_450]; unsigned __int16 *
0x180004d7c  lea     rdx, aModule; "Module"
0x180004d83  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180004d88  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004d8d  neg     eax
0x180004d8f  mov     edi, 8007000Eh
0x180004d94  sbb     ecx, ecx
0x180004d96  not     ecx
0x180004d98  and     ecx, edi
0x180004d9a  test    ecx, ecx
0x180004d9c  jns     short loc_180004DA2
0x180004d9e  mov     ebx, ecx
0x180004da0  jmp     short loc_180004DC6
0x180004da2  lea     r8, [rsp+0AD0h+Source]; unsigned __int16 *
0x180004da7  lea     rdx, aModuleRaw; "Module_Raw"
0x180004dae  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180004db3  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004db8  mov     ecx, eax
0x180004dba  neg     ecx
0x180004dbc  sbb     ebx, ebx
0x180004dbe  not     ebx
0x180004dc0  and     ebx, edi
0x180004dc2  test    eax, eax
0x180004dc4  jnz     short loc_180004DD4
0x180004dc6  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180004dcb  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180004dd0  mov     eax, ebx
0x180004dd2  jmp     short loc_180004E10
0x180004dd4  mov     eax, r15d
0x180004dd7  movzx   r8d, r14w; unsigned __int16 *
0x180004ddb  test    esi, esi
0x180004ddd  lea     r9, aRegistry; "REGISTRY"
0x180004de4  lea     rdx, [rbp+9D0h+Filename]; unsigned __int16 *
0x180004deb  setnz   al
0x180004dee  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180004df3  mov     [rsp+0AD0h+var_AB0], eax; int
0x180004df7  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180004dfc  jmp     loc_180004C77
0x180004e01  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180004e06  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180004e0b  mov     eax, 80004005h
0x180004e10  mov     rcx, [rbp+9D0h+var_30]
0x180004e17  xor     rcx, rsp; StackCookie
0x180004e1a  call    __security_check_cookie
0x180004e1f  mov     rbx, [rsp+0AD0h+arg_0]
0x180004e27  add     rsp, 0AB0h
0x180004e2e  pop     r15
0x180004e30  pop     r14
0x180004e32  pop     rdi
0x180004e33  pop     rsi
0x180004e34  pop     rbp
0x180004e35  retn
0x180004e36  call    __report_rangecheckfailure
```
