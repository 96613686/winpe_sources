# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003630`
- end: `0x1800036a1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004f04`
- `0x18000f650`

## callees

- `0x180003630`
- `0x180004cf8`
- `0x18000596c`

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
0x180003630  mov     [rsp+arg_0], rbx
0x180003635  mov     [rsp+arg_8], rsi
0x18000363a  push    rdi
0x18000363b  sub     rsp, 20h
0x18000363f  mov     rbx, r9
0x180003642  mov     rdi, rcx
0x180003645  cmp     rcx, rdx
0x180003648  jz      short loc_180003681
0x18000364a  test    r8, r8
0x18000364d  jz      short loc_180003681
0x18000364f  cmp     byte ptr [r8], 0
0x180003653  jz      short loc_180003681
0x180003655  mov     rcx, r8; this
0x180003658  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000365d  sub     rdx, rdi; DestinationSize
0x180003660  mov     rsi, rax
0x180003663  cmp     rdx, rax
0x180003666  jb      short loc_180003681
0x180003668  mov     r9, rax; SourceSize
0x18000366b  mov     rcx, rdi; Destination
0x18000366e  call    memcpy_s
0x180003673  test    rbx, rbx
0x180003676  jz      short loc_18000367B
0x180003678  mov     [rbx], rdi
0x18000367b  lea     rax, [rsi+rdi]
0x18000367f  jmp     short loc_180003690
0x180003681  test    rbx, rbx
0x180003684  jz      short loc_18000368D
0x180003686  mov     qword ptr [r9], 0
0x18000368d  mov     rax, rdi
0x180003690  mov     rbx, [rsp+28h+arg_0]
0x180003695  mov     rsi, [rsp+28h+arg_8]
0x18000369a  add     rsp, 20h
0x18000369e  pop     rdi
0x18000369f  retn
```
