# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800366fc`
- end: `0x1800367bc`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022ba8`
- `0x180023030`
- `0x180026460`
- `0x180036220`

## callees

- `0x180006cf8`
- `0x180011984`
- `0x180011dfc`
- `0x1800366fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003676f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003676f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003672d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003672d`

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
0x1800366fc  mov     [rsp+arg_8], rbx
0x180036701  mov     [rsp+arg_10], rbp
0x180036706  push    rsi
0x180036707  push    rdi
0x180036708  push    r14
0x18003670a  sub     rsp, 20h
0x18003670e  mov     rax, [rcx+820h]
0x180036715  mov     rbx, rcx
0x180036718  sub     rax, [rcx+810h]
0x18003671f  cmp     rax, rdx
0x180036722  cmova   rdx, rax
0x180036726  lea     r14, [rdx+rdx]
0x18003672a  mov     rcx, r14; cb
0x18003672d  call    cs:__imp_CoTaskMemAlloc
0x180036733  mov     rdi, rax
0x180036736  test    rax, rax
0x180036739  jz      short loc_1800367A3
0x18003673b  mov     r8, [rbx+810h]; Source
0x180036742  mov     rdx, r14; DestinationSize
0x180036745  mov     rsi, [rbx+818h]
0x18003674c  mov     rcx, rax; Destination
0x18003674f  sub     rsi, r8
0x180036752  mov     r9, rsi; SourceSize
0x180036755  call    memcpy_s
0x18003675a  mov     rbp, [rbx]
0x18003675d  test    rbp, rbp
0x180036760  jz      short loc_18003677F
0x180036762  lea     rcx, [rsp+38h+arg_0]; this
0x180036767  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003676c  mov     rcx, rbp; pv
0x18003676f  call    cs:__imp_CoTaskMemFree
0x180036775  lea     rcx, [rsp+38h+arg_0]; this
0x18003677a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003677f  mov     [rbx], rdi
0x180036782  lea     rax, [rsi+rdi]
0x180036786  mov     [rbx+818h], rax
0x18003678d  lea     rax, [r14+rdi]
0x180036791  mov     [rbx+820h], rax
0x180036798  mov     al, 1
0x18003679a  mov     [rbx+810h], rdi
0x1800367a1  jmp     short loc_1800367A9
0x1800367a3  mov     byte ptr [rbx+8], 1
0x1800367a7  xor     al, al
0x1800367a9  mov     rbx, [rsp+38h+arg_8]
0x1800367ae  mov     rbp, [rsp+38h+arg_10]
0x1800367b3  add     rsp, 20h
0x1800367b7  pop     r14
0x1800367b9  pop     rdi
0x1800367ba  pop     rsi
0x1800367bb  retn
```
