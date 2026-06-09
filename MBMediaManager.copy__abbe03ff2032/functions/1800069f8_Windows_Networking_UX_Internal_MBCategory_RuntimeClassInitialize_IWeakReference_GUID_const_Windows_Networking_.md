# Windows::Networking::UX::Internal::MBCategory::RuntimeClassInitialize(IWeakReference *,_GUID const &,Windows::Networking::UX::Internal::InterfaceConnectivity)

- ea: `0x1800069f8`
- end: `0x180006bc5`
- name: `?RuntimeClassInitialize@MBCategory@Internal@UX@Networking@Windows@@QEAAJPEAUIWeakReference@@AEBU_GUID@@W4InterfaceConnectivity@2345@@Z`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800068f8`

## callees

- `0x180002150`
- `0x180004980`
- `0x180006748`
- `0x1800069f8`
- `0x18000735c`
- `0x180009150`
- `0x18000ad20`
- `0x18000d6c0`
- `0x18000ecbc`
- `0x18000fe20`
- `0x18001bdb8`
- `0x18001cb10`
- `0x18002cd20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006a58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006a58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        const struct _GUID *a3,
        int a4)
{
  LPVOID *v8; // rbx
  HRESULT Instance; // eax
  unsigned int v10; // r9d
  Windows::Networking::UX::Internal::CategoryBase *v11; // rcx
  int InterfaceName; // ebx
  __int64 v13; // rdx
  __int64 v15; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[19]; // [rsp+48h] [rbp-B8h]
  char v20[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  char *v22; // [rsp+98h] [rbp-68h]
  unsigned __int16 v23[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v8 = (LPVOID *)(a1 + 272);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 272);
  Instance = CoCreateInstance(&CLSID_MbaeManagerInternal, 0, 0x17u, &GUID_b1874de5_5f25_4397_b439_aa6b4f09f40c, v8);
  v11 = retaddr;
  if ( Instance < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  InterfaceName = Windows::Networking::UX::Internal::CategoryBase::GetInterfaceName(v11, a3, v23, v10);
  if ( InterfaceName < 0 )
  {
    v13 = 53;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)InterfaceName,
      ppv);
    return (unsigned int)InterfaceName;
  }
  InterfaceName = Windows::Networking::UX::Internal::CategoryBase::Initialize(
                    (Windows::Networking::UX::Internal::CategoryBase *)a1,
                    a3,
                    v23);
  if ( InterfaceName < 0 )
  {
    v13 = 54;
    goto LABEL_5;
  }
  if ( *(_QWORD *)(a1 + 264) != a2 )
  {
    v17 = a2;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v17);
    v17 = *(_QWORD *)(a1 + 264);
    *(_QWORD *)(a1 + 264) = a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  }
  *(_DWORD *)(a1 + 292) = a4;
  Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae((Windows::Networking::UX::Internal::MBCategory *)a1);
  *(_QWORD *)v20 = off_18005DE30;
  v21 = a1;
  v22 = v20;
  InterfaceName = Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult(
                    a1,
                    (__int64)v20);
  std::_Func_class<void,>::~_Func_class<void,>(v20);
  if ( InterfaceName < 0 )
  {
    v13 = 64;
    goto LABEL_5;
  }
  v15 = MbLoggingHelperGuidToString(v20);
  v18 = *(_OWORD *)v15;
  *(_OWORD *)v19 = *(_OWORD *)(v15 + 16);
  *(_DWORD *)&v19[15] = *(_DWORD *)(v15 + 31);
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::RuntimeClassInitialize",
    66,
    "Category Name=%ls, Category GUID=%hs",
    v23,
    (const char *)&v18);
  return 0;
}

