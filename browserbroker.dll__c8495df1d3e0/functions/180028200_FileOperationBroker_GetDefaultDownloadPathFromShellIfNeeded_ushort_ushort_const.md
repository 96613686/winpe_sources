# FileOperationBroker::GetDefaultDownloadPathFromShellIfNeeded(ushort * *,ushort const *)

- ea: `0x180028200`
- end: `0x180028486`
- name: `?GetDefaultDownloadPathFromShellIfNeeded@FileOperationBroker@@UEAAJPEAPEAGPEBG@Z`
- size: `646`
- prototype: `int(FileOperationBroker *__hidden this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000dc74`
- `0x18000e428`
- `0x18001078c`
- `0x180010b4c`
- `0x18001e93c`
- `0x18002583c`
- `0x180026b10`
- `0x180028200`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18002841a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18002841a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800282f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800282f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028365`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028299`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180028299`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x180028429`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x180028429`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800283a5`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800283ec`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800283a5`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800283ec`

## string_xrefs

- `0x18002833f`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FileOperationBroker::GetDefaultDownloadPathFromShellIfNeeded(
        FileOperationBroker *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3)
{
  int PIC; // ebx
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r14
  WCHAR *v8; // rcx
  signed int v9; // edi
  signed int LastError; // eax
  unsigned __int16 *v11; // rax
  unsigned __int16 **v13; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v14; // [rsp+28h] [rbp-D8h]
  unsigned int v15; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 **v17; // [rsp+48h] [rbp-B8h] BYREF
  PWSTR ppszPath; // [rsp+50h] [rbp-B0h] BYREF
  char v19; // [rsp+58h] [rbp-A8h]
  LPWSTR pszPath[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Dst[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  LODWORD(v16) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&v16);
  *a2 = 0;
  if ( PIC >= 0 )
  {
    v16 = 0;
    if ( a3 && *a3 )
    {
      memset_0(Dst, 0, 0x208u);
      if ( ExpandEnvironmentStringsW(a3, Dst, 0x104u) )
      {
        v17 = &v16;
        v19 = 1;
        v6 = -1;
        do
          ++v6;
        while ( Dst[v6] );
        ppszPath = 0;
        v7 = v6 + 1;
        if ( v6 + 1 < v6 )
        {
          v9 = -2147024362;
        }
        else
        {
          v8 = 0;
          ppszPath = 0;
          pszPath[0] = 0;
          if ( is_mul_ok(v7, 2u) )
          {
            v8 = (WCHAR *)CoTaskMemAlloc(2 * v7);
            ppszPath = v8;
            v9 = v8 == 0 ? 0x8007000E : 0;
          }
          else
          {
            v9 = -2147024362;
          }
          if ( v9 >= 0 )
            StringCchCopyNExW(v8, v6 + 1, Dst, v6, v13, v14, v15);
        }
        if ( v9 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x1D6,
            (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
            (const char *)(unsigned int)v9,
            (int)v13);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v17);
        goto LABEL_22;
      }
      LastError = GetLastError();
      PIC = LastError;
      if ( LastError > 0 )
        PIC = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v17 = &v16;
      ppszPath = 0;
      v19 = 1;
      PIC = SHGetKnownFolderPath(&FOLDERID_Downloads, 0, 0, &ppszPath);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v17);
      if ( PIC == -2147024809 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v16,
          0);
        v17 = &v16;
        ppszPath = 0;
        v19 = 1;
        PIC = SHGetKnownFolderPath(&FOLDERID_PublicDownloads, 0, 0, &ppszPath);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v17);
      }
    }
    if ( PIC < 0 )
    {
LABEL_27:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v16);
      return (unsigned int)PIC;
    }
LABEL_22:
    wil::make_cotaskmem_string_failfast((wil *)pszPath, v16, 0xFFFFFFFFFFFFFFFFuLL);
    if ( PathStripToRootW(pszPath[0]) && !PathIsDirectoryW(pszPath[0]) )
      PIC = -2147024809;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)pszPath);
    if ( PIC >= 0 )
    {
      v11 = v16;
      v16 = 0;
      *a2 = v11;
    }
    goto LABEL_27;
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180028200  mov     [rsp-8+arg_0], rbx
0x180028205  mov     [rsp-8+arg_18], rsi
0x18002820a  push    rbp
0x18002820b  push    rdi
0x18002820c  push    r12
0x18002820e  push    r14
0x180028210  push    r15
0x180028212  lea     rbp, [rsp-190h]
0x18002821a  sub     rsp, 290h
0x180028221  mov     rax, cs:__security_cookie
0x180028228  xor     rax, rsp
0x18002822b  mov     [rbp+1B0h+var_30], rax
0x180028232  mov     rdi, r8
0x180028235  mov     r15, rdx
0x180028238  xor     r12d, r12d
0x18002823b  mov     dword ptr [rsp+2B0h+var_270], r12d
0x180028240  lea     rdx, [rsp+2B0h+var_270]; unsigned int *
0x180028245  lea     ecx, [r12+1]; unsigned int
0x18002824a  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18002824f  mov     ebx, eax
0x180028251  mov     [r15], r12
0x180028254  test    eax, eax
0x180028256  js      loc_180028459
0x18002825c  mov     [rsp+2B0h+var_270], r12
0x180028261  mov     esi, 80070057h
0x180028266  test    rdi, rdi
0x180028269  jz      loc_180028380
0x18002826f  cmp     [rdi], r12w
0x180028273  jz      loc_180028380
0x180028279  xor     edx, edx; Val
0x18002827b  mov     r8d, 208h; Size
0x180028281  lea     rcx, [rsp+2B0h+Dst]; void *
0x180028286  call    memset_0
0x18002828b  mov     r8d, 104h; nSize
0x180028291  lea     rdx, [rsp+2B0h+Dst]; lpDst
0x180028296  mov     rcx, rdi; lpSrc
0x180028299  call    cs:__imp_ExpandEnvironmentStringsW
0x18002829f  test    eax, eax
0x1800282a1  jz      loc_180028365
0x1800282a7  lea     rax, [rsp+2B0h+var_270]
0x1800282ac  mov     [rsp+2B0h+var_268], rax
0x1800282b1  mov     [rsp+2B0h+var_258], 1
0x1800282b6  lea     rax, [rsp+2B0h+Dst]
0x1800282bb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800282bf  inc     rsi
0x1800282c2  cmp     [rax+rsi*2], r12w
0x1800282c7  jnz     short loc_1800282BF
0x1800282c9  mov     [rsp+2B0h+ppszPath], r12
0x1800282ce  lea     r14, [rsi+1]
0x1800282d2  cmp     r14, rsi
0x1800282d5  jb      short loc_18002832C
0x1800282d7  mov     rcx, r12; unsigned __int16 *
0x1800282da  mov     [rsp+2B0h+ppszPath], rcx
0x1800282df  mov     [rsp+2B0h+pszPath], r12
0x1800282e4  mov     eax, 2
0x1800282e9  mul     r14
0x1800282ec  test    rdx, rdx
0x1800282ef  jnz     short loc_180028311
0x1800282f1  mov     rcx, rax; cb
0x1800282f4  call    cs:__imp_CoTaskMemAlloc
0x1800282fa  mov     rcx, rax
0x1800282fd  mov     [rsp+2B0h+ppszPath], rax
0x180028302  neg     rax
0x180028305  sbb     edi, edi
0x180028307  not     edi
0x180028309  and     edi, 8007000Eh
0x18002830f  jmp     short loc_180028316
0x180028311  mov     edi, 80070216h
0x180028316  test    edi, edi
0x180028318  js      short loc_180028331
0x18002831a  mov     r9, rsi; unsigned __int64
0x18002831d  lea     r8, [rsp+2B0h+Dst]; unsigned __int16 *
0x180028322  mov     rdx, r14; unsigned __int64
0x180028325  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18002832a  jmp     short loc_180028331
0x18002832c  mov     edi, 80070216h
0x180028331  mov     rcx, [rbp+1B8h]; this
0x180028338  test    edi, edi
0x18002833a  jns     short loc_180028351
0x18002833c  mov     r9d, edi; char *
0x18002833f  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180028346  mov     edx, 1D6h; void *
0x18002834b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180028351  lea     rcx, [rsp+2B0h+var_268]
0x180028356  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002835b  mov     esi, 80070057h
0x180028360  jmp     loc_180028402
0x180028365  call    cs:__imp_GetLastError
0x18002836b  mov     ebx, eax
0x18002836d  test    eax, eax
0x18002836f  jle     loc_1800283FE
0x180028375  movzx   ebx, ax
0x180028378  or      ebx, 80070000h
0x18002837e  jmp     short loc_1800283FE
0x180028380  lea     rax, [rsp+2B0h+var_270]
0x180028385  mov     [rsp+2B0h+var_268], rax
0x18002838a  mov     [rsp+2B0h+ppszPath], r12
0x18002838f  mov     [rsp+2B0h+var_258], 1
0x180028394  lea     r9, [rsp+2B0h+ppszPath]; ppszPath
0x180028399  xor     r8d, r8d; hToken
0x18002839c  xor     edx, edx; dwFlags
0x18002839e  lea     rcx, FOLDERID_Downloads; rfid
0x1800283a5  call    cs:__imp_SHGetKnownFolderPath
0x1800283ab  mov     ebx, eax
0x1800283ad  lea     rcx, [rsp+2B0h+var_268]
0x1800283b2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800283b7  cmp     ebx, esi
0x1800283b9  jnz     short loc_1800283FE
0x1800283bb  xor     edx, edx
0x1800283bd  lea     rcx, [rsp+2B0h+var_270]
0x1800283c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800283c7  lea     rax, [rsp+2B0h+var_270]
0x1800283cc  mov     [rsp+2B0h+var_268], rax
0x1800283d1  mov     [rsp+2B0h+ppszPath], r12
0x1800283d6  mov     [rsp+2B0h+var_258], 1
0x1800283db  lea     r9, [rsp+2B0h+ppszPath]; ppszPath
0x1800283e0  xor     r8d, r8d; hToken
0x1800283e3  xor     edx, edx; dwFlags
0x1800283e5  lea     rcx, FOLDERID_PublicDownloads; rfid
0x1800283ec  call    cs:__imp_SHGetKnownFolderPath
0x1800283f2  mov     ebx, eax
0x1800283f4  lea     rcx, [rsp+2B0h+var_268]
0x1800283f9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800283fe  test    ebx, ebx
0x180028400  js      short loc_18002844F
0x180028402  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180028406  mov     rdx, [rsp+2B0h+var_270]; unsigned __int16 *
0x18002840b  lea     rcx, [rsp+2B0h+pszPath]; this
0x180028410  call    ?make_cotaskmem_string_failfast@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_failfast(ushort const *,unsigned __int64)
0x180028415  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x18002841a  call    cs:__imp_PathStripToRootW
0x180028420  test    eax, eax
0x180028422  jz      short loc_180028434
0x180028424  mov     rcx, [rsp+2B0h+pszPath]; pszPath
0x180028429  call    cs:__imp_PathIsDirectoryW
0x18002842f  test    eax, eax
0x180028431  cmovz   ebx, esi
0x180028434  lea     rcx, [rsp+2B0h+pszPath]
0x180028439  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002843e  test    ebx, ebx
0x180028440  js      short loc_18002844F
0x180028442  mov     rax, [rsp+2B0h+var_270]
0x180028447  mov     [rsp+2B0h+var_270], r12
0x18002844c  mov     [r15], rax
0x18002844f  lea     rcx, [rsp+2B0h+var_270]
0x180028454  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028459  mov     eax, ebx
0x18002845b  mov     rcx, [rbp+1B0h+var_30]
0x180028462  xor     rcx, rsp; StackCookie
0x180028465  call    __security_check_cookie
0x18002846a  lea     r11, [rsp+2B0h+var_20]
0x180028472  mov     rbx, [r11+30h]
0x180028476  mov     rsi, [r11+48h]
0x18002847a  mov     rsp, r11
0x18002847d  pop     r15
0x18002847f  pop     r14
0x180028481  pop     r12
0x180028483  pop     rdi
0x180028484  pop     rbp
0x180028485  retn
```
