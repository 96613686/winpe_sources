# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x1800527d8`
- end: `0x180052889`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `177`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `17`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a4a0`
- `0x18002a70c`
- `0x18002a7a8`
- `0x18002ee58`
- `0x18002eef0`
- `0x18002f214`
- `0x18002f40c`
- `0x18002f49c`
- `0x180031570`
- `0x18004fd10`
- `0x180051ff4`
- `0x180052890`
- `0x18005293c`
- `0x1800529bc`
- `0x180052f20`
- `0x1800549a0`
- `0x180054bb4`

## callees

- `0x18000c634`
- `0x1800527d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052839`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005284c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005284c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052844`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052844`

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
0x1800527d8  push    rbx
0x1800527da  push    rbp
0x1800527db  push    rsi
0x1800527dc  push    rdi
0x1800527dd  push    r14
0x1800527df  push    r15
0x1800527e1  sub     rsp, 28h
0x1800527e5  mov     rax, [rcx+820h]
0x1800527ec  mov     rdi, rcx
0x1800527ef  sub     rax, [rcx+810h]
0x1800527f6  cmp     rax, rdx
0x1800527f9  cmova   rdx, rax
0x1800527fd  lea     r15, [rdx+rdx]
0x180052801  mov     rcx, r15; cb
0x180052804  call    cs:__imp_CoTaskMemAlloc
0x18005280a  mov     rsi, rax
0x18005280d  test    rax, rax
0x180052810  jz      short loc_180052876
0x180052812  mov     r8, [rdi+810h]; Source
0x180052819  mov     rdx, r15; DestinationSize
0x18005281c  mov     r14, [rdi+818h]
0x180052823  mov     rcx, rax; Destination
0x180052826  sub     r14, r8
0x180052829  mov     r9, r14; SourceSize
0x18005282c  call    memcpy_s
0x180052831  mov     rbp, [rdi]
0x180052834  test    rbp, rbp
0x180052837  jz      short loc_180052852
0x180052839  call    cs:__imp_GetLastError
0x18005283f  mov     rcx, rbp; pv
0x180052842  mov     ebx, eax
0x180052844  call    cs:__imp_CoTaskMemFree
0x18005284a  mov     ecx, ebx; dwErrCode
0x18005284c  call    cs:__imp_SetLastError
0x180052852  mov     [rdi], rsi
0x180052855  lea     rax, [r14+rsi]
0x180052859  mov     [rdi+818h], rax
0x180052860  lea     rax, [r15+rsi]
0x180052864  mov     [rdi+820h], rax
0x18005286b  mov     al, 1
0x18005286d  mov     [rdi+810h], rsi
0x180052874  jmp     short loc_18005287C
0x180052876  mov     byte ptr [rdi+8], 1
0x18005287a  xor     al, al
0x18005287c  add     rsp, 28h
0x180052880  pop     r15
0x180052882  pop     r14
0x180052884  pop     rdi
0x180052885  pop     rsi
0x180052886  pop     rbp
0x180052887  pop     rbx
0x180052888  retn
```
