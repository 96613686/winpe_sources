# CompletionIterator::MoveNext(void)

- ea: `0x180002a00`
- end: `0x180002aa5`
- name: `?MoveNext@CompletionIterator@@UEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CompletionIterator *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000283c`
- `0x180002a00`
- `0x180002dc0`
- `0x180002fcc`

## pseudocode

```c
__int64 __fastcall CompletionIterator::MoveNext(CompletionIterator *this)
{
  char v1; // si
  __int64 result; // rax
  __int64 *v4; // rdi
  unsigned int i; // ebp
  int v6; // eax
  unsigned int v7; // ecx
  char v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v9; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  v9 = 0;
  v8 = 0;
  if ( *((_BYTE *)this + 24) )
  {
    if ( *((_DWORD *)this + 7) != *((_DWORD *)this + 13) )
    {
      v4 = (__int64 *)*((_QWORD *)this + 13);
      for ( i = 0; i < *((_DWORD *)this + 13); ++i )
      {
        if ( !v4 )
          v4 = (__int64 *)*((_QWORD *)this + 10);
        if ( CompletionIterator::IsUnvisitedPositionPredicate((struct PositionData *)(v4 + 2)) )
        {
          v9 = v4;
          v1 = 1;
          break;
        }
        v4 = (__int64 *)*v4;
      }
    }
  }
  else
  {
    result = CompletionIterator::TryGetNextByBaseIterator((__int64)this, (__int64)&v9, &v8);
    if ( (int)result < 0 )
      return result;
    v1 = v8;
  }
  if ( !v1 )
    return 1;
  v6 = CompletionIterator::SetCurrentPosition(this, &v9);
  v7 = 0;
  if ( v6 < 0 )
    return (unsigned int)v6;
  return v7;
}

```

## disassembly

```asm
0x180002a00  mov     rax, rsp
0x180002a03  mov     [rax+18h], rbx
0x180002a07  push    rbp
0x180002a08  push    rsi
0x180002a09  push    rdi
0x180002a0a  sub     rsp, 20h
0x180002a0e  xor     sil, sil
0x180002a11  mov     qword ptr [rax+10h], 0
0x180002a19  mov     rbx, rcx
0x180002a1c  mov     [rax+8], sil
0x180002a20  cmp     [rcx+18h], sil
0x180002a24  jnz     short loc_180002A3E
0x180002a26  lea     r8, [rax+8]
0x180002a2a  lea     rdx, [rax+10h]
0x180002a2e  call    ?TryGetNextByBaseIterator@CompletionIterator@@AEAAJPEAVIterator@?$OrderedSet@VPositionData@@@@PEA_N@Z; CompletionIterator::TryGetNextByBaseIterator(OrderedSet<PositionData>::Iterator *,bool *)
0x180002a33  test    eax, eax
0x180002a35  js      short loc_180002A98
0x180002a37  mov     sil, [rsp+38h+arg_0]
0x180002a3c  jmp     short loc_180002A76
0x180002a3e  mov     eax, [rcx+34h]
0x180002a41  cmp     [rcx+1Ch], eax
0x180002a44  jz      short loc_180002A76
0x180002a46  mov     rdi, [rcx+68h]
0x180002a4a  xor     ebp, ebp
0x180002a4c  cmp     ebp, [rbx+34h]
0x180002a4f  jnb     short loc_180002A76
0x180002a51  test    rdi, rdi
0x180002a54  jnz     short loc_180002A5A
0x180002a56  mov     rdi, [rbx+50h]
0x180002a5a  lea     rcx, [rdi+10h]; struct PositionData *
0x180002a5e  call    ?IsUnvisitedPositionPredicate@CompletionIterator@@CA_NAEAVPositionData@@@Z; CompletionIterator::IsUnvisitedPositionPredicate(PositionData &)
0x180002a63  test    al, al
0x180002a65  jnz     short loc_180002A6E
0x180002a67  mov     rdi, [rdi]
0x180002a6a  inc     ebp
0x180002a6c  jmp     short loc_180002A4C
0x180002a6e  mov     [rsp+38h+arg_8], rdi
0x180002a73  mov     sil, 1
0x180002a76  test    sil, sil
0x180002a79  jnz     short loc_180002A82
0x180002a7b  mov     eax, 1
0x180002a80  jmp     short loc_180002A98
0x180002a82  lea     rdx, [rsp+38h+arg_8]
0x180002a87  mov     rcx, rbx
0x180002a8a  call    ?SetCurrentPosition@CompletionIterator@@AEAAJAEAVIterator@?$OrderedSet@VPositionData@@@@@Z; CompletionIterator::SetCurrentPosition(OrderedSet<PositionData>::Iterator &)
0x180002a8f  xor     ecx, ecx
0x180002a91  test    eax, eax
0x180002a93  cmovs   ecx, eax
0x180002a96  mov     eax, ecx
0x180002a98  mov     rbx, [rsp+38h+arg_10]
0x180002a9d  add     rsp, 20h
0x180002aa1  pop     rdi
0x180002aa2  pop     rsi
0x180002aa3  pop     rbp
0x180002aa4  retn
```
