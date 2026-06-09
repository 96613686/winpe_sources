# CWinTaskHandler::StartWorker(IUnknown *,ushort *)

- ea: `0x180007bb0`
- end: `0x180007c00`
- name: `?StartWorker@CWinTaskHandler@@MEAAJPEAUIUnknown@@PEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004274`
- `0x180007bb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180007bd4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180007bd4`

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
0x180007bb0  mov     [rsp+arg_0], rbx
0x180007bb5  push    rdi
0x180007bb6  sub     rsp, 20h
0x180007bba  mov     rdi, rdx
0x180007bbd  mov     rbx, rcx
0x180007bc0  test    rdx, rdx
0x180007bc3  jnz     short loc_180007BCC
0x180007bc5  mov     eax, 80070057h
0x180007bca  jmp     short loc_180007BF5
0x180007bcc  test    r8, r8
0x180007bcf  jz      short loc_180007BEA
0x180007bd1  mov     rcx, r8
0x180007bd4  call    cs:__imp__o__wcsdup
0x180007bda  mov     [rbx+8], rax
0x180007bde  test    rax, rax
0x180007be1  jnz     short loc_180007BEA
0x180007be3  mov     eax, 8007000Eh
0x180007be8  jmp     short loc_180007BF5
0x180007bea  mov     rdx, rdi; struct IUnknown *
0x180007bed  mov     rcx, rbx; this
0x180007bf0  call    ?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z; CWinTaskHandler::CreateWorkerThread(IUnknown *)
0x180007bf5  mov     rbx, [rsp+28h+arg_0]
0x180007bfa  add     rsp, 20h
0x180007bfe  pop     rdi
0x180007bff  retn
```
