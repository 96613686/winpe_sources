# RWService::OnStarting(void)

- ea: `0x180008cd0`
- end: `0x180008ec1`
- name: `?OnStarting@RWService@@UEAAJXZ`
- size: `497`
- prototype: `__int64 __fastcall(LPVOID *pv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c0`
- `0x180005ab0`
- `0x180008cd0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008e6d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008e6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008cea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008d4d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008cea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d19`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180008e8e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180008e8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008eab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008eab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008dc5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008dc5`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180008dea`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180008dea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008e1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008e1a`

## string_xrefs

- `0x180008d8f`: `WalletServiceIdleShutdown`

## pseudocode

```c
__int64 __fastcall RWService::OnStarting(LPVOID *pv)
{
  HANDLE *v2; // rsi
  signed int LastError; // eax
  HRESULT Instance; // ebx
  unsigned int v5; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  HANDLE pvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF

  v2 = pv + 24;
  pvData = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::operator=(v2, &pvData);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&pvData);
  if ( *v2
    && (pvData = CreateEventW(0, 0, 0, 0),
        tlx::unique_any<tlx::file_handle_traits>::operator=(&g_hCOMReg, &pvData),
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&pvData),
        g_hCOMReg) )
  {
    LODWORD(pvData) = 0;
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Wallet",
           L"WalletServiceIdleShutdown",
           0x10u,
           0,
           &pvData,
           &pcbData) )
    {
      v5 = g_cSecondsUntilShutdown;
    }
    else
    {
      v5 = (unsigned int)pvData;
      g_cSecondsUntilShutdown = (unsigned int)pvData;
    }
    Instance = CoRegisterServerShutdownDelay(*v2, 1000 * v5);
    if ( Instance >= 0 )
    {
      Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, pv + 25);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)pv[25] + 24LL))(
                     pv[25],
                     RegisterClassObjectsCallback,
                     0,
                     &GUID_000001da_0000_0000_c000_000000000046,
                     5,
                     0);
        if ( Instance >= 0 )
        {
          if ( WaitForSingleObject(g_hCOMReg, 0x1388u) == 258 )
            return (unsigned int)-2147418113;
          ThreadpoolWait = CreateThreadpoolWait(ServiceIdleWaitCallback, pv, 0);
          if ( (pv[23] = ThreadpoolWait) == 0 )
          {
            return (unsigned int)-2147418113;
          }
          else
          {
            Instance = 0;
            SetThreadpoolWait(ThreadpoolWait, *v2, 0);
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2143748092;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180008cd0  mov     [rsp+arg_10], rbx
0x180008cd5  push    rsi
0x180008cd6  push    rdi
0x180008cd7  push    r14
0x180008cd9  sub     rsp, 40h
0x180008cdd  mov     rdi, rcx
0x180008ce0  xor     r9d, r9d; lpName
0x180008ce3  xor     ecx, ecx; lpEventAttributes
0x180008ce5  xor     r8d, r8d; bInitialState
0x180008ce8  xor     edx, edx; bManualReset
0x180008cea  call    cs:__imp_CreateEventW
0x180008cf0  lea     rsi, [rdi+0C0h]
0x180008cf7  mov     [rsp+58h+arg_0], rax
0x180008cfc  mov     rcx, rsi
0x180008cff  lea     rdx, [rsp+58h+arg_0]
0x180008d04  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x180008d09  lea     rcx, [rsp+58h+arg_0]
0x180008d0e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180008d13  cmp     qword ptr [rsi], 0
0x180008d17  jnz     short loc_180008D43
0x180008d19  call    cs:__imp_GetLastError
0x180008d1f  mov     ebx, eax
0x180008d21  test    eax, eax
0x180008d23  jz      short loc_180008D39
0x180008d25  jle     loc_180008EB1
0x180008d2b  movzx   ebx, ax
0x180008d2e  or      ebx, 80070000h
0x180008d34  jmp     loc_180008EB1
0x180008d39  mov     ebx, 80390004h
0x180008d3e  jmp     loc_180008EB1
0x180008d43  xor     r9d, r9d; lpName
0x180008d46  xor     r8d, r8d; bInitialState
0x180008d49  xor     edx, edx; bManualReset
0x180008d4b  xor     ecx, ecx; lpEventAttributes
0x180008d4d  call    cs:__imp_CreateEventW
0x180008d53  lea     rdx, [rsp+58h+arg_0]
0x180008d58  mov     [rsp+58h+arg_0], rax
0x180008d5d  lea     rcx, ?g_hCOMReg@@3V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A; tlx::unique_any<tlx::file_handle_traits> g_hCOMReg
0x180008d64  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x180008d69  lea     rcx, [rsp+58h+arg_0]
0x180008d6e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180008d73  cmp     cs:?g_hCOMReg@@3V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A, 0; tlx::unique_any<tlx::file_handle_traits> g_hCOMReg
0x180008d7b  jz      short loc_180008D19
0x180008d7d  lea     rax, [rsp+58h+arg_8]
0x180008d82  mov     dword ptr [rsp+58h+arg_0], 0
0x180008d8a  mov     [rsp+58h+pcbData], rax; pcbData
0x180008d8f  lea     r8, ?sc_szServiceIdleShutdownValue@@3QBGB; "WalletServiceIdleShutdown"
0x180008d96  lea     rax, [rsp+58h+arg_0]
0x180008d9b  mov     [rsp+58h+arg_8], 4
0x180008da3  mov     [rsp+58h+pvData], rax; pvData
0x180008da8  lea     rdx, ?sc_szServiceIdleShutdownKey@@3QBGB; "Software\\Microsoft\\Wallet"
0x180008daf  mov     r9d, 10h; dwFlags
0x180008db5  mov     [rsp+58h+pdwType], 0; pdwType
0x180008dbe  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008dc5  call    cs:__imp_RegGetValueW
0x180008dcb  test    eax, eax
0x180008dcd  jnz     short loc_180008DDB
0x180008dcf  mov     eax, dword ptr [rsp+58h+arg_0]
0x180008dd3  mov     cs:?g_cSecondsUntilShutdown@@3KA, eax; ulong g_cSecondsUntilShutdown
0x180008dd9  jmp     short loc_180008DE1
0x180008ddb  mov     eax, cs:?g_cSecondsUntilShutdown@@3KA; ulong g_cSecondsUntilShutdown
0x180008de1  mov     rcx, [rsi]
0x180008de4  imul    edx, eax, 3E8h
0x180008dea  call    cs:__imp_CoRegisterServerShutdownDelay
0x180008df0  mov     ebx, eax
0x180008df2  test    eax, eax
0x180008df4  js      loc_180008EB1
0x180008dfa  xor     edx, edx; pUnkOuter
0x180008dfc  lea     r14, [rdi+0C8h]
0x180008e03  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180008e0a  mov     [rsp+58h+pdwType], r14; ppv
0x180008e0f  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180008e16  lea     r8d, [rdx+1]; dwClsContext
0x180008e1a  call    cs:__imp_CoCreateInstance
0x180008e20  mov     ebx, eax
0x180008e22  test    eax, eax
0x180008e24  js      loc_180008EB1
0x180008e2a  mov     rcx, [r14]
0x180008e2d  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x180008e34  mov     [rsp+58h+pvData], 0
0x180008e3d  lea     rdx, ?RegisterClassObjectsCallback@@YAJPEAUtagComCallData@@@Z; RegisterClassObjectsCallback(tagComCallData *)
0x180008e44  xor     r8d, r8d
0x180008e47  mov     dword ptr [rsp+58h+pdwType], 5
0x180008e4f  mov     rax, [rcx]
0x180008e52  mov     rax, [rax+18h]
0x180008e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e5b  mov     ebx, eax
0x180008e5d  test    eax, eax
0x180008e5f  js      short loc_180008EB1
0x180008e61  mov     rcx, cs:?g_hCOMReg@@3V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A; hHandle
0x180008e68  mov     edx, 1388h; dwMilliseconds
0x180008e6d  call    cs:__imp_WaitForSingleObject
0x180008e73  cmp     eax, 102h
0x180008e78  jnz     short loc_180008E81
0x180008e7a  mov     ebx, 8000FFFFh
0x180008e7f  jmp     short loc_180008EB1
0x180008e81  xor     r8d, r8d; pcbe
0x180008e84  lea     rcx, ?ServiceIdleWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180008e8b  mov     rdx, rdi; pv
0x180008e8e  call    cs:__imp_CreateThreadpoolWait
0x180008e94  mov     [rdi+0B8h], rax
0x180008e9b  test    rax, rax
0x180008e9e  jz      short loc_180008E7A
0x180008ea0  mov     rdx, [rsi]; h
0x180008ea3  xor     ebx, ebx
0x180008ea5  xor     r8d, r8d; pftTimeout
0x180008ea8  mov     rcx, rax; pwa
0x180008eab  call    cs:__imp_SetThreadpoolWait
0x180008eb1  mov     eax, ebx
0x180008eb3  mov     rbx, [rsp+58h+arg_10]
0x180008eb8  add     rsp, 40h
0x180008ebc  pop     r14
0x180008ebe  pop     rdi
0x180008ebf  pop     rsi
0x180008ec0  retn
```
