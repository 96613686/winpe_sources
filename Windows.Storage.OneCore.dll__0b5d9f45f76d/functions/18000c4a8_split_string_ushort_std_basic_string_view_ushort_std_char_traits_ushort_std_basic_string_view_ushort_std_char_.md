# split_string<ushort,std::basic_string_view<ushort,std::char_traits<ushort>> (*)(std::basic_string_view<ushort,std::char_traits<ushort>>)>(std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string_view<ushort,std::char_traits<ushort>> (*)(std::basic_string_view<ushort,std::char_traits<ushort>>),bool)

- ea: `0x18000c4a8`
- end: `0x18000c530`
- name: `??$split_string@GP6A?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@Z@@YA?AU?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@P6A?AV32@0@Z_N@Z`
- size: `136`
- prototype: `__int64 *__fastcall(__int64 *, _OWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e01c`

## callees

- `0x18000adb4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000c511`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000c511`

## pseudocode

```c
__int64 *__fastcall split_string<unsigned short,std::basic_string_view<unsigned short> (*)(std::basic_string_view<unsigned short>)>(
        __int64 *a1,
        _OWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx

  v4 = std::_Allocate<16,std::_Default_allocate_traits>(240);
  v5 = v4 + 32;
  *(_OWORD *)(v4 + 200) = *a2;
  *(_QWORD *)(v4 + 216) = nt_path_segment_tokenizer<unsigned short>::match_nt_path_delim;
  *(_BYTE *)(v4 + 224) = 0;
  *(_QWORD *)(v4 + 32) = split_string__ResumeCoro_1_unsigned_short_std::basic_string_view_unsigned_short_std::char_traits_unsigned_short_______cdecl___std::basic_string_view_unsigned_short_std::char_traits_unsigned_short_____;
  *(_DWORD *)(v4 + 40) = 65538;
  *(_QWORD *)v4 = 0;
  *(_QWORD *)(v4 + 8) = 0;
  *(_QWORD *)(v4 + 16) = 0;
  __ExceptionPtrCreate((void *)(v4 + 8));
  *a1 = v5;
  *(_BYTE *)(v5 + 160) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000c4a8  mov     [rsp+arg_8], rbx
0x18000c4ad  push    rbp
0x18000c4ae  push    rsi
0x18000c4af  push    rdi
0x18000c4b0  sub     rsp, 30h
0x18000c4b4  mov     rsi, rdx
0x18000c4b7  mov     rdi, rcx
0x18000c4ba  mov     ebp, 0A0h
0x18000c4bf  lea     rcx, [rbp+50h]
0x18000c4c3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000c4c8  mov     [rsp+48h+arg_10], rax
0x18000c4cd  lea     rbx, [rax+20h]
0x18000c4d1  mov     [rsp+48h+arg_10], rbx
0x18000c4d6  movups  xmm0, xmmword ptr [rsi]
0x18000c4d9  movdqu  xmmword ptr [rbx+rbp+8], xmm0
0x18000c4df  lea     rax, ?match_nt_path_delim@?$nt_path_segment_tokenizer@G@@SA@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; nt_path_segment_tokenizer<ushort>::match_nt_path_delim(std::basic_string_view<ushort>)
0x18000c4e6  mov     [rbx+rbp+18h], rax
0x18000c4eb  xor     edx, edx
0x18000c4ed  mov     [rbx+rbp+20h], dl
0x18000c4f1  lea     rax, split_string$_ResumeCoro$1_unsigned_short_std__basic_string_view_unsigned_short_std__char_traits_unsigned_short_______cdecl___std__basic_string_view_unsigned_short_std__char_traits_unsigned_short_____
0x18000c4f8  mov     [rbx], rax
0x18000c4fb  mov     dword ptr [rbx+8], 10002h
0x18000c502  mov     [rbx-20h], rdx
0x18000c506  lea     rcx, [rbx-18h]
0x18000c50a  mov     [rcx], rdx
0x18000c50d  mov     [rcx+8], rdx
0x18000c511  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000c517  nop
0x18000c518  mov     [rdi], rbx
0x18000c51b  xor     eax, eax
0x18000c51d  mov     [rbx+rbp], al
0x18000c520  mov     rax, rdi
0x18000c523  mov     rbx, [rsp+48h+arg_8]
0x18000c528  add     rsp, 30h
0x18000c52c  pop     rdi
0x18000c52d  pop     rsi
0x18000c52e  pop     rbp
0x18000c52f  retn
```
