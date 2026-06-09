# CMDMPushConfiguration::Initialize(ushort const *,EnrollmentEnrollType)

- ea: `0x140015d98`
- end: `0x140015f5a`
- name: `?Initialize@CMDMPushConfiguration@@QEAAJPEBGW4EnrollmentEnrollType@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x140002930`
- `0x140006984`
- `0x14000905c`
- `0x14001281c`
- `0x140012a8c`
- `0x140012b7c`
- `0x140015d98`
- `0x140015f70`
- `0x140016ab0`
- `0x140016bbc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140015e7c`
- `OLEAUT32!__imp_SysAllocString` at `0x140015e7c`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140015e5a`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140015e5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015ed3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015ed3`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::Initialize(__int64 a1, const OLECHAR *a2, int a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  BSTR v9; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rbx
  int dwAuthnLevel; // [rsp+20h] [rbp-1B8h]
  _BYTE v14[16]; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v15[34]; // [rsp+60h] [rbp-178h] BYREF
  __int64 v16; // [rsp+170h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "InitializeActivity");
  v15[0] = &MDMPushProvider::InitializeActivity::`vftable';
  MDMPushProvider::InitializeActivity::StartActivity((MDMPushProvider::InitializeActivity *)v15);
  if ( *(_DWORD *)a1 )
  {
    v6 = -2147483634;
    v7 = 127;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)v6,
      dwAuthnLevel);
    goto LABEL_16;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 128;
    goto LABEL_5;
  }
  v8 = CoInitializeSecurity(0, -1, 0, 0, 1u, 3u, 0, 0, 0);
  if ( v8 < 0 )
  {
    v6 = 0;
    if ( v8 != -2147417831 )
      v6 = v8;
    if ( v6 < 0 )
    {
      v7 = 140;
      goto LABEL_5;
    }
  }
  v9 = SysAllocString(a2);
  *(_QWORD *)(a1 + 8) = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v7 = 144;
    goto LABEL_5;
  }
  v10 = c_szTestHookLocation;
  *(_DWORD *)(a1 + 16) = a3;
  if ( !RegGetValueW(HKEY_LOCAL_MACHINE, v10, L"MDMPushTestHook", 0x18u, 0, 0, 0) )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v15, v14);
    v11 = v16;
    wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)(v16 + 40));
    *(_QWORD *)(v11 + 56) = L"TestHook";
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v14);
    *(_DWORD *)(a1 + 20) = 1;
  }
  *(_DWORD *)a1 = 1;
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v15);
  v6 = 0;
LABEL_16:
  MDMPushProvider::InitializeActivity::~InitializeActivity((MDMPushProvider::InitializeActivity *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140015d98  mov     [rsp+arg_10], rbx
0x140015d9d  push    rbp
0x140015d9e  push    rsi
0x140015d9f  push    rdi
0x140015da0  sub     rsp, 1C0h
0x140015da7  mov     rax, cs:__security_cookie
0x140015dae  xor     rax, rsp
0x140015db1  mov     [rsp+1D8h+var_28], rax
0x140015db9  mov     rsi, rdx
0x140015dbc  mov     rdi, rcx
0x140015dbf  lea     rdx, aInitializeacti; "InitializeActivity"
0x140015dc6  mov     ebp, r8d
0x140015dc9  lea     rcx, [rsp+1D8h+var_178]
0x140015dce  call    ??0?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140015dd3  lea     rax, ??_7InitializeActivity@MDMPushProvider@@6B@; const MDMPushProvider::InitializeActivity::`vftable'
0x140015dda  lea     rcx, [rsp+1D8h+var_178]; this
0x140015ddf  mov     [rsp+1D8h+var_178], rax
0x140015de4  call    ?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ; MDMPushProvider::InitializeActivity::StartActivity(void)
0x140015de9  cmp     dword ptr [rdi], 0
0x140015dec  jz      short loc_140015DFA
0x140015dee  mov     ebx, 8000000Eh
0x140015df3  mov     edx, 7Fh
0x140015df8  jmp     short loc_140015E09
0x140015dfa  test    rsi, rsi
0x140015dfd  jnz     short loc_140015E25
0x140015dff  mov     ebx, 80070057h
0x140015e04  mov     edx, 80h; void *
0x140015e09  mov     rcx, [rsp+1D8h]; this
0x140015e11  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140015e18  mov     r9d, ebx; char *
0x140015e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015e20  jmp     loc_140015F2B
0x140015e25  mov     [rsp+1D8h+pReserved3], 0; pReserved3
0x140015e2e  xor     r9d, r9d; pReserved1
0x140015e31  mov     [rsp+1D8h+dwCapabilities], 0; dwCapabilities
0x140015e39  xor     r8d, r8d; asAuthSvc
0x140015e3c  mov     [rsp+1D8h+pAuthList], 0; pAuthList
0x140015e45  or      edx, 0FFFFFFFFh; cAuthSvc
0x140015e48  mov     [rsp+1D8h+dwImpLevel], 3; dwImpLevel
0x140015e50  xor     ecx, ecx; pSecDesc
0x140015e52  mov     [rsp+1D8h+dwAuthnLevel], 1; dwAuthnLevel
0x140015e5a  call    cs:__imp_CoInitializeSecurity
0x140015e60  test    eax, eax
0x140015e62  jns     short loc_140015E79
0x140015e64  xor     ebx, ebx
0x140015e66  cmp     eax, 80010119h
0x140015e6b  cmovnz  ebx, eax
0x140015e6e  test    ebx, ebx
0x140015e70  jns     short loc_140015E79
0x140015e72  mov     edx, 8Ch
0x140015e77  jmp     short loc_140015E09
0x140015e79  mov     rcx, rsi; psz
0x140015e7c  call    cs:__imp_SysAllocString
0x140015e82  mov     [rdi+8], rax
0x140015e86  test    rax, rax
0x140015e89  jnz     short loc_140015E9A
0x140015e8b  mov     ebx, 8007000Eh
0x140015e90  mov     edx, 90h
0x140015e95  jmp     loc_140015E09
0x140015e9a  mov     rdx, cs:?c_szTestHookLocation@@3PEBGEB; lpSubKey
0x140015ea1  lea     r8, aMdmpushtesthoo; "MDMPushTestHook"
0x140015ea8  mov     [rsp+1D8h+pAuthList], 0; pcbData
0x140015eb1  mov     r9d, 18h; dwFlags
0x140015eb7  mov     qword ptr [rsp+1D8h+dwImpLevel], 0; pvData
0x140015ec0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140015ec7  mov     qword ptr [rsp+1D8h+dwAuthnLevel], 0; pdwType
0x140015ed0  mov     [rdi+10h], ebp
0x140015ed3  call    cs:__imp_RegGetValueW
0x140015ed9  test    eax, eax
0x140015edb  jnz     short loc_140015F19
0x140015edd  lea     rdx, [rsp+1D8h+var_188]
0x140015ee2  lea     rcx, [rsp+1D8h+var_178]
0x140015ee7  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140015eec  mov     rbx, [rsp+1D8h+var_68]
0x140015ef4  lea     rcx, [rbx+28h]; this
0x140015ef8  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x140015efd  lea     rax, aTesthook; "TestHook"
0x140015f04  lea     rcx, [rsp+1D8h+var_188]
0x140015f09  mov     [rbx+38h], rax
0x140015f0d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140015f12  mov     dword ptr [rdi+14h], 1
0x140015f19  lea     rcx, [rsp+1D8h+var_178]
0x140015f1e  mov     dword ptr [rdi], 1
0x140015f24  call    ?Stop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140015f29  xor     ebx, ebx
0x140015f2b  lea     rcx, [rsp+1D8h+var_178]; this
0x140015f30  call    ??1InitializeActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::InitializeActivity::~InitializeActivity(void)
0x140015f35  mov     eax, ebx
0x140015f37  mov     rcx, [rsp+1D8h+var_28]
0x140015f3f  xor     rcx, rsp; StackCookie
0x140015f42  call    __security_check_cookie
0x140015f47  mov     rbx, [rsp+1D8h+arg_10]
0x140015f4f  add     rsp, 1C0h
0x140015f56  pop     rdi
0x140015f57  pop     rsi
0x140015f58  pop     rbp
0x140015f59  retn
```
