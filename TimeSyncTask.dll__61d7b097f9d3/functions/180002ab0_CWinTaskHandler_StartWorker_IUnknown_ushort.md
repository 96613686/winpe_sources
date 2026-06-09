# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180002ab0`
- end: `0x180002b00`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800023c4`
- `0x180002ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180002ad4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180002ad4`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StartWorker(CWinTaskHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  __int64 v6; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  v6 = _o__wcsdup(a3);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180002ab0  mov     [rsp+arg_0], rbx
0x180002ab5  push    rdi
0x180002ab6  sub     rsp, 20h
0x180002aba  mov     rdi, rdx
0x180002abd  mov     rbx, rcx
0x180002ac0  test    rdx, rdx
0x180002ac3  jnz     short loc_180002ACC
0x180002ac5  mov     eax, 80070057h
0x180002aca  jmp     short loc_180002AF5
0x180002acc  test    r8, r8
0x180002acf  jz      short loc_180002AEA
0x180002ad1  mov     rcx, r8
0x180002ad4  call    cs:__imp__o__wcsdup
0x180002ada  mov     [rbx+8], rax
0x180002ade  test    rax, rax
0x180002ae1  jnz     short loc_180002AEA
0x180002ae3  mov     eax, 8007000Eh
0x180002ae8  jmp     short loc_180002AF5
0x180002aea  mov     rdx, rdi; struct IUnknown *
0x180002aed  mov     rcx, rbx; this
0x180002af0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180002af5  mov     rbx, [rsp+28h+arg_0]
0x180002afa  add     rsp, 20h
0x180002afe  pop     rdi
0x180002aff  retn
```
