# CloudStoreUtilities::GetPackageRootFolder(ushort const *,ushort const *,ushort *,ulong)

- ea: `0x1801c11b0`
- end: `0x1801c131f`
- name: `?GetPackageRootFolder@CloudStoreUtilities@@YAJPEBG0PEAGK@Z`
- size: `367`
- prototype: `__int64 __fastcall(PCWSTR pszMore, const unsigned __int16 *, WCHAR *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003e904`
- `0x1800b3714`

## callees

- `0x180031e70`
- `0x18003b254`
- `0x180047904`
- `0x180062040`
- `0x180095150`
- `0x1800c8458`
- `0x1800fc644`
- `0x1801c11b0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801c12e1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801c12e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801c1225`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801c1225`
- `USERENV!GetAppContainerFolderPath` at `0x1801c1278`
- `USERENV!GetAppContainerFolderPath` at `0x1801c1278`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1801c11e1`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1801c11e1`

## string_xrefs

- `0x1801c11f1`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1801c1233`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1801c12b8`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`

## pseudocode

```c
__int64 __fastcall CloudStoreUtilities::GetPackageRootFolder(
        PCWSTR pszMore,
        const unsigned __int16 *a2,
        WCHAR *a3,
        unsigned __int16 *a4)
{
  int v7; // eax
  int AppContainerFolderPath; // ebx
  const char *v9; // r9
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  HRESULT v12; // eax
  PCWSTR pszPathIn; // [rsp+20h] [rbp-38h] BYREF
  PSID Sid; // [rsp+28h] [rbp-30h] BYREF
  PCWSTR *p_pszPathIn; // [rsp+30h] [rbp-28h] BYREF
  __int64 v17; // [rsp+38h] [rbp-20h] BYREF
  char v18; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  LPWSTR StringSid; // [rsp+90h] [rbp+38h] BYREF

  *a3 = 0;
  Sid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0,
    a3,
    a4);
  v7 = AppContainerDeriveSidFromMoniker(a2, &Sid);
  AppContainerFolderPath = v7;
  if ( v7 >= 0 )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      p_pszPathIn = &pszPathIn;
      pszPathIn = 0;
      v17 = 0;
      v18 = 1;
      AppContainerFolderPath = GetAppContainerFolderPath(StringSid, &v17);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pszPathIn);
      if ( AppContainerFolderPath >= 0 )
      {
        v12 = PathCchCombine(a3, 0x104u, pszPathIn, pszMore);
        AppContainerFolderPath = v12;
        if ( v12 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathIn);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          AppContainerFolderPath = 0;
          goto LABEL_14;
        }
        v10 = (unsigned int)v12;
        v11 = 665;
      }
      else
      {
        if ( AppContainerFolderPath == -2147024894 )
        {
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathIn);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          AppContainerFolderPath = -2147024894;
          goto LABEL_14;
        }
        v10 = (unsigned int)AppContainerFolderPath;
        v11 = 664;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
        (const char *)v10,
        (int)pszPathIn);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathIn);
    }
    else
    {
      AppContainerFolderPath = wil::details::in1diag3::Return_GetLastError(
                                 retaddr,
                                 (void *)0x295,
                                 (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
                                 v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\cloudstoreutilities.cpp",
      (const char *)(unsigned int)v7,
      (int)pszPathIn);
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return (unsigned int)AppContainerFolderPath;
}

```

## disassembly

