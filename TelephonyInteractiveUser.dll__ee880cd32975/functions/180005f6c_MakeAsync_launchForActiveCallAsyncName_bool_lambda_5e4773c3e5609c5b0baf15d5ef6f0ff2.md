# MakeAsync_&launchForActiveCallAsyncName_bool__lambda_5e4773c3e5609c5b0baf15d5ef6f0ff2___

- ea: `0x180005f6c`
- end: `0x180006256`
- name: `MakeAsync_&launchForActiveCallAsyncName_bool__lambda_5e4773c3e5609c5b0baf15d5ef6f0ff2___`
- size: `746`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c960`

## callees

- `0x180001990`
- `0x180001de4`
- `0x180005f6c`
- `0x180006d9c`
- `0x18000cf2c`
- `0x18000f1c0`
- `0x180011530`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180006106`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180006106`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800060d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800060d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000614b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000618d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000614b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000618d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006141`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006141`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000612e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000612e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800061fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800061fa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000617f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000617f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000620c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000620c`

## pseudocode

```c
__int64 __fastcall MakeAsync__launchForActiveCallAsyncName_bool__lambda_5e4773c3e5609c5b0baf15d5ef6f0ff2___(
        __int64 *a1,
        __int64 *a2)
{
  void *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  signed int v13; // eax
  int v14; // eax
  HANDLE CurrentThread; // rax
  signed int v16; // eax
  struct _TP_WORK *ThreadpoolWork; // rdi
  signed int LastError; // eax
  struct _TP_WORK *v19; // rax

  v4 = operator new(0xB8u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4
    || (v5 = details::AsyncOperationBase__launchForActiveCallAsyncName_Windows::Foundation::IAsyncOperation_bool__details::OpInfo_Windows::Foundation::IAsyncOperation_bool_____::AsyncOperationBase__launchForActiveCallAsyncName_Windows::Foundation::IAsyncOperation_bool__details::OpInfo_Windows::Foundation::IAsyncOperation_bool_____(v4),
        (v6 = v5) == 0) )
  {
    v8 = -2147024882;
    Log_HREvent_0(2147942414LL, 0, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
    return v8;
  }
  v7 = Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::put_Id(
         v5 + 16,
         (unsigned int)_InterlockedIncrement(&sm_AsyncOperationCookie));
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::Start(v6 + 16);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v10 = operator new(0x48u);
      v11 = v10;
      if ( !v10 )
      {
        v9 = 0;
        v8 = -2147024882;
        goto LABEL_6;
      }
      v10[1] = 0;
      v10[6] = 0;
      v10[7] = 0;
      v10[8] = 0;
      v10[2] = 0;
      v10[3] = 0;
      v10[4] = 0;
      v10[5] = 0;
      *v10 = &off_18001B2C8;
      v12 = *a2;
      v10[6] = *a2;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      *((_DWORD *)v11 + 14) = *((_DWORD *)a2 + 2);
      v11[8] = v6;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      v11[1] = 0;
      if ( GetModuleHandleExW(4u, (LPCWSTR)details::MakeAsyncWorkerBase::Execute, (HMODULE *)v11 + 5) )
      {
        v14 = CoIncrementMTAUsage(v11 + 4);
        v8 = v14;
        if ( v14 < 0 )
        {
          Log_HREvent_0((unsigned int)v14, 1, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
LABEL_27:
          Log_HREvent_0(v8, 1, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
          (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
          goto LABEL_7;
        }
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)v11 + 3)
          || (v16 = GetLastError(), v8 = v16, v16 == 1008)
          || !v16 )
        {
          ThreadpoolWork = CreateThreadpoolWork(
                             details::MakeAsyncWorkerBase::Execute,
                             v11,
                             (PTP_CALLBACK_ENVIRON)v11[1]);
          if ( ThreadpoolWork )
          {
            v19 = (struct _TP_WORK *)v11[2];
            if ( ThreadpoolWork == v19 )
            {
              ThreadpoolWork = (struct _TP_WORK *)v11[2];
            }
            else
            {
              if ( v19 )
                CloseThreadpoolWork((PTP_WORK)v11[2]);
              v11[2] = ThreadpoolWork;
            }
            SubmitThreadpoolWork(ThreadpoolWork);
            goto LABEL_34;
          }
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
        else if ( v16 > 0 )
        {
          v8 = (unsigned __int16)v16 | 0x80070000;
        }
      }
      else
      {
        v13 = GetLastError();
        v8 = v13;
        if ( v13 > 0 )
          v8 = (unsigned __int16)v13 | 0x80070000;
      }
      Log_HREvent_0(v8, 0, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
      if ( (v8 & 0x80000000) != 0 )
        goto LABEL_27;
LABEL_34:
      *a1 = v6;
      return 0;
    }
  }
  Log_HREvent_0((unsigned int)v7, 1, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
  v9 = 1;
LABEL_6:
  Log_HREvent_0(v8, v9, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
LABEL_7:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v8;
}

```

