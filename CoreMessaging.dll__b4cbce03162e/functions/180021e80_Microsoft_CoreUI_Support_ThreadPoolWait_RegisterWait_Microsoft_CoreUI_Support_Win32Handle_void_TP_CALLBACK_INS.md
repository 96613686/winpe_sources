# Microsoft::CoreUI::Support::ThreadPoolWait::RegisterWait(Microsoft::CoreUI::Support::Win32Handle,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long),void *)

- ea: `0x180021e80`
- end: `0x180021ed3`
- name: `?RegisterWait@ThreadPoolWait@Support@CoreUI@Microsoft@@QEAA_NUWin32Handle@234@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z2@Z`
- size: `83`
- prototype: `bool __high(struct Microsoft::CoreUI::Support::Win32Handle, void (__high *)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int), void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021d8c`
- `0x180021e38`
- `0x1800b9660`

## callees

- `0x180021e80`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021ebb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021ebb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180021ea4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180021ea4`

## pseudocode

```c
bool __fastcall Microsoft::CoreUI::Support::ThreadPoolWait::RegisterWait(
        struct _TP_WAIT **a1,
        void *a2,
        void (__stdcall *a3)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult),
        void *a4)
{
  struct _TP_WAIT *ThreadpoolWait; // rax

  ThreadpoolWait = *a1;
  if ( *a1 || (ThreadpoolWait = CreateThreadpoolWait(a3, a4, 0), (*a1 = ThreadpoolWait) != 0) )
    SetThreadpoolWait(ThreadpoolWait, a2, 0);
  return *a1 != 0;
}

```

## disassembly

```asm
0x180021e80  mov     [rsp+arg_0], rbx
0x180021e85  push    rdi
0x180021e86  sub     rsp, 20h
0x180021e8a  mov     rax, [rcx]
0x180021e8d  mov     r10, r8
0x180021e90  mov     rbx, rdx
0x180021e93  mov     rdi, rcx
0x180021e96  test    rax, rax
0x180021e99  jnz     short loc_180021EB2
0x180021e9b  xor     r8d, r8d; pcbe
0x180021e9e  mov     rdx, r9; pv
0x180021ea1  mov     rcx, r10; pfnwa
0x180021ea4  call    cs:__imp_CreateThreadpoolWait
0x180021eaa  mov     [rdi], rax
0x180021ead  test    rax, rax
0x180021eb0  jz      short loc_180021EC1
0x180021eb2  xor     r8d, r8d; pftTimeout
0x180021eb5  mov     rdx, rbx; h
0x180021eb8  mov     rcx, rax; pwa
0x180021ebb  call    cs:__imp_SetThreadpoolWait
0x180021ec1  cmp     qword ptr [rdi], 0
0x180021ec5  mov     rbx, [rsp+28h+arg_0]
0x180021eca  setnz   al
0x180021ecd  add     rsp, 20h
0x180021ed1  pop     rdi
0x180021ed2  retn
```
