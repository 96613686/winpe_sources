# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000591c`
- end: `0x180005980`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `56`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005a04`
- `0x180005f70`
- `0x180007864`
- `0x180007b30`
- `0x180007e50`
- `0x180008800`
- `0x1800088e4`
- `0x180008ae0`
- `0x180008d90`
- `0x180009c2c`
- `0x180009c88`
- `0x18000a0e8`
- `0x18000b2f4`
- `0x18000ba9c`
- `0x18000cfc8`
- `0x18000d090`
- `0x18000d140`
- `0x18000d2d0`
- `0x18000da44`
- `0x18000dbd0`
- `0x18000fd8c`
- `0x180010e20`
- `0x1800139c8`
- `0x180013a48`
- `0x180013b1c`
- `0x180013bb0`
- `0x180014080`
- `0x180014520`
- `0x180014570`
- `0x180014910`
- `0x180015660`
- `0x180015e20`
- `0x180016600`
- `0x180016830`
- `0x180016f04`
- `0x1800178af`
- `0x1800178c1`
- `0x180017972`
- `0x18001799d`
- `0x1800179af`
- `0x180017a00`
- `0x180017a35`
- `0x180017bbf`
- `0x180017c2b`
- `0x180017f49`
- `0x180017f78`
- `0x1800186c9`
- `0x18001872a`
- `0x18001874e`
- `0x180018760`

## callees

- `0x180002054`
- `0x18000591c`

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
0x18000591c  push    rbx
0x18000591e  sub     rsp, 20h
0x180005922  mov     rdx, [rcx+18h]
0x180005926  mov     rbx, rcx
0x180005929  cmp     rdx, 7
0x18000592d  jbe     short loc_180005969
0x18000592f  mov     rax, [rcx]
0x180005932  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000593a  cmp     rdx, 1000h
0x180005941  jb      short loc_180005961
0x180005943  mov     rcx, [rax-8]
0x180005947  sub     rax, rcx
0x18000594a  sub     rax, 8
0x18000594e  cmp     rax, 1Fh
0x180005952  ja      short loc_18000595A
0x180005954  add     rdx, 27h ; '''
0x180005958  jmp     short loc_180005964
0x18000595a  mov     ecx, 5
0x18000595f  int     29h; Win8: RtlFailFast(ecx)
0x180005961  mov     rcx, rax; void *
0x180005964  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005969  xor     eax, eax
0x18000596b  mov     qword ptr [rbx+18h], 7
0x180005973  mov     [rbx+10h], rax
0x180005977  mov     [rbx], ax
0x18000597a  add     rsp, 20h
0x18000597e  pop     rbx
0x18000597f  retn
```
