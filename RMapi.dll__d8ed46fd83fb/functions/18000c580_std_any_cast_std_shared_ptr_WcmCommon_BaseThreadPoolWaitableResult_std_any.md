# std::any_cast<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::any &)

- ea: `0x18000c580`
- end: `0x18000c5f2`
- name: `??$any_cast@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@std@@YA?AV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@0@AEAVany@0@@Z`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c31c`
- `0x18000c400`

## callees

- `0x18000c580`
- `0x180022aac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c5aa`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000c5aa`

## pseudocode

```c
_QWORD *__fastcall std::any_cast<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rax

  if ( !a2
    || (a2[7] & 0xFFFFFFFFFFFFFFFCuLL) == 0
    || (unsigned int)__std_type_info_compare((a2[7] & 0xFFFFFFFFFFFFFFFCuLL) + 8, &qword_180037708) )
  {
    std::_Throw_bad_any_cast();
  }
  v4 = a2[1];
  *a1 = 0;
  a1[1] = 0;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x18000c580  mov     [rsp+arg_0], rbx
0x18000c585  push    rdi
0x18000c586  sub     rsp, 30h
0x18000c58a  mov     rdi, rdx
0x18000c58d  mov     rbx, rcx
0x18000c590  test    rdx, rdx
0x18000c593  jz      short loc_18000C5EC
0x18000c595  mov     rcx, [rdx+38h]
0x18000c599  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000c59d  jz      short loc_18000C5EC
0x18000c59f  add     rcx, 8
0x18000c5a3  lea     rdx, qword_180037708
0x18000c5aa  call    cs:__imp___std_type_info_compare
0x18000c5b0  test    eax, eax
0x18000c5b2  jnz     short loc_18000C5EC
0x18000c5b4  mov     rax, [rdi+8]
0x18000c5b8  mov     qword ptr [rbx], 0
0x18000c5bf  mov     qword ptr [rbx+8], 0
0x18000c5c7  test    rax, rax
0x18000c5ca  jz      short loc_18000C5D0
0x18000c5cc  lock inc dword ptr [rax+8]
0x18000c5d0  mov     rax, [rdi]
0x18000c5d3  mov     [rbx], rax
0x18000c5d6  mov     rax, [rdi+8]
0x18000c5da  mov     [rbx+8], rax
0x18000c5de  mov     rax, rbx
0x18000c5e1  mov     rbx, [rsp+38h+arg_0]
0x18000c5e6  add     rsp, 30h
0x18000c5ea  pop     rdi
0x18000c5eb  retn
0x18000c5ec  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
```
