# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001b9e4`
- end: `0x18001baa4`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800080d8`
- `0x180008330`
- `0x180008f84`
- `0x18001b78c`

## callees

- `0x180007df8`
- `0x180009980`
- `0x18000a7e8`
- `0x18001b9e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ba57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ba57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ba15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ba15`

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
0x18001b9e4  mov     [rsp+arg_8], rbx
0x18001b9e9  mov     [rsp+arg_10], rbp
0x18001b9ee  push    rsi
0x18001b9ef  push    rdi
0x18001b9f0  push    r14
0x18001b9f2  sub     rsp, 20h
0x18001b9f6  mov     rax, [rcx+820h]
0x18001b9fd  mov     rbx, rcx
0x18001ba00  sub     rax, [rcx+810h]
0x18001ba07  cmp     rax, rdx
0x18001ba0a  cmova   rdx, rax
0x18001ba0e  lea     r14, [rdx+rdx]
0x18001ba12  mov     rcx, r14; cb
0x18001ba15  call    cs:__imp_CoTaskMemAlloc
0x18001ba1b  mov     rdi, rax
0x18001ba1e  test    rax, rax
0x18001ba21  jz      short loc_18001BA8B
0x18001ba23  mov     r8, [rbx+810h]; Source
0x18001ba2a  mov     rdx, r14; DestinationSize
0x18001ba2d  mov     rsi, [rbx+818h]
0x18001ba34  mov     rcx, rax; Destination
0x18001ba37  sub     rsi, r8
0x18001ba3a  mov     r9, rsi; SourceSize
0x18001ba3d  call    memcpy_s_0
0x18001ba42  mov     rbp, [rbx]
0x18001ba45  test    rbp, rbp
0x18001ba48  jz      short loc_18001BA67
0x18001ba4a  lea     rcx, [rsp+38h+arg_0]; this
0x18001ba4f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ba54  mov     rcx, rbp; pv
0x18001ba57  call    cs:__imp_CoTaskMemFree
0x18001ba5d  lea     rcx, [rsp+38h+arg_0]; this
0x18001ba62  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ba67  mov     [rbx], rdi
0x18001ba6a  lea     rax, [rsi+rdi]
0x18001ba6e  mov     [rbx+818h], rax
0x18001ba75  lea     rax, [r14+rdi]
0x18001ba79  mov     [rbx+820h], rax
0x18001ba80  mov     al, 1
0x18001ba82  mov     [rbx+810h], rdi
0x18001ba89  jmp     short loc_18001BA91
0x18001ba8b  mov     byte ptr [rbx+8], 1
0x18001ba8f  xor     al, al
0x18001ba91  mov     rbx, [rsp+38h+arg_8]
0x18001ba96  mov     rbp, [rsp+38h+arg_10]
0x18001ba9b  add     rsp, 20h
0x18001ba9f  pop     r14
0x18001baa1  pop     rdi
0x18001baa2  pop     rsi
0x18001baa3  retn
```
