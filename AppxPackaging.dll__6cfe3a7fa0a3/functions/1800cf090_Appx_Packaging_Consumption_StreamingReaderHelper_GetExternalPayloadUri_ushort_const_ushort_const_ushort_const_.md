# Appx::Packaging::Consumption::StreamingReaderHelper::GetExternalPayloadUri(ushort const *,ushort const *,ushort const *,Common::StringBuffer &)

- ea: `0x1800cf090`
- end: `0x1800cf330`
- name: `?GetExternalPayloadUri@StreamingReaderHelper@Consumption@Packaging@Appx@@SAJPEBG00AEAVStringBuffer@Common@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const char **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180023590`
- `0x1800932b0`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180029ad0`
- `0x18002a224`
- `0x180039ef0`
- `0x1800446d0`
- `0x1800c97ec`
- `0x1800cef74`
- `0x1800cf090`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800cf2b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800cf304`
- `OLEAUT32!__imp_SysFreeString` at `0x1800cf2b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800cf304`
- `urlmon!CreateUri` at `0x1800cf110`
- `urlmon!CreateUri` at `0x1800cf110`

## string_xrefs

- `0x1800cf0da`: `onecore\printscan\appxpackaging\consumption\src\streamingreaderhelper.cpp`
- `0x1800cf126`: `onecore\printscan\appxpackaging\consumption\src\streamingreaderhelper.cpp`
- `0x1800cf243`: `onecore\printscan\appxpackaging\consumption\src\streamingreaderhelper.cpp`
- `0x1800cf2a4`: `onecore\printscan\appxpackaging\consumption\src\streamingreaderhelper.cpp`
- `0x1800cf2d6`: `onecore\printscan\appxpackaging\consumption\src\streamingreaderhelper.cpp`
- `0x1800cf1a1`: `x-windowsupdate`
- `0x1800cf0c6`: `No bundle source uri specified; unable to get package from flat bundle`
- `0x1800cf231`: `Scheme does not support getting a package from outside the bundle`
- `0x1800cf2e7`: `Improperly formed Uri %ws`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::StreamingReaderHelper::GetExternalPayloadUri(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const char **a4)
{
  unsigned int v8; // ebx
  HRESULT v9; // eax
  int appended; // eax
  __int64 v11; // rdx
  int v12; // edx
  int v14; // [rsp+20h] [rbp-30h]
  char *v15; // [rsp+28h] [rbp-28h]
  IUri *ppURI; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v17[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  BSTR bstrString; // [rsp+80h] [rbp+30h] BYREF
  const unsigned __int16 *v20; // [rsp+90h] [rbp+40h] BYREF

  v20 = a3;
  Appx::Packaging::AppxPackagingProvider::FlatBundle<unsigned short const * &>(&v20);
  if ( a1 )
  {
    ppURI = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
    v9 = CreateUri(a1, 0x100u, 0, &ppURI);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\streamingreaderhelper.cpp",
        (const char *)(unsigned int)v9,
        v14);
LABEL_29:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
      return v8;
    }
    bstrString = 0;
    appended = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &bstrString);
    v8 = appended;
    if ( appended >= 0 )
    {
      v17[1] = a4;
      v17[0] = &Common::StringBufferBuilder::`vftable';
      v17[2] = a4;
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v17, a1);
      v8 = appended;
      if ( appended >= 0 )
      {
        if ( Common::String::CaseInsensitiveEquals(bstrString, L"x-windowsupdate") )
        {
          appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v17, L"?PFun=");
          v8 = appended;
          if ( appended < 0 )
          {
            v11 = 310;
            goto LABEL_25;
          }
          appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v17, a3);
          v8 = appended;
          if ( appended < 0 )
          {
            v11 = 311;
            goto LABEL_25;
          }
        }
        else
        {
          if ( !Common::String::CaseInsensitiveEquals(bstrString, L"file")
            && !Common::String::CaseInsensitiveEquals(bstrString, L"http")
            && !Common::String::CaseInsensitiveEquals(bstrString, L"https") )
          {
            v8 = wil::details::in1diag3::Return_Win32Msg(
                   retaddr,
                   (void *)0x145,
                   (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\streamingreaderhelper.cpp",
                   (const char *)0x32,
                   (unsigned int)"Scheme does not support getting a package from outside the bundle",
                   v15);
LABEL_28:
            SysFreeString(bstrString);
            goto LABEL_29;
          }
          v12 = *(_DWORD *)a4;
          do
          {
            if ( --v12 < 0 )
            {
              v8 = -2147024809;
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x13F,
                (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\streamingreaderhelper.cpp",
                (const char *)0x80070057LL,
                (int)"Improperly formed Uri %ws",
                a4[1]);
              goto LABEL_28;
            }
          }
          while ( *(_WORD *)&a4[1][2 * v12] != 47 );
          appended = Common::StringBufferBuilder::SetLength((Common::StringBufferBuilder *)v17, v12 + 1);
          v8 = appended;
          if ( appended < 0 )
          {
            v11 = 320;
            goto LABEL_25;
          }
          appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v17, a2);
          v8 = appended;
          if ( appended < 0 )
          {
            v11 = 321;
            goto LABEL_25;
          }
        }
        SysFreeString(bstrString);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
        return 0;
      }
      v11 = 305;
    }
    else
    {
      v11 = 302;
    }
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\streamingreaderhelper.cpp",
      (const char *)(unsigned int)appended,
      v14);
    goto LABEL_28;
  }
  v8 = -2147024846;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x129,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\streamingreaderhelper.cpp",
    (const char *)0x80070032LL,
    (int)"No bundle source uri specified; unable to get package from flat bundle",
    v15);
  return v8;
}

```

## disassembly

```asm
0x1800cf090  mov     [rsp-28h+arg_8], rbx
0x1800cf095  mov     [rsp-28h+arg_10], r8
0x1800cf09a  push    rbp
0x1800cf09b  push    rsi
0x1800cf09c  push    rdi
0x1800cf09d  push    r14
0x1800cf09f  push    r15
0x1800cf0a1  mov     rbp, rsp
0x1800cf0a4  sub     rsp, 50h
0x1800cf0a8  mov     rsi, rcx
0x1800cf0ab  mov     rdi, r9
0x1800cf0ae  lea     rcx, [rbp+arg_10]
0x1800cf0b2  mov     r14, r8
0x1800cf0b5  mov     r15, rdx
0x1800cf0b8  call    ??$FlatBundle@AEAPEBG@AppxPackagingProvider@Packaging@Appx@@SAXAEAPEBG@Z; Appx::Packaging::AppxPackagingProvider::FlatBundle<ushort const * &>(ushort const * &)
0x1800cf0bd  test    rsi, rsi
0x1800cf0c0  jnz     short loc_1800CF0F0
0x1800cf0c2  mov     rcx, [rbp+28h]; this
0x1800cf0c6  lea     rax, aNoBundleSource; "No bundle source uri specified; unable "...
0x1800cf0cd  mov     ebx, 80070032h
0x1800cf0d2  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800cf0d7  mov     r9d, ebx; char *
0x1800cf0da  lea     r8, aOnecorePrintsc_185; "onecore\\printscan\\appxpackaging\\cons"...
0x1800cf0e1  mov     edx, 129h; void *
0x1800cf0e6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800cf0eb  jmp     loc_1800CF319
0x1800cf0f0  lea     rcx, [rbp+ppURI]
0x1800cf0f4  mov     [rbp+ppURI], 0
0x1800cf0fc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800cf101  lea     r9, [rbp+ppURI]; ppURI
0x1800cf105  xor     r8d, r8d; dwReserved
0x1800cf108  mov     edx, 100h; dwFlags
0x1800cf10d  mov     rcx, rsi; pwzURI
0x1800cf110  call    cs:__imp_CreateUri
0x1800cf117  nop     dword ptr [rax+rax+00h]
0x1800cf11c  mov     ebx, eax
0x1800cf11e  test    eax, eax
0x1800cf120  jns     short loc_1800CF13F
0x1800cf122  mov     rcx, [rbp+28h]; this
0x1800cf126  lea     r8, aOnecorePrintsc_185; "onecore\\printscan\\appxpackaging\\cons"...
0x1800cf12d  mov     r9d, eax; char *
0x1800cf130  mov     edx, 12Ch; void *
0x1800cf135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf13a  jmp     loc_1800CF310
0x1800cf13f  mov     rcx, [rbp+ppURI]
0x1800cf143  lea     rdx, [rbp+bstrString]
0x1800cf147  mov     [rbp+bstrString], 0
0x1800cf14f  mov     rax, [rcx]
0x1800cf152  mov     rax, [rax+98h]
0x1800cf159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf15e  mov     ebx, eax
0x1800cf160  test    eax, eax
0x1800cf162  jns     short loc_1800CF16E
0x1800cf164  mov     edx, 12Eh
0x1800cf169  jmp     loc_1800CF2A0
0x1800cf16e  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800cf175  mov     [rbp+var_10], rdi
0x1800cf179  mov     rdx, rsi; unsigned __int16 *
0x1800cf17c  mov     [rbp+var_18], rax
0x1800cf180  lea     rcx, [rbp+var_18]; this
0x1800cf184  mov     [rbp+var_8], rdi
0x1800cf188  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800cf18d  mov     ebx, eax
0x1800cf18f  test    eax, eax
0x1800cf191  jns     short loc_1800CF19D
0x1800cf193  mov     edx, 131h
0x1800cf198  jmp     loc_1800CF2A0
0x1800cf19d  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x1800cf1a1  lea     rdx, aXWindowsupdate; "x-windowsupdate"
0x1800cf1a8  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800cf1ad  test    eax, eax
0x1800cf1af  jz      short loc_1800CF1F1
0x1800cf1b1  lea     rdx, aPfun; "?PFun="
0x1800cf1b8  lea     rcx, [rbp+var_18]; this
0x1800cf1bc  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800cf1c1  mov     ebx, eax
0x1800cf1c3  test    eax, eax
0x1800cf1c5  jns     short loc_1800CF1D1
0x1800cf1c7  mov     edx, 136h
0x1800cf1cc  jmp     loc_1800CF2A0
0x1800cf1d1  mov     rdx, r14; unsigned __int16 *
0x1800cf1d4  lea     rcx, [rbp+var_18]; this
0x1800cf1d8  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800cf1dd  mov     ebx, eax
0x1800cf1df  test    eax, eax
0x1800cf1e1  jns     loc_1800CF2B5
0x1800cf1e7  mov     edx, 137h
0x1800cf1ec  jmp     loc_1800CF2A0
0x1800cf1f1  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x1800cf1f5  lea     rdx, aFile; "file"
0x1800cf1fc  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800cf201  test    eax, eax
0x1800cf203  jnz     short loc_1800CF25B
0x1800cf205  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x1800cf209  lea     rdx, aHttp; "http"
0x1800cf210  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800cf215  test    eax, eax
0x1800cf217  jnz     short loc_1800CF25B
0x1800cf219  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x1800cf21d  lea     rdx, aHttps; "https"
0x1800cf224  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800cf229  test    eax, eax
0x1800cf22b  jnz     short loc_1800CF25B
0x1800cf22d  mov     rcx, [rbp+28h]; this
0x1800cf231  lea     rax, aSchemeDoesNotS; "Scheme does not support getting a packa"...
0x1800cf238  mov     r9d, 32h ; '2'; char *
0x1800cf23e  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x1800cf243  lea     r8, aOnecorePrintsc_185; "onecore\\printscan\\appxpackaging\\cons"...
0x1800cf24a  mov     edx, 145h; void *
0x1800cf24f  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800cf254  mov     ebx, eax
0x1800cf256  jmp     loc_1800CF300
0x1800cf25b  mov     edx, [rdi]
0x1800cf25d  mov     rax, [rdi+8]
0x1800cf261  dec     edx
0x1800cf263  test    edx, edx
0x1800cf265  js      short loc_1800CF2D2
0x1800cf267  movsxd  rcx, edx
0x1800cf26a  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x1800cf26f  jnz     short loc_1800CF25D
0x1800cf271  inc     edx; unsigned int
0x1800cf273  lea     rcx, [rbp+var_18]; this
0x1800cf277  call    ?SetLength@StringBufferBuilder@Common@@UEAAJK@Z; Common::StringBufferBuilder::SetLength(ulong)
0x1800cf27c  mov     ebx, eax
0x1800cf27e  test    eax, eax
0x1800cf280  jns     short loc_1800CF289
0x1800cf282  mov     edx, 140h
0x1800cf287  jmp     short loc_1800CF2A0
0x1800cf289  mov     rdx, r15; unsigned __int16 *
0x1800cf28c  lea     rcx, [rbp+var_18]; this
0x1800cf290  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800cf295  mov     ebx, eax
0x1800cf297  test    eax, eax
0x1800cf299  jns     short loc_1800CF2B5
0x1800cf29b  mov     edx, 141h; void *
0x1800cf2a0  mov     rcx, [rbp+28h]; this
0x1800cf2a4  lea     r8, aOnecorePrintsc_185; "onecore\\printscan\\appxpackaging\\cons"...
0x1800cf2ab  mov     r9d, eax; char *
0x1800cf2ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf2b3  jmp     short loc_1800CF300
0x1800cf2b5  mov     rcx, [rbp+bstrString]; bstrString
0x1800cf2b9  call    cs:__imp_SysFreeString
0x1800cf2c0  nop     dword ptr [rax+rax+00h]
0x1800cf2c5  lea     rcx, [rbp+ppURI]
0x1800cf2c9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800cf2ce  xor     eax, eax
0x1800cf2d0  jmp     short loc_1800CF31B
0x1800cf2d2  mov     rcx, [rbp+28h]; this
0x1800cf2d6  lea     r8, aOnecorePrintsc_185; "onecore\\printscan\\appxpackaging\\cons"...
0x1800cf2dd  mov     [rsp+50h+var_28], rax; char *
0x1800cf2e2  mov     ebx, 80070057h
0x1800cf2e7  lea     rax, aImproperlyForm; "Improperly formed Uri %ws"
0x1800cf2ee  mov     r9d, ebx; char *
0x1800cf2f1  mov     edx, 13Fh; void *
0x1800cf2f6  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800cf2fb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800cf300  mov     rcx, [rbp+bstrString]; bstrString
0x1800cf304  call    cs:__imp_SysFreeString
0x1800cf30b  nop     dword ptr [rax+rax+00h]
0x1800cf310  lea     rcx, [rbp+ppURI]
0x1800cf314  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800cf319  mov     eax, ebx
0x1800cf31b  mov     rbx, [rsp+50h+arg_8]
0x1800cf323  add     rsp, 50h
0x1800cf327  pop     r15
0x1800cf329  pop     r14
0x1800cf32b  pop     rdi
0x1800cf32c  pop     rsi
0x1800cf32d  pop     rbp
0x1800cf32e  retn
```
