# DoesHostRuntimeHaveCustomCapability(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IHostRuntime> const &,void * const)

- ea: `0x14000ae54`
- end: `0x14000afe3`
- name: `?DoesHostRuntimeHaveCustomCapability@@YA_NAEBV?$ComPtr@UIHostRuntime@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAX@Z`
- size: `399`
- prototype: `bool __fastcall(__int64 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b114`

## callees

- `0x14000ae54`
- `0x14000afec`
- `0x14000d49c`
- `0x14000fbb0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000af52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000afa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000af52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000afa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000af92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000af92`

## pseudocode

```c
bool __fastcall DoesHostRuntimeHaveCustomCapability(__int64 *a1, void *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, int *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  bool HaveCustomCapability; // bl
  int v18[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+50h] [rbp+20h] BYREF
  __int64 v21; // [rsp+60h] [rbp+30h] BYREF
  __int64 v22; // [rsp+68h] [rbp+38h] BYREF

  v21 = 0;
  v3 = *a1;
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a1 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v21);
  v5 = v4(v3, &v21);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC9,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v5,
      v18[0]);
  *(_QWORD *)v18 = 0;
  v6 = v21;
  v7 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v18);
  v8 = v7(v6, v18);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xCC,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v8,
      v18[0]);
  v22 = 0;
  v9 = v21;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v22);
  v11 = v10(v9, &v22);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xCF,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v11,
      v18[0]);
  string = 0;
  v12 = v22;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 112LL);
  WindowsDeleteString(0);
  string = 0;
  v14 = v13(v12, &string);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xD2,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v14,
      v18[0]);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  HaveCustomCapability = DoesPackageHaveCustomCapability(StringRawBuffer, a2);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v18);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v21);
  return HaveCustomCapability;
}

```

## disassembly

```asm
0x14000ae54  mov     [rsp-18h+arg_8], rbx
0x14000ae59  push    rbp
0x14000ae5a  push    rsi
0x14000ae5b  push    rdi
0x14000ae5c  mov     rbp, rsp
0x14000ae5f  sub     rsp, 30h
0x14000ae63  mov     rsi, rdx
0x14000ae66  mov     [rbp+arg_10], 0
0x14000ae6e  mov     rdi, [rcx]
0x14000ae71  mov     rax, [rdi]
0x14000ae74  mov     rbx, [rax+50h]
0x14000ae78  lea     rcx, [rbp+arg_10]
0x14000ae7c  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000ae81  lea     rdx, [rbp+arg_10]
0x14000ae85  mov     rcx, rdi
0x14000ae88  mov     rax, rbx
0x14000ae8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae90  mov     rcx, [rbp+18h]; this
0x14000ae94  test    eax, eax
0x14000ae96  jns     short loc_14000AEAD
0x14000ae98  mov     r9d, eax; char *
0x14000ae9b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000aea2  mov     edx, 0C9h; void *
0x14000aea7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000aead  mov     qword ptr [rbp+var_10], 0
0x14000aeb5  mov     rdi, [rbp+arg_10]
0x14000aeb9  mov     rax, [rdi]
0x14000aebc  mov     rbx, [rax+68h]
0x14000aec0  lea     rcx, [rbp+var_10]
0x14000aec4  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000aec9  lea     rdx, [rbp+var_10]
0x14000aecd  mov     rcx, rdi
0x14000aed0  mov     rax, rbx
0x14000aed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aed8  mov     rcx, [rbp+18h]; this
0x14000aedc  test    eax, eax
0x14000aede  jns     short loc_14000AEF5
0x14000aee0  mov     r9d, eax; char *
0x14000aee3  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000aeea  mov     edx, 0CCh; void *
0x14000aeef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000aef5  mov     [rbp+arg_18], 0
0x14000aefd  mov     rdi, [rbp+arg_10]
0x14000af01  mov     rax, [rdi]
0x14000af04  mov     rbx, [rax+48h]
0x14000af08  lea     rcx, [rbp+arg_18]
0x14000af0c  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000af11  lea     rdx, [rbp+arg_18]
0x14000af15  mov     rcx, rdi
0x14000af18  mov     rax, rbx
0x14000af1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af20  mov     rcx, [rbp+18h]; this
0x14000af24  test    eax, eax
0x14000af26  jns     short loc_14000AF3D
0x14000af28  mov     r9d, eax; char *
0x14000af2b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000af32  mov     edx, 0CFh; void *
0x14000af37  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000af3d  mov     [rbp+string], 0
0x14000af45  mov     rdi, [rbp+arg_18]
0x14000af49  mov     rax, [rdi]
0x14000af4c  mov     rbx, [rax+70h]
0x14000af50  xor     ecx, ecx; string
0x14000af52  call    cs:__imp_WindowsDeleteString
0x14000af58  mov     [rbp+string], 0
0x14000af60  lea     rdx, [rbp+string]
0x14000af64  mov     rcx, rdi
0x14000af67  mov     rax, rbx
0x14000af6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af6f  mov     rcx, [rbp+18h]; this
0x14000af73  test    eax, eax
0x14000af75  jns     short loc_14000AF8C
0x14000af77  mov     r9d, eax; char *
0x14000af7a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000af81  mov     edx, 0D2h; void *
0x14000af86  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000af8c  xor     edx, edx; length
0x14000af8e  mov     rcx, [rbp+string]; string
0x14000af92  call    cs:__imp_WindowsGetStringRawBuffer
0x14000af98  mov     rdx, rsi; void *
0x14000af9b  mov     rcx, rax; unsigned __int16 *
0x14000af9e  call    ?DoesPackageHaveCustomCapability@@YA_NPEBGQEAX@Z; DoesPackageHaveCustomCapability(ushort const *,void * const)
0x14000afa3  mov     bl, al
0x14000afa5  mov     rcx, [rbp+string]; string
0x14000afa9  call    cs:__imp_WindowsDeleteString
0x14000afaf  mov     [rbp+string], 0
0x14000afb7  lea     rcx, [rbp+arg_18]
0x14000afbb  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000afc0  nop
0x14000afc1  lea     rcx, [rbp+var_10]
0x14000afc5  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000afca  nop
0x14000afcb  lea     rcx, [rbp+arg_10]
0x14000afcf  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000afd4  mov     al, bl
0x14000afd6  mov     rbx, [rsp+30h+arg_8]
0x14000afdb  add     rsp, 30h
0x14000afdf  pop     rdi
0x14000afe0  pop     rsi
0x14000afe1  pop     rbp
0x14000afe2  retn
```
