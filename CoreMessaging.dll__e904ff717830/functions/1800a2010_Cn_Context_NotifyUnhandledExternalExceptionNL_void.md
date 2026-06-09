# Cn::Context::NotifyUnhandledExternalExceptionNL(void *)

- ea: `0x1800a2010`
- end: `0x1800a2101`
- name: `?NotifyUnhandledExternalExceptionNL@Context@Cn@@QEAAXPEAX@Z`
- size: `241`
- prototype: `void __fastcall(Cn::Context *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a236c`

## callees

- `0x18009e054`
- `0x1800a2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a2038`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800a2038`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a20bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a20bc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800a20e5`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800a20e5`

## pseudocode

```c
void __fastcall Cn::Context::NotifyUnhandledExternalExceptionNL(Cn::Context *this, _OWORD **a2)
{
  void *v4; // rax
  _OWORD *v5; // rax
  __int64 v6; // rcx

  if ( *((_DWORD *)this + 18) != 2 )
  {
    *((_DWORD *)this + 18) = 2;
    v4 = malloc(0x8A8u);
    *((_QWORD *)this + 12) = v4;
    if ( v4 )
    {
      memset_0(v4, 0, 0x8A8u);
      v5 = *a2;
      v6 = *((_QWORD *)this + 12);
      *(_OWORD *)v6 = **a2;
      *(_OWORD *)(v6 + 16) = v5[1];
      *(_OWORD *)(v6 + 32) = v5[2];
      *(_OWORD *)(v6 + 48) = v5[3];
      *(_OWORD *)(v6 + 64) = v5[4];
      *(_OWORD *)(v6 + 80) = v5[5];
      *(_OWORD *)(v6 + 96) = v5[6];
      *(_OWORD *)(v6 + 112) = v5[7];
      *(_OWORD *)(v6 + 128) = v5[8];
      *(_QWORD *)(v6 + 144) = *((_QWORD *)v5 + 18);
      *(_DWORD *)(*((_QWORD *)this + 12) + 152LL) = GetCurrentThreadId();
      *(_WORD *)(*((_QWORD *)this + 12) + 156LL) = RtlCaptureStackBackTrace(
                                                     0,
                                                     0x100u,
                                                     (PVOID *)(*((_QWORD *)this + 12) + 168LL),
                                                     (PULONG)(*((_QWORD *)this + 12) + 160LL));
    }
  }
}

```

## disassembly

```asm
0x1800a2010  mov     [rsp+arg_0], rbx
0x1800a2015  push    rdi
0x1800a2016  sub     rsp, 20h
0x1800a201a  mov     eax, [rcx+48h]
0x1800a201d  mov     rdi, rdx
0x1800a2020  mov     rbx, rcx
0x1800a2023  cmp     eax, 2
0x1800a2026  jz      loc_1800A20F6
0x1800a202c  mov     dword ptr [rcx+48h], 2
0x1800a2033  mov     ecx, 8A8h; Size
0x1800a2038  call    cs:__imp_malloc
0x1800a203e  mov     [rbx+60h], rax
0x1800a2042  test    rax, rax
0x1800a2045  jz      loc_1800A20F6
0x1800a204b  xor     edx, edx; Val
0x1800a204d  mov     r8d, 8A8h; Size
0x1800a2053  mov     rcx, rax; void *
0x1800a2056  call    memset_0
0x1800a205b  mov     rax, [rdi]
0x1800a205e  mov     rcx, [rbx+60h]
0x1800a2062  movups  xmm0, xmmword ptr [rax]
0x1800a2065  movups  xmmword ptr [rcx], xmm0
0x1800a2068  movups  xmm1, xmmword ptr [rax+10h]
0x1800a206c  movups  xmmword ptr [rcx+10h], xmm1
0x1800a2070  movups  xmm0, xmmword ptr [rax+20h]
0x1800a2074  movups  xmmword ptr [rcx+20h], xmm0
0x1800a2078  movups  xmm1, xmmword ptr [rax+30h]
0x1800a207c  movups  xmmword ptr [rcx+30h], xmm1
0x1800a2080  movups  xmm0, xmmword ptr [rax+40h]
0x1800a2084  movups  xmmword ptr [rcx+40h], xmm0
0x1800a2088  movups  xmm1, xmmword ptr [rax+50h]
0x1800a208c  movups  xmmword ptr [rcx+50h], xmm1
0x1800a2090  movups  xmm0, xmmword ptr [rax+60h]
0x1800a2094  movups  xmmword ptr [rcx+60h], xmm0
0x1800a2098  movups  xmm1, xmmword ptr [rax+70h]
0x1800a209c  movups  xmmword ptr [rcx+70h], xmm1
0x1800a20a0  movups  xmm0, xmmword ptr [rax+80h]
0x1800a20a7  movups  xmmword ptr [rcx+80h], xmm0
0x1800a20ae  mov     rax, [rax+90h]
0x1800a20b5  mov     [rcx+90h], rax
0x1800a20bc  call    cs:__imp_GetCurrentThreadId
0x1800a20c2  mov     rcx, [rbx+60h]
0x1800a20c6  mov     edx, 100h; FramesToCapture
0x1800a20cb  mov     [rcx+98h], eax
0x1800a20d1  xor     ecx, ecx; FramesToSkip
0x1800a20d3  mov     r8, [rbx+60h]
0x1800a20d7  lea     r9, [r8+0A0h]; BackTraceHash
0x1800a20de  add     r8, 0A8h; BackTrace
0x1800a20e5  call    cs:__imp_RtlCaptureStackBackTrace
0x1800a20eb  mov     rcx, [rbx+60h]
0x1800a20ef  mov     [rcx+9Ch], ax
0x1800a20f6  mov     rbx, [rsp+28h+arg_0]
0x1800a20fb  add     rsp, 20h
0x1800a20ff  pop     rdi
0x1800a2100  retn
```
