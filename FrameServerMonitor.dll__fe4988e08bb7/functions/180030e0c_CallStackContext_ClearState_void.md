# CallStackContext::ClearState(void)

- ea: `0x180030e0c`
- end: `0x180030e51`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(GUID *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180030fb8`
- `0x1800317c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030e3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030e3f`

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
0x180030e0c  push    rbx
0x180030e0e  sub     rsp, 20h
0x180030e12  xor     eax, eax
0x180030e14  mov     rbx, rcx
0x180030e17  mov     [rcx+7C4h], eax
0x180030e1d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180030e24  mov     [rcx+7E0h], rax
0x180030e2b  mov     [rcx+7CCh], eax
0x180030e31  movdqu  xmmword ptr [rcx+7D0h], xmm0
0x180030e39  mov     [rcx+7E8h], eax
0x180030e3f  call    cs:__imp_GetCurrentThreadId
0x180030e45  mov     [rbx+7C0h], eax
0x180030e4b  add     rsp, 20h
0x180030e4f  pop     rbx
0x180030e50  retn
```
