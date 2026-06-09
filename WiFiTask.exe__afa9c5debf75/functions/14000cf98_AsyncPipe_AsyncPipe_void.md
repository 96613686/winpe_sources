# AsyncPipe::AsyncPipe(void)

- ea: `0x14000cf98`
- end: `0x14000d17e`
- name: `??0AsyncPipe@@QEAA@XZ`
- size: `486`
- prototype: `AsyncPipe *__fastcall(AsyncPipe *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000728c`

## callees

- `0x1400016d0`
- `0x14000cf98`
- `0x14000e1b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000d115`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000d115`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d01b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d15b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d168`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d01b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d15b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14000d168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d127`

## string_xrefs

- `0x14000d130`: `CreateThreadpoolCleanupGroup`

## pseudocode

```c
AsyncPipe *__fastcall AsyncPipe::AsyncPipe(AsyncPipe *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD LastError; // eax
  const char *v6; // rcx
  char *v8; // [rsp+58h] [rbp+10h]

  *(_QWORD *)this = &SynchronizedObject::`vftable';
  *((_QWORD *)this + 1) = 0;
  v8 = (char *)operator new(0x68u);
  *(_DWORD *)v8 = 1;
  *(_OWORD *)(v8 + 8) = 0;
  *(_OWORD *)(v8 + 24) = 0;
  *((_QWORD *)v8 + 5) = 0;
  *((_WORD *)v8 + 24) = 0;
  *((_QWORD *)v8 + 7) = 0;
  *((_QWORD *)v8 + 8) = 0;
  *((_QWORD *)v8 + 9) = 0;
  *((_QWORD *)v8 + 10) = 0;
  *((_QWORD *)v8 + 11) = 0;
  v2 = operator new(0x10u);
  v2[1] = 0;
  *((_QWORD *)v8 + 7) = v2;
  *v2 = v8 + 56;
  *((_DWORD *)v8 + 24) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  *((_QWORD *)this + 1) = v8;
  *(_QWORD *)this = &AsyncPipe::`vftable';
  *((_DWORD *)this + 4) = 1;
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  v3 = operator new(0x10u);
  v3[1] = 0;
  *((_QWORD *)this + 6) = v3;
  *v3 = (char *)this + 48;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 62) = -1;
  *((_DWORD *)this + 63) = -1;
  *((_DWORD *)this + 64) = 0;
  *((_QWORD *)this + 183) = 0;
  *((_QWORD *)this + 184) = 3;
  *((_QWORD *)this + 192) = 72;
  *((_QWORD *)this + 193) = 0;
  *((_BYTE *)this + 1552) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *((_QWORD *)this + 185) = 0;
  *((_QWORD *)this + 186) = 0;
  *((_QWORD *)this + 187) = 0;
  *((_QWORD *)this + 188) = 0;
  *((_QWORD *)this + 189) = 0;
  *((_QWORD *)this + 190) = 0;
  *((_DWORD *)this + 382) = 0;
  *((_DWORD *)this + 383) = 1;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 193) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    LastError = GetLastError();
    __FatalError(v6, 0x47u, "CreateThreadpoolCleanupGroup", LastError);
  }
  *((_QWORD *)this + 186) = *((_QWORD *)this + 193);
  *((_QWORD *)this + 187) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  return this;
}

