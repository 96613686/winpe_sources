# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::COemLicense>::LoadDynamic(void)

- ea: `0x18004838c`
- end: `0x1800484f0`
- name: `?LoadDynamic@?$MsixProvisioningModule@VCOemLicense@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047234`
- `0x180049f94`

## callees

- `0x18000cfc8`
- `0x18000cfe8`
- `0x18001bf0c`
- `0x18003ae3c`
- `0x18004838c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004844c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004844c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180048472`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004848e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180048472`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004848e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048467`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004847a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004847a`

## string_xrefs

- `0x180048431`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004849f`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x1800484be`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180048406`: `OemLicense.dll`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::COemLicense>::LoadDynamic(
        _QWORD *a1)
{
  int *v1; // rdi
  WCHAR *v2; // rbx
  char *v3; // rdx
  unsigned __int64 v4; // r8
  int v5; // ebx
  HMODULE Library; // rsi
  const char *v7; // r9
  HMODULE v8; // r14
  DWORD LastError; // ebx
  int v11; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = (int *)(a1 + 1);
  if ( !a1[1] )
  {
    v2 = (WCHAR *)(a1 + 3);
    if ( !a1[5] )
    {
      v3 = (char *)a1[2];
      if ( *(_WORD *)v3 )
      {
        v4 = -1;
        do
          ++v4;
        while ( *(_WORD *)&v3[2 * v4] );
      }
      else
      {
        v4 = 0;
      }
      std::wstring::assign(a1 + 3, v3, v4);
      std::wstring::append(v2, (char *)L"\\", pszSrc[0] != 0);
      std::wstring::append(v2, (char *)L"OemLicense.dll", 0xEu);
      if ( *((_QWORD *)v2 + 3) >= 8u )
        v2 = *(WCHAR **)v2;
      if ( !v2 )
      {
        v5 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)0x80070057LL,
          v11);
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)(unsigned int)v5,
          v11);
        return (unsigned int)v5;
      }
      Library = LoadLibraryExW(v2, 0, 0);
      if ( v1 == &v11 )
      {
        if ( Library )
          FreeLibrary(Library);
      }
      else
      {
        v8 = *(HMODULE *)v1;
        if ( *(_QWORD *)v1 )
        {
          LastError = GetLastError();
          FreeLibrary(v8);
          SetLastError(LastError);
        }
        *(_QWORD *)v1 = Library;
      }
      if ( !*(_QWORD *)v1 )
      {
        v5 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x4B,
               (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
               v7);
        if ( v5 < 0 )
          goto LABEL_19;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004838c  mov     [rsp+arg_8], rbx
0x180048391  mov     [rsp+arg_10], rsi
0x180048396  push    rdi
0x180048397  push    r14
0x180048399  push    r15
0x18004839b  sub     rsp, 30h
0x18004839f  lea     rdi, [rcx+8]
0x1800483a3  xor     r15d, r15d
0x1800483a6  cmp     [rdi], r15
0x1800483a9  jnz     loc_1800484D3
0x1800483af  lea     rbx, [rcx+18h]
0x1800483b3  cmp     [rbx+10h], r15
0x1800483b7  jnz     loc_1800484D3
0x1800483bd  mov     rdx, [rcx+10h]; Src
0x1800483c1  cmp     [rdx], r15w
0x1800483c5  jnz     short loc_1800483CC
0x1800483c7  mov     r8d, r15d
0x1800483ca  jmp     short loc_1800483DA
0x1800483cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800483d0  inc     r8
0x1800483d3  cmp     [rdx+r8*2], r15w
0x1800483d8  jnz     short loc_1800483D0
0x1800483da  mov     rcx, rbx; void *
0x1800483dd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800483e2  mov     r8, r15
0x1800483e5  cmp     word ptr cs:pszSrc, r15w; "\\"
0x1800483ed  setnz   r8b
0x1800483f1  lea     rdx, pszSrc; "\\"
0x1800483f8  mov     rcx, rbx; Src
0x1800483fb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180048400  mov     r8d, 0Eh
0x180048406  lea     rdx, aOemlicenseDll; "OemLicense.dll"
0x18004840d  mov     rcx, rbx; Src
0x180048410  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180048415  cmp     qword ptr [rbx+18h], 8
0x18004841a  jb      short loc_18004841F
0x18004841c  mov     rbx, [rbx]
0x18004841f  test    rbx, rbx
0x180048422  jnz     short loc_180048444
0x180048424  mov     rcx, [rsp+48h]; this
0x180048429  mov     ebx, 80070057h
0x18004842e  mov     r9d, ebx; char *
0x180048431  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048438  mov     edx, 48h ; 'H'; void *
0x18004843d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048442  jmp     short loc_1800484B6
0x180048444  xor     r8d, r8d; dwFlags
0x180048447  xor     edx, edx; hFile
0x180048449  mov     rcx, rbx; lpLibFileName
0x18004844c  call    cs:__imp_LoadLibraryExW
0x180048452  mov     rsi, rax
0x180048455  lea     rax, [rsp+48h+var_28]
0x18004845a  cmp     rdi, rax
0x18004845d  jz      short loc_180048486
0x18004845f  mov     r14, [rdi]
0x180048462  test    r14, r14
0x180048465  jz      short loc_180048481
0x180048467  call    cs:__imp_GetLastError
0x18004846d  mov     ebx, eax
0x18004846f  mov     rcx, r14; hLibModule
0x180048472  call    cs:__imp_FreeLibrary
0x180048478  mov     ecx, ebx; dwErrCode
0x18004847a  call    cs:__imp_SetLastError
0x180048480  nop
0x180048481  mov     [rdi], rsi
0x180048484  jmp     short loc_180048495
0x180048486  test    rsi, rsi
0x180048489  jz      short loc_180048495
0x18004848b  mov     rcx, rsi; hLibModule
0x18004848e  call    cs:__imp_FreeLibrary
0x180048494  nop
0x180048495  cmp     [rdi], r15
0x180048498  jnz     short loc_1800484D3
0x18004849a  mov     rcx, [rsp+48h]; this
0x18004849f  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800484a6  mov     edx, 4Bh ; 'K'; void *
0x1800484ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800484b0  mov     ebx, eax
0x1800484b2  test    eax, eax
0x1800484b4  jns     short loc_1800484D3
0x1800484b6  mov     rcx, [rsp+48h]; this
0x1800484bb  mov     r9d, ebx; char *
0x1800484be  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800484c5  mov     edx, 3Eh ; '>'; void *
0x1800484ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800484cf  mov     eax, ebx
0x1800484d1  jmp     short loc_1800484DB
0x1800484d3  xor     eax, eax
0x1800484d5  jmp     short loc_1800484DB
0x1800484d7  mov     eax, [rsp+48h+arg_0]
0x1800484db  mov     rbx, [rsp+48h+arg_8]
0x1800484e0  mov     rsi, [rsp+48h+arg_10]
0x1800484e5  add     rsp, 30h
0x1800484e9  pop     r15
0x1800484eb  pop     r14
0x1800484ed  pop     rdi
0x1800484ee  retn
```
