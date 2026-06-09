# MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::COemLicense>::LoadDynamic(void)

- ea: `0x18004c420`
- end: `0x18004c5a5`
- name: `?LoadDynamic@?$MsixProvisioningModule@VCOemLicense@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004b268`
- `0x18004e0e0`

## callees

- `0x18000d3bc`
- `0x18000d3dc`
- `0x18001d160`
- `0x18003e50c`
- `0x18004c420`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004c4e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004c4e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c515`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c53d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c515`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c53d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c504`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c523`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c523`

## string_xrefs

- `0x18004c4c5`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004c554`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004c573`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004c49a`: `OemLicense.dll`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::COemLicense>::LoadDynamic(
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
      std::wstring::append(v2, L"OemLicense.dll");
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
0x18004c420  mov     [rsp+arg_8], rbx
0x18004c425  mov     [rsp+arg_10], rsi
0x18004c42a  push    rdi
0x18004c42b  push    r14
0x18004c42d  push    r15
0x18004c42f  sub     rsp, 30h
0x18004c433  lea     rdi, [rcx+8]
0x18004c437  xor     r15d, r15d
0x18004c43a  cmp     [rdi], r15
0x18004c43d  jnz     loc_18004C588
0x18004c443  lea     rbx, [rcx+18h]
0x18004c447  cmp     [rbx+10h], r15
0x18004c44b  jnz     loc_18004C588
0x18004c451  mov     rdx, [rcx+10h]; Src
0x18004c455  cmp     [rdx], r15w
0x18004c459  jnz     short loc_18004C460
0x18004c45b  mov     r8d, r15d
0x18004c45e  jmp     short loc_18004C46E
0x18004c460  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004c464  inc     r8
0x18004c467  cmp     [rdx+r8*2], r15w
0x18004c46c  jnz     short loc_18004C464
0x18004c46e  mov     rcx, rbx; void *
0x18004c471  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004c476  mov     r8, r15
0x18004c479  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18004c481  setnz   r8b
0x18004c485  lea     rdx, pszSrc; "\\"
0x18004c48c  mov     rcx, rbx; Src
0x18004c48f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004c494  mov     r8d, 0Eh
0x18004c49a  lea     rdx, aOemlicenseDll; "OemLicense.dll"
0x18004c4a1  mov     rcx, rbx; Src
0x18004c4a4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004c4a9  cmp     qword ptr [rbx+18h], 8
0x18004c4ae  jb      short loc_18004C4B3
0x18004c4b0  mov     rbx, [rbx]
0x18004c4b3  test    rbx, rbx
0x18004c4b6  jnz     short loc_18004C4DB
0x18004c4b8  mov     rcx, [rsp+48h]; this
0x18004c4bd  mov     ebx, 80070057h
0x18004c4c2  mov     r9d, ebx; char *
0x18004c4c5  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c4cc  mov     edx, 48h ; 'H'; void *
0x18004c4d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c4d6  jmp     loc_18004C56B
0x18004c4db  xor     r8d, r8d; dwFlags
0x18004c4de  xor     edx, edx; hFile
0x18004c4e0  mov     rcx, rbx; lpLibFileName
0x18004c4e3  call    cs:__imp_LoadLibraryExW
0x18004c4ea  nop     dword ptr [rax+rax+00h]
0x18004c4ef  mov     rsi, rax
0x18004c4f2  lea     rax, [rsp+48h+var_28]
0x18004c4f7  cmp     rdi, rax
0x18004c4fa  jz      short loc_18004C535
0x18004c4fc  mov     r14, [rdi]
0x18004c4ff  test    r14, r14
0x18004c502  jz      short loc_18004C530
0x18004c504  call    cs:__imp_GetLastError
0x18004c50b  nop     dword ptr [rax+rax+00h]
0x18004c510  mov     ebx, eax
0x18004c512  mov     rcx, r14; hLibModule
0x18004c515  call    cs:__imp_FreeLibrary
0x18004c51c  nop     dword ptr [rax+rax+00h]
0x18004c521  mov     ecx, ebx; dwErrCode
0x18004c523  call    cs:__imp_SetLastError
0x18004c52a  nop     dword ptr [rax+rax+00h]
0x18004c52f  nop
0x18004c530  mov     [rdi], rsi
0x18004c533  jmp     short loc_18004C54A
0x18004c535  test    rsi, rsi
0x18004c538  jz      short loc_18004C54A
0x18004c53a  mov     rcx, rsi; hLibModule
0x18004c53d  call    cs:__imp_FreeLibrary
0x18004c544  nop     dword ptr [rax+rax+00h]
0x18004c549  nop
0x18004c54a  cmp     [rdi], r15
0x18004c54d  jnz     short loc_18004C588
0x18004c54f  mov     rcx, [rsp+48h]; this
0x18004c554  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c55b  mov     edx, 4Bh ; 'K'; void *
0x18004c560  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c565  mov     ebx, eax
0x18004c567  test    eax, eax
0x18004c569  jns     short loc_18004C588
0x18004c56b  mov     rcx, [rsp+48h]; this
0x18004c570  mov     r9d, ebx; char *
0x18004c573  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c57a  mov     edx, 3Eh ; '>'; void *
0x18004c57f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c584  mov     eax, ebx
0x18004c586  jmp     short loc_18004C590
0x18004c588  xor     eax, eax
0x18004c58a  jmp     short loc_18004C590
0x18004c58c  mov     eax, [rsp+48h+arg_0]
0x18004c590  mov     rbx, [rsp+48h+arg_8]
0x18004c595  mov     rsi, [rsp+48h+arg_10]
0x18004c59a  add     rsp, 30h
0x18004c59e  pop     r15
0x18004c5a0  pop     r14
0x18004c5a2  pop     rdi
0x18004c5a3  retn
```
