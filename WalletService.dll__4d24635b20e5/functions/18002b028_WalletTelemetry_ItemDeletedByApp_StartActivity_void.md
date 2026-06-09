# WalletTelemetry::ItemDeletedByApp::StartActivity(void)

- ea: `0x18002b028`
- end: `0x18002b18b`
- name: `?StartActivity@ItemDeletedByApp@WalletTelemetry@@QEAAXXZ`
- size: `355`
- prototype: `void __fastcall(WalletTelemetry::ItemDeletedByApp *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002912c`

## callees

- `0x180001afc`
- `0x180001b28`
- `0x180005764`
- `0x180027f2c`
- `0x18002a708`
- `0x18002b028`
- `0x18002b194`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b0d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b0d6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002b08b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002b08b`

## pseudocode

```c
void __fastcall WalletTelemetry::ItemDeletedByApp::StartActivity(WalletTelemetry::ItemDeletedByApp *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp-9h] BYREF
  __int64 v12; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v14; // [rsp+60h] [rbp+27h]
  __int64 v15; // [rsp+68h] [rbp+2Fh]
  RTL_SRWLOCK **v16; // [rsp+70h] [rbp+37h]
  __int64 v17; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &v11);
  v2 = *((_QWORD *)this + 34);
  v3 = WalletLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  v5 = WalletLogging::Provider();
  v7 = v5;
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(v11) = CurrentThreadId;
    v12 = 0;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    v15 = 8;
    v17 = 4;
    v16 = &v11;
    v14 = &v12;
    tlgWriteTransfer_EventWriteTransfer(v7, qword_1800629D8, v9 + 8, v10, 4, v13);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((WalletTelemetry::ItemDeletedByApp *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002b028  mov     [rsp-8+arg_8], rbx
0x18002b02d  mov     [rsp-8+arg_10], rdi
0x18002b032  push    rbp
0x18002b033  lea     rbp, [rsp-57h]
0x18002b038  sub     rsp, 90h
0x18002b03f  mov     rax, cs:__security_cookie
0x18002b046  xor     rax, rsp
0x18002b049  mov     [rbp+57h+var_10], rax
0x18002b04d  lea     rdx, [rbp+57h+var_60]
0x18002b051  mov     rdi, rcx
0x18002b054  call    ?LockExclusive@?$ActivityBase@VWalletLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WalletLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b059  mov     rbx, [rdi+110h]
0x18002b060  call    ?Provider@WalletLogging@@SAPEBU_tlgProvider_t@@XZ; WalletLogging::Provider(void)
0x18002b065  mov     edx, [rax]
0x18002b067  cmp     edx, 5
0x18002b06a  jbe     short loc_18002B093
0x18002b06c  mov     rdx, 200000000000h
0x18002b076  mov     rcx, rax
0x18002b079  call    _tlgKeywordOn
0x18002b07e  test    al, al
0x18002b080  jz      short loc_18002B093
0x18002b082  lea     rdx, [rbx+8]; ActivityId
0x18002b086  mov     ecx, 3; ControlCode
0x18002b08b  call    cs:__imp_EventActivityIdControl
0x18002b091  jmp     short loc_18002B09A
0x18002b093  xorps   xmm0, xmm0
0x18002b096  movups  xmmword ptr [rbx+8], xmm0
0x18002b09a  lea     rcx, [rbp+57h+var_60]
0x18002b09e  mov     dword ptr [rbx], 1
0x18002b0a4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b0a9  call    ?Provider@WalletLogging@@SAPEBU_tlgProvider_t@@XZ; WalletLogging::Provider(void)
0x18002b0ae  mov     rbx, rax
0x18002b0b1  mov     ecx, [rax]
0x18002b0b3  cmp     ecx, 5
0x18002b0b6  jbe     loc_18002B158
0x18002b0bc  mov     rdx, 200000000000h
0x18002b0c6  mov     rcx, rax
0x18002b0c9  call    _tlgKeywordOn
0x18002b0ce  test    al, al
0x18002b0d0  jz      loc_18002B158
0x18002b0d6  call    cs:__imp_GetCurrentThreadId
0x18002b0dc  mov     r8, [rdi+110h]
0x18002b0e3  mov     dword ptr [rbp+57h+var_60], eax
0x18002b0e6  mov     [rbp+57h+var_58], 0
0x18002b0ee  cmp     byte ptr [r8+4], 0
0x18002b0f3  jz      short loc_18002B114
0x18002b0f5  lea     r9, [r8+18h]
0x18002b0f9  cmp     dword ptr [r9], 0
0x18002b0fd  jnz     short loc_18002B117
0x18002b0ff  cmp     dword ptr [r9+4], 0
0x18002b104  jnz     short loc_18002B117
0x18002b106  cmp     dword ptr [r9+8], 0
0x18002b10b  jnz     short loc_18002B117
0x18002b10d  cmp     dword ptr [r9+0Ch], 0
0x18002b112  jnz     short loc_18002B117
0x18002b114  xor     r9d, r9d
0x18002b117  mov     ecx, 4
0x18002b11c  mov     [rbp+57h+var_28], 8
0x18002b124  lea     rax, [rbp+57h+var_60]
0x18002b128  mov     [rbp+57h+var_18], rcx
0x18002b12c  mov     [rbp+57h+var_20], rax
0x18002b130  lea     rdx, qword_1800629D8
0x18002b137  lea     rax, [rbp+57h+var_58]
0x18002b13b  add     r8, 8
0x18002b13f  mov     [rbp+57h+var_30], rax
0x18002b143  lea     rax, [rbp+57h+var_50]
0x18002b147  mov     [rsp+90h+var_68], rax
0x18002b14c  mov     [rsp+90h+var_70], ecx
0x18002b150  mov     rcx, rbx
0x18002b153  call    _tlgWriteTransfer_EventWriteTransfer
0x18002b158  lea     rcx, [rdi+120h]; this
0x18002b15f  cmp     dword ptr [rcx+18h], 0
0x18002b163  jnz     short loc_18002B16A
0x18002b165  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002b16a  mov     rcx, [rbp+57h+var_10]
0x18002b16e  xor     rcx, rsp; StackCookie
0x18002b171  call    __security_check_cookie
0x18002b176  lea     r11, [rsp+90h+var_s0]
0x18002b17e  mov     rbx, [r11+18h]
0x18002b182  mov     rdi, [r11+20h]
0x18002b186  mov     rsp, r11
0x18002b189  pop     rbp
0x18002b18a  retn
```
