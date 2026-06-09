# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x14002c138`
- end: `0x14002c1f8`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140009654`
- `0x14000971c`
- `0x14000d308`
- `0x14002bf80`

## callees

- `0x14000e428`
- `0x14000f384`
- `0x14002c138`
- `0x14002e000`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14002c169`
- `ole32!CoTaskMemAlloc` at `0x14002c169`
- `ole32!CoTaskMemFree` at `0x14002c1ab`
- `ole32!CoTaskMemFree` at `0x14002c1ab`

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
0x14002c138  mov     [rsp+arg_8], rbx
0x14002c13d  mov     [rsp+arg_10], rbp
0x14002c142  push    rsi
0x14002c143  push    rdi
0x14002c144  push    r14
0x14002c146  sub     rsp, 20h
0x14002c14a  mov     rax, [rcx+820h]
0x14002c151  mov     rbx, rcx
0x14002c154  sub     rax, [rcx+810h]
0x14002c15b  cmp     rax, rdx
0x14002c15e  cmova   rdx, rax
0x14002c162  lea     r14, [rdx+rdx]
0x14002c166  mov     rcx, r14; cb
0x14002c169  call    cs:__imp_CoTaskMemAlloc
0x14002c16f  mov     rdi, rax
0x14002c172  test    rax, rax
0x14002c175  jz      short loc_14002C1DF
0x14002c177  mov     r8, [rbx+810h]; Source
0x14002c17e  mov     rdx, r14; DestinationSize
0x14002c181  mov     rsi, [rbx+818h]
0x14002c188  mov     rcx, rax; Destination
0x14002c18b  sub     rsi, r8
0x14002c18e  mov     r9, rsi; SourceSize
0x14002c191  call    memcpy_s_0
0x14002c196  mov     rbp, [rbx]
0x14002c199  test    rbp, rbp
0x14002c19c  jz      short loc_14002C1BB
0x14002c19e  lea     rcx, [rsp+38h+arg_0]; this
0x14002c1a3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14002c1a8  mov     rcx, rbp; pv
0x14002c1ab  call    cs:__imp_CoTaskMemFree
0x14002c1b1  lea     rcx, [rsp+38h+arg_0]; this
0x14002c1b6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002c1bb  mov     [rbx], rdi
0x14002c1be  lea     rax, [rsi+rdi]
0x14002c1c2  mov     [rbx+818h], rax
0x14002c1c9  lea     rax, [r14+rdi]
0x14002c1cd  mov     [rbx+820h], rax
0x14002c1d4  mov     al, 1
0x14002c1d6  mov     [rbx+810h], rdi
0x14002c1dd  jmp     short loc_14002C1E5
0x14002c1df  mov     byte ptr [rbx+8], 1
0x14002c1e3  xor     al, al
0x14002c1e5  mov     rbx, [rsp+38h+arg_8]
0x14002c1ea  mov     rbp, [rsp+38h+arg_10]
0x14002c1ef  add     rsp, 20h
0x14002c1f3  pop     r14
0x14002c1f5  pop     rdi
0x14002c1f6  pop     rsi
0x14002c1f7  retn
```
