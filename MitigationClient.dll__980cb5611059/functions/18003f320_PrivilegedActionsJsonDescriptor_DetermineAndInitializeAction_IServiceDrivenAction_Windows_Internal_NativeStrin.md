# PrivilegedActionsJsonDescriptor::DetermineAndInitializeAction(IServiceDrivenAction * *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,Microsoft::WRL::ComPtr<ActionContext>)

- ea: `0x18003f320`
- end: `0x18003f450`
- name: `?DetermineAndInitializeAction@PrivilegedActionsJsonDescriptor@@MEAAJPEAPEAUIServiceDrivenAction@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$ComPtr@VActionContext@@@78@@Z`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001055c`
- `0x18001208c`
- `0x18001e1b4`
- `0x180038890`
- `0x18003f058`
- `0x18003f320`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f38c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f38c`

## string_xrefs

- `0x18003f41a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedactionsjsondescriptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrivilegedActionsJsonDescriptor::DetermineAndInitializeAction(
        __int64 a1,
        _QWORD *a2,
        const WCHAR **a3,
        __int64 *a4,
        __int64 *a5)
{
  __int64 v9; // rdx
  const WCHAR *v10; // rcx
  int v11; // eax
  __int64 *v12; // rsi
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-48h]
  __int64 v19[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v21; // [rsp+80h] [rbp+18h] BYREF
  __int64 *v22; // [rsp+88h] [rbp+20h]

  v22 = a4;
  v9 = (__int64)a3[1];
  if ( v9 != -1 )
  {
    v10 = *a3;
    if ( *a3 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !*a3 )
  {
    LODWORD(v9) = 0;
LABEL_8:
    v10 = &String1;
    goto LABEL_9;
  }
  v9 = -1;
  do
    ++v9;
  while ( (*a3)[v9] );
  v10 = *a3;
LABEL_9:
  v11 = CompareStringOrdinal(v10, v9, L"LaunchExeV2", -1, 1);
  v12 = a5;
  if ( v11 == 2 )
  {
    v13 = Microsoft::WRL::Details::MakeAndInitialize<LaunchExePrivilegedAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(
            a2,
            (__int64)a4,
            a5);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 27;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedactionsjsondescriptor.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
    }
  }
  else
  {
    v21 = *a5;
    Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(&v21);
    v16 = *a4;
    v19[0] = v16;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    v13 = ServiceDrivenActionJsonDescriptor::DetermineAndInitializeAction(a1, a2, (__int64)a3, v19, &v21);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 33;
      goto LABEL_16;
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a4);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v12);
  return v14;
}

```

## disassembly

```asm
0x18003f320  mov     [rsp+arg_0], rbx
0x18003f325  mov     [rsp+arg_18], r9
0x18003f32a  push    rbp
0x18003f32b  push    rsi
0x18003f32c  push    rdi
0x18003f32d  push    r14
0x18003f32f  push    r15
0x18003f331  sub     rsp, 40h
0x18003f335  mov     r14, r9
0x18003f338  mov     rdi, r8
0x18003f33b  mov     rbp, rdx
0x18003f33e  mov     r15, rcx
0x18003f341  mov     rdx, [r8+8]; cchCount1
0x18003f345  or      r9, 0FFFFFFFFFFFFFFFFh; cchCount2
0x18003f349  cmp     rdx, r9
0x18003f34c  jnz     short loc_18003F36E
0x18003f34e  mov     rax, [r8]
0x18003f351  xor     ebx, ebx
0x18003f353  test    rax, rax
0x18003f356  jz      short loc_18003F369
0x18003f358  mov     rdx, r9
0x18003f35b  inc     rdx
0x18003f35e  cmp     [rax+rdx*2], bx
0x18003f362  jnz     short loc_18003F35B
0x18003f364  mov     rcx, rax
0x18003f367  jmp     short loc_18003F37D
0x18003f369  mov     rdx, rbx
0x18003f36c  jmp     short loc_18003F376
0x18003f36e  mov     rcx, [r8]
0x18003f371  test    rcx, rcx
0x18003f374  jnz     short loc_18003F37D
0x18003f376  lea     rcx, String1; lpString1
0x18003f37d  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18003f385  lea     r8, aLaunchexev2; "LaunchExeV2"
0x18003f38c  call    cs:__imp_CompareStringOrdinal
0x18003f392  mov     rsi, [rsp+68h+arg_20]
0x18003f39a  cmp     eax, 2
0x18003f39d  jnz     short loc_18003F3BA
0x18003f39f  mov     r8, rsi
0x18003f3a2  mov     rdx, r14
0x18003f3a5  mov     rcx, rbp
0x18003f3a8  call    ??$MakeAndInitialize@VLaunchExePrivilegedAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<LaunchExePrivilegedAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &)
0x18003f3ad  mov     edi, eax
0x18003f3af  test    eax, eax
0x18003f3b1  jns     short loc_18003F42C
0x18003f3b3  mov     edx, 1Bh
0x18003f3b8  jmp     short loc_18003F417
0x18003f3ba  mov     rax, [rsi]
0x18003f3bd  mov     [rsp+68h+arg_10], rax
0x18003f3c5  lea     rcx, [rsp+68h+arg_10]
0x18003f3cd  call    ?InternalAddRef@?$ComPtr@VMitigationOneSettingsMetadata@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MitigationOneSettingsMetadata>::InternalAddRef(void)
0x18003f3d2  mov     rcx, [r14]
0x18003f3d5  mov     [rsp+68h+var_38], rcx
0x18003f3da  test    rcx, rcx
0x18003f3dd  jz      short loc_18003F3EC
0x18003f3df  mov     rax, [rcx]
0x18003f3e2  mov     rax, [rax+8]
0x18003f3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3eb  nop
0x18003f3ec  lea     rax, [rsp+68h+arg_10]
0x18003f3f4  mov     qword ptr [rsp+68h+bIgnoreCase], rax; int
0x18003f3f9  lea     r9, [rsp+68h+var_38]
0x18003f3fe  mov     r8, rdi
0x18003f401  mov     rdx, rbp
0x18003f404  mov     rcx, r15
0x18003f407  call    ?DetermineAndInitializeAction@ServiceDrivenActionJsonDescriptor@@MEAAJPEAPEAUIServiceDrivenAction@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$ComPtr@VActionContext@@@78@@Z; ServiceDrivenActionJsonDescriptor::DetermineAndInitializeAction(IServiceDrivenAction * *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,Microsoft::WRL::ComPtr<ActionContext>)
0x18003f40c  mov     edi, eax
0x18003f40e  test    eax, eax
0x18003f410  jns     short loc_18003F42C
0x18003f412  mov     edx, 21h ; '!'; void *
0x18003f417  mov     r9d, eax; char *
0x18003f41a  lea     r8, aOnecoreBaseDia_16; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003f421  mov     rcx, [rsp+68h]; this
0x18003f426  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f42b  nop
0x18003f42c  mov     rcx, r14
0x18003f42f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f434  nop
0x18003f435  mov     rcx, rsi
0x18003f438  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003f43d  mov     eax, edi
0x18003f43f  mov     rbx, [rsp+68h+arg_0]
0x18003f444  add     rsp, 40h
0x18003f448  pop     r15
0x18003f44a  pop     r14
0x18003f44c  pop     rdi
0x18003f44d  pop     rsi
0x18003f44e  pop     rbp
0x18003f44f  retn
```
