# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x1800050f0`
- end: `0x180005140`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003cc4`
- `0x1800050f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180005114`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180005114`

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
0x1800050f0  mov     [rsp+arg_0], rbx
0x1800050f5  push    rdi
0x1800050f6  sub     rsp, 20h
0x1800050fa  mov     rdi, rdx
0x1800050fd  mov     rbx, rcx
0x180005100  test    rdx, rdx
0x180005103  jnz     short loc_18000510C
0x180005105  mov     eax, 80070057h
0x18000510a  jmp     short loc_180005135
0x18000510c  test    r8, r8
0x18000510f  jz      short loc_18000512A
0x180005111  mov     rcx, r8
0x180005114  call    cs:__imp__o__wcsdup
0x18000511a  mov     [rbx+8], rax
0x18000511e  test    rax, rax
0x180005121  jnz     short loc_18000512A
0x180005123  mov     eax, 8007000Eh
0x180005128  jmp     short loc_180005135
0x18000512a  mov     rdx, rdi; struct IUnknown *
0x18000512d  mov     rcx, rbx; this
0x180005130  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180005135  mov     rbx, [rsp+28h+arg_0]
0x18000513a  add     rsp, 20h
0x18000513e  pop     rdi
0x18000513f  retn
```
