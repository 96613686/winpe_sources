# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180023604`
- end: `0x1800236c4`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001ea18`
- `0x18001eae4`
- `0x18001f6b4`
- `0x180023384`

## callees

- `0x18001003c`
- `0x18001031c`
- `0x18001360c`
- `0x180023604`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x180023635`
- `OLE32!CoTaskMemAlloc` at `0x180023635`
- `OLE32!CoTaskMemFree` at `0x180023677`
- `OLE32!CoTaskMemFree` at `0x180023677`

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
0x180023604  mov     [rsp+arg_8], rbx
0x180023609  mov     [rsp+arg_10], rbp
0x18002360e  push    rsi
0x18002360f  push    rdi
0x180023610  push    r14
0x180023612  sub     rsp, 20h
0x180023616  mov     rax, [rcx+820h]
0x18002361d  mov     rbx, rcx
0x180023620  sub     rax, [rcx+810h]
0x180023627  cmp     rax, rdx
0x18002362a  cmova   rdx, rax
0x18002362e  lea     r14, [rdx+rdx]
0x180023632  mov     rcx, r14; cb
0x180023635  call    cs:__imp_CoTaskMemAlloc
0x18002363b  mov     rdi, rax
0x18002363e  test    rax, rax
0x180023641  jz      short loc_1800236AB
0x180023643  mov     r8, [rbx+810h]; Source
0x18002364a  mov     rdx, r14; DestinationSize
0x18002364d  mov     rsi, [rbx+818h]
0x180023654  mov     rcx, rax; Destination
0x180023657  sub     rsi, r8
0x18002365a  mov     r9, rsi; SourceSize
0x18002365d  call    memcpy_s
0x180023662  mov     rbp, [rbx]
0x180023665  test    rbp, rbp
0x180023668  jz      short loc_180023687
0x18002366a  lea     rcx, [rsp+38h+arg_0]; this
0x18002366f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180023674  mov     rcx, rbp; pv
0x180023677  call    cs:__imp_CoTaskMemFree
0x18002367d  lea     rcx, [rsp+38h+arg_0]; this
0x180023682  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180023687  mov     [rbx], rdi
0x18002368a  lea     rax, [rsi+rdi]
0x18002368e  mov     [rbx+818h], rax
0x180023695  lea     rax, [r14+rdi]
0x180023699  mov     [rbx+820h], rax
0x1800236a0  mov     al, 1
0x1800236a2  mov     [rbx+810h], rdi
0x1800236a9  jmp     short loc_1800236B1
0x1800236ab  mov     byte ptr [rbx+8], 1
0x1800236af  xor     al, al
0x1800236b1  mov     rbx, [rsp+38h+arg_8]
0x1800236b6  mov     rbp, [rsp+38h+arg_10]
0x1800236bb  add     rsp, 20h
0x1800236bf  pop     r14
0x1800236c1  pop     rdi
0x1800236c2  pop     rsi
0x1800236c3  retn
```
