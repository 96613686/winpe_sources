# CallStackContext::CallStackContext(ulong,ulong)

- ea: `0x180009370`
- end: `0x180009409`
- name: `??0CallStackContext@@QEAA@KK@Z`
- size: `153`
- prototype: `CallStackContext *__fastcall(CallStackContext *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18004ef84`
- `0x180058b10`

## callees

- `0x180009370`
- `0x180017e20`
- `0x18004f044`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093ec`

## pseudocode

```c
CallStackContext *__fastcall CallStackContext::CallStackContext(CallStackContext *this, int a2, unsigned int a3)
{
  int v3; // r14d
  __int64 v5; // rbx
  CallStackInfo *v8; // rdi
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
  memset_0(this, 0, 0x7C0u);
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
0x180009370  push    rbx
0x180009372  push    rbp
0x180009373  push    rsi
0x180009374  push    rdi
0x180009375  push    r14
0x180009377  push    r15
0x180009379  sub     rsp, 28h
0x18000937d  mov     r14d, 7Ch ; '|'
0x180009383  mov     ebp, r8d
0x180009386  mov     ebx, r14d
0x180009389  mov     r15d, edx
0x18000938c  mov     rsi, rcx
0x18000938f  mov     rdi, rcx
0x180009392  mov     rcx, rdi; this
0x180009395  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x18000939a  add     rdi, 10h
0x18000939e  sub     rbx, 1
0x1800093a2  jnz     short loc_180009392
0x1800093a4  cmp     ebp, r14d
0x1800093a7  jnb     short loc_1800093AC
0x1800093a9  mov     r14, rbp
0x1800093ac  xor     edx, edx; Val
0x1800093ae  mov     [rsi+7C8h], r14d
0x1800093b5  mov     r8d, 7C0h; Size
0x1800093bb  mov     rcx, rsi; void *
0x1800093be  call    memset_0
0x1800093c3  xor     eax, eax
0x1800093c5  mov     [rsi+7C4h], eax
0x1800093cb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800093d2  mov     [rsi+7E0h], rax
0x1800093d9  mov     [rsi+7CCh], eax
0x1800093df  movups  xmmword ptr [rsi+7D0h], xmm0
0x1800093e6  mov     [rsi+7E8h], eax
0x1800093ec  call    cs:__imp_GetCurrentThreadId
0x1800093f2  mov     rax, rsi
0x1800093f5  mov     [rsi+7C0h], r15d
0x1800093fc  add     rsp, 28h
0x180009400  pop     r15
0x180009402  pop     r14
0x180009404  pop     rdi
0x180009405  pop     rsi
0x180009406  pop     rbp
0x180009407  pop     rbx
0x180009408  retn
```
