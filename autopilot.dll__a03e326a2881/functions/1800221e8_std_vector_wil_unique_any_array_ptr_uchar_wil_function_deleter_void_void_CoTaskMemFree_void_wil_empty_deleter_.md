# std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1800221e8`
- end: `0x18002227c`
- name: `??1_Reallocation_guard@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180021d84`

## callees

- `0x1800049f4`
- `0x1800221e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022213`

## pseudocode

```c
void __fastcall std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rbx
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 16 )
    {
      if ( *(_QWORD *)i )
      {
        CoTaskMemFree(*(LPVOID *)i);
        *(_QWORD *)i = 0;
        *(_QWORD *)(i + 8) = 0;
      }
    }
    v4 = a1[1];
    if ( (unsigned __int64)(16LL * a1[2]) < 0x1000 )
    {
      v5 = (void *)a1[1];
    }
    else
    {
      v5 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
}

```

## disassembly

```asm
0x1800221e8  mov     [rsp+arg_0], rbx
0x1800221ed  mov     [rsp+arg_8], rsi
0x1800221f2  push    rdi
0x1800221f3  sub     rsp, 20h
0x1800221f7  cmp     qword ptr [rcx+8], 0
0x1800221fc  mov     rdi, rcx
0x1800221ff  jz      short loc_18002226C
0x180022201  mov     rsi, [rcx+20h]
0x180022205  mov     rbx, [rcx+18h]
0x180022209  jmp     short loc_18002222C
0x18002220b  mov     rcx, [rbx]; pv
0x18002220e  test    rcx, rcx
0x180022211  jz      short loc_180022228
0x180022213  call    cs:__imp_CoTaskMemFree
0x180022219  mov     qword ptr [rbx], 0
0x180022220  mov     qword ptr [rbx+8], 0
0x180022228  add     rbx, 10h
0x18002222c  cmp     rbx, rsi
0x18002222f  jnz     short loc_18002220B
0x180022231  mov     rdx, [rdi+10h]
0x180022235  mov     rax, [rdi+8]
0x180022239  shl     rdx, 4
0x18002223d  cmp     rdx, 1000h
0x180022244  jb      short loc_180022264
0x180022246  mov     rcx, [rax-8]
0x18002224a  sub     rax, rcx
0x18002224d  sub     rax, 8
0x180022251  cmp     rax, 1Fh
0x180022255  ja      short loc_18002225D
0x180022257  add     rdx, 27h ; '''
0x18002225b  jmp     short loc_180022267
0x18002225d  mov     ecx, 5
0x180022262  int     29h; Win8: RtlFailFast(ecx)
0x180022264  mov     rcx, rax; Block
0x180022267  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002226c  mov     rbx, [rsp+28h+arg_0]
0x180022271  mov     rsi, [rsp+28h+arg_8]
0x180022276  add     rsp, 20h
0x18002227a  pop     rdi
0x18002227b  retn
```
