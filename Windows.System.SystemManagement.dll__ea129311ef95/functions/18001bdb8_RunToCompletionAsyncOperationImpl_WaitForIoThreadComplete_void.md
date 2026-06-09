# RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete(void *)

- ea: `0x18001bdb8`
- end: `0x18001be22`
- name: `?WaitForIoThreadComplete@RunToCompletionAsyncOperationImpl@@AEAAXPEAX@Z`
- size: `106`
- prototype: `void(RunToCompletionAsyncOperationImpl *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019d90`

## callees

- `0x18001bdb8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001bdf2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001bdf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdda`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001be02`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001be02`
- `api-ms-win-core-io-l1-1-1!CancelSynchronousIo` at `0x18001bdd0`
- `api-ms-win-core-io-l1-1-1!CancelSynchronousIo` at `0x18001bdd0`

## pseudocode

```c
void __fastcall RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete(
        RunToCompletionAsyncOperationImpl *this,
        void *a2)
{
  if ( a2 && (!CancelSynchronousIo(a2) && GetLastError() != 1168 || WaitForSingleObjectEx(a2, 0x2710u, 0)) )
  {
    TerminateThread(a2, 0xFFFFFFFF);
    (*(void (__fastcall **)(RunToCompletionAsyncOperationImpl *))(*(_QWORD *)this + 16LL))(this);
  }
}

```

## disassembly

```asm
0x18001bdb8  test    rdx, rdx
0x18001bdbb  jz      short locret_18001BE21
0x18001bdbd  mov     [rsp+arg_0], rbx
0x18001bdc2  push    rdi
0x18001bdc3  sub     rsp, 20h
0x18001bdc7  mov     rdi, rcx
0x18001bdca  mov     rbx, rdx
0x18001bdcd  mov     rcx, rdx; hThread
0x18001bdd0  call    cs:__imp_CancelSynchronousIo
0x18001bdd6  test    eax, eax
0x18001bdd8  jnz     short loc_18001BDE7
0x18001bdda  call    cs:__imp_GetLastError
0x18001bde0  cmp     eax, 490h
0x18001bde5  jnz     short loc_18001BDFC
0x18001bde7  xor     r8d, r8d; bAlertable
0x18001bdea  mov     edx, 2710h; dwMilliseconds
0x18001bdef  mov     rcx, rbx; hHandle
0x18001bdf2  call    cs:__imp_WaitForSingleObjectEx
0x18001bdf8  test    eax, eax
0x18001bdfa  jz      short loc_18001BE17
0x18001bdfc  or      edx, 0FFFFFFFFh; dwExitCode
0x18001bdff  mov     rcx, rbx; hThread
0x18001be02  call    cs:__imp_TerminateThread
0x18001be08  mov     rax, [rdi]
0x18001be0b  mov     rcx, rdi
0x18001be0e  mov     rax, [rax+10h]
0x18001be12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be17  mov     rbx, [rsp+28h+arg_0]
0x18001be1c  add     rsp, 20h
0x18001be20  pop     rdi
0x18001be21  retn
```
