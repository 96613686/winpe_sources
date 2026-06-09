# CopyString

- ea: `0x18000a380`
- end: `0x18000a3e8`
- name: `CopyString`
- size: `104`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f848`
- `0x1800164cc`
- `0x18003ab24`

## callees

- `0x18000a380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000a3cf`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000a3cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3b8`

## pseudocode

```c
__int64 __fastcall CopyString(char *Source, char a2, char **a3)
{
  __int64 v5; // rax
  rsize_t v6; // rbp
  char *v7; // rax
  char *v8; // rsi

  if ( a2 )
  {
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
  }
  else
  {
    *a3 = Source;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a380  push    rbx
0x18000a382  push    rbp
0x18000a383  push    rsi
0x18000a384  push    rdi
0x18000a385  sub     rsp, 28h
0x18000a389  mov     rbx, r8
0x18000a38c  mov     rdi, rcx
0x18000a38f  test    dl, dl
0x18000a391  jz      short loc_18000A3DA
0x18000a393  test    rbx, rbx
0x18000a396  jz      short loc_18000A3DD
0x18000a398  mov     qword ptr [r8], 0
0x18000a39f  test    rcx, rcx
0x18000a3a2  jz      short loc_18000A3DD
0x18000a3a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a3a8  inc     rax
0x18000a3ab  cmp     byte ptr [rcx+rax], 0
0x18000a3af  jnz     short loc_18000A3A8
0x18000a3b1  lea     rbp, [rax+1]
0x18000a3b5  mov     rcx, rbp; cb
0x18000a3b8  call    cs:__imp_CoTaskMemAlloc
0x18000a3be  mov     rsi, rax
0x18000a3c1  test    rax, rax
0x18000a3c4  jz      short loc_18000A3DD
0x18000a3c6  mov     r8, rdi; Source
0x18000a3c9  mov     rdx, rbp; SizeInBytes
0x18000a3cc  mov     rcx, rax; Destination
0x18000a3cf  call    cs:__imp_strcpy_s
0x18000a3d5  mov     [rbx], rsi
0x18000a3d8  jmp     short loc_18000A3DD
0x18000a3da  mov     [r8], rdi
0x18000a3dd  xor     eax, eax
0x18000a3df  add     rsp, 28h
0x18000a3e3  pop     rdi
0x18000a3e4  pop     rsi
0x18000a3e5  pop     rbp
0x18000a3e6  pop     rbx
0x18000a3e7  retn
```
