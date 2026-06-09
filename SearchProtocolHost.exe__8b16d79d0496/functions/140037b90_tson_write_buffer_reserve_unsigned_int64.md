# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x140037b90`
- end: `0x140037c22`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `146`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007564`
- `0x1400076dc`
- `0x14000c2c8`
- `0x140037624`

## callees

- `0x140037b90`
- `0x140037ce0`
- `0x14003a0a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037bb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037bb9`

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
      this,
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
0x140037b90  push    rbx
0x140037b92  push    rsi
0x140037b93  push    rdi
0x140037b94  push    r14
0x140037b96  sub     rsp, 28h
0x140037b9a  mov     rax, [rcx+820h]
0x140037ba1  mov     rdi, rcx
0x140037ba4  sub     rax, [rcx+810h]
0x140037bab  cmp     rax, rdx
0x140037bae  cmova   rdx, rax
0x140037bb2  lea     r14, [rdx+rdx]
0x140037bb6  mov     rcx, r14; cb
0x140037bb9  call    cs:__imp_CoTaskMemAlloc
0x140037bbf  mov     rsi, rax
0x140037bc2  test    rax, rax
0x140037bc5  jz      short loc_140037C12
0x140037bc7  mov     r8, [rdi+810h]; Source
0x140037bce  mov     rdx, r14; DestinationSize
0x140037bd1  mov     rbx, [rdi+818h]
0x140037bd8  mov     rcx, rax; Destination
0x140037bdb  sub     rbx, r8
0x140037bde  mov     r9, rbx; SourceSize
0x140037be1  call    memcpy_s
0x140037be6  mov     rdx, rsi
0x140037be9  mov     rcx, rdi
0x140037bec  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x140037bf1  lea     rax, [rbx+rsi]
0x140037bf5  mov     [rdi+810h], rsi
0x140037bfc  mov     [rdi+818h], rax
0x140037c03  lea     rax, [r14+rsi]
0x140037c07  mov     [rdi+820h], rax
0x140037c0e  mov     al, 1
0x140037c10  jmp     short loc_140037C18
0x140037c12  mov     byte ptr [rdi+8], 1
0x140037c16  xor     al, al
0x140037c18  add     rsp, 28h
0x140037c1c  pop     r14
0x140037c1e  pop     rdi
0x140037c1f  pop     rsi
0x140037c20  pop     rbx
0x140037c21  retn
```
