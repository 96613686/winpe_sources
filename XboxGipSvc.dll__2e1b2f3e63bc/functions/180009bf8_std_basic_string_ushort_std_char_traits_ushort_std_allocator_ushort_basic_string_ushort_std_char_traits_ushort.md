# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180009bf8`
- end: `0x180009c5c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009508`
- `0x180009c64`
- `0x180009da8`
- `0x18000ae98`
- `0x18000ed8c`
- `0x18000ee70`
- `0x18000ef14`
- `0x180010768`
- `0x1800111fc`
- `0x180011800`
- `0x1800118e8`

## callees

- `0x180001b6c`
- `0x180009bf8`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  const struct std::nothrow_t *v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = (const struct std::nothrow_t *)(2 * v1 + 2);
    if ( (unsigned __int64)v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
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
0x180009bf8  push    rbx
0x180009bfa  sub     rsp, 20h
0x180009bfe  mov     rdx, [rcx+18h]
0x180009c02  mov     rbx, rcx
0x180009c05  cmp     rdx, 7
0x180009c09  jbe     short loc_180009C45
0x180009c0b  mov     rax, [rcx]
0x180009c0e  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180009c16  cmp     rdx, 1000h
0x180009c1d  jb      short loc_180009C3D
0x180009c1f  mov     rcx, [rax-8]
0x180009c23  sub     rax, rcx
0x180009c26  sub     rax, 8
0x180009c2a  cmp     rax, 1Fh
0x180009c2e  ja      short loc_180009C36
0x180009c30  add     rdx, 27h ; '''
0x180009c34  jmp     short loc_180009C40
0x180009c36  mov     ecx, 5
0x180009c3b  int     29h; Win8: RtlFailFast(ecx)
0x180009c3d  mov     rcx, rax; void *
0x180009c40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009c45  xor     eax, eax
0x180009c47  mov     qword ptr [rbx+18h], 7
0x180009c4f  mov     [rbx+10h], rax
0x180009c53  mov     [rbx], ax
0x180009c56  add     rsp, 20h
0x180009c5a  pop     rbx
0x180009c5b  retn
```
