# Broker::BrokeredEventTable::Find(_BROKERED_EVENT * const &)

- ea: `0x180005a80`
- end: `0x180005b3c`
- name: `?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBQEAU_BROKERED_EVENT@@@Z`
- size: `188`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005390`
- `0x180005580`
- `0x180005a00`
- `0x18000b3cc`

## callees

- `0x180005a80`
- `0x1800165da`

## pseudocode

```c
_QWORD *__fastcall Broker::BrokeredEventTable::Find(__int64 **a1, _QWORD *a2, unsigned __int64 *a3)
{
  __int64 *v3; // r11
  __int64 *v5; // r9
  __int64 *v6; // rax
  unsigned __int64 v7; // r8
  __int64 *v8; // rcx
  __int64 v9; // rax
  void **pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __int128 v12; // [rsp+30h] [rbp-28h]
  int v13; // [rsp+40h] [rbp-18h]

  v3 = *a1;
  DWORD1(v12) = 0;
  v5 = v3;
  v6 = (__int64 *)v3[1];
  if ( !*((_BYTE *)v6 + 25) )
  {
    v7 = *a3;
    do
    {
      v8 = v6 + 2;
      if ( v6[4] >= v7 )
      {
        v8 = v6;
        v5 = v6;
      }
      v6 = (__int64 *)*v8;
    }
    while ( !*(_BYTE *)(*v8 + 25) );
  }
  if ( *((_BYTE *)v5 + 25) || *a3 < v5[4] || v5 == v3 )
  {
    v13 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    v12 = 0;
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v9 = v5[6];
  *a2 = 0;
  a2[1] = 0;
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  *a2 = v5[5];
  a2[1] = v5[6];
  return a2;
}

```

## disassembly

```asm
0x180005a80  mov     [rsp+arg_0], rbx
0x180005a85  push    rdi
0x180005a86  sub     rsp, 50h
0x180005a8a  mov     r11, [rcx]
0x180005a8d  xor     edi, edi
0x180005a8f  xor     ecx, ecx
0x180005a91  mov     rbx, r8
0x180005a94  mov     [rsp+58h+var_24], ecx
0x180005a98  mov     r9, r11
0x180005a9b  mov     rax, [r11+8]
0x180005a9f  cmp     [rax+19h], cl
0x180005aa2  jnz     short loc_180005AC9
0x180005aa4  mov     r8, [r8]
0x180005aa7  nop     word ptr [rax+rax+00000000h]
0x180005ab0  cmp     [rax+20h], r8
0x180005ab4  lea     rcx, [rax+10h]
0x180005ab8  cmovnb  rcx, rax
0x180005abc  cmovnb  r9, rax
0x180005ac0  mov     rax, [rcx]
0x180005ac3  cmp     [rax+19h], dil
0x180005ac7  jz      short loc_180005AB0
0x180005ac9  cmp     [r9+19h], dil
0x180005acd  jnz     short loc_180005B0E
0x180005acf  mov     rax, [r9+20h]
0x180005ad3  cmp     [rbx], rax
0x180005ad6  jb      short loc_180005B0E
0x180005ad8  cmp     r9, r11
0x180005adb  jz      short loc_180005B0E
0x180005add  mov     rax, [r9+30h]
0x180005ae1  mov     [rdx], rdi
0x180005ae4  mov     [rdx+8], rdi
0x180005ae8  test    rax, rax
0x180005aeb  jz      short loc_180005AF1
0x180005aed  lock inc dword ptr [rax+8]
0x180005af1  mov     rax, [r9+28h]
0x180005af5  mov     rbx, [rsp+58h+arg_0]
0x180005afa  mov     [rdx], rax
0x180005afd  mov     rax, [r9+30h]
0x180005b01  mov     [rdx+8], rax
0x180005b05  mov     rax, rdx
0x180005b08  add     rsp, 50h
0x180005b0c  pop     rdi
0x180005b0d  retn
0x180005b0e  xorps   xmm0, xmm0
0x180005b11  mov     [rsp+58h+var_18], 3
0x180005b19  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180005b20  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180005b27  mov     [rsp+58h+pExceptionObject], rax
0x180005b2c  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180005b31  movups  xmmword ptr [rsp+30h], xmm0
0x180005b36  call    _CxxThrowException_0
```
