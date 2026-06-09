# CMDMPushConfiguration::Initialize(ushort const *,EnrollmentEnrollType)

- ea: `0x140016a28`
- end: `0x140016bfd`
- name: `?Initialize@CMDMPushConfiguration@@QEAAJPEBGW4EnrollmentEnrollType@@@Z`
- size: `469`
- prototype: `int __high(const unsigned __int16 *, enum EnrollmentEnrollType)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x1400029c0`
- `0x140006bf4`
- `0x140009434`
- `0x140013134`
- `0x1400133c4`
- `0x1400134bc`
- `0x140016a28`
- `0x140016c14`
- `0x140017760`
- `0x140017878`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140016b12`
- `OLEAUT32!__imp_SysAllocString` at `0x140016b12`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140016aea`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140016aea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016b6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016b6f`

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
0x140016a28  mov     [rsp+arg_10], rbx
0x140016a2d  push    rbp
0x140016a2e  push    rsi
0x140016a2f  push    rdi
0x140016a30  sub     rsp, 1C0h
0x140016a37  mov     rax, cs:__security_cookie
0x140016a3e  xor     rax, rsp
0x140016a41  mov     [rsp+1D8h+var_28], rax
0x140016a49  mov     rsi, rdx
0x140016a4c  mov     rdi, rcx
0x140016a4f  lea     rdx, aInitializeacti; "InitializeActivity"
0x140016a56  mov     ebp, r8d
0x140016a59  lea     rcx, [rsp+1D8h+var_178]
0x140016a5e  call    ??0?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140016a63  lea     rax, ??_7InitializeActivity@MDMPushProvider@@6B@; const MDMPushProvider::InitializeActivity::`vftable'
0x140016a6a  lea     rcx, [rsp+1D8h+var_178]; this
0x140016a6f  mov     [rsp+1D8h+var_178], rax
0x140016a74  call    ?StartActivity@InitializeActivity@MDMPushProvider@@QEAAXXZ; MDMPushProvider::InitializeActivity::StartActivity(void)
0x140016a79  cmp     dword ptr [rdi], 0
0x140016a7c  jz      short loc_140016A8A
0x140016a7e  mov     ebx, 8000000Eh
0x140016a83  mov     edx, 7Fh
0x140016a88  jmp     short loc_140016A99
0x140016a8a  test    rsi, rsi
0x140016a8d  jnz     short loc_140016AB5
0x140016a8f  mov     ebx, 80070057h
0x140016a94  mov     edx, 80h; void *
0x140016a99  mov     rcx, [rsp+1D8h]; this
0x140016aa1  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140016aa8  mov     r9d, ebx; char *
0x140016aab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016ab0  jmp     loc_140016BCD
0x140016ab5  mov     [rsp+1D8h+pReserved3], 0; pReserved3
0x140016abe  xor     r9d, r9d; pReserved1
0x140016ac1  mov     [rsp+1D8h+dwCapabilities], 0; dwCapabilities
0x140016ac9  xor     r8d, r8d; asAuthSvc
0x140016acc  mov     [rsp+1D8h+pAuthList], 0; pAuthList
0x140016ad5  or      edx, 0FFFFFFFFh; cAuthSvc
0x140016ad8  mov     [rsp+1D8h+dwImpLevel], 3; dwImpLevel
0x140016ae0  xor     ecx, ecx; pSecDesc
0x140016ae2  mov     [rsp+1D8h+dwAuthnLevel], 1; dwAuthnLevel
0x140016aea  call    cs:__imp_CoInitializeSecurity
0x140016af1  nop     dword ptr [rax+rax+00h]
0x140016af6  test    eax, eax
0x140016af8  jns     short loc_140016B0F
0x140016afa  xor     ebx, ebx
0x140016afc  cmp     eax, 80010119h
0x140016b01  cmovnz  ebx, eax
0x140016b04  test    ebx, ebx
0x140016b06  jns     short loc_140016B0F
0x140016b08  mov     edx, 8Ch
0x140016b0d  jmp     short loc_140016A99
0x140016b0f  mov     rcx, rsi; psz
0x140016b12  call    cs:__imp_SysAllocString
0x140016b19  nop     dword ptr [rax+rax+00h]
0x140016b1e  mov     [rdi+8], rax
0x140016b22  test    rax, rax
0x140016b25  jnz     short loc_140016B36
0x140016b27  mov     ebx, 8007000Eh
0x140016b2c  mov     edx, 90h
0x140016b31  jmp     loc_140016A99
0x140016b36  mov     rdx, cs:?c_szTestHookLocation@@3PEBGEB; lpSubKey
0x140016b3d  lea     r8, aMdmpushtesthoo; "MDMPushTestHook"
0x140016b44  mov     [rsp+1D8h+pAuthList], 0; pcbData
0x140016b4d  mov     r9d, 18h; dwFlags
0x140016b53  mov     qword ptr [rsp+1D8h+dwImpLevel], 0; pvData
0x140016b5c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140016b63  mov     qword ptr [rsp+1D8h+dwAuthnLevel], 0; pdwType
0x140016b6c  mov     [rdi+10h], ebp
0x140016b6f  call    cs:__imp_RegGetValueW
0x140016b76  nop     dword ptr [rax+rax+00h]
0x140016b7b  test    eax, eax
0x140016b7d  jnz     short loc_140016BBB
0x140016b7f  lea     rdx, [rsp+1D8h+var_188]
0x140016b84  lea     rcx, [rsp+1D8h+var_178]
0x140016b89  call    ?LockExclusive@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140016b8e  mov     rbx, [rsp+1D8h+var_68]
0x140016b96  lea     rcx, [rbx+28h]; this
0x140016b9a  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x140016b9f  lea     rax, aTesthook; "TestHook"
0x140016ba6  lea     rcx, [rsp+1D8h+var_188]
0x140016bab  mov     [rbx+38h], rax
0x140016baf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140016bb4  mov     dword ptr [rdi+14h], 1
0x140016bbb  lea     rcx, [rsp+1D8h+var_178]
0x140016bc0  mov     dword ptr [rdi], 1
0x140016bc6  call    ?Stop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140016bcb  xor     ebx, ebx
0x140016bcd  lea     rcx, [rsp+1D8h+var_178]; this
0x140016bd2  call    ??1InitializeActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::InitializeActivity::~InitializeActivity(void)
0x140016bd7  mov     eax, ebx
0x140016bd9  mov     rcx, [rsp+1D8h+var_28]
0x140016be1  xor     rcx, rsp; StackCookie
0x140016be4  call    __security_check_cookie
0x140016be9  mov     rbx, [rsp+1D8h+arg_10]
0x140016bf1  add     rsp, 1C0h
0x140016bf8  pop     rdi
0x140016bf9  pop     rsi
0x140016bfa  pop     rbp
0x140016bfb  retn
```
