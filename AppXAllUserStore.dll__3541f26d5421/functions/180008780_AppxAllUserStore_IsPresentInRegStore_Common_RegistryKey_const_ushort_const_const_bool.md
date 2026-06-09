# AppxAllUserStore::IsPresentInRegStore(Common::RegistryKey const *,ushort const * const,bool *)

- ea: `0x180008780`
- end: `0x180008da1`
- name: `?IsPresentInRegStore@AppxAllUserStore@@YAJPEBVRegistryKey@Common@@QEBGPEA_N@Z`
- size: `1569`
- prototype: `int(AppxAllUserStore *__hidden this, const struct Common::RegistryKey *, const unsigned __int16 *const, bool *)`
- caller_count: `5`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007638`
- `0x18000c6e4`
- `0x180018698`
- `0x18002919c`
- `0x18002ad3c`

## callees

- `0x1800036d4`
- `0x180003a38`
- `0x180004920`
- `0x180004968`
- `0x180006c00`
- `0x180006d40`
- `0x180007a10`
- `0x180008780`
- `0x180009040`
- `0x180017f50`
- `0x18004c972`
- `0x18004c98a`
- `0x18004c9d0`
- `0x18004d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000881f`
- `msvcrt!_wcsicmp` at `0x18000881f`
- `ntdll!RtlFreeHeap` at `0x180008ab7`
- `ntdll!RtlFreeHeap` at `0x180008ab7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008cb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008cb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008d20`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008803`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008a85`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008803`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008a85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008a2a`

## string_xrefs

- `0x180008ac9`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008af4`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008b0c`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008b37`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008b4f`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008b7a`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008d48`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008d68`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180008d88`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::IsPresentInRegStore(HKEY *this, const wchar_t *a2, unsigned __int16 *a3, bool *a4)
{
  unsigned int v7; // ebx
  DWORD v8; // r15d
  LSTATUS v9; // edi
  __int64 v10; // rcx
  WCHAR *p_Name; // rax
  __int64 v12; // r9
  __int64 v13; // rdx
  unsigned int v14; // edi
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // esi
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rax
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned int v22; // ebx
  __int64 v23; // rdi
  int v24; // eax
  unsigned int v25; // esi
  __int64 v26; // rcx
  const wchar_t *v27; // rax
  unsigned int v28; // ebx
  __int64 v29; // r9
  __int64 v30; // rdi
  int v31; // eax
  unsigned int v32; // esi
  HKEY v33; // rcx
  int v34; // eax
  const unsigned __int16 *v35; // rdx
  struct Common::StringBuffer *v36; // r9
  bool v37; // sf
  HKEY v38; // rcx
  __int64 v39; // rdx
  int AllUserChildStorePath; // eax
  __int64 v42; // rcx
  HKEY v43; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  const int *v46; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR *v47; // [rsp+58h] [rbp-A8h]
  LPCWSTR *v48; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpSubKey[2]; // [rsp+68h] [rbp-98h] BYREF
  int v50; // [rsp+78h] [rbp-88h]
  void *v51[2]; // [rsp+80h] [rbp-80h] BYREF
  int v52; // [rsp+90h] [rbp-70h]
  const int *v53; // [rsp+98h] [rbp-68h] BYREF
  void **v54; // [rsp+A0h] [rbp-60h]
  void **v55; // [rsp+A8h] [rbp-58h]
  WCHAR Name; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v57[526]; // [rsp+B2h] [rbp-4Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  cchName = 261;
  Name = 0;
  v7 = 0;
  *(_BYTE *)a3 = 0;
  memset_0(v57, 0, 0x208u);
  v8 = 0;
  v9 = RegEnumKeyExW(*this, 0, &Name, &cchName, 0, 0, 0, 0);
  while ( 1 )
  {
    if ( v9 )
    {
      if ( v9 != 259 )
      {
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        else
          return (unsigned int)v9;
      }
      return v7;
    }
    if ( !_wcsicmp(&Name, a2) )
    {
      *(_BYTE *)a3 = 1;
      return 0;
    }
    v50 = 0;
    v47 = lpSubKey;
    v10 = 0x3FFFFFFF;
    v46 = &Common::StringBufferBuilder::`vftable';
    v48 = lpSubKey;
    p_Name = &Name;
    *(_OWORD *)lpSubKey = 0;
    while ( *p_Name )
    {
      ++p_Name;
      if ( !--v10 )
      {
        v12 = 2147942487LL;
        v13 = 53;
        goto LABEL_43;
      }
    }
    v14 = _mm_cvtsi128_si32((__m128i)0LL);
    v15 = 0x3FFFFFFF - v10;
    if ( v14 > ~(0x3FFFFFFF - (int)v10) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x107,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)0x80070216LL);
      v17 = -2147024362;
    }
    else if ( v15 + v14 > 0x3FFFFFFF )
    {
      v17 = -2147023613;
    }
    else
    {
      v16 = Common::StringBufferBuilder::SetLength((Common::StringBufferBuilder *)&v46, v15 + v14);
      v17 = v16;
      if ( v16 >= 0 )
      {
        memcpy_0((void *)&v47[1][v14], &Name, 2LL * v15);
        goto LABEL_12;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10D,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v16);
    }
    v12 = v17;
    v13 = 121;
