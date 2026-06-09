# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800066b0`
- end: `0x180006700`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003fe4`
- `0x1800066b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800066d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800066d4`

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
0x1800066b0  mov     [rsp+arg_0], rbx
0x1800066b5  push    rdi
0x1800066b6  sub     rsp, 20h
0x1800066ba  mov     rdi, rdx
0x1800066bd  mov     rbx, rcx
0x1800066c0  test    rdx, rdx
0x1800066c3  jnz     short loc_1800066CC
0x1800066c5  mov     eax, 80070057h
0x1800066ca  jmp     short loc_1800066F5
0x1800066cc  test    r8, r8
0x1800066cf  jz      short loc_1800066EA
0x1800066d1  mov     rcx, r8
0x1800066d4  call    cs:__imp__o__wcsdup
0x1800066da  mov     [rbx+8], rax
0x1800066de  test    rax, rax
0x1800066e1  jnz     short loc_1800066EA
0x1800066e3  mov     eax, 8007000Eh
0x1800066e8  jmp     short loc_1800066F5
0x1800066ea  mov     rdx, rdi; struct IUnknown *
0x1800066ed  mov     rcx, rbx; this
0x1800066f0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x1800066f5  mov     rbx, [rsp+28h+arg_0]
0x1800066fa  add     rsp, 20h
0x1800066fe  pop     rdi
0x1800066ff  retn
```
