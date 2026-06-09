# Dynamo::details::DataStore::DataStore(ushort const *,ushort const *,bool)

- ea: `0x14004002c`
- end: `0x140040456`
- name: `??0DataStore@details@Dynamo@@QEAA@PEBG0_N@Z`
- size: `1066`
- prototype: `Dynamo::details::DataStore *__fastcall(Dynamo::details::DataStore *this, char *, char *, const char *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140039fe8`

## callees

- `0x1400042f0`
- `0x14000a6a8`
- `0x14000a6e4`
- `0x14000bb88`
- `0x14001e784`
- `0x14001ed14`
- `0x14002a688`
- `0x14003d008`
- `0x14003d0d0`
- `0x14003e278`
- `0x14003fb78`
- `0x14004002c`
- `0x14004089c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400402bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400402bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400402cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400402dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400402cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400402dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040378`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400402fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004038b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400402fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004038b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400402e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400402e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040383`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400400db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400400f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140040163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004017c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400400db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400400f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140040163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004017c`

## string_xrefs

- `0x14004040f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140040421`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
Dynamo::details::DataStore *__fastcall Dynamo::details::DataStore::DataStore(
        Dynamo::details::DataStore *this,
        char *a2,
        char *a3,
        const char *a4)
{
  char v4; // r13
  HLOCAL v7; // rax
  HLOCAL *p_hMem; // rcx
  int v9; // edi
  const char *v10; // r9
  int v11; // edi
  HLOCAL v12; // rax
  HLOCAL *v13; // rcx
  unsigned int v14; // edi
  HKEY *v15; // r14
  void **v16; // r15
  void *v17; // rbx
  int v18; // edi
  __int64 v19; // rax
  _OWORD *v20; // r12
  int v21; // edi
  void *v22; // rbx
  __int64 v23; // rax
  int v24; // edi
  __int64 v25; // rax
  void *v26; // rdx
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE Mutex; // r12
  void *v30; // rbx
  DWORD LastError; // r13d
  unsigned int v32; // r8d
  const char *v33; // r9
  const unsigned __int16 *v34; // r9
  HKEY v35; // rdi
  DWORD v36; // ebx
  int DynamicManagementRegistryKey; // eax
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  HKEY *v41; // [rsp+28h] [rbp-D8h]
  char v42; // [rsp+30h] [rbp-D0h]
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL v44[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v45[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v46[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD Src[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v48[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v49[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v50[32]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v4 = (char)a4;
  v42 = (char)a4;
  v44[1] = this;
  LODWORD(hMem) = 0;
  *(_QWORD *)this = &Dynamo::details::DataStore::`vftable';
  if ( a2 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v44,
      a2,
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    LODWORD(hMem) = 256;
    v7 = v44[0];
    if ( !v44[0] )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    p_hMem = v44;
    v9 = 129;
  }
  else
  {
    p_hMem = &hMem;
    v9 = 2;
    v7 = 0;
  }
  *((_QWORD *)this + 1) = v7;
  *p_hMem = 0;
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    if ( hMem )
      LocalFree(hMem);
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    if ( v44[0] )
      LocalFree(v44[0]);
  }
  if ( a3 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v44,
      a3,
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    v11 = v9 | 0x400;
    LODWORD(hMem) = v11;
    v12 = v44[0];
    if ( !v44[0] )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    LODWORD(hMem) = v11 & 0xFFFFFBFF;
    v13 = v44;
    v14 = v11 & 0xFFFFF9FB | 0x204;
  }
  else
  {
    v13 = &hMem;
    v14 = v9 | 8;
    v12 = 0;
  }
  *((_QWORD *)this + 2) = v12;
  *v13 = 0;
  if ( (v14 & 8) != 0 )
  {
    v14 &= ~8u;
    if ( hMem )
      LocalFree(hMem);
  }
  if ( (v14 & 4) != 0 )
  {
    v14 &= ~4u;
    if ( v44[0] )
      LocalFree(v44[0]);
  }
  v15 = (HKEY *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  v16 = (void **)((char *)this + 32);
  v44[0] = (char *)this + 32;
  v17 = (void *)*((_QWORD *)this + 2);
  if ( v17 )
  {
    memset(Src, 0, sizeof(Src));
    std::wstring::_Construct<1,unsigned short const *>((char **)Src, L"-", 1u);
    v18 = v14 | 0x10;
    LODWORD(hMem) = v18;
    v19 = std::wstring::append(Src, v17);
    v49[0] = *(_OWORD *)v19;
    v49[1] = *(_OWORD *)(v19 + 16);
    *(_QWORD *)(v19 + 16) = 0;
    *(_QWORD *)(v19 + 24) = 7;
    *(_WORD *)v19 = 0;
    v20 = v49;
    v21 = v18 | 0x820;
  }
  else
  {
    v46[0] = 0;
    v46[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v46[0]) = 0;
    v20 = v46;
    v21 = v14 | 0x40;
  }
  LODWORD(hMem) = v21;
  v22 = (void *)*((_QWORD *)this + 1);
  memset(v45, 0, sizeof(v45));
  std::wstring::_Construct<1,unsigned short const *>((char **)v45, L"Global\\Dynamo-", 0xEu);
  v23 = std::wstring::append(v45, v22);
  v48[0] = *(_OWORD *)v23;
  v48[1] = *(_OWORD *)(v23 + 16);
  *(_QWORD *)(v23 + 16) = 0;
  *(_QWORD *)(v23 + 24) = 7;
  *(_WORD *)v23 = 0;
  v24 = v21 | 0x1000;
  LODWORD(hMem) = v24;
  v25 = std::operator+<unsigned short>(v50, v48, v20);
  if ( *(_QWORD *)(v25 + 24) > 7u )
    v25 = *(_QWORD *)v25;
  *v16 = 0;
  Mutex = CreateMutexExW(0, (LPCWSTR)v25, 0, 0x1F0001u);
  if ( !Mutex )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v26, v27, v28);
  GetLastError();
  v30 = *v16;
  if ( *v16 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v30) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    SetLastError(LastError);
    v4 = v42;
  }
  *v16 = Mutex;
  std::wstring::~wstring(v50);
  std::wstring::~wstring(v48);
  std::wstring::~wstring(v45);
  if ( (v24 & 0x40) != 0 )
  {
    LOBYTE(v24) = v24 & 0xBF;
    std::wstring::~wstring(v46);
  }
  if ( (v24 & 0x20) != 0 )
  {
    LOBYTE(v24) = v24 & 0xDF;
    std::wstring::~wstring(v49);
  }
  if ( (v24 & 0x10) != 0 )
    std::wstring::~wstring(Src);
  if ( !*((_QWORD *)this + 1) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)0x80070057LL,
      v39);
  v35 = *v15;
  if ( *v15 )
  {
    v36 = GetLastError();
    RegCloseKey(v35);
    SetLastError(v36);
  }
  *v15 = 0;
  LOBYTE(v34) = v4;
  DynamicManagementRegistryKey = dmstd::GetDynamicManagementRegistryKey(
                                   *((dmstd **)this + 1),
                                   *((const unsigned __int16 **)this + 2),
                                   L"Contexts",
                                   v34,
                                   (unsigned __int8)this + 24,
                                   v41);
  if ( DynamicManagementRegistryKey < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      (const char *)(unsigned int)DynamicManagementRegistryKey,
      v40);
  anonymous_namespace_::CreateWnfIfNeeded(*v15);
  return this;
}

```

## disassembly

```asm
0x14004002c  push    rbp
0x14004002e  push    rbx
0x14004002f  push    rsi
0x140040030  push    rdi
0x140040031  push    r12
0x140040033  push    r13
0x140040035  push    r14
0x140040037  push    r15
0x140040039  lea     rbp, [rsp-28h]
0x14004003e  sub     rsp, 128h
0x140040045  mov     rax, cs:__security_cookie
0x14004004c  xor     rax, rsp
0x14004004f  mov     [rbp+60h+var_50], rax
0x140040053  mov     r13b, r9b
0x140040056  mov     [rsp+160h+var_130], r9b
0x14004005b  mov     rbx, r8
0x14004005e  mov     rsi, rcx
0x140040061  mov     [rsp+160h+var_118], rcx
0x140040066  xor     r12d, r12d
0x140040069  mov     dword ptr [rsp+160h+hMem], r12d
0x14004006e  lea     rax, ??_7DataStore@details@Dynamo@@6B@; const Dynamo::details::DataStore::`vftable'
0x140040075  mov     [rcx], rax
0x140040078  or      r14, 0FFFFFFFFFFFFFFFFh
0x14004007c  test    rdx, rdx
0x14004007f  jz      short loc_1400400B4
0x140040081  mov     r8, r14
0x140040084  lea     rcx, [rsp+160h+var_120]
0x140040089  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14004008e  mov     dword ptr [rsp+160h+hMem], 100h
0x140040096  mov     rcx, [rbp+68h]; this
0x14004009a  mov     rax, [rsp+160h+var_120]
0x14004009f  test    rax, rax
0x1400400a2  jz      loc_14004040F
0x1400400a8  lea     rcx, [rsp+160h+var_120]
0x1400400ad  mov     edi, 81h
0x1400400b2  jmp     short loc_1400400C1
0x1400400b4  lea     rcx, [rsp+160h+hMem]
0x1400400b9  mov     edi, 2
0x1400400be  mov     rax, r12
0x1400400c1  mov     [rsi+8], rax
0x1400400c5  mov     [rcx], r12
0x1400400c8  test    dil, 2
0x1400400cc  jz      short loc_1400400E1
0x1400400ce  and     edi, 0FFFFFFFDh
0x1400400d1  mov     rcx, [rsp+160h+hMem]; hMem
0x1400400d6  test    rcx, rcx
0x1400400d9  jz      short loc_1400400E1
0x1400400db  call    cs:__imp_LocalFree
0x1400400e1  test    dil, 1
0x1400400e5  jz      short loc_1400400FA
0x1400400e7  and     edi, 0FFFFFFFEh
0x1400400ea  mov     rcx, [rsp+160h+var_120]; hMem
0x1400400ef  test    rcx, rcx
0x1400400f2  jz      short loc_1400400FA
0x1400400f4  call    cs:__imp_LocalFree
0x1400400fa  test    rbx, rbx
0x1400400fd  jz      short loc_14004013E
0x1400400ff  mov     r8, r14
0x140040102  mov     rdx, rbx
0x140040105  lea     rcx, [rsp+160h+var_120]
0x14004010a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14004010f  bts     edi, 0Ah
0x140040113  mov     dword ptr [rsp+160h+hMem], edi
0x140040117  mov     rcx, [rbp+68h]; this
0x14004011b  mov     rax, [rsp+160h+var_120]
0x140040120  test    rax, rax
0x140040123  jz      loc_140040421
0x140040129  btr     edi, 0Ah
0x14004012d  mov     dword ptr [rsp+160h+hMem], edi
0x140040131  lea     rcx, [rsp+160h+var_120]
0x140040136  or      edi, 204h
0x14004013c  jmp     short loc_140040149
0x14004013e  lea     rcx, [rsp+160h+hMem]
0x140040143  or      edi, 8
0x140040146  mov     rax, r12
0x140040149  mov     [rsi+10h], rax
0x14004014d  mov     [rcx], r12
0x140040150  test    dil, 8
0x140040154  jz      short loc_140040169
0x140040156  and     edi, 0FFFFFFF7h
0x140040159  mov     rcx, [rsp+160h+hMem]; hMem
0x14004015e  test    rcx, rcx
0x140040161  jz      short loc_140040169
0x140040163  call    cs:__imp_LocalFree
0x140040169  test    dil, 4
0x14004016d  jz      short loc_140040182
0x14004016f  and     edi, 0FFFFFFFBh
0x140040172  mov     rcx, [rsp+160h+var_120]; hMem
0x140040177  test    rcx, rcx
0x14004017a  jz      short loc_140040182
0x14004017c  call    cs:__imp_LocalFree
0x140040182  lea     r14, [rsi+18h]
0x140040186  mov     [r14], r12
0x140040189  lea     r15, [rsi+20h]
0x14004018d  mov     [rsp+160h+var_120], r15
0x140040192  mov     rbx, [rsi+10h]
0x140040196  xorps   xmm0, xmm0
0x140040199  test    rbx, rbx
0x14004019c  jz      short loc_140040200
0x14004019e  movups  [rbp+60h+Src], xmm0
0x1400401a2  xorps   xmm1, xmm1
0x1400401a5  movdqu  [rbp+60h+var_C0], xmm1
0x1400401aa  mov     r8d, 1
0x1400401b0  lea     rdx, asc_140067560; "-"
0x1400401b7  lea     rcx, [rbp+60h+Src]
0x1400401bb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400401c0  nop
0x1400401c1  or      edi, 10h
0x1400401c4  mov     dword ptr [rsp+160h+hMem], edi
0x1400401c8  mov     rdx, rbx; void *
0x1400401cb  lea     rcx, [rbp+60h+Src]; Src
0x1400401cf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1400401d4  movups  xmm0, xmmword ptr [rax]
0x1400401d7  movups  [rbp+60h+var_90], xmm0
0x1400401db  movups  xmm1, xmmword ptr [rax+10h]
0x1400401df  movups  [rbp+60h+var_80], xmm1
0x1400401e3  mov     [rax+10h], r12
0x1400401e7  mov     qword ptr [rax+18h], 7
0x1400401ef  mov     [rax], r12w
0x1400401f3  bts     edi, 0Bh
0x1400401f7  lea     r12, [rbp+60h+var_90]
0x1400401fb  or      edi, 20h
0x1400401fe  jmp     short loc_140040220
0x140040200  movups  [rsp+160h+var_F0], xmm0
0x140040205  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14004020d  movdqu  [rbp+60h+var_E0], xmm1
0x140040212  mov     word ptr [rsp+160h+var_F0], r12w
0x140040218  lea     r12, [rsp+160h+var_F0]
0x14004021d  or      edi, 40h
0x140040220  mov     dword ptr [rsp+160h+hMem], edi
0x140040224  mov     rbx, [rsi+8]
0x140040228  xorps   xmm0, xmm0
0x14004022b  movups  [rsp+160h+var_110], xmm0
0x140040230  xorps   xmm1, xmm1
0x140040233  movdqu  [rsp+160h+var_100], xmm1
0x140040239  mov     r8d, 0Eh
0x14004023f  lea     rdx, aGlobalDynamo; "Global\\Dynamo-"
0x140040246  lea     rcx, [rsp+160h+var_110]
0x14004024b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140040250  nop
0x140040251  mov     rdx, rbx; void *
0x140040254  lea     rcx, [rsp+160h+var_110]; Src
0x140040259  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14004025e  mov     rcx, rax
0x140040261  movups  xmm0, xmmword ptr [rax]
0x140040264  movups  [rbp+60h+var_B0], xmm0
0x140040268  movups  xmm1, xmmword ptr [rax+10h]
0x14004026c  movups  [rbp+60h+var_A0], xmm1
0x140040270  mov     qword ptr [rax+10h], 0
0x140040278  mov     qword ptr [rax+18h], 7
0x140040280  xor     eax, eax
0x140040282  mov     [rcx], ax
0x140040285  bts     edi, 0Ch
0x140040289  mov     dword ptr [rsp+160h+hMem], edi
0x14004028d  mov     r8, r12
0x140040290  lea     rdx, [rbp+60h+var_B0]
0x140040294  lea     rcx, [rbp+60h+var_70]
0x140040298  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x14004029d  nop
0x14004029e  cmp     qword ptr [rax+18h], 7
0x1400402a3  jbe     short loc_1400402A8
0x1400402a5  mov     rax, [rax]
0x1400402a8  mov     qword ptr [r15], 0
0x1400402af  mov     r9d, 1F0001h; dwDesiredAccess
0x1400402b5  xor     r8d, r8d; dwFlags
0x1400402b8  mov     rdx, rax; lpName
0x1400402bb  xor     ecx, ecx; lpMutexAttributes
0x1400402bd  call    cs:__imp_CreateMutexExW
0x1400402c3  mov     r12, rax
0x1400402c6  test    rax, rax
0x1400402c9  jz      loc_140040405
0x1400402cf  call    cs:__imp_GetLastError
0x1400402d5  mov     rbx, [r15]
0x1400402d8  test    rbx, rbx
0x1400402db  jz      short loc_140040309
0x1400402dd  call    cs:__imp_GetLastError
0x1400402e3  mov     r13d, eax
0x1400402e6  mov     rcx, rbx; hObject
0x1400402e9  call    cs:__imp_CloseHandle
0x1400402ef  mov     rcx, [rbp+68h]; this
0x1400402f3  test    eax, eax
0x1400402f5  jz      loc_140040433
0x1400402fb  mov     ecx, r13d; dwErrCode
0x1400402fe  call    cs:__imp_SetLastError
0x140040304  mov     r13b, [rsp+160h+var_130]
0x140040309  mov     [r15], r12
0x14004030c  lea     rcx, [rbp+60h+var_70]
0x140040310  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040315  nop
0x140040316  lea     rcx, [rbp+60h+var_B0]
0x14004031a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004031f  nop
0x140040320  lea     rcx, [rsp+160h+var_110]
0x140040325  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004032a  nop
0x14004032b  test    dil, 40h
0x14004032f  jz      short loc_14004033F
0x140040331  and     edi, 0FFFFFFBFh
0x140040334  lea     rcx, [rsp+160h+var_F0]
0x140040339  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004033e  nop
0x14004033f  test    dil, 20h
0x140040343  jz      short loc_140040352
0x140040345  and     edi, 0FFFFFFDFh
0x140040348  lea     rcx, [rbp+60h+var_90]
0x14004034c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040351  nop
0x140040352  test    dil, 10h
0x140040356  jz      short loc_140040361
0x140040358  lea     rcx, [rbp+60h+Src]
0x14004035c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040361  mov     rcx, [rbp+68h]; this
0x140040365  cmp     qword ptr [rsi+8], 0
0x14004036a  jz      loc_14004043E
0x140040370  mov     rdi, [r14]
0x140040373  test    rdi, rdi
0x140040376  jz      short loc_140040391
0x140040378  call    cs:__imp_GetLastError
0x14004037e  mov     ebx, eax
0x140040380  mov     rcx, rdi; hKey
0x140040383  call    cs:__imp_RegCloseKey
0x140040389  mov     ecx, ebx; dwErrCode
0x14004038b  call    cs:__imp_SetLastError
0x140040391  mov     qword ptr [r14], 0
0x140040398  mov     qword ptr [rsp+160h+var_140], r14; int
0x14004039d  mov     r9b, r13b; unsigned __int16 *
0x1400403a0  lea     r8, aContexts; "Contexts"
0x1400403a7  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1400403ab  mov     rcx, [rsi+8]; this
0x1400403af  call    ?GetDynamicManagementRegistryKey@dmstd@@YAJPEBG00_NPEAPEAUHKEY__@@@Z; dmstd::GetDynamicManagementRegistryKey(ushort const *,ushort const *,ushort const *,bool,HKEY__ * *)
0x1400403b4  mov     rcx, [rbp+68h]; this
0x1400403b8  test    eax, eax
0x1400403ba  js      short loc_1400403F0
0x1400403bc  mov     r8, [rsi+10h]
0x1400403c0  mov     rdx, [rsi+8]
0x1400403c4  mov     rcx, [r14]; hKey
0x1400403c7  call    _anonymous_namespace___CreateWnfIfNeeded
0x1400403cc  nop
0x1400403cd  mov     rax, rsi
0x1400403d0  mov     rcx, [rbp+60h+var_50]
0x1400403d4  xor     rcx, rsp; StackCookie
0x1400403d7  call    __security_check_cookie
0x1400403dc  add     rsp, 128h
0x1400403e3  pop     r15
0x1400403e5  pop     r14
0x1400403e7  pop     r13
0x1400403e9  pop     r12
0x1400403eb  pop     rdi
0x1400403ec  pop     rsi
0x1400403ed  pop     rbx
0x1400403ee  pop     rbp
0x1400403ef  retn
0x1400403f0  mov     r9d, eax; char *
0x1400403f3  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400403fa  mov     edx, 6Dh ; 'm'; void *
0x1400403ff  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140040405  mov     rcx, [rbp+68h]; this
0x140040409  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14004040f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140040416  mov     edx, 0FF8h; void *
0x14004041b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140040421  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140040428  mov     edx, 0FF8h; void *
0x14004042d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140040433  mov     edx, 0A0Bh; void *
0x140040438  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14004043e  mov     r9d, 80070057h; char *
0x140040444  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14004044b  mov     edx, 6Ch ; 'l'; void *
0x140040450  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
