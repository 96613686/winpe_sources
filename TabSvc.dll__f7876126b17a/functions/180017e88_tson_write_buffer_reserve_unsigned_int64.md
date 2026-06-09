# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180017e88`
- end: `0x180017f48`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d2a8`
- `0x18001e62c`
- `0x180029eb0`
- `0x18002a3e4`

## callees

- `0x180017e88`
- `0x180017f50`
- `0x1800186a0`
- `0x1800186c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017efb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017efb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017eb9`

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
0x180017e88  mov     [rsp+arg_8], rbx
0x180017e8d  mov     [rsp+arg_10], rbp
0x180017e92  push    rsi
0x180017e93  push    rdi
0x180017e94  push    r14
0x180017e96  sub     rsp, 20h
0x180017e9a  mov     rax, [rcx+820h]
0x180017ea1  mov     rbx, rcx
0x180017ea4  sub     rax, [rcx+810h]
0x180017eab  cmp     rax, rdx
0x180017eae  cmova   rdx, rax
0x180017eb2  lea     r14, [rdx+rdx]
0x180017eb6  mov     rcx, r14; cb
0x180017eb9  call    cs:__imp_CoTaskMemAlloc
0x180017ebf  mov     rdi, rax
0x180017ec2  test    rax, rax
0x180017ec5  jz      short loc_180017F2F
0x180017ec7  mov     r8, [rbx+810h]; Source
0x180017ece  mov     rdx, r14; DestinationSize
0x180017ed1  mov     rsi, [rbx+818h]
0x180017ed8  mov     rcx, rax; Destination
0x180017edb  sub     rsi, r8
0x180017ede  mov     r9, rsi; SourceSize
0x180017ee1  call    memcpy_s
0x180017ee6  mov     rbp, [rbx]
0x180017ee9  test    rbp, rbp
0x180017eec  jz      short loc_180017F0B
0x180017eee  lea     rcx, [rsp+38h+arg_0]; this
0x180017ef3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017ef8  mov     rcx, rbp; pv
0x180017efb  call    cs:__imp_CoTaskMemFree
0x180017f01  lea     rcx, [rsp+38h+arg_0]; this
0x180017f06  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017f0b  mov     [rbx], rdi
0x180017f0e  lea     rax, [rsi+rdi]
0x180017f12  mov     [rbx+818h], rax
0x180017f19  lea     rax, [r14+rdi]
0x180017f1d  mov     [rbx+820h], rax
0x180017f24  mov     al, 1
0x180017f26  mov     [rbx+810h], rdi
0x180017f2d  jmp     short loc_180017F35
0x180017f2f  mov     byte ptr [rbx+8], 1
0x180017f33  xor     al, al
0x180017f35  mov     rbx, [rsp+38h+arg_8]
0x180017f3a  mov     rbp, [rsp+38h+arg_10]
0x180017f3f  add     rsp, 20h
0x180017f43  pop     r14
0x180017f45  pop     rdi
0x180017f46  pop     rsi
0x180017f47  retn
```
