# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)

- ea: `0x180007818`
- end: `0x1800078a6`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z`
- size: `142`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002198`
- `0x18000467c`
- `0x1800048a8`
- `0x180004af8`
- `0x180004c38`
- `0x18000593c`

## callees

- `0x180007818`
- `0x1800079e8`
- `0x18000ed9c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007872`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007872`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rcx
  _QWORD *v4; // rbx
  size_t v5; // rcx
  void *v6; // rax

  v2 = *a2 + 1;
  *a2 = v2;
  if ( v2 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_10;
  v4 = 0;
  v5 = 2 * v2;
  if ( !v5 )
    goto LABEL_9;
  if ( v5 < 0x1000 )
  {
    v4 = operator new(v5);
    goto LABEL_9;
  }
  if ( v5 + 39 < v5 )
LABEL_10:
    __scrt_throw_std_bad_array_new_length();
  v6 = operator new(v5 + 39);
  if ( !v6 )
    _invoke_watson(0, 0, 0, 0, 0);
  v4 = (_QWORD *)(((unsigned __int64)v6 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v4 - 1) = v6;
LABEL_9:
  --*a2;
  return v4;
}

```

## disassembly

```asm
0x180007818  mov     [rsp+arg_0], rbx
0x18000781d  push    rdi
0x18000781e  sub     rsp, 30h
0x180007822  mov     rcx, [rdx]
0x180007825  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000782f  inc     rcx
0x180007832  mov     rdi, rdx
0x180007835  mov     [rdx], rcx
0x180007838  cmp     rcx, rax
0x18000783b  ja      short loc_1800078A0
0x18000783d  xor     ebx, ebx
0x18000783f  add     rcx, rcx; Size
0x180007842  jz      short loc_18000788F
0x180007844  cmp     rcx, 1000h
0x18000784b  jb      short loc_180007887
0x18000784d  lea     rax, [rcx+27h]
0x180007851  cmp     rax, rcx
0x180007854  jbe     short loc_1800078A0
0x180007856  mov     rcx, rax; Size
0x180007859  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000785e  test    rax, rax
0x180007861  jnz     short loc_180007879
0x180007863  xor     r9d, r9d; LineNo
0x180007866  mov     [rsp+38h+Reserved], rbx; Reserved
0x18000786b  xor     r8d, r8d; FileName
0x18000786e  xor     edx, edx; FunctionName
0x180007870  xor     ecx, ecx; Expression
0x180007872  call    cs:__imp__invoke_watson
0x180007879  lea     rbx, [rax+27h]
0x18000787d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180007881  mov     [rbx-8], rax
0x180007885  jmp     short loc_18000788F
0x180007887  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000788c  mov     rbx, rax
0x18000788f  dec     qword ptr [rdi]
0x180007892  mov     rax, rbx
0x180007895  mov     rbx, [rsp+38h+arg_0]
0x18000789a  add     rsp, 30h
0x18000789e  pop     rdi
0x18000789f  retn
0x1800078a0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
