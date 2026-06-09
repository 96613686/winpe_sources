# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180079328`
- end: `0x1800793f5`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `205`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180072bd4`
- `0x180072c9c`
- `0x1800742d0`
- `0x180079218`

## callees

- `0x180053c78`
- `0x18005427c`
- `0x180059d18`
- `0x180079328`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800793a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800793a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079359`

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
0x180079328  mov     [rsp+arg_8], rbx
0x18007932d  mov     [rsp+arg_10], rbp
0x180079332  push    rsi
0x180079333  push    rdi
0x180079334  push    r14
0x180079336  sub     rsp, 20h
0x18007933a  mov     rax, [rcx+820h]
0x180079341  mov     rbx, rcx
0x180079344  sub     rax, [rcx+810h]
0x18007934b  cmp     rax, rdx
0x18007934e  cmova   rdx, rax
0x180079352  lea     r14, [rdx+rdx]
0x180079356  mov     rcx, r14; cb
0x180079359  call    cs:__imp_CoTaskMemAlloc
0x180079360  nop     dword ptr [rax+rax+00h]
0x180079365  mov     rdi, rax
0x180079368  test    rax, rax
0x18007936b  jz      short loc_1800793DB
0x18007936d  mov     r8, [rbx+810h]; Source
0x180079374  mov     rdx, r14; DestinationSize
0x180079377  mov     rsi, [rbx+818h]
0x18007937e  mov     rcx, rax; Destination
0x180079381  sub     rsi, r8
0x180079384  mov     r9, rsi; SourceSize
0x180079387  call    memcpy_s
0x18007938c  mov     rbp, [rbx]
0x18007938f  test    rbp, rbp
0x180079392  jz      short loc_1800793B7
0x180079394  lea     rcx, [rsp+38h+arg_0]; this
0x180079399  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007939e  mov     rcx, rbp; pv
0x1800793a1  call    cs:__imp_CoTaskMemFree
0x1800793a8  nop     dword ptr [rax+rax+00h]
0x1800793ad  lea     rcx, [rsp+38h+arg_0]; this
0x1800793b2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800793b7  mov     [rbx], rdi
0x1800793ba  lea     rax, [rsi+rdi]
0x1800793be  mov     [rbx+818h], rax
0x1800793c5  lea     rax, [r14+rdi]
0x1800793c9  mov     [rbx+820h], rax
0x1800793d0  mov     al, 1
0x1800793d2  mov     [rbx+810h], rdi
0x1800793d9  jmp     short loc_1800793E1
0x1800793db  mov     byte ptr [rbx+8], 1
0x1800793df  xor     al, al
0x1800793e1  mov     rbx, [rsp+38h+arg_8]
0x1800793e6  mov     rbp, [rsp+38h+arg_10]
0x1800793eb  add     rsp, 20h
0x1800793ef  pop     r14
0x1800793f1  pop     rdi
0x1800793f2  pop     rsi
0x1800793f3  retn
```
