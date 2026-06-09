# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180006800`
- end: `0x180006850`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003d68`
- `0x180006800`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180006824`
- `msvcrt!_wcsdup` at `0x180006824`

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
0x180006800  mov     [rsp+arg_0], rbx
0x180006805  push    rdi
0x180006806  sub     rsp, 20h
0x18000680a  mov     rdi, rdx
0x18000680d  mov     rbx, rcx
0x180006810  test    rdx, rdx
0x180006813  jnz     short loc_18000681C
0x180006815  mov     eax, 80070057h
0x18000681a  jmp     short loc_180006845
0x18000681c  test    r8, r8
0x18000681f  jz      short loc_18000683A
0x180006821  mov     rcx, r8; String
0x180006824  call    cs:__imp__wcsdup
0x18000682a  mov     [rbx+8], rax
0x18000682e  test    rax, rax
0x180006831  jnz     short loc_18000683A
0x180006833  mov     eax, 8007000Eh
0x180006838  jmp     short loc_180006845
0x18000683a  mov     rdx, rdi; struct IUnknown *
0x18000683d  mov     rcx, rbx; this
0x180006840  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180006845  mov     rbx, [rsp+28h+arg_0]
0x18000684a  add     rsp, 20h
0x18000684e  pop     rdi
0x18000684f  retn
```
