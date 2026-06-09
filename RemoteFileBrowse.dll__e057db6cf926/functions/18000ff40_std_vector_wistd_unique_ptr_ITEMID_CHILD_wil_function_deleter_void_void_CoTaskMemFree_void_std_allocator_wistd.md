# std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>,std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18000ff40`
- end: `0x18000ffd3`
- name: `??1_Reallocation_guard@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000ee58`

## callees

- `0x180002054`
- `0x18000ff40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff72`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  void **v2; // rsi
  void **i; // rbx
  void *v4; // rcx
  __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  void *v7; // rax

  if ( a1[1] )
  {
    v2 = (void **)a1[4];
    for ( i = (void **)a1[3]; i != v2; ++i )
    {
      v4 = *i;
      *i = 0;
      if ( v4 )
        CoTaskMemFree(v4);
    }
    v5 = a1[1];
    v6 = 8LL * a1[2];
    if ( v6 < 0x1000 )
    {
      v7 = (void *)a1[1];
    }
    else
    {
      v7 = *(void **)(v5 - 8);
      if ( (unsigned __int64)(v5 - (_QWORD)v7 - 8) > 0x1F )
        __fastfail(5u);
      v6 += 39LL;
    }
    operator delete(v7, v6);
  }
}

```

## disassembly

```asm
0x18000ff40  mov     [rsp+arg_0], rbx
0x18000ff45  mov     [rsp+arg_8], rsi
0x18000ff4a  push    rdi
0x18000ff4b  sub     rsp, 20h
0x18000ff4f  cmp     qword ptr [rcx+8], 0
0x18000ff54  mov     rdi, rcx
0x18000ff57  jz      short loc_18000FFC3
0x18000ff59  mov     rsi, [rcx+20h]
0x18000ff5d  mov     rbx, [rcx+18h]
0x18000ff61  jmp     short loc_18000FF7C
0x18000ff63  mov     rcx, [rbx]; pv
0x18000ff66  mov     qword ptr [rbx], 0
0x18000ff6d  test    rcx, rcx
0x18000ff70  jz      short loc_18000FF78
0x18000ff72  call    cs:__imp_CoTaskMemFree
0x18000ff78  add     rbx, 8
0x18000ff7c  cmp     rbx, rsi
0x18000ff7f  jnz     short loc_18000FF63
0x18000ff81  mov     rax, [rdi+10h]
0x18000ff85  mov     rcx, [rdi+8]
0x18000ff89  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18000ff91  cmp     rdx, 1000h
0x18000ff98  jb      short loc_18000FFB8
0x18000ff9a  mov     rax, [rcx-8]
0x18000ff9e  sub     rcx, rax
0x18000ffa1  sub     rcx, 8
0x18000ffa5  cmp     rcx, 1Fh
0x18000ffa9  ja      short loc_18000FFB1
0x18000ffab  add     rdx, 27h ; '''
0x18000ffaf  jmp     short loc_18000FFBB
0x18000ffb1  mov     ecx, 5
0x18000ffb6  int     29h; Win8: RtlFailFast(ecx)
0x18000ffb8  mov     rax, rcx
0x18000ffbb  mov     rcx, rax; void *
0x18000ffbe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ffc3  mov     rbx, [rsp+28h+arg_0]
0x18000ffc8  mov     rsi, [rsp+28h+arg_8]
0x18000ffcd  add     rsp, 20h
0x18000ffd1  pop     rdi
0x18000ffd2  retn
```
