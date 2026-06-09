# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001591c`
- end: `0x1800159dc`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `10`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014ef8`
- `0x1800152b8`
- `0x180015560`
- `0x1800155c8`
- `0x180015634`
- `0x180015850`
- `0x1800158c4`
- `0x18001f318`
- `0x180054bdc`
- `0x180054e4c`

## callees

- `0x18001591c`
- `0x18001bc08`
- `0x18001bcb0`
- `0x18005b5b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001594d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001594d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001598f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001598f`

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
0x18001591c  mov     [rsp+arg_8], rbx
0x180015921  mov     [rsp+arg_10], rbp
0x180015926  push    rsi
0x180015927  push    rdi
0x180015928  push    r14
0x18001592a  sub     rsp, 20h
0x18001592e  mov     rax, [rcx+820h]
0x180015935  mov     rbx, rcx
0x180015938  sub     rax, [rcx+810h]
0x18001593f  cmp     rax, rdx
0x180015942  cmova   rdx, rax
0x180015946  lea     r14, [rdx+rdx]
0x18001594a  mov     rcx, r14; cb
0x18001594d  call    cs:__imp_CoTaskMemAlloc
0x180015953  mov     rdi, rax
0x180015956  test    rax, rax
0x180015959  jz      short loc_1800159C3
0x18001595b  mov     r8, [rbx+810h]; Source
0x180015962  mov     rdx, r14; DestinationSize
0x180015965  mov     rsi, [rbx+818h]
0x18001596c  mov     rcx, rax; Destination
0x18001596f  sub     rsi, r8
0x180015972  mov     r9, rsi; SourceSize
0x180015975  call    memcpy_s_0
0x18001597a  mov     rbp, [rbx]
0x18001597d  test    rbp, rbp
0x180015980  jz      short loc_18001599F
0x180015982  lea     rcx, [rsp+38h+arg_0]; this
0x180015987  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001598c  mov     rcx, rbp; pv
0x18001598f  call    cs:__imp_CoTaskMemFree
0x180015995  lea     rcx, [rsp+38h+arg_0]; this
0x18001599a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001599f  mov     [rbx], rdi
0x1800159a2  lea     rax, [rsi+rdi]
0x1800159a6  mov     [rbx+818h], rax
0x1800159ad  lea     rax, [r14+rdi]
0x1800159b1  mov     [rbx+820h], rax
0x1800159b8  mov     al, 1
0x1800159ba  mov     [rbx+810h], rdi
0x1800159c1  jmp     short loc_1800159C9
0x1800159c3  mov     byte ptr [rbx+8], 1
0x1800159c7  xor     al, al
0x1800159c9  mov     rbx, [rsp+38h+arg_8]
0x1800159ce  mov     rbp, [rsp+38h+arg_10]
0x1800159d3  add     rsp, 20h
0x1800159d7  pop     r14
0x1800159d9  pop     rdi
0x1800159da  pop     rsi
0x1800159db  retn
```
