# Appx::Packaging::CatalogHelper::MergeWithExternalCatalog(ushort const *)

- ea: `0x1801000e4`
- end: `0x1801006d6`
- name: `?MergeWithExternalCatalog@CatalogHelper@Packaging@Appx@@QEAAJPEBG@Z`
- size: `1522`
- prototype: `__int64 __fastcall(Appx::Packaging::CatalogHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180090d60`

## callees

- `0x1800133fc`
- `0x18006a900`
- `0x1800a5640`
- `0x1800ab28c`
- `0x1801000e4`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180100111`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180100111`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180100134`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180100134`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100169`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801001a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801001cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801001f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010024a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100274`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010029e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801002c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801002ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100315`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100169`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801001a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801001cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801001f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010024a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100274`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010029e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801002c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801002ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180100315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100638`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010052f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010052f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180100466`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180100466`

## string_xrefs

- `0x180100103`: `wintrust.dll`
- `0x180100127`: `Wintrust.dll`
- `0x18010015f`: `CryptCATOpen`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::CatalogHelper::MergeWithExternalCatalog(
        Appx::Packaging::CatalogHelper *this,
        const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rbx
  HMODULE Library; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  FARPROC ProcAddress; // rbp
  unsigned int LastError; // ebx
  FARPROC v10; // rdi
  FARPROC v11; // r15
  FARPROC v12; // r12
  char v13; // r14
  __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // rbp
  __int64 v19; // rax
  const char *v20; // r9
  __int64 v21; // r14
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 (__fastcall *v24)(__int64, __int64); // r12
  __int64 i; // rbx
  __int64 v26; // r15
  __int64 j; // r8
  __int64 v28; // rax
  __int64 v29; // r14
  DWORD v30; // eax
  DWORD v31; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-98h]
  __int64 v34; // [rsp+28h] [rbp-90h]
  FARPROC v35; // [rsp+40h] [rbp-78h]
  FARPROC v36; // [rsp+48h] [rbp-70h]
  FARPROC v37; // [rsp+50h] [rbp-68h]
  FARPROC v38; // [rsp+58h] [rbp-60h]
  FARPROC v39; // [rsp+60h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  __int64 v41; // [rsp+D0h] [rbp+18h] BYREF
  FARPROC v42; // [rsp+D8h] [rbp+20h]

  v41 = 0;
  ModuleHandleW = GetModuleHandleW(L"wintrust.dll");
  if ( ModuleHandleW )
  {
LABEL_5:
    ProcAddress = GetProcAddress(ModuleHandleW, "CryptCATOpen");
    if ( !ProcAddress )
    {
      v7 = 574;
      goto LABEL_7;
    }
    v10 = GetProcAddress(ModuleHandleW, "CryptCATClose");
    if ( !v10 )
    {
      v7 = 577;
      goto LABEL_7;
    }
    v39 = GetProcAddress(ModuleHandleW, "CryptCATPersistStore");
    if ( !v39 )
    {
      v7 = 581;
      goto LABEL_7;
    }
    v42 = GetProcAddress(ModuleHandleW, "CryptCATEnumerateMember");
    if ( !v42 )
    {
      v7 = 585;
      goto LABEL_7;
    }
    v36 = GetProcAddress(ModuleHandleW, "CryptCATGetMemberInfo");
    if ( !v36 )
    {
      v7 = 589;
      goto LABEL_7;
    }
    v37 = GetProcAddress(ModuleHandleW, "CryptCATPutMemberInfo");
    if ( !v37 )
    {
      v7 = 593;
      goto LABEL_7;
    }
    v35 = GetProcAddress(ModuleHandleW, "CryptCATEnumerateAttr");
    if ( !v35 )
    {
      v7 = 597;
      goto LABEL_7;
    }
    if ( !GetProcAddress(ModuleHandleW, "CryptCATGetAttrInfo") )
    {
      v7 = 601;
      goto LABEL_7;
    }
    v38 = GetProcAddress(ModuleHandleW, "CryptCATPutAttrInfo");
    if ( !v38 )
    {
      v7 = 605;
      goto LABEL_7;
    }
    v11 = GetProcAddress(ModuleHandleW, "CryptCATGetCatAttrInfo");
    if ( !v11 )
    {
      v7 = 609;
      goto LABEL_7;
    }
    v12 = GetProcAddress(ModuleHandleW, "CryptCATPutCatAttrInfo");
    if ( !v12 )
    {
      v7 = 613;
      goto LABEL_7;
    }
    v13 = *((_BYTE *)this + 200);
    v14 = -1;
    v15 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD, __int64, int))ProcAddress)(
            a2,
            v13 != 0 ? 131074 : 65538,
            0,
            512,
            65537);
    if ( v15 == -1 )
    {
      v7 = 628;
      goto LABEL_7;
    }
    bIgnoreCase = 65537;
    v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))ProcAddress)(
            *((_QWORD *)this + 8),
            v13 != 0 ? 131076 : 65540,
            0,
            512);
    v18 = v16;
    if ( v16 == -1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x281,
                    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                    v17);
