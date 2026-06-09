# Broker::BrokerEventTable<CBroker::SebEvent>::Find(_GUID const &)

- ea: `0x18000cb50`
- end: `0x18000cc34`
- name: `?Find@?$BrokerEventTable@VSebEvent@CBroker@@@Broker@@QEAA?AV?$shared_ptr@VSebEvent@CBroker@@@std@@AEBU_GUID@@@Z`
- size: `228`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *, const void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009740`
- `0x18000b3d0`
- `0x18001bcdc`
- `0x18001be34`

## callees

- `0x18000cb50`
- `0x18001d9ac`
- `0x180022434`

## pseudocode

```c
_QWORD *__fastcall Broker::BrokerEventTable<CBroker::SebEvent>::Find(__int64 **a1, _QWORD *a2, const void *a3)
{
  __int64 *v3; // rbp
  __int64 *v6; // rsi
  __int64 *v7; // rbx
  char v8; // cl
  __int64 *v9; // rax
  __int64 v10; // rax
  void **pExceptionObject; // [rsp+28h] [rbp-60h] BYREF
  __int128 v13; // [rsp+30h] [rbp-58h]
  int v14; // [rsp+40h] [rbp-48h]

  v3 = *a1;
  DWORD1(v13) = 0;
  v6 = v3;
  v7 = (__int64 *)v3[1];
  if ( !*((_BYTE *)v7 + 25) )
  {
    do
    {
      if ( memcmp_0(v7 + 4, a3, 0x10u) >= 0 )
      {
        v8 = 0;
        v6 = v7;
      }
      else
      {
        v8 = 1;
      }
      v9 = v7 + 2;
      if ( !v8 )
        v9 = v7;
      v7 = (__int64 *)*v9;
    }
    while ( !*(_BYTE *)(*v9 + 25) );
  }
  if ( *((_BYTE *)v6 + 25) || memcmp_0(a3, v6 + 4, 0x10u) < 0 || v6 == v3 )
  {
    v14 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    v13 = 0;
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v10 = v6[7];
  *a2 = 0;
  a2[1] = 0;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  *a2 = v6[6];
  a2[1] = v6[7];
  return a2;
}

```

## disassembly

```asm
0x18000cb50  push    rbx
0x18000cb52  push    rbp
0x18000cb53  push    rsi
0x18000cb54  push    rdi
0x18000cb55  push    r14
0x18000cb57  push    r15
0x18000cb59  sub     rsp, 58h
0x18000cb5d  mov     rbp, [rcx]
0x18000cb60  xor     eax, eax
0x18000cb62  xor     r15d, r15d
0x18000cb65  mov     [rsp+88h+var_54], eax
0x18000cb69  mov     rdi, r8
0x18000cb6c  mov     r14, rdx
0x18000cb6f  mov     rsi, rbp
0x18000cb72  mov     rbx, [rbp+8]
0x18000cb76  cmp     [rbx+19h], al
0x18000cb79  jnz     short loc_18000CBAB
0x18000cb7b  nop     dword ptr [rax+rax+00h]
0x18000cb80  lea     rcx, [rbx+20h]; Buf1
0x18000cb84  mov     r8d, 10h; Size
0x18000cb8a  mov     rdx, rdi; Buf2
0x18000cb8d  call    memcmp_0
0x18000cb92  test    eax, eax
0x18000cb94  jns     short loc_18000CBFF
0x18000cb96  mov     cl, 1
0x18000cb98  test    cl, cl
0x18000cb9a  lea     rax, [rbx+10h]
0x18000cb9e  cmovz   rax, rbx
0x18000cba2  mov     rbx, [rax]
0x18000cba5  cmp     [rbx+19h], r15b
0x18000cba9  jz      short loc_18000CB80
0x18000cbab  cmp     [rsi+19h], r15b
0x18000cbaf  jnz     short loc_18000CC06
0x18000cbb1  lea     rdx, [rsi+20h]; Buf2
0x18000cbb5  mov     r8d, 10h; Size
0x18000cbbb  mov     rcx, rdi; Buf1
0x18000cbbe  call    memcmp_0
0x18000cbc3  test    eax, eax
0x18000cbc5  js      short loc_18000CC06
0x18000cbc7  cmp     rsi, rbp
0x18000cbca  jz      short loc_18000CC06
0x18000cbcc  mov     rax, [rsi+38h]
0x18000cbd0  mov     [r14], r15
0x18000cbd3  mov     [r14+8], r15
0x18000cbd7  test    rax, rax
0x18000cbda  jz      short loc_18000CBE0
0x18000cbdc  lock inc dword ptr [rax+8]
0x18000cbe0  mov     rax, [rsi+30h]
0x18000cbe4  mov     [r14], rax
0x18000cbe7  mov     rax, [rsi+38h]
0x18000cbeb  mov     [r14+8], rax
0x18000cbef  mov     rax, r14
0x18000cbf2  add     rsp, 58h
0x18000cbf6  pop     r15
0x18000cbf8  pop     r14
0x18000cbfa  pop     rdi
0x18000cbfb  pop     rsi
0x18000cbfc  pop     rbp
0x18000cbfd  pop     rbx
0x18000cbfe  retn
0x18000cbff  xor     cl, cl
0x18000cc01  mov     rsi, rbx
0x18000cc04  jmp     short loc_18000CB98
0x18000cc06  xorps   xmm0, xmm0
0x18000cc09  mov     [rsp+88h+var_48], 3
0x18000cc11  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000cc18  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x18000cc1f  mov     [rsp+88h+pExceptionObject], rax
0x18000cc24  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000cc29  movups  xmmword ptr [rsp+30h], xmm0
0x18000cc2e  call    _CxxThrowException_0
```
