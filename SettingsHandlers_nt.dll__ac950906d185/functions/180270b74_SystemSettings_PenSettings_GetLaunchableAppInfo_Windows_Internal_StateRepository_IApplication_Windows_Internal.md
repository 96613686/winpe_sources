# SystemSettings::PenSettings::GetLaunchableAppInfo(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationResourceResolverStatics *,SystemSettings::PenSettings::AppInfo *)

- ea: `0x180270b74`
- end: `0x180270e25`
- name: `?GetLaunchableAppInfo@PenSettings@SystemSettings@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAUIApplicationResourceResolverStatics@456@PEAUAppInfo@12@@Z`
- size: `689`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings *__hidden this, struct Windows::Internal::StateRepository::IApplication *, struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *, struct SystemSettings::PenSettings::AppInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180214f8c`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x18002395c`
- `0x180270b74`
- `0x180270e94`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270bf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270ca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270ced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270da4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270e14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270bf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270ca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270ced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270da4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270dc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180270e14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180270d86`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::PenSettings::GetLaunchableAppInfo(
        SystemSettings::PenSettings *this,
        struct Windows::Internal::StateRepository::IApplication *a2,
        struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *a3,
        struct SystemSettings::PenSettings::AppInfo *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  char v10; // r15
  bool v11; // al
  __int64 (__fastcall *v12)(SystemSettings::PenSettings *, HSTRING *); // rbx
  int v13; // eax
  __int64 (__fastcall *v14)(struct Windows::Internal::StateRepository::IApplication *, SystemSettings::PenSettings *, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  SystemSettings::PenSettings *StringRawBuffer; // rax
  const unsigned __int16 *v20; // rdx
  PCWSTR v21; // rax
  unsigned __int64 v22; // rcx
  PCWSTR v23; // rax
  PCWSTR v24; // rax
  const char *v25; // r9
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  __int64 v27; // [rsp+28h] [rbp-40h] BYREF
  HSTRING v28[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v30; // [rsp+70h] [rbp+8h] BYREF
  __int64 v31; // [rsp+88h] [rbp+20h]

  v30 = 0;
  v7 = (*(__int64 (__fastcall **)(SystemSettings::PenSettings *, int *, struct Windows::Internal::StateRepository::IApplicationResourceResolverStatics *, struct SystemSettings::PenSettings::AppInfo *))(*(_QWORD *)this + 528LL))(
         this,
         &v30,
         a3,
         a4);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\pen\\lib\\penblocklist.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    return v8;
  }
  v10 = 1;
  v11 = v30 != 1;
  *((_BYTE *)a3 + 64) = v30 != 1;
  if ( v11 )
  {
    v28[0] = 0;
    v12 = *(__int64 (__fastcall **)(SystemSettings::PenSettings *, HSTRING *))(*(_QWORD *)this + 232LL);
    WindowsDeleteString(0);
    v28[0] = 0;
    v13 = v12(this, v28);
    v8 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\pen\\lib\\penblocklist.cpp",
        (const char *)(unsigned int)v13,
        (int)string);
LABEL_23:
      WindowsDeleteString(v28[0]);
      return v8;
    }
    v27 = 0;
    v14 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IApplication *, SystemSettings::PenSettings *, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    v15 = v14(a2, this, &v27);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\pen\\lib\\penblocklist.cpp",
        (const char *)(unsigned int)v15,
        (int)string);
LABEL_9:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      goto LABEL_23;
    }
    string = 0;
    v16 = v27;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v18 = v17(v16, &string);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\pen\\lib\\penblocklist.cpp",
        (const char *)(unsigned int)v18,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_9;
    }
    StringRawBuffer = (SystemSettings::PenSettings *)WindowsGetStringRawBuffer(v28[0], 0);
    if ( SystemSettings::PenSettings::IsBlockedAumid(StringRawBuffer, v20) )
      goto LABEL_19;
    v21 = WindowsGetStringRawBuffer(string, 0);
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    if ( v22 >= 3 && *v21 == 64 && v21[1] == 123 && v21[v22 - 1] == 125 )
LABEL_19:
      v10 = 0;
    *((_BYTE *)a3 + 64) = v10;
    try
    {
      v23 = WindowsGetStringRawBuffer(v28[0], 0);
      std::wstring::assign(a3, v23);
      v24 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::assign((char *)a3 + 32, v24);
    }
    catch ( ... )
    {
      LODWORD(v31) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x3D,
                       (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\pen\\lib\\penblocklist.cpp",
                       v25);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      v8 = v31;
      goto LABEL_23;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    WindowsDeleteString(v28[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x180270b74  mov     [rsp+arg_8], rbx
0x180270b79  push    rsi
0x180270b7a  push    rdi
0x180270b7b  push    r12
0x180270b7d  push    r14
0x180270b7f  push    r15
0x180270b81  sub     rsp, 40h
0x180270b85  mov     r14, r8
0x180270b88  mov     r12, rdx
0x180270b8b  mov     rdi, rcx
0x180270b8e  xor     esi, esi
0x180270b90  mov     [rsp+68h+arg_0], esi
0x180270b94  mov     rax, [rcx]
0x180270b97  lea     rdx, [rsp+68h+arg_0]
0x180270b9c  mov     rax, [rax+210h]
0x180270ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270ba8  mov     ebx, eax
0x180270baa  test    eax, eax
0x180270bac  jns     short loc_180270BCC
0x180270bae  mov     rcx, [rsp+68h]; this
0x180270bb3  mov     r9d, eax; char *
0x180270bb6  lea     r8, aShellSystemset_96; "shell\\systemsettingsthreshold\\handler"...
0x180270bbd  lea     edx, [rsi+27h]; void *
0x180270bc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270bc5  mov     eax, ebx
0x180270bc7  jmp     loc_180270DD3
0x180270bcc  mov     r15d, 1
0x180270bd2  cmp     [rsp+68h+arg_0], r15d
0x180270bd7  setnz   al
0x180270bda  mov     [r14+40h], al
0x180270bde  test    al, al
0x180270be0  jz      loc_180270DD1
0x180270be6  mov     [rsp+68h+var_38], rsi
0x180270beb  mov     rax, [rdi]
0x180270bee  mov     rbx, [rax+0E8h]
0x180270bf5  xor     ecx, ecx; string
0x180270bf7  call    cs:__imp_WindowsDeleteString
0x180270bfe  nop     dword ptr [rax+rax+00h]
0x180270c03  mov     [rsp+68h+var_38], rsi
0x180270c08  lea     rdx, [rsp+68h+var_38]
0x180270c0d  mov     rcx, rdi
0x180270c10  mov     rax, rbx
0x180270c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270c18  mov     ebx, eax
0x180270c1a  test    eax, eax
0x180270c1c  jns     short loc_180270C3B
0x180270c1e  mov     rcx, [rsp+68h]; this
0x180270c23  mov     r9d, eax; char *
0x180270c26  lea     r8, aShellSystemset_96; "shell\\systemsettingsthreshold\\handler"...
0x180270c2d  lea     edx, [r15+2Ch]; void *
0x180270c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270c36  jmp     loc_180270E0F
0x180270c3b  mov     [rsp+68h+var_40], rsi
0x180270c40  mov     rax, [r12]
0x180270c44  mov     rbx, [rax+30h]
0x180270c48  lea     rcx, [rsp+68h+var_40]
0x180270c4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180270c52  lea     r8, [rsp+68h+var_40]
0x180270c57  mov     rdx, rdi
0x180270c5a  mov     rcx, r12
0x180270c5d  mov     rax, rbx
0x180270c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270c65  mov     ebx, eax
0x180270c67  test    eax, eax
0x180270c69  jns     short loc_180270C94
0x180270c6b  mov     rcx, [rsp+68h]; this
0x180270c70  mov     r9d, eax; char *
0x180270c73  lea     r8, aShellSystemset_96; "shell\\systemsettingsthreshold\\handler"...
0x180270c7a  mov     edx, 31h ; '1'; void *
0x180270c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270c84  nop
0x180270c85  lea     rcx, [rsp+68h+var_40]
0x180270c8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180270c8f  jmp     loc_180270E0F
0x180270c94  mov     [rsp+68h+string], rsi
0x180270c99  mov     rdi, [rsp+68h+var_40]
0x180270c9e  mov     rax, [rdi]
0x180270ca1  mov     rbx, [rax+30h]
0x180270ca5  xor     ecx, ecx; string
0x180270ca7  call    cs:__imp_WindowsDeleteString
0x180270cae  nop     dword ptr [rax+rax+00h]
0x180270cb3  mov     [rsp+68h+string], rsi; int
0x180270cb8  lea     rdx, [rsp+68h+string]
0x180270cbd  mov     rcx, rdi
0x180270cc0  mov     rax, rbx
0x180270cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180270cc8  mov     ebx, eax
0x180270cca  test    eax, eax
0x180270ccc  jns     short loc_180270D00
0x180270cce  mov     rcx, [rsp+68h]; this
0x180270cd3  mov     r9d, eax; char *
0x180270cd6  lea     r8, aShellSystemset_96; "shell\\systemsettingsthreshold\\handler"...
0x180270cdd  mov     edx, 33h ; '3'; void *
0x180270ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270ce7  nop
0x180270ce8  mov     rcx, [rsp+68h+string]; string
0x180270ced  call    cs:__imp_WindowsDeleteString
0x180270cf4  nop     dword ptr [rax+rax+00h]
0x180270cf9  mov     [rsp+68h+string], rsi
0x180270cfe  jmp     short loc_180270C85
0x180270d00  xor     edx, edx; length
0x180270d02  mov     rcx, [rsp+68h+var_38]; string
0x180270d07  call    cs:__imp_WindowsGetStringRawBuffer
0x180270d0e  nop     dword ptr [rax+rax+00h]
0x180270d13  mov     rcx, rax; this
0x180270d16  call    ?IsBlockedAumid@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsBlockedAumid(ushort const *)
0x180270d1b  test    al, al
0x180270d1d  jnz     short loc_180270D5A
0x180270d1f  xor     edx, edx; length
0x180270d21  mov     rcx, [rsp+68h+string]; string
0x180270d26  call    cs:__imp_WindowsGetStringRawBuffer
0x180270d2d  nop     dword ptr [rax+rax+00h]
0x180270d32  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180270d36  inc     rcx
0x180270d39  cmp     [rax+rcx*2], si
0x180270d3d  jnz     short loc_180270D36
0x180270d3f  cmp     rcx, 3
0x180270d43  jb      short loc_180270D5D
0x180270d45  cmp     word ptr [rax], 40h ; '@'
0x180270d49  jnz     short loc_180270D5D
0x180270d4b  cmp     word ptr [rax+2], 7Bh ; '{'
0x180270d50  jnz     short loc_180270D5D
0x180270d52  cmp     word ptr [rax+rcx*2-2], 7Dh ; '}'
0x180270d58  jnz     short loc_180270D5D
0x180270d5a  mov     r15b, sil
0x180270d5d  mov     [r14+40h], r15b
0x180270d61  xor     edx, edx; length
0x180270d63  mov     rcx, [rsp+68h+var_38]; string
0x180270d68  call    cs:__imp_WindowsGetStringRawBuffer
0x180270d6f  nop     dword ptr [rax+rax+00h]
0x180270d74  mov     rdx, rax
0x180270d77  mov     rcx, r14
0x180270d7a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180270d7f  xor     edx, edx; length
0x180270d81  mov     rcx, [rsp+68h+string]; string
0x180270d86  call    cs:__imp_WindowsGetStringRawBuffer
0x180270d8d  nop     dword ptr [rax+rax+00h]
0x180270d92  lea     rcx, [r14+20h]
0x180270d96  mov     rdx, rax
0x180270d99  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180270d9e  nop
0x180270d9f  mov     rcx, [rsp+68h+string]; string
0x180270da4  call    cs:__imp_WindowsDeleteString
0x180270dab  nop     dword ptr [rax+rax+00h]
0x180270db0  mov     [rsp+68h+string], rsi
0x180270db5  lea     rcx, [rsp+68h+var_40]
0x180270dba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180270dbf  nop
0x180270dc0  mov     rcx, [rsp+68h+var_38]; string
0x180270dc5  call    cs:__imp_WindowsDeleteString
0x180270dcc  nop     dword ptr [rax+rax+00h]
0x180270dd1  xor     eax, eax
0x180270dd3  mov     rbx, [rsp+68h+arg_8]
0x180270dd8  add     rsp, 40h
0x180270ddc  pop     r15
0x180270dde  pop     r14
0x180270de0  pop     r12
0x180270de2  pop     rdi
0x180270de3  pop     rsi
0x180270de4  retn
0x180270de6  mov     rcx, [rsp+68h+string]; string
0x180270deb  call    cs:__imp_WindowsDeleteString
0x180270df2  nop     dword ptr [rax+rax+00h]
0x180270df7  xor     esi, esi
0x180270df9  mov     [rsp+68h+string], rsi
0x180270dfe  lea     rcx, [rsp+68h+var_40]
0x180270e03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180270e08  mov     ebx, dword ptr [rsp+68h+arg_18]
0x180270e0f  mov     rcx, [rsp+68h+var_38]; string
0x180270e14  call    cs:__imp_WindowsDeleteString
0x180270e1b  nop     dword ptr [rax+rax+00h]
0x180270e20  jmp     loc_180270BC5
```
