# std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180022ca4`
- end: `0x180022d3f`
- name: `??1_Reallocation_guard@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180022828`

## callees

- `0x180004a08`
- `0x180022ca4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022ccf`

## pseudocode

```c
void __fastcall std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rdx
  void *v6; // rcx

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
    v5 = 16LL * a1[2];
    if ( v5 < 0x1000 )
    {
      v6 = (void *)a1[1];
    }
    else
    {
      v6 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
  }
}

```

## disassembly

```asm
0x180022ca4  mov     [rsp+arg_0], rbx
0x180022ca9  mov     [rsp+arg_8], rsi
0x180022cae  push    rdi
0x180022caf  sub     rsp, 20h
0x180022cb3  cmp     qword ptr [rcx+8], 0
0x180022cb8  mov     rdi, rcx
0x180022cbb  jz      short loc_180022D2E
0x180022cbd  mov     rsi, [rcx+20h]
0x180022cc1  mov     rbx, [rcx+18h]
0x180022cc5  jmp     short loc_180022CEE
0x180022cc7  mov     rcx, [rbx]; pv
0x180022cca  test    rcx, rcx
0x180022ccd  jz      short loc_180022CEA
0x180022ccf  call    cs:__imp_CoTaskMemFree
0x180022cd6  nop     dword ptr [rax+rax+00h]
0x180022cdb  mov     qword ptr [rbx], 0
0x180022ce2  mov     qword ptr [rbx+8], 0
0x180022cea  add     rbx, 10h
0x180022cee  cmp     rbx, rsi
0x180022cf1  jnz     short loc_180022CC7
0x180022cf3  mov     rdx, [rdi+10h]
0x180022cf7  mov     rax, [rdi+8]
0x180022cfb  shl     rdx, 4; unsigned __int64
0x180022cff  cmp     rdx, 1000h
0x180022d06  jb      short loc_180022D26
0x180022d08  mov     rcx, [rax-8]
0x180022d0c  sub     rax, rcx
0x180022d0f  sub     rax, 8
0x180022d13  cmp     rax, 1Fh
0x180022d17  ja      short loc_180022D1F
0x180022d19  add     rdx, 27h ; '''
0x180022d1d  jmp     short loc_180022D29
0x180022d1f  mov     ecx, 5
0x180022d24  int     29h; Win8: RtlFailFast(ecx)
0x180022d26  mov     rcx, rax; void *
0x180022d29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022d2e  mov     rbx, [rsp+28h+arg_0]
0x180022d33  mov     rsi, [rsp+28h+arg_8]
0x180022d38  add     rsp, 20h
0x180022d3c  pop     rdi
0x180022d3d  retn
```
