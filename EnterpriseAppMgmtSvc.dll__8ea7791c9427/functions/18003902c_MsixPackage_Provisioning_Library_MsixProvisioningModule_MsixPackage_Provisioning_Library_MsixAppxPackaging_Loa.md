# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxPackaging>::LoadModule(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &)

- ea: `0x18003902c`
- end: `0x1800390da`
- name: `?LoadModule@?$MsixProvisioningModule@VMsixAppxPackaging@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18003167c`
- `0x180038f50`
- `0x18003b0b0`

## callees

- `0x18000cfc8`
- `0x18000cfe8`
- `0x18003902c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039068`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039068`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003908e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800390aa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003908e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800390aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039083`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039096`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039096`

## string_xrefs

- `0x18003904d`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x1800390bc`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`

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
0x18003902c  push    rbx
0x18003902e  push    rbp
0x18003902f  push    rsi
0x180039030  push    rdi
0x180039031  sub     rsp, 38h
0x180039035  mov     rdi, r8
0x180039038  mov     rax, rdx
0x18003903b  test    rdx, rdx
0x18003903e  jnz     short loc_180039060
0x180039040  mov     rcx, [rsp+58h]; this
0x180039045  mov     ebx, 80070057h
0x18003904a  mov     r9d, ebx; char *
0x18003904d  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180039054  lea     edx, [rax+48h]; void *
0x180039057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003905c  mov     eax, ebx
0x18003905e  jmp     short loc_1800390D1
0x180039060  xor     r8d, r8d; dwFlags
0x180039063  xor     edx, edx; hFile
0x180039065  mov     rcx, rax; lpLibFileName
0x180039068  call    cs:__imp_LoadLibraryExW
0x18003906e  mov     rsi, rax
0x180039071  lea     rax, [rsp+58h+var_38]
0x180039076  cmp     rdi, rax
0x180039079  jz      short loc_1800390A2
0x18003907b  mov     rbp, [rdi]
0x18003907e  test    rbp, rbp
0x180039081  jz      short loc_18003909D
0x180039083  call    cs:__imp_GetLastError
0x180039089  mov     ebx, eax
0x18003908b  mov     rcx, rbp; hLibModule
0x18003908e  call    cs:__imp_FreeLibrary
0x180039094  mov     ecx, ebx; dwErrCode
0x180039096  call    cs:__imp_SetLastError
0x18003909c  nop
0x18003909d  mov     [rdi], rsi
0x1800390a0  jmp     short loc_1800390B1
0x1800390a2  test    rsi, rsi
0x1800390a5  jz      short loc_1800390B1
0x1800390a7  mov     rcx, rsi; hLibModule
0x1800390aa  call    cs:__imp_FreeLibrary
0x1800390b0  nop
0x1800390b1  cmp     qword ptr [rdi], 0
0x1800390b5  jnz     short loc_1800390CF
0x1800390b7  mov     rcx, [rsp+58h]; this
0x1800390bc  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800390c3  mov     edx, 4Bh ; 'K'; void *
0x1800390c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800390cd  jmp     short loc_1800390D1
0x1800390cf  xor     eax, eax
0x1800390d1  add     rsp, 38h
0x1800390d5  pop     rdi
0x1800390d6  pop     rsi
0x1800390d7  pop     rbp
0x1800390d8  pop     rbx
0x1800390d9  retn
```
