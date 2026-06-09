# winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1

- ea: `0x180008230`
- end: `0x1800088ac`
- name: `winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1`
- size: `1660`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800088c0`

## callees

- `0x180001940`
- `0x180001fea`
- `0x1800048e4`
- `0x180006068`
- `0x1800068d0`
- `0x180008230`
- `0x180009088`
- `0x180009144`
- `0x18000917c`
- `0x180009224`
- `0x18000a014`
- `0x18000d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180008854`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180008854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800084e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000877a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800084d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000877a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087d8`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // r12
  _QWORD *v3; // r14
  __int64 v4; // rcx
  int v5; // r15d
  __int64 v6; // rbx
  const struct winrt::impl::slim_source_location *v7; // rax
  __int64 v8; // rcx
  LPVOID *v9; // r14
  _QWORD *v10; // r15
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void *v15; // r13
  DWORD LastError; // ebx
  int v17; // eax
  int v18; // ebx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // ebx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-C8h]
  int v29[2]; // [rsp+20h] [rbp-C8h]
  const char *v30; // [rsp+28h] [rbp-C0h]
  __int64 (__fastcall *v31)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+58h] [rbp-90h]
  __int64 v32; // [rsp+60h] [rbp-88h]
  _BYTE pExceptionObject[112]; // [rsp+78h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_66;
    case 2:
      v3 = (_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 16) = 0;
      v5 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(*(_QWORD *)(a1 + 152) + 32LL))(
             *(_QWORD *)(*(_QWORD *)(a1 + 152) + 32LL),
             &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22,
             a1 + 16);
      v6 = a1 - 112;
      *(_QWORD *)(a1 + 128) = a1 - 112;
      if ( v5 >= 0 )
      {
        if ( *v3 )
        {
          *(_BYTE *)(a1 + 24) = 0;
          if ( *(_DWORD *)(v6 + 96) == 2 )
          {
            v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 96);
            winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v7);
            throw (winrt::hresult_canceled *)pExceptionObject;
          }
          *v2 = 4;
          `winrt::resume_background'::`2'::awaitable::await_suspend(v4, a1);
          return;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8F,
          (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
          (const char *)0x8000FFFFLL,
          v28);
        *(_DWORD *)(v6 + 104) = -2147418113;
        if ( *v3 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
          (const char *)(unsigned int)v5,
          (int)"Query ICbsSession9",
          v30);
        *(_DWORD *)(v6 + 104) = v5;
        if ( *v3 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
      }
