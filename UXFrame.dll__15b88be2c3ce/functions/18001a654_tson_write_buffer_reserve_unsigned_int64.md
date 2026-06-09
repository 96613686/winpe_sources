# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001a654`
- end: `0x18001a714`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800091d0`
- `0x18000c820`
- `0x18001a0cc`
- `0x18001a9bc`

## callees

- `0x18000d84c`
- `0x18000e9e4`
- `0x18001a654`
- `0x18001d2dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6c7`

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
0x18001a654  mov     [rsp+arg_8], rbx
0x18001a659  mov     [rsp+arg_10], rbp
0x18001a65e  push    rsi
0x18001a65f  push    rdi
0x18001a660  push    r14
0x18001a662  sub     rsp, 20h
0x18001a666  mov     rax, [rcx+820h]
0x18001a66d  mov     rbx, rcx
0x18001a670  sub     rax, [rcx+810h]
0x18001a677  cmp     rax, rdx
0x18001a67a  cmova   rdx, rax
0x18001a67e  lea     r14, [rdx+rdx]
0x18001a682  mov     rcx, r14; cb
0x18001a685  call    cs:__imp_CoTaskMemAlloc
0x18001a68b  mov     rdi, rax
0x18001a68e  test    rax, rax
0x18001a691  jz      short loc_18001A6FB
0x18001a693  mov     r8, [rbx+810h]; Source
0x18001a69a  mov     rdx, r14; DestinationSize
0x18001a69d  mov     rsi, [rbx+818h]
0x18001a6a4  mov     rcx, rax; Destination
0x18001a6a7  sub     rsi, r8
0x18001a6aa  mov     r9, rsi; SourceSize
0x18001a6ad  call    memcpy_s_0
0x18001a6b2  mov     rbp, [rbx]
0x18001a6b5  test    rbp, rbp
0x18001a6b8  jz      short loc_18001A6D7
0x18001a6ba  lea     rcx, [rsp+38h+arg_0]; this
0x18001a6bf  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a6c4  mov     rcx, rbp; pv
0x18001a6c7  call    cs:__imp_CoTaskMemFree
0x18001a6cd  lea     rcx, [rsp+38h+arg_0]; this
0x18001a6d2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001a6d7  mov     [rbx], rdi
0x18001a6da  lea     rax, [rsi+rdi]
0x18001a6de  mov     [rbx+818h], rax
0x18001a6e5  lea     rax, [r14+rdi]
0x18001a6e9  mov     [rbx+820h], rax
0x18001a6f0  mov     al, 1
0x18001a6f2  mov     [rbx+810h], rdi
0x18001a6f9  jmp     short loc_18001A701
0x18001a6fb  mov     byte ptr [rbx+8], 1
0x18001a6ff  xor     al, al
0x18001a701  mov     rbx, [rsp+38h+arg_8]
0x18001a706  mov     rbp, [rsp+38h+arg_10]
0x18001a70b  add     rsp, 20h
0x18001a70f  pop     r14
0x18001a711  pop     rdi
0x18001a712  pop     rsi
0x18001a713  retn
```
