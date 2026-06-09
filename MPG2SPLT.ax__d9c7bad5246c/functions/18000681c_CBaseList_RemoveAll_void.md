# CBaseList::RemoveAll(void)

- ea: `0x18000681c`
- end: `0x180006859`
- name: `?RemoveAll@CBaseList@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(CBaseList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005be0`
- `0x18000676c`

## callees

- `0x180001048`
- `0x18000681c`

## pseudocode

```c
void __fastcall CBaseList::RemoveAll(CBaseList *this)
{
  _QWORD *v1; // rdi
  void *v3; // rcx

  v1 = *(_QWORD **)this;
  while ( v1 )
  {
    v3 = v1;
    v1 = (_QWORD *)v1[1];
    operator delete(v3);
  }
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18000681c  mov     [rsp+arg_0], rbx
0x180006821  push    rdi
0x180006822  sub     rsp, 20h
0x180006826  mov     rdi, [rcx]
0x180006829  mov     rbx, rcx
0x18000682c  jmp     short loc_18000683F
0x18000682e  mov     rcx, rdi; void *
0x180006831  mov     edx, 18h; unsigned __int64
0x180006836  mov     rdi, [rdi+8]
0x18000683a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000683f  test    rdi, rdi
0x180006842  jnz     short loc_18000682E
0x180006844  mov     [rbx+10h], edi
0x180006847  mov     [rbx+8], rdi
0x18000684b  mov     [rbx], rdi
0x18000684e  mov     rbx, [rsp+28h+arg_0]
0x180006853  add     rsp, 20h
0x180006857  pop     rdi
0x180006858  retn
```
