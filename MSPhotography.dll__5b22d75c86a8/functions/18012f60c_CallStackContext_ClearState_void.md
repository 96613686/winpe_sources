# CallStackContext::ClearState(void)

- ea: `0x18012f60c`
- end: `0x18012f651`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(CallStackContext *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002afd0`
- `0x18012f7b8`
- `0x18013014c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f63f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f63f`

## pseudocode

```c
void __fastcall CallStackContext::ClearState(GUID *this)
{
  *(_DWORD *)&this[124].Data2 = 0;
  *(_QWORD *)&this[126].Data1 = 0;
  *(_DWORD *)&this[124].Data4[4] = 0;
  this[125] = GUID_00000000_0000_0000_0000_000000000000;
  *(_DWORD *)this[126].Data4 = 0;
  this[124].Data1 = GetCurrentThreadId();
}

```

## disassembly

```asm
0x18012f60c  push    rbx
0x18012f60e  sub     rsp, 20h
0x18012f612  xor     eax, eax
0x18012f614  mov     rbx, rcx
0x18012f617  mov     [rcx+7C4h], eax
0x18012f61d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18012f624  mov     [rcx+7E0h], rax
0x18012f62b  mov     [rcx+7CCh], eax
0x18012f631  movdqu  xmmword ptr [rcx+7D0h], xmm0
0x18012f639  mov     [rcx+7E8h], eax
0x18012f63f  call    cs:__imp_GetCurrentThreadId
0x18012f645  mov     [rbx+7C0h], eax
0x18012f64b  add     rsp, 20h
0x18012f64f  pop     rbx
0x18012f650  retn
```
