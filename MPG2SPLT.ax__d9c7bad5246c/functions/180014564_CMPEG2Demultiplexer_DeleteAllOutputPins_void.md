# CMPEG2Demultiplexer::DeleteAllOutputPins_(void)

- ea: `0x180014564`
- end: `0x180014602`
- name: `?DeleteAllOutputPins_@CMPEG2Demultiplexer@@AEAAJXZ`
- size: `158`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180015260`
- `0x18001a9a0`

## callees

- `0x180001048`
- `0x180014564`
- `0x180014608`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::DeleteAllOutputPins_(CMPEG2Demultiplexer *this)
{
  int v1; // esi
  volatile signed __int32 **i; // rax
  volatile signed __int32 *v4; // rbx

  v1 = 0;
  if ( *((_DWORD *)this + 48) )
  {
    for ( i = (volatile signed __int32 **)*((_QWORD *)this + 23); ; i = (volatile signed __int32 **)*((_QWORD *)this + 23) )
    {
      v4 = *i;
      if ( !*i || v1 < 0 )
        break;
      _InterlockedIncrement(v4 + 2);
      v1 = CMPEG2Demultiplexer::DeletePin_(this, *((const unsigned __int16 **)v4 + 2));
      if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        operator delete(*((void **)v4 + 2));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v4 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v4 + 8LL));
        operator delete((void *)v4);
      }
      if ( !*((_DWORD *)this + 48) )
        break;
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180014564  mov     [rsp+arg_8], rbx
0x180014569  mov     [rsp+arg_10], rsi
0x18001456e  push    rdi
0x18001456f  sub     rsp, 20h
0x180014573  xor     esi, esi
0x180014575  mov     rdi, rcx
0x180014578  cmp     [rcx+0C0h], esi
0x18001457e  jbe     short loc_1800145F0
0x180014580  mov     rax, [rcx+0B8h]
0x180014587  jmp     short loc_1800145E8
0x180014589  test    esi, esi
0x18001458b  js      short loc_1800145F0
0x18001458d  lock inc dword ptr [rbx+8]
0x180014591  mov     rdx, [rbx+10h]; unsigned __int16 *
0x180014595  mov     rcx, rdi; this
0x180014598  call    ?DeletePin_@CMPEG2Demultiplexer@@AEAAJPEBG@Z; CMPEG2Demultiplexer::DeletePin_(ushort const *)
0x18001459d  mov     esi, eax
0x18001459f  or      ecx, 0FFFFFFFFh
0x1800145a2  lock xadd [rbx+8], ecx
0x1800145a7  cmp     ecx, 1
0x1800145aa  jnz     short loc_1800145D8
0x1800145ac  lea     edx, [rcx+1]; unsigned __int64
0x1800145af  mov     rcx, [rbx+10h]; void *
0x1800145b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800145b8  mov     rdx, [rbx]
0x1800145bb  mov     rcx, [rdx+8]
0x1800145bf  mov     rdx, [rcx]
0x1800145c2  mov     rax, [rdx+10h]
0x1800145c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145cb  mov     edx, 18h; unsigned __int64
0x1800145d0  mov     rcx, rbx; void *
0x1800145d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800145d8  cmp     dword ptr [rdi+0C0h], 0
0x1800145df  jbe     short loc_1800145F0
0x1800145e1  mov     rax, [rdi+0B8h]
0x1800145e8  mov     rbx, [rax]
0x1800145eb  test    rbx, rbx
0x1800145ee  jnz     short loc_180014589
0x1800145f0  mov     rbx, [rsp+28h+arg_8]
0x1800145f5  mov     eax, esi
0x1800145f7  mov     rsi, [rsp+28h+arg_10]
0x1800145fc  add     rsp, 20h
0x180014600  pop     rdi
0x180014601  retn
```
