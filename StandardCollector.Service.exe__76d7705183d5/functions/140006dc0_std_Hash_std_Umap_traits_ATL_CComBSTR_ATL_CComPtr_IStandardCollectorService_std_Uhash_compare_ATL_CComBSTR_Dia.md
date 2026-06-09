# std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)

- ea: `0x140006dc0`
- end: `0x140006e5c`
- name: `??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005b70`
- `0x14000697c`

## callees

- `0x140006dc0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x140006e29`
- `KERNEL32!CompareStringOrdinal` at `0x140006e29`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(
        _QWORD *a1,
        _QWORD *a2,
        LPCWCH *a3,
        __int64 a4)
{
  __int64 v5; // rsi
  __int64 v6; // rdx
  __int64 v8; // rdi
  __int64 v9; // rsi

  v5 = a1[3];
  v6 = a1[1];
  v8 = *(_QWORD *)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
  }
  else
  {
    v9 = *(_QWORD *)(v5 + 16 * (a4 & a1[6]));
    while ( 1 )
    {
      if ( CompareStringOrdinal(*a3, -1, *(LPCWCH *)(v8 + 16), -1, 1) == 2 )
      {
        *a2 = *(_QWORD *)v8;
        a2[1] = v8;
        return a2;
      }
      if ( v8 == v9 )
        break;
      v8 = *(_QWORD *)(v8 + 8);
    }
    *a2 = v8;
  }
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x140006dc0  mov     [rsp+arg_0], rbx
0x140006dc5  mov     [rsp+arg_8], rsi
0x140006dca  mov     [rsp+arg_10], rdi
0x140006dcf  push    r14
0x140006dd1  sub     rsp, 30h
0x140006dd5  mov     rax, [rcx+30h]
0x140006dd9  mov     rbx, rdx
0x140006ddc  mov     rsi, [rcx+18h]
0x140006de0  and     rax, r9
0x140006de3  mov     rdx, [rcx+8]
0x140006de7  add     rax, rax
0x140006dea  mov     r14, r8
0x140006ded  mov     rdi, [rsi+rax*8+8]
0x140006df2  cmp     rdi, rdx
0x140006df5  jnz     short loc_140006E04
0x140006df7  mov     [rbx], rdx
0x140006dfa  mov     qword ptr [rbx+8], 0
0x140006e02  jmp     short loc_140006E3E
0x140006e04  mov     rsi, [rsi+rax*8]
0x140006e08  jmp     short loc_140006E13
0x140006e0a  cmp     rdi, rsi
0x140006e0d  jz      short loc_140006E57
0x140006e0f  mov     rdi, [rdi+8]
0x140006e13  mov     r8, [rdi+10h]; lpString2
0x140006e17  or      r9d, 0FFFFFFFFh; cchCount2
0x140006e1b  mov     rcx, [r14]; lpString1
0x140006e1e  or      edx, r9d; cchCount1
0x140006e21  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x140006e29  call    cs:__imp_CompareStringOrdinal
0x140006e2f  cmp     eax, 2
0x140006e32  jnz     short loc_140006E0A
0x140006e34  mov     rax, [rdi]
0x140006e37  mov     [rbx], rax
0x140006e3a  mov     [rbx+8], rdi
0x140006e3e  mov     rsi, [rsp+38h+arg_8]
0x140006e43  mov     rax, rbx
0x140006e46  mov     rbx, [rsp+38h+arg_0]
0x140006e4b  mov     rdi, [rsp+38h+arg_10]
0x140006e50  add     rsp, 30h
0x140006e54  pop     r14
0x140006e56  retn
0x140006e57  mov     [rbx], rdi
0x140006e5a  jmp     short loc_140006DFA
```
