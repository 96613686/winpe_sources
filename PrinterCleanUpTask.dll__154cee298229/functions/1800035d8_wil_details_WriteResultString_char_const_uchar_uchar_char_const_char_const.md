# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800035d8`
- end: `0x180003648`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004e70`
- `0x18000e7a8`

## callees

- `0x1800035d8`
- `0x180004d88`
- `0x180005920`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x1800035d8  mov     [rsp+arg_0], rbx
0x1800035dd  mov     [rsp+arg_8], rsi
0x1800035e2  push    rdi
0x1800035e3  sub     rsp, 20h
0x1800035e7  mov     rbx, r9
0x1800035ea  mov     rdi, rcx
0x1800035ed  cmp     rcx, rdx
0x1800035f0  jz      short loc_180003629
0x1800035f2  test    r8, r8
0x1800035f5  jz      short loc_180003629
0x1800035f7  cmp     byte ptr [r8], 0
0x1800035fb  jz      short loc_180003629
0x1800035fd  mov     rcx, r8; this
0x180003600  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180003605  sub     rdx, rdi; DestinationSize
0x180003608  mov     rsi, rax
0x18000360b  cmp     rdx, rax
0x18000360e  jb      short loc_180003629
0x180003610  mov     r9, rax; SourceSize
0x180003613  mov     rcx, rdi; Destination
0x180003616  call    memcpy_s
0x18000361b  test    rbx, rbx
0x18000361e  jz      short loc_180003623
0x180003620  mov     [rbx], rdi
0x180003623  lea     rax, [rsi+rdi]
0x180003627  jmp     short loc_180003638
0x180003629  test    rbx, rbx
0x18000362c  jz      short loc_180003635
0x18000362e  mov     qword ptr [r9], 0
0x180003635  mov     rax, rdi
0x180003638  mov     rbx, [rsp+28h+arg_0]
0x18000363d  mov     rsi, [rsp+28h+arg_8]
0x180003642  add     rsp, 20h
0x180003646  pop     rdi
0x180003647  retn
```
