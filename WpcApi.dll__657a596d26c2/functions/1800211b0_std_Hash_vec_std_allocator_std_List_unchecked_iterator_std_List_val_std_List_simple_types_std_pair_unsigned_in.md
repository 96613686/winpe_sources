# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>(void)

- ea: `0x1800211b0`
- end: `0x18002121a`
- name: `??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180021278`
- `0x1800215b0`
- `0x180021c30`
- `0x18002a692`
- `0x18002a718`

## callees

- `0x1800036e4`
- `0x1800211b0`

## pseudocode

```c
void __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>(
        char **a1)
{
  char *v1; // rdx
  char *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    if ( ((a1[2] - v1) & 0xFFFFFFFFFFFFFFF8uLL) < 0x1000 )
    {
      v3 = *a1;
    }
    else
    {
      v3 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v3 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x1800211b0  push    rbx
0x1800211b2  sub     rsp, 20h
0x1800211b6  mov     rdx, [rcx]
0x1800211b9  mov     rbx, rcx
0x1800211bc  test    rdx, rdx
0x1800211bf  jz      short loc_180021214
0x1800211c1  mov     rax, [rcx+10h]
0x1800211c5  sub     rax, rdx
0x1800211c8  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800211cc  cmp     rax, 1000h
0x1800211d2  jb      short loc_1800211F2
0x1800211d4  mov     rcx, [rdx-8]
0x1800211d8  sub     rdx, rcx
0x1800211db  sub     rdx, 8
0x1800211df  cmp     rdx, 1Fh
0x1800211e3  ja      short loc_1800211EB
0x1800211e5  add     rax, 27h ; '''
0x1800211e9  jmp     short loc_1800211F5
0x1800211eb  mov     ecx, 5
0x1800211f0  int     29h; Win8: RtlFailFast(ecx)
0x1800211f2  mov     rcx, rdx; Block
0x1800211f5  mov     rdx, rax
0x1800211f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800211fd  mov     qword ptr [rbx], 0
0x180021204  mov     qword ptr [rbx+8], 0
0x18002120c  mov     qword ptr [rbx+10h], 0
0x180021214  add     rsp, 20h
0x180021218  pop     rbx
0x180021219  retn
```
