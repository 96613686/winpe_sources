# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180008048`
- end: `0x1800080b8`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b960`
- `0x18000bb8c`

## callees

- `0x180008048`
- `0x18000b7d8`
- `0x18000d374`

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
0x180008048  mov     [rsp+arg_0], rbx
0x18000804d  mov     [rsp+arg_8], rsi
0x180008052  push    rdi
0x180008053  sub     rsp, 20h
0x180008057  mov     rbx, r9
0x18000805a  mov     rdi, rcx
0x18000805d  cmp     rcx, rdx
0x180008060  jz      short loc_180008099
0x180008062  test    r8, r8
0x180008065  jz      short loc_180008099
0x180008067  cmp     byte ptr [r8], 0
0x18000806b  jz      short loc_180008099
0x18000806d  mov     rcx, r8; this
0x180008070  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008075  sub     rdx, rdi; DestinationSize
0x180008078  mov     rsi, rax
0x18000807b  cmp     rdx, rax
0x18000807e  jb      short loc_180008099
0x180008080  mov     r9, rax; SourceSize
0x180008083  mov     rcx, rdi; Destination
0x180008086  call    memcpy_s
0x18000808b  test    rbx, rbx
0x18000808e  jz      short loc_180008093
0x180008090  mov     [rbx], rdi
0x180008093  lea     rax, [rsi+rdi]
0x180008097  jmp     short loc_1800080A8
0x180008099  test    rbx, rbx
0x18000809c  jz      short loc_1800080A5
0x18000809e  mov     qword ptr [r9], 0
0x1800080a5  mov     rax, rdi
0x1800080a8  mov     rbx, [rsp+28h+arg_0]
0x1800080ad  mov     rsi, [rsp+28h+arg_8]
0x1800080b2  add     rsp, 20h
0x1800080b6  pop     rdi
0x1800080b7  retn
```
