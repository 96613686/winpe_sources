# tson::write_buffer::push_back<tson::details::archive_marker>(tson::details::archive_marker const &)

- ea: `0x18007b050`
- end: `0x18007b14d`
- name: `??$push_back@W4archive_marker@details@tson@@@write_buffer@tson@@QEAA_NAEBW4archive_marker@details@1@@Z`
- size: `253`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800700e0`
- `0x1800704b0`
- `0x1800707b0`
- `0x1800710d0`
- `0x180071ca0`
- `0x180072764`
- `0x180072ea4`
- `0x180073574`
- `0x180073b40`
- `0x18007f784`

## callees

- `0x18007b050`
- `0x1800a6f3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b138`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b095`

## pseudocode

```c
char __fastcall tson::write_buffer::push_back<enum tson::details::archive_marker>(__int64 a1, char *a2)
{
  unsigned __int64 v2; // r8
  char *v4; // rcx
  unsigned __int64 v6; // r8
  __int64 v7; // rax
  rsize_t v8; // r12
  char *v9; // rax
  char *v10; // rsi
  const void *v11; // r8
  rsize_t v12; // r14
  void *v13; // rbp
  char result; // al
  DWORD LastError; // edi

  v2 = *(_QWORD *)(a1 + 2080);
  v4 = *(char **)(a1 + 2072);
  if ( (unsigned __int64)v4 < v2 )
  {
LABEL_8:
    *v4 = *a2;
    result = 1;
    ++*(_QWORD *)(a1 + 2072);
    return result;
  }
  v6 = v2 - *(_QWORD *)(a1 + 2064);
  v7 = 1;
  if ( v6 > 1 )
    v7 = v6;
  v8 = 2 * v7;
  v9 = (char *)CoTaskMemAlloc(2 * v7);
  v10 = v9;
  if ( v9 )
  {
    v11 = *(const void **)(a1 + 2064);
    v12 = *(_QWORD *)(a1 + 2072) - (_QWORD)v11;
    memcpy_s_1(v9, v8, v11, v12);
    v13 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v13);
      SetLastError(LastError);
    }
    v4 = &v10[v12];
    *(_QWORD *)a1 = v10;
    *(_QWORD *)(a1 + 2072) = &v10[v12];
    *(_QWORD *)(a1 + 2080) = &v10[v8];
    *(_QWORD *)(a1 + 2064) = v10;
    goto LABEL_8;
  }
  *(_BYTE *)(a1 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x18007b050  mov     [rsp+arg_18], rbx
0x18007b055  push    rsi
0x18007b056  push    r12
0x18007b058  push    r15
0x18007b05a  sub     rsp, 20h
0x18007b05e  mov     r8, [rcx+820h]
0x18007b065  mov     rbx, rcx
0x18007b068  mov     rcx, [rcx+818h]
0x18007b06f  mov     r15, rdx
0x18007b072  cmp     rcx, r8
0x18007b075  jb      loc_18007B102
0x18007b07b  sub     r8, [rbx+810h]
0x18007b082  mov     eax, 1
0x18007b087  cmp     r8, rax
0x18007b08a  cmova   rax, r8
0x18007b08e  lea     r12, [rax+rax]
0x18007b092  mov     rcx, r12; cb
0x18007b095  call    cs:__imp_CoTaskMemAlloc
0x18007b09b  mov     rsi, rax
0x18007b09e  test    rax, rax
0x18007b0a1  jz      loc_18007B145
0x18007b0a7  mov     r8, [rbx+810h]; Source
0x18007b0ae  mov     rdx, r12; DestinationSize
0x18007b0b1  mov     [rsp+38h+arg_0], rbp
0x18007b0b6  mov     rcx, rax; Destination
0x18007b0b9  mov     [rsp+38h+arg_10], r14
0x18007b0be  mov     r14, [rbx+818h]
0x18007b0c5  sub     r14, r8
0x18007b0c8  mov     r9, r14; SourceSize
0x18007b0cb  call    memcpy_s_1
0x18007b0d0  mov     rbp, [rbx]
0x18007b0d3  test    rbp, rbp
0x18007b0d6  jnz     short loc_18007B120
0x18007b0d8  mov     rbp, [rsp+38h+arg_0]
0x18007b0dd  lea     rcx, [r14+rsi]
0x18007b0e1  mov     r14, [rsp+38h+arg_10]
0x18007b0e6  lea     rax, [r12+rsi]
0x18007b0ea  mov     [rbx], rsi
0x18007b0ed  mov     [rbx+818h], rcx
0x18007b0f4  mov     [rbx+820h], rax
0x18007b0fb  mov     [rbx+810h], rsi
0x18007b102  movzx   eax, byte ptr [r15]
0x18007b106  mov     [rcx], al
0x18007b108  mov     al, 1
0x18007b10a  inc     qword ptr [rbx+818h]
0x18007b111  mov     rbx, [rsp+38h+arg_18]
0x18007b116  add     rsp, 20h
0x18007b11a  pop     r15
0x18007b11c  pop     r12
0x18007b11e  pop     rsi
0x18007b11f  retn
0x18007b120  mov     [rsp+38h+arg_8], rdi
0x18007b125  call    cs:__imp_GetLastError
0x18007b12b  mov     rcx, rbp; pv
0x18007b12e  mov     edi, eax
0x18007b130  call    cs:__imp_CoTaskMemFree
0x18007b136  mov     ecx, edi; dwErrCode
0x18007b138  call    cs:__imp_SetLastError
0x18007b13e  mov     rdi, [rsp+38h+arg_8]
0x18007b143  jmp     short loc_18007B0D8
0x18007b145  mov     byte ptr [rbx+8], 1
0x18007b149  xor     al, al
0x18007b14b  jmp     short loc_18007B111
```
