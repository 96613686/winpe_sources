# std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>::~vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>(void)

- ea: `0x180022134`
- end: `0x1800221e2`
- name: `??1?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800248b0`
- `0x180029221`

## callees

- `0x1800049f4`
- `0x180022134`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022160`

## pseudocode

```c
void __fastcall std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::~vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(
        void **a1)
{
  LPVOID *v1; // rbx
  LPVOID *v3; // rsi
  char *v4; // rax
  _BYTE *v5; // rcx

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
    if ( (((_BYTE *)a1[2] - (_BYTE *)*a1) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (_BYTE *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180022134  mov     [rsp+arg_0], rbx
0x180022139  mov     [rsp+arg_8], rsi
0x18002213e  push    rdi
0x18002213f  sub     rsp, 20h
0x180022143  mov     rbx, [rcx]
0x180022146  mov     rdi, rcx
0x180022149  test    rbx, rbx
0x18002214c  jz      loc_1800221D2
0x180022152  mov     rsi, [rcx+8]
0x180022156  jmp     short loc_180022179
0x180022158  mov     rcx, [rbx]; pv
0x18002215b  test    rcx, rcx
0x18002215e  jz      short loc_180022175
0x180022160  call    cs:__imp_CoTaskMemFree
0x180022166  mov     qword ptr [rbx], 0
0x18002216d  mov     qword ptr [rbx+8], 0
0x180022175  add     rbx, 10h
0x180022179  cmp     rbx, rsi
0x18002217c  jnz     short loc_180022158
0x18002217e  mov     rax, [rdi]
0x180022181  mov     rdx, [rdi+10h]
0x180022185  sub     rdx, rax
0x180022188  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002218c  cmp     rdx, 1000h
0x180022193  jb      short loc_1800221B3
0x180022195  mov     rcx, [rax-8]
0x180022199  sub     rax, rcx
0x18002219c  sub     rax, 8
0x1800221a0  cmp     rax, 1Fh
0x1800221a4  ja      short loc_1800221AC
0x1800221a6  add     rdx, 27h ; '''
0x1800221aa  jmp     short loc_1800221B6
0x1800221ac  mov     ecx, 5
0x1800221b1  int     29h; Win8: RtlFailFast(ecx)
0x1800221b3  mov     rcx, rax; Block
0x1800221b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800221bb  mov     qword ptr [rdi], 0
0x1800221c2  mov     qword ptr [rdi+8], 0
0x1800221ca  mov     qword ptr [rdi+10h], 0
0x1800221d2  mov     rbx, [rsp+28h+arg_0]
0x1800221d7  mov     rsi, [rsp+28h+arg_8]
0x1800221dc  add     rsp, 20h
0x1800221e0  pop     rdi
0x1800221e1  retn
```
