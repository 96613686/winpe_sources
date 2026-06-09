# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000bf6c`
- end: `0x18000bfd0`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `81`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bffc`
- `0x18000d8e8`
- `0x18000d9b4`
- `0x18000e0a4`
- `0x18000e840`
- `0x18000eae0`
- `0x18000ec98`
- `0x180010954`
- `0x180010cd4`
- `0x1800116e0`
- `0x1800117d8`
- `0x180011858`
- `0x180011918`
- `0x180012d10`
- `0x1800130d0`
- `0x180014484`
- `0x180014ab0`
- `0x1800159c8`
- `0x180015ae4`
- `0x180016348`
- `0x180016740`
- `0x180016bec`
- `0x180017014`
- `0x180017670`
- `0x180018b70`
- `0x180019558`
- `0x18001a9b4`
- `0x18001ab60`
- `0x18001b094`
- `0x18001b1b0`
- `0x18001c494`
- `0x18001cf9c`
- `0x18001d680`
- `0x18001e714`
- `0x18001e8cc`
- `0x18001ea90`
- `0x18001fe0f`
- `0x18001fe21`
- `0x18001fe33`
- `0x18001fe57`
- `0x18001fe69`
- `0x18001fe7b`
- `0x18001fe9f`
- `0x18001fec3`
- `0x18001fed5`
- `0x18001fee7`
- `0x18001fef9`
- `0x18001ff0b`
- `0x18001ff1d`
- `0x18001ff2f`

## callees

- `0x180003914`
- `0x18000bf6c`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
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
0x18000bf6c  push    rbx
0x18000bf6e  sub     rsp, 20h
0x18000bf72  mov     rdx, [rcx+18h]
0x18000bf76  mov     rbx, rcx
0x18000bf79  cmp     rdx, 7
0x18000bf7d  jbe     short loc_18000BFB9
0x18000bf7f  mov     rax, [rcx]
0x18000bf82  lea     rdx, ds:2[rdx*2]
0x18000bf8a  cmp     rdx, 1000h
0x18000bf91  jb      short loc_18000BFB1
0x18000bf93  mov     rcx, [rax-8]
0x18000bf97  sub     rax, rcx
0x18000bf9a  sub     rax, 8
0x18000bf9e  cmp     rax, 1Fh
0x18000bfa2  ja      short loc_18000BFAA
0x18000bfa4  add     rdx, 27h ; '''
0x18000bfa8  jmp     short loc_18000BFB4
0x18000bfaa  mov     ecx, 5
0x18000bfaf  int     29h; Win8: RtlFailFast(ecx)
0x18000bfb1  mov     rcx, rax; Block
0x18000bfb4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bfb9  xor     eax, eax
0x18000bfbb  mov     qword ptr [rbx+18h], 7
0x18000bfc3  mov     [rbx+10h], rax
0x18000bfc7  mov     [rbx], ax
0x18000bfca  add     rsp, 20h
0x18000bfce  pop     rbx
0x18000bfcf  retn
```
