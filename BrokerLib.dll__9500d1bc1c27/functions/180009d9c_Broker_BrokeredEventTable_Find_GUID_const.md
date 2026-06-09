# Broker::BrokeredEventTable::Find(_GUID const &)

- ea: `0x180009d9c`
- end: `0x180009e8d`
- name: `?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBU_GUID@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009bb0`
- `0x18001854c`
- `0x1800187b8`
- `0x180018ec0`

## callees

- `0x180009d9c`
- `0x18001659e`
- `0x1800165da`

## pseudocode

```c
_QWORD *__fastcall Broker::BrokeredEventTable::Find(__int64 a1, _QWORD *a2, const void *a3)
{
  __int64 *v3; // rbp
  __int64 *v6; // rbx
  __int64 *v7; // rsi
  char v8; // cl
  __int64 *v9; // rax
  __int64 v11; // rax
  void **pExceptionObject; // [rsp+28h] [rbp-50h] BYREF
  __int128 v14; // [rsp+30h] [rbp-48h]
  int v15; // [rsp+40h] [rbp-38h]

  v3 = *(__int64 **)(a1 + 16);
  DWORD1(v14) = 0;
  v6 = v3;
  v7 = (__int64 *)v3[1];
  if ( !*((_BYTE *)v7 + 25) )
  {
    do
    {
      if ( memcmp_0(v7 + 4, a3, 0x10u) < 0 )
      {
        v8 = 1;
      }
      else
      {
        v8 = 0;
        v6 = v7;
      }
      v9 = v7 + 2;
      if ( !v8 )
        v9 = v7;
      v7 = (__int64 *)*v9;
    }
    while ( !*(_BYTE *)(*v9 + 25) );
  }
  if ( *((_BYTE *)v6 + 25) || memcmp_0(a3, v6 + 4, 0x10u) < 0 )
    v6 = v3;
  if ( v6 == v3 )
  {
    v15 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    v14 = 0;
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v11 = v6[7];
  *a2 = 0;
  a2[1] = 0;
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *a2 = v6[6];
  a2[1] = v6[7];
  return a2;
}

```

## disassembly

```asm
0x180009d9c  push    rbx
0x180009d9e  push    rbp
0x180009d9f  push    rsi
0x180009da0  push    rdi
0x180009da1  push    r14
0x180009da3  sub     rsp, 50h
0x180009da7  mov     rbp, [rcx+10h]
0x180009dab  xor     eax, eax
0x180009dad  mov     r14, r8
0x180009db0  mov     [rsp+78h+var_44], eax
0x180009db4  mov     rdi, rdx
0x180009db7  mov     rbx, rbp
0x180009dba  mov     rsi, [rbp+8]
0x180009dbe  cmp     [rsi+19h], al
0x180009dc1  jnz     short loc_180009DF1
0x180009dc3  lea     rcx, [rsi+20h]; Buf1
0x180009dc7  mov     r8d, 10h; Size
0x180009dcd  mov     rdx, r14; Buf2
0x180009dd0  call    memcmp_0
0x180009dd5  test    eax, eax
0x180009dd7  js      short loc_180009E57
0x180009dd9  xor     cl, cl
0x180009ddb  mov     rbx, rsi
0x180009dde  test    cl, cl
0x180009de0  lea     rax, [rsi+10h]
0x180009de4  cmovz   rax, rsi
0x180009de8  mov     rsi, [rax]
0x180009deb  cmp     byte ptr [rsi+19h], 0
0x180009def  jz      short loc_180009DC3
0x180009df1  cmp     byte ptr [rbx+19h], 0
0x180009df5  jnz     loc_180009E89
0x180009dfb  lea     rdx, [rbx+20h]; Buf2
0x180009dff  mov     r8d, 10h; Size
0x180009e05  mov     rcx, r14; Buf1
0x180009e08  call    memcmp_0
0x180009e0d  test    eax, eax
0x180009e0f  js      short loc_180009E89
0x180009e11  mov     al, 1
0x180009e13  test    al, al
0x180009e15  cmovz   rbx, rbp
0x180009e19  cmp     rbx, rbp
0x180009e1c  jz      short loc_180009E5B
0x180009e1e  mov     rax, [rbx+38h]
0x180009e22  mov     qword ptr [rdi], 0
0x180009e29  mov     qword ptr [rdi+8], 0
0x180009e31  test    rax, rax
0x180009e34  jz      short loc_180009E3A
0x180009e36  lock inc dword ptr [rax+8]
0x180009e3a  mov     rax, [rbx+30h]
0x180009e3e  mov     [rdi], rax
0x180009e41  mov     rax, [rbx+38h]
0x180009e45  mov     [rdi+8], rax
0x180009e49  mov     rax, rdi
0x180009e4c  add     rsp, 50h
0x180009e50  pop     r14
0x180009e52  pop     rdi
0x180009e53  pop     rsi
0x180009e54  pop     rbp
0x180009e55  pop     rbx
0x180009e56  retn
0x180009e57  mov     cl, 1
0x180009e59  jmp     short loc_180009DDE
0x180009e5b  xorps   xmm0, xmm0
0x180009e5e  mov     [rsp+78h+var_38], 3
0x180009e66  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180009e6d  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180009e74  mov     [rsp+78h+pExceptionObject], rax
0x180009e79  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180009e7e  movups  xmmword ptr [rsp+30h], xmm0
0x180009e83  call    _CxxThrowException_0
0x180009e89  xor     al, al
0x180009e8b  jmp     short loc_180009E13
```
