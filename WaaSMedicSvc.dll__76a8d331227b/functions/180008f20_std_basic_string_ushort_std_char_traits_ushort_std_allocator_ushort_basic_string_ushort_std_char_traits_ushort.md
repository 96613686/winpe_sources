# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180008f20`
- end: `0x180008f84`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `20`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006aec`
- `0x18000865c`
- `0x180008b20`
- `0x180008f8c`
- `0x180009118`
- `0x18000915c`
- `0x1800098a0`
- `0x180009ad0`
- `0x180009b34`
- `0x180009c3c`
- `0x180009d10`
- `0x180009fc8`
- `0x18000a060`
- `0x18000aa84`
- `0x18000b4e8`
- `0x18000c444`
- `0x18000c47e`
- `0x18000c490`
- `0x18000c565`
- `0x18000c710`

## callees

- `0x1800025d0`
- `0x180008f20`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = 2 * v1 + 2;
    if ( v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 += 39LL;
    }
    operator delete(v5, v4);
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
0x180008f20  push    rbx
0x180008f22  sub     rsp, 20h
0x180008f26  mov     rdx, [rcx+18h]
0x180008f2a  mov     rbx, rcx
0x180008f2d  cmp     rdx, 7
0x180008f31  jbe     short loc_180008F6D
0x180008f33  mov     rax, [rcx]
0x180008f36  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180008f3e  cmp     rdx, 1000h
0x180008f45  jb      short loc_180008F65
0x180008f47  mov     rcx, [rax-8]
0x180008f4b  sub     rax, rcx
0x180008f4e  sub     rax, 8
0x180008f52  cmp     rax, 1Fh
0x180008f56  ja      short loc_180008F5E
0x180008f58  add     rdx, 27h ; '''
0x180008f5c  jmp     short loc_180008F68
0x180008f5e  mov     ecx, 5
0x180008f63  int     29h; Win8: RtlFailFast(ecx)
0x180008f65  mov     rcx, rax; void *
0x180008f68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008f6d  xor     eax, eax
0x180008f6f  mov     qword ptr [rbx+18h], 7
0x180008f77  mov     [rbx+10h], rax
0x180008f7b  mov     [rbx], ax
0x180008f7e  add     rsp, 20h
0x180008f82  pop     rbx
0x180008f83  retn
```
