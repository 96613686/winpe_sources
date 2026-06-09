# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18003e454`
- end: `0x18003e514`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031584`
- `0x180031b50`
- `0x1800353cc`
- `0x18003dfc4`

## callees

- `0x1800054ac`
- `0x180005768`
- `0x180008148`
- `0x18003e454`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e4c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e4c7`

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
0x18003e454  mov     [rsp+arg_8], rbx
0x18003e459  mov     [rsp+arg_10], rbp
0x18003e45e  push    rsi
0x18003e45f  push    rdi
0x18003e460  push    r14
0x18003e462  sub     rsp, 20h
0x18003e466  mov     rax, [rcx+820h]
0x18003e46d  mov     rbx, rcx
0x18003e470  sub     rax, [rcx+810h]
0x18003e477  cmp     rax, rdx
0x18003e47a  cmova   rdx, rax
0x18003e47e  lea     r14, [rdx+rdx]
0x18003e482  mov     rcx, r14; cb
0x18003e485  call    cs:__imp_CoTaskMemAlloc
0x18003e48b  mov     rdi, rax
0x18003e48e  test    rax, rax
0x18003e491  jz      short loc_18003E4FB
0x18003e493  mov     r8, [rbx+810h]; Source
0x18003e49a  mov     rdx, r14; DestinationSize
0x18003e49d  mov     rsi, [rbx+818h]
0x18003e4a4  mov     rcx, rax; Destination
0x18003e4a7  sub     rsi, r8
0x18003e4aa  mov     r9, rsi; SourceSize
0x18003e4ad  call    memcpy_s
0x18003e4b2  mov     rbp, [rbx]
0x18003e4b5  test    rbp, rbp
0x18003e4b8  jz      short loc_18003E4D7
0x18003e4ba  lea     rcx, [rsp+38h+arg_0]; this
0x18003e4bf  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003e4c4  mov     rcx, rbp; pv
0x18003e4c7  call    cs:__imp_CoTaskMemFree
0x18003e4cd  lea     rcx, [rsp+38h+arg_0]; this
0x18003e4d2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003e4d7  mov     [rbx], rdi
0x18003e4da  lea     rax, [rsi+rdi]
0x18003e4de  mov     [rbx+818h], rax
0x18003e4e5  lea     rax, [r14+rdi]
0x18003e4e9  mov     [rbx+820h], rax
0x18003e4f0  mov     al, 1
0x18003e4f2  mov     [rbx+810h], rdi
0x18003e4f9  jmp     short loc_18003E501
0x18003e4fb  mov     byte ptr [rbx+8], 1
0x18003e4ff  xor     al, al
0x18003e501  mov     rbx, [rsp+38h+arg_8]
0x18003e506  mov     rbp, [rsp+38h+arg_10]
0x18003e50b  add     rsp, 20h
0x18003e50f  pop     r14
0x18003e511  pop     rdi
0x18003e512  pop     rsi
0x18003e513  retn
```
