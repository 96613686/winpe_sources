# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixApplicabilityEngine>::LoadDynamic(void)

- ea: `0x18003f240`
- end: `0x18003f3a4`
- name: `?LoadDynamic@?$MsixProvisioningModule@VMsixApplicabilityEngine@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003c414`
- `0x18003c534`
- `0x180055f7c`
- `0x1800560f8`

## callees

- `0x18000cfc8`
- `0x18000cfe8`
- `0x18001bf0c`
- `0x18003ae3c`
- `0x18003f240`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003f300`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003f300`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003f326`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003f342`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003f326`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003f342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f31b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f32e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f32e`

## string_xrefs

- `0x18003f2e5`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003f353`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003f372`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003f2ba`: `AppxApplicabilityEngine.dll`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixApplicabilityEngine>::LoadDynamic(
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
      std::wstring::append(v2, (char *)L"AppxApplicabilityEngine.dll", 0x1Bu);
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
0x18003f240  mov     [rsp+arg_8], rbx
0x18003f245  mov     [rsp+arg_10], rsi
0x18003f24a  push    rdi
0x18003f24b  push    r14
0x18003f24d  push    r15
0x18003f24f  sub     rsp, 30h
0x18003f253  lea     rdi, [rcx+8]
0x18003f257  xor     r15d, r15d
0x18003f25a  cmp     [rdi], r15
0x18003f25d  jnz     loc_18003F387
0x18003f263  lea     rbx, [rcx+18h]
0x18003f267  cmp     [rbx+10h], r15
0x18003f26b  jnz     loc_18003F387
0x18003f271  mov     rdx, [rcx+10h]; Src
0x18003f275  cmp     [rdx], r15w
0x18003f279  jnz     short loc_18003F280
0x18003f27b  mov     r8d, r15d
0x18003f27e  jmp     short loc_18003F28E
0x18003f280  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f284  inc     r8
0x18003f287  cmp     [rdx+r8*2], r15w
0x18003f28c  jnz     short loc_18003F284
0x18003f28e  mov     rcx, rbx; void *
0x18003f291  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003f296  mov     r8, r15
0x18003f299  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18003f2a1  setnz   r8b
0x18003f2a5  lea     rdx, pszSrc; "\\"
0x18003f2ac  mov     rcx, rbx; Src
0x18003f2af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003f2b4  mov     r8d, 1Bh
0x18003f2ba  lea     rdx, aAppxapplicabil; "AppxApplicabilityEngine.dll"
0x18003f2c1  mov     rcx, rbx; Src
0x18003f2c4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003f2c9  cmp     qword ptr [rbx+18h], 8
0x18003f2ce  jb      short loc_18003F2D3
0x18003f2d0  mov     rbx, [rbx]
0x18003f2d3  test    rbx, rbx
0x18003f2d6  jnz     short loc_18003F2F8
0x18003f2d8  mov     rcx, [rsp+48h]; this
0x18003f2dd  mov     ebx, 80070057h
0x18003f2e2  mov     r9d, ebx; char *
0x18003f2e5  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f2ec  mov     edx, 48h ; 'H'; void *
0x18003f2f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f2f6  jmp     short loc_18003F36A
0x18003f2f8  xor     r8d, r8d; dwFlags
0x18003f2fb  xor     edx, edx; hFile
0x18003f2fd  mov     rcx, rbx; lpLibFileName
0x18003f300  call    cs:__imp_LoadLibraryExW
0x18003f306  mov     rsi, rax
0x18003f309  lea     rax, [rsp+48h+var_28]
0x18003f30e  cmp     rdi, rax
0x18003f311  jz      short loc_18003F33A
0x18003f313  mov     r14, [rdi]
0x18003f316  test    r14, r14
0x18003f319  jz      short loc_18003F335
0x18003f31b  call    cs:__imp_GetLastError
0x18003f321  mov     ebx, eax
0x18003f323  mov     rcx, r14; hLibModule
0x18003f326  call    cs:__imp_FreeLibrary
0x18003f32c  mov     ecx, ebx; dwErrCode
0x18003f32e  call    cs:__imp_SetLastError
0x18003f334  nop
0x18003f335  mov     [rdi], rsi
0x18003f338  jmp     short loc_18003F349
0x18003f33a  test    rsi, rsi
0x18003f33d  jz      short loc_18003F349
0x18003f33f  mov     rcx, rsi; hLibModule
0x18003f342  call    cs:__imp_FreeLibrary
0x18003f348  nop
0x18003f349  cmp     [rdi], r15
0x18003f34c  jnz     short loc_18003F387
0x18003f34e  mov     rcx, [rsp+48h]; this
0x18003f353  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f35a  mov     edx, 4Bh ; 'K'; void *
0x18003f35f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f364  mov     ebx, eax
0x18003f366  test    eax, eax
0x18003f368  jns     short loc_18003F387
0x18003f36a  mov     rcx, [rsp+48h]; this
0x18003f36f  mov     r9d, ebx; char *
0x18003f372  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f379  mov     edx, 3Eh ; '>'; void *
0x18003f37e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f383  mov     eax, ebx
0x18003f385  jmp     short loc_18003F38F
0x18003f387  xor     eax, eax
0x18003f389  jmp     short loc_18003F38F
0x18003f38b  mov     eax, [rsp+48h+arg_0]
0x18003f38f  mov     rbx, [rsp+48h+arg_8]
0x18003f394  mov     rsi, [rsp+48h+arg_10]
0x18003f399  add     rsp, 30h
0x18003f39d  pop     r15
0x18003f39f  pop     r14
0x18003f3a1  pop     rdi
0x18003f3a2  retn
```
