# std::list<std::pair<unsigned __int64 const,Private::ThreadInfo *>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>::~list<std::pair<unsigned __int64 const,Private::ThreadInfo *>,std::allocator<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>(void)

- ea: `0x180021220`
- end: `0x18002126f`
- name: `??1?$list@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@2@@std@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002a67c`
- `0x18002a702`

## callees

- `0x1800036e4`
- `0x180021220`

## pseudocode

```c
void __fastcall std::list<std::pair<unsigned __int64 const,Private::ThreadInfo *>>::~list<std::pair<unsigned __int64 const,Private::ThreadInfo *>>(
        void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v1 = (_QWORD **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x180021220  mov     [rsp+arg_0], rbx
0x180021225  push    rdi
0x180021226  sub     rsp, 20h
0x18002122a  mov     rdx, [rcx]
0x18002122d  mov     rdi, rcx
0x180021230  mov     rax, [rdx+8]
0x180021234  mov     qword ptr [rax], 0
0x18002123b  mov     rcx, [rdx]; Block
0x18002123e  test    rcx, rcx
0x180021241  jz      short loc_180021258
0x180021243  mov     rbx, [rcx]
0x180021246  mov     edx, 20h ; ' '
0x18002124b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021250  mov     rcx, rbx
0x180021253  test    rbx, rbx
0x180021256  jnz     short loc_180021243
0x180021258  mov     rcx, [rdi]; Block
0x18002125b  mov     edx, 20h ; ' '
0x180021260  mov     rbx, [rsp+28h+arg_0]
0x180021265  add     rsp, 20h
0x180021269  pop     rdi
0x18002126a  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
