# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18000dca8`
- end: `0x18000dd68`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a664`
- `0x18000ae94`
- `0x18000dc18`
- `0x18000dd70`

## callees

- `0x1800045b8`
- `0x180004c88`
- `0x18000a0b8`
- `0x18000dca8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dcd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dcd9`

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
0x18000dca8  mov     [rsp+arg_8], rbx
0x18000dcad  mov     [rsp+arg_10], rbp
0x18000dcb2  push    rsi
0x18000dcb3  push    rdi
0x18000dcb4  push    r14
0x18000dcb6  sub     rsp, 20h
0x18000dcba  mov     rax, [rcx+820h]
0x18000dcc1  mov     rbx, rcx
0x18000dcc4  sub     rax, [rcx+810h]
0x18000dccb  cmp     rax, rdx
0x18000dcce  cmova   rdx, rax
0x18000dcd2  lea     r14, [rdx+rdx]
0x18000dcd6  mov     rcx, r14; cb
0x18000dcd9  call    cs:__imp_CoTaskMemAlloc
0x18000dcdf  mov     rdi, rax
0x18000dce2  test    rax, rax
0x18000dce5  jz      short loc_18000DD4F
0x18000dce7  mov     r8, [rbx+810h]; Source
0x18000dcee  mov     rdx, r14; DestinationSize
0x18000dcf1  mov     rsi, [rbx+818h]
0x18000dcf8  mov     rcx, rax; Destination
0x18000dcfb  sub     rsi, r8
0x18000dcfe  mov     r9, rsi; SourceSize
0x18000dd01  call    memcpy_s
0x18000dd06  mov     rbp, [rbx]
0x18000dd09  test    rbp, rbp
0x18000dd0c  jz      short loc_18000DD2B
0x18000dd0e  lea     rcx, [rsp+38h+arg_0]; this
0x18000dd13  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000dd18  mov     rcx, rbp; pv
0x18000dd1b  call    cs:__imp_CoTaskMemFree
0x18000dd21  lea     rcx, [rsp+38h+arg_0]; this
0x18000dd26  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000dd2b  mov     [rbx], rdi
0x18000dd2e  lea     rax, [rsi+rdi]
0x18000dd32  mov     [rbx+818h], rax
0x18000dd39  lea     rax, [r14+rdi]
0x18000dd3d  mov     [rbx+820h], rax
0x18000dd44  mov     al, 1
0x18000dd46  mov     [rbx+810h], rdi
0x18000dd4d  jmp     short loc_18000DD55
0x18000dd4f  mov     byte ptr [rbx+8], 1
0x18000dd53  xor     al, al
0x18000dd55  mov     rbx, [rsp+38h+arg_8]
0x18000dd5a  mov     rbp, [rsp+38h+arg_10]
0x18000dd5f  add     rsp, 20h
0x18000dd63  pop     r14
0x18000dd65  pop     rdi
0x18000dd66  pop     rsi
0x18000dd67  retn
```