## disassembly

```asm
0x180005f6c  push    rbx
0x180005f6e  push    rsi
0x180005f6f  push    rdi
0x180005f70  push    r12
0x180005f72  push    r14
0x180005f74  push    r15
0x180005f76  sub     rsp, 38h
0x180005f7a  mov     r14, rdx
0x180005f7d  mov     r15, rcx
0x180005f80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005f87  mov     ecx, 0B8h; unsigned __int64
0x180005f8c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005f91  test    rax, rax
0x180005f94  jz      loc_18000622B
0x180005f9a  mov     rcx, rax
0x180005f9d  call    details__AsyncOperationBase__launchForActiveCallAsyncName_Windows__Foundation__IAsyncOperation_bool__details__OpInfo_Windows__Foundation__IAsyncOperation_bool_______AsyncOperationBase__launchForActiveCallAsyncName_Windows__Foundation__IAsyncOperation_bool__details__OpInfo_Windows__Foundation__IAsyncOperation_bool_____
0x180005fa2  mov     rbx, rax
0x180005fa5  test    rax, rax
0x180005fa8  jz      loc_18000622B
0x180005fae  mov     r12d, 1
0x180005fb4  mov     edx, r12d
0x180005fb7  lock xadd cs:?sm_AsyncOperationCookie@@3JA, edx; long sm_AsyncOperationCookie
0x180005fbf  add     edx, r12d
0x180005fc2  lea     rcx, [rax+10h]
0x180005fc6  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____put_Id
0x180005fcb  mov     edi, eax
0x180005fcd  test    eax, eax
0x180005fcf  jns     short loc_180005FD9
0x180005fd1  mov     r9d, 331h
0x180005fd7  jmp     short loc_180005FEE
0x180005fd9  lea     rcx, [rbx+10h]
0x180005fdd  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____Start
0x180005fe2  mov     edi, eax
0x180005fe4  test    eax, eax
0x180005fe6  jns     short loc_18000602A
0x180005fe8  mov     r9d, 332h
0x180005fee  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x180005ff5  mov     edx, r12d
0x180005ff8  mov     ecx, eax
0x180005ffa  call    Log_HREvent_0
0x180005fff  mov     r9d, 695h
0x180006005  mov     edx, r12d
0x180006008  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x18000600f  mov     ecx, edi
0x180006011  call    Log_HREvent_0
0x180006016  mov     rcx, [rbx]
0x180006019  mov     rax, [rcx+10h]
0x18000601d  mov     rcx, rbx
0x180006020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006025  jmp     loc_180006246
0x18000602a  mov     ecx, 48h ; 'H'; Size
0x18000602f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006034  mov     rsi, rax
0x180006037  test    rax, rax
0x18000603a  jz      loc_180006219
0x180006040  mov     qword ptr [rax+8], 0
0x180006048  mov     qword ptr [rax+30h], 0
0x180006050  mov     qword ptr [rax+38h], 0
0x180006058  mov     qword ptr [rax+40h], 0
0x180006060  mov     qword ptr [rax+10h], 0
0x180006068  mov     qword ptr [rax+18h], 0
0x180006070  mov     qword ptr [rax+20h], 0
0x180006078  mov     qword ptr [rax+28h], 0
0x180006080  lea     rax, off_18001B2C8
0x180006087  mov     [rsi], rax
0x18000608a  mov     rcx, [r14]
0x18000608d  mov     [rsi+30h], rcx
0x180006091  test    rcx, rcx
0x180006094  jz      short loc_1800060A2
0x180006096  mov     rax, [rcx]
0x180006099  mov     rax, [rax+8]
0x18000609d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a2  mov     eax, [r14+8]
0x1800060a6  mov     rcx, rbx
0x1800060a9  mov     [rsi+38h], eax
0x1800060ac  mov     [rsi+40h], rbx
0x1800060b0  mov     rax, [rbx]
0x1800060b3  mov     rax, [rax+8]
0x1800060b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060bc  mov     r14d, 4
0x1800060c2  mov     qword ptr [rsi+8], 0
0x1800060ca  mov     ecx, r14d; dwFlags
0x1800060cd  lea     r8, [rsi+28h]; phModule
0x1800060d1  lea     rdx, ?Execute@MakeAsyncWorkerBase@details@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x1800060d8  call    cs:__imp_GetModuleHandleExW
0x1800060de  test    eax, eax
0x1800060e0  jnz     short loc_180006102
0x1800060e2  call    cs:__imp_GetLastError
0x1800060e8  mov     edi, eax
0x1800060ea  test    eax, eax
0x1800060ec  jle     short loc_1800060F7
0x1800060ee  movzx   edi, ax
0x1800060f1  or      edi, 80070000h
0x1800060f7  mov     r9d, 458h
0x1800060fd  jmp     loc_1800061A8
0x180006102  lea     rcx, [rsi+20h]
0x180006106  call    cs:__imp_CoIncrementMTAUsage
0x18000610c  mov     edi, eax
0x18000610e  test    eax, eax
0x180006110  jns     short loc_18000612E
0x180006112  mov     r9d, 45Ah
0x180006118  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x18000611f  mov     edx, r12d
0x180006122  mov     ecx, eax
0x180006124  call    Log_HREvent_0
0x180006129  jmp     loc_1800061BC
0x18000612e  call    cs:__imp_GetCurrentThread
0x180006134  lea     r9, [rsi+18h]; TokenHandle
0x180006138  mov     r8d, r12d; OpenAsSelf
0x18000613b  mov     rcx, rax; ThreadHandle
0x18000613e  mov     edx, r14d; DesiredAccess
0x180006141  call    cs:__imp_OpenThreadToken
0x180006147  test    eax, eax
0x180006149  jnz     short loc_180006171
0x18000614b  call    cs:__imp_GetLastError
0x180006151  mov     edi, eax
0x180006153  cmp     eax, 3F0h
0x180006158  jz      short loc_180006171
0x18000615a  test    eax, eax
0x18000615c  jz      short loc_180006171
0x18000615e  jle     short loc_180006169
0x180006160  movzx   edi, ax
0x180006163  or      edi, 80070000h
0x180006169  mov     r9d, 463h
0x18000616f  jmp     short loc_1800061A8
0x180006171  mov     r8, [rsi+8]; pcbe
0x180006175  lea     rcx, ?Execute@MakeAsyncWorkerBase@details@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000617c  mov     rdx, rsi; pv
0x18000617f  call    cs:__imp_CreateThreadpoolWork
0x180006185  mov     rdi, rax
0x180006188  test    rax, rax
0x18000618b  jnz     short loc_1800061E9
0x18000618d  call    cs:__imp_GetLastError
0x180006193  mov     edi, eax
0x180006195  test    eax, eax
0x180006197  jle     short loc_1800061A2
0x180006199  movzx   edi, ax
0x18000619c  or      edi, 80070000h
0x1800061a2  mov     r9d, 46Ch
0x1800061a8  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x1800061af  xor     edx, edx
0x1800061b1  mov     ecx, edi
0x1800061b3  call    Log_HREvent_0
0x1800061b8  test    edi, edi
0x1800061ba  jns     short loc_180006212
0x1800061bc  mov     r9d, 6ACh
0x1800061c2  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x1800061c9  mov     edx, r12d
0x1800061cc  mov     ecx, edi
0x1800061ce  call    Log_HREvent_0
0x1800061d3  mov     rcx, [rsi]
0x1800061d6  mov     edx, r12d
0x1800061d9  mov     rax, [rcx]
0x1800061dc  mov     rcx, rsi
0x1800061df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061e4  jmp     loc_180006016
0x1800061e9  mov     rax, [rsi+10h]
0x1800061ed  cmp     rdi, rax
0x1800061f0  jz      short loc_180006206
0x1800061f2  test    rax, rax
0x1800061f5  jz      short loc_180006200
0x1800061f7  mov     rcx, rax; pwk
0x1800061fa  call    cs:__imp_CloseThreadpoolWork
0x180006200  mov     [rsi+10h], rdi
0x180006204  jmp     short loc_180006209
0x180006206  mov     rdi, rax
0x180006209  mov     rcx, rdi; pwk
0x18000620c  call    cs:__imp_SubmitThreadpoolWork
0x180006212  mov     [r15], rbx
0x180006215  xor     eax, eax
0x180006217  jmp     short loc_180006248
0x180006219  mov     r9d, 6ABh
0x18000621f  xor     edx, edx
0x180006221  mov     edi, 8007000Eh
0x180006226  jmp     loc_180006008
0x18000622b  mov     edi, 8007000Eh
0x180006230  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x180006237  mov     ecx, edi
0x180006239  mov     r9d, 694h
0x18000623f  xor     edx, edx
0x180006241  call    Log_HREvent_0
0x180006246  mov     eax, edi
0x180006248  add     rsp, 38h
0x18000624c  pop     r15
0x18000624e  pop     r14
0x180006250  pop     r12
0x180006252  pop     rdi
0x180006253  pop     rsi
0x180006254  pop     rbx
0x180006255  retn
```
