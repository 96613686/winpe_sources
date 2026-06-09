# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000672c`
- end: `0x180006b0c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `992`
- prototype: `int(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006700`
- `0x180007000`

## callees

- `0x180001a68`
- `0x180002530`
- `0x180002b10`
- `0x180003714`
- `0x1800037f4`
- `0x180004480`
- `0x180005d94`
- `0x1800060d0`
- `0x18000672c`
- `0x180007034`
- `0x18000b640`
- `0x18000b700`
- `0x18000d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800069af`
- `msvcrt!memcpy_s` at `0x1800069af`
- `msvcrt!free` at `0x180006a4d`
- `msvcrt!free` at `0x180006a65`
- `msvcrt!free` at `0x180006a81`
- `msvcrt!free` at `0x180006ac6`
- `msvcrt!free` at `0x180006ade`
- `msvcrt!free` at `0x180006a4d`
- `msvcrt!free` at `0x180006a65`
- `msvcrt!free` at `0x180006a81`
- `msvcrt!free` at `0x180006ac6`
- `msvcrt!free` at `0x180006ade`
- `msvcrt!malloc` at `0x1800068b6`
- `msvcrt!malloc` at `0x1800068b6`
- `KERNEL32!GetModuleHandleA` at `0x18000695a`
- `KERNEL32!GetModuleHandleA` at `0x18000695a`
- `KERNEL32!MultiByteToWideChar` at `0x1800068f8`
- `KERNEL32!MultiByteToWideChar` at `0x1800068f8`
- `KERNEL32!GetModuleFileNameA` at `0x180006804`
- `KERNEL32!GetModuleFileNameA` at `0x180006804`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  int Error; // ebx
  HMODULE v10; // r15
  DWORD ModuleFileNameA; // eax
  __int64 v12; // r14
  __int64 v13; // rax
  int v14; // ecx
  _QWORD *v15; // rbx
  unsigned __int64 v16; // rsi
  __int64 v17; // rax
  void *v18; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v20; // rax
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rsi
  unsigned __int16 *v23; // r8
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  int v26; // edi
  const unsigned __int16 *v27; // r9
  int v28; // eax
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v33; // rcx
  void *v34; // rcx
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  __int64 v36; // [rsp+38h] [rbp+8h]
  __int64 v37; // [rsp+40h] [rbp+10h]
  int v38; // [rsp+48h] [rbp+18h]
  _OWORD v39[2]; // [rsp+50h] [rbp+20h] BYREF
  __int64 v40; // [rsp+70h] [rbp+40h]
  char v41; // [rsp+78h] [rbp+48h]
  CHAR Filename[272]; // [rsp+80h] [rbp+50h] BYREF
  unsigned __int16 Source[520]; // [rsp+190h] [rbp+160h] BYREF
  unsigned __int16 v44; // [rsp+5A0h] [rbp+570h] BYREF
  _BYTE Destination[1054]; // [rsp+5A2h] [rbp+572h] BYREF

  *(_QWORD *)WideCharStr = &ATL::CRegObject::`vftable';
  v36 = 0;
  v37 = 0;
  v38 = 0;
  memset(v39, 0, sizeof(v39));
  v40 = 0;
  v41 = 0;
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v39);
  if ( v8 < 0 )
  {
LABEL_54:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
    return (unsigned int)v8;
  }
  v41 = 1;
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
    goto LABEL_61;
  v10 = hModule;
  ModuleFileNameA = GetModuleFileNameA(hModule, Filename, 0x104u);
  if ( ModuleFileNameA )
  {
    if ( ModuleFileNameA == 260 )
    {
      Error = -2147024774;
      goto LABEL_61;
    }
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( Filename[v13] );
    v14 = 2 * v13 + 2;
    if ( (unsigned __int64)(2LL * (int)v13 + 2147483650LL) <= 0xFFFFFFFF )
    {
      v15 = 0;
      v16 = v14;
      if ( v14 <= 1024
        && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v14, 0xFFFFFFFF) )
      {
        v17 = v16 + 15;
        if ( v16 + 15 < v16 )
          v17 = 0xFFFFFFFFFFFFFF0LL;
        v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
        lpWideCharStr = WideCharStr;
      }
      else
      {
        if ( ~v16 < 0x10 )
          ATL::AtlThrowImpl(-2147024809);
        v20 = malloc(v16 + 16);
        if ( v20 )
        {
          *v20 = 0;
          v15 = v20;
          lpWideCharStr = (WCHAR *)(v20 + 2);
        }
        else
        {
          lpWideCharStr = 0;
        }
      }
      if ( lpWideCharStr )
      {
        *lpWideCharStr = 0;
        if ( MultiByteToWideChar(3u, 0, Filename, -1, lpWideCharStr, v16 >> 1) )
        {
          v21 = 0;
          v22 = lpWideCharStr;
          do
          {
            if ( !*lpWideCharStr )
              break;
            Source[v21] = *lpWideCharStr;
            if ( *lpWideCharStr == 39 && (unsigned int)v21 < 0x206 )
            {
              LODWORD(v21) = v21 + 1;
              Source[(unsigned int)v21] = 39;
            }
            ++lpWideCharStr;
            v21 = (unsigned int)(v21 + 1);
          }
          while ( (unsigned int)v21 < 0x207 );
          Source[v21] = 0;
          if ( !v10 || v10 == GetModuleHandleA(0) )
          {
            v44 = 34;
            v24 = -1;
            do
              ++v24;
            while ( Source[v24] );
            if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v24 + 1)) )
            {
              while ( v15 )
              {
                v33 = v15;
                v15 = (_QWORD *)*v15;
                free(v33);
              }
              Error = -2147467259;
              goto LABEL_61;
            }
            do
              ++v12;
            while ( *(_WORD *)&Destination[2 * v12 - 2] );
            *(_WORD *)&Destination[2 * (int)v12 - 2] = 34;
            v25 = 2LL * (int)v12 + 2;
            if ( v25 >= 0x418 )
              _report_rangecheckfailure();
            *(_WORD *)&Destination[v25 - 2] = 0;
            v23 = &v44;
          }
          else
          {
            v23 = Source;
          }
          v26 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module", v23);
          if ( v26 < 0 )
          {
            while ( v15 )
            {
              v29 = v15;
              v15 = (_QWORD *)*v15;
              free(v29);
            }
          }
          else
          {
            v26 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module_Raw", Source);
            if ( v26 >= 0 )
            {
              if ( a3 )
                v28 = ATL::CRegObject::ResourceRegister((ATL::CRegObject *)WideCharStr, v22, a2, v27);
              else
                v28 = ATL::CRegObject::ResourceUnregister((ATL::CRegObject *)WideCharStr, v22, a2, v27);
              v8 = v28;
              while ( v15 )
              {
                v31 = v15;
                v15 = (_QWORD *)*v15;
                free(v31);
              }
              goto LABEL_54;
            }
            while ( v15 )
            {
              v30 = v15;
              v15 = (_QWORD *)*v15;
              free(v30);
            }
          }
          Error = v26;
          goto LABEL_61;
        }
      }
      while ( v15 )
      {
        v34 = v15;
        v15 = (_QWORD *)*v15;
        free(v34);
      }
    }
    Error = -2147024882;
    goto LABEL_61;
  }
  Error = ATL::AtlHresultFromLastError();
