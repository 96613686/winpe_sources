# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1800076b4`
- end: `0x180007718`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007758`
- `0x180007768`
- `0x180007918`
- `0x18000a5f0`
- `0x180011b90`
- `0x1800127a8`
- `0x180013528`
- `0x180013720`
- `0x180013c0a`
- `0x180013da9`
- `0x180013f48`
- `0x180013f7e`
- `0x180013fb4`
- `0x180013fd8`

## callees

- `0x180002014`
- `0x1800076b4`

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
0x1800076b4  push    rbx
0x1800076b6  sub     rsp, 20h
0x1800076ba  mov     rdx, [rcx+18h]
0x1800076be  mov     rbx, rcx
0x1800076c1  cmp     rdx, 7
0x1800076c5  jbe     short loc_180007701
0x1800076c7  mov     rax, [rcx]
0x1800076ca  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x1800076d2  cmp     rdx, 1000h
0x1800076d9  jb      short loc_1800076F9
0x1800076db  mov     rcx, [rax-8]
0x1800076df  sub     rax, rcx
0x1800076e2  sub     rax, 8
0x1800076e6  cmp     rax, 1Fh
0x1800076ea  ja      short loc_1800076F2
0x1800076ec  add     rdx, 27h ; '''
0x1800076f0  jmp     short loc_1800076FC
0x1800076f2  mov     ecx, 5
0x1800076f7  int     29h; Win8: RtlFailFast(ecx)
0x1800076f9  mov     rcx, rax; void *
0x1800076fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007701  xor     eax, eax
0x180007703  mov     qword ptr [rbx+18h], 7
0x18000770b  mov     [rbx+10h], rax
0x18000770f  mov     [rbx], ax
0x180007712  add     rsp, 20h
0x180007716  pop     rbx
0x180007717  retn
```
