# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18007336c`
- end: `0x18007342c`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006b6b0`
- `0x18006b798`
- `0x18006c5a8`
- `0x1800732dc`

## callees

- `0x180009534`
- `0x180009eb0`
- `0x180010a58`
- `0x18007336c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800733df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800733df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007339d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007339d`

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
0x18007336c  mov     [rsp+arg_8], rbx
0x180073371  mov     [rsp+arg_10], rbp
0x180073376  push    rsi
0x180073377  push    rdi
0x180073378  push    r14
0x18007337a  sub     rsp, 20h
0x18007337e  mov     rax, [rcx+820h]
0x180073385  mov     rbx, rcx
0x180073388  sub     rax, [rcx+810h]
0x18007338f  cmp     rax, rdx
0x180073392  cmova   rdx, rax
0x180073396  lea     r14, [rdx+rdx]
0x18007339a  mov     rcx, r14; cb
0x18007339d  call    cs:__imp_CoTaskMemAlloc
0x1800733a3  mov     rdi, rax
0x1800733a6  test    rax, rax
0x1800733a9  jz      short loc_180073413
0x1800733ab  mov     r8, [rbx+810h]; Source
0x1800733b2  mov     rdx, r14; DestinationSize
0x1800733b5  mov     rsi, [rbx+818h]
0x1800733bc  mov     rcx, rax; Destination
0x1800733bf  sub     rsi, r8
0x1800733c2  mov     r9, rsi; SourceSize
0x1800733c5  call    memcpy_s
0x1800733ca  mov     rbp, [rbx]
0x1800733cd  test    rbp, rbp
0x1800733d0  jz      short loc_1800733EF
0x1800733d2  lea     rcx, [rsp+38h+arg_0]; this
0x1800733d7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800733dc  mov     rcx, rbp; pv
0x1800733df  call    cs:__imp_CoTaskMemFree
0x1800733e5  lea     rcx, [rsp+38h+arg_0]; this
0x1800733ea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800733ef  mov     [rbx], rdi
0x1800733f2  lea     rax, [rsi+rdi]
0x1800733f6  mov     [rbx+818h], rax
0x1800733fd  lea     rax, [r14+rdi]
0x180073401  mov     [rbx+820h], rax
0x180073408  mov     al, 1
0x18007340a  mov     [rbx+810h], rdi
0x180073411  jmp     short loc_180073419
0x180073413  mov     byte ptr [rbx+8], 1
0x180073417  xor     al, al
0x180073419  mov     rbx, [rsp+38h+arg_8]
0x18007341e  mov     rbp, [rsp+38h+arg_10]
0x180073423  add     rsp, 20h
0x180073427  pop     r14
0x180073429  pop     rdi
0x18007342a  pop     rsi
0x18007342b  retn
```
