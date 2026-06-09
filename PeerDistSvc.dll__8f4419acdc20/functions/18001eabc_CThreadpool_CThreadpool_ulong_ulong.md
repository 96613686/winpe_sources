# CThreadpool::CThreadpool(ulong,ulong)

- ea: `0x18001eabc`
- end: `0x18001eb40`
- name: `??0CThreadpool@@IEAA@KK@Z`
- size: `132`
- prototype: `CThreadpool *__fastcall(CThreadpool *__hidden this, DWORD cthrdMost, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180032238`

## callees

- `0x180018d3c`
- `0x18001eabc`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18001eb18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18001eb18`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18001eaf3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18001eaf3`

## string_xrefs

- `0x18001eb02`: `CThreadpool::CThreadpool - CreateThreadpool`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CThreadpool *__fastcall CThreadpool::CThreadpool(CThreadpool *this, DWORD cthrdMost, unsigned int a3)
{
  struct _TP_POOL *Threadpool; // rax

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CThreadpool::`vftable';
  *((_QWORD *)this + 2) = 0;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 2) = Threadpool;
  if ( !Threadpool )
    SystemError::Throw(L"CThreadpool::CThreadpool - CreateThreadpool");
  if ( cthrdMost )
    SetThreadpoolThreadMaximum(Threadpool, cthrdMost);
  if ( a3 )
    CThreadpool::SetThreadpoolThreadMaximum(this, a3);
  return this;
}

```

## disassembly

```asm
0x18001eabc  mov     [rsp+arg_8], rbx
0x18001eac1  mov     [rsp+arg_10], rsi
0x18001eac6  mov     [rsp+arg_0], rcx
0x18001eacb  push    rdi
0x18001eacc  sub     rsp, 20h
0x18001ead0  mov     edi, r8d
0x18001ead3  mov     esi, edx
0x18001ead5  mov     rbx, rcx
0x18001ead8  mov     dword ptr [rcx+8], 0
0x18001eadf  lea     rax, ??_7CThreadpool@@6B@; const CThreadpool::`vftable'
0x18001eae6  mov     [rcx], rax
0x18001eae9  mov     qword ptr [rcx+10h], 0
0x18001eaf1  xor     ecx, ecx; reserved
0x18001eaf3  call    cs:__imp_CreateThreadpool
0x18001eaf9  mov     [rbx+10h], rax
0x18001eafd  test    rax, rax
0x18001eb00  jnz     short loc_18001EB0F
0x18001eb02  lea     rcx, aCthreadpoolCth; "CThreadpool::CThreadpool - CreateThread"...
0x18001eb09  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x18001eb0f  test    esi, esi
0x18001eb11  jz      short loc_18001EB1E
0x18001eb13  mov     edx, esi; cthrdMost
0x18001eb15  mov     rcx, rax; ptpp
0x18001eb18  call    cs:__imp_SetThreadpoolThreadMaximum
0x18001eb1e  test    edi, edi
0x18001eb20  jz      short loc_18001EB2D
0x18001eb22  mov     edx, edi; unsigned int
0x18001eb24  mov     rcx, rbx; this
0x18001eb27  call    ?SetThreadpoolThreadMaximum@CThreadpool@@QEAAXK@Z; CThreadpool::SetThreadpoolThreadMaximum(ulong)
0x18001eb2c  nop
0x18001eb2d  mov     rax, rbx
0x18001eb30  mov     rbx, [rsp+28h+arg_8]
0x18001eb35  mov     rsi, [rsp+28h+arg_10]
0x18001eb3a  add     rsp, 20h
0x18001eb3e  pop     rdi
0x18001eb3f  retn
```
