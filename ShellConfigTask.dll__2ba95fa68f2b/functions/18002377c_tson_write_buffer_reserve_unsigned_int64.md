# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18002377c`
- end: `0x18002382d`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d5b0`
- `0x18000d660`
- `0x180012414`
- `0x1800124ac`
- `0x180012540`
- `0x1800125d0`
- `0x180013784`
- `0x180022cb8`
- `0x180023638`
- `0x1800238d8`
- `0x180023958`
- `0x180023f1c`
- `0x1800245dc`
- `0x180024f48`
- `0x18002515c`

## callees

- `0x18000cdf0`
- `0x18002377c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800237f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800237f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800237e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800237e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800237a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800237a8`

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
0x18002377c  push    rbx
0x18002377e  push    rbp
0x18002377f  push    rsi
0x180023780  push    rdi
0x180023781  push    r14
0x180023783  push    r15
0x180023785  sub     rsp, 28h
0x180023789  mov     rax, [rcx+820h]
0x180023790  mov     rdi, rcx
0x180023793  sub     rax, [rcx+810h]
0x18002379a  cmp     rax, rdx
0x18002379d  cmova   rdx, rax
0x1800237a1  lea     r15, [rdx+rdx]
0x1800237a5  mov     rcx, r15; cb
0x1800237a8  call    cs:__imp_CoTaskMemAlloc
0x1800237ae  mov     rsi, rax
0x1800237b1  test    rax, rax
0x1800237b4  jz      short loc_18002381A
0x1800237b6  mov     r8, [rdi+810h]; Source
0x1800237bd  mov     rdx, r15; DestinationSize
0x1800237c0  mov     r14, [rdi+818h]
0x1800237c7  mov     rcx, rax; Destination
0x1800237ca  sub     r14, r8
0x1800237cd  mov     r9, r14; SourceSize
0x1800237d0  call    memcpy_s
0x1800237d5  mov     rbp, [rdi]
0x1800237d8  test    rbp, rbp
0x1800237db  jz      short loc_1800237F6
0x1800237dd  call    cs:__imp_GetLastError
0x1800237e3  mov     rcx, rbp; pv
0x1800237e6  mov     ebx, eax
0x1800237e8  call    cs:__imp_CoTaskMemFree
0x1800237ee  mov     ecx, ebx; dwErrCode
0x1800237f0  call    cs:__imp_SetLastError
0x1800237f6  mov     [rdi], rsi
0x1800237f9  lea     rax, [r14+rsi]
0x1800237fd  mov     [rdi+818h], rax
0x180023804  lea     rax, [r15+rsi]
0x180023808  mov     [rdi+820h], rax
0x18002380f  mov     al, 1
0x180023811  mov     [rdi+810h], rsi
0x180023818  jmp     short loc_180023820
0x18002381a  mov     byte ptr [rdi+8], 1
0x18002381e  xor     al, al
0x180023820  add     rsp, 28h
0x180023824  pop     r15
0x180023826  pop     r14
0x180023828  pop     rdi
0x180023829  pop     rsi
0x18002382a  pop     rbp
0x18002382b  pop     rbx
0x18002382c  retn
```
