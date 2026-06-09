# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18005e388`
- end: `0x18005e448`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049430`
- `0x18004b628`
- `0x18005e2f8`
- `0x18005e4bc`

## callees

- `0x1800239d0`
- `0x180032e40`
- `0x18003b2a8`
- `0x18005e388`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e3fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e3fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e3b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e3b9`

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
0x18005e388  mov     [rsp+arg_8], rbx
0x18005e38d  mov     [rsp+arg_10], rbp
0x18005e392  push    rsi
0x18005e393  push    rdi
0x18005e394  push    r14
0x18005e396  sub     rsp, 20h
0x18005e39a  mov     rax, [rcx+820h]
0x18005e3a1  mov     rbx, rcx
0x18005e3a4  sub     rax, [rcx+810h]
0x18005e3ab  cmp     rax, rdx
0x18005e3ae  cmova   rdx, rax
0x18005e3b2  lea     r14, [rdx+rdx]
0x18005e3b6  mov     rcx, r14; cb
0x18005e3b9  call    cs:__imp_CoTaskMemAlloc
0x18005e3bf  mov     rdi, rax
0x18005e3c2  test    rax, rax
0x18005e3c5  jz      short loc_18005E42F
0x18005e3c7  mov     r8, [rbx+810h]; Source
0x18005e3ce  mov     rdx, r14; DestinationSize
0x18005e3d1  mov     rsi, [rbx+818h]
0x18005e3d8  mov     rcx, rax; Destination
0x18005e3db  sub     rsi, r8
0x18005e3de  mov     r9, rsi; SourceSize
0x18005e3e1  call    memcpy_s
0x18005e3e6  mov     rbp, [rbx]
0x18005e3e9  test    rbp, rbp
0x18005e3ec  jz      short loc_18005E40B
0x18005e3ee  lea     rcx, [rsp+38h+arg_0]; this
0x18005e3f3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005e3f8  mov     rcx, rbp; pv
0x18005e3fb  call    cs:__imp_CoTaskMemFree
0x18005e401  lea     rcx, [rsp+38h+arg_0]; this
0x18005e406  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005e40b  mov     [rbx], rdi
0x18005e40e  lea     rax, [rsi+rdi]
0x18005e412  mov     [rbx+818h], rax
0x18005e419  lea     rax, [r14+rdi]
0x18005e41d  mov     [rbx+820h], rax
0x18005e424  mov     al, 1
0x18005e426  mov     [rbx+810h], rdi
0x18005e42d  jmp     short loc_18005E435
0x18005e42f  mov     byte ptr [rbx+8], 1
0x18005e433  xor     al, al
0x18005e435  mov     rbx, [rsp+38h+arg_8]
0x18005e43a  mov     rbp, [rsp+38h+arg_10]
0x18005e43f  add     rsp, 20h
0x18005e443  pop     r14
0x18005e445  pop     rdi
0x18005e446  pop     rsi
0x18005e447  retn
```
