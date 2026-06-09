# NetworkAdapter::SetNetworkAdapter(_GUID const &,NetworkAdapterCommand,ushort const *)

- ea: `0x14003aa1c`
- end: `0x14003aec8`
- name: `?SetNetworkAdapter@NetworkAdapter@@SAJAEBU_GUID@@W4NetworkAdapterCommand@@PEBG@Z`
- size: `1196`
- prototype: `static int __high(const struct _GUID *, enum NetworkAdapterCommand, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f5a8`

## callees

- `0x140005f30`
- `0x140011b68`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x140036ce0`
- `0x140038464`
- `0x14003aa1c`
- `0x14007d010`

## import_xrefs

- `ole32!CoUninitialize` at `0x14003aac1`
- `ole32!CoUninitialize` at `0x14003ab3f`
- `ole32!CoUninitialize` at `0x14003abda`
- `ole32!CoUninitialize` at `0x14003ac4d`
- `ole32!CoUninitialize` at `0x14003ace9`
- `ole32!CoUninitialize` at `0x14003ad6d`
- `ole32!CoUninitialize` at `0x14003adf0`
- `ole32!CoUninitialize` at `0x14003ae5f`
- `ole32!CoUninitialize` at `0x14003ae97`
- `ole32!CoUninitialize` at `0x14003aac1`
- `ole32!CoUninitialize` at `0x14003ab3f`
- `ole32!CoUninitialize` at `0x14003abda`
- `ole32!CoUninitialize` at `0x14003ac4d`
- `ole32!CoUninitialize` at `0x14003ace9`
- `ole32!CoUninitialize` at `0x14003ad6d`
- `ole32!CoUninitialize` at `0x14003adf0`
- `ole32!CoUninitialize` at `0x14003ae5f`
- `ole32!CoUninitialize` at `0x14003ae97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ac61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003acb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ad34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ad7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ac61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003acb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ad34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ad7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003ac82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003ac82`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall NetworkAdapter::SetNetworkAdapter(_OWORD *a1, int a2, const WCHAR *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  char v8; // cl
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  char v14; // al
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING_HEADER *, __int64 *); // rbx
  int v17; // eax
  unsigned int v18; // ebx
  char v19; // al
  int v20; // esi
  char v21; // cl
  __int64 v22; // rdx
  HRESULT v23; // eax
  unsigned int v24; // ebx
  char v25; // al
  int v26; // eax
  unsigned int v27; // ebx
  char v28; // al
  int v29; // eax
  unsigned int v30; // ebx
  char v31; // al
  int v32; // eax
  unsigned int v33; // ebx
  char v34; // al
  char v35; // al
  int v36; // [rsp+20h] [rbp-78h] BYREF
  __int64 v37; // [rsp+28h] [rbp-70h] BYREF
  __int64 v38; // [rsp+30h] [rbp-68h] BYREF
  __int64 v39; // [rsp+38h] [rbp-60h] BYREF
  HSTRING_HEADER string; // [rsp+40h] [rbp-58h] BYREF
  __int64 v41; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  wil::CoInitializeEx(&v36);
  v39 = 0;
  v41 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&string, L"Windows.Networking.UX.UXManager", 0x20u, 0x1Fu);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(v41, &v39);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
      (const char *)(unsigned int)v6,
      v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v8 = v36;
    LOBYTE(v36) = 0;
    if ( v8 )
      CoUninitialize();
    return v7;
  }
  v38 = 0;
  v10 = v39;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  v12 = v11(v10, &v38);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
      (const char *)(unsigned int)v12,
      v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v14 = v36;
    LOBYTE(v36) = 0;
    if ( v14 )
      CoUninitialize();
    return v13;
  }
  v37 = 0;
  v15 = v38;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *))(*(_QWORD *)v38 + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  *(_OWORD *)&string.Reserved.Reserved1 = *a1;
  v17 = v16(v15, &string, &v37);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
      (const char *)(unsigned int)v17,
      v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v19 = v36;
    LOBYTE(v36) = 0;
    if ( v19 )
      CoUninitialize();
    return v18;
  }
  if ( a2 )
  {
    v20 = a2 - 1;
    if ( v20 )
    {
      if ( v20 != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
          (const char *)0x80070057LL,
          v36);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        v21 = v36;
        LOBYTE(v36) = 0;
        if ( v21 )
          CoUninitialize();
        return 2147942487LL;
      }
      string.Reserved.Reserved1 = 0;
      WindowsDeleteString(0);
      string.Reserved.Reserved1 = 0;
      v22 = -1;
      do
        ++v22;
      while ( a3[v22] );
      v23 = WindowsCreateString(a3, v22, (HSTRING *)&string);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x25,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
          (const char *)(unsigned int)v23,
          v36);
        WindowsDeleteString((HSTRING)string.Reserved.Reserved1);
        string.Reserved.Reserved1 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        v25 = v36;
        LOBYTE(v36) = 0;
        if ( v25 )
          CoUninitialize();
        return v24;
      }
      v26 = (*(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v37 + 88LL))(v37, string.Reserved.Reserved1);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
          (const char *)(unsigned int)v26,
          v36);
        WindowsDeleteString((HSTRING)string.Reserved.Reserved1);
        string.Reserved.Reserved1 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        v28 = v36;
        LOBYTE(v36) = 0;
        if ( v28 )
          CoUninitialize();
        return v27;
      }
      WindowsDeleteString((HSTRING)string.Reserved.Reserved1);
      goto LABEL_38;
    }
    v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 104LL))(v37);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
        (const char *)(unsigned int)v29,
        v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v31 = v36;
      LOBYTE(v36) = 0;
      if ( v31 )
        CoUninitialize();
      return v30;
    }
LABEL_38:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v35 = v36;
    LOBYTE(v36) = 0;
    if ( v35 )
      CoUninitialize();
    return 0;
  }
  v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 96LL))(v37);
  v33 = v32;
  if ( v32 >= 0 )
    goto LABEL_38;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D,
    (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\networkadapter\\networkadapter.cpp",
    (const char *)(unsigned int)v32,
    v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  v34 = v36;
  LOBYTE(v36) = 0;
  if ( v34 )
    CoUninitialize();
  return v33;
}

```

