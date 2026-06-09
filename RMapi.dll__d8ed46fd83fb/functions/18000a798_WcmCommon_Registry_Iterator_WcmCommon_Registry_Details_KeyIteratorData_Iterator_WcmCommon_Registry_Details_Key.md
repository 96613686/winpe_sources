# WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::Iterator<WcmCommon::Registry::Details::KeyIteratorData>(HKEY__ * const,WcmCommon::Registry::IteratorCreationFlag)

- ea: `0x18000a798`
- end: `0x18000a851`
- name: `??0?$Iterator@UKeyIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@QEAA@QEAUHKEY__@@W4IteratorCreationFlag@12@@Z`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800213d4`

## callees

- `0x18000844c`
- `0x1800093c4`
- `0x18000a798`
- `0x18000a858`
- `0x18000df4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::Iterator<WcmCommon::Registry::Details::KeyIteratorData>(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int v5; // r8d
  __int64 v6; // r9
  unsigned __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r14
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  size_t v12; // rbx

  WcmCommon::Registry::Details::KeyIteratorData::KeyIteratorData((WcmCommon::Registry::Details::KeyIteratorData *)a1);
  *(_QWORD *)a1 = v6;
  v7 = v5 == 0 ? 0x10 : 0;
  v8 = *(_QWORD *)(a1 + 8);
  v9 = *(_QWORD *)(a1 + 16);
  v10 = (v9 - v8) >> 1;
  if ( v7 >= v10 )
  {
    if ( v7 <= v10 )
      goto LABEL_8;
    if ( v7 > (*(_QWORD *)(a1 + 24) - v8) >> 1 )
    {
      std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(a1 + 8, v5 == 0 ? 0x10 : 0);
      goto LABEL_8;
    }
    v12 = 2 * (v7 - v10);
    memset_0(*(void **)(a1 + 16), 0, v12);
    v11 = v12 + v9;
  }
  else
  {
    v11 = v8 + 2 * v7;
  }
  *(_QWORD *)(a1 + 16) = v11;
LABEL_8:
  *(_DWORD *)(a1 + 32) = -(a3 != 0);
  if ( !a3 )
    WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::enumerateNext(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a798  mov     [rsp+arg_8], rbx
0x18000a79d  mov     [rsp+arg_10], rbp
0x18000a7a2  push    rsi
0x18000a7a3  push    rdi
0x18000a7a4  push    r14
0x18000a7a6  sub     rsp, 30h
0x18000a7aa  mov     ebp, r8d
0x18000a7ad  mov     r9, rdx
0x18000a7b0  mov     rdi, rcx
0x18000a7b3  mov     [rsp+48h+var_28], rcx
0x18000a7b8  call    ??0KeyIteratorData@Details@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Details::KeyIteratorData::KeyIteratorData(void)
0x18000a7bd  nop
0x18000a7be  mov     [rdi], r9
0x18000a7c1  mov     eax, r8d
0x18000a7c4  neg     eax
0x18000a7c6  sbb     rbx, rbx
0x18000a7c9  not     rbx
0x18000a7cc  and     ebx, 10h
0x18000a7cf  mov     rdx, [rdi+8]
0x18000a7d3  mov     r14, [rdi+10h]
0x18000a7d7  mov     rcx, r14
0x18000a7da  sub     rcx, rdx
0x18000a7dd  sar     rcx, 1
0x18000a7e0  cmp     rbx, rcx
0x18000a7e3  jnb     short loc_18000A7EB
0x18000a7e5  lea     rax, [rdx+rbx*2]
0x18000a7e9  jmp     short loc_18000A821
0x18000a7eb  jbe     short loc_18000A825
0x18000a7ed  mov     rax, [rdi+18h]
0x18000a7f1  sub     rax, rdx
0x18000a7f4  sar     rax, 1
0x18000a7f7  cmp     rbx, rax
0x18000a7fa  jbe     short loc_18000A80A
0x18000a7fc  mov     rdx, rbx
0x18000a7ff  lea     rcx, [rdi+8]
0x18000a803  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000a808  jmp     short loc_18000A825
0x18000a80a  sub     rbx, rcx
0x18000a80d  add     rbx, rbx
0x18000a810  mov     r8, rbx; Size
0x18000a813  xor     edx, edx; Val
0x18000a815  mov     rcx, r14; void *
0x18000a818  call    memset_0
0x18000a81d  lea     rax, [rbx+r14]
0x18000a821  mov     [rdi+10h], rax
0x18000a825  mov     ecx, ebp
0x18000a827  neg     ecx
0x18000a829  sbb     edx, edx
0x18000a82b  mov     [rdi+20h], edx
0x18000a82e  test    ebp, ebp
0x18000a830  jnz     short loc_18000A83B
0x18000a832  mov     rcx, rdi
0x18000a835  call    ?enumerateNext@?$Iterator@UKeyIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@AEAAXXZ; WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::enumerateNext(void)
0x18000a83a  nop
0x18000a83b  mov     rax, rdi
0x18000a83e  mov     rbx, [rsp+48h+arg_8]
0x18000a843  mov     rbp, [rsp+48h+arg_10]
0x18000a848  add     rsp, 30h
0x18000a84c  pop     r14
0x18000a84e  pop     rdi
0x18000a84f  pop     rsi
0x18000a850  retn
```
