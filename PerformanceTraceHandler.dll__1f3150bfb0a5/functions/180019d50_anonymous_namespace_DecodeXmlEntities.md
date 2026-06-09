# _anonymous_namespace_::DecodeXmlEntities

- ea: `0x180019d50`
- end: `0x180019e0a`
- name: `_anonymous_namespace_::DecodeXmlEntities`
- size: `186`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180019e10`

## callees

- `0x180002700`
- `0x180018e14`
- `0x180019214`
- `0x180019d50`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::DecodeXmlEntities(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v3; // rsi
  __int64 v4; // r8
  unsigned __int64 v5; // rcx
  __int64 v6; // r14
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rsi

  v3 = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::_Construct<2,unsigned short const *>(a1, a2, v4);
  while ( 1 )
  {
    v5 = *(_QWORD *)(a1 + 16);
    v6 = *(_QWORD *)(a1 + 24) <= 7u ? a1 : *(_QWORD *)a1;
    if ( v5 < 5 )
      break;
    if ( v3 > v5 - 5 )
      break;
    v7 = v6 + 2 * v5;
    v8 = _std_search_2(v6 + 2 * v3, v7, L"&amp;", 5);
    if ( v8 == v7 )
      break;
    v11 = (v8 - v6) >> 1;
    if ( v11 == -1 )
      break;
    std::wstring::_Replace<unsigned short>(a1, v11, v9, v10, 1);
    v3 = v11 + 1;
  }
  return a1;
}

```

## disassembly

```asm
0x180019d50  mov     [rsp+arg_0], rcx
0x180019d55  push    rbx
0x180019d56  push    rsi
0x180019d57  push    rdi
0x180019d58  push    r14
0x180019d5a  sub     rsp, 48h
0x180019d5e  mov     rdi, rcx
0x180019d61  xor     esi, esi
0x180019d63  mov     [rsp+68h+var_38], esi
0x180019d67  xorps   xmm0, xmm0
0x180019d6a  movups  xmmword ptr [rcx], xmm0
0x180019d6d  mov     [rcx+10h], rsi
0x180019d71  mov     [rcx+18h], rsi
0x180019d75  mov     r8, [rdx+10h]
0x180019d79  cmp     qword ptr [rdx+18h], 7
0x180019d7e  jbe     short loc_180019D83
0x180019d80  mov     rdx, [rdx]
0x180019d83  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180019d88  mov     [rsp+68h+var_38], 1
0x180019d90  mov     rcx, [rdi+10h]
0x180019d94  cmp     qword ptr [rdi+18h], 7
0x180019d99  jbe     short loc_180019DA0
0x180019d9b  mov     r14, [rdi]
0x180019d9e  jmp     short loc_180019DA3
0x180019da0  mov     r14, rdi
0x180019da3  cmp     rcx, 5
0x180019da7  jb      short loc_180019DFC
0x180019da9  lea     rax, [rcx-5]
0x180019dad  cmp     rsi, rax
0x180019db0  ja      short loc_180019DFC
0x180019db2  lea     rbx, [r14+rcx*2]
0x180019db6  lea     rcx, [r14+rsi*2]
0x180019dba  mov     r9d, 5
0x180019dc0  lea     r8, aAmp; "&amp;"
0x180019dc7  mov     rdx, rbx
0x180019dca  call    __std_search_2
0x180019dcf  mov     rsi, rax
0x180019dd2  cmp     rax, rbx
0x180019dd5  jz      short loc_180019DFC
0x180019dd7  sub     rsi, r14
0x180019dda  sar     rsi, 1
0x180019ddd  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180019de1  jz      short loc_180019DFC
0x180019de3  mov     [rsp+68h+var_48], 1
0x180019dec  mov     rdx, rsi
0x180019def  mov     rcx, rdi
0x180019df2  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180019df7  inc     rsi
0x180019dfa  jmp     short loc_180019D90
0x180019dfc  mov     rax, rdi
0x180019dff  add     rsp, 48h
0x180019e03  pop     r14
0x180019e05  pop     rdi
0x180019e06  pop     rsi
0x180019e07  pop     rbx
0x180019e08  retn
```
