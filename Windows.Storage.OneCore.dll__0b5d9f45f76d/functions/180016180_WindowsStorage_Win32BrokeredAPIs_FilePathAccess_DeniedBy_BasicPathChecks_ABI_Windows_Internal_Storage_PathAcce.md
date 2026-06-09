# WindowsStorage::Win32BrokeredAPIs::FilePathAccess::_DeniedBy_BasicPathChecks(ABI::Windows::Internal::Storage::PathAccessChecks)

- ea: `0x180016180`
- end: `0x1800162ba`
- name: `?_DeniedBy_BasicPathChecks@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@AEBA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z`
- size: `314`
- prototype: `bool __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015b24`

## callees

- `0x18000d504`
- `0x180011c44`
- `0x180016180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800161b6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800161b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016226`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016289`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016226`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016289`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800161a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x1800161a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall WindowsStorage::Win32BrokeredAPIs::FilePathAccess::_DeniedBy_BasicPathChecks(__int64 a1, int a2)
{
  char v4; // bl
  const wchar_t *v5; // rax
  char *v6; // rsi
  char *v7; // rax
  char *v8; // rdx
  char v9; // bp
  LPCWCH lpString1; // [rsp+80h] [rbp+18h] BYREF

  v4 = 1;
  if ( (a2 & 1) != 0 )
  {
    v5 = PathSkipRootW(*(LPCWSTR *)(a1 + 16));
    if ( v5 )
    {
      if ( wcsstr(v5, L":") )
        return 1;
    }
  }
  v6 = byte_180028858;
  v7 = byte_180028858;
  if ( *(_QWORD *)a1 )
    v7 = *(char **)a1;
  if ( !*(_WORD *)v7 || (a2 & 0x10000) != 0 )
    return 0;
  if ( (a2 & 4) != 0 )
  {
    v8 = byte_180028858;
    if ( *(_QWORD *)a1 )
      v8 = *(char **)a1;
    WindowsStorage::Utilities::TryGetExtensionKind(&lpString1, v8);
    if ( !lpString1 || (v9 = 1, CompareStringOrdinal(lpString1, -1, L"program", -1, 1) != 2) )
      v9 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    if ( v9 )
      return 1;
  }
  if ( (a2 & 8) == 0 )
    return 0;
  if ( *(_QWORD *)a1 )
    v6 = *(char **)a1;
  WindowsStorage::Utilities::TryGetExtensionKind(&lpString1, v6);
  if ( !lpString1 || CompareStringOrdinal(lpString1, -1, L"link", -1, 1) != 2 )
    v4 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  return v4 != 0;
}

```

## disassembly

```asm
0x180016180  push    rbx
0x180016182  push    rbp
0x180016183  push    rsi
0x180016184  push    rdi
0x180016185  push    r14
0x180016187  push    r15
0x180016189  sub     rsp, 38h
0x18001618d  xor     r15d, r15d
0x180016190  mov     edi, edx
0x180016192  mov     r14, rcx
0x180016195  lea     ebx, [r15+1]
0x180016199  test    bl, dl
0x18001619b  jz      short loc_1800161C5
0x18001619d  mov     rcx, [rcx+10h]; pszPath
0x1800161a1  call    cs:__imp_PathSkipRootW
0x1800161a7  test    rax, rax
0x1800161aa  jz      short loc_1800161C5
0x1800161ac  lea     rdx, SubStr; ":"
0x1800161b3  mov     rcx, rax; Str
0x1800161b6  call    cs:__imp_wcsstr
0x1800161bc  test    rax, rax
0x1800161bf  jnz     loc_180016249
0x1800161c5  cmp     [r14], r15
0x1800161c8  lea     rsi, byte_180028858
0x1800161cf  mov     rax, rsi
0x1800161d2  cmovnz  rax, [r14]
0x1800161d6  cmp     [rax], r15w
0x1800161da  jz      loc_1800162AB
0x1800161e0  bt      edi, 10h
0x1800161e4  jb      loc_1800162AB
0x1800161ea  test    dil, 4
0x1800161ee  jz      short loc_18001624D
0x1800161f0  cmp     [r14], r15
0x1800161f3  lea     rcx, [rsp+68h+lpString1]
0x1800161fb  mov     rdx, rsi
0x1800161fe  cmovnz  rdx, [r14]
0x180016202  call    ?TryGetExtensionKind@Utilities@WindowsStorage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; WindowsStorage::Utilities::TryGetExtensionKind(ushort const *)
0x180016207  mov     rcx, [rsp+68h+lpString1]; lpString1
0x18001620f  test    rcx, rcx
0x180016212  jz      short loc_180016234
0x180016214  or      r9d, 0FFFFFFFFh; cchCount2
0x180016218  mov     [rsp+68h+bIgnoreCase], ebx; bIgnoreCase
0x18001621c  or      edx, r9d; cchCount1
0x18001621f  lea     r8, String2; "program"
0x180016226  call    cs:__imp_CompareStringOrdinal
0x18001622c  mov     bpl, bl
0x18001622f  cmp     eax, 2
0x180016232  jz      short loc_180016237
0x180016234  mov     bpl, r15b
0x180016237  lea     rcx, [rsp+68h+lpString1]
0x18001623f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016244  test    bpl, bpl
0x180016247  jz      short loc_18001624D
0x180016249  mov     al, bl
0x18001624b  jmp     short loc_1800162AD
0x18001624d  test    dil, 8
0x180016251  jz      short loc_1800162AB
0x180016253  cmp     [r14], r15
0x180016256  lea     rcx, [rsp+68h+lpString1]
0x18001625e  cmovnz  rsi, [r14]
0x180016262  mov     rdx, rsi
0x180016265  call    ?TryGetExtensionKind@Utilities@WindowsStorage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; WindowsStorage::Utilities::TryGetExtensionKind(ushort const *)
0x18001626a  mov     rcx, [rsp+68h+lpString1]; lpString1
0x180016272  test    rcx, rcx
0x180016275  jz      short loc_180016294
0x180016277  or      r9d, 0FFFFFFFFh; cchCount2
0x18001627b  mov     [rsp+68h+bIgnoreCase], ebx; bIgnoreCase
0x18001627f  or      edx, r9d; cchCount1
0x180016282  lea     r8, aLink; "link"
0x180016289  call    cs:__imp_CompareStringOrdinal
0x18001628f  cmp     eax, 2
0x180016292  jz      short loc_180016297
0x180016294  mov     bl, r15b
0x180016297  lea     rcx, [rsp+68h+lpString1]
0x18001629f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800162a4  test    bl, bl
0x1800162a6  setnz   al
0x1800162a9  jmp     short loc_1800162AD
0x1800162ab  xor     al, al
0x1800162ad  add     rsp, 38h
0x1800162b1  pop     r15
0x1800162b3  pop     r14
0x1800162b5  pop     rdi
0x1800162b6  pop     rsi
0x1800162b7  pop     rbp
0x1800162b8  pop     rbx
0x1800162b9  retn
```
