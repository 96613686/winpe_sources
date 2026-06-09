# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x180013960`
- end: `0x180013a7a`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `282`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `10`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010a20`
- `0x1800122c0`
- `0x180012670`
- `0x180012750`
- `0x180012820`
- `0x180012e50`
- `0x180013370`
- `0x1800134c0`
- `0x1800135a0`
- `0x1800138f0`

## callees

- `0x180013960`
- `0x18005e2c0`
- `0x18005e770`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800139eb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800139fe`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800139eb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800139fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180013a0a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180013a0a`
- `KERNEL32!SetLastError` at `0x180013a2b`
- `KERNEL32!SetLastError` at `0x180013a2b`
- `KERNEL32!GetLastError` at `0x180013a18`
- `KERNEL32!GetLastError` at `0x180013a18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a23`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  size_t v3; // rbp
  char *v4; // rax
  char *v5; // r14
  const void *v6; // rbx
  size_t v7; // rsi
  void *v8; // r15
  DWORD LastError; // ebx
  bool result; // al

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( !v4 )
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  v6 = (const void *)*((_QWORD *)this + 258);
  v7 = *((_QWORD *)this + 259) - (_QWORD)v6;
  if ( v7 )
  {
    if ( !v6 || v3 < v7 )
    {
      memset(v4, 0, v3);
      if ( v6 )
      {
        if ( v3 >= v7 )
          goto LABEL_13;
        *_errno() = 34;
      }
      else
      {
        *_errno() = 22;
      }
      _invalid_parameter_noinfo();
      goto LABEL_13;
    }
    _mm_lfence();
    memmove(v4, v6, v7);
  }
LABEL_13:
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
  return result;
}

```

## disassembly

```asm
0x180013960  push    rbp
0x180013962  push    rdi
0x180013963  push    r14
0x180013965  sub     rsp, 20h
0x180013969  mov     rax, [rcx+820h]
0x180013970  mov     rdi, rcx
0x180013973  sub     rax, [rcx+810h]
0x18001397a  cmp     rax, rdx
0x18001397d  cmova   rdx, rax
0x180013981  lea     rbp, [rdx+rdx]
0x180013985  mov     rcx, rbp; cb
0x180013988  call    cs:__imp_CoTaskMemAlloc
0x18001398e  mov     r14, rax
0x180013991  test    rax, rax
0x180013994  jz      loc_180013A6B
0x18001399a  mov     [rsp+38h+arg_0], rbx
0x18001399f  mov     rbx, [rdi+810h]
0x1800139a6  mov     [rsp+38h+arg_8], rsi
0x1800139ab  mov     rsi, [rdi+818h]
0x1800139b2  mov     [rsp+38h+arg_10], r15
0x1800139b7  sub     rsi, rbx
0x1800139ba  jz      short loc_180013A10
0x1800139bc  test    rbx, rbx
0x1800139bf  jz      short loc_1800139D9
0x1800139c1  cmp     rbp, rsi
0x1800139c4  jb      short loc_1800139D9
0x1800139c6  lfence
0x1800139c9  mov     r8, rsi; Size
0x1800139cc  mov     rdx, rbx; Src
0x1800139cf  mov     rcx, rax; void *
0x1800139d2  call    memmove
0x1800139d7  jmp     short loc_180013A10
0x1800139d9  mov     r8, rbp; Size
0x1800139dc  xor     edx, edx; Val
0x1800139de  mov     rcx, r14; void *
0x1800139e1  call    memset
0x1800139e6  test    rbx, rbx
0x1800139e9  jnz     short loc_1800139F9
0x1800139eb  call    cs:__imp__errno
0x1800139f1  mov     dword ptr [rax], 16h
0x1800139f7  jmp     short loc_180013A0A
0x1800139f9  cmp     rbp, rsi
0x1800139fc  jnb     short loc_180013A10
0x1800139fe  call    cs:__imp__errno
0x180013a04  mov     dword ptr [rax], 22h ; '"'
0x180013a0a  call    cs:__imp__invalid_parameter_noinfo
0x180013a10  mov     r15, [rdi]
0x180013a13  test    r15, r15
0x180013a16  jz      short loc_180013A31
0x180013a18  call    cs:__imp_GetLastError
0x180013a1e  mov     rcx, r15; pv
0x180013a21  mov     ebx, eax
0x180013a23  call    cs:__imp_CoTaskMemFree
0x180013a29  mov     ecx, ebx; dwErrCode
0x180013a2b  call    cs:__imp_SetLastError
0x180013a31  mov     r15, [rsp+38h+arg_10]
0x180013a36  lea     rax, [rsi+r14]
0x180013a3a  mov     rsi, [rsp+38h+arg_8]
0x180013a3f  mov     rbx, [rsp+38h+arg_0]
0x180013a44  mov     [rdi], r14
0x180013a47  mov     [rdi+818h], rax
0x180013a4e  lea     rax, [r14+rbp]
0x180013a52  mov     [rdi+820h], rax
0x180013a59  mov     al, 1
0x180013a5b  mov     [rdi+810h], r14
0x180013a62  add     rsp, 20h
0x180013a66  pop     r14
0x180013a68  pop     rdi
0x180013a69  pop     rbp
0x180013a6a  retn
0x180013a6b  mov     byte ptr [rdi+8], 1
0x180013a6f  xor     al, al
0x180013a71  add     rsp, 20h
0x180013a75  pop     r14
0x180013a77  pop     rdi
0x180013a78  pop     rbp
0x180013a79  retn
```
