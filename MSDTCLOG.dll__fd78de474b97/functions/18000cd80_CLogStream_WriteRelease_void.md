# CLogStream::WriteRelease(void)

- ea: `0x18000cd80`
- end: `0x18000cdd1`
- name: `?WriteRelease@CLogStream@@MEAAKXZ`
- size: `81`
- prototype: `unsigned int __fastcall(CLogStream *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CLogStream::WriteRelease(CLogStream *this)
{
  char *v1; // rsi
  unsigned int v3; // ebx

  v1 = (char *)this + 16;
  (**((void (__fastcall ***)(char *))this + 2))((char *)this + 16);
  v3 = *((_DWORD *)this + 19);
  --*((_DWORD *)this + 2);
  *((_DWORD *)this + 19) = v3 - 1;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v1 + 8LL))(v1);
  return v3;
}

```

## disassembly

```asm
0x18000cd80  mov     [rsp+arg_0], rbx
0x18000cd85  mov     [rsp+arg_8], rsi
0x18000cd8a  push    rdi
0x18000cd8b  sub     rsp, 20h
0x18000cd8f  lea     rsi, [rcx+10h]
0x18000cd93  mov     rdi, rcx
0x18000cd96  mov     rax, [rsi]
0x18000cd99  mov     rcx, rsi
0x18000cd9c  mov     rax, [rax]
0x18000cd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cda4  mov     ebx, [rdi+4Ch]
0x18000cda7  mov     rcx, rsi
0x18000cdaa  dec     dword ptr [rdi+8]
0x18000cdad  lea     edx, [rbx-1]
0x18000cdb0  mov     [rdi+4Ch], edx
0x18000cdb3  mov     rdx, [rsi]
0x18000cdb6  mov     rax, [rdx+8]
0x18000cdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdbf  mov     rsi, [rsp+28h+arg_8]
0x18000cdc4  mov     eax, ebx
0x18000cdc6  mov     rbx, [rsp+28h+arg_0]
0x18000cdcb  add     rsp, 20h
0x18000cdcf  pop     rdi
0x18000cdd0  retn
```
