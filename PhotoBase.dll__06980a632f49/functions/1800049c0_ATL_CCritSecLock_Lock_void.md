# ATL::CCritSecLock::Lock(void)

- ea: `0x1800049c0`
- end: `0x1800049e8`
- name: `?Lock@CCritSecLock@ATL@@QEAAXXZ`
- size: `40`
- prototype: `void __fastcall(ATL::CCritSecLock *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180003420`
- `0x180003550`
- `0x1800036c4`
- `0x18000387c`
- `0x180003aec`
- `0x180003c38`
- `0x180003cd0`
- `0x1800048b0`
- `0x180004f94`
- `0x1800066dc`
- `0x180006880`
- `0x1800069e4`
- `0x180006b20`

## callees

- `0x180002420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800049cc`
- `KERNEL32!EnterCriticalSection` at `0x1800049cc`

## pseudocode

```c
void __fastcall ATL::CCritSecLock::Lock(LPCRITICAL_SECTION *this)
{
  EnterCriticalSection(*this);
  *((_BYTE *)this + 8) = 1;
}

```

## disassembly

```asm
0x1800049c0  push    rbx
0x1800049c2  sub     rsp, 20h
0x1800049c6  mov     rbx, rcx
0x1800049c9  mov     rcx, [rcx]; lpCriticalSection
0x1800049cc  call    cs:__imp_EnterCriticalSection
0x1800049d2  nop
0x1800049d3  mov     byte ptr [rbx+8], 1
0x1800049d7  add     rsp, 20h
0x1800049db  pop     rbx
0x1800049dc  retn
0x1800049dd  mov     ecx, 8007000Eh; int
0x1800049e2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180007649  push    rbp
0x18000764b  sub     rsp, 20h
0x18000764f  mov     rbp, rdx
0x180007652  mov     rax, [rcx]
0x180007655  xor     ecx, ecx
0x180007657  cmp     dword ptr [rax], 0C0000017h
0x18000765d  setz    cl
0x180007660  mov     eax, ecx
0x180007662  add     rsp, 20h
0x180007666  pop     rbp
0x180007667  retn
```
