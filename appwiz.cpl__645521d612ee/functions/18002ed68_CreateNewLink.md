# _CreateNewLink

- ea: `0x18002ed68`
- end: `0x18002f11d`
- name: `_CreateNewLink`
- size: `949`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002dd80`
- `0x18002e9ac`

## callees

- `0x180007560`
- `0x180016edc`
- `0x18002dd58`
- `0x18002e0a4`
- `0x18002e900`
- `0x18002ed68`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x18002eec7`
- `SHELL32!SHFileOperationW` at `0x18002eec7`
- `SHELL32!SHGetFileInfoW` at `0x18002ee21`
- `SHELL32!SHGetFileInfoW` at `0x18002ee21`
- `SHLWAPI!PathFileExistsW` at `0x18002eedc`
- `SHLWAPI!PathFileExistsW` at `0x18002eedc`
- `SHLWAPI!PathFindExtensionW` at `0x18002eda9`
- `SHLWAPI!PathFindExtensionW` at `0x18002edbc`
- `SHLWAPI!PathFindExtensionW` at `0x18002eda9`
- `SHLWAPI!PathFindExtensionW` at `0x18002edbc`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002edc8`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002edc8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002efc8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002efc8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002ef51`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002ef51`

## string_xrefs

- `0x18002edde`: `shell\cpls\appwzdui\link.cpp`
- `0x18002eefe`: `shell\cpls\appwzdui\link.cpp`

## pseudocode

```c
__int64 __fastcall CreateNewLink(__int64 a1, __int64 (__fastcall ***a2)(_QWORD, GUID *, const WCHAR **))
{
  const WCHAR *v3; // rsi
  const WCHAR *v4; // rdi
  const WCHAR *ExtensionW; // rbx
  const WCHAR *v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  bool v9; // sf
  int uFlags; // [rsp+20h] [rbp-E0h]
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  const WCHAR *v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  _SHFILEOPSTRUCTW FileOp; // [rsp+48h] [rbp-B8h] BYREF
  SHFILEINFOW psfi; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  if ( (*(_DWORD *)a1 & 0x200) != 0 )
  {
    v3 = (const WCHAR *)(a1 + 4);
    v4 = (const WCHAR *)(a1 + 524);
    ExtensionW = PathFindExtensionW((LPCWSTR)(a1 + 4));
    v6 = PathFindExtensionW(v4);
    if ( StrCmpICW(v6, ExtensionW) )
    {
      v7 = 159;
LABEL_4:
      v8 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"shell\\cpls\\appwzdui\\link.cpp",
        (const char *)0x80070057LL,
        uFlags);
      return (unsigned int)v8;
    }
    memset_0(&psfi, 0, sizeof(psfi));
    if ( !SHGetFileInfoW(v4, 0x80u, &psfi, 0x2B8u, 0x810u) )
    {
      v7 = 162;
      goto LABEL_4;
    }
    if ( (psfi.dwAttributes & 0x10000) == 0 )
    {
      v7 = 163;
      goto LABEL_4;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56311826>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56311826>::GetImpl'::`2'::impl) )
    {
      if ( !CopyFileW(v4, v3, 0) )
        return (unsigned int)ResultFromKnownLastError();
      return 0;
    }
    MakeDoubleNullTerminatedString(&ppv, v4);
    MakeDoubleNullTerminatedString(&v13, v3);
    if ( !ppv || !v13 )
    {
      v8 = -2147024882;
      goto LABEL_22;
    }
    FileOp.pTo = v13;
    *(_OWORD *)&FileOp.hwnd = 0;
    FileOp.wFunc = 2;
    memset(&FileOp.fFlags, 0, 24);
    FileOp.fFlags = 1044;
    FileOp.pFrom = (PCZZWSTR)ppv;
    v8 = SHFileOperationW(&FileOp);
    if ( !v8 )
    {
      if ( FileOp.fAnyOperationsAborted )
        goto LABEL_17;
      if ( PathFileExistsW(v3) )
      {
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppv);
        return 0;
      }
    }
    v9 = v8 < 0;
    if ( v8 <= 0 )
      goto LABEL_18;
    v8 = (unsigned __int16)v8 | 0x80070000;
LABEL_17:
    v9 = v8 < 0;
LABEL_18:
    if ( v9 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"shell\\cpls\\appwzdui\\link.cpp",
        (const char *)(unsigned int)v8,
        uFlags);
