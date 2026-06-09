# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140008278`
- end: `0x1400082dc`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006c84`
- `0x140007210`
- `0x140007778`
- `0x1400080e0`
- `0x140008150`
- `0x140008308`
- `0x14000842c`
- `0x14000b248`
- `0x14000b5b4`
- `0x14000bf30`
- `0x14000eb60`
- `0x140011b3b`
- `0x140011b9d`
- `0x140011bb3`
- `0x140011bc5`
- `0x140011f03`
- `0x140011f15`
- `0x140011f85`

## callees

- `0x140001934`
- `0x140008278`

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
0x140008278  push    rbx
0x14000827a  sub     rsp, 20h
0x14000827e  mov     rdx, [rcx+18h]
0x140008282  mov     rbx, rcx
0x140008285  cmp     rdx, 7
0x140008289  jbe     short loc_1400082C5
0x14000828b  mov     rax, [rcx]
0x14000828e  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x140008296  cmp     rdx, 1000h
0x14000829d  jb      short loc_1400082BD
0x14000829f  mov     rcx, [rax-8]
0x1400082a3  sub     rax, rcx
0x1400082a6  sub     rax, 8
0x1400082aa  cmp     rax, 1Fh
0x1400082ae  ja      short loc_1400082B6
0x1400082b0  add     rdx, 27h ; '''
0x1400082b4  jmp     short loc_1400082C0
0x1400082b6  mov     ecx, 5
0x1400082bb  int     29h; Win8: RtlFailFast(ecx)
0x1400082bd  mov     rcx, rax; void *
0x1400082c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400082c5  xor     eax, eax
0x1400082c7  mov     qword ptr [rbx+18h], 7
0x1400082cf  mov     [rbx+10h], rax
0x1400082d3  mov     [rbx], ax
0x1400082d6  add     rsp, 20h
0x1400082da  pop     rbx
0x1400082db  retn
```
