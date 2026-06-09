# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180025068`
- end: `0x180025128`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009524`
- `0x180009660`
- `0x180016d5c`
- `0x180024bf4`

## callees

- `0x180004dc8`
- `0x180005094`
- `0x180007ac8`
- `0x180025068`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800250db`

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
0x180025068  mov     [rsp+arg_8], rbx
0x18002506d  mov     [rsp+arg_10], rbp
0x180025072  push    rsi
0x180025073  push    rdi
0x180025074  push    r14
0x180025076  sub     rsp, 20h
0x18002507a  mov     rax, [rcx+820h]
0x180025081  mov     rbx, rcx
0x180025084  sub     rax, [rcx+810h]
0x18002508b  cmp     rax, rdx
0x18002508e  cmova   rdx, rax
0x180025092  lea     r14, [rdx+rdx]
0x180025096  mov     rcx, r14; cb
0x180025099  call    cs:__imp_CoTaskMemAlloc
0x18002509f  mov     rdi, rax
0x1800250a2  test    rax, rax
0x1800250a5  jz      short loc_18002510F
0x1800250a7  mov     r8, [rbx+810h]; Source
0x1800250ae  mov     rdx, r14; DestinationSize
0x1800250b1  mov     rsi, [rbx+818h]
0x1800250b8  mov     rcx, rax; Destination
0x1800250bb  sub     rsi, r8
0x1800250be  mov     r9, rsi; SourceSize
0x1800250c1  call    memcpy_s
0x1800250c6  mov     rbp, [rbx]
0x1800250c9  test    rbp, rbp
0x1800250cc  jz      short loc_1800250EB
0x1800250ce  lea     rcx, [rsp+38h+arg_0]; this
0x1800250d3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800250d8  mov     rcx, rbp; pv
0x1800250db  call    cs:__imp_CoTaskMemFree
0x1800250e1  lea     rcx, [rsp+38h+arg_0]; this
0x1800250e6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800250eb  mov     [rbx], rdi
0x1800250ee  lea     rax, [rsi+rdi]
0x1800250f2  mov     [rbx+818h], rax
0x1800250f9  lea     rax, [r14+rdi]
0x1800250fd  mov     [rbx+820h], rax
0x180025104  mov     al, 1
0x180025106  mov     [rbx+810h], rdi
0x18002510d  jmp     short loc_180025115
0x18002510f  mov     byte ptr [rbx+8], 1
0x180025113  xor     al, al
0x180025115  mov     rbx, [rsp+38h+arg_8]
0x18002511a  mov     rbp, [rsp+38h+arg_10]
0x18002511f  add     rsp, 20h
0x180025123  pop     r14
0x180025125  pop     rdi
0x180025126  pop     rsi
0x180025127  retn
```
