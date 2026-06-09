# CoTaskMemAllocString

- ea: `0x180006720`
- end: `0x1800067b2`
- name: `CoTaskMemAllocString`
- size: `146`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c8bc`
- `0x18002cac8`
- `0x18002cb84`

## callees

- `0x180006720`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800067a5`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800067a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006764`

## pseudocode

```c
__int64 __fastcall CoTaskMemAllocString(char *Source, char **a2)
{
  __int64 v4; // rax
  rsize_t v6; // rbp
  char *v7; // rax
  char *v8; // rsi

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( !Source )
    return 0;
  v4 = -1;
  while ( Source[++v4] != 0 )
    ;
  v6 = v4 + 1;
  v7 = (char *)CoTaskMemAlloc(v4 + 1);
  v8 = v7;
  if ( v7 )
  {
    strcpy_s(v7, v6, Source);
    *a2 = v8;
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180006720  mov     [rsp+arg_10], rbx
0x180006725  push    rdi
0x180006726  sub     rsp, 20h
0x18000672a  mov     rdi, rdx
0x18000672d  mov     rbx, rcx
0x180006730  test    rdx, rdx
0x180006733  jz      short loc_18000678C
0x180006735  mov     [rsp+28h+arg_0], rbp
0x18000673a  mov     [rsp+28h+arg_8], rsi
0x18000673f  mov     qword ptr [rdx], 0
0x180006746  test    rcx, rcx
0x180006749  jz      short loc_1800067AE
0x18000674b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006752  cmp     byte ptr [rcx+rax+1], 0
0x180006757  lea     rax, [rax+1]
0x18000675b  jnz     short loc_180006752
0x18000675d  lea     rbp, [rax+1]
0x180006761  mov     rcx, rbp; cb
0x180006764  call    cs:__imp_CoTaskMemAlloc
0x18000676a  mov     rsi, rax
0x18000676d  test    rax, rax
0x180006770  jnz     short loc_18000679C
0x180006772  mov     eax, 8007000Eh
0x180006777  mov     rbp, [rsp+28h+arg_0]
0x18000677c  mov     rsi, [rsp+28h+arg_8]
0x180006781  mov     rbx, [rsp+28h+arg_10]
0x180006786  add     rsp, 20h
0x18000678a  pop     rdi
0x18000678b  retn
0x18000678c  mov     rbx, [rsp+28h+arg_10]
0x180006791  mov     eax, 80004003h
0x180006796  add     rsp, 20h
0x18000679a  pop     rdi
0x18000679b  retn
0x18000679c  mov     r8, rbx; Source
0x18000679f  mov     rdx, rbp; SizeInBytes
0x1800067a2  mov     rcx, rsi; Destination
0x1800067a5  call    cs:__imp_strcpy_s
0x1800067ab  mov     [rdi], rsi
0x1800067ae  xor     eax, eax
0x1800067b0  jmp     short loc_180006777
```
