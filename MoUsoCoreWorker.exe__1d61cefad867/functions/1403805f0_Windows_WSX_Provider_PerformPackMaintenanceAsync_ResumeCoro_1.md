# Windows::WSX::Provider::PerformPackMaintenanceAsync$_ResumeCoro$1

- ea: `0x1403805f0`
- end: `0x140380a90`
- name: `Windows::WSX::Provider::PerformPackMaintenanceAsync$_ResumeCoro$1`
- size: `1184`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14034bd50`
- `0x1403805e0`

## callees

- `0x14004045c`
- `0x140041318`
- `0x1400413a8`
- `0x14013ddc8`
- `0x14013e2d4`
- `0x14034b87c`
- `0x14034dedc`
- `0x140379070`
- `0x1403790cc`
- `0x14037b4b0`
- `0x14037f919`
- `0x1403805f0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x1403807ef`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x140380924`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x1403807ef`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x140380924`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140380726`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140380726`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1403806db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1403806db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140380972`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140380972`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1403806a8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1403806a8`

## string_xrefs

- `0x1403806ba`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140380984`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140380743`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\WSXProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::WSX::Provider::PerformPackMaintenanceAsync__ResumeCoro_1(_WORD *Block)
{
  RTL_SRWLOCK *v2; // r14
  volatile signed __int32 *Ptr; // rax
  void **v4; // rcx
  void *v5; // rcx
  const char *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  PVOID v11; // rcx
  int v12; // eax
  volatile __int64 *v13; // rbx
  void (**v14)(void); // rax
  void (**v15)(void); // rax
  int v16; // eax
  volatile __int64 *v17; // rbx
  void *v18; // rcx
  const char *v19; // r9
  void (**v20)(void); // rax
  void (**v21)(void); // rax
  int v22; // [rsp+20h] [rbp-C8h]
  _BYTE pExceptionObject[24]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v24; // [rsp+78h] [rbp-70h]
  void **v25; // [rsp+80h] [rbp-68h]
  __int64 v26; // [rsp+88h] [rbp-60h]
  void *v27; // [rsp+90h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  LOWORD(v22) = Block[16];
  switch ( (__int16)v22 )
  {
    case -1:
    case 3:
      goto LABEL_56;
    case 2:
      *((_QWORD *)Block + 6) = 0;
      v2 = (RTL_SRWLOCK *)*((_QWORD *)Block + 3);
      Ptr = (volatile signed __int32 *)v2[4].Ptr;
      if ( Ptr )
        _InterlockedAdd(Ptr + 2, 1u);
      v4 = (void **)v2[3].Ptr;
      *((_QWORD *)Block + 18) = v4;
      *((_QWORD *)Block + 5) = v4;
      *((RTL_SRWLOCK *)Block + 6) = v2[4];
      if ( v4 )
      {
        v25 = v4;
        v5 = *v4;
      }
      else
      {
        v5 = 0;
      }
      if ( !ResetEvent(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9CC,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v6);
      *((_QWORD *)Block + 7) = 0;
      AcquireSRWLockExclusive(v2 + 1);
      *((_QWORD *)Block + 15) = 0;
      WINRT_IMPL_GetSystemTimePreciseAsFileTime(Block + 60);
      v27 = (void *)*((_QWORD *)Block + 15);
      v2[2].Ptr = v27;
      *((_DWORD *)Block + 16) = *((_DWORD *)Block + 30);
      v27 = (void *)*((_QWORD *)Block + 15);
      *((_DWORD *)Block + 17) = HIDWORD(v27);
      *((_QWORD *)Block + 7) = *((_QWORD *)Block + 8);
      if ( v2 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v2 + 1);
      v10 = anonymous_namespace_::SHRegSetFILETIME(v8, v7, v9, Block + 28);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x173,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\WSXProvider.cpp",
          (const char *)(unsigned int)v10,
          v22);
      v11 = v2[6].Ptr;
      if ( !v11 )
        goto LABEL_45;
      *((_QWORD *)Block + 16) = 0;
      v12 = (*(__int64 (__fastcall **)(PVOID, char *))(*(_QWORD *)v11 + 72LL))(v11, (char *)Block + 128);
      if ( v12 < 0 )
        winrt::throw_hresult((unsigned int)v12);
      v24 = *((_QWORD *)Block + 16);
      *((_QWORD *)Block + 9) = v24;
      *((_QWORD *)Block + 10) = 0;
      *((_QWORD *)Block + 11) = Block + 36;
      *((_QWORD *)Block + 12) = 0;
      *((_BYTE *)Block + 104) = 1;
      if ( winrt_suspend_handler )
        winrt_suspend_handler(Block + 40);
      Block[16] = 4;
      if ( !(unsigned __int8)winrt::impl::notify_awaiter<winrt::Windows::Foundation::IAsyncAction>::await_suspend<std::coroutine_traits<winrt::fire_and_forget,Windows::WSX::Provider &>::promise_type>(
                               Block + 40,
                               Block) )
      {
LABEL_31:
        if ( winrt_resume_handler )
          winrt_resume_handler(Block + 40);
        if ( *((int *)Block + 25) < 0 )
          winrt::throw_hresult(*((unsigned int *)Block + 25));
        if ( *((_DWORD *)Block + 24) == 2 )
        {
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject);
          throw (winrt::hresult_canceled *)pExceptionObject;
        }
        v16 = (*(__int64 (__fastcall **)(_QWORD))(***((_QWORD ***)Block + 11) + 64LL))(**((_QWORD **)Block + 11));
        if ( v16 < 0 )
          winrt::throw_hresult((unsigned int)v16);
        if ( *((_QWORD *)Block + 10) )
        {
          v17 = (volatile __int64 *)*((_QWORD *)Block + 10);
          while ( _InterlockedExchange64(v17, 0) == 1 )
            SwitchToThread();
        }
        if ( *((_QWORD *)Block + 9) )
          winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Block + 36);
LABEL_45:
        if ( *((_QWORD *)Block + 18) )
        {
          v25 = (void **)*((_QWORD *)Block + 5);
          v18 = *v25;
        }
        else
        {
          v18 = 0;
        }
        if ( !SetEvent(v18) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9C7,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            v19);
        if ( *((_QWORD *)Block + 6) )
        {
          v26 = *((_QWORD *)Block + 6);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 8), 0xFFFFFFFF) == 1 )
          {
            v26 = *((_QWORD *)Block + 6);
            v20 = *(void (***)(void))v26;
            v26 = *((_QWORD *)Block + 6);
            (*v20)();
            v26 = *((_QWORD *)Block + 6);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 12), 0xFFFFFFFF) == 1 )
            {
              v26 = *((_QWORD *)Block + 6);
              v21 = *(void (***)(void))v26;
              v26 = *((_QWORD *)Block + 6);
              v21[1]();
            }
          }
        }
        if ( winrt_suspend_handler )
          winrt_suspend_handler(Block + 8);
LABEL_56:
        if ( Block[17] )
          operator delete(Block);
      }
      return;
    case 4:
      goto LABEL_31;
    case 5:
      if ( *((_QWORD *)Block + 10) )
      {
        v13 = (volatile __int64 *)*((_QWORD *)Block + 10);
        while ( _InterlockedExchange64(v13, 0) == 1 )
          SwitchToThread();
      }
      if ( *((_QWORD *)Block + 9) )
        winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(Block + 36);
      if ( *((_QWORD *)Block + 6) )
      {
        v26 = *((_QWORD *)Block + 6);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 8), 0xFFFFFFFF) == 1 )
        {
          v26 = *((_QWORD *)Block + 6);
          v14 = *(void (***)(void))v26;
          v26 = *((_QWORD *)Block + 6);
          (*v14)();
          v26 = *((_QWORD *)Block + 6);
          if ( !_InterlockedDecrement((volatile signed __int32 *)(v26 + 12)) )
          {
            v26 = *((_QWORD *)Block + 6);
            v15 = *(void (***)(void))v26;
            v26 = *((_QWORD *)Block + 6);
            v15[1]();
          }
        }
      }
      goto LABEL_56;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x1403805f0  mov     r11, rsp
0x1403805f3  mov     [r11+10h], rbx
0x1403805f7  mov     [r11+18h], rsi
0x1403805fb  mov     [r11+8], rcx
0x1403805ff  push    rdi
0x140380600  push    r12
0x140380602  push    r13
0x140380604  push    r14
0x140380606  push    r15
0x140380608  sub     rsp, 0C0h
0x14038060f  mov     rax, cs:__security_cookie
0x140380616  xor     rax, rsp
0x140380619  mov     [rsp+0E8h+var_38], rax
0x140380621  mov     rdi, rcx
0x140380624  mov     [rsp+0E8h+var_B8], rcx
0x140380629  movzx   eax, word ptr [rdi+20h]
0x14038062d  mov     word ptr [rsp+0E8h+var_C8], ax; int
0x140380632  mov     r13d, 1
0x140380638  add     ax, r13w
0x14038063c  cmp     ax, 6; switch 7 cases
0x140380640  ja      def_14038065B; jumptable 000000014038065B default case, cases 1,2
0x140380646  movsx   rax, ax
0x14038064a  lea     rdx, __ImageBase
0x140380651  mov     ecx, ds:(jpt_14038065B - 140000000h)[rdx+rax*4]
0x140380658  add     rcx, rdx
0x14038065b  jmp     rcx; switch jump
0x14038065d  xor     esi, esi; jumptable 000000014038065B case 4
0x14038065f  jmp     loc_140380A2A
0x140380664  xor     esi, esi; jumptable 000000014038065B case 3
0x140380666  mov     [rdi+30h], rsi
0x14038066a  mov     r14, [rdi+18h]
0x14038066e  mov     rax, [r14+20h]
0x140380672  test    rax, rax
0x140380675  jz      short loc_14038067C
0x140380677  lock add [rax+8], r13d
0x14038067c  mov     rcx, [r14+18h]
0x140380680  mov     [rdi+90h], rcx
0x140380687  mov     [rdi+28h], rcx
0x14038068b  mov     rax, [r14+20h]
0x14038068f  mov     [rdi+30h], rax
0x140380693  test    rcx, rcx
0x140380696  jz      short loc_1403806A5
0x140380698  mov     [rsp+0E8h+var_68], rcx
0x1403806a0  mov     rcx, [rcx]
0x1403806a3  jmp     short loc_1403806A8
0x1403806a5  mov     rcx, rsi; hEvent
0x1403806a8  call    cs:__imp_ResetEvent
0x1403806ae  mov     rcx, [rsp+0E8h]; this
0x1403806b6  test    eax, eax
0x1403806b8  jnz     short loc_1403806CC
0x1403806ba  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1403806c1  mov     edx, 9CCh; void *
0x1403806c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1403806cc  lea     r12, [rdi+38h]
0x1403806d0  mov     [r12], rsi
0x1403806d4  lea     r15, [r14+8]
0x1403806d8  mov     rcx, r15; SRWLock
0x1403806db  call    cs:__imp_AcquireSRWLockExclusive
0x1403806e1  lea     rbx, [rdi+78h]
0x1403806e5  mov     [rbx], rsi
0x1403806e8  mov     rcx, rbx
0x1403806eb  call    WINRT_IMPL_GetSystemTimePreciseAsFileTime
0x1403806f0  mov     rax, [rbx]
0x1403806f3  mov     [rsp+0E8h+var_58], rax
0x1403806fb  mov     [r14+10h], rax
0x1403806ff  mov     eax, [rbx]
0x140380701  mov     [rdi+40h], eax
0x140380704  mov     rax, [rbx]
0x140380707  mov     [rsp+0E8h+var_58], rax
0x14038070f  shr     rax, 20h
0x140380713  mov     [rdi+44h], eax
0x140380716  mov     rax, [rdi+40h]
0x14038071a  mov     [r12], rax
0x14038071e  test    r15, r15
0x140380721  jz      short loc_14038072C
0x140380723  mov     rcx, r15; SRWLock
0x140380726  call    cs:__imp_ReleaseSRWLockExclusive
0x14038072c  mov     r9, r12
0x14038072f  call    _anonymous_namespace___SHRegSetFILETIME
0x140380734  mov     rcx, [rsp+0E8h]; this
0x14038073c  test    eax, eax
0x14038073e  jns     short loc_140380754
0x140380740  mov     r9d, eax; char *
0x140380743  lea     r8, aCW1SSrcOrchest_60; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14038074a  mov     edx, 173h; void *
0x14038074f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140380754  mov     rcx, [r14+30h]
0x140380758  test    rcx, rcx
0x14038075b  jz      loc_14038094C
0x140380761  lea     rbx, [rdi+80h]
0x140380768  mov     [rbx], rsi
0x14038076b  mov     rax, [rcx]
0x14038076e  mov     rdx, rbx
0x140380771  mov     rax, [rax+48h]
0x140380775  call    _guard_dispatch_icall
0x14038077a  test    eax, eax
0x14038077c  jns     short loc_140380785
0x14038077e  mov     ecx, eax
0x140380780  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x140380785  lea     rcx, [rdi+48h]
0x140380789  mov     rax, [rbx]
0x14038078c  mov     [rsp+0E8h+var_70], rax
0x140380791  mov     [rcx], rax
0x140380794  lea     rbx, [rdi+50h]
0x140380798  mov     [rbx], rsi
0x14038079b  mov     [rdi+58h], rcx
0x14038079f  mov     [rdi+60h], rsi
0x1403807a3  mov     [rdi+68h], r13b
0x1403807a7  mov     rax, cs:?winrt_suspend_handler@@3P6AXPEBX@_EEA
0x1403807ae  test    rax, rax
0x1403807b1  jz      short loc_1403807BB
0x1403807b3  mov     rcx, rbx
0x1403807b6  call    _guard_dispatch_icall
0x1403807bb  mov     eax, 4
0x1403807c0  mov     [rdi+20h], ax
0x1403807c4  mov     rdx, rdi
0x1403807c7  mov     rcx, rbx
0x1403807ca  call    ??$await_suspend@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@AEAVProvider@WSX@Windows@@@std@@@?$notify_awaiter@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEAA?A_PU?$coroutine_handle@Upromise_type@?$coroutine_traits@Ufire_and_forget@winrt@@AEAVProvider@WSX@Windows@@@std@@@std@@@Z
0x1403807cf  test    al, al
0x1403807d1  jz      loc_14038089C
0x1403807d7  jmp     loc_140380A44
0x1403807dc  xor     esi, esi; jumptable 000000014038065B case 6
0x1403807de  cmp     [rdi+50h], rsi
0x1403807e2  jz      short loc_140380800
0x1403807e4  mov     rbx, [rdi+50h]
0x1403807e8  mov     [rsp+0E8h+var_B0], rbx
0x1403807ed  jmp     short loc_1403807F5
0x1403807ef  call    cs:__imp_SwitchToThread
0x1403807f5  mov     rax, rsi
0x1403807f8  xchg    rax, [rbx]
0x1403807fb  cmp     rax, r13
0x1403807fe  jz      short loc_1403807EF
0x140380800  lea     rcx, [rdi+48h]
0x140380804  mov     rax, [rcx]
0x140380807  mov     [rsp+0E8h+var_C0], rax
0x14038080c  test    rax, rax
0x14038080f  jz      short loc_140380817
0x140380811  call    ?unconditional_release_ref@?$com_ptr@UIGlobalInterfaceTable@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(void)
0x140380816  nop
0x140380817  cmp     [rdi+30h], rsi
0x14038081b  jz      short loc_140380895
0x14038081d  mov     rcx, [rdi+30h]
0x140380821  mov     [rsp+0E8h+var_60], rcx
0x140380829  or      ebx, 0FFFFFFFFh
0x14038082c  mov     eax, ebx
0x14038082e  lock xadd [rcx+8], eax
0x140380833  add     eax, ebx
0x140380835  jnz     short loc_140380895
0x140380837  mov     rax, [rdi+30h]
0x14038083b  mov     [rsp+0E8h+var_60], rax
0x140380843  mov     rax, [rax]
0x140380846  mov     rcx, [rdi+30h]
0x14038084a  mov     [rsp+0E8h+var_60], rcx
0x140380852  mov     rax, [rax]
0x140380855  call    _guard_dispatch_icall
0x14038085a  mov     rcx, [rdi+30h]
0x14038085e  mov     [rsp+0E8h+var_60], rcx
0x140380866  mov     eax, ebx
0x140380868  lock xadd [rcx+0Ch], eax
0x14038086d  add     eax, ebx
0x14038086f  jnz     short loc_140380895
0x140380871  mov     rax, [rdi+30h]
0x140380875  mov     [rsp+0E8h+var_60], rax
0x14038087d  mov     rax, [rax]
0x140380880  mov     rcx, [rdi+30h]
0x140380884  mov     [rsp+0E8h+var_60], rcx
0x14038088c  mov     rax, [rax+8]
0x140380890  call    _guard_dispatch_icall
0x140380895  jmp     loc_140380A2A
0x14038089a  xor     esi, esi; jumptable 000000014038065B case 5
0x14038089c  mov     rax, cs:?winrt_resume_handler@@3P6AXPEBX@_EEA
0x1403808a3  test    rax, rax
0x1403808a6  jz      short loc_1403808B1
0x1403808a8  lea     rcx, [rdi+50h]
0x1403808ac  call    _guard_dispatch_icall
0x1403808b1  mov     eax, [rdi+64h]
0x1403808b4  mov     [rsp+0E8h+var_9C], eax
0x1403808b8  test    eax, eax
0x1403808ba  jns     short loc_1403808C8
0x1403808bc  mov     ecx, [rdi+64h]
0x1403808bf  mov     [rsp+0E8h+var_9C], ecx
0x1403808c3  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x1403808c8  mov     eax, [rdi+60h]
0x1403808cb  mov     [rsp+0E8h+var_A0], eax
0x1403808cf  cmp     eax, 2
0x1403808d2  jnz     short loc_1403808EF
0x1403808d4  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x1403808d9  call    ??0hresult_canceled@winrt@@QEAA@XZ; winrt::hresult_canceled::hresult_canceled(void)
0x1403808de  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1403808e5  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x1403808ea  call    _CxxThrowException
0x1403808ef  mov     rax, [rdi+58h]
0x1403808f3  mov     [rsp+0E8h+var_A8], rax
0x1403808f8  mov     rcx, [rax]
0x1403808fb  mov     rax, [rcx]
0x1403808fe  mov     rax, [rax+40h]
0x140380902  call    _guard_dispatch_icall
0x140380907  test    eax, eax
0x140380909  jns     short loc_140380913
0x14038090b  mov     ecx, eax
0x14038090d  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x140380913  cmp     [rdi+50h], rsi
0x140380917  jz      short loc_140380935
0x140380919  mov     rbx, [rdi+50h]
0x14038091d  mov     [rsp+0E8h+var_B0], rbx
0x140380922  jmp     short loc_14038092A
0x140380924  call    cs:__imp_SwitchToThread
0x14038092a  mov     rax, rsi
0x14038092d  xchg    rax, [rbx]
0x140380930  cmp     rax, r13
0x140380933  jz      short loc_140380924
0x140380935  lea     rcx, [rdi+48h]
0x140380939  mov     rax, [rcx]
0x14038093c  mov     [rsp+0E8h+var_C0], rax
0x140380941  test    rax, rax
0x140380944  jz      short loc_14038094C
0x140380946  call    ?unconditional_release_ref@?$com_ptr@UIGlobalInterfaceTable@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IGlobalInterfaceTable>::unconditional_release_ref(void)
0x14038094b  nop
0x14038094c  jmp     short loc_140380955
0x14038094e  xor     esi, esi
0x140380950  mov     rdi, [rsp+0E8h+var_B8]
0x140380955  cmp     [rdi+90h], rsi
0x14038095c  jz      short loc_14038096F
0x14038095e  mov     rax, [rdi+28h]
0x140380962  mov     [rsp+0E8h+var_68], rax
0x14038096a  mov     rcx, [rax]
0x14038096d  jmp     short loc_140380972
0x14038096f  mov     rcx, rsi; hEvent
0x140380972  call    cs:__imp_SetEvent
0x140380978  mov     rcx, [rsp+0E8h]; this
0x140380980  test    eax, eax
0x140380982  jnz     short loc_140380996
0x140380984  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14038098b  mov     edx, 9C7h; void *
0x140380990  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140380996  cmp     [rdi+30h], rsi
0x14038099a  jz      short loc_140380A14
0x14038099c  mov     rcx, [rdi+30h]
0x1403809a0  mov     [rsp+0E8h+var_60], rcx
0x1403809a8  or      ebx, 0FFFFFFFFh
0x1403809ab  mov     eax, ebx
0x1403809ad  lock xadd [rcx+8], eax
0x1403809b2  add     eax, ebx
0x1403809b4  jnz     short loc_140380A14
0x1403809b6  mov     rax, [rdi+30h]
0x1403809ba  mov     [rsp+0E8h+var_60], rax
0x1403809c2  mov     rax, [rax]
0x1403809c5  mov     rcx, [rdi+30h]
0x1403809c9  mov     [rsp+0E8h+var_60], rcx
0x1403809d1  mov     rax, [rax]
0x1403809d4  call    _guard_dispatch_icall
0x1403809d9  mov     rcx, [rdi+30h]
0x1403809dd  mov     [rsp+0E8h+var_60], rcx
0x1403809e5  mov     eax, ebx
0x1403809e7  lock xadd [rcx+0Ch], eax
0x1403809ec  add     eax, ebx
0x1403809ee  jnz     short loc_140380A14
0x1403809f0  mov     rax, [rdi+30h]
0x1403809f4  mov     [rsp+0E8h+var_60], rax
0x1403809fc  mov     rax, [rax]
0x1403809ff  mov     rcx, [rdi+30h]
0x140380a03  mov     [rsp+0E8h+var_60], rcx
0x140380a0b  mov     rax, [rax+8]
0x140380a0f  call    _guard_dispatch_icall
0x140380a14  lea     rcx, [rdi+10h]
0x140380a18  mov     rax, cs:?winrt_suspend_handler@@3P6AXPEBX@_EEA
0x140380a1f  test    rax, rax
0x140380a22  jz      short loc_140380A2A
0x140380a24  call    _guard_dispatch_icall
0x140380a29  nop
0x140380a2a  jmp     short loc_140380A2E
0x140380a2c  xor     esi, esi; jumptable 000000014038065B case 0
0x140380a2e  cmp     [rdi+22h], si
0x140380a32  jz      short loc_140380A44
0x140380a34  mov     edx, 0A0h
0x140380a39  mov     rcx, rdi; Block
0x140380a3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140380a41  jmp     short loc_140380A44
0x140380a43  int     3; Trap to Debugger
0x140380a44  mov     rcx, [rsp+0E8h+var_38]
0x140380a4c  xor     rcx, rsp; StackCookie
0x140380a4f  call    __security_check_cookie
0x140380a54  lea     r11, [rsp+0E8h+var_28]
0x140380a5c  mov     rbx, [r11+38h]
0x140380a60  mov     rsi, [r11+40h]
0x140380a64  mov     rsp, r11
0x140380a67  pop     r15
0x140380a69  pop     r14
0x140380a6b  pop     r13
0x140380a6d  pop     r12
0x140380a6f  pop     rdi
0x140380a70  retn
```
