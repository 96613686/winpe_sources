# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180042160`
- end: `0x180042220`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `192`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003af38`
- `0x18003b004`
- `0x18003d990`
- `0x180041f48`

## callees

- `0x180005af0`
- `0x180006240`
- `0x18000c460`
- `0x180042160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800421d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800421d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042191`

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
0x180042160  mov     [rsp+arg_8], rbx
0x180042165  mov     [rsp+arg_10], rbp
0x18004216a  push    rsi
0x18004216b  push    rdi
0x18004216c  push    r14
0x18004216e  sub     rsp, 20h
0x180042172  mov     rax, [rcx+820h]
0x180042179  mov     rbx, rcx
0x18004217c  sub     rax, [rcx+810h]
0x180042183  cmp     rax, rdx
0x180042186  cmova   rdx, rax
0x18004218a  lea     r14, [rdx+rdx]
0x18004218e  mov     rcx, r14; cb
0x180042191  call    cs:__imp_CoTaskMemAlloc
0x180042197  mov     rdi, rax
0x18004219a  test    rax, rax
0x18004219d  jz      short loc_180042207
0x18004219f  mov     r8, [rbx+810h]; Source
0x1800421a6  mov     rdx, r14; DestinationSize
0x1800421a9  mov     rsi, [rbx+818h]
0x1800421b0  mov     rcx, rax; Destination
0x1800421b3  sub     rsi, r8
0x1800421b6  mov     r9, rsi; SourceSize
0x1800421b9  call    memcpy_s
0x1800421be  mov     rbp, [rbx]
0x1800421c1  test    rbp, rbp
0x1800421c4  jz      short loc_1800421E3
0x1800421c6  lea     rcx, [rsp+38h+arg_0]; this
0x1800421cb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800421d0  mov     rcx, rbp; pv
0x1800421d3  call    cs:__imp_CoTaskMemFree
0x1800421d9  lea     rcx, [rsp+38h+arg_0]; this
0x1800421de  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800421e3  mov     [rbx], rdi
0x1800421e6  lea     rax, [rsi+rdi]
0x1800421ea  mov     [rbx+818h], rax
0x1800421f1  lea     rax, [r14+rdi]
0x1800421f5  mov     [rbx+820h], rax
0x1800421fc  mov     al, 1
0x1800421fe  mov     [rbx+810h], rdi
0x180042205  jmp     short loc_18004220D
0x180042207  mov     byte ptr [rbx+8], 1
0x18004220b  xor     al, al
0x18004220d  mov     rbx, [rsp+38h+arg_8]
0x180042212  mov     rbp, [rsp+38h+arg_10]
0x180042217  add     rsp, 20h
0x18004221b  pop     r14
0x18004221d  pop     rdi
0x18004221e  pop     rsi
0x18004221f  retn
```
