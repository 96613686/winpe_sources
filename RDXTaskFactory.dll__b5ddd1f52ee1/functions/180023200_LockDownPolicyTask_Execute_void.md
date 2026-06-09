# LockDownPolicyTask::Execute(void)

- ea: `0x180023200`
- end: `0x1800233c3`
- name: `?Execute@LockDownPolicyTask@@MEAAXXZ`
- size: `451`
- prototype: `void __fastcall(LockDownPolicyTask *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003e00`
- `0x180003e0c`
- `0x1800065dc`
- `0x18000c734`
- `0x18000e820`
- `0x1800102f0`
- `0x18001094c`
- `0x180012b30`
- `0x18001eedc`
- `0x1800212d4`
- `0x1800224a4`
- `0x18002290c`
- `0x180022bfc`
- `0x180023200`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002328e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002328e`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800232e8`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800232e8`

## string_xrefs

- `0x180023313`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall LockDownPolicyTask::Execute(LockDownPolicyTask *this)
{
  DWORD CurrentThreadId; // esi
  __int64 *v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdx
  int v7; // esi
  LockDownPolicyTask *v8; // rcx
  __int64 Singleton; // rax
  __int64 v10; // rdx
  _QWORD v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  LockDownPolicyTask *v12; // [rsp+40h] [rbp-C0h]
  _BYTE v13[152]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[3]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v15[208]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE pExceptionObject[224]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]
  __int64 v18; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v19; // [rsp+2C8h] [rbp+1C8h] BYREF
  LockDownPolicyTask *v20; // [rsp+2D0h] [rbp+1D0h]

  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 168LL))(*((_QWORD *)this + 8));
  v19 = 0;
  v14[0] = 0;
  v14[1] = 0;
  memset_0(v13, 0, sizeof(v13));
  v20 = this;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<enum RetailDemoTaskResult,0,0,12>>::AddRef(this);
  v11[0] = &v19;
  v11[1] = v13;
  v12 = this;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<enum RetailDemoTaskResult,0,0,12>>::AddRef(this);
  CurrentThreadId = GetCurrentThreadId();
  v3 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_637685181edf176e3c255b374eed632c_____lambda_637685181edf176e3c255b374eed632c___(
                    &v18,
                    v11);
  v4 = *v3;
  *v3 = 0;
  v5 = v18;
  if ( v18 )
  {
    v18 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v5);
  }
  v7 = SHTaskPoolQueueTask(1, 32, CurrentThreadId);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
      (const char *)(unsigned int)v7,
      v4);
  v8 = v12;
  if ( v12 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<void,1,2,12>>::Release(
      v12,
      v6);
  if ( v19 < 0 )
  {
    wil::ResultException::ResultException((wil::ResultException *)v15, (const struct wil::FailureInfo *)v13);
    wil::ResultException::ResultException(pExceptionObject, v15);
    throw (wil::ResultException *)pExceptionObject;
  }
  if ( *((_DWORD *)this + 20) == 1 )
    LockDownPolicyTask::ApplyAppLockerPolicy(this);
  Singleton = RetailDemo::Health::details::RetailDemoHealthTracker<1>::GetSingleton(v8, v6);
  LOBYTE(v18) = 1;
  RetailDemo::Health::details::RetailDemoScenarioEvents<1>::SetEventValueMember<bool>(Singleton, Singleton + 18, &v18);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<void,1,2,12>>::Release(
    this,
    v10);
  wil::details::shared_buffer::reset((wil::details::shared_buffer *)v14);
}

```

## disassembly

