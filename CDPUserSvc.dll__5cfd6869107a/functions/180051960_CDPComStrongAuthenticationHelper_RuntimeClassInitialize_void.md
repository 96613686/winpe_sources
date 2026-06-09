# CDPComStrongAuthenticationHelper::RuntimeClassInitialize(void)

- ea: `0x180051960`
- end: `0x180051b98`
- name: `?RuntimeClassInitialize@CDPComStrongAuthenticationHelper@@QEAAJXZ`
- size: `568`
- prototype: `__int64 __fastcall(CDPComStrongAuthenticationHelper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180057b9c`

## callees

- `0x180003678`
- `0x180020cc4`
- `0x180051830`
- `0x180051960`
- `0x180051ba0`
- `0x18005cbbc`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180051a2b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180051a2b`
- `cdp!CDPGetAccountProviderInternal` at `0x180051a98`
- `cdp!CDPGetAccountProviderInternal` at `0x180051a98`

## string_xrefs

- `0x1800519ed`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x180051a52`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x180051abe`: `..\cdpcomstrongauthenticationhelper.cpp`
- `0x180051b3f`: `..\cdpcomstrongauthenticationhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDPComStrongAuthenticationHelper::RuntimeClassInitialize(CDPComStrongAuthenticationHelper *this)
{
  unsigned __int16 **v2; // rdx
  int CallingAppIdUsingImpersonation; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, char *); // rdi
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, char *); // rax
  LPCWCH lpString1; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+38h] [rbp-30h]
  __int64 v20; // [rsp+40h] [rbp-28h]
  unsigned int v21; // [rsp+78h] [rbp+10h] BYREF
  int v22; // [rsp+80h] [rbp+18h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, char *); // [rsp+88h] [rbp+20h] BYREF

  lpString1 = 0;
  v19 = 0;
  v20 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  v19 = -1;
  v20 = -1;
  try
  {
    if ( (unsigned int)CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&lpString1, v2) == -2147024891
      && (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1),
          v19 = -1,
          v20 = -1,
          CallingAppIdUsingImpersonation = GetCallingAppIdUsingImpersonation(&lpString1),
          CallingAppIdUsingImpersonation < 0) )
    {
      v21 = CallingAppIdUsingImpersonation;
      v22 = 56;
      Log<long &,char const (&)[40],int>(v5, v4, &v21, "..\\cdpcomstrongauthenticationhelper.cpp", &v22);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      result = v21;
    }
    else if ( CompareStringOrdinal(
                lpString1,
                -1,
                L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
                -1,
                1) == 2 )
    {
      v23 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      v9 = CDPGetAccountProviderInternal(&v23);
      if ( v9 >= 0 )
      {
        v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
        v13 = **v23;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
        v14 = v13(v12, &GUID_2c843c51_2dcc_4471_88d0_1de9a29e7124, (char *)this + 24);
        if ( v14 >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
          result = 0;
        }
        else
        {
          v21 = v14;
          v22 = 64;
          Log<long &,char const (&)[40],int>(v16, v15, &v21, "..\\cdpcomstrongauthenticationhelper.cpp", &v22);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
          result = v21;
        }
      }
      else
      {
        v21 = v9;
        v22 = 63;
        Log<long &,char const (&)[40],int>(v11, v10, &v21, "..\\cdpcomstrongauthenticationhelper.cpp", &v22);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
        result = v21;
      }
    }
    else
    {
      v21 = -2147024891;
      v22 = 60;
      Log<long &,char const (&)[40],int>(v8, v7, &v21, "..\\cdpcomstrongauthenticationhelper.cpp", &v22);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
      result = v21;
    }
  }
  catch ( ... )
  {
    v21 = -2147418113;
    LODWORD(v17) = GetCurrentThreadId();
    v23 = v17;
    v22 = 68;
    cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
      (__int64)&v21,
      (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
      (__int64)"..\\cdpcomstrongauthenticationhelper.cpp",
      (__int64)&v22,
      (__int64)&v23);
  }
  return result;
}

