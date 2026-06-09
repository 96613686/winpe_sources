# std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(void)

- ea: `0x180022be8`
- end: `0x180022c9d`
- name: `??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180025590`
- `0x18002a50b`

## callees

- `0x180004a08`
- `0x180022be8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022c14`

## pseudocode

```c
void __fastcall std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(
        void **a1)
{
  LPVOID *v1; // rbx
  LPVOID *v3; // rsi
  char *v4; // rax
  unsigned __int64 v5; // rdx
  _BYTE *v6; // rcx

  v1 = (LPVOID *)*a1;
  if ( *a1 )
  {
    v3 = (LPVOID *)a1[1];
    while ( v1 != v3 )
    {
      if ( *v1 )
      {
        CoTaskMemFree(*v1);
        *v1 = 0;
        v1[1] = 0;
      }
      v1 += 2;
    }
    v4 = (char *)*a1;
    v5 = ((_BYTE *)a1[2] - (_BYTE *)*a1) & 0xFFFFFFFFFFFFFFF0uLL;
    if ( v5 < 0x1000 )
    {
      v6 = *a1;
    }
    else
    {
      v6 = (_BYTE *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180022be8  mov     [rsp+arg_0], rbx
0x180022bed  mov     [rsp+arg_8], rsi
0x180022bf2  push    rdi
0x180022bf3  sub     rsp, 20h
0x180022bf7  mov     rbx, [rcx]
0x180022bfa  mov     rdi, rcx
0x180022bfd  test    rbx, rbx
0x180022c00  jz      loc_180022C8C
0x180022c06  mov     rsi, [rcx+8]
0x180022c0a  jmp     short loc_180022C33
0x180022c0c  mov     rcx, [rbx]; pv
0x180022c0f  test    rcx, rcx
0x180022c12  jz      short loc_180022C2F
0x180022c14  call    cs:__imp_CoTaskMemFree
0x180022c1b  nop     dword ptr [rax+rax+00h]
0x180022c20  mov     qword ptr [rbx], 0
0x180022c27  mov     qword ptr [rbx+8], 0
0x180022c2f  add     rbx, 10h
0x180022c33  cmp     rbx, rsi
0x180022c36  jnz     short loc_180022C0C
0x180022c38  mov     rax, [rdi]
0x180022c3b  mov     rdx, [rdi+10h]
0x180022c3f  sub     rdx, rax
0x180022c42  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x180022c46  cmp     rdx, 1000h
0x180022c4d  jb      short loc_180022C6D
0x180022c4f  mov     rcx, [rax-8]
0x180022c53  sub     rax, rcx
0x180022c56  sub     rax, 8
0x180022c5a  cmp     rax, 1Fh
0x180022c5e  ja      short loc_180022C66
0x180022c60  add     rdx, 27h ; '''
0x180022c64  jmp     short loc_180022C70
0x180022c66  mov     ecx, 5
0x180022c6b  int     29h; Win8: RtlFailFast(ecx)
0x180022c6d  mov     rcx, rax; void *
0x180022c70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022c75  mov     qword ptr [rdi], 0
0x180022c7c  mov     qword ptr [rdi+8], 0
0x180022c84  mov     qword ptr [rdi+10h], 0
0x180022c8c  mov     rbx, [rsp+28h+arg_0]
0x180022c91  mov     rsi, [rsp+28h+arg_8]
0x180022c96  add     rsp, 20h
0x180022c9a  pop     rdi
0x180022c9b  retn
```
