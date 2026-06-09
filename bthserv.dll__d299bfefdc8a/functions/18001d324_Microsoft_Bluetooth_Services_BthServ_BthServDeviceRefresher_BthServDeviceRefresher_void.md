# Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(void)

- ea: `0x18001d324`
- end: `0x18001d3a9`
- name: `??1BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a384`
- `0x18000a820`
- `0x18000a850`
- `0x18000f35c`

## callees

- `0x180001b60`
- `0x18001d324`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d35a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d35a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001d349`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001d349`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001d352`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001d352`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(
        Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *this)
{
  struct _TP_WORK *v1; // rbp
  DWORD LastError; // ebx
  _QWORD **v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx

  v1 = (struct _TP_WORK *)*((_QWORD *)this + 4);
  if ( v1 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v1, 1);
    CloseThreadpoolWork(v1);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 4) = 0;
  v4 = (_QWORD **)*((_QWORD *)this + 2);
  *v4[1] = 0;
  v5 = *v4;
  if ( v5 )
  {
    do
    {
      v6 = (_QWORD *)*v5;
      operator delete(v5, (const struct std::nothrow_t *)0x20);
      v5 = v6;
    }
    while ( v6 );
  }
  operator delete(*((void **)this + 2), (const struct std::nothrow_t *)0x20);
}

```

## disassembly

```asm
0x18001d324  push    rbx
0x18001d326  push    rbp
0x18001d327  push    rsi
0x18001d328  push    rdi
0x18001d329  sub     rsp, 28h
0x18001d32d  mov     rbp, [rcx+20h]
0x18001d331  mov     rdi, rcx
0x18001d334  test    rbp, rbp
0x18001d337  jz      short loc_18001D360
0x18001d339  call    cs:__imp_GetLastError
0x18001d33f  mov     edx, 1; fCancelPendingCallbacks
0x18001d344  mov     rcx, rbp; pwk
0x18001d347  mov     ebx, eax
0x18001d349  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001d34f  mov     rcx, rbp; pwk
0x18001d352  call    cs:__imp_CloseThreadpoolWork
0x18001d358  mov     ecx, ebx; dwErrCode
0x18001d35a  call    cs:__imp_SetLastError
0x18001d360  xor     eax, eax
0x18001d362  mov     esi, 20h ; ' '
0x18001d367  mov     [rdi+20h], rax
0x18001d36b  mov     rcx, [rdi+10h]
0x18001d36f  mov     rax, [rcx+8]
0x18001d373  mov     qword ptr [rax], 0
0x18001d37a  mov     rcx, [rcx]; void *
0x18001d37d  test    rcx, rcx
0x18001d380  jz      short loc_18001D395
0x18001d382  mov     rbx, [rcx]
0x18001d385  mov     rdx, rsi; struct std::nothrow_t *
0x18001d388  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d38d  mov     rcx, rbx
0x18001d390  test    rbx, rbx
0x18001d393  jnz     short loc_18001D382
0x18001d395  mov     rcx, [rdi+10h]; void *
0x18001d399  mov     rdx, rsi; struct std::nothrow_t *
0x18001d39c  add     rsp, 28h
0x18001d3a0  pop     rdi
0x18001d3a1  pop     rsi
0x18001d3a2  pop     rbp
0x18001d3a3  pop     rbx
0x18001d3a4  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
