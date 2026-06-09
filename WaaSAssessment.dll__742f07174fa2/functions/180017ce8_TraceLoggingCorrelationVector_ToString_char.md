# TraceLoggingCorrelationVector::ToString(char *)

- ea: `0x180017ce8`
- end: `0x180017d9f`
- name: `?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z`
- size: `183`
- prototype: `bool __fastcall(TraceLoggingCorrelationVector *__hidden this, char *Destination)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180016fd0`
- `0x1800170c8`
- `0x180017244`
- `0x1800176a4`
- `0x1800177f0`
- `0x180018234`

## callees

- `0x180017ce8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180017d2d`
- `msvcrt!memcpy_s` at `0x180017d2d`
- `msvcrt!sprintf_s` at `0x180017d86`
- `msvcrt!sprintf_s` at `0x180017d86`

## pseudocode

```c
bool __fastcall TraceLoggingCorrelationVector::ToString(TraceLoggingCorrelationVector *this, char *Destination)
{
  __int64 v4; // rdi
  __int64 v6; // rax
  size_t v7; // rdx
  char *v8; // rcx
  int v9; // eax

  v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)this + 17, 0);
  if ( !Destination )
    return 0;
  *Destination = 0;
  if ( memcpy_s(Destination, *((unsigned __int8 *)this + 130), this, WORD2(v4)) )
    return 0;
  if ( v4 >= 0 || (_DWORD)v4 )
  {
    v6 = *((unsigned __int8 *)this + 129);
    v7 = *((unsigned __int8 *)this + 130) - v6;
    v8 = &Destination[v6];
    if ( v4 >= 0 )
      v9 = sprintf_s(v8, v7, "%u", (unsigned int)v4);
    else
      v9 = sprintf_s(v8, v7, "%u!", (unsigned int)v4);
    return v9 != -1;
  }
  Destination[*((unsigned __int8 *)this + 129)] = 33;
  Destination[*((unsigned __int8 *)this + 129) + 1] = 0;
  return 1;
}

```

## disassembly

```asm
0x180017ce8  push    rbx
0x180017cea  push    rbp
0x180017ceb  push    rsi
0x180017cec  push    rdi
0x180017ced  sub     rsp, 28h
0x180017cf1  mov     rsi, rdx
0x180017cf4  mov     rbx, rcx
0x180017cf7  xor     edi, edi
0x180017cf9  lock xadd [rcx+88h], rdi
0x180017d02  test    rdi, rdi
0x180017d05  sets    bpl
0x180017d09  test    rdx, rdx
0x180017d0c  jnz     short loc_180017D12
0x180017d0e  xor     al, al
0x180017d10  jmp     short loc_180017D59
0x180017d12  mov     byte ptr [rdx], 0
0x180017d15  mov     rax, rdi
0x180017d18  movzx   edx, byte ptr [rcx+82h]; DestinationSize
0x180017d1f  mov     r8, rbx; Source
0x180017d22  shr     rax, 20h
0x180017d26  mov     rcx, rsi; Destination
0x180017d29  movzx   r9d, ax; SourceSize
0x180017d2d  call    cs:__imp_memcpy_s
0x180017d33  test    eax, eax
0x180017d35  jnz     short loc_180017D0E
0x180017d37  test    bpl, bpl
0x180017d3a  jz      short loc_180017D62
0x180017d3c  test    edi, edi
0x180017d3e  jnz     short loc_180017D62
0x180017d40  movzx   eax, byte ptr [rbx+81h]
0x180017d47  mov     byte ptr [rax+rsi], 21h ; '!'
0x180017d4b  movzx   eax, byte ptr [rbx+81h]
0x180017d52  mov     [rax+rsi+1], dil
0x180017d57  mov     al, 1
0x180017d59  add     rsp, 28h
0x180017d5d  pop     rdi
0x180017d5e  pop     rsi
0x180017d5f  pop     rbp
0x180017d60  pop     rbx
0x180017d61  retn
0x180017d62  movzx   eax, byte ptr [rbx+81h]
0x180017d69  mov     r9d, edi
0x180017d6c  movzx   edx, byte ptr [rbx+82h]
0x180017d73  sub     rdx, rax; BufferCount
0x180017d76  lea     rcx, [rax+rsi]; Buffer
0x180017d7a  test    bpl, bpl
0x180017d7d  jz      short loc_180017D96
0x180017d7f  lea     r8, Format; "%u!"
0x180017d86  call    cs:__imp_sprintf_s
0x180017d8c  cmp     eax, 0FFFFFFFFh
0x180017d8f  jnz     short loc_180017D57
0x180017d91  jmp     loc_180017D0E
0x180017d96  lea     r8, aU_0; "%u"
0x180017d9d  jmp     short loc_180017D86
```
