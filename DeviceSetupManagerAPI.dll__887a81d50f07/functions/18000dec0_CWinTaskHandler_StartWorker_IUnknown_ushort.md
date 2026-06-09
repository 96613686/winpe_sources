# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x18000dec0`
- end: `0x18000df10`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000dab4`
- `0x18000dec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000dee4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000dee4`

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
0x18000dec0  mov     [rsp+arg_0], rbx
0x18000dec5  push    rdi
0x18000dec6  sub     rsp, 20h
0x18000deca  mov     rdi, rdx
0x18000decd  mov     rbx, rcx
0x18000ded0  test    rdx, rdx
0x18000ded3  jnz     short loc_18000DEDC
0x18000ded5  mov     eax, 80070057h
0x18000deda  jmp     short loc_18000DF05
0x18000dedc  test    r8, r8
0x18000dedf  jz      short loc_18000DEFA
0x18000dee1  mov     rcx, r8
0x18000dee4  call    cs:__imp__o__wcsdup
0x18000deea  mov     [rbx+8], rax
0x18000deee  test    rax, rax
0x18000def1  jnz     short loc_18000DEFA
0x18000def3  mov     eax, 8007000Eh
0x18000def8  jmp     short loc_18000DF05
0x18000defa  mov     rdx, rdi; struct IUnknown *
0x18000defd  mov     rcx, rbx; this
0x18000df00  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x18000df05  mov     rbx, [rsp+28h+arg_0]
0x18000df0a  add     rsp, 20h
0x18000df0e  pop     rdi
0x18000df0f  retn
```
