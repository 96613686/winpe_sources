# wil::make_unique_cotaskmem_nothrow<void * [0]>(unsigned __int64)

- ea: `0x18000701c`
- end: `0x18000707e`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@PEAX@wil@@YA?AV?$unique_ptr@$$BY0A@PEAXU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006f64`

## callees

- `0x18000701c`
- `0x180009be4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000704e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000704e`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<void * [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        const char *a4)
{
  __int64 v5; // rdi
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)a2, a3, a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(8 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[v5];
    while ( v6 != v7 )
      *v6++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000701c  mov     [rsp+arg_0], rbx
0x180007021  push    rdi
0x180007022  sub     rsp, 20h
0x180007026  mov     rax, 1FFFFFFFFFFFFFFFh
0x180007030  mov     rbx, rcx
0x180007033  cmp     rdx, rax
0x180007036  jbe     short loc_180007043
0x180007038  mov     rcx, [rsp+28h]; this
0x18000703d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180007043  lea     rdi, ds:0[rdx*8]
0x18000704b  mov     rcx, rdi; cb
0x18000704e  call    cs:__imp_CoTaskMemAlloc
0x180007054  mov     [rbx], rax
0x180007057  test    rax, rax
0x18000705a  jz      short loc_180007070
0x18000705c  lea     rcx, [rdi+rax]
0x180007060  jmp     short loc_18000706B
0x180007062  xor     edx, edx
0x180007064  mov     [rax], rdx
0x180007067  add     rax, 8
0x18000706b  cmp     rax, rcx
0x18000706e  jnz     short loc_180007062
0x180007070  mov     rax, rbx
0x180007073  mov     rbx, [rsp+28h+arg_0]
0x180007078  add     rsp, 20h
0x18000707c  pop     rdi
0x18000707d  retn
```
