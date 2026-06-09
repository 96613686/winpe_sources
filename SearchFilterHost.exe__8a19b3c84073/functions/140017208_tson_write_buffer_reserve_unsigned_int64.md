# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x140017208`
- end: `0x1400172c8`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000c86c`
- `0x14000c938`
- `0x14000d5a0`
- `0x140016f18`

## callees

- `0x140006418`
- `0x140006b80`
- `0x14000c284`
- `0x140017208`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001727b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001727b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140017239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140017239`

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
0x140017208  mov     [rsp+arg_8], rbx
0x14001720d  mov     [rsp+arg_10], rbp
0x140017212  push    rsi
0x140017213  push    rdi
0x140017214  push    r14
0x140017216  sub     rsp, 20h
0x14001721a  mov     rax, [rcx+820h]
0x140017221  mov     rbx, rcx
0x140017224  sub     rax, [rcx+810h]
0x14001722b  cmp     rax, rdx
0x14001722e  cmova   rdx, rax
0x140017232  lea     r14, [rdx+rdx]
0x140017236  mov     rcx, r14; cb
0x140017239  call    cs:__imp_CoTaskMemAlloc
0x14001723f  mov     rdi, rax
0x140017242  test    rax, rax
0x140017245  jz      short loc_1400172AF
0x140017247  mov     r8, [rbx+810h]; Source
0x14001724e  mov     rdx, r14; DestinationSize
0x140017251  mov     rsi, [rbx+818h]
0x140017258  mov     rcx, rax; Destination
0x14001725b  sub     rsi, r8
0x14001725e  mov     r9, rsi; SourceSize
0x140017261  call    memcpy_s
0x140017266  mov     rbp, [rbx]
0x140017269  test    rbp, rbp
0x14001726c  jz      short loc_14001728B
0x14001726e  lea     rcx, [rsp+38h+arg_0]; this
0x140017273  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140017278  mov     rcx, rbp; pv
0x14001727b  call    cs:__imp_CoTaskMemFree
0x140017281  lea     rcx, [rsp+38h+arg_0]; this
0x140017286  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001728b  mov     [rbx], rdi
0x14001728e  lea     rax, [rsi+rdi]
0x140017292  mov     [rbx+818h], rax
0x140017299  lea     rax, [r14+rdi]
0x14001729d  mov     [rbx+820h], rax
0x1400172a4  mov     al, 1
0x1400172a6  mov     [rbx+810h], rdi
0x1400172ad  jmp     short loc_1400172B5
0x1400172af  mov     byte ptr [rbx+8], 1
0x1400172b3  xor     al, al
0x1400172b5  mov     rbx, [rsp+38h+arg_8]
0x1400172ba  mov     rbp, [rsp+38h+arg_10]
0x1400172bf  add     rsp, 20h
0x1400172c3  pop     r14
0x1400172c5  pop     rdi
0x1400172c6  pop     rsi
0x1400172c7  retn
```
