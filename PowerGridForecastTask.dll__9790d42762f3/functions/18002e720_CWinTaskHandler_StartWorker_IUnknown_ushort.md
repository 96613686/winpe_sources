# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x18002e720`
- end: `0x18002e770`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180029584`
- `0x18002e720`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18002e744`
- `msvcrt!_wcsdup` at `0x18002e744`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StartWorker(CWinTaskHandler *this, struct IUnknown *a2, wchar_t *String)
{
  wchar_t *v6; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( !String )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  v6 = _wcsdup(String);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
    return CWinTaskHandler::CreateWorkerThread(this, a2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002e720  mov     [rsp+arg_0], rbx
0x18002e725  push    rdi
0x18002e726  sub     rsp, 20h
0x18002e72a  mov     rdi, rdx
0x18002e72d  mov     rbx, rcx
0x18002e730  test    rdx, rdx
0x18002e733  jnz     short loc_18002E73C
0x18002e735  mov     eax, 80070057h
0x18002e73a  jmp     short loc_18002E765
0x18002e73c  test    r8, r8
0x18002e73f  jz      short loc_18002E75A
0x18002e741  mov     rcx, r8; String
0x18002e744  call    cs:__imp__wcsdup
0x18002e74a  mov     [rbx+8], rax
0x18002e74e  test    rax, rax
0x18002e751  jnz     short loc_18002E75A
0x18002e753  mov     eax, 8007000Eh
0x18002e758  jmp     short loc_18002E765
0x18002e75a  mov     rdx, rdi; struct IUnknown *
0x18002e75d  mov     rcx, rbx; this
0x18002e760  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x18002e765  mov     rbx, [rsp+28h+arg_0]
0x18002e76a  add     rsp, 20h
0x18002e76e  pop     rdi
0x18002e76f  retn
```
