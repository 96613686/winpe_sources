# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001a418`
- end: `0x18001a4aa`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `146`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015010`
- `0x1800157b0`
- `0x1800163d0`
- `0x18001a0f8`

## callees

- `0x18000cc94`
- `0x180010a60`
- `0x18001a418`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a441`

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
0x18001a418  push    rbx
0x18001a41a  push    rsi
0x18001a41b  push    rdi
0x18001a41c  push    r14
0x18001a41e  sub     rsp, 28h
0x18001a422  mov     rax, [rcx+820h]
0x18001a429  mov     rdi, rcx
0x18001a42c  sub     rax, [rcx+810h]
0x18001a433  cmp     rax, rdx
0x18001a436  cmova   rdx, rax
0x18001a43a  lea     r14, [rdx+rdx]
0x18001a43e  mov     rcx, r14; cb
0x18001a441  call    cs:__imp_CoTaskMemAlloc
0x18001a447  mov     rsi, rax
0x18001a44a  test    rax, rax
0x18001a44d  jz      short loc_18001A49A
0x18001a44f  mov     r8, [rdi+810h]; Source
0x18001a456  mov     rdx, r14; DestinationSize
0x18001a459  mov     rbx, [rdi+818h]
0x18001a460  mov     rcx, rax; Destination
0x18001a463  sub     rbx, r8
0x18001a466  mov     r9, rbx; SourceSize
0x18001a469  call    memcpy_s
0x18001a46e  mov     rdx, rsi
0x18001a471  mov     rcx, rdi
0x18001a474  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001a479  lea     rax, [rbx+rsi]
0x18001a47d  mov     [rdi+810h], rsi
0x18001a484  mov     [rdi+818h], rax
0x18001a48b  lea     rax, [r14+rsi]
0x18001a48f  mov     [rdi+820h], rax
0x18001a496  mov     al, 1
0x18001a498  jmp     short loc_18001A4A0
0x18001a49a  mov     byte ptr [rdi+8], 1
0x18001a49e  xor     al, al
0x18001a4a0  add     rsp, 28h
0x18001a4a4  pop     r14
0x18001a4a6  pop     rdi
0x18001a4a7  pop     rsi
0x18001a4a8  pop     rbx
0x18001a4a9  retn
```
