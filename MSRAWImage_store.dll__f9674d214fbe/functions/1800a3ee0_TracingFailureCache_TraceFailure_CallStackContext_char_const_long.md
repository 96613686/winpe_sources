# TracingFailureCache::TraceFailure(CallStackContext *,char const *,long)

- ea: `0x1800a3ee0`
- end: `0x1800a3fcf`
- name: `?TraceFailure@TracingFailureCache@@QEAAXPEAVCallStackContext@@PEBDJ@Z`
- size: `239`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a35a0`

## callees

- `0x1800a37c4`
- `0x1800a39bc`
- `0x1800a3b78`
- `0x1800a3ee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a3fc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a3f1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a3f1f`
- `MFPlat!MFGetSystemTime` at `0x1800a3f4a`
- `MFPlat!MFGetSystemTime` at `0x1800a3f4a`

## pseudocode

```c
void __fastcall TracingFailureCache::TraceFailure(
        TracingFailureCache *this,
        struct CallStackContext *a2,
        const char *a3,
        int a4)
{
  struct TracingFailureHash *v8; // rdx
  struct TracingFailureDetails *Match; // rbx
  MFTIME v10; // rax
  int v11; // eax
  __int128 v12; // [rsp+30h] [rbp-18h] BYREF

  v12 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 11);
  TracingFailureDetails::GenerateHashCodeForContext(a2, (struct TracingFailureHash *)&v12);
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  Match = TracingFailureCache::FindMatch(this, (struct TracingFailureHash *)&v12, (__m128i *)a2, a3, a4);
  if ( Match )
  {
    v10 = MFGetSystemTime();
    ++*((_DWORD *)Match + 576);
    *((_QWORD *)Match + 287) = v10;
    *((_DWORD *)Match + 506) = *((_DWORD *)a2 + 506);
    *((_DWORD *)Match + 496) = *((_DWORD *)a2 + 496);
    v11 = *((_DWORD *)a2 + 505);
    if ( v11 )
      *((_DWORD *)Match + 505) = v11;
    *((_BYTE *)Match + 2308) = 0;
  }
  else
  {
    TracingFailureCache::Add(this, v8, a2, a3, a4);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800a3ee0  mov     rax, rsp
0x1800a3ee3  mov     [rax+8], rbx
0x1800a3ee7  mov     [rax+10h], rbp
0x1800a3eeb  mov     [rax+18h], rsi
0x1800a3eef  mov     [rax+20h], rdi
0x1800a3ef3  push    r14
0x1800a3ef5  sub     rsp, 40h
0x1800a3ef9  xorps   xmm0, xmm0
0x1800a3efc  mov     ebp, r9d
0x1800a3eff  movups  xmmword ptr [rax-18h], xmm0
0x1800a3f03  mov     r14, r8
0x1800a3f06  mov     rdi, rdx
0x1800a3f09  mov     rsi, rcx
0x1800a3f0c  lock inc dword ptr [rcx+2Ch]
0x1800a3f10  lea     rdx, [rax-18h]; struct TracingFailureHash *
0x1800a3f14  mov     rcx, rdi; struct CallStackContext *
0x1800a3f17  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x1800a3f1c  mov     rcx, rsi; lpCriticalSection
0x1800a3f1f  call    cs:__imp_EnterCriticalSection
0x1800a3f26  nop     dword ptr [rax+rax+00h]
0x1800a3f2b  mov     r9, r14; char *
0x1800a3f2e  mov     [rsp+48h+var_28], ebp; int
0x1800a3f32  mov     r8, rdi; struct CallStackContext *
0x1800a3f35  lea     rdx, [rsp+48h+var_18]; struct TracingFailureHash *
0x1800a3f3a  mov     rcx, rsi; this
0x1800a3f3d  call    ?FindMatch@TracingFailureCache@@IEAAPEAVTracingFailureDetails@@AEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z; TracingFailureCache::FindMatch(TracingFailureHash &,CallStackContext &,char const *,long)
0x1800a3f42  mov     rbx, rax
0x1800a3f45  test    rax, rax
0x1800a3f48  jz      short loc_1800A3F94
0x1800a3f4a  call    cs:__imp_MFGetSystemTime
0x1800a3f51  nop     dword ptr [rax+rax+00h]
0x1800a3f56  inc     dword ptr [rbx+900h]
0x1800a3f5c  mov     [rbx+8F8h], rax
0x1800a3f63  mov     ecx, [rdi+7E8h]
0x1800a3f69  mov     [rbx+7E8h], ecx
0x1800a3f6f  mov     ecx, [rdi+7C0h]
0x1800a3f75  mov     [rbx+7C0h], ecx
0x1800a3f7b  mov     eax, [rdi+7E4h]
0x1800a3f81  test    eax, eax
0x1800a3f83  jz      short loc_1800A3F8B
0x1800a3f85  mov     [rbx+7E4h], eax
0x1800a3f8b  mov     byte ptr [rbx+904h], 0
0x1800a3f92  jmp     short loc_1800A3FA6
0x1800a3f94  mov     r9, r14; char *
0x1800a3f97  mov     [rsp+48h+var_28], ebp; int
0x1800a3f9b  mov     r8, rdi; struct CallStackContext *
0x1800a3f9e  mov     rcx, rsi; this
0x1800a3fa1  call    ?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z; TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)
0x1800a3fa6  mov     rcx, rsi
0x1800a3fa9  mov     rbx, [rsp+48h+arg_0]
0x1800a3fae  mov     rbp, [rsp+48h+arg_8]
0x1800a3fb3  mov     rsi, [rsp+48h+arg_10]
0x1800a3fb8  mov     rdi, [rsp+48h+arg_18]
0x1800a3fbd  add     rsp, 40h
0x1800a3fc1  pop     r14
0x1800a3fc3  jmp     cs:__imp_LeaveCriticalSection
```
