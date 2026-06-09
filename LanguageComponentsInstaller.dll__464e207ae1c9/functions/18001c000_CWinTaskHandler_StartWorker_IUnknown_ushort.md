# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x18001c000`
- end: `0x18001c050`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800158b8`
- `0x18001c000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18001c024`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18001c024`

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
0x18001c000  mov     [rsp+arg_0], rbx
0x18001c005  push    rdi
0x18001c006  sub     rsp, 20h
0x18001c00a  mov     rdi, rdx
0x18001c00d  mov     rbx, rcx
0x18001c010  test    rdx, rdx
0x18001c013  jnz     short loc_18001C01C
0x18001c015  mov     eax, 80070057h
0x18001c01a  jmp     short loc_18001C045
0x18001c01c  test    r8, r8
0x18001c01f  jz      short loc_18001C03A
0x18001c021  mov     rcx, r8
0x18001c024  call    cs:__imp__o__wcsdup
0x18001c02a  mov     [rbx+8], rax
0x18001c02e  test    rax, rax
0x18001c031  jnz     short loc_18001C03A
0x18001c033  mov     eax, 8007000Eh
0x18001c038  jmp     short loc_18001C045
0x18001c03a  mov     rdx, rdi; struct IUnknown *
0x18001c03d  mov     rcx, rbx; this
0x18001c040  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x18001c045  mov     rbx, [rsp+28h+arg_0]
0x18001c04a  add     rsp, 20h
0x18001c04e  pop     rdi
0x18001c04f  retn
```