```

## disassembly

```asm
0x180051960  mov     rax, rsp
0x180051963  push    rbx
0x180051964  push    rsi
0x180051965  push    rdi
0x180051966  sub     rsp, 50h
0x18005196a  mov     rsi, rcx
0x18005196d  mov     qword ptr [rax-38h], 0
0x180051975  mov     qword ptr [rax-30h], 0
0x18005197d  mov     qword ptr [rax-28h], 0
0x180051985  lea     rcx, [rax-38h]
0x180051989  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005198e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180051992  mov     [rsp+68h+var_30], rbx
0x180051997  mov     [rsp+68h+var_28], rbx
0x18005199c  lea     rcx, [rsp+68h+lpString1]; this
0x1800519a1  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x1800519a6  mov     edi, 80070005h
0x1800519ab  cmp     eax, edi
0x1800519ad  jnz     short loc_180051A12
0x1800519af  lea     rcx, [rsp+68h+lpString1]
0x1800519b4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800519b9  mov     [rsp+68h+var_30], rbx
0x1800519be  mov     [rsp+68h+var_28], rbx
0x1800519c3  lea     rcx, [rsp+68h+lpString1]; void *
0x1800519c8  call    GetCallingAppIdUsingImpersonation
0x1800519cd  test    eax, eax
0x1800519cf  jns     short loc_180051A12
0x1800519d1  mov     [rsp+68h+arg_8], eax
0x1800519d5  mov     [rsp+68h+arg_10], 38h ; '8'
0x1800519e0  lea     rax, [rsp+68h+arg_10]
0x1800519e8  mov     qword ptr [rsp+68h+bIgnoreCase], rax
0x1800519ed  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x1800519f4  lea     r8, [rsp+68h+arg_8]
0x1800519f9  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800519fe  nop
0x1800519ff  lea     rcx, [rsp+68h+lpString1]
0x180051a04  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180051a09  mov     eax, [rsp+68h+arg_8]
0x180051a0d  jmp     loc_180051B8F
0x180051a12  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180051a1a  mov     r9d, ebx; cchCount2
0x180051a1d  lea     r8, ?c_szPCSettingsAppID@@3QBGB; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x180051a24  mov     edx, ebx; cchCount1
0x180051a26  mov     rcx, [rsp+68h+lpString1]; lpString1
0x180051a2b  call    cs:__imp_CompareStringOrdinal
0x180051a31  cmp     eax, 2
0x180051a34  jz      short loc_180051A77
0x180051a36  mov     [rsp+68h+arg_8], edi
0x180051a3a  mov     [rsp+68h+arg_10], 3Ch ; '<'
0x180051a45  lea     rax, [rsp+68h+arg_10]
0x180051a4d  mov     qword ptr [rsp+68h+bIgnoreCase], rax
0x180051a52  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x180051a59  lea     r8, [rsp+68h+arg_8]
0x180051a5e  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180051a63  nop
0x180051a64  lea     rcx, [rsp+68h+lpString1]
0x180051a69  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180051a6e  mov     eax, [rsp+68h+arg_8]
0x180051a72  jmp     loc_180051B8F
0x180051a77  mov     [rsp+68h+arg_18], 0
0x180051a83  lea     rcx, [rsp+68h+arg_18]
0x180051a8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051a90  lea     rcx, [rsp+68h+arg_18]
0x180051a98  call    cs:__imp_CDPGetAccountProviderInternal
0x180051a9e  test    eax, eax
0x180051aa0  jns     short loc_180051AF1
0x180051aa2  mov     [rsp+68h+arg_8], eax
0x180051aa6  mov     [rsp+68h+arg_10], 3Fh ; '?'
0x180051ab1  lea     rax, [rsp+68h+arg_10]
0x180051ab9  mov     qword ptr [rsp+68h+bIgnoreCase], rax
0x180051abe  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x180051ac5  lea     r8, [rsp+68h+arg_8]
0x180051aca  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180051acf  nop
0x180051ad0  lea     rcx, [rsp+68h+arg_18]
0x180051ad8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051add  nop
0x180051ade  lea     rcx, [rsp+68h+lpString1]
0x180051ae3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180051ae8  mov     eax, [rsp+68h+arg_8]
0x180051aec  jmp     loc_180051B8F
0x180051af1  mov     rbx, [rsp+68h+arg_18]
0x180051af9  mov     rax, [rbx]
0x180051afc  mov     rdi, [rax]
0x180051aff  lea     rcx, [rsi+18h]
0x180051b03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051b08  lea     r8, [rsi+18h]
0x180051b0c  lea     rdx, _GUID_2c843c51_2dcc_4471_88d0_1de9a29e7124
0x180051b13  mov     rcx, rbx
0x180051b16  mov     rax, rdi
0x180051b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b1e  nop
0x180051b1f  test    eax, eax
0x180051b21  jns     short loc_180051B6F
0x180051b23  mov     [rsp+68h+arg_8], eax
0x180051b27  mov     [rsp+68h+arg_10], 40h ; '@'
0x180051b32  lea     rax, [rsp+68h+arg_10]
0x180051b3a  mov     qword ptr [rsp+68h+bIgnoreCase], rax
0x180051b3f  lea     r9, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x180051b46  lea     r8, [rsp+68h+arg_8]
0x180051b4b  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180051b50  nop
0x180051b51  lea     rcx, [rsp+68h+arg_18]
0x180051b59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051b5e  nop
0x180051b5f  lea     rcx, [rsp+68h+lpString1]
0x180051b64  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180051b69  mov     eax, [rsp+68h+arg_8]
0x180051b6d  jmp     short loc_180051B8F
0x180051b6f  lea     rcx, [rsp+68h+arg_18]
0x180051b77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051b7c  nop
0x180051b7d  lea     rcx, [rsp+68h+lpString1]
0x180051b82  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180051b87  xor     eax, eax
0x180051b89  jmp     short loc_180051B8F
0x180051b8b  mov     eax, [rsp+68h+arg_8]
0x180051b8f  add     rsp, 50h
0x180051b93  pop     rdi
0x180051b94  pop     rsi
0x180051b95  pop     rbx
0x180051b96  retn
```
