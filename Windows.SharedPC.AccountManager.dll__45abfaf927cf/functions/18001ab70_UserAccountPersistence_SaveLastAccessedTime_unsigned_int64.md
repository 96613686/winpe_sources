# UserAccountPersistence::SaveLastAccessedTime(unsigned __int64)

- ea: `0x18001ab70`
- end: `0x18001ac71`
- name: `?SaveLastAccessedTime@UserAccountPersistence@@UEAAJ_K@Z`
- size: `257`
- prototype: `__int64 __fastcall(UserAccountPersistence *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008a38`
- `0x18000c0f0`
- `0x18000c288`
- `0x18001a1b0`
- `0x18001a644`
- `0x18001a888`
- `0x18001ab70`
- `0x180026010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ac00`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ac00`

## string_xrefs

- `0x18001ac41`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountpersistence.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserAccountPersistence::SaveLastAccessedTime(UserAccountPersistence *this, volatile int *a2)
{
  __int64 v3; // rax
  unsigned int v4; // edi
  __int64 *v5; // rax
  __int64 v6; // rsi
  int v7; // edi
  __int64 v8; // rcx
  _BYTE v10[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  UserAccountPersistence *v13; // [rsp+60h] [rbp+8h] BYREF
  volatile int *v14; // [rsp+68h] [rbp+10h] BYREF

  v14 = a2;
  v13 = this;
  if ( this )
    Microsoft::WRL::Details::SafeUnknownIncrementReference((UserAccountPersistence *)((char *)this + 44), a2);
  v3 = lambda_44dec2ec29b2d12d628edc675583ab93_::_lambda_44dec2ec29b2d12d628edc675583ab93_(v10, &v14, &v13, this);
  v4 = UserAccountPersistence::s_ComTaskPoolContext;
  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_44dec2ec29b2d12d628edc675583ab93_____lambda_44dec2ec29b2d12d628edc675583ab93___(
                    &v13,
                    v3);
  v6 = *v5;
  *v5 = 0;
  if ( v13 )
  {
    v13 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v7 = SHTaskPoolQueueTask(3, 2, v4);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v8 = v11;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUserAccountPersistence,Microsoft::WRL::FtmBase>::Release(v8);
  }
  if ( v7 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountpersistence.cpp",
      (const char *)(unsigned int)v7,
      v6);
  if ( this )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUserAccountPersistence,Microsoft::WRL::FtmBase>::Release(this);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ab70  mov     rax, rsp
0x18001ab73  mov     [rax+18h], rbx
0x18001ab77  mov     [rax+20h], rsi
0x18001ab7b  mov     [rax+10h], rdx
0x18001ab7f  push    rdi
0x18001ab80  sub     rsp, 50h
0x18001ab84  mov     rbx, rcx
0x18001ab87  mov     [rax+8], rcx
0x18001ab8b  test    rcx, rcx
0x18001ab8e  jz      short loc_18001AB99
0x18001ab90  add     rcx, 2Ch ; ','; this
0x18001ab94  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18001ab99  mov     r9, rbx
0x18001ab9c  lea     r8, [rsp+58h+arg_0]
0x18001aba1  lea     rdx, [rsp+58h+arg_8]
0x18001aba6  lea     rcx, [rsp+58h+var_28]
0x18001abab  call    _lambda_44dec2ec29b2d12d628edc675583ab93____lambda_44dec2ec29b2d12d628edc675583ab93_
0x18001abb0  mov     edi, cs:?s_ComTaskPoolContext@UserAccountPersistence@@2KA; ulong UserAccountPersistence::s_ComTaskPoolContext
0x18001abb6  mov     rdx, rax
0x18001abb9  lea     rcx, [rsp+58h+arg_0]
0x18001abbe  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_44dec2ec29b2d12d628edc675583ab93_____lambda_44dec2ec29b2d12d628edc675583ab93___
0x18001abc3  mov     rsi, [rax]
0x18001abc6  mov     qword ptr [rax], 0
0x18001abcd  mov     rcx, [rsp+58h+arg_0]
0x18001abd2  test    rcx, rcx
0x18001abd5  jz      short loc_18001ABE5
0x18001abd7  mov     [rsp+58h+arg_0], 0
0x18001abe0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001abe5  mov     [rsp+58h+var_30], 0
0x18001abee  mov     qword ptr [rsp+58h+var_38], rsi; int
0x18001abf3  xor     r9d, r9d
0x18001abf6  mov     r8d, edi
0x18001abf9  lea     edx, [r9+2]
0x18001abfd  lea     ecx, [rdx+1]
0x18001ac00  call    cs:__imp_SHTaskPoolQueueTask
0x18001ac06  mov     edi, eax
0x18001ac08  test    rsi, rsi
0x18001ac0b  jz      short loc_18001AC1D
0x18001ac0d  mov     rdx, [rsi]
0x18001ac10  mov     rcx, rsi
0x18001ac13  mov     rax, [rdx+10h]
0x18001ac17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac1c  nop
0x18001ac1d  mov     rcx, [rsp+58h+var_20]
0x18001ac22  test    rcx, rcx
0x18001ac25  jz      short loc_18001AC35
0x18001ac27  mov     [rsp+58h+var_20], 0
0x18001ac30  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUserAccountPersistence@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUserAccountPersistence,Microsoft::WRL::FtmBase>::Release(void)
0x18001ac35  test    edi, edi
0x18001ac37  jns     short loc_18001AC52
0x18001ac39  mov     rcx, [rsp+58h]; this
0x18001ac3e  mov     r9d, edi; char *
0x18001ac41  lea     r8, aShellcommonShe; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ac48  mov     edx, 1Eh; void *
0x18001ac4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ac52  test    rbx, rbx
0x18001ac55  jz      short loc_18001AC5F
0x18001ac57  mov     rcx, rbx
0x18001ac5a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUserAccountPersistence@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUserAccountPersistence,Microsoft::WRL::FtmBase>::Release(void)
0x18001ac5f  mov     eax, edi
0x18001ac61  mov     rbx, [rsp+58h+arg_10]
0x18001ac66  mov     rsi, [rsp+58h+arg_18]
0x18001ac6b  add     rsp, 50h
0x18001ac6f  pop     rdi
0x18001ac70  retn
```
