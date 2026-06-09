# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000887c`
- end: `0x1800088e0`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009414`
- `0x180009a30`
- `0x18000c4a7`
- `0x18000c4b9`
- `0x18000c545`

## callees

- `0x180002af0`
- `0x18000887c`

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
0x18000887c  push    rbx
0x18000887e  sub     rsp, 20h
0x180008882  mov     rdx, [rcx+18h]
0x180008886  mov     rbx, rcx
0x180008889  cmp     rdx, 7
0x18000888d  jbe     short loc_1800088C9
0x18000888f  mov     rax, [rcx]
0x180008892  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000889a  cmp     rdx, 1000h
0x1800088a1  jb      short loc_1800088C1
0x1800088a3  mov     rcx, [rax-8]
0x1800088a7  sub     rax, rcx
0x1800088aa  sub     rax, 8
0x1800088ae  cmp     rax, 1Fh
0x1800088b2  ja      short loc_1800088BA
0x1800088b4  add     rdx, 27h ; '''
0x1800088b8  jmp     short loc_1800088C4
0x1800088ba  mov     ecx, 5
0x1800088bf  int     29h; Win8: RtlFailFast(ecx)
0x1800088c1  mov     rcx, rax; void *
0x1800088c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800088c9  xor     eax, eax
0x1800088cb  mov     qword ptr [rbx+18h], 7
0x1800088d3  mov     [rbx+10h], rax
0x1800088d7  mov     [rbx], ax
0x1800088da  add     rsp, 20h
0x1800088de  pop     rbx
0x1800088df  retn
```
