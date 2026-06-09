# Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::BthServDeviceRefresher(void)

- ea: `0x18001d1c0`
- end: `0x18001d26d`
- name: `??0BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ`
- size: `173`
- prototype: `_BYTE *__fastcall(_BYTE *pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a384`

## callees

- `0x180001b9c`
- `0x18001d1c0`
- `0x18001d95c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d21a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d23b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d23b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d208`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d208`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001d22a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001d22a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001d233`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001d233`

## string_xrefs

- `0x18001d25b`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\bthservdevicerefresher.cpp`

## pseudocode

```c
_BYTE *__fastcall Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::BthServDeviceRefresher(_BYTE *pv)
{
  _QWORD *v2; // rax
  PTP_WORK ThreadpoolWork; // rsi
  const char *v4; // r9
  struct _TP_WORK *v5; // rbp
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)pv = 0;
  pv[8] = 0;
  *((_QWORD *)pv + 2) = 0;
  *((_QWORD *)pv + 3) = 0;
  v2 = operator new(0x20u);
  *v2 = v2;
  v2[1] = v2;
  *((_QWORD *)pv + 2) = v2;
  *((_QWORD *)pv + 4) = 0;
  ThreadpoolWork = CreateThreadpoolWork(
                     Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesCallBack,
                     pv,
                     0);
  v5 = (struct _TP_WORK *)*((_QWORD *)pv + 4);
  if ( v5 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v5, 1);
    CloseThreadpoolWork(v5);
    SetLastError(LastError);
  }
  *((_QWORD *)pv + 4) = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\bthservdevicerefresher.cpp",
      v4);
  return pv;
}

```

## disassembly

```asm
0x18001d1c0  mov     [rsp+arg_0], rcx
0x18001d1c5  push    rbx
0x18001d1c6  push    rbp
0x18001d1c7  push    rsi
0x18001d1c8  push    rdi
0x18001d1c9  sub     rsp, 28h
0x18001d1cd  mov     rdi, rcx
0x18001d1d0  xor     eax, eax
0x18001d1d2  mov     [rcx], rax
0x18001d1d5  mov     [rcx+8], al
0x18001d1d8  mov     [rcx+10h], rax
0x18001d1dc  mov     [rcx+18h], rax
0x18001d1e0  lea     ecx, [rax+20h]; Size
0x18001d1e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d1e8  mov     [rax], rax
0x18001d1eb  mov     [rax+8], rax
0x18001d1ef  mov     [rdi+10h], rax
0x18001d1f3  mov     qword ptr [rdi+20h], 0
0x18001d1fb  xor     r8d, r8d; pcbe
0x18001d1fe  mov     rdx, rdi; pv
0x18001d201  lea     rcx, ?RefreshBrServicesCallBack@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001d208  call    cs:__imp_CreateThreadpoolWork
0x18001d20e  mov     rsi, rax
0x18001d211  mov     rbp, [rdi+20h]
0x18001d215  test    rbp, rbp
0x18001d218  jz      short loc_18001D241
0x18001d21a  call    cs:__imp_GetLastError
0x18001d220  mov     ebx, eax
0x18001d222  mov     edx, 1; fCancelPendingCallbacks
0x18001d227  mov     rcx, rbp; pwk
0x18001d22a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001d230  mov     rcx, rbp; pwk
0x18001d233  call    cs:__imp_CloseThreadpoolWork
0x18001d239  mov     ecx, ebx; dwErrCode
0x18001d23b  call    cs:__imp_SetLastError
0x18001d241  mov     [rdi+20h], rsi
0x18001d245  mov     rcx, [rsp+48h]; this
0x18001d24a  test    rsi, rsi
0x18001d24d  jz      short loc_18001D25B
0x18001d24f  mov     rax, rdi
0x18001d252  add     rsp, 28h
0x18001d256  pop     rdi
0x18001d257  pop     rsi
0x18001d258  pop     rbp
0x18001d259  pop     rbx
0x18001d25a  retn
0x18001d25b  lea     r8, aOnecoreDrivers_10; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18001d262  mov     edx, 1Dh; void *
0x18001d267  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
