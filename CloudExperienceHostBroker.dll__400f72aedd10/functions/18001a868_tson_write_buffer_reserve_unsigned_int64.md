# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001a868`
- end: `0x18001a8fa`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `146`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fa64`
- `0x18000fc24`
- `0x180011268`
- `0x18001a444`

## callees

- `0x18000f6c8`
- `0x18001a868`
- `0x18001a980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a891`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a891`

## pseudocode

```c
char __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r14
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // rbx

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
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      (void **)this,
      v5);
    *((_QWORD *)this + 258) = v5;
    *((_QWORD *)this + 259) = &v5[v7];
    *((_QWORD *)this + 260) = &v5[v3];
    return 1;
  }
  else
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x18001a868  push    rbx
0x18001a86a  push    rsi
0x18001a86b  push    rdi
0x18001a86c  push    r14
0x18001a86e  sub     rsp, 28h
0x18001a872  mov     rax, [rcx+820h]
0x18001a879  mov     rdi, rcx
0x18001a87c  sub     rax, [rcx+810h]
0x18001a883  cmp     rax, rdx
0x18001a886  cmova   rdx, rax
0x18001a88a  lea     r14, [rdx+rdx]
0x18001a88e  mov     rcx, r14; cb
0x18001a891  call    cs:__imp_CoTaskMemAlloc
0x18001a897  mov     rsi, rax
0x18001a89a  test    rax, rax
0x18001a89d  jz      short loc_18001A8EA
0x18001a89f  mov     r8, [rdi+810h]; Source
0x18001a8a6  mov     rdx, r14; DestinationSize
0x18001a8a9  mov     rbx, [rdi+818h]
0x18001a8b0  mov     rcx, rax; Destination
0x18001a8b3  sub     rbx, r8
0x18001a8b6  mov     r9, rbx; SourceSize
0x18001a8b9  call    memcpy_s
0x18001a8be  mov     rdx, rsi
0x18001a8c1  mov     rcx, rdi
0x18001a8c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001a8c9  lea     rax, [rbx+rsi]
0x18001a8cd  mov     [rdi+810h], rsi
0x18001a8d4  mov     [rdi+818h], rax
0x18001a8db  lea     rax, [r14+rsi]
0x18001a8df  mov     [rdi+820h], rax
0x18001a8e6  mov     al, 1
0x18001a8e8  jmp     short loc_18001A8F0
0x18001a8ea  mov     byte ptr [rdi+8], 1
0x18001a8ee  xor     al, al
0x18001a8f0  add     rsp, 28h
0x18001a8f4  pop     r14
0x18001a8f6  pop     rdi
0x18001a8f7  pop     rsi
0x18001a8f8  pop     rbx
0x18001a8f9  retn
```
