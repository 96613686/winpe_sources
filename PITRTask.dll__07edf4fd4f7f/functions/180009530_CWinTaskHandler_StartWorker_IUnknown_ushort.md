# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180009530`
- end: `0x180009580`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800049c4`
- `0x180009530`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180009554`
- `msvcrt!_wcsdup` at `0x180009554`

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
0x180009530  mov     [rsp+arg_0], rbx
0x180009535  push    rdi
0x180009536  sub     rsp, 20h
0x18000953a  mov     rdi, rdx
0x18000953d  mov     rbx, rcx
0x180009540  test    rdx, rdx
0x180009543  jnz     short loc_18000954C
0x180009545  mov     eax, 80070057h
0x18000954a  jmp     short loc_180009575
0x18000954c  test    r8, r8
0x18000954f  jz      short loc_18000956A
0x180009551  mov     rcx, r8; String
0x180009554  call    cs:__imp__wcsdup
0x18000955a  mov     [rbx+8], rax
0x18000955e  test    rax, rax
0x180009561  jnz     short loc_18000956A
0x180009563  mov     eax, 8007000Eh
0x180009568  jmp     short loc_180009575
0x18000956a  mov     rdx, rdi; struct IUnknown *
0x18000956d  mov     rcx, rbx; this
0x180009570  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180009575  mov     rbx, [rsp+28h+arg_0]
0x18000957a  add     rsp, 20h
0x18000957e  pop     rdi
0x18000957f  retn
```