LABEL_32:
      ((void (__fastcall *)(__int64))v10)(v15);
      goto LABEL_69;
    }
    v19 = ((__int64 (__fastcall *)(__int64, const wchar_t *))v11)(v16, L"OSAttr");
    v21 = v19;
    if ( !v19 )
    {
      v22 = 652;
      goto LABEL_35;
    }
    if ( *(_DWORD *)(v19 + 16) == 268500993 )
    {
      if ( CompareStringOrdinal(*(LPCWCH *)(v19 + 24), -1, L"2:6.2", -1, 1) == 2 )
      {
        if ( !((__int64 (__fastcall *)(__int64, const wchar_t *))v11)(v15, L"OSAttr") )
        {
          if ( !((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD))v12)(
                  v15,
                  *(_QWORD *)(v21 + 8),
                  *(unsigned int *)(v21 + 16),
                  *(unsigned int *)(v21 + 20),
                  *(_QWORD *)(v21 + 24)) )
          {
            v22 = 669;
            goto LABEL_35;
          }
          if ( *((_QWORD *)this + 1)
            && !((__int64 (__fastcall *)(__int64, const wchar_t *))v11)(v15, L"PackageFullName") )
          {
            do
              ++v14;
            while ( *(_WORD *)(*((_QWORD *)this + 1) + 2 * v14) );
            if ( !((__int64 (__fastcall *)(__int64, const wchar_t *, __int64, _QWORD, _QWORD))v12)(
                    v15,
                    L"PackageFullName",
                    268500993,
                    (unsigned int)(2 * v14 + 2),
                    *((_QWORD *)this + 1)) )
            {
              v22 = 687;
              goto LABEL_35;
            }
          }
        }
        SetLastError(0);
        v24 = (__int64 (__fastcall *)(__int64, __int64))v42;
        for ( i = ((__int64 (__fastcall *)(__int64, _QWORD))v42)(v18, 0); i; i = v24(v18, i) )
        {
          if ( !((__int64 (__fastcall *)(__int64, _QWORD))v36)(v15, *(_QWORD *)(i + 8)) )
          {
            LODWORD(v34) = 64;
            v26 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, _DWORD, __int64, _QWORD))v37)(
                    v15,
                    *(_QWORD *)(i + 16),
                    *(_QWORD *)(i + 8),
                    i + 24,
                    *(_DWORD *)(i + 56),
                    v34,
                    *(_QWORD *)(i + 48));
            if ( !v26 )
            {
              v22 = 711;
              goto LABEL_35;
            }
            for ( j = 0; ; j = v29 )
            {
              v28 = ((__int64 (__fastcall *)(__int64, __int64, __int64))v35)(v18, i, j);
              v29 = v28;
              if ( !v28 )
                break;
              if ( !((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _DWORD, _QWORD))v38)(
                      v15,
                      v26,
                      *(_QWORD *)(v28 + 8),
                      *(unsigned int *)(v28 + 16),
                      *(_DWORD *)(v28 + 20),
                      *(_QWORD *)(v28 + 24)) )
              {
                v22 = 725;
                goto LABEL_35;
              }
            }
            v30 = GetLastError();
            if ( v30 && v30 != -2146885628 )
            {
              v22 = 728;
              goto LABEL_35;
            }
          }
        }
        v31 = GetLastError();
        if ( v31 && v31 != -2146885628 )
        {
          v22 = 732;
          goto LABEL_35;
        }
        if ( ((unsigned int (__fastcall *)(__int64))v39)(v15) )
        {
          ((void (__fastcall *)(__int64))v10)(v18);
          ((void (__fastcall *)(__int64))v10)(v15);
          LastError = 0;
          goto LABEL_69;
        }
        v22 = 733;
