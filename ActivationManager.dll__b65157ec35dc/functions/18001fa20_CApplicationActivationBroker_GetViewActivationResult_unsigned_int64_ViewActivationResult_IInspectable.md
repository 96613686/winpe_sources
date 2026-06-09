# CApplicationActivationBroker::GetViewActivationResult(unsigned __int64,ViewActivationResult *,IInspectable * *)

- ea: `0x18001fa20`
- end: `0x18001ff09`
- name: `?GetViewActivationResult@CApplicationActivationBroker@@UEAAJ_KPEAUViewActivationResult@@PEAPEAUIInspectable@@@Z`
- size: `1257`
- prototype: `int(CApplicationActivationBroker *__hidden this, unsigned __int64, struct ViewActivationResult *, struct IInspectable **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180011328`
- `0x18001fa20`
- `0x18001ff10`
- `0x1800445ac`
- `0x18005ae90`
- `0x18005b3c4`
- `0x18005b840`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001feac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001feac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fefe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fef3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fefe`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18001fb41`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18001fb81`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18001fb41`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18001fb81`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001fab3`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001fab3`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18001fbce`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18001fbce`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18001fb00`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18001fb00`

## string_xrefs

- `0x18001fc52`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`
- `0x18001fd11`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`
- `0x18001fd72`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`
- `0x18001fdb0`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`
- `0x18001fdd5`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`
- `0x18001fe6c`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`
- `0x18001fe91`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`
- `0x18001fec3`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationactivationbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CApplicationActivationBroker::GetViewActivationResult(
        CApplicationActivationBroker *this,
        __int64 a2,
        struct ViewActivationResult *a3,
        struct IInspectable **a4)
{
  int v5; // r14d
  unsigned int v7; // eax
  DWORD CurrentProcessId; // eax
  int v9; // ebx
  int v10; // ebx
  HANDLE v11; // r12
  __int64 v12; // r13
  int SecurityAttributesToken; // ebx
  _QWORD *v14; // rdi
  unsigned int ApplicationUserModelIdFromToken; // eax
  int Instance; // eax
  struct IViewActivatorHelper *v17; // rdi
  __int64 (__fastcall *v18)(struct IViewActivatorHelper *, __int64, __int64, WCHAR *); // rbx
  int v19; // eax
  __int64 (__fastcall ***v20)(_QWORD, GUID *, struct IInspectable **); // rcx
  struct IViewActivatorHelper *v21; // rcx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, GUID *, struct IInspectable **); // rcx
  struct IViewActivatorHelper *v25; // rcx
  struct IViewActivatorHelper *v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, GUID *, struct IInspectable **); // rcx
  struct IViewActivatorHelper *v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // [rsp+20h] [rbp-E0h]
  struct IViewActivatorHelper *v31; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE token; // [rsp+48h] [rbp-B8h] BYREF
  size_t Size; // [rsp+50h] [rbp-B0h]
  __int64 (__fastcall ***v34)(_QWORD, GUID *, struct IInspectable **); // [rsp+58h] [rbp-A8h] BYREF
  UINT32 applicationUserModelIdLength[4]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h]
  __int128 v38; // [rsp+88h] [rbp-78h]
  __int128 v39; // [rsp+98h] [rbp-68h]
  __int128 v40; // [rsp+A8h] [rbp-58h]
  __int128 v41; // [rsp+B8h] [rbp-48h]
  __int128 v42; // [rsp+C8h] [rbp-38h]
  __int128 v43; // [rsp+D8h] [rbp-28h]
  WCHAR applicationUserModelId[136]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v5 = (int)a3;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
      (const char *)0x80004003LL,
      v30);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
      (const char *)0x80004003LL,
      v30);
    return 2147500035LL;
  }
  *a4 = 0;
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  RpcCallAttributes[0] = 3;
  RpcCallAttributes[1] = 16;
  v7 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v7 )
  {
    if ( v7 == 1725 )
    {
      CurrentProcessId = GetCurrentProcessId();
    }
    else
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x28,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutilscontext.cpp",
             (const char *)v7,
             v30);
      CurrentProcessId = 0;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
          (const char *)(unsigned int)v9,
          v30);
        return (unsigned int)v9;
      }
    }
  }
  else
  {
    CurrentProcessId = DWORD2(v40);
  }
  token = 0;
  v10 = UMgrOpenProcessTokenForQuery(CurrentProcessId, &token);
  if ( v10 < 0 )
  {
    v29 = 168;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
      (const char *)(unsigned int)v10,
      v30);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
    return (unsigned int)v10;
  }
  v11 = token;
  v12 = -1;
  LODWORD(Size) = 0;
  v30 = 0;
  SecurityAttributesToken = NtQuerySecurityAttributesToken(token, &qword_1800A12E8, 1, 0);
  if ( SecurityAttributesToken == -1073741789 )
  {
    v14 = operator new((unsigned int)Size);
    v30 = Size;
    SecurityAttributesToken = NtQuerySecurityAttributesToken(v11, &qword_1800A12E8, 1, v14);
    if ( SecurityAttributesToken >= 0 )
    {
      if ( *((_DWORD *)v14 + 1) )
        v12 = **(_QWORD **)(v14[1] + 32LL);
      else
        SecurityAttributesToken = -1073741275;
    }
    operator delete(v14);
  }
  v10 = SecurityAttributesToken | 0x10000000;
  if ( v10 < 0 )
  {
    v29 = 171;
    goto LABEL_48;
  }
  applicationUserModelIdLength[0] = 130;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xAF,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
            (const char *)ApplicationUserModelIdFromToken,
            v30);
    if ( (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(token);
    return (unsigned int)v10;
  }
  v31 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  Instance = ViewActivator::GetInstance(&v31);
  v10 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
      (const char *)(unsigned int)Instance,
      v30);
    v26 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(struct IViewActivatorHelper *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    goto LABEL_21;
  }
  v34 = 0;
  v17 = v31;
  v18 = *(__int64 (__fastcall **)(struct IViewActivatorHelper *, __int64, __int64, WCHAR *))(*(_QWORD *)v31 + 40LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  v19 = v18(v17, a2, v12, applicationUserModelId);
  v10 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
      (const char *)(unsigned int)v19,
      v5);
    v20 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **)))(*v20)[2])(v20);
    }
    v21 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(struct IViewActivatorHelper *))(*(_QWORD *)v21 + 16LL))(v21);
    }
