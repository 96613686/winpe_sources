# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800298e8`
- end: `0x180029999`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f2b0`
- `0x1800114d8`
- `0x18001176c`
- `0x180011964`
- `0x180011c74`
- `0x180013024`
- `0x18002895c`
- `0x180029724`
- `0x1800299a0`
- `0x18002a03c`
- `0x18002a4ec`
- `0x18002aa9c`
- `0x18002acb0`

## callees

- `0x18000eb78`
- `0x1800298e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002995c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002995c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029949`
- `ole32!CoTaskMemFree` at `0x180029954`
- `ole32!CoTaskMemFree` at `0x180029954`
- `ole32!CoTaskMemAlloc` at `0x180029914`
- `ole32!CoTaskMemAlloc` at `0x180029914`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // r15
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // r14
  void *v8; // rbp
  DWORD LastError; // ebx
  bool result; // al

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
      LastError = GetLastError();
      CoTaskMemFree(v8);
      SetLastError(LastError);
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
0x1800298e8  push    rbx
0x1800298ea  push    rbp
0x1800298eb  push    rsi
0x1800298ec  push    rdi
0x1800298ed  push    r14
0x1800298ef  push    r15
0x1800298f1  sub     rsp, 28h
0x1800298f5  mov     rax, [rcx+820h]
0x1800298fc  mov     rdi, rcx
0x1800298ff  sub     rax, [rcx+810h]
0x180029906  cmp     rax, rdx
0x180029909  cmova   rdx, rax
0x18002990d  lea     r15, [rdx+rdx]
0x180029911  mov     rcx, r15; cb
0x180029914  call    cs:__imp_CoTaskMemAlloc
0x18002991a  mov     rsi, rax
0x18002991d  test    rax, rax
0x180029920  jz      short loc_180029986
0x180029922  mov     r8, [rdi+810h]; Source
0x180029929  mov     rdx, r15; DestinationSize
0x18002992c  mov     r14, [rdi+818h]
0x180029933  mov     rcx, rax; Destination
0x180029936  sub     r14, r8
0x180029939  mov     r9, r14; SourceSize
0x18002993c  call    memcpy_s
0x180029941  mov     rbp, [rdi]
0x180029944  test    rbp, rbp
0x180029947  jz      short loc_180029962
0x180029949  call    cs:__imp_GetLastError
0x18002994f  mov     rcx, rbp; pv
0x180029952  mov     ebx, eax
0x180029954  call    cs:__imp_CoTaskMemFree
0x18002995a  mov     ecx, ebx; dwErrCode
0x18002995c  call    cs:__imp_SetLastError
0x180029962  mov     [rdi], rsi
0x180029965  lea     rax, [r14+rsi]
0x180029969  mov     [rdi+818h], rax
0x180029970  lea     rax, [r15+rsi]
0x180029974  mov     [rdi+820h], rax
0x18002997b  mov     al, 1
0x18002997d  mov     [rdi+810h], rsi
0x180029984  jmp     short loc_18002998C
0x180029986  mov     byte ptr [rdi+8], 1
0x18002998a  xor     al, al
0x18002998c  add     rsp, 28h
0x180029990  pop     r15
0x180029992  pop     r14
0x180029994  pop     rdi
0x180029995  pop     rsi
0x180029996  pop     rbp
0x180029997  pop     rbx
0x180029998  retn
```
