# CallStackContext::CallStackContext(ulong,ulong)

- ea: `0x1800021f0`
- end: `0x1800022a2`
- name: `??0CallStackContext@@QEAA@KK@Z`
- size: `178`
- prototype: `CallStackContext *__fastcall(CallStackContext *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a3064`
- `0x1800a3770`

## callees

- `0x1800021f0`
- `0x1800a3128`
- `0x1800b0b00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002273`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002273`

## pseudocode

```c
CallStackContext *__fastcall CallStackContext::CallStackContext(CallStackContext *this, int a2, unsigned int a3)
{
  int v3; // esi
  __int64 v5; // r15
  CallStackInfo *v8; // r14
  CallStackContext *result; // rax

  v3 = 124;
  v5 = 124;
  v8 = this;
  do
  {
    CallStackInfo::CallStackInfo(v8);
    v8 = (CallStackInfo *)((char *)v8 + 16);
    --v5;
  }
  while ( v5 );
  if ( a3 < 0x7C )
    v3 = a3;
  *((_DWORD *)this + 498) = v3;
  memset(this, 0, 0x7C0u);
  *((_DWORD *)this + 497) = 0;
  *((_QWORD *)this + 252) = 0;
  *((_DWORD *)this + 499) = 0;
  *((GUID *)this + 125) = GUID_00000000_0000_0000_0000_000000000000;
  *((_DWORD *)this + 506) = 0;
  GetCurrentThreadId();
  result = this;
  *((_DWORD *)this + 496) = a2;
  return result;
}

```

## disassembly

```asm
0x1800021f0  mov     [rsp+arg_0], rbx
0x1800021f5  mov     [rsp+arg_10], rbp
0x1800021fa  mov     [rsp+arg_18], rsi
0x1800021ff  push    rdi
0x180002200  push    r14
0x180002202  push    r15
0x180002204  sub     rsp, 20h
0x180002208  mov     esi, 7Ch ; '|'
0x18000220d  mov     edi, r8d
0x180002210  mov     r15d, esi
0x180002213  mov     ebp, edx
0x180002215  mov     rbx, rcx
0x180002218  mov     r14, rcx
0x18000221b  mov     rcx, r14; this
0x18000221e  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x180002223  add     r14, 10h
0x180002227  sub     r15, 1
0x18000222b  jnz     short loc_18000221B
0x18000222d  cmp     edi, esi
0x18000222f  jnb     short loc_180002234
0x180002231  mov     rsi, rdi
0x180002234  xor     edx, edx; Val
0x180002236  mov     [rbx+7C8h], esi
0x18000223c  mov     r8d, 7C0h; Size
0x180002242  mov     rcx, rbx; void *
0x180002245  call    memset
0x18000224a  xor     eax, eax
0x18000224c  mov     [rbx+7C4h], eax
0x180002252  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180002259  mov     [rbx+7E0h], rax
0x180002260  mov     [rbx+7CCh], eax
0x180002266  movups  xmmword ptr [rbx+7D0h], xmm0
0x18000226d  mov     [rbx+7E8h], eax
0x180002273  call    cs:__imp_GetCurrentThreadId
0x18000227a  nop     dword ptr [rax+rax+00h]
0x18000227f  mov     rsi, [rsp+38h+arg_18]
0x180002284  mov     rax, rbx
0x180002287  mov     [rbx+7C0h], ebp
0x18000228d  mov     rbx, [rsp+38h+arg_0]
0x180002292  mov     rbp, [rsp+38h+arg_10]
0x180002297  add     rsp, 20h
0x18000229b  pop     r15
0x18000229d  pop     r14
0x18000229f  pop     rdi
0x1800022a0  retn
```
