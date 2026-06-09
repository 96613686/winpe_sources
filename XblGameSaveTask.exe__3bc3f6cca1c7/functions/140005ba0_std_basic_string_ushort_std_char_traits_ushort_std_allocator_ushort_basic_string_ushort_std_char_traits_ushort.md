# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140005ba0`
- end: `0x140005c04`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140005c30`
- `0x1400065f0`
- `0x140006700`

## callees

- `0x140001714`
- `0x140005ba0`

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
0x140005ba0  push    rbx
0x140005ba2  sub     rsp, 20h
0x140005ba6  mov     rdx, [rcx+18h]
0x140005baa  mov     rbx, rcx
0x140005bad  cmp     rdx, 7
0x140005bb1  jbe     short loc_140005BED
0x140005bb3  mov     rax, [rcx]
0x140005bb6  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x140005bbe  cmp     rdx, 1000h
0x140005bc5  jb      short loc_140005BE5
0x140005bc7  mov     rcx, [rax-8]
0x140005bcb  sub     rax, rcx
0x140005bce  sub     rax, 8
0x140005bd2  cmp     rax, 1Fh
0x140005bd6  ja      short loc_140005BDE
0x140005bd8  add     rdx, 27h ; '''
0x140005bdc  jmp     short loc_140005BE8
0x140005bde  mov     ecx, 5
0x140005be3  int     29h; Win8: RtlFailFast(ecx)
0x140005be5  mov     rcx, rax; void *
0x140005be8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005bed  xor     eax, eax
0x140005bef  mov     qword ptr [rbx+18h], 7
0x140005bf7  mov     [rbx+10h], rax
0x140005bfb  mov     [rbx], ax
0x140005bfe  add     rsp, 20h
0x140005c02  pop     rbx
0x140005c03  retn
```
