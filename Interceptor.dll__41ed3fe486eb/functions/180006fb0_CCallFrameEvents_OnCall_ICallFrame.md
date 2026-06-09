# CCallFrameEvents::OnCall(ICallFrame *)

- ea: `0x180006fb0`
- end: `0x180007036`
- name: `?OnCall@CCallFrameEvents@@UEAAJPEAUICallFrame@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(CCallFrameEvents *__hidden this, struct ICallFrame *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180006fb0`
- `0x18002515c`
- `0x18002b3c0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180007002`
- `ole32!CoTaskMemFree` at `0x18000700d`
- `ole32!CoTaskMemFree` at `0x180007002`
- `ole32!CoTaskMemFree` at `0x18000700d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCallFrameEvents::OnCall(CCallFrameEvents *this, struct ICallFrame *a2)
{
  unsigned int v4; // ebx
  char v6; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF
  LPVOID v8; // [rsp+40h] [rbp+18h] BYREF

  JITVirtualize::JITVirtualize((JITVirtualize *)&v6);
  ((void (__fastcall *)(struct ICallFrame *, LPVOID *, LPVOID *))a2->lpVtbl->GetNames)(a2, &pv, &v8);
  v4 = a2->lpVtbl->Invoke(a2, (void *)*((_QWORD *)this + 1));
  CoTaskMemFree(pv);
  CoTaskMemFree(v8);
  if ( v6 )
    DisableVirtualization();
  return v4;
}

```

## disassembly

```asm
0x180006fb0  mov     [rsp+arg_18], rbx
0x180006fb5  push    rdi
0x180006fb6  sub     rsp, 20h
0x180006fba  mov     rdi, rdx
0x180006fbd  mov     rbx, rcx
0x180006fc0  lea     rcx, [rsp+28h+arg_0]; this
0x180006fc5  call    ??0JITVirtualize@@QEAA@XZ; JITVirtualize::JITVirtualize(void)
0x180006fca  mov     rax, [rdi]
0x180006fcd  lea     r8, [rsp+28h+arg_10]
0x180006fd2  lea     rdx, [rsp+28h+pv]
0x180006fd7  mov     rcx, rdi
0x180006fda  mov     rax, [rax+28h]
0x180006fde  call    cs:__guard_dispatch_icall_fptr
0x180006fe4  mov     rax, [rdi]
0x180006fe7  mov     rdx, [rbx+8]
0x180006feb  mov     rcx, rdi
0x180006fee  mov     rax, [rax+0A8h]
0x180006ff5  call    cs:__guard_dispatch_icall_fptr
0x180006ffb  mov     ebx, eax
0x180006ffd  mov     rcx, [rsp+28h+pv]; pv
0x180007002  call    cs:__imp_CoTaskMemFree
0x180007008  mov     rcx, [rsp+28h+arg_10]; pv
0x18000700d  call    cs:__imp_CoTaskMemFree
0x180007013  nop
0x180007014  cmp     [rsp+28h+arg_0], 0
0x180007019  jz      short loc_180007029
0x18000701b  mov     rax, cs:?DisableVirtualization@@3P6AHXZEA; int (*DisableVirtualization)(void)
0x180007022  call    cs:__guard_dispatch_icall_fptr
0x180007028  nop
0x180007029  mov     eax, ebx
0x18000702b  mov     rbx, [rsp+28h+arg_18]
0x180007030  add     rsp, 20h
0x180007034  pop     rdi
0x180007035  retn
```
