# sub_18005CAAC

- ea: `0x18005caac`
- end: `0x18005cb6d`
- name: `sub_18005CAAC`
- size: `193`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f210`
- `0x18003f41c`
- `0x180040c88`
- `0x18005c9a0`

## callees

- `0x18003aafc`
- `0x18003ade8`
- `0x18005caac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18005cb05`
- `msvcrt!memcpy_s` at `0x18005cb05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cb20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cb20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005cadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005cadd`

## pseudocode

```c
char __fastcall sub_18005CAAC(__int64 a1, unsigned __int64 a2)
{
  rsize_t v3; // r14
  char *v4; // rax
  char *v5; // rdi
  const void *v6; // r8
  rsize_t v7; // rsi
  void *v8; // rbp
  char result; // al
  char v10; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 2080) - *(_QWORD *)(a1 + 2064) > a2 )
    a2 = *(_QWORD *)(a1 + 2080) - *(_QWORD *)(a1 + 2064);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( v4 )
  {
    v6 = *(const void **)(a1 + 2064);
    v7 = *(_QWORD *)(a1 + 2072) - (_QWORD)v6;
    memcpy_s(v4, v3, v6, v7);
    v8 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      sub_18003AAFC(&v10);
      CoTaskMemFree(v8);
      sub_18003ADE8(&v10);
    }
    *(_QWORD *)a1 = v5;
    *(_QWORD *)(a1 + 2072) = &v5[v7];
    *(_QWORD *)(a1 + 2080) = &v5[v3];
    result = 1;
    *(_QWORD *)(a1 + 2064) = v5;
  }
  else
  {
    *(_BYTE *)(a1 + 8) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18005caac  mov     [rsp+arg_8], rbx
0x18005cab1  mov     [rsp+arg_10], rbp
0x18005cab6  push    rsi
0x18005cab7  push    rdi
0x18005cab8  push    r14
0x18005caba  sub     rsp, 20h
0x18005cabe  mov     rax, [rcx+820h]
0x18005cac5  mov     rbx, rcx
0x18005cac8  sub     rax, [rcx+810h]
0x18005cacf  cmp     rax, rdx
0x18005cad2  cmova   rdx, rax
0x18005cad6  lea     r14, [rdx+rdx]
0x18005cada  mov     rcx, r14; cb
0x18005cadd  call    cs:CoTaskMemAlloc
0x18005cae3  mov     rdi, rax
0x18005cae6  test    rax, rax
0x18005cae9  jz      short loc_18005CB54
0x18005caeb  mov     r8, [rbx+810h]; Source
0x18005caf2  mov     rdx, r14; DestinationSize
0x18005caf5  mov     rsi, [rbx+818h]
0x18005cafc  mov     rcx, rax; Destination
0x18005caff  sub     rsi, r8
0x18005cb02  mov     r9, rsi; SourceSize
0x18005cb05  call    cs:memcpy_s
0x18005cb0b  mov     rbp, [rbx]
0x18005cb0e  test    rbp, rbp
0x18005cb11  jz      short loc_18005CB30
0x18005cb13  lea     rcx, [rsp+38h+arg_0]
0x18005cb18  call    sub_18003AAFC
0x18005cb1d  mov     rcx, rbp; pv
0x18005cb20  call    cs:CoTaskMemFree
0x18005cb26  lea     rcx, [rsp+38h+arg_0]
0x18005cb2b  call    sub_18003ADE8
0x18005cb30  mov     [rbx], rdi
0x18005cb33  lea     rax, [rsi+rdi]
0x18005cb37  mov     [rbx+818h], rax
0x18005cb3e  lea     rax, [r14+rdi]
0x18005cb42  mov     [rbx+820h], rax
0x18005cb49  mov     al, 1
0x18005cb4b  mov     [rbx+810h], rdi
0x18005cb52  jmp     short loc_18005CB5A
0x18005cb54  mov     byte ptr [rbx+8], 1
0x18005cb58  xor     al, al
0x18005cb5a  mov     rbx, [rsp+38h+arg_8]
0x18005cb5f  mov     rbp, [rsp+38h+arg_10]
0x18005cb64  add     rsp, 20h
0x18005cb68  pop     r14
0x18005cb6a  pop     rdi
0x18005cb6b  pop     rsi
0x18005cb6c  retn
```