```asm
0x1801c11b0  push    rbp
0x1801c11b2  push    rbx
0x1801c11b3  push    rsi
0x1801c11b4  push    rdi
0x1801c11b5  mov     rbp, rsp
0x1801c11b8  sub     rsp, 58h
0x1801c11bc  xor     eax, eax
0x1801c11be  mov     rbx, rdx
0x1801c11c1  mov     rsi, rcx
0x1801c11c4  mov     [r8], ax
0x1801c11c8  xor     edx, edx
0x1801c11ca  mov     [rbp+Sid], rax
0x1801c11ce  lea     rcx, [rbp+Sid]
0x1801c11d2  mov     rdi, r8
0x1801c11d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1801c11da  lea     rdx, [rbp+Sid]
0x1801c11de  mov     rcx, rbx
0x1801c11e1  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1801c11e7  mov     ebx, eax
0x1801c11e9  test    eax, eax
0x1801c11eb  jns     short loc_1801C120A
0x1801c11ed  mov     rcx, [rbp+20h]; this
0x1801c11f1  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1801c11f8  mov     r9d, eax; char *
0x1801c11fb  mov     edx, 292h; void *
0x1801c1200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c1205  jmp     loc_1801C130B
0x1801c120a  xor     edx, edx
0x1801c120c  mov     [rbp+StringSid], 0
0x1801c1214  lea     rcx, [rbp+StringSid]
0x1801c1218  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801c121d  mov     rcx, [rbp+Sid]; Sid
0x1801c1221  lea     rdx, [rbp+StringSid]; StringSid
0x1801c1225  call    cs:__imp_ConvertSidToStringSidW
0x1801c122b  test    eax, eax
0x1801c122d  jnz     short loc_1801C1254
0x1801c122f  mov     rcx, [rbp+20h]; this
0x1801c1233  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1801c123a  mov     edx, 295h; void *
0x1801c123f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801c1244  mov     ebx, eax
0x1801c1246  lea     rcx, [rbp+StringSid]
0x1801c124a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801c124f  jmp     loc_1801C130B
0x1801c1254  mov     rcx, [rbp+StringSid]
0x1801c1258  lea     rax, [rbp+pszPathIn]
0x1801c125c  lea     rdx, [rbp+var_20]
0x1801c1260  mov     [rbp+var_28], rax
0x1801c1264  mov     [rbp+pszPathIn], 0
0x1801c126c  mov     [rbp+var_20], 0
0x1801c1274  mov     [rbp+var_18], 1
0x1801c1278  call    cs:__imp_GetAppContainerFolderPath
0x1801c127e  lea     rcx, [rbp+var_28]
0x1801c1282  mov     ebx, eax
0x1801c1284  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1801c1289  test    ebx, ebx
0x1801c128b  jns     short loc_1801C12D2
0x1801c128d  mov     edi, 80070002h
0x1801c1292  cmp     ebx, edi
0x1801c1294  jnz     short loc_1801C12AC
0x1801c1296  lea     rcx, [rbp+pszPathIn]
0x1801c129a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c129f  lea     rcx, [rbp+StringSid]
0x1801c12a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801c12a8  mov     ebx, edi
0x1801c12aa  jmp     short loc_1801C130B
0x1801c12ac  mov     r9d, ebx; char *
0x1801c12af  mov     edx, 298h; void *
0x1801c12b4  mov     rcx, [rbp+20h]; this
0x1801c12b8  lea     r8, aOnecoreuapShel_101; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1801c12bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c12c4  lea     rcx, [rbp+pszPathIn]
0x1801c12c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c12cd  jmp     loc_1801C1246
0x1801c12d2  mov     r8, [rbp+pszPathIn]; pszPathIn
0x1801c12d6  mov     r9, rsi; pszMore
0x1801c12d9  mov     edx, 104h; cchPathOut
0x1801c12de  mov     rcx, rdi; pszPathOut
0x1801c12e1  call    cs:__imp_PathCchCombine
0x1801c12e7  mov     ebx, eax
0x1801c12e9  test    eax, eax
0x1801c12eb  jns     short loc_1801C12F7
0x1801c12ed  mov     r9d, eax
0x1801c12f0  mov     edx, 299h
0x1801c12f5  jmp     short loc_1801C12B4
0x1801c12f7  lea     rcx, [rbp+pszPathIn]
0x1801c12fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c1300  lea     rcx, [rbp+StringSid]
0x1801c1304  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801c1309  xor     ebx, ebx
0x1801c130b  lea     rcx, [rbp+Sid]
0x1801c130f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801c1314  mov     eax, ebx
0x1801c1316  add     rsp, 58h
0x1801c131a  pop     rdi
0x1801c131b  pop     rsi
0x1801c131c  pop     rbx
0x1801c131d  pop     rbp
0x1801c131e  retn
```
