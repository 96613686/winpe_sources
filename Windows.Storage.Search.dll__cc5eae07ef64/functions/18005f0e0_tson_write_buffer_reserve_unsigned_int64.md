# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18005f0e0`
- end: `0x18005f191`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065e9c`
- `0x180069094`
- `0x18008f3a4`
- `0x1800942a8`

## callees

- `0x18005f0e0`
- `0x180068598`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f154`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f14c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f14c`

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
0x18005f0e0  push    rbx
0x18005f0e2  push    rbp
0x18005f0e3  push    rsi
0x18005f0e4  push    rdi
0x18005f0e5  push    r14
0x18005f0e7  push    r15
0x18005f0e9  sub     rsp, 28h
0x18005f0ed  mov     rax, [rcx+820h]
0x18005f0f4  mov     rdi, rcx
0x18005f0f7  sub     rax, [rcx+810h]
0x18005f0fe  cmp     rax, rdx
0x18005f101  cmova   rdx, rax
0x18005f105  lea     r15, [rdx+rdx]
0x18005f109  mov     rcx, r15; cb
0x18005f10c  call    cs:__imp_CoTaskMemAlloc
0x18005f112  mov     rsi, rax
0x18005f115  test    rax, rax
0x18005f118  jz      short loc_18005F17E
0x18005f11a  mov     r8, [rdi+810h]; Source
0x18005f121  mov     rdx, r15; DestinationSize
0x18005f124  mov     r14, [rdi+818h]
0x18005f12b  mov     rcx, rax; Destination
0x18005f12e  sub     r14, r8
0x18005f131  mov     r9, r14; SourceSize
0x18005f134  call    memcpy_s
0x18005f139  mov     rbp, [rdi]
0x18005f13c  test    rbp, rbp
0x18005f13f  jz      short loc_18005F15A
0x18005f141  call    cs:__imp_GetLastError
0x18005f147  mov     rcx, rbp; pv
0x18005f14a  mov     ebx, eax
0x18005f14c  call    cs:__imp_CoTaskMemFree
0x18005f152  mov     ecx, ebx; dwErrCode
0x18005f154  call    cs:__imp_SetLastError
0x18005f15a  mov     [rdi], rsi
0x18005f15d  lea     rax, [r14+rsi]
0x18005f161  mov     [rdi+818h], rax
0x18005f168  lea     rax, [r15+rsi]
0x18005f16c  mov     [rdi+820h], rax
0x18005f173  mov     al, 1
0x18005f175  mov     [rdi+810h], rsi
0x18005f17c  jmp     short loc_18005F184
0x18005f17e  mov     byte ptr [rdi+8], 1
0x18005f182  xor     al, al
0x18005f184  add     rsp, 28h
0x18005f188  pop     r15
0x18005f18a  pop     r14
0x18005f18c  pop     rdi
0x18005f18d  pop     rsi
0x18005f18e  pop     rbp
0x18005f18f  pop     rbx
0x18005f190  retn
```
