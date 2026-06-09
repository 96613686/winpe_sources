# std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)

- ea: `0x140010408`
- end: `0x1400104b5`
- name: `??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@VCComBSTR@ATL@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000f9d4`
- `0x140010260`

## callees

- `0x140010408`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14001047a`
- `KERNEL32!CompareStringOrdinal` at `0x14001047a`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(
        __int64 a1,
        _QWORD *a2,
        LPCWCH *a3,
        __int64 a4)
{
  __int64 v6; // rdi
  __int64 v7; // rsi

  v6 = *(_QWORD *)(qword_140024AA8 + 16 * (a4 & qword_140024AC0) + 8);
  if ( v6 == qword_140024A98 )
  {
    *a2 = qword_140024A98;
    a2[1] = 0;
  }
  else
  {
    v7 = *(_QWORD *)(qword_140024AA8 + 16 * (a4 & qword_140024AC0));
    while ( 1 )
    {
      if ( CompareStringOrdinal(*a3, -1, *(LPCWCH *)(v6 + 16), -1, 1) == 2 )
      {
        *a2 = *(_QWORD *)v6;
        a2[1] = v6;
        return a2;
      }
      if ( v6 == v7 )
        break;
      v6 = *(_QWORD *)(v6 + 8);
    }
    *a2 = v6;
    a2[1] = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x140010408  mov     [rsp+arg_0], rbx
0x14001040d  mov     [rsp+arg_8], rsi
0x140010412  mov     [rsp+arg_10], rdi
0x140010417  push    r14
0x140010419  sub     rsp, 30h
0x14001041d  mov     rax, cs:qword_140024AC0
0x140010424  mov     r14, r8
0x140010427  mov     rsi, cs:qword_140024AA8
0x14001042e  and     rax, r9
0x140010431  mov     rcx, cs:qword_140024A98
0x140010438  add     rax, rax
0x14001043b  mov     rbx, rdx
0x14001043e  mov     rdi, [rsi+rax*8+8]
0x140010443  cmp     rdi, rcx
0x140010446  jnz     short loc_140010455
0x140010448  mov     [rdx], rcx
0x14001044b  mov     qword ptr [rdx+8], 0
0x140010453  jmp     short loc_14001048F
0x140010455  mov     rsi, [rsi+rax*8]
0x140010459  jmp     short loc_140010464
0x14001045b  cmp     rdi, rsi
0x14001045e  jz      short loc_1400104A8
0x140010460  mov     rdi, [rdi+8]
0x140010464  mov     r8, [rdi+10h]; lpString2
0x140010468  or      r9d, 0FFFFFFFFh; cchCount2
0x14001046c  mov     rcx, [r14]; lpString1
0x14001046f  or      edx, r9d; cchCount1
0x140010472  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x14001047a  call    cs:__imp_CompareStringOrdinal
0x140010480  cmp     eax, 2
0x140010483  jnz     short loc_14001045B
0x140010485  mov     rax, [rdi]
0x140010488  mov     [rbx], rax
0x14001048b  mov     [rbx+8], rdi
0x14001048f  mov     rsi, [rsp+38h+arg_8]
0x140010494  mov     rax, rbx
0x140010497  mov     rbx, [rsp+38h+arg_0]
0x14001049c  mov     rdi, [rsp+38h+arg_10]
0x1400104a1  add     rsp, 30h
0x1400104a5  pop     r14
0x1400104a7  retn
0x1400104a8  mov     [rbx], rdi
0x1400104ab  mov     qword ptr [rbx+8], 0
0x1400104b3  jmp     short loc_14001048F
```
