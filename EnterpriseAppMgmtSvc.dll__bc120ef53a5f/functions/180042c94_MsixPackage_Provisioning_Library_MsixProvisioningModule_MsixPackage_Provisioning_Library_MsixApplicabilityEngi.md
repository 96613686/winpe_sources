# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixApplicabilityEngine>::LoadDynamic(void)

- ea: `0x180042c94`
- end: `0x180042e19`
- name: `?LoadDynamic@?$MsixProvisioningModule@VMsixApplicabilityEngine@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ`
- size: `389`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003fbb8`
- `0x18003fcf0`
- `0x18005a578`
- `0x18005a710`

## callees

- `0x18000d3bc`
- `0x18000d3dc`
- `0x18001d160`
- `0x18003e50c`
- `0x180042c94`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042d57`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042d57`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042d89`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042db1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042d89`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042d97`

## string_xrefs

- `0x180042d39`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180042dc8`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180042de7`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180042d0e`: `AppxApplicabilityEngine.dll`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixApplicabilityEngine>::LoadDynamic(
        _QWORD *a1)
{
  int *v1; // rdi
  _QWORD *v2; // rbx
  _WORD *v3; // rdx
  __int64 v4; // r8
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
    v2 = a1 + 3;
    if ( !a1[5] )
    {
      v3 = (_WORD *)a1[2];
      if ( *v3 )
      {
        v4 = -1;
        do
          ++v4;
        while ( v3[v4] );
      }
      std::wstring::assign(a1 + 3, v3);
      std::wstring::append(v2, (void *)L"\\");
      std::wstring::append(v2, L"AppxApplicabilityEngine.dll");
      if ( v2[3] >= 8u )
        v2 = (_QWORD *)*v2;
      if ( !v2 )
      {
        v5 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)0x80070057LL,
          v11);
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)(unsigned int)v5,
          v11);
        return (unsigned int)v5;
      }
      Library = LoadLibraryExW((LPCWSTR)v2, 0, 0);
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
          goto LABEL_18;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180042c94  mov     [rsp+arg_8], rbx
0x180042c99  mov     [rsp+arg_10], rsi
0x180042c9e  push    rdi
0x180042c9f  push    r14
0x180042ca1  push    r15
0x180042ca3  sub     rsp, 30h
0x180042ca7  lea     rdi, [rcx+8]
0x180042cab  xor     r15d, r15d
0x180042cae  cmp     [rdi], r15
0x180042cb1  jnz     loc_180042DFC
0x180042cb7  lea     rbx, [rcx+18h]
0x180042cbb  cmp     [rbx+10h], r15
0x180042cbf  jnz     loc_180042DFC
0x180042cc5  mov     rdx, [rcx+10h]; Src
0x180042cc9  cmp     [rdx], r15w
0x180042ccd  jnz     short loc_180042CD4
0x180042ccf  mov     r8d, r15d
0x180042cd2  jmp     short loc_180042CE2
0x180042cd4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042cd8  inc     r8
0x180042cdb  cmp     [rdx+r8*2], r15w
0x180042ce0  jnz     short loc_180042CD8
0x180042ce2  mov     rcx, rbx; void *
0x180042ce5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180042cea  mov     r8, r15
0x180042ced  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180042cf5  setnz   r8b
0x180042cf9  lea     rdx, pszSrc; "\\"
0x180042d00  mov     rcx, rbx; Src
0x180042d03  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180042d08  mov     r8d, 1Bh
0x180042d0e  lea     rdx, aAppxapplicabil; "AppxApplicabilityEngine.dll"
0x180042d15  mov     rcx, rbx; Src
0x180042d18  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180042d1d  cmp     qword ptr [rbx+18h], 8
0x180042d22  jb      short loc_180042D27
0x180042d24  mov     rbx, [rbx]
0x180042d27  test    rbx, rbx
0x180042d2a  jnz     short loc_180042D4F
0x180042d2c  mov     rcx, [rsp+48h]; this
0x180042d31  mov     ebx, 80070057h
0x180042d36  mov     r9d, ebx; char *
0x180042d39  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180042d40  mov     edx, 48h ; 'H'; void *
0x180042d45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042d4a  jmp     loc_180042DDF
0x180042d4f  xor     r8d, r8d; dwFlags
0x180042d52  xor     edx, edx; hFile
0x180042d54  mov     rcx, rbx; lpLibFileName
0x180042d57  call    cs:__imp_LoadLibraryExW
0x180042d5e  nop     dword ptr [rax+rax+00h]
0x180042d63  mov     rsi, rax
0x180042d66  lea     rax, [rsp+48h+var_28]
0x180042d6b  cmp     rdi, rax
0x180042d6e  jz      short loc_180042DA9
0x180042d70  mov     r14, [rdi]
0x180042d73  test    r14, r14
0x180042d76  jz      short loc_180042DA4
0x180042d78  call    cs:__imp_GetLastError
0x180042d7f  nop     dword ptr [rax+rax+00h]
0x180042d84  mov     ebx, eax
0x180042d86  mov     rcx, r14; hLibModule
0x180042d89  call    cs:__imp_FreeLibrary
0x180042d90  nop     dword ptr [rax+rax+00h]
0x180042d95  mov     ecx, ebx; dwErrCode
0x180042d97  call    cs:__imp_SetLastError
0x180042d9e  nop     dword ptr [rax+rax+00h]
0x180042da3  nop
0x180042da4  mov     [rdi], rsi
0x180042da7  jmp     short loc_180042DBE
0x180042da9  test    rsi, rsi
0x180042dac  jz      short loc_180042DBE
0x180042dae  mov     rcx, rsi; hLibModule
0x180042db1  call    cs:__imp_FreeLibrary
0x180042db8  nop     dword ptr [rax+rax+00h]
0x180042dbd  nop
0x180042dbe  cmp     [rdi], r15
0x180042dc1  jnz     short loc_180042DFC
0x180042dc3  mov     rcx, [rsp+48h]; this
0x180042dc8  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180042dcf  mov     edx, 4Bh ; 'K'; void *
0x180042dd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042dd9  mov     ebx, eax
0x180042ddb  test    eax, eax
0x180042ddd  jns     short loc_180042DFC
0x180042ddf  mov     rcx, [rsp+48h]; this
0x180042de4  mov     r9d, ebx; char *
0x180042de7  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180042dee  mov     edx, 3Eh ; '>'; void *
0x180042df3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042df8  mov     eax, ebx
0x180042dfa  jmp     short loc_180042E04
0x180042dfc  xor     eax, eax
0x180042dfe  jmp     short loc_180042E04
0x180042e00  mov     eax, [rsp+48h+arg_0]
0x180042e04  mov     rbx, [rsp+48h+arg_8]
0x180042e09  mov     rsi, [rsp+48h+arg_10]
0x180042e0e  add     rsp, 30h
0x180042e12  pop     r15
0x180042e14  pop     r14
0x180042e16  pop     rdi
0x180042e17  retn
```
