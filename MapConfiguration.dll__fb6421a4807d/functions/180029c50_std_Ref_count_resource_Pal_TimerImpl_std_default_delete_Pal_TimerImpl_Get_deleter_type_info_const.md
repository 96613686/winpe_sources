# std::_Ref_count_resource<Pal::TimerImpl *,std::default_delete<Pal::TimerImpl>>::_Get_deleter(type_info const &)

- ea: `0x180029c50`
- end: `0x180029c7c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAVTimerImpl@Pal@@U?$default_delete@VTimerImpl@Pal@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180029c50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180029c64`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180029c64`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<Pal::TimerImpl *,std::default_delete<Pal::TimerImpl>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180079618) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x180029c50  push    rbx
0x180029c52  sub     rsp, 20h
0x180029c56  mov     rbx, rcx
0x180029c59  lea     rcx, [rdx+8]
0x180029c5d  lea     rdx, qword_180079618
0x180029c64  call    cs:__imp___std_type_info_compare
0x180029c6a  test    eax, eax
0x180029c6c  jnz     short loc_180029C74
0x180029c6e  lea     rax, [rbx+10h]
0x180029c72  jmp     short loc_180029C76
0x180029c74  xor     eax, eax
0x180029c76  add     rsp, 20h
0x180029c7a  pop     rbx
0x180029c7b  retn
```
