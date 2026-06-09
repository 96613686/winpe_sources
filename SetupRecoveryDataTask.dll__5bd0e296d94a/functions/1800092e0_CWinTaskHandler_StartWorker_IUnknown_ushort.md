# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800092e0`
- end: `0x180009330`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, wchar_t *String)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004444`
- `0x1800092e0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180009304`
- `msvcrt!_wcsdup` at `0x180009304`

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
0x1800092e0  mov     [rsp+arg_0], rbx
0x1800092e5  push    rdi
0x1800092e6  sub     rsp, 20h
0x1800092ea  mov     rdi, rdx
0x1800092ed  mov     rbx, rcx
0x1800092f0  test    rdx, rdx
0x1800092f3  jnz     short loc_1800092FC
0x1800092f5  mov     eax, 80070057h
0x1800092fa  jmp     short loc_180009325
0x1800092fc  test    r8, r8
0x1800092ff  jz      short loc_18000931A
0x180009301  mov     rcx, r8; String
0x180009304  call    cs:__imp__wcsdup
0x18000930a  mov     [rbx+8], rax
0x18000930e  test    rax, rax
0x180009311  jnz     short loc_18000931A
0x180009313  mov     eax, 8007000Eh
0x180009318  jmp     short loc_180009325
0x18000931a  mov     rdx, rdi; struct IUnknown *
0x18000931d  mov     rcx, rbx; this
0x180009320  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180009325  mov     rbx, [rsp+28h+arg_0]
0x18000932a  add     rsp, 20h
0x18000932e  pop     rdi
0x18000932f  retn
```