LABEL_43:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v13,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v12);
LABEL_12:
    v18 = 0x3FFFFFFF;
    v19 = L"\\";
    while ( *v19 )
    {
      ++v19;
      if ( !--v18 )
      {
        v20 = 2147942487LL;
        v21 = 53;
        goto LABEL_46;
      }
    }
    v22 = 0x3FFFFFFF - v18;
    v23 = *(unsigned int *)v47;
    if ( (unsigned int)v23 > ~(0x3FFFFFFF - (int)v18) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x107,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)0x80070216LL);
      v25 = -2147024362;
    }
    else if ( v22 + (unsigned int)v23 > 0x3FFFFFFF )
    {
      v25 = -2147023613;
    }
    else
    {
      v24 = (*(__int64 (__fastcall **)(const int **))v46)(&v46);
      v25 = v24;
      if ( v24 >= 0 )
      {
        memcpy_0((void *)&v47[1][v23], L"\\", 2LL * v22);
        goto LABEL_20;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10D,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v24);
    }
    v20 = v25;
    v21 = 121;
LABEL_46:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v21,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v20);
LABEL_20:
    if ( !a2 )
    {
      v29 = 2147942487LL;
LABEL_66:
      v39 = 53;
      goto LABEL_49;
    }
    v26 = 0x3FFFFFFF;
    v27 = a2;
    while ( *v27 )
    {
      ++v27;
      if ( !--v26 )
      {
        v28 = 0;
        v29 = 2147942487LL;
        goto LABEL_26;
      }
    }
    v28 = 0x3FFFFFFF - v26;
    v29 = 0;
LABEL_26:
    if ( (int)v29 < 0 )
      goto LABEL_66;
    v30 = *(unsigned int *)v47;
    if ( (unsigned int)v30 > ~v28 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x107,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)0x80070216LL);
      v32 = -2147024362;
    }
    else if ( (unsigned int)v30 + v28 > 0x3FFFFFFF )
    {
      v32 = -2147023613;
    }
    else
    {
      v31 = (*(__int64 (__fastcall **)(const int **))v46)(&v46);
      v32 = v31;
      if ( v31 >= 0 )
      {
        memcpy_0((void *)&v47[1][v30], a2, 2LL * v28);
        goto LABEL_31;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10D,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v31);
    }
    v29 = v32;
    v39 = 121;
