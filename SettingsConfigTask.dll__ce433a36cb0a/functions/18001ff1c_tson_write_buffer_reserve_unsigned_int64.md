# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001ff1c`
- end: `0x18001ffdc`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c4ec`
- `0x180010b74`
- `0x18001fb00`
- `0x180020218`

## callees

- `0x180004264`
- `0x180004a88`
- `0x18000b99c`
- `0x18001ff1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ff4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ff4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff8f`

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
0x18001ff1c  mov     [rsp+arg_8], rbx
0x18001ff21  mov     [rsp+arg_10], rbp
0x18001ff26  push    rsi
0x18001ff27  push    rdi
0x18001ff28  push    r14
0x18001ff2a  sub     rsp, 20h
0x18001ff2e  mov     rax, [rcx+820h]
0x18001ff35  mov     rbx, rcx
0x18001ff38  sub     rax, [rcx+810h]
0x18001ff3f  cmp     rax, rdx
0x18001ff42  cmova   rdx, rax
0x18001ff46  lea     r14, [rdx+rdx]
0x18001ff4a  mov     rcx, r14; cb
0x18001ff4d  call    cs:__imp_CoTaskMemAlloc
0x18001ff53  mov     rdi, rax
0x18001ff56  test    rax, rax
0x18001ff59  jz      short loc_18001FFC3
0x18001ff5b  mov     r8, [rbx+810h]; Source
0x18001ff62  mov     rdx, r14; DestinationSize
0x18001ff65  mov     rsi, [rbx+818h]
0x18001ff6c  mov     rcx, rax; Destination
0x18001ff6f  sub     rsi, r8
0x18001ff72  mov     r9, rsi; SourceSize
0x18001ff75  call    memcpy_s
0x18001ff7a  mov     rbp, [rbx]
0x18001ff7d  test    rbp, rbp
0x18001ff80  jz      short loc_18001FF9F
0x18001ff82  lea     rcx, [rsp+38h+arg_0]; this
0x18001ff87  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ff8c  mov     rcx, rbp; pv
0x18001ff8f  call    cs:__imp_CoTaskMemFree
0x18001ff95  lea     rcx, [rsp+38h+arg_0]; this
0x18001ff9a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ff9f  mov     [rbx], rdi
0x18001ffa2  lea     rax, [rsi+rdi]
0x18001ffa6  mov     [rbx+818h], rax
0x18001ffad  lea     rax, [r14+rdi]
0x18001ffb1  mov     [rbx+820h], rax
0x18001ffb8  mov     al, 1
0x18001ffba  mov     [rbx+810h], rdi
0x18001ffc1  jmp     short loc_18001FFC9
0x18001ffc3  mov     byte ptr [rbx+8], 1
0x18001ffc7  xor     al, al
0x18001ffc9  mov     rbx, [rsp+38h+arg_8]
0x18001ffce  mov     rbp, [rsp+38h+arg_10]
0x18001ffd3  add     rsp, 20h
0x18001ffd7  pop     r14
0x18001ffd9  pop     rdi
0x18001ffda  pop     rsi
0x18001ffdb  retn
```
