# WriteBuffer::Write(void const * const,ulong)

- ea: `0x180003780`
- end: `0x18000384f`
- name: `?Write@WriteBuffer@@QEAAXQEBXK@Z`
- size: `207`
- prototype: `void(WriteBuffer *__hidden this, const void *const, unsigned int)`
- caller_count: `29`
- callee_count: `4`
- tags: ``

## callers

- `0x180001d58`
- `0x1800020f0`
- `0x1800023e8`
- `0x1800031f0`
- `0x180004070`
- `0x18002404c`
- `0x180024338`
- `0x180024388`
- `0x18002e478`
- `0x18002e4e4`
- `0x18002e628`
- `0x18002e660`
- `0x18002e704`
- `0x18002e89c`
- `0x18002e944`
- `0x18002eab4`
- `0x18002eafc`
- `0x18002f324`
- `0x18002f50c`
- `0x18002f560`
- `0x18002f6fc`
- `0x18002f778`
- `0x18002f7ec`
- `0x18002f84c`
- `0x18002f8d4`
- `0x18002fec0`
- `0x1800303fc`
- `0x1800359f0`
- `0x180035c70`

## callees

- `0x180003780`
- `0x1800231d0`
- `0x180038fcc`
- `0x18003c010`

## pseudocode

```c
void __fastcall WriteBuffer::Write(Write *this, const void *a2, unsigned int a3)
{
  __int64 v3; // r9
  int v7; // edi
  unsigned int v8; // eax

  v3 = *((_QWORD *)this + 1);
  if ( v3 && a3 <= 0x10000000 && a3 <= *((_DWORD *)this + 5) - *((_DWORD *)this + 4) )
  {
    memcpy_0((void *)(v3 + *((unsigned int *)this + 4)), a2, a3);
    *((_DWORD *)this + 4) += a3;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 32LL))(*(_QWORD *)this, *((unsigned int *)this + 4));
    (*(void (__fastcall **)(_QWORD, const void *, _QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, a2, a3);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *((_QWORD *)this + 1) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 48LL))(*(_QWORD *)this);
    *((_DWORD *)this + 5) = v7;
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this);
    if ( v8 > *((_DWORD *)this + 5) )
      UserBuffer::ThrowUnexpectedEOFException();
    *((_DWORD *)this + 4) = v8;
  }
}

```

## disassembly

```asm
0x180003780  mov     [rsp+arg_0], rbx
0x180003785  mov     [rsp+arg_8], rsi
0x18000378a  push    rdi
0x18000378b  sub     rsp, 20h
0x18000378f  mov     r9, [rcx+8]
0x180003793  mov     rsi, rdx
0x180003796  mov     edi, r8d
0x180003799  mov     rbx, rcx
0x18000379c  test    r9, r9
0x18000379f  jz      short loc_1800037D4
0x1800037a1  cmp     edi, 10000000h
0x1800037a7  ja      short loc_1800037D4
0x1800037a9  mov     eax, [rcx+14h]
0x1800037ac  sub     eax, [rcx+10h]
0x1800037af  cmp     edi, eax
0x1800037b1  ja      short loc_1800037D4
0x1800037b3  mov     ecx, [rcx+10h]
0x1800037b6  mov     r8d, edi; Size
0x1800037b9  add     rcx, r9; void *
0x1800037bc  call    memcpy_0
0x1800037c1  add     [rbx+10h], edi
0x1800037c4  mov     rbx, [rsp+28h+arg_0]
0x1800037c9  mov     rsi, [rsp+28h+arg_8]
0x1800037ce  add     rsp, 20h
0x1800037d2  pop     rdi
0x1800037d3  retn
0x1800037d4  mov     rcx, [rcx]
0x1800037d7  mov     edx, [rbx+10h]
0x1800037da  mov     rax, [rcx]
0x1800037dd  mov     rax, [rax+20h]
0x1800037e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e6  mov     rcx, [rbx]
0x1800037e9  mov     r8d, edi
0x1800037ec  mov     rdx, rsi
0x1800037ef  mov     rax, [rcx]
0x1800037f2  mov     rax, [rax+8]
0x1800037f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037fb  mov     rcx, [rbx]
0x1800037fe  mov     rax, [rcx]
0x180003801  mov     rax, [rax+10h]
0x180003805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380a  mov     rcx, [rbx]
0x18000380d  mov     edi, eax
0x18000380f  mov     rdx, [rcx]
0x180003812  mov     rax, [rdx+30h]
0x180003816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381b  mov     [rbx+8], rax
0x18000381f  mov     [rbx+14h], edi
0x180003822  mov     rcx, [rbx]
0x180003825  mov     rax, [rcx]
0x180003828  mov     rax, [rax+18h]
0x18000382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003831  cmp     eax, [rbx+14h]
0x180003834  ja      short loc_180003849
0x180003836  mov     rsi, [rsp+28h+arg_8]
0x18000383b  mov     [rbx+10h], eax
0x18000383e  mov     rbx, [rsp+28h+arg_0]
0x180003843  add     rsp, 20h
0x180003847  pop     rdi
0x180003848  retn
0x180003849  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
```
