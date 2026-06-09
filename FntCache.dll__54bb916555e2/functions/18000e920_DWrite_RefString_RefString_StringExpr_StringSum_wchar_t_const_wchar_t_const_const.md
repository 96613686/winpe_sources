# DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)

- ea: `0x18000e920`
- end: `0x18000e9d0`
- name: `??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z`
- size: `176`
- prototype: `struct DWrite::RefString::Data **__fastcall(struct DWrite::RefString::Data **, __int64)`
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e0ac`
- `0x1800105b4`
- `0x180041908`
- `0x180067e1c`
- `0x18009772c`
- `0x1800a781c`
- `0x1800a7a44`
- `0x1800a8148`
- `0x1800a92ec`
- `0x1800b0ef8`
- `0x1800b3c24`
- `0x1800b3d58`
- `0x1800b9810`
- `0x1800c2658`
- `0x1800c2794`

## callees

- `0x18000e920`
- `0x18002bf90`
- `0x1800ab0aa`
- `0x1800ab168`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e966`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e99b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e966`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e99b`

## pseudocode

```c
struct DWrite::RefString::Data **__fastcall DWrite::RefString::RefString(
        struct DWrite::RefString::Data **a1,
        __int64 a2)
{
  unsigned __int64 v3; // rbp
  struct DWrite::RefString::Data *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  char *v8; // rdi
  size_t v9; // r8
  void *v10; // rcx
  size_t v11; // r8
  char *v12; // rcx
  const void *v13; // rdx

  v3 = *(_QWORD *)(a2 + 8) + *(_QWORD *)(a2 + 24);
  v5 = DWrite::RefString::NewData(0, v3);
  *a1 = v5;
  v8 = (char *)v5 + 8;
  v9 = 2LL * *(_QWORD *)(a2 + 8);
  if ( v9 )
  {
    if ( v5 == (struct DWrite::RefString::Data *)-8LL )
    {
LABEL_5:
      *(_DWORD *)_o__errno(v7, v6, v9) = 22;
      invalid_parameter_noinfo();
      goto LABEL_6;
    }
    v10 = (char *)v5 + 8;
    if ( !*(_QWORD *)a2 )
    {
      memset_0(v10, 0, v9);
      goto LABEL_5;
    }
    memcpy_0(v10, *(const void **)a2, v9);
  }
LABEL_6:
  v11 = 2LL * *(_QWORD *)(a2 + 24);
  if ( v11 )
  {
    v12 = &v8[2 * *(_QWORD *)(a2 + 8)];
    if ( v12 )
    {
      v13 = *(const void **)(a2 + 16);
      if ( v13 )
      {
        memcpy_0(v12, v13, v11);
        goto LABEL_11;
      }
      memset_0(v12, 0, v11);
    }
    *(_DWORD *)_o__errno(v12, v6, v11) = 22;
    invalid_parameter_noinfo();
  }
LABEL_11:
  *((_WORD *)*a1 + v3 + 4) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000e920  push    rbx
0x18000e922  push    rbp
0x18000e923  push    rsi
0x18000e924  push    rdi
0x18000e925  sub     rsp, 28h
0x18000e929  mov     rbp, [rdx+18h]
0x18000e92d  mov     rbx, rdx
0x18000e930  add     rbp, [rdx+8]
0x18000e934  mov     rsi, rcx
0x18000e937  mov     rdx, rbp; unsigned __int64
0x18000e93a  xor     ecx, ecx; Src
0x18000e93c  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x18000e941  mov     [rsi], rax
0x18000e944  mov     r8, [rbx+8]
0x18000e948  lea     rdi, [rax+8]
0x18000e94c  add     r8, r8; Size
0x18000e94f  jz      short loc_18000E977
0x18000e951  test    rdi, rdi
0x18000e954  jz      short loc_18000E966
0x18000e956  mov     rdx, [rbx]; Val
0x18000e959  mov     rcx, rdi; void *
0x18000e95c  test    rdx, rdx
0x18000e95f  jnz     short loc_18000E9C2
0x18000e961  call    memset_0
0x18000e966  call    cs:__imp__o__errno
0x18000e96c  mov     dword ptr [rax], 16h
0x18000e972  call    _invalid_parameter_noinfo
0x18000e977  mov     r8, [rbx+18h]
0x18000e97b  add     r8, r8; Size
0x18000e97e  jz      short loc_18000E9AC
0x18000e980  mov     rax, [rbx+8]
0x18000e984  lea     rcx, [rdi+rax*2]; void *
0x18000e988  test    rcx, rcx
0x18000e98b  jz      short loc_18000E99B
0x18000e98d  mov     rdx, [rbx+10h]; Val
0x18000e991  test    rdx, rdx
0x18000e994  jnz     short loc_18000E9C9
0x18000e996  call    memset_0
0x18000e99b  call    cs:__imp__o__errno
0x18000e9a1  mov     dword ptr [rax], 16h
0x18000e9a7  call    _invalid_parameter_noinfo
0x18000e9ac  mov     rcx, [rsi]
0x18000e9af  xor     eax, eax
0x18000e9b1  mov     [rcx+rbp*2+8], ax
0x18000e9b6  mov     rax, rsi
0x18000e9b9  add     rsp, 28h
0x18000e9bd  pop     rdi
0x18000e9be  pop     rsi
0x18000e9bf  pop     rbp
0x18000e9c0  pop     rbx
0x18000e9c1  retn
0x18000e9c2  call    memcpy_0
0x18000e9c7  jmp     short loc_18000E977
0x18000e9c9  call    memcpy_0
0x18000e9ce  jmp     short loc_18000E9AC
```
