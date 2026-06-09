# wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)

- ea: `0x180012700`
- end: `0x180012755`
- name: `??1ActivityThreadWatcher@wil@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(wil::ActivityThreadWatcher *__hidden this)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180014de4`
- `0x1800154fc`
- `0x180016b54`
- `0x180017144`
- `0x1800179e8`
- `0x180017b98`
- `0x180018f08`
- `0x18001bc2c`
- `0x18001ef30`
- `0x18001f118`
- `0x18001f554`
- `0x18001f77c`
- `0x18001f9a4`
- `0x1800203b0`
- `0x180020e9c`
- `0x180028456`
- `0x1800284dd`
- `0x1800289dc`
- `0x180028b2e`
- `0x180028b64`
- `0x180028cca`
- `0x180029016`
- `0x180029237`
- `0x1800292a3`
- `0x180029333`

## callees

- `0x180012700`
- `0x180012a8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012733`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012725`

## pseudocode

```c
void __fastcall wil::ActivityThreadWatcher::~ActivityThreadWatcher(wil::ActivityThreadWatcher *this)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::ActivityThreadWatcher *)((char *)this + 32));
  if ( *((_BYTE *)this + 24) )
  {
    v2 = (void *)*((_QWORD *)this + 2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *((_BYTE *)this + 24) = 0;
  }
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180012700  mov     [rsp+arg_0], rbx
0x180012705  mov     [rsp+arg_8], rsi
0x18001270a  push    rdi
0x18001270b  sub     rsp, 20h
0x18001270f  mov     rsi, rcx
0x180012712  add     rcx, 20h ; ' '; this
0x180012716  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001271b  cmp     byte ptr [rsi+18h], 0
0x18001271f  jz      short loc_18001273D
0x180012721  mov     rbx, [rsi+10h]
0x180012725  call    cs:__imp_GetProcessHeap
0x18001272b  mov     r8, rbx; lpMem
0x18001272e  xor     edx, edx; dwFlags
0x180012730  mov     rcx, rax; hHeap
0x180012733  call    cs:__imp_HeapFree
0x180012739  mov     byte ptr [rsi+18h], 0
0x18001273d  mov     rbx, [rsp+28h+arg_0]
0x180012742  mov     qword ptr [rsi+10h], 0
0x18001274a  mov     rsi, [rsp+28h+arg_8]
0x18001274f  add     rsp, 20h
0x180012753  pop     rdi
0x180012754  retn
```
