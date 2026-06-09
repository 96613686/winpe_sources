# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy_deallocate(void)

- ea: `0x14000d5d8`
- end: `0x14000d63c`
- name: `?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000bbbc`
- `0x14000c61c`
- `0x14000c6f0`
- `0x14000d75c`
- `0x14000d884`
- `0x14000ef70`

## callees

- `0x140003644`
- `0x14000d5d8`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy_deallocate(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  char *v4; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    if ( 2 * v1 + 2 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v4 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v4);
  }
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x14000d5d8  push    rbx
0x14000d5da  sub     rsp, 20h
0x14000d5de  mov     rdx, [rcx+18h]
0x14000d5e2  mov     rbx, rcx
0x14000d5e5  cmp     rdx, 7
0x14000d5e9  jbe     short loc_14000D625
0x14000d5eb  mov     rax, [rcx]
0x14000d5ee  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x14000d5f6  cmp     rdx, 1000h
0x14000d5fd  jb      short loc_14000D61D
0x14000d5ff  mov     rcx, [rax-8]
0x14000d603  sub     rax, rcx
0x14000d606  sub     rax, 8
0x14000d60a  cmp     rax, 1Fh
0x14000d60e  ja      short loc_14000D616
0x14000d610  add     rdx, 27h ; '''
0x14000d614  jmp     short loc_14000D620
0x14000d616  mov     ecx, 5
0x14000d61b  int     29h; Win8: RtlFailFast(ecx)
0x14000d61d  mov     rcx, rax; void *
0x14000d620  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d625  xor     eax, eax
0x14000d627  mov     qword ptr [rbx+18h], 7
0x14000d62f  mov     [rbx+10h], rax
0x14000d633  mov     [rbx], ax
0x14000d636  add     rsp, 20h
0x14000d63a  pop     rbx
0x14000d63b  retn
```