LABEL_49:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v39,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v29);
LABEL_31:
    v33 = *this;
    phkResult = 0;
    v34 = RegOpenKeyExW(v33, lpSubKey[1], 0, 0x20019u, &phkResult);
    v37 = v34 < 0;
    if ( v34 > 0 )
    {
      v34 = (unsigned __int16)v34 | 0x80070000;
      v37 = v34 < 0;
    }
    if ( !v37 )
      break;
    v7 = 0;
    if ( v34 != -2147024894 )
      v7 = v34;
    if ( (v7 & 0x80000000) != 0 )
    {
      v52 = 0;
      LOBYTE(v35) = 1;
      *(_OWORD *)v51 = 0;
      AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                                (AppxAllUserStore *)L"Applications",
                                v35,
                                (unsigned int *)v51,
                                v36);
      v7 = AllUserChildStorePath;
      if ( AllUserChildStorePath < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x55,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
          (const char *)(unsigned int)AllUserChildStorePath);
        if ( v51[1] )
          Common::GlobalHeap::Free(v51[1]);
        if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(phkResult);
        if ( lpSubKey[1] )
          Common::GlobalHeap::Free((void *)lpSubKey[1]);
      }
      else
      {
        v54 = v51;
        v53 = &Common::StringBufferBuilder::`vftable';
        v55 = v51;
        Common::StringBuilder::AppendChar((Common::StringBuilder *)&v53, 92);
        Common::StringBuilder::AppendString((Common::StringBuilder *)&v53, lpSubKey[1]);
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
          McTemplateU0zd_EventWriteTransfer(v42, AppxAllUserStoreOpenKeyError, v54[1], v7);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v51);
        Common::RegistryKey::~RegistryKey(&phkResult);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
      }
      return v7;
    }
    v38 = *this;
    ++v8;
    cchName = 261;
    v9 = RegEnumKeyExW(v38, v8, &Name, &cchName, 0, 0, 0, 0);
    if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(phkResult);
    if ( lpSubKey[1] )
      RtlFreeHeap(ReservedForLocalUse::g_heap, 0, (PVOID)lpSubKey[1]);
  }
  v43 = phkResult;
  *(_BYTE *)a3 = 1;
  if ( (unsigned __int64)v43 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v43);
  if ( lpSubKey[1] )
    Common::GlobalHeap::Free((void *)lpSubKey[1]);
  return 0;
}

```

## disassembly

```asm
0x180008780  mov     [rsp-8+arg_18], rbx
0x180008785  push    rbp
0x180008786  push    rsi
0x180008787  push    rdi
0x180008788  push    r12
0x18000878a  push    r13
0x18000878c  push    r14
0x18000878e  push    r15
0x180008790  lea     rbp, [rsp-1D0h]
0x180008798  sub     rsp, 2D0h
0x18000879f  mov     rax, cs:__security_cookie
0x1800087a6  xor     rax, rsp
0x1800087a9  mov     [rbp+200h+var_40], rax
0x1800087b0  xor     esi, esi
0x1800087b2  mov     [rsp+300h+cchName], 105h
0x1800087ba  mov     r13, r8
0x1800087bd  mov     [rbp+200h+Name], si
0x1800087c1  mov     r14, rdx
0x1800087c4  mov     r12, rcx
0x1800087c7  mov     ebx, esi
0x1800087c9  lea     rcx, [rbp+200h+var_24E]; void *
0x1800087cd  mov     [r8], bl
0x1800087d0  xor     edx, edx; Val
0x1800087d2  mov     r8d, 208h; Size
0x1800087d8  call    memset_0
0x1800087dd  mov     rcx, [r12]; hKey
0x1800087e1  lea     r9, [rsp+300h+cchName]; lpcchName
0x1800087e6  mov     [rsp+300h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800087eb  lea     r8, [rbp+200h+Name]; lpName
0x1800087ef  mov     [rsp+300h+lpcchClass], rsi; lpcchClass
0x1800087f4  xor     edx, edx; dwIndex
0x1800087f6  mov     [rsp+300h+lpClass], rsi; lpClass
0x1800087fb  mov     r15d, esi
0x1800087fe  mov     [rsp+300h+lpReserved], rsi; int
0x180008803  call    cs:__imp_RegEnumKeyExW
0x180008809  mov     edi, eax
0x18000880b  nop     dword ptr [rax+rax+00h]
0x180008810  test    edi, edi
0x180008812  jnz     loc_180008BAE
0x180008818  mov     rdx, r14; String2
0x18000881b  lea     rcx, [rbp+200h+Name]; String1
0x18000881f  call    cs:__imp__wcsicmp
0x180008825  test    eax, eax
0x180008827  jz      loc_180008BE6
0x18000882d  lea     rax, [rsp+300h+lpSubKey]
0x180008832  mov     [rsp+300h+var_288], esi
0x180008836  mov     [rsp+300h+var_2A8], rax
0x18000883b  xorps   xmm0, xmm0
0x18000883e  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180008845  mov     ecx, 3FFFFFFFh
0x18000884a  mov     [rsp+300h+var_2B0], rax
0x18000884f  lea     rax, [rsp+300h+lpSubKey]
0x180008854  mov     [rsp+300h+var_2A0], rax
0x180008859  lea     rax, [rbp+200h+Name]
0x18000885d  movups  xmmword ptr [rsp+300h+lpSubKey], xmm0
0x180008862  cmp     word ptr [rax], 0
0x180008866  jz      short loc_180008882
0x180008868  add     rax, 2
0x18000886c  sub     rcx, 1
0x180008870  jnz     short loc_180008862
0x180008872  mov     r9d, 80070057h
0x180008878  mov     edx, 35h ; '5'
0x18000887d  jmp     loc_180008AED
0x180008882  mov     ebx, 3FFFFFFFh
0x180008887  movd    edi, xmm0
0x18000888b  sub     ebx, ecx
0x18000888d  mov     eax, ebx
0x18000888f  not     eax
0x180008891  cmp     edi, eax
0x180008893  ja      loc_180008AC2
0x180008899  lea     edx, [rbx+rdi]; unsigned int
0x18000889c  cmp     edx, 3FFFFFFFh
0x1800088a2  ja      loc_180008B8B
0x1800088a8  lea     rcx, [rsp+300h+var_2B0]; this
0x1800088ad  call    ?SetLength@StringBufferBuilder@Common@@UEAAJK@Z; Common::StringBufferBuilder::SetLength(ulong)
0x1800088b2  mov     esi, eax
0x1800088b4  test    eax, eax
0x1800088b6  js      loc_180008D41
0x1800088bc  mov     rax, [rsp+300h+var_2A8]
0x1800088c1  lea     rdx, [rbp+200h+Name]; Src
0x1800088c5  mov     r8d, ebx
0x1800088c8  add     r8, r8; Size
0x1800088cb  mov     rcx, [rax+8]
0x1800088cf  lea     rcx, [rcx+rdi*2]; void *
0x1800088d3  call    memcpy_0
0x1800088d8  mov     ecx, 3FFFFFFFh
0x1800088dd  lea     rax, asc_18004F868; "\\"
0x1800088e4  cmp     word ptr [rax], 0
0x1800088e8  jz      short loc_180008904
0x1800088ea  add     rax, 2
0x1800088ee  sub     rcx, 1
0x1800088f2  jnz     short loc_1800088E4
0x1800088f4  mov     r9d, 80070057h
0x1800088fa  mov     edx, 35h ; '5'
0x1800088ff  jmp     loc_180008B30
0x180008904  mov     rax, [rsp+300h+var_2A8]
0x180008909  mov     ebx, 3FFFFFFFh
0x18000890e  sub     ebx, ecx
0x180008910  mov     edi, [rax]
0x180008912  mov     eax, ebx
0x180008914  not     eax
0x180008916  cmp     edi, eax
0x180008918  ja      loc_180008B05
0x18000891e  lea     edx, [rbx+rdi]
0x180008921  cmp     edx, 3FFFFFFFh
0x180008927  ja      loc_180008B95
0x18000892d  mov     rax, [rsp+300h+var_2B0]
0x180008932  lea     rcx, [rsp+300h+var_2B0]
0x180008937  mov     rax, [rax]
0x18000893a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000893f  mov     esi, eax
0x180008941  test    eax, eax
0x180008943  js      loc_180008D61
0x180008949  mov     rax, [rsp+300h+var_2A8]
0x18000894e  lea     rdx, asc_18004F868; "\\"
0x180008955  mov     r8d, ebx
0x180008958  add     r8, r8; Size
0x18000895b  mov     rcx, [rax+8]
0x18000895f  lea     rcx, [rcx+rdi*2]; void *
0x180008963  call    memcpy_0
0x180008968  test    r14, r14
0x18000896b  jz      loc_180008CC0
0x180008971  mov     ecx, 3FFFFFFFh
0x180008976  mov     rax, r14
0x180008979  nop     dword ptr [rax+00000000h]
0x180008980  cmp     word ptr [rax], 0
0x180008984  jz      short loc_18000899A
0x180008986  add     rax, 2
0x18000898a  sub     rcx, 1
0x18000898e  jnz     short loc_180008980
0x180008990  xor     ebx, ebx
0x180008992  mov     r9d, 80070057h
0x180008998  jmp     short loc_1800089A5
0x18000899a  mov     ebx, 3FFFFFFFh
0x18000899f  sub     rbx, rcx
0x1800089a2  xor     r9d, r9d
0x1800089a5  test    r9d, r9d
0x1800089a8  js      loc_180008CC6
0x1800089ae  mov     rax, [rsp+300h+var_2A8]
0x1800089b3  mov     edi, [rax]
0x1800089b5  mov     eax, ebx
0x1800089b7  not     eax
0x1800089b9  cmp     edi, eax
0x1800089bb  ja      loc_180008B48
0x1800089c1  lea     edx, [rdi+rbx]
0x1800089c4  cmp     edx, 3FFFFFFFh
0x1800089ca  ja      loc_180008B9C
0x1800089d0  mov     rax, [rsp+300h+var_2B0]
0x1800089d5  lea     rcx, [rsp+300h+var_2B0]
0x1800089da  mov     rax, [rax]
0x1800089dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e2  mov     esi, eax
0x1800089e4  test    eax, eax
0x1800089e6  js      loc_180008D81
0x1800089ec  mov     rax, [rsp+300h+var_2A8]
0x1800089f1  mov     rdx, r14; Src
0x1800089f4  mov     r8d, ebx
0x1800089f7  add     r8, r8; Size
0x1800089fa  mov     rcx, [rax+8]
0x1800089fe  lea     rcx, [rcx+rdi*2]; void *
0x180008a02  call    memcpy_0
0x180008a07  mov     rdx, [rsp+300h+lpSubKey+8]; lpSubKey
0x180008a0c  lea     rax, [rsp+300h+phkResult]
0x180008a11  mov     rcx, [r12]; hKey
0x180008a15  xor     esi, esi
0x180008a17  mov     r9d, 20019h; samDesired
0x180008a1d  mov     [rsp+300h+phkResult], rsi
0x180008a22  xor     r8d, r8d; ulOptions
0x180008a25  mov     [rsp+300h+lpReserved], rax; int
0x180008a2a  call    cs:__imp_RegOpenKeyExW
0x180008a30  test    eax, eax
0x180008a32  jle     short loc_180008A3E
0x180008a34  movzx   eax, ax
0x180008a37  or      eax, 80070000h
0x180008a3c  test    eax, eax
0x180008a3e  jns     loc_180008C8E
0x180008a44  cmp     eax, 80070002h
0x180008a49  mov     ebx, esi
0x180008a4b  cmovnz  ebx, eax
0x180008a4e  test    ebx, ebx
0x180008a50  js      loc_180008BEF
0x180008a56  mov     rcx, [r12]; hKey
0x180008a5a  lea     r9, [rsp+300h+cchName]; lpcchName
0x180008a5f  mov     [rsp+300h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180008a64  lea     r8, [rbp+200h+Name]; lpName
0x180008a68  mov     [rsp+300h+lpcchClass], rsi; lpcchClass
0x180008a6d  inc     r15d
0x180008a70  mov     [rsp+300h+lpClass], rsi; lpClass
0x180008a75  mov     edx, r15d; dwIndex
0x180008a78  mov     [rsp+300h+lpReserved], rsi; lpReserved
0x180008a7d  mov     [rsp+300h+cchName], 105h
0x180008a85  call    cs:__imp_RegEnumKeyExW
0x180008a8b  mov     rcx, [rsp+300h+phkResult]; hKey
0x180008a90  mov     edi, eax
0x180008a92  lea     rax, [rcx-1]
0x180008a96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008a9a  jbe     loc_180008BA3
0x180008aa0  mov     r8, [rsp+300h+lpSubKey+8]; P
0x180008aa5  test    r8, r8
0x180008aa8  jz      loc_180008810
0x180008aae  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x180008ab5  xor     edx, edx; Flags
0x180008ab7  call    cs:__imp_RtlFreeHeap
0x180008abd  jmp     loc_180008810
0x180008ac2  mov     rcx, [rbp+208h]; this
0x180008ac9  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180008ad0  mov     r9d, 80070216h; char *
0x180008ad6  mov     edx, 107h; void *
0x180008adb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008ae0  mov     esi, 80070216h
0x180008ae5  mov     r9d, esi; char *
0x180008ae8  mov     edx, 79h ; 'y'; void *
0x180008aed  mov     rcx, [rbp+208h]; this
0x180008af4  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180008afb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008b00  jmp     loc_1800088D8
0x180008b05  mov     rcx, [rbp+208h]; this
0x180008b0c  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180008b13  mov     r9d, 80070216h; char *
0x180008b19  mov     edx, 107h; void *
0x180008b1e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008b23  mov     esi, 80070216h
0x180008b28  mov     r9d, esi; char *
0x180008b2b  mov     edx, 79h ; 'y'; void *
0x180008b30  mov     rcx, [rbp+208h]; this
0x180008b37  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180008b3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008b43  jmp     loc_180008968
0x180008b48  mov     rcx, [rbp+208h]; this
0x180008b4f  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180008b56  mov     r9d, 80070216h; char *
0x180008b5c  mov     edx, 107h; void *
0x180008b61  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008b66  mov     esi, 80070216h
0x180008b6b  mov     r9d, esi; char *
0x180008b6e  mov     edx, 79h ; 'y'; void *
0x180008b73  mov     rcx, [rbp+208h]; this
0x180008b7a  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180008b81  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008b86  jmp     loc_180008A07
0x180008b8b  mov     esi, 80070503h
0x180008b90  jmp     loc_180008AE5
0x180008b95  mov     esi, 80070503h
0x180008b9a  jmp     short loc_180008B28
0x180008b9c  mov     esi, 80070503h
0x180008ba1  jmp     short loc_180008B6B
0x180008ba3  call    cs:__imp_RegCloseKey
0x180008ba9  jmp     loc_180008AA0
0x180008bae  cmp     edi, 103h
0x180008bb4  jnz     loc_180008D28
0x180008bba  mov     eax, ebx
0x180008bbc  mov     rcx, [rbp+200h+var_40]
0x180008bc3  xor     rcx, rsp; StackCookie
0x180008bc6  call    __security_check_cookie
0x180008bcb  mov     rbx, [rsp+300h+arg_18]
0x180008bd3  add     rsp, 2D0h
0x180008bda  pop     r15
0x180008bdc  pop     r14
0x180008bde  pop     r13
0x180008be0  pop     r12
0x180008be2  pop     rdi
0x180008be3  pop     rsi
0x180008be4  pop     rbp
0x180008be5  retn
0x180008be6  mov     byte ptr [r13+0], 1
0x180008beb  xor     eax, eax
0x180008bed  jmp     short loc_180008BBC
0x180008bef  xorps   xmm0, xmm0
0x180008bf2  mov     [rbp+200h+var_270], esi
0x180008bf5  lea     r8, [rbp+200h+var_280]; bool
0x180008bf9  mov     dl, 1; unsigned __int16 *
0x180008bfb  lea     rcx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x180008c02  movups  xmmword ptr [rbp+200h+var_280], xmm0
0x180008c06  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180008c0b  mov     ebx, eax
0x180008c0d  test    eax, eax
0x180008c0f  js      loc_180008CD0
0x180008c15  lea     rax, [rbp+200h+var_280]
0x180008c19  mov     edx, 5Ch ; '\'; unsigned __int16
0x180008c1e  mov     [rbp+200h+var_260], rax
0x180008c22  lea     rcx, [rbp+200h+var_268]; this
0x180008c26  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180008c2d  mov     [rbp+200h+var_268], rax
0x180008c31  lea     rax, [rbp+200h+var_280]
0x180008c35  mov     [rbp+200h+var_258], rax
0x180008c39  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x180008c3e  mov     rdx, [rsp+300h+lpSubKey+8]; unsigned __int16 *
0x180008c43  lea     rcx, [rbp+200h+var_268]; this
0x180008c47  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180008c4c  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, sil
0x180008c53  jge     short loc_180008C6C
0x180008c55  mov     r8, [rbp+200h+var_260]
0x180008c59  lea     rdx, AppxAllUserStoreOpenKeyError
0x180008c60  mov     r9d, ebx
0x180008c63  mov     r8, [r8+8]
0x180008c67  call    McTemplateU0zd_EventWriteTransfer
0x180008c6c  lea     rcx, [rbp+200h+var_280]; this
0x180008c70  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180008c75  lea     rcx, [rsp+300h+phkResult]; this
0x180008c7a  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
  ... truncated ...
```
