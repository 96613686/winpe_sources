# UbpmUtilsWorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180026810`
- end: `0x18002687b`
- name: `?UbpmUtilsWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `107`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180026810`
- `0x180041010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180026856`
- `ntdll!RtlFreeHeap` at `0x180026856`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180026826`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180026826`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002686f`

## pseudocode

```c
void __fastcall UbpmUtilsWorkCallback(PTP_CALLBACK_INSTANCE Instance, _BYTE *Context, PTP_WORK Work)
{
  void (__fastcall **v4)(_QWORD, _BYTE *, _QWORD); // rbx

  v4 = (void (__fastcall **)(_QWORD, _BYTE *, _QWORD))Context;
  if ( (Context[24] & 1) != 0 )
    CallbackMayRunLong(Instance);
  LOBYTE(Context) = 2;
  v4[2](v4[1], Context, 0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  CloseThreadpoolWork(Work);
}

```

## disassembly

```asm
0x180026810  mov     [rsp+arg_0], rbx
0x180026815  push    rdi
0x180026816  sub     rsp, 20h
0x18002681a  test    byte ptr [rdx+18h], 1
0x18002681e  mov     rdi, r8
0x180026821  mov     rbx, rdx
0x180026824  jz      short loc_180026832
0x180026826  call    cs:__imp_CallbackMayRunLong
0x18002682d  nop     dword ptr [rax+rax+00h]
0x180026832  mov     rcx, [rbx+8]
0x180026836  xor     r8d, r8d
0x180026839  mov     rax, [rbx+10h]
0x18002683d  mov     dl, 2
0x18002683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026844  mov     rcx, gs:60h
0x18002684d  mov     r8, rbx; P
0x180026850  xor     edx, edx; Flags
0x180026852  mov     rcx, [rcx+30h]; HeapHandle
0x180026856  call    cs:__imp_RtlFreeHeap
0x18002685d  nop     dword ptr [rax+rax+00h]
0x180026862  mov     rcx, rdi
0x180026865  mov     rbx, [rsp+28h+arg_0]
0x18002686a  add     rsp, 20h
0x18002686e  pop     rdi
0x18002686f  jmp     cs:__imp_CloseThreadpoolWork
```
