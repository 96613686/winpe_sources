# EventStateTable::Find(_WNF_STATE_NAME)

- ea: `0x180014fec`
- end: `0x1800150a8`
- name: `?Find@EventStateTable@@QEAAPEAVSebRpcEventState@CBroker@@U_WNF_STATE_NAME@@@Z`
- size: `188`
- prototype: `struct CBroker::SebRpcEventState *__fastcall(EventStateTable *__hidden this, struct _WNF_STATE_NAME)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014d60`
- `0x180014e40`
- `0x180015b10`
- `0x1800186b8`

## callees

- `0x180014fec`
- `0x180022434`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18001508f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001508f`
- `ntdll!RtlAcquireSRWLockShared` at `0x180015007`
- `ntdll!RtlAcquireSRWLockShared` at `0x180015007`

## pseudocode

```c
struct CBroker::SebRpcEventState *__fastcall EventStateTable::Find(EventStateTable *this, struct _WNF_STATE_NAME a2)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rdi
  char v5; // cl
  __int64 *v6; // rax
  __int64 v7; // rbx
  struct _WNF_STATE_NAME Buf2; // [rsp+58h] [rbp+10h] BYREF

  Buf2 = a2;
  RtlAcquireSRWLockShared(&stru_180036E10);
  v2 = qword_180036E00;
  v3 = qword_180036E00;
  v4 = *(_QWORD *)(qword_180036E00 + 8);
  if ( !*(_BYTE *)(v4 + 25) )
  {
    do
    {
      if ( memcmp_0((const void *)(v4 + 32), &Buf2, 8u) >= 0 )
      {
        v5 = 0;
        v3 = v4;
      }
      else
      {
        v5 = 1;
      }
      v6 = (__int64 *)(v4 + 16);
      if ( !v5 )
        v6 = (__int64 *)v4;
      v4 = *v6;
    }
    while ( !*(_BYTE *)(*v6 + 25) );
  }
  if ( *(_BYTE *)(v3 + 25) || memcmp_0(&Buf2, (const void *)(v3 + 32), 8u) < 0 )
    v3 = v2;
  if ( v3 == v2 )
    v7 = 0;
  else
    v7 = *(_QWORD *)(v3 + 40);
  RtlReleaseSRWLockShared(&stru_180036E10);
  return (struct CBroker::SebRpcEventState *)v7;
}

```

## disassembly

```asm
0x180014fec  mov     [rsp+arg_0], rbx
0x180014ff1  mov     [rsp+arg_10], rsi
0x180014ff6  mov     [rsp+Buf2], rdx
0x180014ffb  push    rdi
0x180014ffc  sub     rsp, 40h
0x180015000  lea     rcx, stru_180036E10
0x180015007  call    cs:__imp_RtlAcquireSRWLockShared
0x18001500d  mov     rsi, cs:qword_180036E00
0x180015014  xor     eax, eax
0x180015016  mov     [rsp+48h+var_1C], eax
0x18001501a  mov     rbx, rsi
0x18001501d  mov     rdi, [rsi+8]
0x180015021  cmp     [rdi+19h], al
0x180015024  jnz     short loc_18001505A
0x180015026  lea     rcx, [rdi+20h]; Buf1
0x18001502a  mov     r8d, 8; Size
0x180015030  lea     rdx, [rsp+48h+Buf2]; Buf2
0x180015035  call    memcmp_0
0x18001503a  test    eax, eax
0x18001503c  jns     short loc_180015042
0x18001503e  mov     cl, 1
0x180015040  jmp     short loc_180015047
0x180015042  xor     cl, cl
0x180015044  mov     rbx, rdi
0x180015047  test    cl, cl
0x180015049  lea     rax, [rdi+10h]
0x18001504d  cmovz   rax, rdi
0x180015051  mov     rdi, [rax]
0x180015054  cmp     byte ptr [rdi+19h], 0
0x180015058  jz      short loc_180015026
0x18001505a  cmp     byte ptr [rbx+19h], 0
0x18001505e  jnz     short loc_180015078
0x180015060  lea     rdx, [rbx+20h]; Buf2
0x180015064  mov     r8d, 8; Size
0x18001506a  lea     rcx, [rsp+48h+Buf2]; Buf1
0x18001506f  call    memcmp_0
0x180015074  test    eax, eax
0x180015076  jns     short loc_18001507B
0x180015078  mov     rbx, rsi
0x18001507b  cmp     rbx, rsi
0x18001507e  jnz     short loc_180015084
0x180015080  xor     ebx, ebx
0x180015082  jmp     short loc_180015088
0x180015084  mov     rbx, [rbx+28h]
0x180015088  lea     rcx, stru_180036E10
0x18001508f  call    cs:__imp_RtlReleaseSRWLockShared
0x180015095  mov     rsi, [rsp+48h+arg_10]
0x18001509a  mov     rax, rbx
0x18001509d  mov     rbx, [rsp+48h+arg_0]
0x1800150a2  add     rsp, 40h
0x1800150a6  pop     rdi
0x1800150a7  retn
```
