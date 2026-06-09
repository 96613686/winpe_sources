# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)

- ea: `0x14000eb3c`
- end: `0x14000ebac`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ebb4`
- `0x14000ef1c`
- `0x14000f014`
- `0x14000f194`
- `0x14000f544`
- `0x14001071c`

## callees

- `0x14000892c`
- `0x14000d918`
- `0x14000eb3c`

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
0x14000eb3c  push    rbx
0x14000eb3e  sub     rsp, 20h
0x14000eb42  inc     qword ptr [rdx]
0x14000eb45  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000eb4f  mov     rcx, [rdx]
0x14000eb52  mov     rbx, rdx
0x14000eb55  cmp     rcx, rax
0x14000eb58  ja      short loc_14000EBA6
0x14000eb5a  add     rcx, rcx; Size
0x14000eb5d  jnz     short loc_14000EB63
0x14000eb5f  xor     eax, eax
0x14000eb61  jmp     short loc_14000EB9D
0x14000eb63  cmp     rcx, 1000h
0x14000eb6a  jb      short loc_14000EB98
0x14000eb6c  lea     rax, [rcx+27h]
0x14000eb70  cmp     rax, rcx
0x14000eb73  jbe     short loc_14000EBA6
0x14000eb75  mov     rcx, rax; Size
0x14000eb78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000eb7d  mov     rcx, rax
0x14000eb80  test    rax, rax
0x14000eb83  jnz     short loc_14000EB8A
0x14000eb85  lea     ecx, [rax+5]
0x14000eb88  int     29h; Win8: RtlFailFast(ecx)
0x14000eb8a  add     rax, 27h ; '''
0x14000eb8e  and     rax, 0FFFFFFFFFFFFFFE0h
0x14000eb92  mov     [rax-8], rcx
0x14000eb96  jmp     short loc_14000EB9D
0x14000eb98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000eb9d  dec     qword ptr [rbx]
0x14000eba0  add     rsp, 20h
0x14000eba4  pop     rbx
0x14000eba5  retn
0x14000eba6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
