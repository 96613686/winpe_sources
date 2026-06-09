# CDPComAFSUserSettings::GetUserEnvironment(char const *,char * *)

- ea: `0x18001dc90`
- end: `0x18001ddef`
- name: `?GetUserEnvironment@CDPComAFSUserSettings@@UEAAJPEBDPEAPEAD@Z`
- size: `351`
- prototype: `__int64 __fastcall(CDPComAFSUserSettings *__hidden this, const char *, char **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004928`
- `0x18000e9c8`
- `0x180018ecc`
- `0x18001dc90`
- `0x18001ddf8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dd5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dd5c`
- `cdp!CDPCreateAFSUserSettingsInternal` at `0x18001dd06`
- `cdp!CDPCreateAFSUserSettingsInternal` at `0x18001dd06`

## string_xrefs

- `0x18001dcc1`: `.\cdpcomafsusersettings.cpp`
- `0x18001dd23`: `.\cdpcomafsusersettings.cpp`
- `0x18001dd85`: `.\cdpcomafsusersettings.cpp`

## pseudocode

```c
__int64 __fastcall CDPComAFSUserSettings::GetUserEnvironment(CDPComAFSUserSettings *this, const char *a2, char **a3)
{
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rax
  const char *v10; // rsi
  __int64 v11; // rcx
  unsigned __int64 v12; // rbx
  char *v13; // rax
  int v14; // edx
  int v15; // ecx
  unsigned int v16; // ebx
  int v17; // eax
  char *v18; // r10
  char *v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+68h] [rbp+28h] BYREF
  int v22; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 )
  {
    v21 = -2147024809;
    v22 = 21;
LABEL_3:
    Log<long &,char const (&)[28],int>(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)&v21,
      (unsigned int)".\\cdpcomafsusersettings.cpp",
      (__int64)&v22);
    return v21;
  }
  if ( !a3 )
  {
    v21 = -2147467261;
    v22 = 22;
    goto LABEL_3;
  }
  v20 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
  v6 = CDPCreateAFSUserSettingsInternal(a2, &v20);
  if ( v6 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
    v10 = (const char *)v9;
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v12 = v11 + 1;
    v13 = (char *)CoTaskMemAlloc(v11 + 1);
    v19 = v13;
    if ( v13 )
    {
      v17 = StringCchCopyA(v13, v12, v10);
      if ( v17 >= 0 )
      {
        v19 = 0;
        *a3 = v18;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v19);
        v16 = 0;
        goto LABEL_17;
      }
      v21 = v17;
      v22 = 33;
    }
    else
    {
      v21 = -2147024882;
      v22 = 32;
    }
    Log<long &,char const (&)[28],int>(
      v15,
      v14,
      (unsigned int)&v21,
      (unsigned int)".\\cdpcomafsusersettings.cpp",
      (__int64)&v22);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v19);
  }
  else
  {
    v21 = v6;
    v22 = 25;
    Log<long &,char const (&)[28],int>(
      v8,
      v7,
      (unsigned int)&v21,
      (unsigned int)".\\cdpcomafsusersettings.cpp",
      (__int64)&v22);
  }
  v16 = v21;
LABEL_17:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
  return v16;
}

```

## disassembly