LABEL_35:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v22,
                      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                      v20);
        goto LABEL_36;
      }
      v23 = 656;
    }
    else
    {
      v23 = 654;
    }
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
LABEL_36:
    ((void (__fastcall *)(__int64))v10)(v18);
    goto LABEL_32;
  }
  Library = LoadLibraryExW(L"Wintrust.dll", 0, 0x800u);
  ModuleHandleW = Library;
  if ( Library )
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &v41,
      Library);
    goto LABEL_5;
  }
  v7 = 569;
LABEL_7:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v7,
                (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                v6);
LABEL_69:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v41);
  return LastError;
}

```

## disassembly

```asm
0x1801000e4  mov     rax, rsp
0x1801000e7  mov     [rax+8], rbx
0x1801000eb  push    rbp
0x1801000ec  push    rsi
0x1801000ed  push    rdi
0x1801000ee  push    r12
0x1801000f0  push    r13
0x1801000f2  push    r14
0x1801000f4  push    r15
0x1801000f6  sub     rsp, 80h
0x1801000fd  mov     r13, rcx
0x180100100  xor     r14d, r14d
0x180100103  lea     rcx, aWintrustDll_1; "wintrust.dll"
0x18010010a  mov     [rax+18h], r14
0x18010010e  mov     rsi, rdx
0x180100111  call    cs:__imp_GetModuleHandleW
0x180100118  nop     dword ptr [rax+rax+00h]
0x18010011d  mov     rbx, rax
0x180100120  test    rax, rax
0x180100123  jnz     short loc_18010015F
0x180100125  xor     edx, edx; hFile
0x180100127  lea     rcx, aWintrustDll_0; "Wintrust.dll"
0x18010012e  mov     r8d, 800h; dwFlags
0x180100134  call    cs:__imp_LoadLibraryExW
0x18010013b  nop     dword ptr [rax+rax+00h]
0x180100140  mov     rbx, rax
0x180100143  test    rax, rax
0x180100146  jnz     short loc_18010014F
0x180100148  mov     edx, 239h
0x18010014d  jmp     short loc_180100182
0x18010014f  mov     rdx, rax
0x180100152  lea     rcx, [rsp+0B8h+arg_10]
0x18010015a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18010015f  lea     rdx, aCryptcatopen; "CryptCATOpen"
0x180100166  mov     rcx, rbx; hModule
0x180100169  call    cs:__imp_GetProcAddress
0x180100170  nop     dword ptr [rax+rax+00h]
0x180100175  mov     rbp, rax
0x180100178  test    rax, rax
0x18010017b  jnz     short loc_18010019D
0x18010017d  mov     edx, 23Eh; void *
0x180100182  mov     rcx, [rsp+0B8h]; this
0x18010018a  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x180100191  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180100196  mov     ebx, eax
0x180100198  jmp     loc_1801006AB
0x18010019d  lea     rdx, aCryptcatclose; "CryptCATClose"
0x1801001a4  mov     rcx, rbx; hModule
0x1801001a7  call    cs:__imp_GetProcAddress
0x1801001ae  nop     dword ptr [rax+rax+00h]
0x1801001b3  mov     rdi, rax
0x1801001b6  test    rax, rax
0x1801001b9  jnz     short loc_1801001C2
0x1801001bb  mov     edx, 241h
0x1801001c0  jmp     short loc_180100182
0x1801001c2  lea     rdx, aCryptcatpersis; "CryptCATPersistStore"
0x1801001c9  mov     rcx, rbx; hModule
0x1801001cc  call    cs:__imp_GetProcAddress
0x1801001d3  nop     dword ptr [rax+rax+00h]
0x1801001d8  mov     [rsp+0B8h+var_58], rax
0x1801001dd  test    rax, rax
0x1801001e0  jnz     short loc_1801001E9
0x1801001e2  mov     edx, 245h
0x1801001e7  jmp     short loc_180100182
0x1801001e9  lea     rdx, aCryptcatenumer; "CryptCATEnumerateMember"
0x1801001f0  mov     rcx, rbx; hModule
0x1801001f3  call    cs:__imp_GetProcAddress
0x1801001fa  nop     dword ptr [rax+rax+00h]
0x1801001ff  mov     [rsp+0B8h+arg_18], rax
0x180100207  test    rax, rax
0x18010020a  jnz     short loc_180100216
0x18010020c  mov     edx, 249h
0x180100211  jmp     loc_180100182
0x180100216  lea     rdx, aCryptcatgetmem; "CryptCATGetMemberInfo"
0x18010021d  mov     rcx, rbx; hModule
0x180100220  call    cs:__imp_GetProcAddress
0x180100227  nop     dword ptr [rax+rax+00h]
0x18010022c  mov     [rsp+0B8h+var_70], rax
0x180100231  test    rax, rax
0x180100234  jnz     short loc_180100240
0x180100236  mov     edx, 24Dh
0x18010023b  jmp     loc_180100182
0x180100240  lea     rdx, aCryptcatputmem; "CryptCATPutMemberInfo"
0x180100247  mov     rcx, rbx; hModule
0x18010024a  call    cs:__imp_GetProcAddress
0x180100251  nop     dword ptr [rax+rax+00h]
0x180100256  mov     [rsp+0B8h+var_68], rax
0x18010025b  test    rax, rax
0x18010025e  jnz     short loc_18010026A
0x180100260  mov     edx, 251h
0x180100265  jmp     loc_180100182
0x18010026a  lea     rdx, aCryptcatenumer_0; "CryptCATEnumerateAttr"
0x180100271  mov     rcx, rbx; hModule
0x180100274  call    cs:__imp_GetProcAddress
0x18010027b  nop     dword ptr [rax+rax+00h]
0x180100280  mov     [rsp+0B8h+var_78], rax
0x180100285  test    rax, rax
0x180100288  jnz     short loc_180100294
0x18010028a  mov     edx, 255h
0x18010028f  jmp     loc_180100182
0x180100294  lea     rdx, aCryptcatgetatt; "CryptCATGetAttrInfo"
0x18010029b  mov     rcx, rbx; hModule
0x18010029e  call    cs:__imp_GetProcAddress
0x1801002a5  nop     dword ptr [rax+rax+00h]
0x1801002aa  test    rax, rax
0x1801002ad  jnz     short loc_1801002B9
0x1801002af  mov     edx, 259h
0x1801002b4  jmp     loc_180100182
0x1801002b9  lea     rdx, aCryptcatputatt; "CryptCATPutAttrInfo"
0x1801002c0  mov     rcx, rbx; hModule
0x1801002c3  call    cs:__imp_GetProcAddress
0x1801002ca  nop     dword ptr [rax+rax+00h]
0x1801002cf  mov     [rsp+0B8h+var_60], rax
0x1801002d4  test    rax, rax
0x1801002d7  jnz     short loc_1801002E3
0x1801002d9  mov     edx, 25Dh
0x1801002de  jmp     loc_180100182
0x1801002e3  lea     rdx, aCryptcatgetcat; "CryptCATGetCatAttrInfo"
0x1801002ea  mov     rcx, rbx; hModule
0x1801002ed  call    cs:__imp_GetProcAddress
0x1801002f4  nop     dword ptr [rax+rax+00h]
0x1801002f9  mov     r15, rax
0x1801002fc  test    rax, rax
0x1801002ff  jnz     short loc_18010030B
0x180100301  mov     edx, 261h
0x180100306  jmp     loc_180100182
0x18010030b  lea     rdx, aCryptcatputcat; "CryptCATPutCatAttrInfo"
0x180100312  mov     rcx, rbx; hModule
0x180100315  call    cs:__imp_GetProcAddress
0x18010031c  nop     dword ptr [rax+rax+00h]
0x180100321  mov     r12, rax
0x180100324  test    rax, rax
0x180100327  jnz     short loc_180100333
0x180100329  mov     edx, 265h
0x18010032e  jmp     loc_180100182
0x180100333  mov     r14b, [r13+0C8h]
0x18010033a  mov     r9d, 200h
0x180100340  mov     al, r14b
0x180100343  mov     [rsp+0B8h+bIgnoreCase], 10001h
0x18010034b  neg     al
0x18010034d  mov     rcx, rsi
0x180100350  mov     rax, rbp
0x180100353  sbb     edx, edx
0x180100355  xor     r8d, r8d
0x180100358  and     edx, 10000h
0x18010035e  add     edx, 10002h
0x180100364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100369  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18010036d  mov     rsi, rax
0x180100370  cmp     rax, rbx
0x180100373  jnz     short loc_18010037F
0x180100375  mov     edx, 274h
0x18010037a  jmp     loc_180100182
0x18010037f  mov     rcx, [r13+40h]
0x180100383  neg     r14b
0x180100386  mov     r9d, 200h
0x18010038c  mov     [rsp+0B8h+bIgnoreCase], 10001h; int
0x180100394  sbb     edx, edx
0x180100396  mov     rax, rbp
0x180100399  and     edx, 10000h
0x18010039f  xor     r8d, r8d
0x1801003a2  add     edx, 10004h
0x1801003a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801003ad  mov     rbp, rax
0x1801003b0  cmp     rax, rbx
0x1801003b3  jnz     short loc_1801003E0
0x1801003b5  mov     rcx, [rsp+0B8h]; this
0x1801003bd  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1801003c4  mov     edx, 281h; void *
0x1801003c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801003ce  mov     ebx, eax
0x1801003d0  mov     rcx, rsi
0x1801003d3  mov     rax, rdi
0x1801003d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801003db  jmp     loc_1801006AB
0x1801003e0  lea     rdx, aOsattr; "OSAttr"
0x1801003e7  mov     rcx, rbp
0x1801003ea  mov     rax, r15
0x1801003ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801003f2  mov     r14, rax
0x1801003f5  test    rax, rax
0x1801003f8  jnz     short loc_180100422
0x1801003fa  mov     edx, 28Ch; void *
0x1801003ff  mov     rcx, [rsp+0B8h]; this
0x180100407  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x18010040e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180100413  mov     ebx, eax
0x180100415  mov     rcx, rbp
0x180100418  mov     rax, rdi
0x18010041b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100420  jmp     short loc_1801003D0
0x180100422  cmp     dword ptr [rax+10h], 10010001h
0x180100429  jz      short loc_18010044E
0x18010042b  mov     edx, 28Eh; void *
0x180100430  mov     rcx, [rsp+0B8h]; this
0x180100438  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x18010043f  mov     ebx, 80070057h
0x180100444  mov     r9d, ebx; char *
0x180100447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010044c  jmp     short loc_180100415
0x18010044e  mov     rcx, [rax+18h]; lpString1
0x180100452  lea     r8, a262; "2:6.2"
0x180100459  mov     r9d, ebx; cchCount2
0x18010045c  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x180100464  mov     edx, ebx; cchCount1
0x180100466  call    cs:__imp_CompareStringOrdinal
0x18010046d  nop     dword ptr [rax+rax+00h]
0x180100472  cmp     eax, 2
0x180100475  jz      short loc_18010047E
0x180100477  mov     edx, 290h
0x18010047c  jmp     short loc_180100430
0x18010047e  lea     rdx, aOsattr; "OSAttr"
0x180100485  mov     rcx, rsi
0x180100488  mov     rax, r15
0x18010048b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100490  test    rax, rax
0x180100493  jnz     loc_18010052A
0x180100499  mov     rax, [r14+18h]
0x18010049d  mov     rcx, rsi
0x1801004a0  mov     r9d, [r14+14h]
0x1801004a4  mov     r8d, [r14+10h]
0x1801004a8  mov     rdx, [r14+8]
0x1801004ac  mov     qword ptr [rsp+0B8h+bIgnoreCase], rax
0x1801004b1  mov     rax, r12
0x1801004b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801004b9  xor     r14d, r14d
0x1801004bc  test    rax, rax
0x1801004bf  jnz     short loc_1801004CB
0x1801004c1  mov     edx, 29Dh
0x1801004c6  jmp     loc_1801003FF
0x1801004cb  cmp     [r13+8], r14
0x1801004cf  jz      short loc_18010052D
0x1801004d1  lea     rdx, aPackagefullnam; "PackageFullName"
0x1801004d8  mov     rcx, rsi
0x1801004db  mov     rax, r15
0x1801004de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801004e3  test    rax, rax
0x1801004e6  jnz     short loc_18010052D
0x1801004e8  mov     rax, [r13+8]
0x1801004ec  inc     rbx
0x1801004ef  cmp     [rax+rbx*2], r14w
0x1801004f4  jnz     short loc_1801004EC
0x1801004f6  mov     qword ptr [rsp+0B8h+bIgnoreCase], rax
0x1801004fb  lea     r9d, ds:2[rbx*2]
0x180100503  mov     rax, r12
0x180100506  lea     rdx, aPackagefullnam; "PackageFullName"
0x18010050d  mov     r8d, 10010001h
0x180100513  mov     rcx, rsi
0x180100516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010051b  test    rax, rax
0x18010051e  jnz     short loc_18010052D
0x180100520  mov     edx, 2AFh
0x180100525  jmp     loc_1801003FF
0x18010052a  xor     r14d, r14d
0x18010052d  xor     ecx, ecx; dwErrCode
0x18010052f  call    cs:__imp_SetLastError
0x180100536  nop     dword ptr [rax+rax+00h]
0x18010053b  mov     r12, [rsp+0B8h+arg_18]
0x180100543  xor     edx, edx
0x180100545  mov     rax, r12
0x180100548  mov     rcx, rbp
0x18010054b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100550  mov     rbx, rax
0x180100553  test    rax, rax
0x180100556  jz      loc_180100638
0x18010055c  mov     r13, [rsp+0B8h+var_78]
0x180100561  mov     rdx, [rbx+8]
0x180100565  mov     rcx, rsi
0x180100568  mov     rax, [rsp+0B8h+var_70]
0x18010056d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100572  test    rax, rax
0x180100575  jnz     loc_18010061E
0x18010057b  mov     rax, [rbx+30h]
0x18010057f  lea     r9, [rbx+18h]
0x180100583  mov     r8, [rbx+8]
0x180100587  mov     rcx, rsi
0x18010058a  mov     rdx, [rbx+10h]
0x18010058e  mov     [rsp+0B8h+var_88], rax
0x180100593  mov     eax, [rbx+38h]
0x180100596  mov     dword ptr [rsp+0B8h+var_90], 40h ; '@'
0x18010059e  mov     [rsp+0B8h+bIgnoreCase], eax
0x1801005a2  mov     rax, [rsp+0B8h+var_68]
0x1801005a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801005ac  mov     r15, rax
0x1801005af  test    rax, rax
0x1801005b2  jz      loc_18010066D
0x1801005b8  xor     r8d, r8d
0x1801005bb  jmp     short loc_1801005EE
0x1801005bd  mov     rcx, [r14+18h]
0x1801005c1  mov     rdx, r15
0x1801005c4  mov     r9d, [r14+10h]
0x1801005c8  mov     r8, [r14+8]
0x1801005cc  mov     rax, [rsp+0B8h+var_60]
0x1801005d1  mov     [rsp+0B8h+var_90], rcx
0x1801005d6  mov     ecx, [r14+14h]
0x1801005da  mov     [rsp+0B8h+bIgnoreCase], ecx
0x1801005de  mov     rcx, rsi
0x1801005e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801005e6  test    rax, rax
0x1801005e9  jz      short loc_180100659
  ... truncated ...
```
