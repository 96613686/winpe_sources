# std::vector<double,std::allocator<double>>::~vector<double,std::allocator<double>>(void)

- ea: `0x1400130a0`
- end: `0x14001310a`
- name: `??1?$vector@NV?$allocator@N@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140017b40`
- `0x140017b60`
- `0x140017b80`
- `0x140017ba0`
- `0x140017bc0`
- `0x140017be0`

## callees

- `0x1400088f4`
- `0x1400130a0`

## pseudocode

```c
void __fastcall std::vector<double>::~vector<double>(char **a1)
{
  char *v1; // rdx
  unsigned __int64 v3; // rax
  char *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = (a1[2] - v1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v3 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v4 - 8) > 0x1F )
        __fastfail(5u);
      v3 += 39LL;
    }
    operator delete(v4, v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x1400130a0  push    rbx
0x1400130a2  sub     rsp, 20h
0x1400130a6  mov     rdx, [rcx]
0x1400130a9  mov     rbx, rcx
0x1400130ac  test    rdx, rdx
0x1400130af  jz      short loc_140013104
0x1400130b1  mov     rax, [rcx+10h]
0x1400130b5  sub     rax, rdx
0x1400130b8  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400130bc  cmp     rax, 1000h
0x1400130c2  jb      short loc_1400130E2
0x1400130c4  mov     rcx, [rdx-8]
0x1400130c8  sub     rdx, rcx
0x1400130cb  sub     rdx, 8
0x1400130cf  cmp     rdx, 1Fh
0x1400130d3  ja      short loc_1400130DB
0x1400130d5  add     rax, 27h ; '''
0x1400130d9  jmp     short loc_1400130E5
0x1400130db  mov     ecx, 5
0x1400130e0  int     29h; Win8: RtlFailFast(ecx)
0x1400130e2  mov     rcx, rdx; void *
0x1400130e5  mov     rdx, rax; unsigned __int64
0x1400130e8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400130ed  mov     qword ptr [rbx], 0
0x1400130f4  mov     qword ptr [rbx+8], 0
0x1400130fc  mov     qword ptr [rbx+10h], 0
0x140013104  add     rsp, 20h
0x140013108  pop     rbx
0x140013109  retn
```
