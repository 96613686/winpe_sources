# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18000e20c`
- end: `0x18000e2cc`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ab88`
- `0x18000e17c`
- `0x18000e368`

## callees

- `0x1800034d8`
- `0x18000371c`
- `0x1800037a0`
- `0x18000e20c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e23d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e23d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e27f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e27f`

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
0x18000e20c  mov     [rsp+arg_8], rbx
0x18000e211  mov     [rsp+arg_10], rbp
0x18000e216  push    rsi
0x18000e217  push    rdi
0x18000e218  push    r14
0x18000e21a  sub     rsp, 20h
0x18000e21e  mov     rax, [rcx+820h]
0x18000e225  mov     rbx, rcx
0x18000e228  sub     rax, [rcx+810h]
0x18000e22f  cmp     rax, rdx
0x18000e232  cmova   rdx, rax
0x18000e236  lea     r14, [rdx+rdx]
0x18000e23a  mov     rcx, r14; cb
0x18000e23d  call    cs:__imp_CoTaskMemAlloc
0x18000e243  mov     rdi, rax
0x18000e246  test    rax, rax
0x18000e249  jz      short loc_18000E2B3
0x18000e24b  mov     r8, [rbx+810h]; Source
0x18000e252  mov     rdx, r14; DestinationSize
0x18000e255  mov     rsi, [rbx+818h]
0x18000e25c  mov     rcx, rax; Destination
0x18000e25f  sub     rsi, r8
0x18000e262  mov     r9, rsi; SourceSize
0x18000e265  call    memcpy_s
0x18000e26a  mov     rbp, [rbx]
0x18000e26d  test    rbp, rbp
0x18000e270  jz      short loc_18000E28F
0x18000e272  lea     rcx, [rsp+38h+arg_0]; this
0x18000e277  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e27c  mov     rcx, rbp; pv
0x18000e27f  call    cs:__imp_CoTaskMemFree
0x18000e285  lea     rcx, [rsp+38h+arg_0]; this
0x18000e28a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e28f  mov     [rbx], rdi
0x18000e292  lea     rax, [rsi+rdi]
0x18000e296  mov     [rbx+818h], rax
0x18000e29d  lea     rax, [r14+rdi]
0x18000e2a1  mov     [rbx+820h], rax
0x18000e2a8  mov     al, 1
0x18000e2aa  mov     [rbx+810h], rdi
0x18000e2b1  jmp     short loc_18000E2B9
0x18000e2b3  mov     byte ptr [rbx+8], 1
0x18000e2b7  xor     al, al
0x18000e2b9  mov     rbx, [rsp+38h+arg_8]
0x18000e2be  mov     rbp, [rsp+38h+arg_10]
0x18000e2c3  add     rsp, 20h
0x18000e2c7  pop     r14
0x18000e2c9  pop     rdi
0x18000e2ca  pop     rsi
0x18000e2cb  retn
```