LABEL_22:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppv);
      return (unsigned int)v8;
    }
    goto LABEL_20;
  }
  v13 = 0;
  if ( a2 )
  {
    v8 = (**a2)(a2, &GUID_0000010b_0000_0000_c000_000000000046, &v13);
  }
  else
  {
    ppv = 0;
    v8 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &ppv);
    if ( v8 < 0 )
      return (unsigned int)v8;
    v14 = 0;
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1, &v14) >= 0 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 56LL))(v14, 0x80000);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 160LL))(ppv, a1 + 524);
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 88LL))(ppv, a1 + 1044);
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 72LL))(ppv, a1 + 1564);
    if ( (*(_BYTE *)a1 & 4) != 0 )
      (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 136LL))(
        ppv,
        a1 + 4684,
        *(unsigned __int16 *)(a1 + 5204));
    v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, const WCHAR **))ppv)(
           ppv,
           &GUID_0000010b_0000_0000_c000_000000000046,
           &v13);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(const WCHAR *, __int64, __int64))(*(_QWORD *)v13 + 48LL))(v13, a1 + 4, 1);
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002ed68  mov     [rsp-8+arg_10], rbx
0x18002ed6d  push    rbp
0x18002ed6e  push    rsi
0x18002ed6f  push    rdi
0x18002ed70  lea     rbp, [rsp-250h]
0x18002ed78  sub     rsp, 350h
0x18002ed7f  mov     rax, cs:__security_cookie
0x18002ed86  xor     rax, rsp
0x18002ed89  mov     [rbp+260h+var_20], rax
0x18002ed90  test    dword ptr [rcx], 200h
0x18002ed96  mov     r9, rdx
0x18002ed99  mov     rdi, rcx
0x18002ed9c  jz      loc_18002EF6E
0x18002eda2  lea     rsi, [rcx+4]
0x18002eda6  mov     rcx, rsi; pszPath
0x18002eda9  call    cs:__imp_PathFindExtensionW
0x18002edaf  add     rdi, 20Ch
0x18002edb6  mov     rbx, rax
0x18002edb9  mov     rcx, rdi; pszPath
0x18002edbc  call    cs:__imp_PathFindExtensionW
0x18002edc2  mov     rcx, rax; pszStr1
0x18002edc5  mov     rdx, rbx; pszStr2
0x18002edc8  call    cs:__imp_StrCmpICW
0x18002edce  test    eax, eax
0x18002edd0  jz      short loc_18002EDF7
0x18002edd2  mov     edx, 9Fh; void *
0x18002edd7  mov     rcx, [rbp+268h]; this
0x18002edde  lea     r8, aShellCplsAppwz_0; "shell\\cpls\\appwzdui\\link.cpp"
0x18002ede5  mov     ebx, 80070057h
0x18002edea  mov     r9d, ebx; char *
0x18002eded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002edf2  jmp     loc_18002F0F9
0x18002edf7  mov     ebx, 2B8h
0x18002edfc  lea     rcx, [rbp+260h+psfi]; void *
0x18002ee00  mov     r8d, ebx; Size
0x18002ee03  xor     edx, edx; Val
0x18002ee05  call    memset_0
0x18002ee0a  mov     r9d, ebx; cbFileInfo
0x18002ee0d  mov     [rsp+360h+uFlags], 810h; int
0x18002ee15  lea     r8, [rbp+260h+psfi]; psfi
0x18002ee19  mov     edx, 80h; dwFileAttributes
0x18002ee1e  mov     rcx, rdi; pszPath
0x18002ee21  call    cs:__imp_SHGetFileInfoW
0x18002ee27  test    rax, rax
0x18002ee2a  jnz     short loc_18002EE33
0x18002ee2c  mov     edx, 0A2h
0x18002ee31  jmp     short loc_18002EDD7
0x18002ee33  test    [rbp+260h+psfi.dwAttributes], 10000h
0x18002ee3a  jnz     short loc_18002EE43
0x18002ee3c  mov     edx, 0A3h
0x18002ee41  jmp     short loc_18002EDD7
0x18002ee43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56311826@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56311826@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56311826> `wil::Feature<__WilFeatureTraits_Feature_56311826>::GetImpl(void)'::`2'::impl
0x18002ee4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56311826@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56311826>::__private_IsEnabled(void)
0x18002ee4f  test    al, al
0x18002ee51  jz      loc_18002EF48
0x18002ee57  mov     rdx, rdi
0x18002ee5a  lea     rcx, [rsp+360h+ppv]
0x18002ee5f  call    ?MakeDoubleNullTerminatedString@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; MakeDoubleNullTerminatedString(ushort const *)
0x18002ee64  mov     rdx, rsi
0x18002ee67  lea     rcx, [rsp+360h+var_328]
0x18002ee6c  call    ?MakeDoubleNullTerminatedString@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; MakeDoubleNullTerminatedString(ushort const *)
0x18002ee71  mov     rdx, [rsp+360h+ppv]
0x18002ee76  test    rdx, rdx
0x18002ee79  jz      loc_18002EF2A
0x18002ee7f  mov     rax, [rsp+360h+var_328]
0x18002ee84  test    rax, rax
0x18002ee87  jz      loc_18002EF2A
0x18002ee8d  xorps   xmm0, xmm0
0x18002ee90  xor     ecx, ecx
0x18002ee92  movups  xmmword ptr [rsp+360h+FileOp.pFrom], xmm0
0x18002ee97  mov     [rsp+360h+FileOp.pTo], rax
0x18002ee9c  mov     eax, 414h
0x18002eea1  mov     [rsp+360h+FileOp.lpszProgressTitle], rcx
0x18002eea6  lea     rcx, [rsp+360h+FileOp]; lpFileOp
0x18002eeab  movups  xmmword ptr [rsp+360h+FileOp.hwnd], xmm0
0x18002eeb0  mov     [rsp+360h+FileOp.wFunc], 2
0x18002eeb8  movups  xmmword ptr [rsp+360h+FileOp.fFlags], xmm0
0x18002eebd  mov     [rsp+360h+FileOp.fFlags], ax
0x18002eec2  mov     [rsp+360h+FileOp.pFrom], rdx
0x18002eec7  call    cs:__imp_SHFileOperationW
0x18002eecd  mov     ebx, eax
0x18002eecf  test    eax, eax
0x18002eed1  jnz     short loc_18002EEE6
0x18002eed3  cmp     [rsp+360h+FileOp.fAnyOperationsAborted], eax
0x18002eed7  jnz     short loc_18002EEF3
0x18002eed9  mov     rcx, rsi; pszPath
0x18002eedc  call    cs:__imp_PathFileExistsW
0x18002eee2  test    eax, eax
0x18002eee4  jnz     short loc_18002EF14
0x18002eee6  test    ebx, ebx
0x18002eee8  jle     short loc_18002EEF5
0x18002eeea  movzx   ebx, bx
0x18002eeed  or      ebx, 80070000h
0x18002eef3  test    ebx, ebx
0x18002eef5  jns     short loc_18002EF14
0x18002eef7  mov     rcx, [rbp+268h]; this
0x18002eefe  lea     r8, aShellCplsAppwz_0; "shell\\cpls\\appwzdui\\link.cpp"
0x18002ef05  mov     r9d, ebx; char *
0x18002ef08  mov     edx, 0C3h; void *
0x18002ef0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef12  jmp     short loc_18002EF2F
0x18002ef14  lea     rcx, [rsp+360h+var_328]
0x18002ef19  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ef1e  lea     rcx, [rsp+360h+ppv]
0x18002ef23  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ef28  jmp     short loc_18002EF5B
0x18002ef2a  mov     ebx, 8007000Eh
0x18002ef2f  lea     rcx, [rsp+360h+var_328]
0x18002ef34  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ef39  lea     rcx, [rsp+360h+ppv]
0x18002ef3e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ef43  jmp     loc_18002F0F9
0x18002ef48  xor     r8d, r8d; bFailIfExists
0x18002ef4b  mov     rdx, rsi; lpNewFileName
0x18002ef4e  mov     rcx, rdi; lpExistingFileName
0x18002ef51  call    cs:__imp_CopyFileW
0x18002ef57  test    eax, eax
0x18002ef59  jz      short loc_18002EF62
0x18002ef5b  xor     ebx, ebx
0x18002ef5d  jmp     loc_18002F0F9
0x18002ef62  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ef67  mov     ebx, eax
0x18002ef69  jmp     loc_18002F0F9
0x18002ef6e  mov     [rsp+360h+var_328], 0
0x18002ef77  mov     esi, 1
0x18002ef7c  test    r9, r9
0x18002ef7f  jz      short loc_18002EFA2
0x18002ef81  mov     rax, [rdx]
0x18002ef84  lea     r8, [rsp+360h+var_328]
0x18002ef89  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18002ef90  mov     rcx, r9
0x18002ef93  mov     rax, [rax]
0x18002ef96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef9b  mov     ebx, eax
0x18002ef9d  jmp     loc_18002F0CA
0x18002efa2  lea     rax, [rsp+360h+ppv]
0x18002efa7  mov     [rsp+360h+ppv], 0
0x18002efb0  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18002efb7  mov     qword ptr [rsp+360h+uFlags], rax; ppv
0x18002efbc  mov     r8d, esi; dwClsContext
0x18002efbf  lea     rcx, CLSID_ShellLink; rclsid
0x18002efc6  xor     edx, edx; pUnkOuter
0x18002efc8  call    cs:__imp_CoCreateInstance
0x18002efce  mov     ebx, eax
0x18002efd0  test    eax, eax
0x18002efd2  js      loc_18002F0F9
0x18002efd8  mov     rcx, [rsp+360h+ppv]
0x18002efdd  lea     r8, [rsp+360h+var_320]
0x18002efe2  mov     [rsp+360h+var_320], 0
0x18002efeb  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x18002eff2  mov     rax, [rcx]
0x18002eff5  mov     rax, [rax]
0x18002eff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002effd  test    eax, eax
0x18002efff  js      short loc_18002F028
0x18002f001  mov     rcx, [rsp+360h+var_320]
0x18002f006  mov     edx, 80000h
0x18002f00b  mov     rax, [rcx]
0x18002f00e  mov     rax, [rax+38h]
0x18002f012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f017  mov     rcx, [rsp+360h+var_320]
0x18002f01c  mov     rax, [rcx]
0x18002f01f  mov     rax, [rax+10h]
0x18002f023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f028  mov     rcx, [rsp+360h+ppv]
0x18002f02d  lea     rdx, [rdi+20Ch]
0x18002f034  mov     rax, [rcx]
0x18002f037  mov     rax, [rax+0A0h]
0x18002f03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f043  mov     rcx, [rsp+360h+ppv]
0x18002f048  lea     rdx, [rdi+414h]
0x18002f04f  mov     rax, [rcx]
0x18002f052  mov     rax, [rax+58h]
0x18002f056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f05b  mov     rcx, [rsp+360h+ppv]
0x18002f060  lea     rdx, [rdi+61Ch]
0x18002f067  mov     rax, [rcx]
0x18002f06a  mov     rax, [rax+48h]
0x18002f06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f073  test    byte ptr [rdi], 4
0x18002f076  jz      short loc_18002F09B
0x18002f078  mov     rcx, [rsp+360h+ppv]
0x18002f07d  lea     rdx, [rdi+124Ch]
0x18002f084  movzx   r8d, word ptr [rdi+1454h]
0x18002f08c  mov     rax, [rcx]
0x18002f08f  mov     rax, [rax+88h]
0x18002f096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f09b  mov     rcx, [rsp+360h+ppv]
0x18002f0a0  lea     r8, [rsp+360h+var_328]
0x18002f0a5  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18002f0ac  mov     rax, [rcx]
0x18002f0af  mov     rax, [rax]
0x18002f0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0b7  mov     rcx, [rsp+360h+ppv]
0x18002f0bc  mov     ebx, eax
0x18002f0be  mov     rax, [rcx]
0x18002f0c1  mov     rax, [rax+10h]
0x18002f0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0ca  test    ebx, ebx
0x18002f0cc  js      short loc_18002F0F9
0x18002f0ce  mov     rcx, [rsp+360h+var_328]
0x18002f0d3  lea     rdx, [rdi+4]
0x18002f0d7  mov     r8d, esi
0x18002f0da  mov     rax, [rcx]
0x18002f0dd  mov     rax, [rax+30h]
0x18002f0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0e6  mov     rcx, [rsp+360h+var_328]
0x18002f0eb  mov     ebx, eax
0x18002f0ed  mov     rax, [rcx]
0x18002f0f0  mov     rax, [rax+10h]
0x18002f0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0f9  mov     eax, ebx
0x18002f0fb  mov     rcx, [rbp+260h+var_20]
0x18002f102  xor     rcx, rsp; StackCookie
0x18002f105  call    __security_check_cookie
0x18002f10a  mov     rbx, [rsp+360h+arg_10]
0x18002f112  add     rsp, 350h
0x18002f119  pop     rdi
0x18002f11a  pop     rsi
0x18002f11b  pop     rbp
0x18002f11c  retn
```
