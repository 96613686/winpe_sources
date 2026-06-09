# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x1800077d8`
- end: `0x180007848`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180007940`
- `0x180007b54`
- `0x180007da0`
- `0x180007ea4`
- `0x18000826c`
- `0x180008c00`
- `0x18000b4e8`

## callees

- `0x18000260c`
- `0x1800077d8`
- `0x18000b278`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, _QWORD *a2)
{
  size_t v3; // rcx
  _QWORD *result; // rax
  void *v5; // rax
  void *v6; // rcx

  if ( ++*a2 > 0x7FFFFFFFFFFFFFFFuLL )
    goto LABEL_11;
  v3 = 2LL * *a2;
  if ( !v3 )
  {
    result = 0;
    goto LABEL_10;
  }
  if ( v3 < 0x1000 )
  {
    result = operator new(v3);
    goto LABEL_10;
  }
  if ( v3 + 39 < v3 )
LABEL_11:
    __scrt_throw_std_bad_array_new_length();
  v5 = operator new(v3 + 39);
  v6 = v5;
  if ( !v5 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v6;
LABEL_10:
  --*a2;
  return result;
}

```

## disassembly

```asm
0x1800077d8  push    rbx
0x1800077da  sub     rsp, 20h
0x1800077de  inc     qword ptr [rdx]
0x1800077e1  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800077eb  mov     rcx, [rdx]
0x1800077ee  mov     rbx, rdx
0x1800077f1  cmp     rcx, rax
0x1800077f4  ja      short loc_180007842
0x1800077f6  add     rcx, rcx; Size
0x1800077f9  jnz     short loc_1800077FF
0x1800077fb  xor     eax, eax
0x1800077fd  jmp     short loc_180007839
0x1800077ff  cmp     rcx, 1000h
0x180007806  jb      short loc_180007834
0x180007808  lea     rax, [rcx+27h]
0x18000780c  cmp     rax, rcx
0x18000780f  jbe     short loc_180007842
0x180007811  mov     rcx, rax; Size
0x180007814  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007819  mov     rcx, rax
0x18000781c  test    rax, rax
0x18000781f  jnz     short loc_180007826
0x180007821  lea     ecx, [rax+5]
0x180007824  int     29h; Win8: RtlFailFast(ecx)
0x180007826  add     rax, 27h ; '''
0x18000782a  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000782e  mov     [rax-8], rcx
0x180007832  jmp     short loc_180007839
0x180007834  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007839  dec     qword ptr [rbx]
0x18000783c  add     rsp, 20h
0x180007840  pop     rbx
0x180007841  retn
0x180007842  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
