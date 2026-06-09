# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800036c0`
- end: `0x180003710`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002d18`
- `0x1800036c0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x1800036e4`
- `msvcrt!_wcsdup` at `0x1800036e4`

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
0x1800036c0  mov     [rsp+arg_0], rbx
0x1800036c5  push    rdi
0x1800036c6  sub     rsp, 20h
0x1800036ca  mov     rdi, rdx
0x1800036cd  mov     rbx, rcx
0x1800036d0  test    rdx, rdx
0x1800036d3  jnz     short loc_1800036DC
0x1800036d5  mov     eax, 80070057h
0x1800036da  jmp     short loc_180003705
0x1800036dc  test    r8, r8
0x1800036df  jz      short loc_1800036FA
0x1800036e1  mov     rcx, r8; String
0x1800036e4  call    cs:__imp__wcsdup
0x1800036ea  mov     [rbx+8], rax
0x1800036ee  test    rax, rax
0x1800036f1  jnz     short loc_1800036FA
0x1800036f3  mov     eax, 8007000Eh
0x1800036f8  jmp     short loc_180003705
0x1800036fa  mov     rdx, rdi; struct IUnknown *
0x1800036fd  mov     rcx, rbx; this
0x180003700  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180003705  mov     rbx, [rsp+28h+arg_0]
0x18000370a  add     rsp, 20h
0x18000370e  pop     rdi
0x18000370f  retn
```
