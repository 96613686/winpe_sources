# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x140057144`
- end: `0x1400571f5`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140052050`
- `0x140052100`
- `0x14005244c`
- `0x1400524e4`
- `0x140052578`
- `0x14005260c`
- `0x14005269c`
- `0x140052ac8`
- `0x140056e80`
- `0x1400570d0`
- `0x1400571fc`
- `0x14005781c`
- `0x140057c30`
- `0x140058174`
- `0x140058388`

## callees

- `0x14000a978`
- `0x140057144`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400571a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400571a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400571b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400571b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400571b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400571b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140057170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140057170`

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
0x140057144  push    rbx
0x140057146  push    rbp
0x140057147  push    rsi
0x140057148  push    rdi
0x140057149  push    r14
0x14005714b  push    r15
0x14005714d  sub     rsp, 28h
0x140057151  mov     rax, [rcx+820h]
0x140057158  mov     rdi, rcx
0x14005715b  sub     rax, [rcx+810h]
0x140057162  cmp     rax, rdx
0x140057165  cmova   rdx, rax
0x140057169  lea     r15, [rdx+rdx]
0x14005716d  mov     rcx, r15; cb
0x140057170  call    cs:__imp_CoTaskMemAlloc
0x140057176  mov     rsi, rax
0x140057179  test    rax, rax
0x14005717c  jz      short loc_1400571E2
0x14005717e  mov     r8, [rdi+810h]; Source
0x140057185  mov     rdx, r15; DestinationSize
0x140057188  mov     r14, [rdi+818h]
0x14005718f  mov     rcx, rax; Destination
0x140057192  sub     r14, r8
0x140057195  mov     r9, r14; SourceSize
0x140057198  call    memcpy_s
0x14005719d  mov     rbp, [rdi]
0x1400571a0  test    rbp, rbp
0x1400571a3  jz      short loc_1400571BE
0x1400571a5  call    cs:__imp_GetLastError
0x1400571ab  mov     rcx, rbp; pv
0x1400571ae  mov     ebx, eax
0x1400571b0  call    cs:__imp_CoTaskMemFree
0x1400571b6  mov     ecx, ebx; dwErrCode
0x1400571b8  call    cs:__imp_SetLastError
0x1400571be  mov     [rdi], rsi
0x1400571c1  lea     rax, [r14+rsi]
0x1400571c5  mov     [rdi+818h], rax
0x1400571cc  lea     rax, [r15+rsi]
0x1400571d0  mov     [rdi+820h], rax
0x1400571d7  mov     al, 1
0x1400571d9  mov     [rdi+810h], rsi
0x1400571e0  jmp     short loc_1400571E8
0x1400571e2  mov     byte ptr [rdi+8], 1
0x1400571e6  xor     al, al
0x1400571e8  add     rsp, 28h
0x1400571ec  pop     r15
0x1400571ee  pop     r14
0x1400571f0  pop     rdi
0x1400571f1  pop     rsi
0x1400571f2  pop     rbp
0x1400571f3  pop     rbx
0x1400571f4  retn
```
