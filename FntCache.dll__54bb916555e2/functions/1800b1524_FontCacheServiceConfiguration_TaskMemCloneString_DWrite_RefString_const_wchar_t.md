# FontCacheServiceConfiguration::TaskMemCloneString(DWrite::RefString const &,wchar_t * *)

- ea: `0x1800b1524`
- end: `0x1800b1576`
- name: `?TaskMemCloneString@FontCacheServiceConfiguration@@CAJAEBVRefString@DWrite@@PEAPEA_W@Z`
- size: `82`
- prototype: `__int64 __fastcall(const struct DWrite::RefString *, wchar_t **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b10f0`
- `0x1800b1150`
- `0x1800b11b0`

## callees

- `0x1800ab168`
- `0x1800b1524`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b153e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b153e`

## pseudocode

```c
__int64 __fastcall FontCacheServiceConfiguration::TaskMemCloneString(const struct DWrite::RefString *a1, wchar_t **a2)
{
  __int64 v2; // rbp
  size_t v4; // rsi
  wchar_t *v5; // rax
  wchar_t *v6; // rdi

  v2 = *(_QWORD *)a1;
  v4 = 2LL * *(unsigned int *)(*(_QWORD *)a1 + 4LL);
  v5 = (wchar_t *)CoTaskMemAlloc(v4 + 2);
  *a2 = v5;
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  memcpy_0(v5, (const void *)(v2 + 8), v4);
  v6[v4 / 2] = 0;
  return 0;
}

```

## disassembly

```asm
0x1800b1524  push    rbx
0x1800b1526  push    rbp
0x1800b1527  push    rsi
0x1800b1528  push    rdi
0x1800b1529  sub     rsp, 28h
0x1800b152d  mov     rbp, [rcx]
0x1800b1530  mov     rbx, rdx
0x1800b1533  mov     eax, [rbp+4]
0x1800b1536  lea     rsi, [rax+rax]
0x1800b153a  lea     rcx, [rsi+2]; cb
0x1800b153e  call    cs:__imp_CoTaskMemAlloc
0x1800b1544  mov     [rbx], rax
0x1800b1547  mov     rdi, rax
0x1800b154a  test    rax, rax
0x1800b154d  jz      short loc_1800B1568
0x1800b154f  lea     rdx, [rbp+8]; Src
0x1800b1553  mov     r8, rsi; Size
0x1800b1556  mov     rcx, rax; void *
0x1800b1559  call    memcpy_0
0x1800b155e  xor     ecx, ecx
0x1800b1560  mov     [rsi+rdi], cx
0x1800b1564  xor     eax, eax
0x1800b1566  jmp     short loc_1800B156D
0x1800b1568  mov     eax, 8007000Eh
0x1800b156d  add     rsp, 28h
0x1800b1571  pop     rdi
0x1800b1572  pop     rsi
0x1800b1573  pop     rbp
0x1800b1574  pop     rbx
0x1800b1575  retn
```
