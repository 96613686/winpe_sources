# Windows::Management::Provisioning::OperationServerBase::OnStart(void)

- ea: `0x1800761e0`
- end: `0x18007627f`
- name: `?OnStart@OperationServerBase@Provisioning@Management@Windows@@MEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::OperationServerBase *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18003abb4`
- `0x1800761e0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076220`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180076249`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180076249`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180076212`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180076212`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180076267`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180076267`

## pseudocode

```c
__int64 __fastcall Windows::Management::Provisioning::OperationServerBase::OnStart(
        Windows::Management::Provisioning::OperationServerBase *this)
{
  char *v1; // rdi
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v4; // rsi
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  int v8; // r9d

  v1 = (char *)this - 16;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 8LL))((char *)this - 16);
  ThreadpoolWork = CreateThreadpoolWork(Windows::Management::Provisioning::OperationServerBase::DoAsyncStub, v1, 0);
  v4 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    wil::handle_wait(*((wil **)this + 17), (void *)0xFFFFFFFFLL, v7, v8);
    v6 = *((_DWORD *)this + 37);
    CloseThreadpoolWork(v4);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v1 + 16LL))(v1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800761e0  mov     [rsp+arg_0], rbx
0x1800761e5  mov     [rsp+arg_8], rsi
0x1800761ea  push    rdi
0x1800761eb  sub     rsp, 20h
0x1800761ef  lea     rdi, [rcx-10h]
0x1800761f3  mov     rbx, rcx
0x1800761f6  mov     rax, [rdi]
0x1800761f9  mov     rcx, rdi
0x1800761fc  mov     rax, [rax+8]
0x180076200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076205  xor     r8d, r8d; pcbe
0x180076208  lea     rcx, ?DoAsyncStub@OperationServerBase@Provisioning@Management@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18007620f  mov     rdx, rdi; pv
0x180076212  call    cs:__imp_CreateThreadpoolWork
0x180076218  mov     rsi, rax
0x18007621b  test    rax, rax
0x18007621e  jnz     short loc_180076246
0x180076220  call    cs:__imp_GetLastError
0x180076226  mov     ebx, eax
0x180076228  test    eax, eax
0x18007622a  jle     short loc_180076235
0x18007622c  movzx   ebx, ax
0x18007622f  or      ebx, 80070000h
0x180076235  mov     rax, [rdi]
0x180076238  mov     rcx, rdi
0x18007623b  mov     rax, [rax+10h]
0x18007623f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076244  jmp     short loc_18007626D
0x180076246  mov     rcx, rsi; pwk
0x180076249  call    cs:__imp_SubmitThreadpoolWork
0x18007624f  mov     rcx, [rbx+88h]; this
0x180076256  or      edx, 0FFFFFFFFh; void *
0x180076259  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x18007625e  mov     ebx, [rbx+94h]
0x180076264  mov     rcx, rsi; pwk
0x180076267  call    cs:__imp_CloseThreadpoolWork
0x18007626d  mov     rsi, [rsp+28h+arg_8]
0x180076272  mov     eax, ebx
0x180076274  mov     rbx, [rsp+28h+arg_0]
0x180076279  add     rsp, 20h
0x18007627d  pop     rdi
0x18007627e  retn
```
