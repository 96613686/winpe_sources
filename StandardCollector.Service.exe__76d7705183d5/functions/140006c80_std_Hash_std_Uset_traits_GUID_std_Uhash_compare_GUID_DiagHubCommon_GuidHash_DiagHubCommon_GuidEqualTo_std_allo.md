# std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)

- ea: `0x140006c80`
- end: `0x140006d0f`
- name: `??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z`
- size: `143`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400051d0`
- `0x140005400`
- `0x140005620`
- `0x1400067a8`
- `0x140006bfc`

## callees

- `0x140006c80`
- `0x140014bb6`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
        _QWORD *a1,
        _QWORD *a2,
        const void *a3,
        __int64 a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi

  v5 = a1[3];
  v6 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( 1 )
    {
      if ( !memcmp_0(a3, v8 + 2, 0x10u) )
      {
        *a2 = *v8;
        a2[1] = v8;
        return a2;
      }
      if ( v8 == v9 )
        break;
      v8 = (_QWORD *)v8[1];
    }
    *a2 = v8;
  }
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x140006c80  mov     [rsp+arg_0], rbx
0x140006c85  mov     [rsp+arg_8], rbp
0x140006c8a  mov     [rsp+arg_10], rsi
0x140006c8f  push    rdi
0x140006c90  sub     rsp, 20h
0x140006c94  mov     rax, [rcx+30h]
0x140006c98  mov     rbx, rdx
0x140006c9b  mov     rsi, [rcx+18h]
0x140006c9f  and     rax, r9
0x140006ca2  mov     rdx, [rcx+8]
0x140006ca6  add     rax, rax
0x140006ca9  mov     rbp, r8
0x140006cac  mov     rdi, [rsi+rax*8+8]
0x140006cb1  cmp     rdi, rdx
0x140006cb4  jnz     short loc_140006CC3
0x140006cb6  mov     [rbx], rdx
0x140006cb9  mov     qword ptr [rbx+8], 0
0x140006cc1  jmp     short loc_140006CF2
0x140006cc3  mov     rsi, [rsi+rax*8]
0x140006cc7  jmp     short loc_140006CD2
0x140006cc9  cmp     rdi, rsi
0x140006ccc  jz      short loc_140006D0A
0x140006cce  mov     rdi, [rdi+8]
0x140006cd2  mov     r8d, 10h; Size
0x140006cd8  lea     rdx, [rdi+10h]; Buf2
0x140006cdc  mov     rcx, rbp; Buf1
0x140006cdf  call    memcmp_0
0x140006ce4  test    eax, eax
0x140006ce6  jnz     short loc_140006CC9
0x140006ce8  mov     rax, [rdi]
0x140006ceb  mov     [rbx], rax
0x140006cee  mov     [rbx+8], rdi
0x140006cf2  mov     rbp, [rsp+28h+arg_8]
0x140006cf7  mov     rax, rbx
0x140006cfa  mov     rbx, [rsp+28h+arg_0]
0x140006cff  mov     rsi, [rsp+28h+arg_10]
0x140006d04  add     rsp, 20h
0x140006d08  pop     rdi
0x140006d09  retn
0x140006d0a  mov     [rbx], rdi
0x140006d0d  jmp     short loc_140006CB9
```
