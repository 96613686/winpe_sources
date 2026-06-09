# std::_Ref_count_resource<void *,void * (*)(void *)>::_Get_deleter(type_info const &)

- ea: `0x18001f130`
- end: `0x18001f15c`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAXP6APEAXPEAX@Z@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001f130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001f144`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001f144`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<void *,void * (*)(void *)>::_Get_deleter(__int64 a1, __int64 a2)
{
  if ( (unsigned int)__std_type_info_compare(a2 + 8, &qword_180036C28) )
    return 0;
  else
    return a1 + 16;
}

```

## disassembly

```asm
0x18001f130  push    rbx
0x18001f132  sub     rsp, 20h
0x18001f136  mov     rbx, rcx
0x18001f139  lea     rcx, [rdx+8]
0x18001f13d  lea     rdx, qword_180036C28
0x18001f144  call    cs:__imp___std_type_info_compare
0x18001f14a  test    eax, eax
0x18001f14c  jnz     short loc_18001F154
0x18001f14e  lea     rax, [rbx+10h]
0x18001f152  jmp     short loc_18001F156
0x18001f154  xor     eax, eax
0x18001f156  add     rsp, 20h
0x18001f15a  pop     rbx
0x18001f15b  retn
```
