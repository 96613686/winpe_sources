# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800379e0`
- end: `0x180037aa0`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033f44`
- `0x180034084`
- `0x180035758`
- `0x1800376dc`

## callees

- `0x180014290`
- `0x1800198fc`
- `0x18001991c`
- `0x1800379e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037a11`

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
0x1800379e0  mov     [rsp+arg_8], rbx
0x1800379e5  mov     [rsp+arg_10], rbp
0x1800379ea  push    rsi
0x1800379eb  push    rdi
0x1800379ec  push    r14
0x1800379ee  sub     rsp, 20h
0x1800379f2  mov     rax, [rcx+820h]
0x1800379f9  mov     rbx, rcx
0x1800379fc  sub     rax, [rcx+810h]
0x180037a03  cmp     rax, rdx
0x180037a06  cmova   rdx, rax
0x180037a0a  lea     r14, [rdx+rdx]
0x180037a0e  mov     rcx, r14; cb
0x180037a11  call    cs:__imp_CoTaskMemAlloc
0x180037a17  mov     rdi, rax
0x180037a1a  test    rax, rax
0x180037a1d  jz      short loc_180037A87
0x180037a1f  mov     r8, [rbx+810h]; Source
0x180037a26  mov     rdx, r14; DestinationSize
0x180037a29  mov     rsi, [rbx+818h]
0x180037a30  mov     rcx, rax; Destination
0x180037a33  sub     rsi, r8
0x180037a36  mov     r9, rsi; SourceSize
0x180037a39  call    memcpy_s
0x180037a3e  mov     rbp, [rbx]
0x180037a41  test    rbp, rbp
0x180037a44  jz      short loc_180037A63
0x180037a46  lea     rcx, [rsp+38h+arg_0]; this
0x180037a4b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180037a50  mov     rcx, rbp; pv
0x180037a53  call    cs:__imp_CoTaskMemFree
0x180037a59  lea     rcx, [rsp+38h+arg_0]; this
0x180037a5e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180037a63  mov     [rbx], rdi
0x180037a66  lea     rax, [rsi+rdi]
0x180037a6a  mov     [rbx+818h], rax
0x180037a71  lea     rax, [r14+rdi]
0x180037a75  mov     [rbx+820h], rax
0x180037a7c  mov     al, 1
0x180037a7e  mov     [rbx+810h], rdi
0x180037a85  jmp     short loc_180037A8D
0x180037a87  mov     byte ptr [rbx+8], 1
0x180037a8b  xor     al, al
0x180037a8d  mov     rbx, [rsp+38h+arg_8]
0x180037a92  mov     rbp, [rsp+38h+arg_10]
0x180037a97  add     rsp, 20h
0x180037a9b  pop     r14
0x180037a9d  pop     rdi
0x180037a9e  pop     rsi
0x180037a9f  retn
```