```

## disassembly

```asm
0x14000cf98  mov     [rsp+arg_0], rcx
0x14000cf9d  push    rbx
0x14000cf9e  push    rsi
0x14000cf9f  push    rdi
0x14000cfa0  push    r12
0x14000cfa2  push    r14
0x14000cfa4  sub     rsp, 20h
0x14000cfa8  mov     r14, rcx
0x14000cfab  lea     rax, ??_7SynchronizedObject@@6B@; const SynchronizedObject::`vftable'
0x14000cfb2  mov     [rcx], rax
0x14000cfb5  xor     r12d, r12d
0x14000cfb8  mov     [rcx+8], r12
0x14000cfbc  lea     ecx, [r12+68h]; Size
0x14000cfc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000cfc6  mov     rsi, rax
0x14000cfc9  mov     [rsp+48h+arg_8], rax
0x14000cfce  mov     dword ptr [rax], 1
0x14000cfd4  xorps   xmm0, xmm0
0x14000cfd7  xor     eax, eax
0x14000cfd9  movups  xmmword ptr [rsi+8], xmm0
0x14000cfdd  movups  xmmword ptr [rsi+18h], xmm0
0x14000cfe1  mov     [rsi+28h], rax
0x14000cfe5  mov     [rsi+30h], r12w
0x14000cfea  lea     rbx, [rsi+38h]
0x14000cfee  mov     [rbx], r12
0x14000cff1  mov     [rbx+8], r12
0x14000cff5  mov     [rbx+10h], r12
0x14000cff9  mov     [rbx+18h], r12
0x14000cffd  mov     [rbx+20h], r12
0x14000d001  lea     ecx, [rax+10h]; Size
0x14000d004  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d009  mov     [rax+8], r12
0x14000d00d  mov     [rbx], rax
0x14000d010  mov     [rax], rbx
0x14000d013  mov     [rsi+60h], r12d
0x14000d017  lea     rcx, [rsi+8]; lpCriticalSection
0x14000d01b  call    cs:__imp_InitializeCriticalSection
0x14000d021  nop
0x14000d022  mov     [r14+8], rsi
0x14000d026  lea     rax, ??_7AsyncPipe@@6B@; const AsyncPipe::`vftable'
0x14000d02d  mov     [r14], rax
0x14000d030  mov     dword ptr [r14+10h], 1
0x14000d038  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000d03c  mov     [r14+18h], rdi
0x14000d040  mov     [r14+20h], r12
0x14000d044  mov     [r14+28h], r12
0x14000d048  lea     rbx, [r14+30h]
0x14000d04c  mov     [rbx], r12
0x14000d04f  mov     [rbx+8], r12
0x14000d053  mov     [rbx+10h], r12
0x14000d057  mov     [rbx+18h], r12
0x14000d05b  mov     [rbx+20h], r12
0x14000d05f  lea     ecx, [rdi+11h]; Size
0x14000d062  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d067  mov     [rax+8], r12
0x14000d06b  mov     [rbx], rax
0x14000d06e  mov     [rax], rbx
0x14000d071  mov     [r14+58h], r12
0x14000d075  mov     [r14+60h], r12
0x14000d079  mov     [r14+0F8h], edi
0x14000d080  mov     [r14+0FCh], edi
0x14000d087  mov     [r14+100h], r12d
0x14000d08e  mov     [r14+5B8h], r12
0x14000d095  mov     qword ptr [r14+5C0h], 3
0x14000d0a0  mov     qword ptr [r14+600h], 48h ; 'H'
0x14000d0ab  mov     [r14+608h], r12
0x14000d0b2  mov     [r14+610h], r12b
0x14000d0b9  xorps   xmm0, xmm0
0x14000d0bc  movups  xmmword ptr [r14+68h], xmm0
0x14000d0c1  movups  xmmword ptr [r14+78h], xmm0
0x14000d0c6  xorps   xmm1, xmm1
0x14000d0c9  movups  xmmword ptr [r14+88h], xmm1
0x14000d0d1  movups  xmmword ptr [r14+98h], xmm1
0x14000d0d9  mov     [r14+5C8h], r12
0x14000d0e0  mov     [r14+5D0h], r12
0x14000d0e7  mov     [r14+5D8h], r12
0x14000d0ee  mov     [r14+5E0h], r12
0x14000d0f5  mov     [r14+5E8h], r12
0x14000d0fc  mov     [r14+5F0h], r12
0x14000d103  mov     [r14+5F8h], r12d
0x14000d10a  mov     dword ptr [r14+5FCh], 1
0x14000d115  call    cs:__imp_CreateThreadpoolCleanupGroup
0x14000d11b  mov     [r14+608h], rax
0x14000d122  test    rax, rax
0x14000d125  jnz     short loc_14000D13F
0x14000d127  call    cs:__imp_GetLastError
0x14000d12d  mov     r9d, eax; unsigned int
0x14000d130  lea     r8, aCreatethreadpo_0; "CreateThreadpoolCleanupGroup"
0x14000d137  lea     edx, [rdi+48h]; unsigned int
0x14000d13a  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d13f  mov     rax, [r14+608h]
0x14000d146  mov     [r14+5D0h], rax
0x14000d14d  mov     [r14+5D8h], r12
0x14000d154  lea     rcx, [r14+0A8h]; lpCriticalSection
0x14000d15b  call    cs:__imp_InitializeCriticalSection
0x14000d161  lea     rcx, [r14+0D0h]; lpCriticalSection
0x14000d168  call    cs:__imp_InitializeCriticalSection
0x14000d16e  nop
0x14000d16f  mov     rax, r14
0x14000d172  add     rsp, 20h
0x14000d176  pop     r14
0x14000d178  pop     r12
0x14000d17a  pop     rdi
0x14000d17b  pop     rsi
0x14000d17c  pop     rbx
0x14000d17d  retn
```
