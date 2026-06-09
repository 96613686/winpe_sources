# Execution::ActivationManagerShim::ActivateApplication(ushort const *,ushort const *,ACTIVATEOPTIONS,ulong *)

- ea: `0x180028c20`
- end: `0x180029021`
- name: `?ActivateApplication@ActivationManagerShim@Execution@@UEAAJPEBG0W4ACTIVATEOPTIONS@@PEAK@Z`
- size: `1025`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, enum ACTIVATEOPTIONS, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180023620`
- `0x180028c20`
- `0x180029028`
- `0x180029270`
- `0x18004a91c`
- `0x18004f090`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028d77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028dd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028e98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028ef0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028fee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029004`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002901a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028d77`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028dd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028e98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028ef0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028fee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029004`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002901a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028fd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028e5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028fd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028d60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028e82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028eda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028d60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028e82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028eda`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x180028cc2`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x180028cc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Execution::ActivationManagerShim::ActivateApplication(
        __int64 a1,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        int a4,
        unsigned int *a5)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int v11; // ecx
  unsigned __int64 v12; // rdi
  const WCHAR *v13; // r12
  unsigned __int64 v14; // rbx
  unsigned int v15; // eax
  UINT32 v16; // edx
  HRESULT v17; // eax
  HSTRING v18; // rcx
  unsigned __int64 v19; // rbx
  unsigned int v20; // eax
  UINT32 v21; // edx
  HRESULT v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r14
  HRESULT v26; // eax
  HSTRING v27; // rbx
  unsigned int v28; // eax
  UINT32 v29; // edx
  HRESULT v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  int v37; // [rsp+7Ch] [rbp-84h]
  PCWSTR sourceString[3]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v39; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v42; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v43; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING string; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER v46; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v47; // [rsp+108h] [rbp+8h] BYREF
  HSTRING_HEADER v48; // [rsp+110h] [rbp+10h] BYREF
  HSTRING v49; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v41 = a1;
  v36 = 0;
  if ( !a5 )
  {
    v8 = 373;
LABEL_3:
    v9 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)v9,
      v33);
    return v9;
  }
  *a5 = 0;
  if ( (a4 & 0x2000007) != a4 )
  {
    v8 = 376;
    goto LABEL_3;
  }
  if ( (a4 & 5) != 0 && ((int)IsDeveloperModeEnabled(&v36) < 0 || !v36) )
  {
    v9 = -2147024891;
    v8 = 378;
    goto LABEL_4;
  }
  v11 = a4 | 0x1000000;
  if ( (a4 & 0x2000000) == 0 )
    v11 = a4;
  v37 = v11;
  sourceString[0] = 0;
  v12 = -1;
  sourceString[1] = (PCWSTR)-1LL;
  sourceString[2] = (PCWSTR)-1LL;
  v13 = a2;
  if ( (int)ParseAppUserModelId(a2, 0, (unsigned __int16 **)sourceString) >= 0 )
    v13 = sourceString[0];
  if ( !a3 )
    a3 = &Src;
  string = 0;
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  if ( v14 > 0xFFFFFFFF )
  {
LABEL_58:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180029020LL);
  }
  v15 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
  v16 = v15 - 1;
  if ( (unsigned int)v14 < v15 )
    v16 = v14;
  v17 = WindowsCreateStringReference(a3, v16, &hstringHeader, &string);
  v18 = 0;
  if ( v17 < 0 )
    RaiseException(v17, 1u, 0, 0);
  v43 = v18;
  v19 = -1;
  do
    ++v19;
  while ( v13[v19] != (_WORD)v18 );
  if ( v19 > 0xFFFFFFFF )
  {
LABEL_57:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_58;
  }
  v20 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v19);
  v21 = v20 - 1;
  if ( (unsigned int)v19 < v20 )
    v21 = v19;
  v22 = WindowsCreateStringReference(v13, v21, &v42, &v43);
  if ( v22 < 0 )
    RaiseException(v22, 1u, 0, 0);
  v35 = 0;
  v39 = v43;
  v40 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
  v23 = Microsoft::WRL::Details::MakeAndInitialize<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,HSTRING__ *,HSTRING__ *>(
          &v35,
          &v40,
          &v39);
  v9 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v23,
      v33);
    v24 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v43 = 0;
    string = 0;
    if ( sourceString[0] )
      CoTaskMemFree((LPVOID)sourceString[0]);
    return v9;
  }
  v25 = v35;
  v47 = 0;
  v26 = WindowsCreateStringReference(L"Windows.Launch", 0xEu, &v46, &v47);
  if ( v26 < 0 )
    RaiseException(v26, 1u, 0, 0);
  v49 = 0;
  do
    ++v12;
  while ( a2[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_57;
  }
  v27 = v47;
  v28 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v29 = v28 - 1;
  if ( (unsigned int)v12 < v28 )
    v29 = v12;
  v30 = WindowsCreateStringReference(a2, v29, &v48, &v49);
  if ( v30 < 0 )
    RaiseException(v30, 1u, 0, 0);
  v31 = Execution::ActivationManagerShim::ActivateApplicationForContractCore(
          v41 - 40,
          v49,
          v27,
          0,
          v37,
          v25,
          0,
          0,
          0,
          0,
          0,
          0,
          a5,
          0);
  v9 = v31;
  if ( v31 >= 0 )
    v9 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v31,
      v34);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)v9,
      v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    v43 = 0;
    string = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
    return v9;
  }
  v32 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v43 = 0;
  string = 0;
  if ( sourceString[0] )
    CoTaskMemFree((LPVOID)sourceString[0]);
  return 0;
}

