# winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>>::put_Completed(void *)

- ea: `0x1800097e0`
- end: `0x1800098e2`
- name: `?put_Completed@?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@@impl@winrt@@UEAAHPEAX@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001fea`
- `0x180002088`
- `0x180002094`
- `0x180005b18`
- `0x180005be0`
- `0x1800063c8`
- `0x180009224`
- `0x1800097e0`
- `0x18000a014`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>>::put_Completed(
        unsigned __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  RTL_SRWLOCK *v4; // rdi
  __int64 *v5; // rsi
  __int64 *v6; // rbx
  __int64 v7; // rdx
  const struct winrt::impl::slim_source_location *v9; // rax
  __int64 *v10; // rdx
  __int64 v11; // [rsp+0h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v13[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = a2;
  v3 = (a1 - 16) & ((unsigned __int128)-(__int128)a1 >> 64);
  v4 = (RTL_SRWLOCK *)(v3 + 72);
  v14 = v3 + 72;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(v3 + 72));
  if ( *(_BYTE *)(v3 + 100) )
  {
    v9 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v13);
    winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(
      (winrt::hresult_illegal_delegate_assignment *)pExceptionObject,
      v9);
    try
    {
      throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
    }
    catch ( ... )
    {
      v10 = &v11;
      *((_DWORD *)v10 + 24) = *(_DWORD *)winrt::to_hresult(v10 + 12);
      return (unsigned int)v14;
    }
  }
  *(_BYTE *)(v3 + 100) = 1;
  LODWORD(v14) = *(_DWORD *)(v3 + 96);
  if ( (_DWORD)v14 )
  {
    ReleaseSRWLockExclusive_0((PSRWLOCK)(v3 + 72));
    if ( a2 )
      winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>,void>,enum winrt::Windows::Foundation::AsyncStatus>(
        &v15,
        v3,
        &v14);
  }
  else
  {
    v5 = (__int64 *)winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>>(
                      &v14,
                      &v15);
    v6 = (__int64 *)(v3 + 80);
    if ( v6 != v5 )
    {
      if ( *v6 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
      v7 = *v5;
      *v5 = 0;
      *v6 = v7;
    }
    if ( v14 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
    ReleaseSRWLockExclusive_0(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800097e0  mov     r11, rsp
0x1800097e3  mov     [r11+18h], rbx
0x1800097e7  mov     [r11+20h], rsi
0x1800097eb  mov     [r11+10h], rdx
0x1800097ef  push    rdi
0x1800097f0  sub     rsp, 50h
0x1800097f4  mov     rsi, rdx
0x1800097f7  lea     rax, [rcx-10h]
0x1800097fb  neg     rcx
0x1800097fe  sbb     rbx, rbx
0x180009801  and     rbx, rax
0x180009804  lea     rdi, [rbx+48h]
0x180009808  mov     [r11+8], rdi
0x18000980c  mov     rcx, rdi; SRWLock
0x18000980f  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180009814  nop
0x180009815  cmp     byte ptr [rbx+64h], 0
0x180009819  jnz     loc_1800098B8
0x18000981f  mov     byte ptr [rbx+64h], 1
0x180009823  mov     eax, [rbx+60h]
0x180009826  mov     dword ptr [rsp+58h+arg_0], eax
0x18000982a  test    eax, eax
0x18000982c  jnz     short loc_180009881
0x18000982e  lea     rdx, [rsp+58h+arg_8]
0x180009833  lea     rcx, [rsp+58h+arg_0]
0x180009838  call    ??$make_agile_delegate@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@I@Foundation@Windows@1@AEBU2341@@Z; winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint> const &)
0x18000983d  mov     rsi, rax
0x180009840  add     rbx, 50h ; 'P'
0x180009844  cmp     rbx, rax
0x180009847  jz      short loc_180009864
0x180009849  cmp     qword ptr [rbx], 0
0x18000984d  jz      short loc_180009857
0x18000984f  mov     rcx, rbx
0x180009852  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009857  mov     rdx, [rsi]
0x18000985a  mov     qword ptr [rsi], 0
0x180009861  mov     [rbx], rdx
0x180009864  cmp     [rsp+58h+arg_0], 0
0x18000986a  jz      short loc_180009877
0x18000986c  lea     rcx, [rsp+58h+arg_0]
0x180009871  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009876  nop
0x180009877  mov     rcx, rdi; SRWLock
0x18000987a  call    ReleaseSRWLockExclusive_0
0x18000987f  jmp     short loc_1800098A0
0x180009881  mov     rcx, rdi; SRWLock
0x180009884  call    ReleaseSRWLockExclusive_0
0x180009889  test    rsi, rsi
0x18000988c  jz      short loc_1800098A0
0x18000988e  lea     r8, [rsp+58h+arg_0]
0x180009893  mov     rdx, rbx
0x180009896  lea     rcx, [rsp+58h+arg_8]
0x18000989b  call    ??$invoke@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@U?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@X@impl@4@W4AsyncStatus@234@@impl@winrt@@YA_NAEBU?$AsyncOperationCompletedHandler@I@Foundation@Windows@1@AEBU?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@X@01@AEBW4AsyncStatus@341@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>,void>,winrt::Windows::Foundation::AsyncStatus>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint> const &,winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>,void> const &,winrt::Windows::Foundation::AsyncStatus const &)
0x1800098a0  xor     eax, eax
0x1800098a2  jmp     short loc_1800098A8
0x1800098a4  mov     eax, dword ptr [rsp+58h+arg_0]
0x1800098a8  mov     rbx, [rsp+58h+arg_10]
0x1800098ad  mov     rsi, [rsp+58h+arg_18]
0x1800098b2  add     rsp, 50h
0x1800098b6  pop     rdi
0x1800098b7  retn
0x1800098b8  lea     rcx, [rsp+58h+var_20]
0x1800098bd  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800098c2  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800098c5  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800098ca  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::impl::slim_source_location const &)
0x1800098cf  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x1800098d6  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800098db  call    _CxxThrowException_0
```
