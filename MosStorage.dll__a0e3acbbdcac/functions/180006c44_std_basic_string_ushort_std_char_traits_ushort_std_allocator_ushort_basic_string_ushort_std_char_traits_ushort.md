# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180006c44`
- end: `0x180006ca8`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `17`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000733c`
- `0x18000771c`
- `0x180008550`
- `0x180008920`
- `0x180008ac0`
- `0x180009590`
- `0x180009650`
- `0x180009790`
- `0x18000d6c4`
- `0x18000d8b8`
- `0x18000ed58`
- `0x18000ed6a`
- `0x18000edd8`
- `0x18000ee32`
- `0x18000f006`
- `0x18000f018`
- `0x18000f04e`

## callees

- `0x18000207c`
- `0x180006c44`

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
0x180006c44  push    rbx
0x180006c46  sub     rsp, 20h
0x180006c4a  mov     rdx, [rcx+18h]
0x180006c4e  mov     rbx, rcx
0x180006c51  cmp     rdx, 7
0x180006c55  jbe     short loc_180006C91
0x180006c57  mov     rax, [rcx]
0x180006c5a  lea     rdx, ds:2[rdx*2]
0x180006c62  cmp     rdx, 1000h
0x180006c69  jb      short loc_180006C89
0x180006c6b  mov     rcx, [rax-8]
0x180006c6f  sub     rax, rcx
0x180006c72  sub     rax, 8
0x180006c76  cmp     rax, 1Fh
0x180006c7a  ja      short loc_180006C82
0x180006c7c  add     rdx, 27h ; '''
0x180006c80  jmp     short loc_180006C8C
0x180006c82  mov     ecx, 5
0x180006c87  int     29h; Win8: RtlFailFast(ecx)
0x180006c89  mov     rcx, rax; Block
0x180006c8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006c91  xor     eax, eax
0x180006c93  mov     qword ptr [rbx+18h], 7
0x180006c9b  mov     [rbx+10h], rax
0x180006c9f  mov     [rbx], ax
0x180006ca2  add     rsp, 20h
0x180006ca6  pop     rbx
0x180006ca7  retn
```
