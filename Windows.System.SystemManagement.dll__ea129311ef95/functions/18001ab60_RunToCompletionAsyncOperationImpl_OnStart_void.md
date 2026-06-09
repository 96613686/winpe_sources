# RunToCompletionAsyncOperationImpl::OnStart(void)

- ea: `0x18001ab60`
- end: `0x18001ac6c`
- name: `?OnStart@RunToCompletionAsyncOperationImpl@@EEAAJXZ`
- size: `268`
- prototype: `__int64 __fastcall(RunToCompletionAsyncOperationImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000fd54`
- `0x18001ab60`
- `0x18001b7f0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001abd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001abd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abe6`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18001ac02`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18001ac02`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ab7f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ab7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ac59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ac59`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ac33`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ac33`

## pseudocode

```c
__int64 __fastcall RunToCompletionAsyncOperationImpl::OnStart(RunToCompletionAsyncOperationImpl *this)
{
  char *v1; // r14
  struct _TP_WORK *ThreadpoolWork; // rbp
  signed int v4; // eax
  signed int v5; // ebx
  signed int LastError; // eax

  v1 = (char *)this - 16;
  ThreadpoolWork = CreateThreadpoolWork(RunToCompletionAsyncOperationImpl::s_RunToCompletionAsync, (char *)this - 16, 0);
  if ( ThreadpoolWork )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)this + 98) == 1 )
    {
      if ( !GetModuleHandleExW(
              4u,
              (LPCWSTR)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
              (HMODULE *)this + 48) )
      {
        *((_QWORD *)this + 48) = 0;
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( v5 < 0 )
          goto LABEL_11;
      }
      v5 = CoIncrementMTAUsage((char *)this + 376);
      if ( v5 < 0 )
      {
        MTARefHelper::ReleaseDll((RunToCompletionAsyncOperationImpl *)((char *)this + 376), 0);
LABEL_11:
        _InterlockedDecrement((volatile signed __int32 *)this + 98);
LABEL_15:
        CloseThreadpoolWork(ThreadpoolWork);
        return (unsigned int)v5;
      }
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v1 + 8LL))(v1);
    SubmitThreadpoolWork(ThreadpoolWork);
    if ( (unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z((char *)this + 224) )
      v5 = *((_DWORD *)this + 90);
    else
      v5 = -2147467260;
    goto LABEL_15;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ab60  push    rbx
0x18001ab62  push    rbp
0x18001ab63  push    rsi
0x18001ab64  push    rdi
0x18001ab65  push    r14
0x18001ab67  sub     rsp, 20h
0x18001ab6b  lea     r14, [rcx-10h]
0x18001ab6f  mov     rdi, rcx
0x18001ab72  mov     rdx, r14; pv
0x18001ab75  lea     rcx, ?s_RunToCompletionAsync@RunToCompletionAsyncOperationImpl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001ab7c  xor     r8d, r8d; pcbe
0x18001ab7f  call    cs:__imp_CreateThreadpoolWork
0x18001ab85  mov     rbp, rax
0x18001ab88  test    rax, rax
0x18001ab8b  jnz     short loc_18001ABAB
0x18001ab8d  call    cs:__imp_GetLastError
0x18001ab93  mov     ebx, eax
0x18001ab95  test    eax, eax
0x18001ab97  jle     loc_18001AC5F
0x18001ab9d  movzx   ebx, ax
0x18001aba0  or      ebx, 80070000h
0x18001aba6  jmp     loc_18001AC5F
0x18001abab  mov     eax, 1
0x18001abb0  lock xadd [rdi+188h], eax
0x18001abb8  inc     eax
0x18001abba  cmp     eax, 1
0x18001abbd  jnz     short loc_18001AC21
0x18001abbf  lea     rsi, [rdi+178h]
0x18001abc6  lea     r8, [rsi+8]; phModule
0x18001abca  lea     rdx, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; lpModuleName
0x18001abd1  lea     ecx, [rax+3]; dwFlags
0x18001abd4  call    cs:__imp_GetModuleHandleExW
0x18001abda  test    eax, eax
0x18001abdc  jnz     short loc_18001ABFF
0x18001abde  mov     qword ptr [rsi+8], 0
0x18001abe6  call    cs:__imp_GetLastError
0x18001abec  mov     ebx, eax
0x18001abee  test    eax, eax
0x18001abf0  jle     short loc_18001ABFB
0x18001abf2  movzx   ebx, ax
0x18001abf5  or      ebx, 80070000h
0x18001abfb  test    ebx, ebx
0x18001abfd  js      short loc_18001AC18
0x18001abff  mov     rcx, rsi
0x18001ac02  call    cs:__imp_CoIncrementMTAUsage
0x18001ac08  mov     ebx, eax
0x18001ac0a  test    eax, eax
0x18001ac0c  jns     short loc_18001AC21
0x18001ac0e  xor     edx, edx; struct _TP_CALLBACK_INSTANCE *
0x18001ac10  mov     rcx, rsi; this
0x18001ac13  call    ?ReleaseDll@MTARefHelper@@AEAAJPEAU_TP_CALLBACK_INSTANCE@@@Z; MTARefHelper::ReleaseDll(_TP_CALLBACK_INSTANCE *)
0x18001ac18  lock dec dword ptr [rdi+188h]
0x18001ac1f  jmp     short loc_18001AC56
0x18001ac21  mov     rax, [r14]
0x18001ac24  mov     rcx, r14
0x18001ac27  mov     rax, [rax+8]
0x18001ac2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac30  mov     rcx, rbp; pwk
0x18001ac33  call    cs:__imp_SubmitThreadpoolWork
0x18001ac39  lea     rcx, [rdi+0E0h]
0x18001ac40  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18001ac45  test    al, al
0x18001ac47  jz      short loc_18001AC51
0x18001ac49  mov     ebx, [rdi+168h]
0x18001ac4f  jmp     short loc_18001AC56
0x18001ac51  mov     ebx, 80004004h
0x18001ac56  mov     rcx, rbp; pwk
0x18001ac59  call    cs:__imp_CloseThreadpoolWork
0x18001ac5f  mov     eax, ebx
0x18001ac61  add     rsp, 20h
0x18001ac65  pop     r14
0x18001ac67  pop     rdi
0x18001ac68  pop     rsi
0x18001ac69  pop     rbp
0x18001ac6a  pop     rbx
0x18001ac6b  retn
```
