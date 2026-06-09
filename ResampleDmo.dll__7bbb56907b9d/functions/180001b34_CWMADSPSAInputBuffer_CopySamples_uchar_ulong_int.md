# CWMADSPSAInputBuffer::CopySamples(uchar *,ulong,int)

- ea: `0x180001b34`
- end: `0x180001b81`
- name: `?CopySamples@CWMADSPSAInputBuffer@@AEAAXPEAEKH@Z`
- size: `77`
- prototype: `void __fastcall(CWMADSPSAInputBuffer *__hidden this, unsigned __int8 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001180`

## callees

- `0x180085010`

## pseudocode

```c
void __fastcall CWMADSPSAInputBuffer::CopySamples(CWMADSPSAInputBuffer *this, unsigned __int8 *a2, __int64 a3, int a4)
{
  (*((void (__fastcall **)(char *, unsigned __int8 *, __int64, _QWORD, __int64, _DWORD, int))this + 15))(
    (char *)this + 72,
    a2,
    a3,
    *((unsigned int *)this + 13) + *((_QWORD *)this + 3),
    *((_QWORD *)this + 2) + 4LL * *((unsigned int *)this + 13),
    *((_DWORD *)this + 3),
    a4);
}

```

## disassembly

```asm
0x180001b34  mov     [rsp+arg_0], rbx
0x180001b39  push    rdi
0x180001b3a  sub     rsp, 40h
0x180001b3e  mov     r10d, [rcx+34h]
0x180001b42  lea     rdi, [rcx+48h]
0x180001b46  mov     rax, [rcx+10h]
0x180001b4a  mov     ebx, r9d
0x180001b4d  mov     r9, [rcx+18h]
0x180001b51  add     r9, r10
0x180001b54  mov     [rsp+48h+var_18], ebx
0x180001b58  lea     r11, [rax+r10*4]
0x180001b5c  mov     r10d, [rcx+0Ch]
0x180001b60  mov     rax, [rdi+30h]
0x180001b64  mov     rcx, rdi
0x180001b67  mov     [rsp+48h+var_20], r10d
0x180001b6c  mov     [rsp+48h+var_28], r11
0x180001b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b76  mov     rbx, [rsp+48h+arg_0]
0x180001b7b  add     rsp, 40h
0x180001b7f  pop     rdi
0x180001b80  retn
```
