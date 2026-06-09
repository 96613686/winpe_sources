# std::vector<ushort const *,std::allocator<ushort const *>>::~vector<ushort const *,std::allocator<ushort const *>>(void)

- ea: `0x180007064`
- end: `0x1800070ce`
- name: `??1?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008de0`
- `0x18000a5c4`
- `0x18000a5d6`

## callees

- `0x180001a70`
- `0x180007064`

## pseudocode

```c
void __fastcall std::vector<unsigned short const *>::~vector<unsigned short const *>(char **a1)
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
0x180007064  push    rbx
0x180007066  sub     rsp, 20h
0x18000706a  mov     rdx, [rcx]
0x18000706d  mov     rbx, rcx
0x180007070  test    rdx, rdx
0x180007073  jz      short loc_1800070C8
0x180007075  mov     rax, [rcx+10h]
0x180007079  sub     rax, rdx
0x18000707c  and     rax, 0FFFFFFFFFFFFFFF8h
0x180007080  cmp     rax, 1000h
0x180007086  jb      short loc_1800070A6
0x180007088  mov     rcx, [rdx-8]
0x18000708c  sub     rdx, rcx
0x18000708f  sub     rdx, 8
0x180007093  cmp     rdx, 1Fh
0x180007097  ja      short loc_18000709F
0x180007099  add     rax, 27h ; '''
0x18000709d  jmp     short loc_1800070A9
0x18000709f  mov     ecx, 5
0x1800070a4  int     29h; Win8: RtlFailFast(ecx)
0x1800070a6  mov     rcx, rdx; void *
0x1800070a9  mov     rdx, rax; unsigned __int64
0x1800070ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800070b1  mov     qword ptr [rbx], 0
0x1800070b8  mov     qword ptr [rbx+8], 0
0x1800070c0  mov     qword ptr [rbx+10h], 0
0x1800070c8  add     rsp, 20h
0x1800070cc  pop     rbx
0x1800070cd  retn
```
