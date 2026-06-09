# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180002d40`
- end: `0x180002d90`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002664`
- `0x180002d40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180002d64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180002d64`

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
0x180002d40  mov     [rsp+arg_0], rbx
0x180002d45  push    rdi
0x180002d46  sub     rsp, 20h
0x180002d4a  mov     rdi, rdx
0x180002d4d  mov     rbx, rcx
0x180002d50  test    rdx, rdx
0x180002d53  jnz     short loc_180002D5C
0x180002d55  mov     eax, 80070057h
0x180002d5a  jmp     short loc_180002D85
0x180002d5c  test    r8, r8
0x180002d5f  jz      short loc_180002D7A
0x180002d61  mov     rcx, r8
0x180002d64  call    cs:__imp__o__wcsdup
0x180002d6a  mov     [rbx+8], rax
0x180002d6e  test    rax, rax
0x180002d71  jnz     short loc_180002D7A
0x180002d73  mov     eax, 8007000Eh
0x180002d78  jmp     short loc_180002D85
0x180002d7a  mov     rdx, rdi; struct IUnknown *
0x180002d7d  mov     rcx, rbx; this
0x180002d80  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180002d85  mov     rbx, [rsp+28h+arg_0]
0x180002d8a  add     rsp, 20h
0x180002d8e  pop     rdi
0x180002d8f  retn
```
