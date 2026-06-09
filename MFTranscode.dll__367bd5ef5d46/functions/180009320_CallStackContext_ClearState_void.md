# CallStackContext::ClearState(void)

- ea: `0x180009320`
- end: `0x180009364`
- name: `?ClearState@CallStackContext@@QEAAXXZ`
- size: `68`
- prototype: `void __fastcall(CallStackContext *__hidden this)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019a0`
- `0x1800026f0`
- `0x180002a10`
- `0x180002f50`
- `0x180003690`
- `0x180003950`
- `0x180004a40`
- `0x180005a40`
- `0x180007d00`
- `0x180008f00`
- `0x180059018`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009352`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009352`

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
0x180009320  push    rbx
0x180009322  sub     rsp, 20h
0x180009326  xor     eax, eax
0x180009328  mov     rbx, rcx
0x18000932b  mov     [rcx+7C4h], eax
0x180009331  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180009338  mov     [rcx+7E0h], rax
0x18000933f  mov     [rcx+7CCh], eax
0x180009345  movups  xmmword ptr [rcx+7D0h], xmm0
0x18000934c  mov     [rcx+7E8h], eax
0x180009352  call    cs:__imp_GetCurrentThreadId
0x180009358  mov     [rbx+7C0h], eax
0x18000935e  add     rsp, 20h
0x180009362  pop     rbx
0x180009363  retn
```
