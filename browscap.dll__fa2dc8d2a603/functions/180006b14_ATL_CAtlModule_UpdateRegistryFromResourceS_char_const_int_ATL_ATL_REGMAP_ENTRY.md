# ATL::CAtlModule::UpdateRegistryFromResourceS(char const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006b14`
- end: `0x180006fec`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBDHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `1240`
- prototype: `int(ATL::CAtlModule *__hidden this, const char *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007010`

## callees

- `0x180001a68`
- `0x180002530`
- `0x180002b10`
- `0x180003714`
- `0x1800037f4`
- `0x180004480`
- `0x180005eb0`
- `0x1800061ec`
- `0x180006b14`
- `0x180007034`
- `0x18000b640`
- `0x18000b700`
- `0x18000d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006da5`
- `msvcrt!memcpy_s` at `0x180006da5`
- `msvcrt!free` at `0x180006ea7`
- `msvcrt!free` at `0x180006ebf`
- `msvcrt!free` at `0x180006f4e`
- `msvcrt!free` at `0x180006f93`
- `msvcrt!free` at `0x180006fb6`
- `msvcrt!free` at `0x180006fce`
- `msvcrt!free` at `0x180006ea7`
- `msvcrt!free` at `0x180006ebf`
- `msvcrt!free` at `0x180006f4e`
- `msvcrt!free` at `0x180006f93`
- `msvcrt!free` at `0x180006fb6`
- `msvcrt!free` at `0x180006fce`
- `msvcrt!malloc` at `0x180006c98`
- `msvcrt!malloc` at `0x180006ee0`
- `msvcrt!malloc` at `0x180006c98`
- `msvcrt!malloc` at `0x180006ee0`
- `KERNEL32!GetModuleHandleA` at `0x180006d3d`
- `KERNEL32!GetModuleHandleA` at `0x180006d3d`
- `KERNEL32!MultiByteToWideChar` at `0x180006cdb`
- `KERNEL32!MultiByteToWideChar` at `0x180006f1f`
- `KERNEL32!MultiByteToWideChar` at `0x180006cdb`
- `KERNEL32!MultiByteToWideChar` at `0x180006f1f`
- `KERNEL32!GetModuleFileNameA` at `0x180006bec`
- `KERNEL32!GetModuleFileNameA` at `0x180006bec`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const char *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  int Error; // ebx
  HMODULE v10; // r14
  DWORD ModuleFileNameA; // eax
  __int64 v12; // rax
  int v13; // ecx
  _QWORD *v14; // rbx
  unsigned __int64 v15; // rsi
  __int64 v16; // rax
  void *v17; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v19; // rax
  __int64 v20; // rcx
  const unsigned __int16 *v21; // r15
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  int v26; // edi
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rsi
  __int64 v30; // rax
  void *v31; // rsp
  WCHAR *v32; // rdi
  void *v33; // rcx
  void *v34; // rcx
  _QWORD *v35; // rax
  const unsigned __int16 *v36; // r9
  int v37; // eax
  void *v38; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  __int64 v44; // [rsp+38h] [rbp+8h]
  __int64 v45; // [rsp+40h] [rbp+10h]
  int v46; // [rsp+48h] [rbp+18h]
  _OWORD v47[2]; // [rsp+50h] [rbp+20h] BYREF
  __int64 v48; // [rsp+70h] [rbp+40h]
  char v49; // [rsp+78h] [rbp+48h]
  CHAR Filename[272]; // [rsp+80h] [rbp+50h] BYREF
  unsigned __int16 Source[520]; // [rsp+190h] [rbp+160h] BYREF
  unsigned __int16 v52; // [rsp+5A0h] [rbp+570h] BYREF
  _BYTE Destination[1054]; // [rsp+5A2h] [rbp+572h] BYREF

  *(_QWORD *)WideCharStr = &ATL::CRegObject::`vftable';
  v44 = 0;
  v45 = 0;
  v46 = 0;
  memset(v47, 0, sizeof(v47));
  v48 = 0;
  v49 = 0;
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v47);
  if ( v8 < 0 )
  {
LABEL_70:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
    return (unsigned int)v8;
  }
  v49 = 1;
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)WideCharStr,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, WCHAR *))(*(_QWORD *)this + 40LL))(this, WideCharStr);
  if ( Error < 0 )
    goto LABEL_74;
  v10 = hModule;
  ModuleFileNameA = GetModuleFileNameA(hModule, Filename, 0x104u);
  if ( ModuleFileNameA )
  {
    if ( ModuleFileNameA == 260 )
    {
      Error = -2147024774;
      goto LABEL_74;
    }
    v12 = -1;
    do
      ++v12;
    while ( Filename[v12] );
    v13 = 2 * v12 + 2;
    if ( (unsigned __int64)(2LL * (int)v12 + 2147483650LL) > 0xFFFFFFFF )
    {
LABEL_73:
      Error = -2147024882;
      goto LABEL_74;
    }
    v14 = 0;
    v15 = v13;
    if ( v13 <= 1024
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v13, 0xFFFFFFFF) )
    {
      v16 = v15 + 15;
      if ( v15 + 15 < v15 )
        v16 = 0xFFFFFFFFFFFFFF0LL;
      v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
      lpWideCharStr = WideCharStr;
    }
    else
    {
      if ( ~v15 < 0x10 )
        goto LABEL_82;
      v19 = malloc(v15 + 16);
      if ( v19 )
      {
        *v19 = 0;
        v14 = v19;
        lpWideCharStr = (WCHAR *)(v19 + 2);
      }
      else
      {
        lpWideCharStr = 0;
      }
    }
    if ( !lpWideCharStr || (*lpWideCharStr = 0, !MultiByteToWideChar(3u, 0, Filename, -1, lpWideCharStr, v15 >> 1)) )
    {
      while ( v14 )
      {
        v42 = v14;
        v14 = (_QWORD *)*v14;
        free(v42);
      }
      goto LABEL_73;
    }
    v20 = 0;
    v21 = lpWideCharStr;
    do
    {
      if ( !*lpWideCharStr )
        break;
      Source[v20] = *lpWideCharStr;
      if ( *lpWideCharStr == 39 && (unsigned int)v20 < 0x206 )
      {
        LODWORD(v20) = v20 + 1;
        Source[(unsigned int)v20] = 39;
      }
      ++lpWideCharStr;
      v20 = (unsigned int)(v20 + 1);
    }
    while ( (unsigned int)v20 < 0x207 );
    Source[v20] = 0;
    if ( !v10 || v10 == GetModuleHandleA(0) )
    {
      v52 = 34;
      v23 = -1;
      do
        ++v23;
      while ( Source[v23] );
      if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v23 + 1)) )
      {
        while ( v14 )
        {
          v41 = v14;
          v14 = (_QWORD *)*v14;
          free(v41);
        }
        Error = -2147467259;
        goto LABEL_74;
      }
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)&Destination[2 * v24 - 2] );
      *(_WORD *)&Destination[2 * (int)v24 - 2] = 34;
      v25 = 2LL * (int)v24 + 2;
      if ( v25 >= 0x418 )
        _report_rangecheckfailure();
      *(_WORD *)&Destination[v25 - 2] = 0;
      v22 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module", &v52);
    }
    else
    {
      v22 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module", Source);
    }
    v26 = v22;
    if ( v22 < 0 )
    {
      while ( v14 )
      {
        v33 = v14;
        v14 = (_QWORD *)*v14;
        free(v33);
      }
    }
    else
    {
      v26 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module_Raw", Source);
      if ( v26 >= 0 )
      {
        if ( !a2 )
          goto LABEL_72;
        v27 = -1;
        do
          ++v27;
        while ( a2[v27] );
        v28 = 2LL * ((int)v27 + 1);
        if ( (unsigned __int64)(v28 + 0x80000000LL) > 0xFFFFFFFF )
        {
LABEL_72:
          while ( v14 )
          {
            v40 = v14;
            v14 = (_QWORD *)*v14;
            free(v40);
          }
          goto LABEL_73;
        }
        v29 = (int)v28;
        if ( (int)v28 <= 1024
          && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)v28, 0xFFFFFFFF) )
        {
          v30 = v29 + 15;
          if ( v29 + 15 < v29 )
            v30 = 0xFFFFFFFFFFFFFF0LL;
          v31 = alloca(v30 & 0xFFFFFFFFFFFFFFF0uLL);
          v32 = WideCharStr;
LABEL_62:
          if ( v32 )
          {
            *v32 = 0;
            if ( MultiByteToWideChar(3u, 0, a2, -1, v32, v29 >> 1) )
            {
              if ( a3 )
                v37 = ATL::CRegObject::ResourceRegisterSz((ATL::CRegObject *)WideCharStr, v21, v32, v36);
              else
                v37 = ATL::CRegObject::ResourceUnregisterSz((ATL::CRegObject *)WideCharStr, v21, v32, v36);
              v8 = v37;
              while ( v14 )
              {
                v38 = v14;
                v14 = (_QWORD *)*v14;
                free(v38);
              }
              goto LABEL_70;
            }
          }
          goto LABEL_72;
        }
        if ( ~v29 >= 0x10 )
        {
          v35 = malloc(v29 + 16);
          if ( v35 )
          {
            *v35 = v14;
            v14 = v35;
            v32 = (WCHAR *)(v35 + 2);
          }
          else
          {
            v32 = 0;
          }
          goto LABEL_62;
        }
LABEL_82:
        ATL::AtlThrowImpl(-2147024809);
      }
      while ( v14 )
      {
        v34 = v14;
        v14 = (_QWORD *)*v14;
        free(v34);
      }
    }
    Error = v26;
    goto LABEL_74;
  }
  Error = ATL::AtlHresultFromLastError();
LABEL_74:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180006b14  push    rbp
0x180006b16  push    rsi
0x180006b17  push    rdi
0x180006b18  push    r12
0x180006b1a  push    r13
0x180006b1c  push    r14
0x180006b1e  push    r15
0x180006b20  sub     rsp, 9D0h
0x180006b27  lea     rbp, [rsp+30h]
0x180006b2c  mov     [rbp+9D0h+arg_10], rbx
0x180006b33  mov     rax, cs:__security_cookie
0x180006b3a  xor     rax, rbp
0x180006b3d  mov     [rbp+9D0h+var_40], rax
0x180006b44  mov     rbx, r9
0x180006b47  mov     r13d, r8d
0x180006b4a  mov     r12, rdx
0x180006b4d  mov     rsi, rcx
0x180006b50  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180006b57  mov     qword ptr [rbp+9D0h+WideCharStr], rax
0x180006b5b  xor     r15d, r15d
0x180006b5e  mov     [rbp+9D0h+var_9C8], r15
0x180006b62  mov     [rbp+9D0h+var_9C0], r15
0x180006b66  mov     [rbp+9D0h+var_9B8], r15d
0x180006b6a  xorps   xmm0, xmm0
0x180006b6d  xor     eax, eax
0x180006b6f  movups  [rbp+9D0h+var_9B0], xmm0
0x180006b73  movups  [rbp+9D0h+var_9A0], xmm0
0x180006b77  mov     [rbp+9D0h+var_990], rax
0x180006b7b  mov     [rbp+9D0h+var_988], r15b
0x180006b7f  lea     rcx, [rbp+9D0h+var_9B0]; this
0x180006b83  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006b88  mov     edi, eax
0x180006b8a  test    eax, eax
0x180006b8c  js      loc_180006F59
0x180006b92  mov     [rbp+9D0h+var_988], 1
0x180006b96  test    rbx, rbx
0x180006b99  jz      short loc_180006BB9
0x180006b9b  jmp     short loc_180006BB1
0x180006b9d  mov     r8, [rbx+8]; unsigned __int16 *
0x180006ba1  mov     rdx, rax; unsigned __int16 *
0x180006ba4  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006ba8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006bad  lea     rbx, [rbx+10h]
0x180006bb1  mov     rax, [rbx]
0x180006bb4  test    rax, rax
0x180006bb7  jnz     short loc_180006B9D
0x180006bb9  mov     rax, [rsi]
0x180006bbc  lea     rdx, [rbp+9D0h+WideCharStr]
0x180006bc0  mov     rcx, rsi
0x180006bc3  mov     rax, [rax+28h]
0x180006bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bcc  mov     ebx, eax
0x180006bce  test    eax, eax
0x180006bd0  js      loc_180006FA3
0x180006bd6  mov     r14, cs:hModule
0x180006bdd  mov     ebx, 104h
0x180006be2  mov     r8d, ebx; nSize
0x180006be5  lea     rdx, [rbp+9D0h+Filename]; lpFilename
0x180006be9  mov     rcx, r14; hModule
0x180006bec  call    cs:__imp_GetModuleFileNameA
0x180006bf2  test    eax, eax
0x180006bf4  jnz     short loc_180006C02
0x180006bf6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006bfb  mov     ebx, eax
0x180006bfd  jmp     loc_180006FA3
0x180006c02  cmp     eax, ebx
0x180006c04  jnz     short loc_180006C10
0x180006c06  mov     ebx, 8007007Ah
0x180006c0b  jmp     loc_180006FA3
0x180006c10  lea     rcx, [rbp+9D0h+Filename]
0x180006c14  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006c18  inc     rax
0x180006c1b  cmp     [rcx+rax], r15b
0x180006c1f  jnz     short loc_180006C18
0x180006c21  cdqe
0x180006c23  lea     rcx, ds:2[rax*2]
0x180006c2b  mov     eax, 80000000h
0x180006c30  add     rax, rcx
0x180006c33  mov     edx, 0FFFFFFFFh; unsigned __int64
0x180006c38  cmp     rax, rdx
0x180006c3b  ja      loc_180006F9E
0x180006c41  mov     rbx, r15
0x180006c44  movsxd  rsi, ecx
0x180006c47  mov     rdi, 0FFFFFFFFFFFFFF0h
0x180006c51  cmp     ecx, 400h
0x180006c57  jg      short loc_180006C84
0x180006c59  mov     rcx, rsi; this
0x180006c5c  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180006c61  test    al, al
0x180006c63  jz      short loc_180006C84
0x180006c65  lea     rax, [rsi+0Fh]
0x180006c69  cmp     rax, rsi
0x180006c6c  ja      short loc_180006C71
0x180006c6e  mov     rax, rdi
0x180006c71  and     rax, 0FFFFFFFFFFFFFFF0h
0x180006c75  call    _alloca_probe
0x180006c7a  sub     rsp, rax
0x180006c7d  lea     rdi, [rsp+0A00h+WideCharStr]
0x180006c82  jmp     short loc_180006CB2
0x180006c84  mov     rax, rsi
0x180006c87  not     rax
0x180006c8a  cmp     rax, 10h
0x180006c8e  jb      loc_180006FE1
0x180006c94  lea     rcx, [rsi+10h]; Size
0x180006c98  call    cs:__imp_malloc
0x180006c9e  test    rax, rax
0x180006ca1  jnz     short loc_180006CA8
0x180006ca3  mov     rdi, r15
0x180006ca6  jmp     short loc_180006CB2
0x180006ca8  mov     [rax], r15
0x180006cab  mov     rbx, rax
0x180006cae  lea     rdi, [rax+10h]
0x180006cb2  test    rdi, rdi
0x180006cb5  jz      loc_180006FD4
0x180006cbb  mov     [rdi], r15w
0x180006cbf  shr     rsi, 1
0x180006cc2  mov     [rsp+0A00h+cchWideChar], esi; cchWideChar
0x180006cc6  mov     [rsp+0A00h+lpWideCharStr], rdi; lpWideCharStr
0x180006ccb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006ccf  mov     r9d, esi; cbMultiByte
0x180006cd2  lea     r8, [rbp+9D0h+Filename]; lpMultiByteStr
0x180006cd6  xor     edx, edx; dwFlags
0x180006cd8  lea     ecx, [rsi+4]; CodePage
0x180006cdb  call    cs:__imp_MultiByteToWideChar
0x180006ce1  test    eax, eax
0x180006ce3  jz      loc_180006FD4
0x180006ce9  mov     ecx, r15d
0x180006cec  mov     r15, rdi
0x180006cef  lea     r9d, [rsi+28h]
0x180006cf3  xor     r8d, r8d
0x180006cf6  movzx   edx, word ptr [rdi]
0x180006cf9  test    dx, dx
0x180006cfc  jz      short loc_180006D2D
0x180006cfe  mov     [rbp+rcx*2+9D0h+Source], dx
0x180006d06  cmp     [rdi], r9w
0x180006d0a  jnz     short loc_180006D1F
0x180006d0c  cmp     ecx, 206h
0x180006d12  jnb     short loc_180006D1F
0x180006d14  inc     ecx
0x180006d16  mov     [rbp+rcx*2+9D0h+Source], r9w
0x180006d1f  add     rdi, 2
0x180006d23  inc     ecx
0x180006d25  cmp     ecx, 207h
0x180006d2b  jb      short loc_180006CF6
0x180006d2d  mov     [rbp+rcx*2+9D0h+Source], r8w
0x180006d36  test    r14, r14
0x180006d39  jz      short loc_180006D67
0x180006d3b  xor     ecx, ecx; lpModuleName
0x180006d3d  call    cs:__imp_GetModuleHandleA
0x180006d43  cmp     r14, rax
0x180006d46  jz      short loc_180006D67
0x180006d48  lea     r8, [rbp+9D0h+Source]; unsigned __int16 *
0x180006d4f  lea     rdx, aModule; "Module"
0x180006d56  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006d5a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006d5f  xor     r14d, r14d
0x180006d62  jmp     loc_180006E06
0x180006d67  mov     edi, 22h ; '"'
0x180006d6c  mov     [rbp+9D0h+var_460], di
0x180006d73  lea     rcx, [rbp+9D0h+Source]
0x180006d7a  mov     rax, rsi
0x180006d7d  xor     r14d, r14d
0x180006d80  inc     rax
0x180006d83  cmp     [rcx+rax*2], r14w
0x180006d88  jnz     short loc_180006D80
0x180006d8a  inc     eax
0x180006d8c  movsxd  r9, eax
0x180006d8f  add     r9, r9; SourceSize
0x180006d92  lea     r8, [rbp+9D0h+Source]; Source
0x180006d99  mov     edx, 414h; DestinationSize
0x180006d9e  lea     rcx, [rbp+9D0h+Destination]; Destination
0x180006da5  call    cs:__imp_memcpy_s
0x180006dab  test    eax, eax
0x180006dad  jnz     loc_180006FBC
0x180006db3  lea     rcx, [rbp+9D0h+var_460]
0x180006dba  mov     rax, rsi
0x180006dbd  inc     rax
0x180006dc0  cmp     [rcx+rax*2], r14w
0x180006dc5  jnz     short loc_180006DBD
0x180006dc7  cdqe
0x180006dc9  mov     [rbp+rax*2+9D0h+var_460], di
0x180006dd1  lea     rcx, ds:2[rax*2]
0x180006dd9  cmp     rcx, 418h
0x180006de0  jnb     loc_180006FDB
0x180006de6  mov     [rbp+rcx+9D0h+var_460], r14w
0x180006def  lea     r8, [rbp+9D0h+var_460]; unsigned __int16 *
0x180006df6  lea     rdx, aModule; "Module"
0x180006dfd  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006e01  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006e06  mov     edi, eax
0x180006e08  test    eax, eax
0x180006e0a  js      loc_180006EAD
0x180006e10  lea     r8, [rbp+9D0h+Source]; unsigned __int16 *
0x180006e17  lea     rdx, aModuleRaw; "Module_Raw"
0x180006e1e  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006e22  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006e27  mov     edi, eax
0x180006e29  test    eax, eax
0x180006e2b  js      loc_180006EC5
0x180006e31  test    r12, r12
0x180006e34  jz      loc_180006F99
0x180006e3a  mov     rax, rsi
0x180006e3d  inc     rax
0x180006e40  cmp     [r12+rax], r14b
0x180006e44  jnz     short loc_180006E3D
0x180006e46  inc     eax
0x180006e48  movsxd  rcx, eax
0x180006e4b  add     rcx, rcx
0x180006e4e  mov     eax, 80000000h
0x180006e53  add     rax, rcx
0x180006e56  mov     edx, 0FFFFFFFFh; unsigned __int64
0x180006e5b  cmp     rax, rdx
0x180006e5e  ja      loc_180006F99
0x180006e64  movsxd  rsi, ecx
0x180006e67  cmp     ecx, 400h
0x180006e6d  jg      short loc_180006ECC
0x180006e6f  mov     rcx, rsi; this
0x180006e72  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180006e77  test    al, al
0x180006e79  jz      short loc_180006ECC
0x180006e7b  lea     rax, [rsi+0Fh]
0x180006e7f  cmp     rax, rsi
0x180006e82  ja      short loc_180006E8E
0x180006e84  mov     rax, 0FFFFFFFFFFFFFF0h
0x180006e8e  and     rax, 0FFFFFFFFFFFFFFF0h
0x180006e92  call    _alloca_probe
0x180006e97  sub     rsp, rax
0x180006e9a  lea     rdi, [rsp+0A00h+WideCharStr]
0x180006e9f  jmp     short loc_180006EFA
0x180006ea1  mov     rcx, rbx; Block
0x180006ea4  mov     rbx, [rbx]
0x180006ea7  call    cs:__imp_free
0x180006ead  test    rbx, rbx
0x180006eb0  jnz     short loc_180006EA1
0x180006eb2  mov     ebx, edi
0x180006eb4  jmp     loc_180006FA3
0x180006eb9  mov     rcx, rbx; Block
0x180006ebc  mov     rbx, [rbx]
0x180006ebf  call    cs:__imp_free
0x180006ec5  test    rbx, rbx
0x180006ec8  jnz     short loc_180006EB9
0x180006eca  jmp     short loc_180006EB2
0x180006ecc  mov     rax, rsi
0x180006ecf  not     rax
0x180006ed2  cmp     rax, 10h
0x180006ed6  jb      loc_180006FE1
0x180006edc  lea     rcx, [rsi+10h]; Size
0x180006ee0  call    cs:__imp_malloc
0x180006ee6  test    rax, rax
0x180006ee9  jnz     short loc_180006EF0
0x180006eeb  mov     rdi, r14
0x180006eee  jmp     short loc_180006EFA
0x180006ef0  mov     [rax], rbx
0x180006ef3  mov     rbx, rax
0x180006ef6  lea     rdi, [rax+10h]
0x180006efa  test    rdi, rdi
0x180006efd  jz      loc_180006F99
0x180006f03  mov     [rdi], r14w
0x180006f07  shr     rsi, 1
0x180006f0a  mov     [rsp+0A00h+cchWideChar], esi; cchWideChar
0x180006f0e  mov     [rsp+0A00h+lpWideCharStr], rdi; lpWideCharStr
0x180006f13  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180006f17  mov     r8, r12; lpMultiByteStr
0x180006f1a  xor     edx, edx; dwFlags
0x180006f1c  lea     ecx, [rdx+3]; CodePage
0x180006f1f  call    cs:__imp_MultiByteToWideChar
0x180006f25  test    eax, eax
0x180006f27  jz      short loc_180006F99
0x180006f29  mov     r8, rdi; lpWideCharStr
0x180006f2c  mov     rdx, r15; unsigned __int16 *
0x180006f2f  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006f33  test    r13d, r13d
0x180006f36  jz      short loc_180006F3F
0x180006f38  call    ?ResourceRegisterSz@CRegObject@ATL@@QEAAJPEBG00@Z; ATL::CRegObject::ResourceRegisterSz(ushort const *,ushort const *,ushort const *)
0x180006f3d  jmp     short loc_180006F44
0x180006f3f  call    ?ResourceUnregisterSz@CRegObject@ATL@@QEAAJPEBG00@Z; ATL::CRegObject::ResourceUnregisterSz(ushort const *,ushort const *,ushort const *)
0x180006f44  mov     edi, eax
0x180006f46  jmp     short loc_180006F54
0x180006f48  mov     rcx, rbx; Block
0x180006f4b  mov     rbx, [rbx]
0x180006f4e  call    cs:__imp_free
0x180006f54  test    rbx, rbx
0x180006f57  jnz     short loc_180006F48
0x180006f59  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006f5d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006f62  mov     eax, edi
0x180006f64  mov     rcx, [rbp+9D0h+var_40]
0x180006f6b  xor     rcx, rbp; StackCookie
0x180006f6e  call    __security_check_cookie
0x180006f73  mov     rbx, [rbp+9D0h+arg_10]
0x180006f7a  lea     rsp, [rbp+9A0h]
0x180006f81  pop     r15
0x180006f83  pop     r14
0x180006f85  pop     r13
0x180006f87  pop     r12
0x180006f89  pop     rdi
0x180006f8a  pop     rsi
0x180006f8b  pop     rbp
0x180006f8c  retn
0x180006f8d  mov     rcx, rbx; Block
  ... truncated ...
```
