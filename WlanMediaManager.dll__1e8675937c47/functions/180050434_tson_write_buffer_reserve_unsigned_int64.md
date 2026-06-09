# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180050434`
- end: `0x1800504f4`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800353dc`
- `0x180035518`
- `0x1800382fc`
- `0x180050098`

## callees

- `0x180007a2c`
- `0x180007d10`
- `0x18000a7d8`
- `0x180050434`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800504a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800504a7`

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
0x180050434  mov     [rsp+arg_8], rbx
0x180050439  mov     [rsp+arg_10], rbp
0x18005043e  push    rsi
0x18005043f  push    rdi
0x180050440  push    r14
0x180050442  sub     rsp, 20h
0x180050446  mov     rax, [rcx+820h]
0x18005044d  mov     rbx, rcx
0x180050450  sub     rax, [rcx+810h]
0x180050457  cmp     rax, rdx
0x18005045a  cmova   rdx, rax
0x18005045e  lea     r14, [rdx+rdx]
0x180050462  mov     rcx, r14; cb
0x180050465  call    cs:__imp_CoTaskMemAlloc
0x18005046b  mov     rdi, rax
0x18005046e  test    rax, rax
0x180050471  jz      short loc_1800504DB
0x180050473  mov     r8, [rbx+810h]; Source
0x18005047a  mov     rdx, r14; DestinationSize
0x18005047d  mov     rsi, [rbx+818h]
0x180050484  mov     rcx, rax; Destination
0x180050487  sub     rsi, r8
0x18005048a  mov     r9, rsi; SourceSize
0x18005048d  call    memcpy_s_0
0x180050492  mov     rbp, [rbx]
0x180050495  test    rbp, rbp
0x180050498  jz      short loc_1800504B7
0x18005049a  lea     rcx, [rsp+38h+arg_0]; this
0x18005049f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800504a4  mov     rcx, rbp; pv
0x1800504a7  call    cs:__imp_CoTaskMemFree
0x1800504ad  lea     rcx, [rsp+38h+arg_0]; this
0x1800504b2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800504b7  mov     [rbx], rdi
0x1800504ba  lea     rax, [rsi+rdi]
0x1800504be  mov     [rbx+818h], rax
0x1800504c5  lea     rax, [r14+rdi]
0x1800504c9  mov     [rbx+820h], rax
0x1800504d0  mov     al, 1
0x1800504d2  mov     [rbx+810h], rdi
0x1800504d9  jmp     short loc_1800504E1
0x1800504db  mov     byte ptr [rbx+8], 1
0x1800504df  xor     al, al
0x1800504e1  mov     rbx, [rsp+38h+arg_8]
0x1800504e6  mov     rbp, [rsp+38h+arg_10]
0x1800504eb  add     rsp, 20h
0x1800504ef  pop     r14
0x1800504f1  pop     rdi
0x1800504f2  pop     rsi
0x1800504f3  retn
```