```asm
0x18001dc90  mov     [rsp-18h+arg_0], rbx
0x18001dc95  push    rbp
0x18001dc96  push    rsi
0x18001dc97  push    rdi
0x18001dc98  mov     rbp, rsp
0x18001dc9b  sub     rsp, 40h
0x18001dc9f  mov     rdi, r8
0x18001dca2  mov     rbx, rdx
0x18001dca5  test    rdx, rdx
0x18001dca8  jnz     short loc_18001DCD9
0x18001dcaa  mov     [rbp+arg_8], 80070057h
0x18001dcb1  mov     [rbp+arg_18], 15h
0x18001dcb8  lea     rax, [rbp+arg_18]
0x18001dcbc  mov     [rsp+40h+var_20], rax
0x18001dcc1  lea     r9, aCdpcomafsusers; ".\\cdpcomafsusersettings.cpp"
0x18001dcc8  lea     r8, [rbp+arg_8]
0x18001dccc  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18001dcd1  mov     eax, [rbp+arg_8]
0x18001dcd4  jmp     loc_18001DDE2
0x18001dcd9  test    rdi, rdi
0x18001dcdc  jnz     short loc_18001DCEE
0x18001dcde  mov     [rbp+arg_8], 80004003h
0x18001dce5  mov     [rbp+arg_18], 16h
0x18001dcec  jmp     short loc_18001DCB8
0x18001dcee  mov     [rbp+var_8], 0
0x18001dcf6  lea     rcx, [rbp+var_8]
0x18001dcfa  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001dcff  lea     rdx, [rbp+var_8]
0x18001dd03  mov     rcx, rbx
0x18001dd06  call    cs:__imp_CDPCreateAFSUserSettingsInternal
0x18001dd0c  test    eax, eax
0x18001dd0e  jns     short loc_18001DD35
0x18001dd10  mov     [rbp+arg_8], eax
0x18001dd13  mov     [rbp+arg_18], 19h
0x18001dd1a  lea     rax, [rbp+arg_18]
0x18001dd1e  mov     [rsp+40h+var_20], rax
0x18001dd23  lea     r9, aCdpcomafsusers; ".\\cdpcomafsusersettings.cpp"
0x18001dd2a  lea     r8, [rbp+arg_8]
0x18001dd2e  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18001dd33  jmp     short loc_18001DD9E
0x18001dd35  mov     rcx, [rbp+var_8]
0x18001dd39  mov     rax, [rcx]
0x18001dd3c  mov     rax, [rax+18h]
0x18001dd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd45  mov     rsi, rax
0x18001dd48  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001dd4c  inc     rcx
0x18001dd4f  cmp     byte ptr [rax+rcx], 0
0x18001dd53  jnz     short loc_18001DD4C
0x18001dd55  lea     rbx, [rcx+1]
0x18001dd59  mov     rcx, rbx; cb
0x18001dd5c  call    cs:__imp_CoTaskMemAlloc
0x18001dd62  mov     r10, rax
0x18001dd65  mov     [rbp+var_10], rax
0x18001dd69  test    rax, rax
0x18001dd6c  jnz     short loc_18001DDA3
0x18001dd6e  mov     [rbp+arg_8], 8007000Eh
0x18001dd75  mov     [rbp+arg_18], 20h ; ' '
0x18001dd7c  lea     rax, [rbp+arg_18]
0x18001dd80  mov     [rsp+40h+var_20], rax
0x18001dd85  lea     r9, aCdpcomafsusers; ".\\cdpcomafsusersettings.cpp"
0x18001dd8c  lea     r8, [rbp+arg_8]
0x18001dd90  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18001dd95  lea     rcx, [rbp+var_10]
0x18001dd99  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001dd9e  mov     ebx, [rbp+arg_8]
0x18001dda1  jmp     short loc_18001DDD7
0x18001dda3  mov     r8, rsi; char *
0x18001dda6  mov     rdx, rbx; unsigned __int64
0x18001dda9  mov     rcx, r10; char *
0x18001ddac  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001ddb1  test    eax, eax
0x18001ddb3  jns     short loc_18001DDC1
0x18001ddb5  mov     [rbp+arg_8], eax
0x18001ddb8  mov     [rbp+arg_18], 21h ; '!'
0x18001ddbf  jmp     short loc_18001DD7C
0x18001ddc1  mov     [rbp+var_10], 0
0x18001ddc9  mov     [rdi], r10
0x18001ddcc  lea     rcx, [rbp+var_10]
0x18001ddd0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001ddd5  xor     ebx, ebx
0x18001ddd7  lea     rcx, [rbp+var_8]
0x18001dddb  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001dde0  mov     eax, ebx
0x18001dde2  mov     rbx, [rsp+40h+arg_0]
0x18001dde7  add     rsp, 40h
0x18001ddeb  pop     rdi
0x18001ddec  pop     rsi
0x18001dded  pop     rbp
0x18001ddee  retn
```
