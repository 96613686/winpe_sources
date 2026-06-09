# CLogStream::ReadAddRef(void)

- ea: `0x18000cbf0`
- end: `0x18000cc3e`
- name: `?ReadAddRef@CLogStream@@MEAAKXZ`
- size: `78`
- prototype: `unsigned int __fastcall(CLogStream *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CLogStream::ReadAddRef(void (__fastcall ***this)(char *))
{
  __int64 *v1; // rsi
  __int64 v3; // rdx
  unsigned int v4; // ebx

  v1 = (__int64 *)(this + 2);
  (*this[2])((char *)this + 16);
  v3 = *v1;
  ++*((_DWORD *)this + 18);
  ++*((_DWORD *)this + 2);
  v4 = *((_DWORD *)this + 18);
  (*(void (__fastcall **)(__int64 *))(v3 + 8))(v1);
  return v4;
}

```

## disassembly

```asm
0x18000cbf0  mov     [rsp+arg_0], rbx
0x18000cbf5  mov     [rsp+arg_8], rsi
0x18000cbfa  push    rdi
0x18000cbfb  sub     rsp, 20h
0x18000cbff  lea     rsi, [rcx+10h]
0x18000cc03  mov     rdi, rcx
0x18000cc06  mov     rax, [rsi]
0x18000cc09  mov     rcx, rsi
0x18000cc0c  mov     rax, [rax]
0x18000cc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc14  mov     rdx, [rsi]
0x18000cc17  mov     rcx, rsi
0x18000cc1a  inc     dword ptr [rdi+48h]
0x18000cc1d  inc     dword ptr [rdi+8]
0x18000cc20  mov     ebx, [rdi+48h]
0x18000cc23  mov     rax, [rdx+8]
0x18000cc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc2c  mov     rsi, [rsp+28h+arg_8]
0x18000cc31  mov     eax, ebx
0x18000cc33  mov     rbx, [rsp+28h+arg_0]
0x18000cc38  add     rsp, 20h
0x18000cc3c  pop     rdi
0x18000cc3d  retn
```
