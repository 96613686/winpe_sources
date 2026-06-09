# midiStreamMessage

- ea: `0x180017cc0`
- end: `0x180017d2a`
- name: `midiStreamMessage`
- size: `106`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180007420`
- `0x18000bee0`
- `0x18000fa80`
- `0x180017aa0`
- `0x180017b20`
- `0x180017d30`
- `0x1800183c0`
- `0x1800186c0`
- `0x1800187a0`
- `0x180019740`

## callees

- `0x180017cc0`
- `0x18001fb58`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ce4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ce4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017d09`

## pseudocode

```c
__int64 __fastcall midiStreamMessage(__int64 a1, UINT a2, unsigned __int8 *a3, __int64 a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  unsigned int v9; // ebx

  if ( (*(_BYTE *)(a1 + 32) & 1) != 0 )
    return mseMessage(a2, *(struct midiemu_tag **)(a1 + 24), a3, a4);
  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int8 *, __int64))(a1 + 16))(
         0,
         a2,
         *(_QWORD *)(a1 + 24),
         a3,
         a4);
  LeaveCriticalSection(v8);
  return v9;
}

```

## disassembly

```asm
0x180017cc0  push    rbx
0x180017cc2  push    rbp
0x180017cc3  push    rsi
0x180017cc4  push    rdi
0x180017cc5  push    r14
0x180017cc7  sub     rsp, 30h
0x180017ccb  test    byte ptr [rcx+20h], 1
0x180017ccf  mov     rsi, r9
0x180017cd2  mov     rbp, r8
0x180017cd5  mov     r14d, edx
0x180017cd8  mov     rbx, rcx
0x180017cdb  jnz     short loc_180017D13
0x180017cdd  lea     rdi, [rcx+28h]
0x180017ce1  mov     rcx, rdi; lpCriticalSection
0x180017ce4  call    cs:__imp_EnterCriticalSection
0x180017cea  mov     r8, [rbx+18h]
0x180017cee  mov     r9, rbp
0x180017cf1  mov     rax, [rbx+10h]
0x180017cf5  mov     edx, r14d
0x180017cf8  xor     ecx, ecx
0x180017cfa  mov     [rsp+58h+var_38], rsi
0x180017cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d04  mov     rcx, rdi; lpCriticalSection
0x180017d07  mov     ebx, eax
0x180017d09  call    cs:__imp_LeaveCriticalSection
0x180017d0f  mov     eax, ebx
0x180017d11  jmp     short loc_180017D1F
0x180017d13  mov     rdx, [rcx+18h]; struct midiemu_tag *
0x180017d17  mov     ecx, r14d; uMsg
0x180017d1a  call    mseMessage
0x180017d1f  add     rsp, 30h
0x180017d23  pop     r14
0x180017d25  pop     rdi
0x180017d26  pop     rsi
0x180017d27  pop     rbp
0x180017d28  pop     rbx
0x180017d29  retn
```
