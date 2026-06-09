# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x14000d5a8`
- end: `0x14000d60c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000d15c`
- `0x14000e0e4`
- `0x14001245b`
- `0x1400124b3`

## callees

- `0x1400015f4`
- `0x14000d5a8`

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
0x14000d5a8  push    rbx
0x14000d5aa  sub     rsp, 20h
0x14000d5ae  mov     rdx, [rcx+18h]
0x14000d5b2  mov     rbx, rcx
0x14000d5b5  cmp     rdx, 7
0x14000d5b9  jbe     short loc_14000D5F5
0x14000d5bb  mov     rax, [rcx]
0x14000d5be  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x14000d5c6  cmp     rdx, 1000h
0x14000d5cd  jb      short loc_14000D5ED
0x14000d5cf  mov     rcx, [rax-8]
0x14000d5d3  sub     rax, rcx
0x14000d5d6  sub     rax, 8
0x14000d5da  cmp     rax, 1Fh
0x14000d5de  ja      short loc_14000D5E6
0x14000d5e0  add     rdx, 27h ; '''
0x14000d5e4  jmp     short loc_14000D5F0
0x14000d5e6  mov     ecx, 5
0x14000d5eb  int     29h; Win8: RtlFailFast(ecx)
0x14000d5ed  mov     rcx, rax; void *
0x14000d5f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d5f5  xor     eax, eax
0x14000d5f7  mov     qword ptr [rbx+18h], 7
0x14000d5ff  mov     [rbx+10h], rax
0x14000d603  mov     [rbx], ax
0x14000d606  add     rsp, 20h
0x14000d60a  pop     rbx
0x14000d60b  retn
```
