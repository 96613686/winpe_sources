# CopyString_1

- ea: `0x18004ec34`
- end: `0x18004ec93`
- name: `CopyString_1`
- size: `95`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e8ec`

## callees

- `0x18004ec34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18004ec7f`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18004ec7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ec68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ec68`

## pseudocode

```c
__int64 __fastcall CopyString_1(char *Source, __int64 a2, char **a3)
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
0x18004ec34  push    rbx
0x18004ec36  push    rbp
0x18004ec37  push    rsi
0x18004ec38  push    rdi
0x18004ec39  sub     rsp, 28h
0x18004ec3d  mov     rbx, r8
0x18004ec40  mov     rdi, rcx
0x18004ec43  test    r8, r8
0x18004ec46  jz      short loc_18004EC88
0x18004ec48  mov     qword ptr [r8], 0
0x18004ec4f  test    rcx, rcx
0x18004ec52  jz      short loc_18004EC88
0x18004ec54  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ec58  inc     rax
0x18004ec5b  cmp     byte ptr [rcx+rax], 0
0x18004ec5f  jnz     short loc_18004EC58
0x18004ec61  lea     rbp, [rax+1]
0x18004ec65  mov     rcx, rbp; cb
0x18004ec68  call    cs:__imp_CoTaskMemAlloc
0x18004ec6e  mov     rsi, rax
0x18004ec71  test    rax, rax
0x18004ec74  jz      short loc_18004EC88
0x18004ec76  mov     r8, rdi; Source
0x18004ec79  mov     rdx, rbp; SizeInBytes
0x18004ec7c  mov     rcx, rax; Destination
0x18004ec7f  call    cs:__imp_strcpy_s
0x18004ec85  mov     [rbx], rsi
0x18004ec88  xor     eax, eax
0x18004ec8a  add     rsp, 28h
0x18004ec8e  pop     rdi
0x18004ec8f  pop     rsi
0x18004ec90  pop     rbp
0x18004ec91  pop     rbx
0x18004ec92  retn
```
