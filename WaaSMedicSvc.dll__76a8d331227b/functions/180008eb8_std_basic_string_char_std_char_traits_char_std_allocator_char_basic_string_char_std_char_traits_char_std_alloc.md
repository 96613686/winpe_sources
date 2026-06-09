# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180008eb8`
- end: `0x180008f19`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008794`
- `0x180008dd8`
- `0x180009118`
- `0x180009ad0`
- `0x18000ae6c`
- `0x18000c256`
- `0x18000c2ca`
- `0x18000c2dc`
- `0x18000c503`
- `0x18000c52f`
- `0x18000c541`
- `0x18000c553`

## callees

- `0x1800025d0`
- `0x180008eb8`

## pseudocode

```c
void __fastcall std::string::~string(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 0xF )
  {
    v3 = *a1;
    v4 = v1 + 1;
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
  a1[2] = 0;
  a1[3] = (char *)15;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x180008eb8  push    rbx
0x180008eba  sub     rsp, 20h
0x180008ebe  mov     rdx, [rcx+18h]
0x180008ec2  mov     rbx, rcx
0x180008ec5  cmp     rdx, 0Fh
0x180008ec9  jbe     short loc_180008F00
0x180008ecb  mov     rax, [rcx]
0x180008ece  inc     rdx; unsigned __int64
0x180008ed1  cmp     rdx, 1000h
0x180008ed8  jb      short loc_180008EF8
0x180008eda  mov     rcx, [rax-8]
0x180008ede  sub     rax, rcx
0x180008ee1  sub     rax, 8
0x180008ee5  cmp     rax, 1Fh
0x180008ee9  ja      short loc_180008EF1
0x180008eeb  add     rdx, 27h ; '''
0x180008eef  jmp     short loc_180008EFB
0x180008ef1  mov     ecx, 5
0x180008ef6  int     29h; Win8: RtlFailFast(ecx)
0x180008ef8  mov     rcx, rax; void *
0x180008efb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008f00  mov     qword ptr [rbx+10h], 0
0x180008f08  mov     qword ptr [rbx+18h], 0Fh
0x180008f10  mov     byte ptr [rbx], 0
0x180008f13  add     rsp, 20h
0x180008f17  pop     rbx
0x180008f18  retn
```
