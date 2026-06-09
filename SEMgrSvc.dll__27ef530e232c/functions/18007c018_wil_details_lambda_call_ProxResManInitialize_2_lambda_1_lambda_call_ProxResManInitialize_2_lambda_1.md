# wil::details::lambda_call__ProxResManInitialize_::_2_::_lambda_1___::_lambda_call__ProxResManInitialize_::_2_::_lambda_1___

- ea: `0x18007c018`
- end: `0x18007c0bc`
- name: `wil::details::lambda_call__ProxResManInitialize_::_2_::_lambda_1___::_lambda_call__ProxResManInitialize_::_2_::_lambda_1___`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007c82c`
- `0x18009af71`

## callees

- `0x18007c018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c08d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c08d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c06b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c0a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c06b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c0a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c04c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c04c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18007c063`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18007c063`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18007c05a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18007c05a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c098`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c098`

## pseudocode

```c
void __fastcall wil::details::lambda_call__ProxResManInitialize_::_2_::_lambda_1___::_lambda_call__ProxResManInitialize_::_2_::_lambda_1___(
        __int64 a1)
{
  struct _TP_WAIT *v1; // rdi
  DWORD LastError; // ebx
  HANDLE v3; // rdi
  DWORD v4; // ebx

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
    v1 = g_threadpoolResourceManagerNotification;
    if ( g_threadpoolResourceManagerNotification )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v1, 0, 0);
      WaitForThreadpoolWaitCallbacks(v1, 1);
      CloseThreadpoolWait(v1);
      SetLastError(LastError);
    }
    v3 = g_hResourceManagerNotification;
    g_threadpoolResourceManagerNotification = 0;
    if ( (char *)g_hResourceManagerNotification - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v4 = GetLastError();
      CloseHandle(v3);
      SetLastError(v4);
    }
    g_hResourceManagerNotification = 0;
  }
}

```

## disassembly

```asm
0x18007c018  mov     [rsp+arg_0], rbx
0x18007c01d  push    rdi
0x18007c01e  sub     rsp, 20h
0x18007c022  cmp     byte ptr [rcx+1], 0
0x18007c026  jz      loc_18007C0B1
0x18007c02c  mov     byte ptr [rcx+1], 0
0x18007c030  mov     rdi, cs:?g_threadpoolResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>> g_threadpoolResourceManagerNotification
0x18007c037  test    rdi, rdi
0x18007c03a  jz      short loc_18007C071
0x18007c03c  call    cs:__imp_GetLastError
0x18007c042  xor     r8d, r8d; pftTimeout
0x18007c045  xor     edx, edx; h
0x18007c047  mov     rcx, rdi; pwa
0x18007c04a  mov     ebx, eax
0x18007c04c  call    cs:__imp_SetThreadpoolWait
0x18007c052  mov     edx, 1; fCancelPendingCallbacks
0x18007c057  mov     rcx, rdi; pwa
0x18007c05a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18007c060  mov     rcx, rdi; pwa
0x18007c063  call    cs:__imp_CloseThreadpoolWait
0x18007c069  mov     ecx, ebx; dwErrCode
0x18007c06b  call    cs:__imp_SetLastError
0x18007c071  mov     rdi, cs:?g_hResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hResourceManagerNotification
0x18007c078  mov     cs:?g_threadpoolResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>> g_threadpoolResourceManagerNotification
0x18007c083  lea     rax, [rdi-1]
0x18007c087  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007c08b  ja      short loc_18007C0A6
0x18007c08d  call    cs:__imp_GetLastError
0x18007c093  mov     rcx, rdi; hObject
0x18007c096  mov     ebx, eax
0x18007c098  call    cs:__imp_CloseHandle
0x18007c09e  mov     ecx, ebx; dwErrCode
0x18007c0a0  call    cs:__imp_SetLastError
0x18007c0a6  mov     cs:?g_hResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hResourceManagerNotification
0x18007c0b1  mov     rbx, [rsp+28h+arg_0]
0x18007c0b6  add     rsp, 20h
0x18007c0ba  pop     rdi
0x18007c0bb  retn
```
