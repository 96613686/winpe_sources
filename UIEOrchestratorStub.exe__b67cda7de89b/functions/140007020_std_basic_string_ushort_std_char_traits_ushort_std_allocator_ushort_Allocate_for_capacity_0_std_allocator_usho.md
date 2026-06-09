# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x140007020`
- end: `0x140007090`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140007188`
- `0x1400073c0`
- `0x14000760c`
- `0x140007710`
- `0x140007ad8`
- `0x1400084c4`

## callees

- `0x1400023ec`
- `0x140007020`
- `0x14000a1a8`

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
0x140007020  push    rbx
0x140007022  sub     rsp, 20h
0x140007026  inc     qword ptr [rdx]
0x140007029  mov     rax, 7FFFFFFFFFFFFFFFh
0x140007033  mov     rcx, [rdx]
0x140007036  mov     rbx, rdx
0x140007039  cmp     rcx, rax
0x14000703c  ja      short loc_14000708A
0x14000703e  add     rcx, rcx; Size
0x140007041  jnz     short loc_140007047
0x140007043  xor     eax, eax
0x140007045  jmp     short loc_140007081
0x140007047  cmp     rcx, 1000h
0x14000704e  jb      short loc_14000707C
0x140007050  lea     rax, [rcx+27h]
0x140007054  cmp     rax, rcx
0x140007057  jbe     short loc_14000708A
0x140007059  mov     rcx, rax; Size
0x14000705c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007061  mov     rcx, rax
0x140007064  test    rax, rax
0x140007067  jnz     short loc_14000706E
0x140007069  lea     ecx, [rax+5]
0x14000706c  int     29h; Win8: RtlFailFast(ecx)
0x14000706e  add     rax, 27h ; '''
0x140007072  and     rax, 0FFFFFFFFFFFFFFE0h
0x140007076  mov     [rax-8], rcx
0x14000707a  jmp     short loc_140007081
0x14000707c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007081  dec     qword ptr [rbx]
0x140007084  add     rsp, 20h
0x140007088  pop     rbx
0x140007089  retn
0x14000708a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
