# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxPackaging>::LoadModule(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &)

- ea: `0x18003c5b8`
- end: `0x18003c688`
- name: `?LoadModule@?$MsixProvisioningModule@VMsixAppxPackaging@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `208`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800344e4`
- `0x18003c4dc`
- `0x18003e780`

## callees

- `0x18000d3bc`
- `0x18000d3dc`
- `0x18003c5b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c5f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c5f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c629`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c651`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c629`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c618`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c637`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c637`

## string_xrefs

- `0x18003c5d9`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003c669`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxPackaging>::LoadModule(
        __int64 a1,
        const WCHAR *a2,
        int *a3)
{
  HMODULE Library; // rsi
  const char *v6; // r9
  HMODULE v7; // rbp
  DWORD LastError; // ebx
  int v9; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 )
  {
    Library = LoadLibraryExW(a2, 0, 0);
    if ( a3 == &v9 )
    {
      if ( Library )
        FreeLibrary(Library);
    }
    else
    {
      v7 = *(HMODULE *)a3;
      if ( *(_QWORD *)a3 )
      {
        LastError = GetLastError();
        FreeLibrary(v7);
        SetLastError(LastError);
      }
      *(_QWORD *)a3 = Library;
    }
    if ( *(_QWORD *)a3 )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x4B,
               (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
               v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)0x80070057LL,
      v9);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18003c5b8  push    rbx
0x18003c5ba  push    rbp
0x18003c5bb  push    rsi
0x18003c5bc  push    rdi
0x18003c5bd  sub     rsp, 38h
0x18003c5c1  mov     rdi, r8
0x18003c5c4  mov     rax, rdx
0x18003c5c7  test    rdx, rdx
0x18003c5ca  jnz     short loc_18003C5EF
0x18003c5cc  mov     rcx, [rsp+58h]; this
0x18003c5d1  mov     ebx, 80070057h
0x18003c5d6  mov     r9d, ebx; char *
0x18003c5d9  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c5e0  lea     edx, [rax+48h]; void *
0x18003c5e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c5e8  mov     eax, ebx
0x18003c5ea  jmp     loc_18003C67E
0x18003c5ef  xor     r8d, r8d; dwFlags
0x18003c5f2  xor     edx, edx; hFile
0x18003c5f4  mov     rcx, rax; lpLibFileName
0x18003c5f7  call    cs:__imp_LoadLibraryExW
0x18003c5fe  nop     dword ptr [rax+rax+00h]
0x18003c603  mov     rsi, rax
0x18003c606  lea     rax, [rsp+58h+var_38]
0x18003c60b  cmp     rdi, rax
0x18003c60e  jz      short loc_18003C649
0x18003c610  mov     rbp, [rdi]
0x18003c613  test    rbp, rbp
0x18003c616  jz      short loc_18003C644
0x18003c618  call    cs:__imp_GetLastError
0x18003c61f  nop     dword ptr [rax+rax+00h]
0x18003c624  mov     ebx, eax
0x18003c626  mov     rcx, rbp; hLibModule
0x18003c629  call    cs:__imp_FreeLibrary
0x18003c630  nop     dword ptr [rax+rax+00h]
0x18003c635  mov     ecx, ebx; dwErrCode
0x18003c637  call    cs:__imp_SetLastError
0x18003c63e  nop     dword ptr [rax+rax+00h]
0x18003c643  nop
0x18003c644  mov     [rdi], rsi
0x18003c647  jmp     short loc_18003C65E
0x18003c649  test    rsi, rsi
0x18003c64c  jz      short loc_18003C65E
0x18003c64e  mov     rcx, rsi; hLibModule
0x18003c651  call    cs:__imp_FreeLibrary
0x18003c658  nop     dword ptr [rax+rax+00h]
0x18003c65d  nop
0x18003c65e  cmp     qword ptr [rdi], 0
0x18003c662  jnz     short loc_18003C67C
0x18003c664  mov     rcx, [rsp+58h]; this
0x18003c669  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c670  mov     edx, 4Bh ; 'K'; void *
0x18003c675  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c67a  jmp     short loc_18003C67E
0x18003c67c  xor     eax, eax
0x18003c67e  add     rsp, 38h
0x18003c682  pop     rdi
0x18003c683  pop     rsi
0x18003c684  pop     rbp
0x18003c685  pop     rbx
0x18003c686  retn
```