```

## disassembly

```asm
0x180028c20  push    rbp
0x180028c22  push    rbx
0x180028c23  push    rdi
0x180028c24  push    r12
0x180028c26  push    r13
0x180028c28  push    r14
0x180028c2a  push    r15
0x180028c2c  lea     rbp, [rsp-40h]
0x180028c31  sub     rsp, 140h
0x180028c38  mov     rax, cs:__security_cookie
0x180028c3f  xor     rax, rsp
0x180028c42  mov     [rbp+70h+var_40], rax
0x180028c46  mov     ebx, r9d
0x180028c49  mov     r14, r8
0x180028c4c  mov     r13, rdx
0x180028c4f  mov     [rbp+70h+var_C8], rcx
0x180028c53  mov     r15, [rbp+70h+arg_20]
0x180028c5a  xor     edi, edi
0x180028c5c  mov     [rsp+170h+var_F8], edi
0x180028c60  test    r15, r15
0x180028c63  jnz     short loc_180028CA3
0x180028c65  mov     edx, 175h; void *
0x180028c6a  mov     ebx, 80070057h
0x180028c6f  mov     rcx, [rbp+78h]; this
0x180028c73  mov     r9d, ebx; char *
0x180028c76  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180028c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c82  mov     eax, ebx
0x180028c84  mov     rcx, [rbp+70h+var_40]
0x180028c88  xor     rcx, rsp; StackCookie
0x180028c8b  call    __security_check_cookie
0x180028c90  add     rsp, 140h
0x180028c97  pop     r15
0x180028c99  pop     r14
0x180028c9b  pop     r13
0x180028c9d  pop     r12
0x180028c9f  pop     rdi
0x180028ca0  pop     rbx
0x180028ca1  pop     rbp
0x180028ca2  retn
0x180028ca3  mov     [r15], edi
0x180028ca6  mov     eax, ebx
0x180028ca8  and     eax, 2000007h
0x180028cad  cmp     eax, ebx
0x180028caf  jz      short loc_180028CB8
0x180028cb1  mov     edx, 178h
0x180028cb6  jmp     short loc_180028C6A
0x180028cb8  test    bl, 5
0x180028cbb  jz      short loc_180028CDE
0x180028cbd  lea     rcx, [rsp+170h+var_F8]
0x180028cc2  call    cs:__imp_IsDeveloperModeEnabled
0x180028cc8  test    eax, eax
0x180028cca  js      short loc_180028CD2
0x180028ccc  cmp     [rsp+170h+var_F8], edi
0x180028cd0  jnz     short loc_180028CDE
0x180028cd2  mov     ebx, 80070005h
0x180028cd7  mov     edx, 17Ah
0x180028cdc  jmp     short loc_180028C6F
0x180028cde  mov     ecx, ebx
0x180028ce0  bts     ecx, 18h
0x180028ce4  bt      ebx, 19h
0x180028ce8  cmovnb  ecx, ebx
0x180028ceb  mov     [rsp+170h+var_F4], ecx
0x180028cef  mov     [rbp+70h+sourceString], rdi
0x180028cf3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028cf7  mov     [rbp+70h+var_E8], rdi
0x180028cfb  mov     [rbp+70h+var_E0], rdi
0x180028cff  lea     r8, [rbp+70h+sourceString]; unsigned __int16 **
0x180028d03  xor     edx, edx; unsigned __int16 **
0x180028d05  mov     rcx, r13; unsigned __int16 *
0x180028d08  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x180028d0d  mov     r12, r13
0x180028d10  xor     ecx, ecx
0x180028d12  test    eax, eax
0x180028d14  cmovns  r12, [rbp+70h+sourceString]
0x180028d19  lea     rax, Src
0x180028d20  test    r14, r14
0x180028d23  cmovz   r14, rax
0x180028d27  mov     [rbp+70h+string], rcx
0x180028d2b  mov     rbx, rdi
0x180028d2e  inc     rbx
0x180028d31  cmp     [r14+rbx*2], cx
0x180028d36  jnz     short loc_180028D2E
0x180028d38  mov     eax, 0FFFFFFFFh
0x180028d3d  cmp     rbx, rax
0x180028d40  ja      loc_18002900B
0x180028d46  mov     ecx, ebx; unsigned int
0x180028d48  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180028d4d  lea     edx, [rax-1]
0x180028d50  cmp     ebx, eax
0x180028d52  cmovb   edx, ebx; length
0x180028d55  lea     r9, [rbp+70h+string]; string
0x180028d59  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x180028d5d  mov     rcx, r14; sourceString
0x180028d60  call    cs:__imp_WindowsCreateStringReference
0x180028d66  xor     ecx, ecx
0x180028d68  test    eax, eax
0x180028d6a  jns     short loc_180028D7E
0x180028d6c  xor     r9d, r9d; lpArguments
0x180028d6f  xor     r8d, r8d; nNumberOfArguments
0x180028d72  lea     edx, [rcx+1]; dwExceptionFlags
0x180028d75  mov     ecx, eax; dwExceptionCode
0x180028d77  call    cs:__imp_RaiseException
0x180028d7d  nop
0x180028d7e  mov     [rbp+70h+var_A8], rcx
0x180028d82  mov     rbx, rdi
0x180028d85  inc     rbx
0x180028d88  cmp     [r12+rbx*2], cx
0x180028d8d  jnz     short loc_180028D85
0x180028d8f  mov     eax, 0FFFFFFFFh
0x180028d94  cmp     rbx, rax
0x180028d97  ja      loc_180028FF5
0x180028d9d  mov     ecx, ebx; unsigned int
0x180028d9f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180028da4  lea     edx, [rax-1]
0x180028da7  cmp     ebx, eax
0x180028da9  cmovb   edx, ebx; length
0x180028dac  lea     r9, [rbp+70h+var_A8]; string
0x180028db0  lea     r8, [rbp+70h+var_C0]; hstringHeader
0x180028db4  mov     rcx, r12; sourceString
0x180028db7  call    cs:__imp_WindowsCreateStringReference
0x180028dbd  xor     r12d, r12d
0x180028dc0  test    eax, eax
0x180028dc2  jns     short loc_180028DD8
0x180028dc4  xor     r9d, r9d; lpArguments
0x180028dc7  xor     r8d, r8d; nNumberOfArguments
0x180028dca  lea     edx, [r12+1]; dwExceptionFlags
0x180028dcf  mov     ecx, eax; dwExceptionCode
0x180028dd1  call    cs:__imp_RaiseException
0x180028dd7  nop
0x180028dd8  mov     [rsp+170h+var_100], r12
0x180028ddd  mov     rax, [rbp+70h+var_A8]
0x180028de1  mov     [rbp+70h+var_D8], rax
0x180028de5  mov     rax, [rbp+70h+string]
0x180028de9  mov     [rbp+70h+var_D0], rax
0x180028ded  lea     rcx, [rsp+170h+var_100]
0x180028df2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028df7  lea     r8, [rbp+70h+var_D8]
0x180028dfb  lea     rdx, [rbp+70h+var_D0]
0x180028dff  lea     rcx, [rsp+170h+var_100]
0x180028e04  call    ??$MakeAndInitialize@VCLaunchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUHSTRING__@@PEAU6@@Details@WRL@Microsoft@@YAJPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@$$QEAPEAUHSTRING__@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,HSTRING__ *,HSTRING__ *>(Windows::ApplicationModel::Activation::IActivatedEventArgs * *,HSTRING__ * &&,HSTRING__ * &&)
0x180028e09  mov     ebx, eax
0x180028e0b  test    eax, eax
0x180028e0d  jns     short loc_180028E65
0x180028e0f  mov     rcx, [rbp+78h]; this
0x180028e13  mov     r9d, eax; char *
0x180028e16  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180028e1d  mov     edx, 193h; void *
0x180028e22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028e27  nop
0x180028e28  mov     rcx, [rsp+170h+var_100]
0x180028e2d  test    rcx, rcx
0x180028e30  jz      short loc_180028E44
0x180028e32  mov     [rsp+170h+var_100], r12
0x180028e37  mov     rax, [rcx]
0x180028e3a  mov     rax, [rax+10h]
0x180028e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e43  nop
0x180028e44  mov     [rbp+70h+var_A8], r12
0x180028e48  mov     [rbp+70h+string], r12
0x180028e4c  cmp     [rbp+70h+sourceString], r12
0x180028e50  jz      loc_180028C82
0x180028e56  mov     rcx, [rbp+70h+sourceString]; pv
0x180028e5a  call    cs:__imp_CoTaskMemFree
0x180028e60  jmp     loc_180028C82
0x180028e65  mov     r14, [rsp+170h+var_100]
0x180028e6a  mov     [rbp+70h+var_68], r12
0x180028e6e  lea     r9, [rbp+70h+var_68]; string
0x180028e72  lea     r8, [rbp+70h+var_80]; hstringHeader
0x180028e76  mov     edx, 0Eh; length
0x180028e7b  lea     rcx, String2; "Windows.Launch"
0x180028e82  call    cs:__imp_WindowsCreateStringReference
0x180028e88  test    eax, eax
0x180028e8a  jns     short loc_180028E9F
0x180028e8c  xor     r9d, r9d; lpArguments
0x180028e8f  xor     r8d, r8d; nNumberOfArguments
0x180028e92  lea     edx, [r9+1]; dwExceptionFlags
0x180028e96  mov     ecx, eax; dwExceptionCode
0x180028e98  call    cs:__imp_RaiseException
0x180028e9e  nop
0x180028e9f  mov     [rbp+70h+var_48], r12
0x180028ea3  inc     rdi
0x180028ea6  cmp     [r13+rdi*2+0], r12w
0x180028eac  jnz     short loc_180028EA3
0x180028eae  mov     eax, 0FFFFFFFFh
0x180028eb3  cmp     rdi, rax
0x180028eb6  ja      loc_180028FDF
0x180028ebc  mov     rbx, [rbp+70h+var_68]
0x180028ec0  mov     ecx, edi; unsigned int
0x180028ec2  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180028ec7  lea     edx, [rax-1]
0x180028eca  cmp     edi, eax
0x180028ecc  cmovb   edx, edi; length
0x180028ecf  lea     r9, [rbp+70h+var_48]; string
0x180028ed3  lea     r8, [rbp+70h+var_60]; hstringHeader
0x180028ed7  mov     rcx, r13; sourceString
0x180028eda  call    cs:__imp_WindowsCreateStringReference
0x180028ee0  test    eax, eax
0x180028ee2  jns     short loc_180028EF7
0x180028ee4  xor     r9d, r9d; lpArguments
0x180028ee7  xor     r8d, r8d; nNumberOfArguments
0x180028eea  lea     edx, [r9+1]; dwExceptionFlags
0x180028eee  mov     ecx, eax; dwExceptionCode
0x180028ef0  call    cs:__imp_RaiseException
0x180028ef6  nop
0x180028ef7  mov     rcx, [rbp+70h+var_C8]
0x180028efb  add     rcx, 0FFFFFFFFFFFFFFD8h
0x180028eff  mov     [rsp+170h+var_108], r12
0x180028f04  mov     [rsp+170h+var_110], r15
0x180028f09  mov     [rsp+170h+var_118], r12
0x180028f0e  mov     [rsp+170h+var_120], r12
0x180028f13  mov     [rsp+170h+var_128], r12d
0x180028f18  mov     [rsp+170h+var_130], r12
0x180028f1d  mov     [rsp+170h+var_138], r12
0x180028f22  mov     [rsp+170h+var_140], r12
0x180028f27  mov     [rsp+170h+var_148], r14
0x180028f2c  mov     eax, [rsp+170h+var_F4]
0x180028f30  mov     [rsp+170h+var_150], eax; int
0x180028f34  xor     r9d, r9d
0x180028f37  mov     r8, rbx
0x180028f3a  mov     rdx, [rbp+70h+var_48]
0x180028f3e  call    ?ActivateApplicationForContractCore@ActivationManagerShim@Execution@@IEAAJPEAUHSTRING__@@0_KW4ACTIVATEOPTIONSINTERNAL@@PEAUIInspectable@@PEBU_ActivateComponentInfo@@PEAUActivateByExtensionArgs@@3W4ActivateType@@PEAXPEA_KPEAKPEAPEAU5@@Z; Execution::ActivationManagerShim::ActivateApplicationForContractCore(HSTRING__ *,HSTRING__ *,unsigned __int64,ACTIVATEOPTIONSINTERNAL,IInspectable *,_ActivateComponentInfo const *,ActivateByExtensionArgs *,IInspectable *,ActivateType,void *,unsigned __int64 *,ulong *,IInspectable * *)
0x180028f43  mov     ebx, eax
0x180028f45  test    eax, eax
0x180028f47  jns     short loc_180028F63
0x180028f49  mov     rcx, [rbp+78h]; this
0x180028f4d  mov     r9d, eax; char *
0x180028f50  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180028f57  mov     edx, 2C2h; void *
0x180028f5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f61  jmp     short loc_180028F66
0x180028f63  mov     ebx, r12d
0x180028f66  test    ebx, ebx
0x180028f68  jns     short loc_180028FA4
0x180028f6a  mov     rcx, [rbp+78h]; this
0x180028f6e  mov     r9d, ebx; char *
0x180028f71  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180028f78  mov     edx, 19Bh; void *
0x180028f7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f82  nop
0x180028f83  lea     rcx, [rsp+170h+var_100]
0x180028f88  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028f8d  nop
0x180028f8e  mov     [rbp+70h+var_A8], r12
0x180028f92  mov     [rbp+70h+string], r12
0x180028f96  lea     rcx, [rbp+70h+sourceString]
0x180028f9a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180028f9f  jmp     loc_180028C82
0x180028fa4  mov     rcx, [rsp+170h+var_100]
0x180028fa9  test    rcx, rcx
0x180028fac  jz      short loc_180028FC0
0x180028fae  mov     [rsp+170h+var_100], r12
0x180028fb3  mov     rax, [rcx]
0x180028fb6  mov     rax, [rax+10h]
0x180028fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fbf  nop
0x180028fc0  mov     [rbp+70h+var_A8], r12
0x180028fc4  mov     [rbp+70h+string], r12
0x180028fc8  cmp     [rbp+70h+sourceString], r12
0x180028fcc  jz      short loc_180028FD8
0x180028fce  mov     rcx, [rbp+70h+sourceString]; pv
0x180028fd2  call    cs:__imp_CoTaskMemFree
0x180028fd8  xor     eax, eax
0x180028fda  jmp     loc_180028C84
0x180028fdf  xor     r9d, r9d; lpArguments
0x180028fe2  xor     r8d, r8d; nNumberOfArguments
0x180028fe5  lea     edx, [r9+1]; dwExceptionFlags
0x180028fe9  mov     ecx, 80070216h; dwExceptionCode
0x180028fee  call    cs:__imp_RaiseException
0x180028ff4  nop
0x180028ff5  xor     r9d, r9d; lpArguments
0x180028ff8  xor     r8d, r8d; nNumberOfArguments
0x180028ffb  lea     edx, [r9+1]; dwExceptionFlags
0x180028fff  mov     ecx, 80070216h; dwExceptionCode
0x180029004  call    cs:__imp_RaiseException
0x18002900a  nop
0x18002900b  xor     r9d, r9d; lpArguments
0x18002900e  xor     r8d, r8d; nNumberOfArguments
0x180029011  lea     edx, [r9+1]; dwExceptionFlags
0x180029015  mov     ecx, 80070216h; dwExceptionCode
0x18002901a  call    cs:__imp_RaiseException
```
