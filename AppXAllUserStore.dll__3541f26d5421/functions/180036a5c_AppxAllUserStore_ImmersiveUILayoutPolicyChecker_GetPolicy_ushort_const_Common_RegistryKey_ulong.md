# AppxAllUserStore::ImmersiveUILayoutPolicyChecker::GetPolicy(ushort const *,Common::RegistryKey *,ulong &)

- ea: `0x180036a5c`
- end: `0x180036ba9`
- name: `?GetPolicy@ImmersiveUILayoutPolicyChecker@AppxAllUserStore@@QEAAJPEBGPEAVRegistryKey@Common@@AEAK@Z`
- size: `333`
- prototype: `__int64 __fastcall(AppxAllUserStore::ImmersiveUILayoutPolicyChecker *__hidden this, const unsigned __int16 *, struct Common::RegistryKey *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038560`

## callees

- `0x18000d7b0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b8d0`
- `0x18001f760`
- `0x18001f780`
- `0x180036a5c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036abd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036abd`

## string_xrefs

- `0x180036a7f`: `CachedPolicies`
- `0x180036b6f`: `CachedPolicies`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::ImmersiveUILayoutPolicyChecker::GetPolicy(
        AppxAllUserStore::ImmersiveUILayoutPolicyChecker *this,
        const unsigned __int16 *a2,
        struct Common::RegistryKey *a3,
        unsigned int *a4)
{
  int v9; // ebx
  struct Common::StringBuffer *v10; // rdx
  char v11; // al
  int IUIPolicyDLL; // eax
  __int64 v13; // rdx
  LSTATUS v14; // eax
  int v15; // [rsp+20h] [rbp-58h]
  const char *v16; // [rsp+28h] [rbp-50h]
  unsigned int v17[18]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v17[0] = 0;
  if ( Common::RegistryKey::GetUInt32Value(a3, L"CachedPolicies", v17) >= 0 )
  {
    *a4 = v17[0];
    return 0;
  }
  if ( *((_BYTE *)this + 56) )
    goto LABEL_12;
  v9 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v11 = *((_BYTE *)this + 56);
  *(_QWORD *)v17 = this;
  if ( v11
    || (IUIPolicyDLL = AppxAllUserStore::ImmersiveUILayoutPolicyChecker::LoadIUIPolicyDLL(this, v10),
        v9 = IUIPolicyDLL,
        IUIPolicyDLL >= 0) )
  {
    *((_BYTE *)this + 56) = 1;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\immersiveuilayoutpolicychecker.cpp",
      (const char *)(unsigned int)IUIPolicyDLL);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v17);
  if ( v9 >= 0 )
  {
LABEL_12:
    v9 = (*((__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))this + 9))(
           *((_QWORD *)this + 6),
           a2,
           a4);
    if ( v9 >= 0 )
    {
      v17[0] = *a4;
      v14 = Common::RegistryKey::SetValue((HKEY *)a3, L"CachedPolicies", (const BYTE *)v17, 4u, 4u);
      v9 = v14;
      if ( v14 >= 0 )
        return 0;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x74,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\immersiveuilayoutpolicychecker.cpp",
        (const char *)(unsigned int)v14);
      v13 = 88;
    }
    else
    {
      v13 = 85;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\immersiveuilayoutpolicychecker.cpp",
      (const char *)(unsigned int)v9,
      v15);
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\immersiveuilayoutpolicychecker.cpp",
      (const char *)(unsigned int)v9,
      (int)"Could not query Immersive UI policies.",
      v16);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180036a5c  push    rbx
