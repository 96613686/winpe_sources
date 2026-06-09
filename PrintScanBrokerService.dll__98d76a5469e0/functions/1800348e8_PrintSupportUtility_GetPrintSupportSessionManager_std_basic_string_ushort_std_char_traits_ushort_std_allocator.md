# PrintSupportUtility::GetPrintSupportSessionManager(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800348e8`
- end: `0x180034a34`
- name: `?GetPrintSupportSessionManager@PrintSupportUtility@@QEAA?AUIInspectable@Foundation@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000aa00`

## callees

- `0x180007a58`
- `0x180012ef4`
- `0x18001d058`
- `0x1800291d0`
- `0x180030a08`
- `0x180031d24`
- `0x1800348e8`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180034976`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180034976`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034a23`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034a23`

## string_xrefs

- `0x180034928`: `ImpersonateUser failed!`
- `0x180034912`: `ImpersonateActiveUser failed!`
- `0x180034937`: `onecoreuap\printscan\print\printscanbroker\class\printsupportutility.cpp`
- `0x180034990`: `onecoreuap\printscan\print\printscanbroker\class\printsupportutility.cpp`
- `0x1800349eb`: `onecoreuap\printscan\print\printscanbroker\class\printsupportutility.cpp`
- `0x1800349dc`: `CreateInstance (IPrintSupportSessionManager) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall PrintSupportUtility::GetPrintSupportSessionManager(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned int v4; // edi
  unsigned int active; // eax
  const char *v6; // rcx
  unsigned int ClassObject; // eax
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, _QWORD, GUID *, void **); // rbx
  struct IUnknown *v10; // rdx
  void **v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rax
  const char *v15; // [rsp+28h] [rbp-30h]
  const char *v16; // [rsp+28h] [rbp-30h]
  const char *v17; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp+10h]
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF

  v20 = a2;
  v19 = a1;
  if ( *(_QWORD *)(a3 + 16) )
  {
    v4 = 33;
    active = PrintCore::UserImpersonationHelpers::ImpersonateUser(a3);
    v6 = "ImpersonateUser failed!";
  }
  else
  {
    v4 = 29;
    active = PrintCore::UserImpersonationHelpers::ImpersonateActiveUser();
    v6 = "ImpersonateActiveUser failed!";
  }
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printsupportutility.cpp",
    (const char *)active,
    (int)v6,
    v15);
  BYTE1(v20) = 1;
  ppv = 0;
  ClassObject = CoGetClassObject(&rclsid, 0x100004u, 0, &GUID_00000001_0000_0000_c000_000000000046, &ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x29,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printsupportutility.cpp",
    (const char *)ClassObject,
    (int)"CoGetClassObject failed!",
    v16);
  v19 = 0;
  v8 = ppv;
  v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)ppv + 24LL);
  v11 = winrt::put_abi((winrt *)&v19, v10);
  v12 = v9(v8, 0, &GUID_8cd48002_1c68_54c7_9bcc_f361b0566ea9, v11);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2C,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printsupportutility.cpp",
    (const char *)v12,
    (int)"CreateInstance (IPrintSupportSessionManager) failed!",
    v17);
  v13 = v19;
  v19 = 0;
  *a2 = v13;
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v19);
  wil::com_ptr_t<IClassFactory,wil::err_exception_policy>::~com_ptr_t<IClassFactory,wil::err_exception_policy>((__int64 *)&ppv);
  RevertToSelf();
  return a2;
}

```

## disassembly

```asm
0x1800348e8  mov     [rsp+arg_8], rdx
0x1800348ed  mov     [rsp+arg_0], rcx
0x1800348f2  push    rbx
0x1800348f3  push    rsi
0x1800348f4  push    rdi
0x1800348f5  sub     rsp, 40h
0x1800348f9  mov     rsi, rdx
0x1800348fc  mov     rbx, [rsp+58h]
0x180034901  cmp     qword ptr [r8+10h], 0
0x180034906  jnz     short loc_18003491B
0x180034908  mov     edi, 1Dh
0x18003490d  call    ?ImpersonateActiveUser@UserImpersonationHelpers@PrintCore@@SAJXZ; PrintCore::UserImpersonationHelpers::ImpersonateActiveUser(void)
0x180034912  lea     rcx, aImpersonateact; "ImpersonateActiveUser failed!"
0x180034919  jmp     short loc_18003492F
0x18003491b  mov     edi, 21h ; '!'
0x180034920  mov     rcx, r8
0x180034923  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(std::wstring const &)
0x180034928  lea     rcx, aImpersonateuse_1; "ImpersonateUser failed!"
0x18003492f  mov     [rsp+58h+ppv], rcx; int
0x180034934  mov     r9d, eax; char *
0x180034937  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\printscan"...
0x18003493e  mov     edx, edi; void *
0x180034940  mov     rcx, rbx; this
0x180034943  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034948  mov     byte ptr [rsp+58h+arg_8+1], 1
0x18003494d  mov     [rsp+58h+arg_10], 0
0x180034956  lea     rax, [rsp+58h+arg_10]
0x18003495b  mov     [rsp+58h+ppv], rax; ppv
0x180034960  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180034967  xor     r8d, r8d; pvReserved
0x18003496a  mov     edx, 100004h; dwClsContext
0x18003496f  lea     rcx, rclsid; rclsid
0x180034976  call    cs:__imp_CoGetClassObject
0x18003497c  mov     rcx, [rsp+58h]; this
0x180034981  lea     rdx, aCogetclassobje; "CoGetClassObject failed!"
0x180034988  mov     [rsp+58h+ppv], rdx; int
0x18003498d  mov     r9d, eax; char *
0x180034990  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\printscan"...
0x180034997  mov     edx, 29h ; ')'; void *
0x18003499c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800349a1  mov     [rsp+58h+arg_0], 0
0x1800349aa  mov     rdi, [rsp+58h+arg_10]
0x1800349af  mov     rax, [rdi]
0x1800349b2  mov     rbx, [rax+18h]
0x1800349b6  lea     rcx, [rsp+58h+arg_0]; this
0x1800349bb  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x1800349c0  mov     r9, rax
0x1800349c3  lea     r8, _GUID_8cd48002_1c68_54c7_9bcc_f361b0566ea9
0x1800349ca  xor     edx, edx
0x1800349cc  mov     rcx, rdi
0x1800349cf  mov     rax, rbx
0x1800349d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349d7  mov     rcx, [rsp+58h]; this
0x1800349dc  lea     rdx, aCreateinstance; "CreateInstance (IPrintSupportSessionMan"...
0x1800349e3  mov     [rsp+58h+ppv], rdx; int
0x1800349e8  mov     r9d, eax; char *
0x1800349eb  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\printscan"...
0x1800349f2  mov     edx, 2Ch ; ','; void *
0x1800349f7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800349fc  mov     rax, [rsp+58h+arg_0]
0x180034a01  mov     [rsp+58h+arg_0], 0
0x180034a0a  mov     [rsi], rax
0x180034a0d  lea     rcx, [rsp+58h+arg_0]; this
0x180034a12  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180034a17  nop
0x180034a18  lea     rcx, [rsp+58h+arg_10]
0x180034a1d  call    ??1?$com_ptr_t@UIClassFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IClassFactory,wil::err_exception_policy>::~com_ptr_t<IClassFactory,wil::err_exception_policy>(void)
0x180034a22  nop
0x180034a23  call    cs:__imp_RevertToSelf
0x180034a29  mov     rax, rsi
0x180034a2c  add     rsp, 40h
0x180034a30  pop     rdi
0x180034a31  pop     rsi
0x180034a32  pop     rbx
0x180034a33  retn
```
