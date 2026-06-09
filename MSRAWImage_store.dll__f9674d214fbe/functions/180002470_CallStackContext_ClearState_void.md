# CallStackContext::ClearState(void)

- ea: `0x180002470`
- end: `0x1800024bb`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `75`
- prototype: `void __fastcall(CallStackContext *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a40`
- `0x180002590`
- `0x1800a3e98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024a2`

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
0x180002470  push    rbx
0x180002472  sub     rsp, 20h
0x180002476  xor     eax, eax
0x180002478  mov     rbx, rcx
0x18000247b  mov     [rcx+7C4h], eax
0x180002481  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180002488  mov     [rcx+7E0h], rax
0x18000248f  mov     [rcx+7CCh], eax
0x180002495  movups  xmmword ptr [rcx+7D0h], xmm0
0x18000249c  mov     [rcx+7E8h], eax
0x1800024a2  call    cs:__imp_GetCurrentThreadId
0x1800024a9  nop     dword ptr [rax+rax+00h]
0x1800024ae  mov     [rbx+7C0h], eax
0x1800024b4  add     rsp, 20h
0x1800024b8  pop     rbx
0x1800024b9  retn
```