LABEL_65:
      *(_QWORD *)(a1 + 88) = v6;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_66:
        if ( *(_QWORD *)(a1 - 24) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref();
        if ( *(_QWORD *)(a1 - 32) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref();
        __ExceptionPtrDestroy((void *)(a1 - 56));
        winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::factory_implementation::WaaSAssessmentHelper,winrt::Windows::Foundation::IActivationFactory>::~root_implements<winrt::Windows::Internal::WaasMedicDocked::factory_implementation::WaaSAssessmentHelper,winrt::Windows::Foundation::IActivationFactory>(a1 - 112);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), 0x110u);
      }
      return;
    case 4:
      v9 = (LPVOID *)(a1 + 32);
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      *(_DWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = 0;
      *(_DWORD *)(a1 + 64) = 0;
      v10 = (_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 72) = 0;
      v11 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 16))(
              *(_QWORD *)(a1 + 16),
              &IID_IClientSecurity,
              a1 + 72);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v32 = *v10;
        v14 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v10 + 24LL);
        v31 = v14;
        v15 = *v9;
        if ( *v9 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v15);
          SetLastError(LastError);
          v14 = v31;
        }
        *v9 = 0;
        v17 = v14(v32, *(_QWORD *)(a1 + 16), a1 + 40, a1 + 44);
        v18 = v17;
        if ( v17 >= 0 )
        {
          *(_QWORD *)v29 = *v9;
          v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(*(_QWORD *)*v10 + 32LL))(
                  *v10,
                  *(_QWORD *)(a1 + 16),
                  0xFFFFFFFFLL,
                  0xFFFFFFFFLL);
          v21 = v20;
          if ( v20 >= 0 )
          {
            *(_DWORD *)(a1 + 80) = 0;
            v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 16) + 112LL))(*(_QWORD *)(a1 + 16), 0);
            v24 = v23;
            if ( v23 >= 0 )
            {
              *(_DWORD *)(a1 - 8) = 0;
              if ( *v10 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
              if ( *v9 )
                CoTaskMemFree(*v9);
              v27 = *(_QWORD *)(a1 + 16);
              if ( v27 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              v6 = *(_QWORD *)(a1 + 128);
            }
            else if ( v23 == -2146498527 )
            {
              *(_DWORD *)(a1 - 8) = -2146498527;
              if ( *v10 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
              if ( *v9 )
                CoTaskMemFree(*v9);
              v25 = *(_QWORD *)(a1 + 16);
              if ( v25 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              v6 = *(_QWORD *)(a1 + 128);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA0,
                (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
                (const char *)(unsigned int)v23,
                v29[0]);
              *(_DWORD *)(a1 - 8) = v24;
              if ( *v10 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
              if ( *v9 )
                CoTaskMemFree(*v9);
              v26 = *(_QWORD *)(a1 + 16);
              if ( v26 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              v6 = *(_QWORD *)(a1 + 128);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9D,
              (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
              (const char *)(unsigned int)v20,
              v29[0]);
            *(_DWORD *)(a1 - 8) = v21;
            if ( *v10 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
            if ( *v9 )
              CoTaskMemFree(*v9);
            v22 = *(_QWORD *)(a1 + 16);
            if ( v22 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            v6 = *(_QWORD *)(a1 + 128);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9C,
            (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
            (const char *)(unsigned int)v17,
            a1 + 32);
          *(_DWORD *)(a1 - 8) = v18;
          if ( *v10 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
          if ( *v9 )
            CoTaskMemFree(*v9);
          v19 = *(_QWORD *)(a1 + 16);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          v6 = *(_QWORD *)(a1 + 128);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
          (const char *)(unsigned int)v11,
          v28);
        *(_DWORD *)(a1 - 8) = v12;
        if ( *v10 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
        if ( *v9 )
          CoTaskMemFree(*v9);
        v13 = *(_QWORD *)(a1 + 16);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        v6 = *(_QWORD *)(a1 + 128);
      }
      goto LABEL_65;
    case 5:
      v8 = *(_QWORD *)(a1 + 16);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      goto LABEL_66;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180008230  mov     [rsp+arg_0], rcx
0x180008235  push    rbx
0x180008236  push    rsi
0x180008237  push    rdi
0x180008238  push    r12
0x18000823a  push    r13
0x18000823c  push    r14
0x18000823e  push    r15
0x180008240  sub     rsp, 0B0h
0x180008247  mov     rsi, [rsp+0E8h+arg_0]
0x18000824f  lea     r12, [rsi+8]
0x180008253  mov     [rsp+0E8h+var_80], r12
0x180008258  movzx   eax, word ptr [r12]
0x18000825d  mov     [rsp+0E8h+var_98], ax
0x180008262  inc     ax; switch 7 cases
0x180008265  cmp     ax, 6
0x180008269  ja      def_180008284; jumptable 0000000180008284 default case, case 0
0x18000826f  movsx   rax, ax
0x180008273  lea     rdx, cs:180000000h
0x18000827a  mov     ecx, ds:(jpt_180008284 - 180000000h)[rdx+rax*4]
0x180008281  add     rcx, rdx
0x180008284  jmp     rcx; switch jump
0x180008286  xor     edi, edi; jumptable 0000000180008284 case 3
0x180008288  jmp     loc_180008834
0x18000828d  lea     r14, [rsi+10h]; jumptable 0000000180008284 case 2
0x180008291  xor     edi, edi
0x180008293  mov     [r14], rdi
0x180008296  mov     rax, [r12+90h]
0x18000829e  mov     rcx, [rax+20h]
0x1800082a2  mov     rax, [rcx]
0x1800082a5  mov     r8, r14
0x1800082a8  lea     rdx, _GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22
0x1800082af  mov     rax, [rax]
0x1800082b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b7  mov     r15d, eax
0x1800082ba  lea     rbx, [rsi-70h]
0x1800082be  mov     [rsi+80h], rbx
0x1800082c5  test    eax, eax
0x1800082c7  jns     short loc_180008317
0x1800082c9  mov     rcx, [rsp+0E8h]; this
0x1800082d1  lea     rax, aQueryIcbssessi; "Query ICbsSession9"
0x1800082d8  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800082dd  mov     r9d, r15d; char *
0x1800082e0  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x1800082e7  mov     edx, 8Eh; void *
0x1800082ec  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800082f1  mov     [rbx+68h], r15d
0x1800082f5  mov     rcx, [r14]
0x1800082f8  test    rcx, rcx
0x1800082fb  jz      short loc_180008312
0x1800082fd  mov     [rsp+0E8h+arg_8], rcx
0x180008305  mov     rax, [rcx]
0x180008308  mov     rax, [rax+10h]
0x18000830c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008311  nop
0x180008312  jmp     loc_180008819
0x180008317  mov     rax, [r14]
0x18000831a  mov     [rsp+0E8h+arg_8], rax
0x180008322  test    rax, rax
0x180008325  jnz     short loc_18000836F
0x180008327  mov     rcx, [rsp+0E8h]; this
0x18000832f  mov     r9d, 8000FFFFh; char *
0x180008335  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000833c  mov     edx, 8Fh; void *
0x180008341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008346  mov     dword ptr [rbx+68h], 8000FFFFh
0x18000834d  mov     rcx, [r14]
0x180008350  test    rcx, rcx
0x180008353  jz      short loc_18000836A
0x180008355  mov     [rsp+0E8h+arg_8], rcx
0x18000835d  mov     rax, [rcx]
0x180008360  mov     rax, [rax+10h]
0x180008364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008369  nop
0x18000836a  jmp     loc_180008819
0x18000836f  mov     [rsi+18h], dil
0x180008373  mov     eax, [rbx+60h]
0x180008376  nop
0x180008377  cmp     eax, 2
0x18000837a  jnz     short loc_1800083A3
0x18000837c  lea     rcx, [rsi+60h]
0x180008380  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180008385  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180008388  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x18000838d  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180008392  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180008399  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18000839e  call    _CxxThrowException_0
0x1800083a3  mov     eax, 4
0x1800083a8  mov     [r12], ax
0x1800083ad  mov     rdx, rsi
0x1800083b0  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x1800083b5  jmp     loc_18000887A
0x1800083ba  mov     rcx, [rsi+10h]; jumptable 0000000180008284 case 5
0x1800083be  xor     edi, edi
0x1800083c0  test    rcx, rcx
0x1800083c3  jz      short loc_1800083DA
0x1800083c5  mov     [rsp+0E8h+arg_8], rcx
0x1800083cd  mov     rax, [rcx]
0x1800083d0  mov     rax, [rax+10h]
0x1800083d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d9  nop
0x1800083da  jmp     loc_180008834
0x1800083df  lea     r14, [rsi+20h]; jumptable 0000000180008284 case 4
0x1800083e3  xor     edi, edi
0x1800083e5  mov     [r14], rdi
0x1800083e8  mov     [rsi+28h], rdi
0x1800083ec  mov     [rsi+30h], edi
0x1800083ef  mov     [rsi+38h], rdi
0x1800083f3  mov     [rsi+40h], edi
0x1800083f6  lea     r15, [rsi+48h]
0x1800083fa  mov     [r15], rdi
0x1800083fd  mov     rcx, [rsi+10h]
0x180008401  mov     [rsp+0E8h+arg_8], rcx
0x180008409  mov     rax, [rcx]
0x18000840c  mov     r8, r15
0x18000840f  lea     rdx, IID_IClientSecurity
0x180008416  mov     rax, [rax]
0x180008419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000841e  mov     ebx, eax
0x180008420  test    eax, eax
0x180008422  jns     short loc_1800084A1
0x180008424  mov     rcx, [rsp+0E8h]; this
0x18000842c  mov     r9d, eax; char *
0x18000842f  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180008436  mov     edx, 9Bh; void *
0x18000843b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008440  mov     [rsi-8], ebx
0x180008443  mov     rcx, [r15]
0x180008446  test    rcx, rcx
0x180008449  jz      short loc_180008460
0x18000844b  mov     [rsp+0E8h+arg_10], rcx
0x180008453  mov     rax, [rcx]
0x180008456  mov     rax, [rax+10h]
0x18000845a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000845f  nop
0x180008460  mov     rcx, [r14]; pv
0x180008463  test    rcx, rcx
0x180008466  jz      short loc_180008477
0x180008468  mov     [rsp+0E8h+arg_18], rcx
0x180008470  call    cs:__imp_CoTaskMemFree
0x180008476  nop
0x180008477  mov     rcx, [rsi+10h]
0x18000847b  test    rcx, rcx
0x18000847e  jz      short loc_180008495
0x180008480  mov     [rsp+0E8h+arg_8], rcx
0x180008488  mov     rax, [rcx]
0x18000848b  mov     rax, [rax+10h]
0x18000848f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008494  nop
0x180008495  mov     rbx, [rsi+80h]
0x18000849c  jmp     loc_180008819
0x1800084a1  mov     rax, [r15]
0x1800084a4  mov     [rsp+0E8h+var_88], rax
0x1800084a9  mov     [rsp+0E8h+arg_10], rax
0x1800084b1  mov     rax, [rax]
0x1800084b4  mov     rax, [rax+18h]
0x1800084b8  mov     [rsp+0E8h+var_90], rax
0x1800084bd  mov     r13, [r14]
0x1800084c0  mov     [rsp+0E8h+arg_18], r13
0x1800084c8  test    r13, r13
0x1800084cb  jz      short loc_1800084EB
0x1800084cd  call    cs:__imp_GetLastError
0x1800084d3  mov     ebx, eax
0x1800084d5  mov     rcx, r13; pv
0x1800084d8  call    cs:__imp_CoTaskMemFree
0x1800084de  mov     ecx, ebx; dwErrCode
0x1800084e0  call    cs:__imp_SetLastError
0x1800084e6  mov     rax, [rsp+0E8h+var_90]
0x1800084eb  mov     [r14], rdi
0x1800084ee  mov     rdx, [rsi+10h]
0x1800084f2  mov     [rsp+0E8h+arg_8], rdx
0x1800084fa  lea     rcx, [rsi+40h]
0x1800084fe  mov     [rsp+0E8h+var_A8], rcx
0x180008503  lea     r13, [rsi+38h]
0x180008507  mov     [rsp+0E8h+var_B0], r13
0x18000850c  mov     [rsp+0E8h+var_B8], rdi
0x180008511  lea     rcx, [rsi+30h]
0x180008515  mov     [rsp+0E8h+var_C0], rcx
0x18000851a  mov     qword ptr [rsp+0E8h+var_C8], r14; int
0x18000851f  lea     r9, [rsi+2Ch]
0x180008523  lea     r8, [rsi+28h]
0x180008527  mov     rcx, [rsp+0E8h+var_88]
0x18000852c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008531  mov     ebx, eax
0x180008533  test    eax, eax
0x180008535  jns     short loc_1800085B4
0x180008537  mov     rcx, [rsp+0E8h]; this
0x18000853f  mov     r9d, eax; char *
0x180008542  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180008549  mov     edx, 9Ch; void *
0x18000854e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008553  mov     [rsi-8], ebx
0x180008556  mov     rcx, [r15]
0x180008559  test    rcx, rcx
0x18000855c  jz      short loc_180008573
0x18000855e  mov     [rsp+0E8h+arg_10], rcx
0x180008566  mov     rax, [rcx]
0x180008569  mov     rax, [rax+10h]
0x18000856d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008572  nop
0x180008573  mov     rcx, [r14]; pv
0x180008576  test    rcx, rcx
0x180008579  jz      short loc_18000858A
0x18000857b  mov     [rsp+0E8h+arg_18], rcx
0x180008583  call    cs:__imp_CoTaskMemFree
0x180008589  nop
0x18000858a  mov     rcx, [rsi+10h]
0x18000858e  test    rcx, rcx
0x180008591  jz      short loc_1800085A8
0x180008593  mov     [rsp+0E8h+arg_8], rcx
0x18000859b  mov     rax, [rcx]
0x18000859e  mov     rax, [rax+10h]
0x1800085a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085a7  nop
0x1800085a8  mov     rbx, [rsi+80h]
0x1800085af  jmp     loc_180008819
0x1800085b4  mov     rcx, [r15]
0x1800085b7  mov     [rsp+0E8h+arg_10], rcx
0x1800085bf  mov     rax, [rcx]
0x1800085c2  mov     r8, [r13+0]
0x1800085c6  mov     [rsp+0E8h+var_78], r8
0x1800085cb  mov     r9, [r14]
0x1800085ce  mov     [rsp+0E8h+arg_18], r9
0x1800085d6  mov     rdx, [rsi+10h]
0x1800085da  mov     [rsp+0E8h+arg_8], rdx
0x1800085e2  mov     dword ptr [rsp+0E8h+var_A8], 20h ; ' '
0x1800085ea  mov     [rsp+0E8h+var_B0], r8
0x1800085ef  mov     dword ptr [rsp+0E8h+var_B8], 3
0x1800085f7  mov     dword ptr [rsp+0E8h+var_C0], 5
0x1800085ff  mov     qword ptr [rsp+0E8h+var_C8], r9; int
0x180008604  or      r8d, 0FFFFFFFFh
0x180008608  mov     r9d, r8d
0x18000860b  mov     rax, [rax+20h]
0x18000860f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008614  mov     ebx, eax
0x180008616  test    eax, eax
0x180008618  jns     short loc_180008697
0x18000861a  mov     rcx, [rsp+0E8h]; this
0x180008622  mov     r9d, eax; char *
0x180008625  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000862c  mov     edx, 9Dh; void *
0x180008631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008636  mov     [rsi-8], ebx
0x180008639  mov     rcx, [r15]
0x18000863c  test    rcx, rcx
0x18000863f  jz      short loc_180008656
0x180008641  mov     [rsp+0E8h+arg_10], rcx
0x180008649  mov     rax, [rcx]
0x18000864c  mov     rax, [rax+10h]
0x180008650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008655  nop
0x180008656  mov     rcx, [r14]; pv
0x180008659  test    rcx, rcx
0x18000865c  jz      short loc_18000866D
0x18000865e  mov     [rsp+0E8h+arg_18], rcx
0x180008666  call    cs:__imp_CoTaskMemFree
0x18000866c  nop
0x18000866d  mov     rcx, [rsi+10h]
0x180008671  test    rcx, rcx
0x180008674  jz      short loc_18000868B
0x180008676  mov     [rsp+0E8h+arg_8], rcx
0x18000867e  mov     rax, [rcx]
0x180008681  mov     rax, [rax+10h]
0x180008685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000868a  nop
0x18000868b  mov     rbx, [rsi+80h]
0x180008692  jmp     loc_180008819
0x180008697  lea     r8, [rsi+50h]
0x18000869b  mov     [r8], edi
0x18000869e  mov     rcx, [rsi+10h]
0x1800086a2  mov     [rsp+0E8h+arg_8], rcx
0x1800086aa  mov     rax, [rcx]
0x1800086ad  xor     edx, edx
0x1800086af  mov     rax, [rax+70h]
0x1800086b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b8  mov     ebx, eax
0x1800086ba  test    eax, eax
0x1800086bc  jns     loc_1800087A8
0x1800086c2  cmp     eax, 800F0821h
0x1800086c7  jnz     short loc_18000872E
0x1800086c9  mov     dword ptr [rsi-8], 800F0821h
0x1800086d0  mov     rcx, [r15]
0x1800086d3  test    rcx, rcx
0x1800086d6  jz      short loc_1800086ED
0x1800086d8  mov     [rsp+0E8h+arg_10], rcx
0x1800086e0  mov     rax, [rcx]
0x1800086e3  mov     rax, [rax+10h]
0x1800086e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ec  nop
0x1800086ed  mov     rcx, [r14]; pv
0x1800086f0  test    rcx, rcx
0x1800086f3  jz      short loc_180008704
0x1800086f5  mov     [rsp+0E8h+arg_18], rcx
0x1800086fd  call    cs:__imp_CoTaskMemFree
0x180008703  nop
0x180008704  mov     rcx, [rsi+10h]
0x180008708  test    rcx, rcx
0x18000870b  jz      short loc_180008722
0x18000870d  mov     [rsp+0E8h+arg_8], rcx
  ... truncated ...
```