```asm
0x180023200  mov     [rsp-8+arg_18], rbx
0x180023205  push    rbp
0x180023206  push    rsi
0x180023207  push    rdi
0x180023208  lea     rbp, [rsp-1A0h]
0x180023210  sub     rsp, 2A0h
0x180023217  mov     rbx, rcx
0x18002321a  mov     rcx, [rcx+40h]
0x18002321e  mov     rax, [rcx]
0x180023221  mov     rax, [rax+0A8h]
0x180023228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002322d  mov     [rbp+1B0h+arg_8], 0
0x180023237  mov     [rbp+1B0h+var_1C8], 0
0x18002323f  mov     [rbp+1B0h+var_1C0], 0
0x180023247  xor     edx, edx; Val
0x180023249  mov     r8d, 98h; Size
0x18002324f  lea     rcx, [rsp+2B0h+var_260]; void *
0x180023254  call    memset_0
0x180023259  nop
0x18002325a  mov     [rbp+1B0h+arg_10], rbx
0x180023261  mov     rcx, rbx
0x180023264  call    ?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@V?$TaskBase@W4RetailDemoTaskResult@@$0A@$0A@$0M@@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<RetailDemoTaskResult,0,0,12>>::AddRef(void)
0x180023269  nop
0x18002326a  lea     rax, [rbp+1B0h+arg_8]
0x180023271  mov     [rsp+2B0h+var_280], rax
0x180023276  lea     rax, [rsp+2B0h+var_260]
0x18002327b  mov     [rsp+2B0h+var_278], rax
0x180023280  mov     [rsp+2B0h+var_270], rbx
0x180023285  mov     rcx, rbx
0x180023288  call    ?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@V?$TaskBase@W4RetailDemoTaskResult@@$0A@$0A@$0M@@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<RetailDemoTaskResult,0,0,12>>::AddRef(void)
0x18002328d  nop
0x18002328e  call    cs:__imp_GetCurrentThreadId
0x180023294  mov     esi, eax
0x180023296  lea     rdx, [rsp+2B0h+var_280]
0x18002329b  lea     rcx, [rbp+1B0h+arg_0]
0x1800232a2  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_637685181edf176e3c255b374eed632c_____lambda_637685181edf176e3c255b374eed632c___
0x1800232a7  mov     rdi, [rax]
0x1800232aa  mov     qword ptr [rax], 0
0x1800232b1  mov     rcx, [rbp+1B0h+arg_0]
0x1800232b8  test    rcx, rcx
0x1800232bb  jz      short loc_1800232CD
0x1800232bd  mov     [rbp+1B0h+arg_0], 0
0x1800232c8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800232cd  mov     [rsp+2B0h+var_288], 0
0x1800232d6  mov     qword ptr [rsp+2B0h+var_290], rdi; int
0x1800232db  xor     r9d, r9d
0x1800232de  mov     r8d, esi
0x1800232e1  lea     edx, [r9+20h]
0x1800232e5  lea     ecx, [rdx-1Fh]
0x1800232e8  call    cs:__imp_SHTaskPoolQueueTask
0x1800232ee  mov     esi, eax
0x1800232f0  test    rdi, rdi
0x1800232f3  jz      short loc_180023305
0x1800232f5  mov     rdx, [rdi]
0x1800232f8  mov     rcx, rdi
0x1800232fb  mov     rax, [rdx+10h]
0x1800232ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023304  nop
0x180023305  mov     rcx, [rbp+1B8h]; this
0x18002330c  test    esi, esi
0x18002330e  jns     short loc_180023325
0x180023310  mov     r9d, esi; char *
0x180023313  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002331a  mov     edx, 62h ; 'b'; void *
0x18002331f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023325  mov     rcx, [rsp+2B0h+var_270]
0x18002332a  test    rcx, rcx
0x18002332d  jz      short loc_180023334
0x18002332f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@V?$TaskBase@X$00$01$0M@@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<void,1,2,12>>::Release(void)
0x180023334  cmp     [rbp+1B0h+arg_8], 0
0x18002333b  jge     short loc_180023370
0x18002333d  lea     rdx, [rsp+2B0h+var_260]; struct wil::FailureInfo *
0x180023342  lea     rcx, [rbp+1B0h+var_1B0]; this
0x180023346  call    ??0ResultException@wil@@QEAA@AEBUFailureInfo@1@@Z; wil::ResultException::ResultException(wil::FailureInfo const &)
0x18002334b  nop
0x18002334c  lea     rdx, [rbp+1B0h+var_1B0]
0x180023350  lea     rcx, [rbp+1B0h+pExceptionObject]
0x180023357  call    ??0ResultException@wil@@QEAA@$$QEAV01@@Z; wil::ResultException::ResultException(wil::ResultException &&)
0x18002335c  lea     rdx, _TI2?AVResultException@wil@@; pThrowInfo
0x180023363  lea     rcx, [rbp+1B0h+pExceptionObject]; pExceptionObject
0x18002336a  call    _CxxThrowException_0
0x180023370  cmp     dword ptr [rbx+50h], 1
0x180023374  jnz     short loc_18002337E
0x180023376  mov     rcx, rbx; this
0x180023379  call    ?ApplyAppLockerPolicy@LockDownPolicyTask@@AEAAXXZ; LockDownPolicyTask::ApplyAppLockerPolicy(void)
0x18002337e  call    ?GetSingleton@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@CAAEAV1234@XZ; RetailDemo::Health::details::RetailDemoHealthTracker<1>::GetSingleton(void)
0x180023383  mov     byte ptr [rbp+1B0h+arg_0], 1
0x18002338a  lea     rdx, [rax+12h]
0x18002338e  lea     r8, [rbp+1B0h+arg_0]
0x180023395  mov     rcx, rax
0x180023398  call    ??$SetEventValueMember@_N@?$RetailDemoScenarioEvents@$00@details@Health@RetailDemo@@AEAAXAEA_NAEB_N@Z; RetailDemo::Health::details::RetailDemoScenarioEvents<1>::SetEventValueMember<bool>(bool &,bool const &)
0x18002339d  nop
0x18002339e  mov     rcx, rbx
0x1800233a1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@V?$TaskBase@X$00$01$0M@@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,TaskBase<void,1,2,12>>::Release(void)
0x1800233a6  nop
0x1800233a7  lea     rcx, [rbp+1B0h+var_1C8]; this
0x1800233ab  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1800233b0  mov     rbx, [rsp+2B0h+arg_18]
0x1800233b8  add     rsp, 2A0h
0x1800233bf  pop     rdi
0x1800233c0  pop     rsi
0x1800233c1  pop     rbp
0x1800233c2  retn
```
