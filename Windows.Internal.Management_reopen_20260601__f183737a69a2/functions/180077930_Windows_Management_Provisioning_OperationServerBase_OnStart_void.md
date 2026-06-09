# Windows::Management::Provisioning::OperationServerBase::OnStart(void)

- ea: `0x180077930`
- end: `0x1800779e8`
- name: `?OnStart@OperationServerBase@Provisioning@Management@Windows@@MEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::OperationServerBase *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180039f24`
- `0x180077930`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077976`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800779a5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800779a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180077962`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180077962`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800779c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800779c9`

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
0x180077930  mov     [rsp+arg_0], rbx
0x180077935  mov     [rsp+arg_8], rsi
0x18007793a  push    rdi
0x18007793b  sub     rsp, 20h
0x18007793f  lea     rdi, [rcx-10h]
0x180077943  mov     rbx, rcx
0x180077946  mov     rax, [rdi]
0x180077949  mov     rcx, rdi
0x18007794c  mov     rax, [rax+8]
0x180077950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077955  xor     r8d, r8d; pcbe
0x180077958  lea     rcx, ?DoAsyncStub@OperationServerBase@Provisioning@Management@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18007795f  mov     rdx, rdi; pv
0x180077962  call    cs:__imp_CreateThreadpoolWork
0x180077969  nop     dword ptr [rax+rax+00h]
0x18007796e  mov     rsi, rax
0x180077971  test    rax, rax
0x180077974  jnz     short loc_1800779A2
0x180077976  call    cs:__imp_GetLastError
0x18007797d  nop     dword ptr [rax+rax+00h]
0x180077982  mov     ebx, eax
0x180077984  test    eax, eax
0x180077986  jle     short loc_180077991
0x180077988  movzx   ebx, ax
0x18007798b  or      ebx, 80070000h
0x180077991  mov     rax, [rdi]
0x180077994  mov     rcx, rdi
0x180077997  mov     rax, [rax+10h]
0x18007799b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779a0  jmp     short loc_1800779D5
0x1800779a2  mov     rcx, rsi; pwk
0x1800779a5  call    cs:__imp_SubmitThreadpoolWork
0x1800779ac  nop     dword ptr [rax+rax+00h]
0x1800779b1  mov     rcx, [rbx+88h]; this
0x1800779b8  or      edx, 0FFFFFFFFh; void *
0x1800779bb  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800779c0  mov     ebx, [rbx+94h]
0x1800779c6  mov     rcx, rsi; pwk
0x1800779c9  call    cs:__imp_CloseThreadpoolWork
0x1800779d0  nop     dword ptr [rax+rax+00h]
0x1800779d5  mov     rsi, [rsp+28h+arg_8]
0x1800779da  mov     eax, ebx
0x1800779dc  mov     rbx, [rsp+28h+arg_0]
0x1800779e1  add     rsp, 20h
0x1800779e5  pop     rdi
0x1800779e6  retn
```
