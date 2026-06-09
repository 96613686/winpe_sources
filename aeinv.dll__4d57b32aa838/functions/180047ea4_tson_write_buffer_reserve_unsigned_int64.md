# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180047ea4`
- end: `0x180047f64`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1801059c4`
- `0x180106468`
- `0x180108154`
- `0x180108480`

## callees

- `0x180047ea4`
- `0x180047f6c`
- `0x18004826c`
- `0x1800487ac`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180047f17`
- `ole32!CoTaskMemFree` at `0x180047f17`
- `ole32!CoTaskMemAlloc` at `0x180047ed5`
- `ole32!CoTaskMemAlloc` at `0x180047ed5`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r14
  char *v4; // rax
  char *v5; // rdi
  const void *v6; // r8
  rsize_t v7; // rsi
  void *v8; // rbp
  bool result; // al
  char v10; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( v4 )
  {
    v6 = (const void *)*((_QWORD *)this + 258);
    v7 = *((_QWORD *)this + 259) - (_QWORD)v6;
    memcpy_s(v4, v3, v6, v7);
    v8 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
      CoTaskMemFree(v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
    }
    *(_QWORD *)this = v5;
    *((_QWORD *)this + 259) = &v5[v7];
    *((_QWORD *)this + 260) = &v5[v3];
    result = 1;
    *((_QWORD *)this + 258) = v5;
  }
  else
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180047ea4  mov     [rsp+arg_8], rbx
0x180047ea9  mov     [rsp+arg_10], rbp
0x180047eae  push    rsi
0x180047eaf  push    rdi
0x180047eb0  push    r14
0x180047eb2  sub     rsp, 20h
0x180047eb6  mov     rax, [rcx+820h]
0x180047ebd  mov     rbx, rcx
0x180047ec0  sub     rax, [rcx+810h]
0x180047ec7  cmp     rax, rdx
0x180047eca  cmova   rdx, rax
0x180047ece  lea     r14, [rdx+rdx]
0x180047ed2  mov     rcx, r14; cb
0x180047ed5  call    cs:__imp_CoTaskMemAlloc
0x180047edb  mov     rdi, rax
0x180047ede  test    rax, rax
0x180047ee1  jz      short loc_180047F4B
0x180047ee3  mov     r8, [rbx+810h]; Source
0x180047eea  mov     rdx, r14; DestinationSize
0x180047eed  mov     rsi, [rbx+818h]
0x180047ef4  mov     rcx, rax; Destination
0x180047ef7  sub     rsi, r8
0x180047efa  mov     r9, rsi; SourceSize
0x180047efd  call    memcpy_s
0x180047f02  mov     rbp, [rbx]
0x180047f05  test    rbp, rbp
0x180047f08  jz      short loc_180047F27
0x180047f0a  lea     rcx, [rsp+38h+arg_0]; this
0x180047f0f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180047f14  mov     rcx, rbp; pv
0x180047f17  call    cs:__imp_CoTaskMemFree
0x180047f1d  lea     rcx, [rsp+38h+arg_0]; this
0x180047f22  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180047f27  mov     [rbx], rdi
0x180047f2a  lea     rax, [rsi+rdi]
0x180047f2e  mov     [rbx+818h], rax
0x180047f35  lea     rax, [r14+rdi]
0x180047f39  mov     [rbx+820h], rax
0x180047f40  mov     al, 1
0x180047f42  mov     [rbx+810h], rdi
0x180047f49  jmp     short loc_180047F51
0x180047f4b  mov     byte ptr [rbx+8], 1
0x180047f4f  xor     al, al
0x180047f51  mov     rbx, [rsp+38h+arg_8]
0x180047f56  mov     rbp, [rsp+38h+arg_10]
0x180047f5b  add     rsp, 20h
0x180047f5f  pop     r14
0x180047f61  pop     rdi
0x180047f62  pop     rsi
0x180047f63  retn
```
