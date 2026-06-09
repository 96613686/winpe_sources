# EnableMitigations(void)

- ea: `0x180008b00`
- end: `0x180008cea`
- name: `?EnableMitigations@@YAXXZ`
- size: `490`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008850`

## callees

- `0x180008b00`
- `0x180008cf0`
- `0x180051492`
- `0x180051524`
- `0x180056c06`
- `0x180058ac4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008cc9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008cc9`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180008b7a`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180008b7a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008c30`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008c30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008b08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008b08`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180008c57`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180008c57`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008b18`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008b18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ce2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008bd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008bd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c7d`

## string_xrefs

- `0x180008cad`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void EnableMitigations(void)
{
  DWORD CurrentProcessId; // eax
  char *v1; // rax
  char *v2; // rbx
  __int64 v3; // rdx
  WCHAR *v4; // rdi
  __int64 v5; // r8
  const WCHAR *v6; // rsi
  int StringOrdinal; // eax
  const char *v8; // r9
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  size_t v11; // r14
  size_t v12; // r15
  WCHAR *v13; // rax
  WCHAR *v14; // rbp
  int i; // esi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPCWSTR lpStringSource; // [rsp+50h] [rbp+8h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  v1 = (char *)OpenProcess(0x1000u, 0, CurrentProcessId);
  lpStringSource = 0;
  v2 = v1;
  wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
    (__int64)v1,
    v3,
    (__int64)&lpStringSource);
  v4 = (WCHAR *)lpStringSource;
  v5 = -1;
  do
    ++v5;
  while ( lpStringSource[v5] );
  v6 = &lpStringSource[v5];
  if ( v5 && *(v6 - 1) == 92 )
    LODWORD(v5) = v5 - 1;
  StringOrdinal = FindStringOrdinal(0x800000u, lpStringSource, v5, L"\\", 1, 1);
  if ( StringOrdinal != -1 )
    v6 = &v4[StringOrdinal + 1];
  if ( !v6 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v8);
  v9 = 0x7FFFFFFF;
  v10 = v6;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = 2 * (v10 - v6);
  v12 = v11 + 2;
  v13 = (WCHAR *)CoTaskMemAlloc(v11 + 2);
  v14 = v13;
  if ( v13 )
  {
    if ( v11 )
    {
      if ( v12 < v11 )
      {
        memset_0(v13, 0, v12);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v13, v6, v11);
      }
    }
    v14[v11 / 2] = 0;
  }
  for ( i = 0; !i; i = 1 )
  {
    if ( CompareStringOrdinal(v14, -1, L"dllhost.exe", -1, 1) == 2 )
    {
      LODWORD(lpStringSource) = 1;
      SetProcessMitigationPolicy(16, &lpStringSource, 4);
      break;
    }
  }
  if ( v14 )
    CoTaskMemFree(v14);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
}

