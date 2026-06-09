# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800398b4`
- end: `0x180039974`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031ad0`
- `0x180032044`
- `0x18003323c`
- `0x1800393d4`

## callees

- `0x18000b198`
- `0x18000b85c`
- `0x1800108a8`
- `0x1800398b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800398e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800398e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039927`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039927`

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
0x1800398b4  mov     [rsp+arg_8], rbx
0x1800398b9  mov     [rsp+arg_10], rbp
0x1800398be  push    rsi
0x1800398bf  push    rdi
0x1800398c0  push    r14
0x1800398c2  sub     rsp, 20h
0x1800398c6  mov     rax, [rcx+820h]
0x1800398cd  mov     rbx, rcx
0x1800398d0  sub     rax, [rcx+810h]
0x1800398d7  cmp     rax, rdx
0x1800398da  cmova   rdx, rax
0x1800398de  lea     r14, [rdx+rdx]
0x1800398e2  mov     rcx, r14; cb
0x1800398e5  call    cs:__imp_CoTaskMemAlloc
0x1800398eb  mov     rdi, rax
0x1800398ee  test    rax, rax
0x1800398f1  jz      short loc_18003995B
0x1800398f3  mov     r8, [rbx+810h]; Source
0x1800398fa  mov     rdx, r14; DestinationSize
0x1800398fd  mov     rsi, [rbx+818h]
0x180039904  mov     rcx, rax; Destination
0x180039907  sub     rsi, r8
0x18003990a  mov     r9, rsi; SourceSize
0x18003990d  call    memcpy_s
0x180039912  mov     rbp, [rbx]
0x180039915  test    rbp, rbp
0x180039918  jz      short loc_180039937
0x18003991a  lea     rcx, [rsp+38h+arg_0]; this
0x18003991f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180039924  mov     rcx, rbp; pv
0x180039927  call    cs:__imp_CoTaskMemFree
0x18003992d  lea     rcx, [rsp+38h+arg_0]; this
0x180039932  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180039937  mov     [rbx], rdi
0x18003993a  lea     rax, [rsi+rdi]
0x18003993e  mov     [rbx+818h], rax
0x180039945  lea     rax, [r14+rdi]
0x180039949  mov     [rbx+820h], rax
0x180039950  mov     al, 1
0x180039952  mov     [rbx+810h], rdi
0x180039959  jmp     short loc_180039961
0x18003995b  mov     byte ptr [rbx+8], 1
0x18003995f  xor     al, al
0x180039961  mov     rbx, [rsp+38h+arg_8]
0x180039966  mov     rbp, [rsp+38h+arg_10]
0x18003996b  add     rsp, 20h
0x18003996f  pop     r14
0x180039971  pop     rdi
0x180039972  pop     rsi
0x180039973  retn
```
