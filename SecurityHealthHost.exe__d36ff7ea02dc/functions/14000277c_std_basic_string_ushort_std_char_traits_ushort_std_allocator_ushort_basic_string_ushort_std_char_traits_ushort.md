# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x14000277c`
- end: `0x1400027e0`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140003188`
- `0x14000c688`
- `0x14000d38c`
- `0x14000fb90`
- `0x14000fba2`
- `0x14000fd7e`
- `0x14000fdd6`

## callees

- `0x140001614`
- `0x14000277c`

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
0x14000277c  push    rbx
0x14000277e  sub     rsp, 20h
0x140002782  mov     rdx, [rcx+18h]
0x140002786  mov     rbx, rcx
0x140002789  cmp     rdx, 7
0x14000278d  jbe     short loc_1400027C9
0x14000278f  mov     rax, [rcx]
0x140002792  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x14000279a  cmp     rdx, 1000h
0x1400027a1  jb      short loc_1400027C1
0x1400027a3  mov     rcx, [rax-8]
0x1400027a7  sub     rax, rcx
0x1400027aa  sub     rax, 8
0x1400027ae  cmp     rax, 1Fh
0x1400027b2  ja      short loc_1400027BA
0x1400027b4  add     rdx, 27h ; '''
0x1400027b8  jmp     short loc_1400027C4
0x1400027ba  mov     ecx, 5
0x1400027bf  int     29h; Win8: RtlFailFast(ecx)
0x1400027c1  mov     rcx, rax; void *
0x1400027c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400027c9  xor     eax, eax
0x1400027cb  mov     qword ptr [rbx+18h], 7
0x1400027d3  mov     [rbx+10h], rax
0x1400027d7  mov     [rbx], ax
0x1400027da  add     rsp, 20h
0x1400027de  pop     rbx
0x1400027df  retn
```
