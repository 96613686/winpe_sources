# CThread::WaitForThread(void)

- ea: `0x1400323bc`
- end: `0x140032415`
- name: `?WaitForThread@CThread@@QEAAXXZ`
- size: `89`
- prototype: `void __fastcall(CThread *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f7b0`
- `0x14000f85c`
- `0x14000f9e8`
- `0x14003a8e8`

## callees

- `0x1400323bc`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400323e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400323e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400323ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400323ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400323d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400323d3`

## pseudocode

```c
void __fastcall CThread::WaitForThread(CThread *this)
{
  int v2; // ebx

  if ( *((_QWORD *)this + 2) )
  {
    v2 = *((_DWORD *)this + 12);
    if ( GetCurrentThreadId() != v2 )
      WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  (*(void (__fastcall **)(CThread *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x1400323bc  mov     [rsp+arg_0], rbx
0x1400323c1  push    rdi
0x1400323c2  sub     rsp, 20h
0x1400323c6  cmp     qword ptr [rcx+10h], 0
0x1400323cb  mov     rdi, rcx
0x1400323ce  jz      short loc_1400323FC
0x1400323d0  mov     ebx, [rcx+30h]
0x1400323d3  call    cs:__imp_GetCurrentThreadId
0x1400323d9  cmp     eax, ebx
0x1400323db  jz      short loc_1400323EA
0x1400323dd  mov     rcx, [rdi+10h]; hHandle
0x1400323e1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400323e4  call    cs:__imp_WaitForSingleObject
0x1400323ea  mov     rcx, [rdi+10h]; hObject
0x1400323ee  call    cs:__imp_CloseHandle
0x1400323f4  mov     qword ptr [rdi+10h], 0
0x1400323fc  mov     rax, [rdi]
0x1400323ff  mov     rcx, rdi
0x140032402  mov     rax, [rax+10h]
0x140032406  mov     rbx, [rsp+28h+arg_0]
0x14003240b  add     rsp, 20h
0x14003240f  pop     rdi
0x140032410  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
