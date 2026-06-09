# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x140002390`
- end: `0x140002400`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140002408`
- `0x140002550`
- `0x14000c360`
- `0x14000c4a0`
- `0x14000d12c`

## callees

- `0x14000164c`
- `0x140002390`
- `0x140002e80`

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
0x140002390  push    rbx
0x140002392  sub     rsp, 20h
0x140002396  inc     qword ptr [rdx]
0x140002399  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400023a3  mov     rcx, [rdx]
0x1400023a6  mov     rbx, rdx
0x1400023a9  cmp     rcx, rax
0x1400023ac  ja      short loc_1400023FA
0x1400023ae  add     rcx, rcx; Size
0x1400023b1  jnz     short loc_1400023B7
0x1400023b3  xor     eax, eax
0x1400023b5  jmp     short loc_1400023F1
0x1400023b7  cmp     rcx, 1000h
0x1400023be  jb      short loc_1400023EC
0x1400023c0  lea     rax, [rcx+27h]
0x1400023c4  cmp     rax, rcx
0x1400023c7  jbe     short loc_1400023FA
0x1400023c9  mov     rcx, rax; Size
0x1400023cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400023d1  mov     rcx, rax
0x1400023d4  test    rax, rax
0x1400023d7  jnz     short loc_1400023DE
0x1400023d9  lea     ecx, [rax+5]
0x1400023dc  int     29h; Win8: RtlFailFast(ecx)
0x1400023de  add     rax, 27h ; '''
0x1400023e2  and     rax, 0FFFFFFFFFFFFFFE0h
0x1400023e6  mov     [rax-8], rcx
0x1400023ea  jmp     short loc_1400023F1
0x1400023ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400023f1  dec     qword ptr [rbx]
0x1400023f4  add     rsp, 20h
0x1400023f8  pop     rbx
0x1400023f9  retn
0x1400023fa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
