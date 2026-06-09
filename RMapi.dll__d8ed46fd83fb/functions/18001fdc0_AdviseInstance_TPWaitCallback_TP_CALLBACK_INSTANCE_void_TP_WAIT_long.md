# AdviseInstance::TPWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18001fdc0`
- end: `0x18001fdf2`
- name: `?TPWaitCallback@AdviseInstance@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `50`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180028010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001fdd0`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18001fdd0`

## pseudocode

```c
void __fastcall AdviseInstance::TPWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _DWORD *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 v4; // rbx
  unsigned int v5; // edi

  v4 = *(_QWORD *)Context;
  v5 = Context[6];
  DisassociateCurrentThreadFromCallback(Instance);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v4 + 8) + 48LL))(v4 + 8, v5);
}

```

## disassembly

```asm
0x18001fdc0  mov     [rsp+arg_0], rbx
0x18001fdc5  push    rdi
0x18001fdc6  sub     rsp, 20h
0x18001fdca  mov     rbx, [rdx]
0x18001fdcd  mov     edi, [rdx+18h]
0x18001fdd0  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18001fdd6  lea     rcx, [rbx+8]
0x18001fdda  mov     edx, edi
0x18001fddc  mov     rax, [rcx]
0x18001fddf  mov     rax, [rax+30h]
0x18001fde3  mov     rbx, [rsp+28h+arg_0]
0x18001fde8  add     rsp, 20h
0x18001fdec  pop     rdi
0x18001fded  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
