# std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::allocator<std::_List_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::allocator<std::_List_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>>(void)

- ea: `0x14000859c`
- end: `0x140008606`
- name: `??1?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006c84`
- `0x140007778`
- `0x1400080e0`
- `0x14000842c`
- `0x14000b248`
- `0x14000b5b4`
- `0x140011bd7`

## callees

- `0x140001934`
- `0x14000859c`

## pseudocode

```c
void __fastcall std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(
        char **a1)
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
0x14000859c  push    rbx
0x14000859e  sub     rsp, 20h
0x1400085a2  mov     rdx, [rcx]
0x1400085a5  mov     rbx, rcx
0x1400085a8  test    rdx, rdx
0x1400085ab  jz      short loc_140008600
0x1400085ad  mov     rax, [rcx+10h]
0x1400085b1  sub     rax, rdx
0x1400085b4  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400085b8  cmp     rax, 1000h
0x1400085be  jb      short loc_1400085DE
0x1400085c0  mov     rcx, [rdx-8]
0x1400085c4  sub     rdx, rcx
0x1400085c7  sub     rdx, 8
0x1400085cb  cmp     rdx, 1Fh
0x1400085cf  ja      short loc_1400085D7
0x1400085d1  add     rax, 27h ; '''
0x1400085d5  jmp     short loc_1400085E1
0x1400085d7  mov     ecx, 5
0x1400085dc  int     29h; Win8: RtlFailFast(ecx)
0x1400085de  mov     rcx, rdx; void *
0x1400085e1  mov     rdx, rax; unsigned __int64
0x1400085e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400085e9  mov     qword ptr [rbx], 0
0x1400085f0  mov     qword ptr [rbx+8], 0
0x1400085f8  mov     qword ptr [rbx+10h], 0
0x140008600  add     rsp, 20h
0x140008604  pop     rbx
0x140008605  retn
```
