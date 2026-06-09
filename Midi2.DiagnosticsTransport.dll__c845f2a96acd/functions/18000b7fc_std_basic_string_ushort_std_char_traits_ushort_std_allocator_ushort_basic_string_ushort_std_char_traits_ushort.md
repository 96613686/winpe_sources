# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000b7fc`
- end: `0x18000b860`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b8d0`
- `0x18000cb4c`
- `0x18000ccf8`
- `0x18000d0b4`
- `0x18000d31c`
- `0x18000f1e4`
- `0x180010b70`
- `0x180011630`
- `0x1800117e8`
- `0x1800119a0`
- `0x18001225b`
- `0x18001226d`
- `0x180012299`
- `0x1800122c5`
- `0x1800122f1`
- `0x18001231d`
- `0x180012349`
- `0x18001235b`
- `0x18001236d`
- `0x18001237f`
- `0x180012391`
- `0x1800123a3`
- `0x1800123c7`
- `0x1800123d9`
- `0x1800123eb`
- `0x18001240f`
- `0x180012421`
- `0x180012445`

## callees

- `0x1800033f4`
- `0x18000b7fc`

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
0x18000b7fc  push    rbx
0x18000b7fe  sub     rsp, 20h
0x18000b802  mov     rdx, [rcx+18h]
0x18000b806  mov     rbx, rcx
0x18000b809  cmp     rdx, 7
0x18000b80d  jbe     short loc_18000B849
0x18000b80f  mov     rax, [rcx]
0x18000b812  lea     rdx, ds:2[rdx*2]
0x18000b81a  cmp     rdx, 1000h
0x18000b821  jb      short loc_18000B841
0x18000b823  mov     rcx, [rax-8]
0x18000b827  sub     rax, rcx
0x18000b82a  sub     rax, 8
0x18000b82e  cmp     rax, 1Fh
0x18000b832  ja      short loc_18000B83A
0x18000b834  add     rdx, 27h ; '''
0x18000b838  jmp     short loc_18000B844
0x18000b83a  mov     ecx, 5
0x18000b83f  int     29h; Win8: RtlFailFast(ecx)
0x18000b841  mov     rcx, rax; Block
0x18000b844  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b849  xor     eax, eax
0x18000b84b  mov     qword ptr [rbx+18h], 7
0x18000b853  mov     [rbx+10h], rax
0x18000b857  mov     [rbx], ax
0x18000b85a  add     rsp, 20h
0x18000b85e  pop     rbx
0x18000b85f  retn
```
