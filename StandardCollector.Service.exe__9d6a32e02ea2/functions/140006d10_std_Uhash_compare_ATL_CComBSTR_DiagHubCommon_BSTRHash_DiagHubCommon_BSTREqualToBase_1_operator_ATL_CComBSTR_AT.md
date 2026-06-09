# std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(ATL::CComBSTR const &)

- ea: `0x140006d10`
- end: `0x140006dbe`
- name: `??$?RVCComBSTR@ATL@@@?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@QEBA_KAEBVCComBSTR@ATL@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, BSTR *)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005b70`
- `0x14000697c`
- `0x140007144`
- `0x14000f9d4`
- `0x140010260`
- `0x140010570`

## callees

- `0x140006d10`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x140006d25`
- `OLEAUT32!__imp_SysStringLen` at `0x140006d25`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(
        __int64 a1,
        BSTR *a2)
{
  BSTR v2; // rbx
  UINT v3; // eax
  __int64 v4; // r11
  __int64 v5; // r9
  OLECHAR *v6; // r8
  OLECHAR *v7; // r10
  __int64 v8; // rcx
  unsigned __int64 i; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 j; // rdx
  __int64 v13; // rax

  v2 = *a2;
  v3 = SysStringLen(*a2);
  v4 = v3;
  v5 = 0;
  v6 = v2;
  v7 = &v2[4 * ((unsigned __int64)(2 * v3) >> 3)];
  if ( v2 != v7 )
  {
    do
    {
      v8 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 8; ++i )
      {
        v10 = *((unsigned __int8 *)v6 + i);
        v8 = 0x100000001B3LL * (v10 ^ v8);
      }
      v5 ^= v8;
      v6 += 4;
    }
    while ( v6 != v7 );
  }
  while ( v6 != &v2[v4] )
  {
    v11 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 2; ++j )
    {
      v13 = *((unsigned __int8 *)v6 + j);
      v11 = 0x100000001B3LL * (v13 ^ v11);
    }
    v5 ^= v11;
    ++v6;
  }
  return v5;
}

```

## disassembly

```asm
0x140006d10  mov     [rsp+arg_0], rbx
0x140006d15  mov     [rsp+arg_8], rsi
0x140006d1a  push    rdi
0x140006d1b  sub     rsp, 20h
0x140006d1f  mov     rbx, [rdx]
0x140006d22  mov     rcx, rbx; pbstr
0x140006d25  call    cs:__imp_SysStringLen
0x140006d2b  mov     r11d, eax
0x140006d2e  xor     r9d, r9d
0x140006d31  mov     r8, rbx
0x140006d34  mov     rdi, 0CBF29CE484222325h
0x140006d3e  mov     rsi, 100000001B3h
0x140006d48  lea     edx, [r11+r11]
0x140006d4c  shr     rdx, 3
0x140006d50  lea     r10, [rbx+rdx*8]
0x140006d54  cmp     rbx, r10
0x140006d57  jz      short loc_140006D7F
0x140006d59  mov     rcx, rdi
0x140006d5c  xor     edx, edx
0x140006d5e  movzx   eax, byte ptr [r8+rdx]
0x140006d63  inc     rdx
0x140006d66  xor     rcx, rax
0x140006d69  imul    rcx, rsi
0x140006d6d  cmp     rdx, 8
0x140006d71  jb      short loc_140006D5E
0x140006d73  xor     r9, rcx
0x140006d76  add     r8, 8
0x140006d7a  cmp     r8, r10
0x140006d7d  jnz     short loc_140006D59
0x140006d7f  lea     r10, [rbx+r11*2]
0x140006d83  jmp     short loc_140006DA6
0x140006d85  mov     rcx, rdi
0x140006d88  xor     edx, edx
0x140006d8a  movzx   eax, byte ptr [r8+rdx]
0x140006d8f  inc     rdx
0x140006d92  xor     rcx, rax
0x140006d95  imul    rcx, rsi
0x140006d99  cmp     rdx, 2
0x140006d9d  jb      short loc_140006D8A
0x140006d9f  xor     r9, rcx
0x140006da2  add     r8, 2
0x140006da6  cmp     r8, r10
0x140006da9  jnz     short loc_140006D85
0x140006dab  mov     rbx, [rsp+28h+arg_0]
0x140006db0  mov     rax, r9
0x140006db3  mov     rsi, [rsp+28h+arg_8]
0x140006db8  add     rsp, 20h
0x140006dbc  pop     rdi
0x140006dbd  retn
```
