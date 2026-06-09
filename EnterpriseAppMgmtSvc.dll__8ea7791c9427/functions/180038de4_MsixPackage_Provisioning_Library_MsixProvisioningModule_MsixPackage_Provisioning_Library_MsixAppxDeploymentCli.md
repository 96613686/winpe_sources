# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxDeploymentClient>::LoadDynamic(void)

- ea: `0x180038de4`
- end: `0x180038f48`
- name: `?LoadDynamic@?$MsixProvisioningModule@VMsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800366d4`
- `0x1800367ec`
- `0x180036974`
- `0x180041940`
- `0x180041a50`
- `0x180041b58`
- `0x1800452e8`
- `0x1800456e4`
- `0x180047a30`
- `0x18004865c`

## callees

- `0x18000cfc8`
- `0x18000cfe8`
- `0x18001bf0c`
- `0x180038de4`
- `0x18003ae3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038ea4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038ea4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038eca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038ee6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038eca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180038ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ebf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038ed2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038ed2`

## string_xrefs

- `0x180038e5e`: `AppxDeploymentClient.dll`
- `0x180038e89`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180038ef7`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180038f16`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`

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
  WCHAR *v5; // rbx
  char *v6; // rdx
  unsigned __int64 v7; // r8
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
      v5 = (WCHAR *)(a1 + 3);
      if ( !a1[5] )
      {
        v6 = (char *)a1[2];
        if ( *(_WORD *)v6 )
        {
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)&v6[2 * v7] );
        }
        else
        {
          v7 = 0;
        }
        std::wstring::assign(a1 + 3, v6, v7);
        std::wstring::append(v5, (char *)L"\\", pszSrc[0] != 0);
        std::wstring::append(v5, (char *)L"AppxDeploymentClient.dll", 0x18u);
        if ( *((_QWORD *)v5 + 3) >= 8u )
          v5 = *(WCHAR **)v5;
        if ( !v5 )
        {
          v8 = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
            (const char *)0x80070057LL,
            v13);
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3E,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
            (const char *)(unsigned int)v8,
            v13);
          return (unsigned int)v8;
        }
        Library = LoadLibraryExW(v5, 0, 0);
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
            goto LABEL_20;
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
0x180038de4  mov     [rsp+arg_8], rbx
0x180038de9  mov     [rsp+arg_10], rsi
0x180038dee  push    rdi
0x180038def  push    r14
0x180038df1  push    r15
0x180038df3  sub     rsp, 30h
0x180038df7  lea     rdi, [rcx+8]
0x180038dfb  xor     r15d, r15d
0x180038dfe  cmp     [rdi], r15
0x180038e01  jnz     loc_180038F2B
0x180038e07  lea     rbx, [rcx+18h]
0x180038e0b  cmp     [rbx+10h], r15
0x180038e0f  jnz     loc_180038F2B
0x180038e15  mov     rdx, [rcx+10h]; Src
0x180038e19  cmp     [rdx], r15w
0x180038e1d  jnz     short loc_180038E24
0x180038e1f  mov     r8d, r15d
0x180038e22  jmp     short loc_180038E32
0x180038e24  or      r8, 0FFFFFFFFFFFFFFFFh
0x180038e28  inc     r8
0x180038e2b  cmp     [rdx+r8*2], r15w
0x180038e30  jnz     short loc_180038E28
0x180038e32  mov     rcx, rbx; void *
0x180038e35  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180038e3a  mov     r8, r15
0x180038e3d  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180038e45  setnz   r8b
0x180038e49  lea     rdx, pszSrc; "\\"
0x180038e50  mov     rcx, rbx; Src
0x180038e53  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180038e58  mov     r8d, 18h
0x180038e5e  lea     rdx, aAppxdeployment; "AppxDeploymentClient.dll"
0x180038e65  mov     rcx, rbx; Src
0x180038e68  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180038e6d  cmp     qword ptr [rbx+18h], 8
0x180038e72  jb      short loc_180038E77
0x180038e74  mov     rbx, [rbx]
0x180038e77  test    rbx, rbx
0x180038e7a  jnz     short loc_180038E9C
0x180038e7c  mov     rcx, [rsp+48h]; this
0x180038e81  mov     ebx, 80070057h
0x180038e86  mov     r9d, ebx; char *
0x180038e89  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180038e90  mov     edx, 48h ; 'H'; void *
0x180038e95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038e9a  jmp     short loc_180038F0E
0x180038e9c  xor     r8d, r8d; dwFlags
0x180038e9f  xor     edx, edx; hFile
0x180038ea1  mov     rcx, rbx; lpLibFileName
0x180038ea4  call    cs:__imp_LoadLibraryExW
0x180038eaa  mov     rsi, rax
0x180038ead  lea     rax, [rsp+48h+var_28]
0x180038eb2  cmp     rdi, rax
0x180038eb5  jz      short loc_180038EDE
0x180038eb7  mov     r14, [rdi]
0x180038eba  test    r14, r14
0x180038ebd  jz      short loc_180038ED9
0x180038ebf  call    cs:__imp_GetLastError
0x180038ec5  mov     ebx, eax
0x180038ec7  mov     rcx, r14; hLibModule
0x180038eca  call    cs:__imp_FreeLibrary
0x180038ed0  mov     ecx, ebx; dwErrCode
0x180038ed2  call    cs:__imp_SetLastError
0x180038ed8  nop
0x180038ed9  mov     [rdi], rsi
0x180038edc  jmp     short loc_180038EED
0x180038ede  test    rsi, rsi
0x180038ee1  jz      short loc_180038EED
0x180038ee3  mov     rcx, rsi; hLibModule
0x180038ee6  call    cs:__imp_FreeLibrary
0x180038eec  nop
0x180038eed  cmp     [rdi], r15
0x180038ef0  jnz     short loc_180038F2B
0x180038ef2  mov     rcx, [rsp+48h]; this
0x180038ef7  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180038efe  mov     edx, 4Bh ; 'K'; void *
0x180038f03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038f08  mov     ebx, eax
0x180038f0a  test    eax, eax
0x180038f0c  jns     short loc_180038F2B
0x180038f0e  mov     rcx, [rsp+48h]; this
0x180038f13  mov     r9d, ebx; char *
0x180038f16  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180038f1d  mov     edx, 3Eh ; '>'; void *
0x180038f22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038f27  mov     eax, ebx
0x180038f29  jmp     short loc_180038F33
0x180038f2b  xor     eax, eax
0x180038f2d  jmp     short loc_180038F33
0x180038f2f  mov     eax, [rsp+48h+arg_0]
0x180038f33  mov     rbx, [rsp+48h+arg_8]
0x180038f38  mov     rsi, [rsp+48h+arg_10]
0x180038f3d  add     rsp, 30h
0x180038f41  pop     r15
0x180038f43  pop     r14
0x180038f45  pop     rdi
0x180038f46  retn
```
