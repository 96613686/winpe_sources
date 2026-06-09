# CopyString_0

- ea: `0x180018d18`
- end: `0x180018d77`
- name: `CopyString_0`
- size: `95`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cd08`
- `0x18000db68`
- `0x18000e9e8`
- `0x180012c2c`
- `0x180012da0`
- `0x180016618`
- `0x18002e798`
- `0x18002e86c`
- `0x18002e940`
- `0x18003366c`

## callees

- `0x180018d18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180018d63`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180018d63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018d4c`

## pseudocode

```c
__int64 __fastcall CopyString_0(char *Source, __int64 a2, char **a3)
{
  __int64 v5; // rax
  rsize_t v6; // rbp
  char *v7; // rax
  char *v8; // rsi

  if ( a3 )
  {
    *a3 = 0;
    if ( Source )
    {
      v5 = -1;
      do
        ++v5;
      while ( Source[v5] );
      v6 = v5 + 1;
      v7 = (char *)CoTaskMemAlloc(v5 + 1);
      v8 = v7;
      if ( v7 )
      {
        strcpy_s(v7, v6, Source);
        *a3 = v8;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018d18  push    rbx
0x180018d1a  push    rbp
0x180018d1b  push    rsi
0x180018d1c  push    rdi
0x180018d1d  sub     rsp, 28h
0x180018d21  mov     rbx, r8
0x180018d24  mov     rdi, rcx
0x180018d27  test    r8, r8
0x180018d2a  jz      short loc_180018D6C
0x180018d2c  mov     qword ptr [r8], 0
0x180018d33  test    rcx, rcx
0x180018d36  jz      short loc_180018D6C
0x180018d38  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018d3c  inc     rax
0x180018d3f  cmp     byte ptr [rcx+rax], 0
0x180018d43  jnz     short loc_180018D3C
0x180018d45  lea     rbp, [rax+1]
0x180018d49  mov     rcx, rbp; cb
0x180018d4c  call    cs:__imp_CoTaskMemAlloc
0x180018d52  mov     rsi, rax
0x180018d55  test    rax, rax
0x180018d58  jz      short loc_180018D6C
0x180018d5a  mov     r8, rdi; Source
0x180018d5d  mov     rdx, rbp; SizeInBytes
0x180018d60  mov     rcx, rax; Destination
0x180018d63  call    cs:__imp_strcpy_s
0x180018d69  mov     [rbx], rsi
0x180018d6c  xor     eax, eax
0x180018d6e  add     rsp, 28h
0x180018d72  pop     rdi
0x180018d73  pop     rsi
0x180018d74  pop     rbp
0x180018d75  pop     rbx
0x180018d76  retn
```
