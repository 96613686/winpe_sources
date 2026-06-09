# FileExplorerPerf::CommandHandlerInvokePerf::StartActivity(void)

- ea: `0x18001d9dc`
- end: `0x18001db12`
- name: `?StartActivity@CommandHandlerInvokePerf@FileExplorerPerf@@QEAAXXZ`
- size: `310`
- prototype: `void __fastcall(FileExplorerPerf::CommandHandlerInvokePerf *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800116bc`

## callees

- `0x180001ba8`
- `0x180004d44`
- `0x180006900`
- `0x18001aad8`
- `0x18001b908`
- `0x18001d9dc`
- `0x18001db18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001da5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001da5c`
- `ntdll!EtwEventActivityIdControl` at `0x18001da2b`
- `ntdll!EtwEventActivityIdControl` at `0x18001da2b`

## pseudocode

```c
void __fastcall FileExplorerPerf::CommandHandlerInvokePerf::StartActivity(
        FileExplorerPerf::CommandHandlerInvokePerf *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp-9h] BYREF
  __int64 v7; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v9; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  RTL_SRWLOCK **v11; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<FileExplorerPerf,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &v6);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)FileExplorerPerf::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EtwEventActivityIdControl(3, v2 + 8);
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  v3 = FileExplorerPerf::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    LODWORD(v6) = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    v11 = &v6;
    v12 = 4;
    v9 = &v7;
    v10 = 8;
    tlgWriteTransfer_EtwEventWriteTransfer((__int64)v3, (unsigned __int8 *)&dword_18005F454, v4 + 8, v5, 4, (__int64)v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FileExplorerPerf::CommandHandlerInvokePerf *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001d9dc  mov     [rsp-8+arg_8], rbx
0x18001d9e1  mov     [rsp-8+arg_10], rdi
0x18001d9e6  push    rbp
0x18001d9e7  lea     rbp, [rsp-57h]
0x18001d9ec  sub     rsp, 90h
0x18001d9f3  mov     rax, cs:__security_cookie
0x18001d9fa  xor     rax, rsp
0x18001d9fd  mov     [rbp+57h+var_10], rax
0x18001da01  mov     rbx, rcx
0x18001da04  lea     rdx, [rbp+57h+var_60]
0x18001da08  call    ?LockExclusive@?$ActivityBase@VFileExplorerPerf@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FileExplorerPerf,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001da0d  mov     rdi, [rbx+110h]
0x18001da14  call    ?Provider@FileExplorerPerf@@SAPEBU_tlgProvider_t@@XZ; FileExplorerPerf::Provider(void)
0x18001da19  mov     r8d, [rax]
0x18001da1c  cmp     r8d, 5
0x18001da20  jbe     short loc_18001DA33
0x18001da22  lea     rdx, [rdi+8]
0x18001da26  mov     ecx, 3
0x18001da2b  call    cs:__imp_EtwEventActivityIdControl
0x18001da31  jmp     short loc_18001DA3A
0x18001da33  xorps   xmm0, xmm0
0x18001da36  movups  xmmword ptr [rdi+8], xmm0
0x18001da3a  mov     dword ptr [rdi], 1
0x18001da40  lea     rcx, [rbp+57h+var_60]
0x18001da44  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001da49  call    ?Provider@FileExplorerPerf@@SAPEBU_tlgProvider_t@@XZ; FileExplorerPerf::Provider(void)
0x18001da4e  mov     rdi, rax
0x18001da51  mov     ecx, [rax]
0x18001da53  cmp     ecx, 5
0x18001da56  jbe     loc_18001DADE
0x18001da5c  call    cs:__imp_GetCurrentThreadId
0x18001da62  mov     dword ptr [rbp+57h+var_60], eax
0x18001da65  mov     [rbp+57h+var_58], 0
0x18001da6d  mov     r8, [rbx+110h]
0x18001da74  cmp     byte ptr [r8+4], 0
0x18001da79  jz      short loc_18001DA9A
0x18001da7b  lea     r9, [r8+18h]
0x18001da7f  cmp     dword ptr [r9], 0
0x18001da83  jnz     short loc_18001DA9D
0x18001da85  cmp     dword ptr [r9+4], 0
0x18001da8a  jnz     short loc_18001DA9D
0x18001da8c  cmp     dword ptr [r9+8], 0
0x18001da91  jnz     short loc_18001DA9D
0x18001da93  cmp     dword ptr [r9+0Ch], 0
0x18001da98  jnz     short loc_18001DA9D
0x18001da9a  xor     r9d, r9d
0x18001da9d  lea     rax, [rbp+57h+var_60]
0x18001daa1  mov     [rbp+57h+var_20], rax
0x18001daa5  mov     ecx, 4
0x18001daaa  mov     [rbp+57h+var_18], rcx
0x18001daae  lea     rax, [rbp+57h+var_58]
0x18001dab2  mov     [rbp+57h+var_30], rax
0x18001dab6  mov     [rbp+57h+var_28], 8
0x18001dabe  add     r8, 8
0x18001dac2  lea     rax, [rbp+57h+var_50]
0x18001dac6  mov     [rsp+90h+var_68], rax
0x18001dacb  mov     [rsp+90h+var_70], ecx
0x18001dacf  lea     rdx, dword_18005F454
0x18001dad6  mov     rcx, rdi
0x18001dad9  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18001dade  lea     rcx, [rbx+120h]; this
0x18001dae5  cmp     dword ptr [rcx+18h], 0
0x18001dae9  jnz     short loc_18001DAF1
0x18001daeb  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001daf0  nop
0x18001daf1  mov     rcx, [rbp+57h+var_10]
0x18001daf5  xor     rcx, rsp; StackCookie
0x18001daf8  call    __security_check_cookie
0x18001dafd  lea     r11, [rsp+90h+var_s0]
0x18001db05  mov     rbx, [r11+18h]
0x18001db09  mov     rdi, [r11+20h]
0x18001db0d  mov     rsp, r11
0x18001db10  pop     rbp
0x18001db11  retn
```
