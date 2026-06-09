# wil::make_unique_cotaskmem_nothrow<ulong [0]>(unsigned __int64)

- ea: `0x180006fb4`
- end: `0x180007015`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@K@wil@@YA?AV?$unique_ptr@$$BY0A@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006f14`

## callees

- `0x180006fb4`
- `0x180009be4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fe6`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<unsigned long [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned int a3,
        const char *a4)
{
  __int64 v5; // rdi
  _DWORD *v6; // rax
  _DWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x3FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)a2, a3, a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(4 * a2);
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
0x180006fb4  mov     [rsp+arg_0], rbx
0x180006fb9  push    rdi
0x180006fba  sub     rsp, 20h
0x180006fbe  mov     rax, 3FFFFFFFFFFFFFFFh
0x180006fc8  mov     rbx, rcx
0x180006fcb  cmp     rdx, rax
0x180006fce  jbe     short loc_180006FDB
0x180006fd0  mov     rcx, [rsp+28h]; this
0x180006fd5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006fdb  lea     rdi, ds:0[rdx*4]
0x180006fe3  mov     rcx, rdi; cb
0x180006fe6  call    cs:__imp_CoTaskMemAlloc
0x180006fec  mov     [rbx], rax
0x180006fef  test    rax, rax
0x180006ff2  jz      short loc_180007007
0x180006ff4  lea     rcx, [rdi+rax]
0x180006ff8  jmp     short loc_180007002
0x180006ffa  xor     edx, edx
0x180006ffc  mov     [rax], edx
0x180006ffe  add     rax, 4
0x180007002  cmp     rax, rcx
0x180007005  jnz     short loc_180006FFA
0x180007007  mov     rax, rbx
0x18000700a  mov     rbx, [rsp+28h+arg_0]
0x18000700f  add     rsp, 20h
0x180007013  pop     rdi
0x180007014  retn
```