## disassembly

```asm
0x14003aa1c  mov     [rsp+arg_8], rbx
0x14003aa21  push    rsi
0x14003aa22  push    rdi
0x14003aa23  push    r12
0x14003aa25  push    r14
0x14003aa27  push    r15
0x14003aa29  sub     rsp, 70h
0x14003aa2d  mov     rax, cs:__security_cookie
0x14003aa34  xor     rax, rsp
0x14003aa37  mov     [rsp+98h+var_38], rax
0x14003aa3c  mov     r14, r8
0x14003aa3f  mov     esi, edx
0x14003aa41  mov     r15, rcx
0x14003aa44  lea     rcx, [rsp+98h+var_78]
0x14003aa49  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x14003aa4e  nop
0x14003aa4f  xor     r12d, r12d
0x14003aa52  mov     [rsp+98h+var_60], r12
0x14003aa57  mov     [rsp+98h+var_40], r12
0x14003aa5c  lea     r9d, [r12+1Fh]; unsigned int
0x14003aa61  lea     r8d, [r12+20h]; unsigned int
0x14003aa66  lea     rdx, ?RuntimeClass_Windows_Networking_UX_UXManager@@3QBGB; "Windows.Networking.UX.UXManager"
0x14003aa6d  lea     rcx, [rsp+98h+string]; hstringHeader
0x14003aa72  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14003aa77  lea     rdx, [rsp+98h+var_60]
0x14003aa7c  mov     rcx, [rsp+98h+var_40]
0x14003aa81  call    ??$ActivateInstance@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUXManager@UX@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::IUXManager>>)
0x14003aa86  mov     ebx, eax
0x14003aa88  test    eax, eax
0x14003aa8a  jns     short loc_14003AACE
0x14003aa8c  mov     rcx, [rsp+98h]; this
0x14003aa94  mov     r9d, eax; char *
0x14003aa97  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003aa9e  lea     edx, [r12+12h]; void *
0x14003aaa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003aaa8  nop
0x14003aaa9  lea     rcx, [rsp+98h+var_60]
0x14003aaae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003aab3  nop
0x14003aab4  mov     cl, byte ptr [rsp+98h+var_78]
0x14003aab8  mov     byte ptr [rsp+98h+var_78], r12b
0x14003aabd  test    cl, cl
0x14003aabf  jz      short loc_14003AAC7
0x14003aac1  call    cs:__imp_CoUninitialize
0x14003aac7  mov     eax, ebx
0x14003aac9  jmp     loc_14003AEA5
0x14003aace  mov     [rsp+98h+var_68], r12
0x14003aad3  mov     rdi, [rsp+98h+var_60]
0x14003aad8  mov     rax, [rdi]
0x14003aadb  mov     rbx, [rax+30h]
0x14003aadf  lea     rcx, [rsp+98h+var_68]
0x14003aae4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003aae9  lea     rdx, [rsp+98h+var_68]
0x14003aaee  mov     rcx, rdi
0x14003aaf1  mov     rax, rbx
0x14003aaf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aaf9  mov     ebx, eax
0x14003aafb  test    eax, eax
0x14003aafd  jns     short loc_14003AB4C
0x14003aaff  mov     rcx, [rsp+98h]; this
0x14003ab07  mov     r9d, eax; char *
0x14003ab0a  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003ab11  mov     edx, 15h; void *
0x14003ab16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ab1b  nop
0x14003ab1c  lea     rcx, [rsp+98h+var_68]
0x14003ab21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ab26  nop
0x14003ab27  lea     rcx, [rsp+98h+var_60]
0x14003ab2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ab31  nop
0x14003ab32  mov     al, byte ptr [rsp+98h+var_78]
0x14003ab36  mov     byte ptr [rsp+98h+var_78], r12b
0x14003ab3b  test    al, al
0x14003ab3d  jz      short loc_14003AB45
0x14003ab3f  call    cs:__imp_CoUninitialize
0x14003ab45  mov     eax, ebx
0x14003ab47  jmp     loc_14003AEA5
0x14003ab4c  mov     [rsp+98h+var_70], r12
0x14003ab51  mov     rdi, [rsp+98h+var_68]
0x14003ab56  mov     rax, [rdi]
0x14003ab59  mov     rbx, [rax+90h]
0x14003ab60  lea     rcx, [rsp+98h+var_70]
0x14003ab65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ab6a  movups  xmm0, xmmword ptr [r15]
0x14003ab6e  movdqu  xmmword ptr [rsp+98h+string], xmm0
0x14003ab74  lea     r8, [rsp+98h+var_70]
0x14003ab79  lea     rdx, [rsp+98h+string]
0x14003ab7e  mov     rcx, rdi
0x14003ab81  mov     rax, rbx
0x14003ab84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ab89  mov     ebx, eax
0x14003ab8b  test    eax, eax
0x14003ab8d  jns     short loc_14003ABE7
0x14003ab8f  mov     rcx, [rsp+98h]; this
0x14003ab97  mov     r9d, eax; char *
0x14003ab9a  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003aba1  mov     edx, 18h; void *
0x14003aba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003abab  nop
0x14003abac  lea     rcx, [rsp+98h+var_70]
0x14003abb1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003abb6  nop
0x14003abb7  lea     rcx, [rsp+98h+var_68]
0x14003abbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003abc1  nop
0x14003abc2  lea     rcx, [rsp+98h+var_60]
0x14003abc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003abcc  nop
0x14003abcd  mov     al, byte ptr [rsp+98h+var_78]
0x14003abd1  mov     byte ptr [rsp+98h+var_78], r12b
0x14003abd6  test    al, al
0x14003abd8  jz      short loc_14003ABE0
0x14003abda  call    cs:__imp_CoUninitialize
0x14003abe0  mov     eax, ebx
0x14003abe2  jmp     loc_14003AEA5
0x14003abe7  test    esi, esi
0x14003abe9  jz      loc_14003ADFD
0x14003abef  sub     esi, 1
0x14003abf2  jz      loc_14003AD8A
0x14003abf8  cmp     esi, 1
0x14003abfb  jz      short loc_14003AC5A
0x14003abfd  mov     rcx, [rsp+98h]; this
0x14003ac05  mov     ebx, 80070057h
0x14003ac0a  mov     r9d, ebx; char *
0x14003ac0d  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003ac14  mov     edx, 2Ah ; '*'; void *
0x14003ac19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ac1e  nop
0x14003ac1f  lea     rcx, [rsp+98h+var_70]
0x14003ac24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ac29  nop
0x14003ac2a  lea     rcx, [rsp+98h+var_68]
0x14003ac2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ac34  nop
0x14003ac35  lea     rcx, [rsp+98h+var_60]
0x14003ac3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ac3f  nop
0x14003ac40  mov     cl, byte ptr [rsp+98h+var_78]
0x14003ac44  mov     byte ptr [rsp+98h+var_78], r12b
0x14003ac49  test    cl, cl
0x14003ac4b  jz      short loc_14003AC53
0x14003ac4d  call    cs:__imp_CoUninitialize
0x14003ac53  mov     eax, ebx
0x14003ac55  jmp     loc_14003AEA5
0x14003ac5a  mov     qword ptr [rsp+98h+string], r12
0x14003ac5f  xor     ecx, ecx; string
0x14003ac61  call    cs:__imp_WindowsDeleteString
0x14003ac67  mov     qword ptr [rsp+98h+string], r12
0x14003ac6c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003ac70  inc     rdx; length
0x14003ac73  cmp     [r14+rdx*2], r12w
0x14003ac78  jnz     short loc_14003AC70
0x14003ac7a  lea     r8, [rsp+98h+string]; string
0x14003ac7f  mov     rcx, r14; sourceString
0x14003ac82  call    cs:__imp_WindowsCreateString
0x14003ac88  mov     ebx, eax
0x14003ac8a  test    eax, eax
0x14003ac8c  jns     short loc_14003ACF6
0x14003ac8e  mov     rcx, [rsp+98h]; this
0x14003ac96  mov     r9d, eax; char *
0x14003ac99  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003aca0  mov     edx, 25h ; '%'; void *
0x14003aca5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003acaa  nop
0x14003acab  mov     rcx, qword ptr [rsp+98h+string]; string
0x14003acb0  call    cs:__imp_WindowsDeleteString
0x14003acb6  mov     qword ptr [rsp+98h+string], r12
0x14003acbb  lea     rcx, [rsp+98h+var_70]
0x14003acc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003acc5  nop
0x14003acc6  lea     rcx, [rsp+98h+var_68]
0x14003accb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003acd0  nop
0x14003acd1  lea     rcx, [rsp+98h+var_60]
0x14003acd6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003acdb  nop
0x14003acdc  mov     al, byte ptr [rsp+98h+var_78]
0x14003ace0  mov     byte ptr [rsp+98h+var_78], r12b
0x14003ace5  test    al, al
0x14003ace7  jz      short loc_14003ACEF
0x14003ace9  call    cs:__imp_CoUninitialize
0x14003acef  mov     eax, ebx
0x14003acf1  jmp     loc_14003AEA5
0x14003acf6  mov     rcx, [rsp+98h+var_70]
0x14003acfb  mov     rax, [rcx]
0x14003acfe  mov     rdx, qword ptr [rsp+98h+string]
0x14003ad03  mov     rax, [rax+58h]
0x14003ad07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ad0c  mov     ebx, eax
0x14003ad0e  test    eax, eax
0x14003ad10  jns     short loc_14003AD7A
0x14003ad12  mov     rcx, [rsp+98h]; this
0x14003ad1a  mov     r9d, eax; char *
0x14003ad1d  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003ad24  mov     edx, 26h ; '&'; void *
0x14003ad29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ad2e  nop
0x14003ad2f  mov     rcx, qword ptr [rsp+98h+string]; string
0x14003ad34  call    cs:__imp_WindowsDeleteString
0x14003ad3a  mov     qword ptr [rsp+98h+string], r12
0x14003ad3f  lea     rcx, [rsp+98h+var_70]
0x14003ad44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ad49  nop
0x14003ad4a  lea     rcx, [rsp+98h+var_68]
0x14003ad4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ad54  nop
0x14003ad55  lea     rcx, [rsp+98h+var_60]
0x14003ad5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ad5f  nop
0x14003ad60  mov     al, byte ptr [rsp+98h+var_78]
0x14003ad64  mov     byte ptr [rsp+98h+var_78], r12b
0x14003ad69  test    al, al
0x14003ad6b  jz      short loc_14003AD73
0x14003ad6d  call    cs:__imp_CoUninitialize
0x14003ad73  mov     eax, ebx
0x14003ad75  jmp     loc_14003AEA5
0x14003ad7a  mov     rcx, qword ptr [rsp+98h+string]; string
0x14003ad7f  call    cs:__imp_WindowsDeleteString
0x14003ad85  jmp     loc_14003AE69
0x14003ad8a  mov     rcx, [rsp+98h+var_70]
0x14003ad8f  mov     rax, [rcx]
0x14003ad92  mov     rax, [rax+68h]
0x14003ad96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ad9b  mov     ebx, eax
0x14003ad9d  test    eax, eax
0x14003ad9f  jns     loc_14003AE69
0x14003ada5  mov     rcx, [rsp+98h]; this
0x14003adad  mov     r9d, eax; char *
0x14003adb0  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003adb7  mov     edx, 20h ; ' '; void *
0x14003adbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003adc1  nop
0x14003adc2  lea     rcx, [rsp+98h+var_70]
0x14003adc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003adcc  nop
0x14003adcd  lea     rcx, [rsp+98h+var_68]
0x14003add2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003add7  nop
0x14003add8  lea     rcx, [rsp+98h+var_60]
0x14003addd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ade2  nop
0x14003ade3  mov     al, byte ptr [rsp+98h+var_78]
0x14003ade7  mov     byte ptr [rsp+98h+var_78], r12b
0x14003adec  test    al, al
0x14003adee  jz      short loc_14003ADF6
0x14003adf0  call    cs:__imp_CoUninitialize
0x14003adf6  mov     eax, ebx
0x14003adf8  jmp     loc_14003AEA5
0x14003adfd  mov     rcx, [rsp+98h+var_70]
0x14003ae02  mov     rax, [rcx]
0x14003ae05  mov     rax, [rax+60h]
0x14003ae09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ae0e  mov     ebx, eax
0x14003ae10  test    eax, eax
0x14003ae12  jns     short loc_14003AE69
0x14003ae14  mov     rcx, [rsp+98h]; this
0x14003ae1c  mov     r9d, eax; char *
0x14003ae1f  lea     r8, aPcshellShellSy_17; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003ae26  mov     edx, 1Dh; void *
0x14003ae2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ae30  nop
0x14003ae31  lea     rcx, [rsp+98h+var_70]
0x14003ae36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ae3b  nop
0x14003ae3c  lea     rcx, [rsp+98h+var_68]
0x14003ae41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ae46  nop
0x14003ae47  lea     rcx, [rsp+98h+var_60]
0x14003ae4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ae51  nop
0x14003ae52  mov     al, byte ptr [rsp+98h+var_78]
0x14003ae56  mov     byte ptr [rsp+98h+var_78], r12b
0x14003ae5b  test    al, al
0x14003ae5d  jz      short loc_14003AE65
0x14003ae5f  call    cs:__imp_CoUninitialize
0x14003ae65  mov     eax, ebx
0x14003ae67  jmp     short loc_14003AEA5
0x14003ae69  lea     rcx, [rsp+98h+var_70]
0x14003ae6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ae73  nop
0x14003ae74  lea     rcx, [rsp+98h+var_68]
0x14003ae79  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ae7e  nop
0x14003ae7f  lea     rcx, [rsp+98h+var_60]
0x14003ae84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003ae89  nop
0x14003ae8a  mov     al, byte ptr [rsp+98h+var_78]
0x14003ae8e  mov     byte ptr [rsp+98h+var_78], r12b
0x14003ae93  test    al, al
0x14003ae95  jz      short loc_14003AE9D
0x14003ae97  call    cs:__imp_CoUninitialize
0x14003ae9d  xor     eax, eax
0x14003ae9f  jmp     short loc_14003AEA5
0x14003aea1  mov     eax, dword ptr [rsp+98h+var_70]
0x14003aea5  mov     rcx, [rsp+98h+var_38]
0x14003aeaa  xor     rcx, rsp; StackCookie
0x14003aead  call    __security_check_cookie
0x14003aeb2  mov     rbx, [rsp+98h+arg_8]
0x14003aeba  add     rsp, 70h
  ... truncated ...
```