LABEL_21:
    if ( (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(token);
    return (unsigned int)v10;
  }
  v23 = (**v34)(v34, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, a4);
  v10 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationbroker.cpp",
      (const char *)(unsigned int)v23,
      v5);
    v24 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **)))(*v24)[2])(v24);
    }
    v25 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(struct IViewActivatorHelper *))(*(_QWORD *)v25 + 16LL))(v25);
    }
    goto LABEL_21;
  }
  v27 = v34;
  if ( v34 )
  {
    v34 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IInspectable **)))(*v27)[2])(v27);
  }
  v28 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(struct IViewActivatorHelper *))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(token);
  return 0;
}

```

## disassembly

```asm
0x18001fa20  mov     [rsp-8+arg_0], rbx
0x18001fa25  push    rbp
0x18001fa26  push    rsi
0x18001fa27  push    rdi
0x18001fa28  push    r12
0x18001fa2a  push    r13
0x18001fa2c  push    r14
0x18001fa2e  push    r15
0x18001fa30  lea     rbp, [rsp-110h]
0x18001fa38  sub     rsp, 210h
0x18001fa3f  mov     rax, cs:__security_cookie
0x18001fa46  xor     rax, rsp
0x18001fa49  mov     [rbp+140h+var_40], rax
0x18001fa50  mov     rsi, r9
0x18001fa53  mov     r14, r8
0x18001fa56  mov     r15, rdx
0x18001fa59  test    r8, r8
0x18001fa5c  jz      loc_18001FDA3
0x18001fa62  test    r9, r9
0x18001fa65  jz      loc_18001FE84
0x18001fa6b  xor     edi, edi
0x18001fa6d  mov     [r9], rdi
0x18001fa70  xorps   xmm0, xmm0
0x18001fa73  movups  xmmword ptr [r8], xmm0
0x18001fa77  movups  xmmword ptr [r8+10h], xmm0
0x18001fa7c  xorps   xmm1, xmm1
0x18001fa7f  movups  [rsp+240h+var_1C8], xmm1
0x18001fa84  movups  [rbp+140h+var_1B8], xmm1
0x18001fa88  movups  [rbp+140h+var_1A8], xmm1
0x18001fa8c  movups  [rbp+140h+var_198], xmm1
0x18001fa90  movups  [rbp+140h+var_188], xmm1
0x18001fa94  movups  [rbp+140h+var_178], xmm1
0x18001fa98  movups  [rbp+140h+var_168], xmm1
0x18001fa9c  mov     [rsp+240h+RpcCallAttributes], 3
0x18001faa4  mov     [rsp+240h+var_1CC], 10h
0x18001faac  lea     rdx, [rsp+240h+RpcCallAttributes]; RpcCallAttributes
0x18001fab1  xor     ecx, ecx; ClientBinding
0x18001fab3  call    cs:__imp_RpcServerInqCallAttributesW
0x18001fab9  test    eax, eax
0x18001fabb  jnz     short loc_18001FAC2
0x18001fabd  mov     eax, dword ptr [rbp+140h+var_198+8]
0x18001fac0  jmp     short loc_18001FAF4
0x18001fac2  cmp     eax, 6BDh
0x18001fac7  jz      loc_18001FEAC
0x18001facd  mov     rcx, [rbp+148h]; this
0x18001fad4  mov     r9d, eax; char *
0x18001fad7  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fade  mov     edx, 28h ; '('; void *
0x18001fae3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001fae8  mov     ebx, eax
0x18001faea  mov     eax, edi
0x18001faec  test    ebx, ebx
0x18001faee  js      loc_18001FE62
0x18001faf4  mov     [rsp+240h+token], rdi
0x18001faf9  lea     rdx, [rsp+240h+token]
0x18001fafe  mov     ecx, eax
0x18001fb00  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18001fb06  mov     ebx, eax
0x18001fb08  test    eax, eax
0x18001fb0a  js      loc_18001FEB7
0x18001fb10  mov     r12, [rsp+240h+token]
0x18001fb15  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001fb1c  mov     dword ptr [rsp+240h+Size], edi
0x18001fb20  lea     rax, [rsp+240h+Size]
0x18001fb25  mov     [rsp+240h+var_218], rax
0x18001fb2a  mov     [rsp+240h+var_220], edi
0x18001fb2e  xor     r9d, r9d
0x18001fb31  mov     r8d, 1
0x18001fb37  lea     rdx, qword_1800A12E8
0x18001fb3e  mov     rcx, r12
0x18001fb41  call    cs:__imp_NtQuerySecurityAttributesToken
0x18001fb47  mov     ebx, eax
0x18001fb49  cmp     eax, 0C0000023h
0x18001fb4e  jnz     short loc_18001FBAC
0x18001fb50  mov     ecx, dword ptr [rsp+240h+Size]; Size
0x18001fb54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb59  mov     rdi, rax
0x18001fb5c  mov     edx, dword ptr [rsp+240h+Size]
0x18001fb60  lea     rax, [rsp+240h+Size]
0x18001fb65  mov     [rsp+240h+var_218], rax
0x18001fb6a  mov     [rsp+240h+var_220], edx; int
0x18001fb6e  mov     r9, rdi
0x18001fb71  mov     r8d, 1
0x18001fb77  lea     rdx, qword_1800A12E8
0x18001fb7e  mov     rcx, r12
0x18001fb81  call    cs:__imp_NtQuerySecurityAttributesToken
0x18001fb87  mov     ebx, eax
0x18001fb89  test    eax, eax
0x18001fb8b  js      short loc_18001FBA2
0x18001fb8d  cmp     dword ptr [rdi+4], 0
0x18001fb91  jz      loc_18001FEE9
0x18001fb97  mov     rax, [rdi+8]
0x18001fb9b  mov     rcx, [rax+20h]
0x18001fb9f  mov     r13, [rcx]
0x18001fba2  mov     rcx, rdi; Block
0x18001fba5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fbaa  xor     edi, edi
0x18001fbac  or      ebx, 10000000h
0x18001fbb2  jl      loc_18001FEBE
0x18001fbb8  mov     [rsp+240h+applicationUserModelIdLength], 82h
0x18001fbc0  lea     r8, [rbp+140h+applicationUserModelId]; applicationUserModelId
0x18001fbc4  lea     rdx, [rsp+240h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18001fbc9  mov     rcx, [rsp+240h+token]; token
0x18001fbce  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18001fbd4  test    eax, eax
0x18001fbd6  jnz     loc_18001FD68
0x18001fbdc  mov     [rsp+240h+var_200], rdi
0x18001fbe1  lea     rcx, [rsp+240h+var_200]
0x18001fbe6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001fbeb  lea     rcx, [rsp+240h+var_200]; struct IViewActivatorHelper **
0x18001fbf0  call    ?GetInstance@ViewActivator@@SAJPEAPEAUIViewActivatorHelper@@@Z; ViewActivator::GetInstance(IViewActivatorHelper * *)
0x18001fbf5  mov     ebx, eax
0x18001fbf7  test    eax, eax
0x18001fbf9  js      loc_18001FDCB
0x18001fbff  mov     [rsp+240h+var_1E8], rdi
0x18001fc04  mov     rdi, [rsp+240h+var_200]
0x18001fc09  mov     rax, [rdi]
0x18001fc0c  mov     rbx, [rax+28h]
0x18001fc10  lea     rcx, [rsp+240h+var_1E8]
0x18001fc15  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001fc1a  lea     rax, [rsp+240h+var_1E8]
0x18001fc1f  mov     [rsp+240h+var_218], rax
0x18001fc24  mov     qword ptr [rsp+240h+var_220], r14; int
0x18001fc29  lea     r9, [rbp+140h+applicationUserModelId]
0x18001fc2d  mov     r8, r13
0x18001fc30  mov     rdx, r15
0x18001fc33  mov     rcx, rdi
0x18001fc36  mov     rax, rbx
0x18001fc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc3e  mov     ebx, eax
0x18001fc40  test    eax, eax
0x18001fc42  jns     loc_18001FCE3
0x18001fc48  mov     rcx, [rbp+148h]; this
0x18001fc4f  mov     r9d, eax; char *
0x18001fc52  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fc59  mov     edx, 0B5h; void *
0x18001fc5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc63  nop
0x18001fc64  mov     rcx, [rsp+240h+var_1E8]
0x18001fc69  test    rcx, rcx
0x18001fc6c  jz      short loc_18001FC84
0x18001fc6e  mov     [rsp+240h+var_1E8], 0
0x18001fc77  mov     rax, [rcx]
0x18001fc7a  mov     rax, [rax+10h]
0x18001fc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc83  nop
0x18001fc84  mov     rcx, [rsp+240h+var_200]
0x18001fc89  test    rcx, rcx
0x18001fc8c  jz      short loc_18001FCA4
0x18001fc8e  mov     [rsp+240h+var_200], 0
0x18001fc97  mov     rax, [rcx]
0x18001fc9a  mov     rax, [rax+10h]
0x18001fc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fca3  nop
0x18001fca4  mov     rcx, [rsp+240h+token]; hObject
0x18001fca9  lea     rax, [rcx-1]
0x18001fcad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001fcb1  jbe     loc_18001FEF3
0x18001fcb7  mov     eax, ebx
0x18001fcb9  mov     rcx, [rbp+140h+var_40]
0x18001fcc0  xor     rcx, rsp; StackCookie
0x18001fcc3  call    __security_check_cookie
0x18001fcc8  mov     rbx, [rsp+240h+arg_0]
0x18001fcd0  add     rsp, 210h
0x18001fcd7  pop     r15
0x18001fcd9  pop     r14
0x18001fcdb  pop     r13
0x18001fcdd  pop     r12
0x18001fcdf  pop     rdi
0x18001fce0  pop     rsi
0x18001fce1  pop     rbp
0x18001fce2  retn
0x18001fce3  mov     rcx, [rsp+240h+var_1E8]
0x18001fce8  mov     rax, [rcx]
0x18001fceb  mov     r8, rsi
0x18001fcee  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18001fcf5  mov     rax, [rax]
0x18001fcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcfd  mov     ebx, eax
0x18001fcff  test    eax, eax
0x18001fd01  jns     loc_18001FE08
0x18001fd07  mov     rcx, [rbp+148h]; this
0x18001fd0e  mov     r9d, eax; char *
0x18001fd11  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fd18  mov     edx, 0B6h; void *
0x18001fd1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd22  nop
0x18001fd23  mov     rcx, [rsp+240h+var_1E8]
0x18001fd28  test    rcx, rcx
0x18001fd2b  jz      short loc_18001FD43
0x18001fd2d  mov     [rsp+240h+var_1E8], 0
0x18001fd36  mov     rax, [rcx]
0x18001fd39  mov     rax, [rax+10h]
0x18001fd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd42  nop
0x18001fd43  mov     rcx, [rsp+240h+var_200]
0x18001fd48  test    rcx, rcx
0x18001fd4b  jz      short loc_18001FD63
0x18001fd4d  mov     [rsp+240h+var_200], 0
0x18001fd56  mov     rax, [rcx]
0x18001fd59  mov     rax, [rax+10h]
0x18001fd5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd62  nop
0x18001fd63  jmp     loc_18001FCA4
0x18001fd68  mov     rcx, [rbp+148h]; this
0x18001fd6f  mov     r9d, eax; char *
0x18001fd72  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fd79  mov     edx, 0AFh; void *
0x18001fd7e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001fd83  mov     ebx, eax
0x18001fd85  mov     rcx, [rsp+240h+token]; hObject
0x18001fd8a  lea     rdx, [rcx-1]
0x18001fd8e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001fd92  ja      loc_18001FCB7
0x18001fd98  call    cs:__imp_CloseHandle
0x18001fd9e  jmp     loc_18001FCB7
0x18001fda3  mov     rcx, [rbp+148h]; this
0x18001fdaa  mov     r9d, 80004003h; char *
0x18001fdb0  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fdb7  mov     edx, 9Eh; void *
0x18001fdbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdc1  mov     eax, 80004003h
0x18001fdc6  jmp     loc_18001FCB9
0x18001fdcb  mov     rcx, [rbp+148h]; this
0x18001fdd2  mov     r9d, ebx; char *
0x18001fdd5  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fddc  mov     edx, 0B2h; void *
0x18001fde1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fde6  nop
0x18001fde7  mov     rcx, [rsp+240h+var_200]
0x18001fdec  test    rcx, rcx
0x18001fdef  jz      short loc_18001FE03
0x18001fdf1  mov     [rsp+240h+var_200], rdi
0x18001fdf6  mov     rax, [rcx]
0x18001fdf9  mov     rax, [rax+10h]
0x18001fdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe02  nop
0x18001fe03  jmp     loc_18001FCA4
0x18001fe08  mov     rcx, [rsp+240h+var_1E8]
0x18001fe0d  test    rcx, rcx
0x18001fe10  jz      short loc_18001FE28
0x18001fe12  mov     [rsp+240h+var_1E8], 0
0x18001fe1b  mov     rax, [rcx]
0x18001fe1e  mov     rax, [rax+10h]
0x18001fe22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe27  nop
0x18001fe28  mov     rcx, [rsp+240h+var_200]
0x18001fe2d  test    rcx, rcx
0x18001fe30  jz      short loc_18001FE48
0x18001fe32  mov     [rsp+240h+var_200], 0
0x18001fe3b  mov     rax, [rcx]
0x18001fe3e  mov     rax, [rax+10h]
0x18001fe42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe47  nop
0x18001fe48  mov     rcx, [rsp+240h+token]; hObject
0x18001fe4d  lea     rax, [rcx-1]
0x18001fe51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001fe55  jbe     loc_18001FEFE
0x18001fe5b  xor     eax, eax
0x18001fe5d  jmp     loc_18001FCB9
0x18001fe62  mov     rcx, [rbp+148h]; this
0x18001fe69  mov     r9d, ebx; char *
0x18001fe6c  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fe73  mov     edx, 0A5h; void *
0x18001fe78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe7d  mov     eax, ebx
0x18001fe7f  jmp     loc_18001FCB9
0x18001fe84  mov     rcx, [rbp+148h]; this
0x18001fe8b  mov     r9d, 80004003h; char *
0x18001fe91  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001fe98  mov     edx, 9Fh; void *
0x18001fe9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fea2  mov     eax, 80004003h
0x18001fea7  jmp     loc_18001FCB9
0x18001feac  call    cs:__imp_GetCurrentProcessId
0x18001feb2  jmp     loc_18001FAF4
0x18001feb7  mov     edx, 0A8h
0x18001febc  jmp     short loc_18001FEC3
0x18001febe  mov     edx, 0ABh; void *
0x18001fec3  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001feca  mov     r9d, ebx; char *
0x18001fecd  mov     rcx, [rbp+148h]; this
0x18001fed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fed9  nop
0x18001feda  lea     rcx, [rsp+240h+token]
0x18001fedf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001fee4  jmp     loc_18001FCB7
0x18001fee9  mov     ebx, 0C0000225h
0x18001feee  jmp     loc_18001FBA2
0x18001fef3  call    cs:__imp_CloseHandle
0x18001fef9  jmp     loc_18001FCB7
0x18001fefe  call    cs:__imp_CloseHandle
0x18001ff04  jmp     loc_18001FE5B
```
