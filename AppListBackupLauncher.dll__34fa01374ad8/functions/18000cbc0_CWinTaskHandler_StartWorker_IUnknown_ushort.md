# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x18000cbc0`
- end: `0x18000cc10`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180007374`
- `0x18000cbc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000cbe4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000cbe4`

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
0x18000cbc0  mov     [rsp+arg_0], rbx
0x18000cbc5  push    rdi
0x18000cbc6  sub     rsp, 20h
0x18000cbca  mov     rdi, rdx
0x18000cbcd  mov     rbx, rcx
0x18000cbd0  test    rdx, rdx
0x18000cbd3  jnz     short loc_18000CBDC
0x18000cbd5  mov     eax, 80070057h
0x18000cbda  jmp     short loc_18000CC05
0x18000cbdc  test    r8, r8
0x18000cbdf  jz      short loc_18000CBFA
0x18000cbe1  mov     rcx, r8
0x18000cbe4  call    cs:__imp__o__wcsdup
0x18000cbea  mov     [rbx+8], rax
0x18000cbee  test    rax, rax
0x18000cbf1  jnz     short loc_18000CBFA
0x18000cbf3  mov     eax, 8007000Eh
0x18000cbf8  jmp     short loc_18000CC05
0x18000cbfa  mov     rdx, rdi; struct IUnknown *
0x18000cbfd  mov     rcx, rbx; this
0x18000cc00  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x18000cc05  mov     rbx, [rsp+28h+arg_0]
0x18000cc0a  add     rsp, 20h
0x18000cc0e  pop     rdi
0x18000cc0f  retn
```