LABEL_61:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000672c  push    rbp
0x18000672e  push    rsi
0x18000672f  push    rdi
0x180006730  push    r12
0x180006732  push    r13
0x180006734  push    r14
0x180006736  push    r15
0x180006738  sub     rsp, 9D0h
0x18000673f  lea     rbp, [rsp+30h]
0x180006744  mov     [rbp+9D0h+arg_10], rbx
0x18000674b  mov     rax, cs:__security_cookie
0x180006752  xor     rax, rbp
0x180006755  mov     [rbp+9D0h+var_40], rax
0x18000675c  mov     rbx, r9
0x18000675f  mov     r13d, r8d
0x180006762  mov     r12d, edx
0x180006765  mov     rsi, rcx
0x180006768  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000676f  mov     qword ptr [rbp+9D0h+WideCharStr], rax
0x180006773  xor     r14d, r14d
0x180006776  mov     [rbp+9D0h+var_9C8], r14
0x18000677a  mov     [rbp+9D0h+var_9C0], r14
0x18000677e  mov     [rbp+9D0h+var_9B8], r14d
0x180006782  xorps   xmm0, xmm0
0x180006785  xor     eax, eax
0x180006787  movups  [rbp+9D0h+var_9B0], xmm0
0x18000678b  movups  [rbp+9D0h+var_9A0], xmm0
0x18000678f  mov     [rbp+9D0h+var_990], rax
0x180006793  mov     [rbp+9D0h+var_988], r14b
0x180006797  lea     rcx, [rbp+9D0h+var_9B0]; this
0x18000679b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800067a0  mov     edi, eax
0x1800067a2  test    eax, eax
0x1800067a4  js      loc_180006A8C
0x1800067aa  mov     [rbp+9D0h+var_988], 1
0x1800067ae  test    rbx, rbx
0x1800067b1  jz      short loc_1800067D1
0x1800067b3  jmp     short loc_1800067C9
0x1800067b5  mov     r8, [rbx+8]; unsigned __int16 *
0x1800067b9  mov     rdx, rax; unsigned __int16 *
0x1800067bc  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x1800067c0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800067c5  lea     rbx, [rbx+10h]
0x1800067c9  mov     rax, [rbx]
0x1800067cc  test    rax, rax
0x1800067cf  jnz     short loc_1800067B5
0x1800067d1  mov     rax, [rsi]
0x1800067d4  lea     rdx, [rbp+9D0h+WideCharStr]
0x1800067d8  mov     rcx, rsi
0x1800067db  mov     rax, [rax+28h]
0x1800067df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067e4  mov     ebx, eax
0x1800067e6  test    eax, eax
0x1800067e8  js      loc_180006AEE
0x1800067ee  mov     r15, cs:hModule
0x1800067f5  mov     ebx, 104h
0x1800067fa  mov     r8d, ebx; nSize
0x1800067fd  lea     rdx, [rbp+9D0h+Filename]; lpFilename
0x180006801  mov     rcx, r15; hModule
0x180006804  call    cs:__imp_GetModuleFileNameA
0x18000680a  test    eax, eax
0x18000680c  jnz     short loc_18000681A
0x18000680e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006813  mov     ebx, eax
0x180006815  jmp     loc_180006AEE
0x18000681a  cmp     eax, ebx
0x18000681c  jnz     short loc_180006828
0x18000681e  mov     ebx, 8007007Ah
0x180006823  jmp     loc_180006AEE
0x180006828  lea     rcx, [rbp+9D0h+Filename]
0x18000682c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006830  mov     rax, r14
0x180006833  xor     r8d, r8d
0x180006836  inc     rax
0x180006839  cmp     [rcx+rax], r8b
0x18000683d  jnz     short loc_180006836
0x18000683f  cdqe
0x180006841  lea     rcx, ds:2[rax*2]
0x180006849  mov     eax, 80000000h
0x18000684e  add     rax, rcx
0x180006851  mov     edx, 0FFFFFFFFh; unsigned __int64
0x180006856  cmp     rax, rdx
0x180006859  ja      loc_180006AE9
0x18000685f  mov     rbx, r8
0x180006862  movsxd  rsi, ecx
0x180006865  cmp     ecx, 400h
0x18000686b  jg      short loc_1800068A2
0x18000686d  mov     rcx, rsi; this
0x180006870  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180006875  xor     r8d, r8d
0x180006878  test    al, al
0x18000687a  jz      short loc_1800068A2
0x18000687c  lea     rax, [rsi+0Fh]
0x180006880  cmp     rax, rsi
0x180006883  ja      short loc_18000688F
0x180006885  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000688f  and     rax, 0FFFFFFFFFFFFFFF0h
0x180006893  call    _alloca_probe
0x180006898  sub     rsp, rax
0x18000689b  lea     rdi, [rsp+0A00h+WideCharStr]
0x1800068a0  jmp     short loc_1800068D3
0x1800068a2  mov     rax, rsi
0x1800068a5  not     rax
0x1800068a8  cmp     rax, 10h
0x1800068ac  jb      loc_180006B01
0x1800068b2  lea     rcx, [rsi+10h]; Size
0x1800068b6  call    cs:__imp_malloc
0x1800068bc  xor     r8d, r8d
0x1800068bf  test    rax, rax
0x1800068c2  jnz     short loc_1800068C9
0x1800068c4  mov     edi, r8d
0x1800068c7  jmp     short loc_1800068D3
0x1800068c9  mov     [rax], r8
0x1800068cc  mov     rbx, rax
0x1800068cf  lea     rdi, [rax+10h]
0x1800068d3  test    rdi, rdi
0x1800068d6  jz      loc_180006AE4
0x1800068dc  mov     [rdi], r8w
0x1800068e0  shr     rsi, 1
0x1800068e3  mov     [rsp+0A00h+cchWideChar], esi; cchWideChar
0x1800068e7  mov     [rsp+0A00h+lpWideCharStr], rdi; lpWideCharStr
0x1800068ec  mov     r9d, r14d; cbMultiByte
0x1800068ef  lea     r8, [rbp+9D0h+Filename]; lpMultiByteStr
0x1800068f3  xor     edx, edx; dwFlags
0x1800068f5  lea     ecx, [rdx+3]; CodePage
0x1800068f8  call    cs:__imp_MultiByteToWideChar
0x1800068fe  xor     r8d, r8d
0x180006901  test    eax, eax
0x180006903  jz      loc_180006AE4
0x180006909  mov     ecx, r8d
0x18000690c  mov     rsi, rdi
0x18000690f  lea     r9d, [r8+27h]
0x180006913  movzx   edx, word ptr [rdi]
0x180006916  test    dx, dx
0x180006919  jz      short loc_18000694A
0x18000691b  mov     [rbp+rcx*2+9D0h+Source], dx
0x180006923  cmp     [rdi], r9w
0x180006927  jnz     short loc_18000693C
0x180006929  cmp     ecx, 206h
0x18000692f  jnb     short loc_18000693C
0x180006931  inc     ecx
0x180006933  mov     [rbp+rcx*2+9D0h+Source], r9w
0x18000693c  add     rdi, 2
0x180006940  inc     ecx
0x180006942  cmp     ecx, 207h
0x180006948  jb      short loc_180006913
0x18000694a  mov     [rbp+rcx*2+9D0h+Source], r8w
0x180006953  test    r15, r15
0x180006956  jz      short loc_180006971
0x180006958  xor     ecx, ecx; lpModuleName
0x18000695a  call    cs:__imp_GetModuleHandleA
0x180006960  cmp     r15, rax
0x180006963  jz      short loc_180006971
0x180006965  lea     r8, [rbp+9D0h+Source]
0x18000696c  jmp     loc_1800069FE
0x180006971  mov     edi, 22h ; '"'
0x180006976  mov     [rbp+9D0h+var_460], di
0x18000697d  lea     rcx, [rbp+9D0h+Source]
0x180006984  mov     rax, r14
0x180006987  xor     r15d, r15d
0x18000698a  inc     rax
0x18000698d  cmp     [rcx+rax*2], r15w
0x180006992  jnz     short loc_18000698A
0x180006994  inc     eax
0x180006996  movsxd  r9, eax
0x180006999  add     r9, r9; SourceSize
0x18000699c  lea     r8, [rbp+9D0h+Source]; Source
0x1800069a3  mov     edx, 414h; DestinationSize
0x1800069a8  lea     rcx, [rbp+9D0h+Destination]; Destination
0x1800069af  call    cs:__imp_memcpy_s
0x1800069b5  test    eax, eax
0x1800069b7  jnz     loc_180006ACC
0x1800069bd  lea     rax, [rbp+9D0h+var_460]
0x1800069c4  inc     r14
0x1800069c7  cmp     [rax+r14*2], r15w
0x1800069cc  jnz     short loc_1800069C4
0x1800069ce  movsxd  rax, r14d
0x1800069d1  mov     [rbp+rax*2+9D0h+var_460], di
0x1800069d9  lea     rcx, ds:2[rax*2]
0x1800069e1  cmp     rcx, 418h
0x1800069e8  jnb     loc_180006AFB
0x1800069ee  mov     [rbp+rcx+9D0h+var_460], r15w
0x1800069f7  lea     r8, [rbp+9D0h+var_460]; unsigned __int16 *
0x1800069fe  lea     rdx, aModule; "Module"
0x180006a05  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006a09  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006a0e  mov     edi, eax
0x180006a10  test    eax, eax
0x180006a12  js      short loc_180006A53
0x180006a14  lea     r8, [rbp+9D0h+Source]; unsigned __int16 *
0x180006a1b  lea     rdx, aModuleRaw; "Module_Raw"
0x180006a22  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006a26  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006a2b  mov     edi, eax
0x180006a2d  test    eax, eax
0x180006a2f  js      short loc_180006A6B
0x180006a31  mov     r8d, r12d; unsigned int
0x180006a34  mov     rdx, rsi; unsigned __int16 *
0x180006a37  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006a3b  test    r13d, r13d
0x180006a3e  jz      short loc_180006A72
0x180006a40  call    ?ResourceRegister@CRegObject@ATL@@QEAAJPEBGI0@Z; ATL::CRegObject::ResourceRegister(ushort const *,uint,ushort const *)
0x180006a45  jmp     short loc_180006A77
0x180006a47  mov     rcx, rbx; Block
0x180006a4a  mov     rbx, [rbx]
0x180006a4d  call    cs:__imp_free
0x180006a53  test    rbx, rbx
0x180006a56  jnz     short loc_180006A47
0x180006a58  mov     ebx, edi
0x180006a5a  jmp     loc_180006AEE
0x180006a5f  mov     rcx, rbx; Block
0x180006a62  mov     rbx, [rbx]
0x180006a65  call    cs:__imp_free
0x180006a6b  test    rbx, rbx
0x180006a6e  jnz     short loc_180006A5F
0x180006a70  jmp     short loc_180006A58
0x180006a72  call    ?ResourceUnregister@CRegObject@ATL@@QEAAJPEBGI0@Z; ATL::CRegObject::ResourceUnregister(ushort const *,uint,ushort const *)
0x180006a77  mov     edi, eax
0x180006a79  jmp     short loc_180006A87
0x180006a7b  mov     rcx, rbx; Block
0x180006a7e  mov     rbx, [rbx]
0x180006a81  call    cs:__imp_free
0x180006a87  test    rbx, rbx
0x180006a8a  jnz     short loc_180006A7B
0x180006a8c  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006a90  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006a95  mov     eax, edi
0x180006a97  mov     rcx, [rbp+9D0h+var_40]
0x180006a9e  xor     rcx, rbp; StackCookie
0x180006aa1  call    __security_check_cookie
0x180006aa6  mov     rbx, [rbp+9D0h+arg_10]
0x180006aad  lea     rsp, [rbp+9A0h]
0x180006ab4  pop     r15
0x180006ab6  pop     r14
0x180006ab8  pop     r13
0x180006aba  pop     r12
0x180006abc  pop     rdi
0x180006abd  pop     rsi
0x180006abe  pop     rbp
0x180006abf  retn
0x180006ac0  mov     rcx, rbx; Block
0x180006ac3  mov     rbx, [rbx]
0x180006ac6  call    cs:__imp_free
0x180006acc  test    rbx, rbx
0x180006acf  jnz     short loc_180006AC0
0x180006ad1  mov     ebx, 80004005h
0x180006ad6  jmp     short loc_180006AEE
0x180006ad8  mov     rcx, rbx; Block
0x180006adb  mov     rbx, [rbx]
0x180006ade  call    cs:__imp_free
0x180006ae4  test    rbx, rbx
0x180006ae7  jnz     short loc_180006AD8
0x180006ae9  mov     ebx, 8007000Eh
0x180006aee  lea     rcx, [rbp+9D0h+WideCharStr]; this
0x180006af2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006af7  mov     eax, ebx
0x180006af9  jmp     short loc_180006A97
0x180006afb  call    __report_rangecheckfailure
0x180006b01  mov     ecx, 80070057h; int
0x180006b06  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