```

## disassembly

```asm
0x180008b00  push    rbx
0x180008b02  push    rsi
0x180008b03  push    rdi
0x180008b04  sub     rsp, 30h
0x180008b08  call    cs:__imp_GetCurrentProcessId
0x180008b0e  xor     edx, edx; bInheritHandle
0x180008b10  mov     ecx, 1000h; dwDesiredAccess
0x180008b15  mov     r8d, eax; dwProcessId
0x180008b18  call    cs:__imp_OpenProcess
0x180008b1e  lea     r8, [rsp+48h+lpStringSource]
0x180008b23  mov     [rsp+48h+lpStringSource], 0
0x180008b2c  mov     rcx, rax
0x180008b2f  mov     rbx, rax
0x180008b32  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180008b37  mov     rdi, [rsp+48h+lpStringSource]
0x180008b3c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008b43  inc     r8; cchSource
0x180008b46  cmp     word ptr [rdi+r8*2], 0
0x180008b4c  jnz     short loc_180008B43
0x180008b4e  lea     rsi, [rdi+r8*2]
0x180008b52  test    r8, r8
0x180008b55  jnz     loc_180008C95
0x180008b5b  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180008b63  lea     r9, pszSrc; "\\"
0x180008b6a  mov     rdx, rdi; lpStringSource
0x180008b6d  mov     [rsp+48h+cchValue], 1; cchValue
0x180008b75  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180008b7a  call    cs:__imp_FindStringOrdinal
0x180008b80  cmp     eax, 0FFFFFFFFh
0x180008b83  jz      short loc_180008B8F
0x180008b85  movsxd  rsi, eax
0x180008b88  inc     rsi
0x180008b8b  lea     rsi, [rdi+rsi*2]
0x180008b8f  test    rsi, rsi
0x180008b92  jz      loc_180008CA8
0x180008b98  mov     [rsp+48h+arg_8], rbp
0x180008b9d  mov     ecx, 7FFFFFFFh
0x180008ba2  mov     [rsp+48h+arg_10], r14
0x180008ba7  mov     rax, rsi
0x180008baa  mov     [rsp+48h+arg_18], r15
0x180008baf  nop
0x180008bb0  cmp     word ptr [rax], 0
0x180008bb4  jz      short loc_180008BC0
0x180008bb6  add     rax, 2
0x180008bba  sub     rcx, 1
0x180008bbe  jnz     short loc_180008BB0
0x180008bc0  sub     rax, rsi
0x180008bc3  sar     rax, 1
0x180008bc6  lea     r14, [rax+rax]
0x180008bca  lea     r15, [r14+2]
0x180008bce  mov     rcx, r15; cb
0x180008bd1  call    cs:__imp_CoTaskMemAlloc
0x180008bd7  mov     rbp, rax
0x180008bda  test    rax, rax
0x180008bdd  jz      short loc_180008C02
0x180008bdf  test    r14, r14
0x180008be2  jz      short loc_180008BFB
0x180008be4  mov     rcx, rax; void *
0x180008be7  cmp     r15, r14
0x180008bea  jb      loc_180008CBF
0x180008bf0  mov     r8, r14; Size
0x180008bf3  mov     rdx, rsi; Src
0x180008bf6  call    memcpy_0
0x180008bfb  xor     eax, eax
0x180008bfd  mov     [r14+rbp], ax
0x180008c02  mov     r15, [rsp+48h+arg_18]
0x180008c07  lea     r14, off_1800E6050; "dllhost.exe"
0x180008c0e  xor     esi, esi
0x180008c10  cmp     esi, 1
0x180008c13  jnb     short loc_180008C5D
0x180008c15  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008c1b  movsxd  r8, esi
0x180008c1e  mov     edx, r9d; cchCount1
0x180008c21  mov     [rsp+48h+cchValue], 1; bIgnoreCase
0x180008c29  mov     rcx, rbp; lpString1
0x180008c2c  mov     r8, [r14+r8*8]; lpString2
0x180008c30  call    cs:__imp_CompareStringOrdinal
0x180008c36  cmp     eax, 2
0x180008c39  jz      short loc_180008C3F
0x180008c3b  inc     esi
0x180008c3d  jmp     short loc_180008C10
0x180008c3f  mov     r8d, 4
0x180008c45  mov     dword ptr [rsp+48h+lpStringSource], 1
0x180008c4d  lea     rdx, [rsp+48h+lpStringSource]
0x180008c52  mov     ecx, 10h
0x180008c57  call    cs:__imp_SetProcessMitigationPolicy
0x180008c5d  mov     r14, [rsp+48h+arg_10]
0x180008c62  test    rbp, rbp
0x180008c65  jz      short loc_180008C70
0x180008c67  mov     rcx, rbp; pv
0x180008c6a  call    cs:__imp_CoTaskMemFree
0x180008c70  mov     rbp, [rsp+48h+arg_8]
0x180008c75  test    rdi, rdi
0x180008c78  jz      short loc_180008C83
0x180008c7a  mov     rcx, rdi; pv
0x180008c7d  call    cs:__imp_CoTaskMemFree
0x180008c83  lea     rax, [rbx-1]
0x180008c87  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008c8b  jbe     short loc_180008CDF
0x180008c8d  add     rsp, 30h
0x180008c91  pop     rdi
0x180008c92  pop     rsi
0x180008c93  pop     rbx
0x180008c94  retn
0x180008c95  cmp     word ptr [rsi-2], 5Ch ; '\'
0x180008c9a  jnz     loc_180008B5B
0x180008ca0  dec     r8
0x180008ca3  jmp     loc_180008B5B
0x180008ca8  mov     rcx, [rsp+48h]; this
0x180008cad  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008cb4  mov     edx, 0F89h; void *
0x180008cb9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180008cbf  mov     r8, r15; Size
0x180008cc2  xor     edx, edx; Val
0x180008cc4  call    memset_0
0x180008cc9  call    cs:__imp__o__errno
0x180008ccf  mov     dword ptr [rax], 22h ; '"'
0x180008cd5  call    _invalid_parameter_noinfo
0x180008cda  jmp     loc_180008BFB
0x180008cdf  mov     rcx, rbx; hObject
0x180008ce2  call    cs:__imp_CloseHandle
0x180008ce8  jmp     short loc_180008C8D
```
