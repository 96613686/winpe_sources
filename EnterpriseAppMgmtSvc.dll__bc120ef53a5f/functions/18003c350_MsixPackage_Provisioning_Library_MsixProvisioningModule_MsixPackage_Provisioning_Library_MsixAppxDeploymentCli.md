# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)

- ea: `0x18003c350`
- end: `0x18003c4d5`
- name: `?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ`
- size: `389`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180039a48`
- `0x180039b78`
- `0x180039d14`
- `0x18004560c`
- `0x180045730`
- `0x180045850`
- `0x18004922c`
- `0x180049664`
- `0x18004ba8c`
- `0x18004c710`

## callees

- `0x18000d3bc`
- `0x18000d3dc`
- `0x18001d160`
- `0x18003c350`
- `0x18003e50c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c413`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c413`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c445`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c46d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c445`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c46d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c434`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c453`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c453`

## string_xrefs

- `0x18003c3ca`: `AppxDeploymentClient.dll`
- `0x18003c3f5`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003c484`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003c4a3`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  int *v4; // rdi
  _QWORD *v5; // rbx
  _WORD *v6; // rdx
  __int64 v7; // r8
  int v8; // ebx
  HMODULE Library; // rsi
  HMODULE v10; // r14
  DWORD LastError; // ebx
  __int64 result; // rax
  int v13; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    v4 = (int *)(a1 + 1);
    if ( !a1[1] )
    {
      v5 = a1 + 3;
      if ( !a1[5] )
      {
        v6 = (_WORD *)a1[2];
        if ( *v6 )
        {
          v7 = -1;
          do
            ++v7;
          while ( v6[v7] );
        }
        std::wstring::assign(a1 + 3, v6);
        std::wstring::append(v5, (void *)L"\\");
        std::wstring::append(v5, L"AppxDeploymentClient.dll");
        if ( v5[3] >= 8u )
          v5 = (_QWORD *)*v5;
        if ( !v5 )
        {
          v8 = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
            (const char *)0x80070057LL,
            v13);
LABEL_19:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3E,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
            (const char *)(unsigned int)v8,
            v13);
          return (unsigned int)v8;
        }
        Library = LoadLibraryExW((LPCWSTR)v5, 0, 0);
        if ( v4 == &v13 )
        {
          if ( Library )
            FreeLibrary(Library);
        }
        else
        {
          v10 = *(HMODULE *)v4;
          if ( *(_QWORD *)v4 )
          {
            LastError = GetLastError();
            FreeLibrary(v10);
            SetLastError(LastError);
          }
          *(_QWORD *)v4 = Library;
        }
        if ( !*(_QWORD *)v4 )
        {
          v8 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x4B,
                 (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
                 a4);
          if ( v8 < 0 )
            goto LABEL_19;
        }
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x44,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x18003c350  mov     [rsp+arg_8], rbx
0x18003c355  mov     [rsp+arg_10], rsi
0x18003c35a  push    rdi
0x18003c35b  push    r14
0x18003c35d  push    r15
0x18003c35f  sub     rsp, 30h
0x18003c363  lea     rdi, [rcx+8]
0x18003c367  xor     r15d, r15d
0x18003c36a  cmp     [rdi], r15
0x18003c36d  jnz     loc_18003C4B8
0x18003c373  lea     rbx, [rcx+18h]
0x18003c377  cmp     [rbx+10h], r15
0x18003c37b  jnz     loc_18003C4B8
0x18003c381  mov     rdx, [rcx+10h]; Src
0x18003c385  cmp     [rdx], r15w
0x18003c389  jnz     short loc_18003C390
0x18003c38b  mov     r8d, r15d
0x18003c38e  jmp     short loc_18003C39E
0x18003c390  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003c394  inc     r8
0x18003c397  cmp     [rdx+r8*2], r15w
0x18003c39c  jnz     short loc_18003C394
0x18003c39e  mov     rcx, rbx; void *
0x18003c3a1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003c3a6  mov     r8, r15
0x18003c3a9  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18003c3b1  setnz   r8b
0x18003c3b5  lea     rdx, pszSrc; "\\"
0x18003c3bc  mov     rcx, rbx; Src
0x18003c3bf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003c3c4  mov     r8d, 18h
0x18003c3ca  lea     rdx, aAppxdeployment; "AppxDeploymentClient.dll"
0x18003c3d1  mov     rcx, rbx; Src
0x18003c3d4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003c3d9  cmp     qword ptr [rbx+18h], 8
0x18003c3de  jb      short loc_18003C3E3
0x18003c3e0  mov     rbx, [rbx]
0x18003c3e3  test    rbx, rbx
0x18003c3e6  jnz     short loc_18003C40B
0x18003c3e8  mov     rcx, [rsp+48h]; this
0x18003c3ed  mov     ebx, 80070057h
0x18003c3f2  mov     r9d, ebx; char *
0x18003c3f5  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c3fc  mov     edx, 48h ; 'H'; void *
0x18003c401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c406  jmp     loc_18003C49B
0x18003c40b  xor     r8d, r8d; dwFlags
0x18003c40e  xor     edx, edx; hFile
0x18003c410  mov     rcx, rbx; lpLibFileName
0x18003c413  call    cs:__imp_LoadLibraryExW
0x18003c41a  nop     dword ptr [rax+rax+00h]
0x18003c41f  mov     rsi, rax
0x18003c422  lea     rax, [rsp+48h+var_28]
0x18003c427  cmp     rdi, rax
0x18003c42a  jz      short loc_18003C465
0x18003c42c  mov     r14, [rdi]
0x18003c42f  test    r14, r14
0x18003c432  jz      short loc_18003C460
0x18003c434  call    cs:__imp_GetLastError
0x18003c43b  nop     dword ptr [rax+rax+00h]
0x18003c440  mov     ebx, eax
0x18003c442  mov     rcx, r14; hLibModule
0x18003c445  call    cs:__imp_FreeLibrary
0x18003c44c  nop     dword ptr [rax+rax+00h]
0x18003c451  mov     ecx, ebx; dwErrCode
0x18003c453  call    cs:__imp_SetLastError
0x18003c45a  nop     dword ptr [rax+rax+00h]
0x18003c45f  nop
0x18003c460  mov     [rdi], rsi
0x18003c463  jmp     short loc_18003C47A
0x18003c465  test    rsi, rsi
0x18003c468  jz      short loc_18003C47A
0x18003c46a  mov     rcx, rsi; hLibModule
0x18003c46d  call    cs:__imp_FreeLibrary
0x18003c474  nop     dword ptr [rax+rax+00h]
0x18003c479  nop
0x18003c47a  cmp     [rdi], r15
0x18003c47d  jnz     short loc_18003C4B8
0x18003c47f  mov     rcx, [rsp+48h]; this
0x18003c484  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c48b  mov     edx, 4Bh ; 'K'; void *
0x18003c490  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c495  mov     ebx, eax
0x18003c497  test    eax, eax
0x18003c499  jns     short loc_18003C4B8
0x18003c49b  mov     rcx, [rsp+48h]; this
0x18003c4a0  mov     r9d, ebx; char *
0x18003c4a3  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003c4aa  mov     edx, 3Eh ; '>'; void *
0x18003c4af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c4b4  mov     eax, ebx
0x18003c4b6  jmp     short loc_18003C4C0
0x18003c4b8  xor     eax, eax
0x18003c4ba  jmp     short loc_18003C4C0
0x18003c4bc  mov     eax, [rsp+48h+arg_0]
0x18003c4c0  mov     rbx, [rsp+48h+arg_8]
0x18003c4c5  mov     rsi, [rsp+48h+arg_10]
0x18003c4ca  add     rsp, 30h
0x18003c4ce  pop     r15
0x18003c4d0  pop     r14
0x18003c4d2  pop     rdi
0x18003c4d3  retn
```