0x180036a5e  push    rbp
0x180036a5f  push    rsi
0x180036a60  push    rdi
0x180036a61  push    r14
0x180036a63  push    r15
0x180036a65  sub     rsp, 48h
0x180036a69  mov     rbp, r8
0x180036a6c  mov     [rsp+78h+var_48], 0
0x180036a74  mov     r14, rdx
0x180036a77  lea     r8, [rsp+78h+var_48]; unsigned int *
0x180036a7c  mov     rdi, rcx
0x180036a7f  lea     rdx, aCachedpolicies; "CachedPolicies"
0x180036a86  mov     rcx, rbp; this
0x180036a89  mov     rsi, r9
0x180036a8c  call    ?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z; Common::RegistryKey::GetUInt32Value(ushort const *,uint *)
0x180036a91  test    eax, eax
0x180036a93  js      short loc_180036AAA
0x180036a95  mov     eax, [rsp+78h+var_48]
0x180036a99  mov     [rsi], eax
0x180036a9b  xor     eax, eax
0x180036a9d  add     rsp, 48h
0x180036aa1  pop     r15
0x180036aa3  pop     r14
0x180036aa5  pop     rdi
0x180036aa6  pop     rsi
0x180036aa7  pop     rbp
0x180036aa8  pop     rbx
0x180036aa9  retn
0x180036aaa  mov     al, [rdi+38h]
0x180036aad  lea     r15, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\appxalluserst"...
0x180036ab4  test    al, al
0x180036ab6  jnz     short loc_180036B2E
0x180036ab8  mov     rcx, rdi; lpCriticalSection
0x180036abb  xor     ebx, ebx
0x180036abd  call    cs:__imp_EnterCriticalSection
0x180036ac3  mov     al, [rdi+38h]
0x180036ac6  mov     qword ptr [rsp+78h+var_48], rdi
0x180036acb  test    al, al
0x180036acd  jnz     short loc_180036AF4
0x180036acf  mov     rcx, rdi; this
0x180036ad2  call    ?LoadIUIPolicyDLL@ImmersiveUILayoutPolicyChecker@AppxAllUserStore@@AEAAJXZ; AppxAllUserStore::ImmersiveUILayoutPolicyChecker::LoadIUIPolicyDLL(void)
0x180036ad7  mov     ebx, eax
0x180036ad9  test    eax, eax
0x180036adb  jns     short loc_180036AF4
0x180036add  mov     rcx, [rsp+78h]; this
0x180036ae2  mov     r9d, eax; char *
0x180036ae5  mov     r8, r15; unsigned int
0x180036ae8  mov     edx, 14h; void *
0x180036aed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036af2  jmp     short loc_180036AF8
0x180036af4  mov     byte ptr [rdi+38h], 1
0x180036af8  lea     rcx, [rsp+78h+var_48]
0x180036afd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180036b02  test    ebx, ebx
0x180036b04  jns     short loc_180036B2E
0x180036b06  mov     rcx, [rsp+78h]; this
0x180036b0b  lea     rax, aCouldNotQueryI; "Could not query Immersive UI policies."
0x180036b12  mov     r9d, ebx; char *
0x180036b15  mov     qword ptr [rsp+78h+var_58], rax; int
0x180036b1a  mov     r8, r15; unsigned int
0x180036b1d  mov     edx, 52h ; 'R'; void *
0x180036b22  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036b27  mov     eax, ebx
0x180036b29  jmp     loc_180036A9D
0x180036b2e  mov     rcx, [rdi+30h]
0x180036b32  mov     r8, rsi
0x180036b35  mov     rax, [rdi+48h]
0x180036b39  mov     rdx, r14
0x180036b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b41  mov     ebx, eax
0x180036b43  test    eax, eax
0x180036b45  jns     short loc_180036B5E
0x180036b47  mov     edx, 55h ; 'U'; void *
0x180036b4c  mov     rcx, [rsp+78h]; this
0x180036b51  mov     r8, r15; unsigned int
0x180036b54  mov     r9d, ebx; char *
0x180036b57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b5c  jmp     short loc_180036B27
0x180036b5e  mov     eax, [rsi]
0x180036b60  lea     r8, [rsp+78h+var_48]; void *
0x180036b65  mov     r9d, 4; unsigned int
0x180036b6b  mov     [rsp+78h+var_48], eax
0x180036b6f  lea     rdx, aCachedpolicies; "CachedPolicies"
0x180036b76  mov     [rsp+78h+var_58], r9d; int
0x180036b7b  mov     rcx, rbp; this
0x180036b7e  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x180036b83  mov     ebx, eax
0x180036b85  test    eax, eax
0x180036b87  jns     loc_180036A9B
0x180036b8d  mov     rcx, [rsp+78h]; this
0x180036b92  mov     r9d, eax; char *
0x180036b95  mov     r8, r15; unsigned int
0x180036b98  mov     edx, 74h ; 't'; void *
0x180036b9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036ba2  mov     edx, 58h ; 'X'
0x180036ba7  jmp     short loc_180036B4C
```