```

## disassembly

```asm
0x1800069f8  mov     [rsp-8+arg_8], rbx
0x1800069fd  push    rbp
0x1800069fe  push    rsi
0x1800069ff  push    rdi
0x180006a00  push    r14
0x180006a02  push    r15
0x180006a04  lea     rbp, [rsp-1C0h]
0x180006a0c  sub     rsp, 2C0h
0x180006a13  mov     rax, cs:__security_cookie
0x180006a1a  xor     rax, rsp
0x180006a1d  mov     [rbp+1E0h+var_30], rax
0x180006a24  mov     r15d, r9d
0x180006a27  mov     r14, r8
0x180006a2a  mov     rsi, rdx
0x180006a2d  mov     rdi, rcx
0x180006a30  lea     rbx, [rcx+110h]
0x180006a37  mov     rcx, rbx
0x180006a3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006a3f  mov     qword ptr [rsp+2E0h+ppv], rbx; int
0x180006a44  lea     r9, _GUID_b1874de5_5f25_4397_b439_aa6b4f09f40c; riid
0x180006a4b  xor     edx, edx; pUnkOuter
0x180006a4d  lea     r8d, [rdx+17h]; dwClsContext
0x180006a51  lea     rcx, CLSID_MbaeManagerInternal; rclsid
0x180006a58  call    cs:__imp_CoCreateInstance
0x180006a5e  mov     rcx, [rbp+1E8h]; this
0x180006a65  test    eax, eax
0x180006a67  jns     short loc_180006A7D
0x180006a69  mov     r9d, eax; char *
0x180006a6c  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180006a73  mov     edx, 31h ; '1'; void *
0x180006a78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006a7d  lea     r8, [rbp+1E0h+var_240]; unsigned __int16 *
0x180006a81  mov     rdx, r14; struct _GUID *
0x180006a84  call    ?GetInterfaceName@CategoryBase@Internal@UX@Networking@Windows@@IEAAJAEBU_GUID@@PEAGI@Z; Windows::Networking::UX::Internal::CategoryBase::GetInterfaceName(_GUID const &,ushort *,uint)
0x180006a89  mov     ebx, eax
0x180006a8b  test    eax, eax
0x180006a8d  jns     short loc_180006AB1
0x180006a8f  mov     edx, 35h ; '5'; void *
0x180006a94  mov     rcx, [rbp+1E8h]; this
0x180006a9b  mov     r9d, ebx; char *
0x180006a9e  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180006aa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006aaa  mov     eax, ebx
0x180006aac  jmp     loc_180006B9F
0x180006ab1  lea     r8, [rbp+1E0h+var_240]; unsigned __int16 *
0x180006ab5  mov     rdx, r14; struct _GUID *
0x180006ab8  mov     rcx, rdi; this
0x180006abb  call    ?Initialize@CategoryBase@Internal@UX@Networking@Windows@@IEAAJAEBU_GUID@@PEBG@Z; Windows::Networking::UX::Internal::CategoryBase::Initialize(_GUID const &,ushort const *)
0x180006ac0  mov     ebx, eax
0x180006ac2  test    eax, eax
0x180006ac4  jns     short loc_180006ACD
0x180006ac6  mov     edx, 36h ; '6'
0x180006acb  jmp     short loc_180006A94
0x180006acd  cmp     [rdi+108h], rsi
0x180006ad4  jz      short loc_180006B02
0x180006ad6  mov     [rsp+2E0h+var_2B0], rsi
0x180006adb  lea     rcx, [rsp+2E0h+var_2B0]
0x180006ae0  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x180006ae5  mov     rax, [rdi+108h]
0x180006aec  mov     [rsp+2E0h+var_2B0], rax
0x180006af1  mov     [rdi+108h], rsi
0x180006af8  lea     rcx, [rsp+2E0h+var_2B0]
0x180006afd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006b02  mov     [rdi+124h], r15d
0x180006b09  mov     rcx, rdi; this
0x180006b0c  call    ?tp_TryInitMbae@MBCategory@Internal@UX@Networking@Windows@@AEAA_NXZ; Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae(void)
0x180006b11  lea     rax, off_18005DE30
0x180006b18  mov     qword ptr [rsp+2E0h+var_280], rax
0x180006b1d  mov     [rsp+2E0h+var_278], rdi
0x180006b22  lea     rax, [rsp+2E0h+var_280]
0x180006b27  mov     [rbp+1E0h+var_248], rax
0x180006b2b  lea     rdx, [rsp+2E0h+var_280]
0x180006b30  mov     rcx, rdi
0x180006b33  call    ?_SubmitThreadpoolWorkItemAndWaitForHResult@MBCategory@Internal@UX@Networking@Windows@@AEAAJ$$QEAV?$function@$$A6AJXZ@std@@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolWorkItemAndWaitForHResult(std::function<long (void)> &&)
0x180006b38  mov     ebx, eax
0x180006b3a  lea     rcx, [rsp+2E0h+var_280]
0x180006b3f  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180006b44  test    ebx, ebx
0x180006b46  jns     short loc_180006B52
0x180006b48  mov     edx, 40h ; '@'
0x180006b4d  jmp     loc_180006A94
0x180006b52  mov     rdx, r14
0x180006b55  lea     rcx, [rsp+2E0h+var_280]; char *
0x180006b5a  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x180006b5f  movups  xmm0, xmmword ptr [rax]
0x180006b62  movups  [rsp+2E0h+var_2A8], xmm0
0x180006b67  movups  xmm1, xmmword ptr [rax+10h]
0x180006b6b  movups  xmmword ptr [rsp+2E0h+var_298], xmm1
0x180006b70  mov     eax, [rax+1Fh]
0x180006b73  mov     dword ptr [rsp+2E0h+var_298+0Fh], eax
0x180006b77  lea     rax, [rsp+2E0h+var_2A8]
0x180006b7c  mov     qword ptr [rsp+2E0h+ppv], rax
0x180006b81  lea     r9, [rbp+1E0h+var_240]
0x180006b85  lea     r8, aCategoryNameLs; "Category Name=%ls, Category GUID=%hs"
0x180006b8c  mov     edx, 42h ; 'B'; unsigned int
0x180006b91  lea     rcx, aWindowsNetwork_272; "Windows::Networking::UX::Internal::MBCa"...
0x180006b98  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180006b9d  xor     eax, eax
0x180006b9f  mov     rcx, [rbp+1E0h+var_30]
0x180006ba6  xor     rcx, rsp; StackCookie
0x180006ba9  call    __security_check_cookie
0x180006bae  mov     rbx, [rsp+2E0h+arg_8]
0x180006bb6  add     rsp, 2C0h
0x180006bbd  pop     r15
0x180006bbf  pop     r14
0x180006bc1  pop     rdi
0x180006bc2  pop     rsi
0x180006bc3  pop     rbp
0x180006bc4  retn
```
