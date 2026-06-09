# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18003ccf0`
- end: `0x18003cdb0`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029bf4`
- `0x180029d64`
- `0x18002dd40`
- `0x18003c954`

## callees

- `0x180016944`
- `0x180017098`
- `0x18001d260`
- `0x18003ccf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cd63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cd63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cd21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cd21`

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
    memcpy_s_0(v4, v3, v6, v7);
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
0x18003ccf0  mov     [rsp+arg_8], rbx
0x18003ccf5  mov     [rsp+arg_10], rbp
0x18003ccfa  push    rsi
0x18003ccfb  push    rdi
0x18003ccfc  push    r14
0x18003ccfe  sub     rsp, 20h
0x18003cd02  mov     rax, [rcx+820h]
0x18003cd09  mov     rbx, rcx
0x18003cd0c  sub     rax, [rcx+810h]
0x18003cd13  cmp     rax, rdx
0x18003cd16  cmova   rdx, rax
0x18003cd1a  lea     r14, [rdx+rdx]
0x18003cd1e  mov     rcx, r14; cb
0x18003cd21  call    cs:__imp_CoTaskMemAlloc
0x18003cd27  mov     rdi, rax
0x18003cd2a  test    rax, rax
0x18003cd2d  jz      short loc_18003CD97
0x18003cd2f  mov     r8, [rbx+810h]; Source
0x18003cd36  mov     rdx, r14; DestinationSize
0x18003cd39  mov     rsi, [rbx+818h]
0x18003cd40  mov     rcx, rax; Destination
0x18003cd43  sub     rsi, r8
0x18003cd46  mov     r9, rsi; SourceSize
0x18003cd49  call    memcpy_s_0
0x18003cd4e  mov     rbp, [rbx]
0x18003cd51  test    rbp, rbp
0x18003cd54  jz      short loc_18003CD73
0x18003cd56  lea     rcx, [rsp+38h+arg_0]; this
0x18003cd5b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003cd60  mov     rcx, rbp; pv
0x18003cd63  call    cs:__imp_CoTaskMemFree
0x18003cd69  lea     rcx, [rsp+38h+arg_0]; this
0x18003cd6e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003cd73  mov     [rbx], rdi
0x18003cd76  lea     rax, [rsi+rdi]
0x18003cd7a  mov     [rbx+818h], rax
0x18003cd81  lea     rax, [r14+rdi]
0x18003cd85  mov     [rbx+820h], rax
0x18003cd8c  mov     al, 1
0x18003cd8e  mov     [rbx+810h], rdi
0x18003cd95  jmp     short loc_18003CD9D
0x18003cd97  mov     byte ptr [rbx+8], 1
0x18003cd9b  xor     al, al
0x18003cd9d  mov     rbx, [rsp+38h+arg_8]
0x18003cda2  mov     rbp, [rsp+38h+arg_10]
0x18003cda7  add     rsp, 20h
0x18003cdab  pop     r14
0x18003cdad  pop     rdi
0x18003cdae  pop     rsi
0x18003cdaf  retn
```
