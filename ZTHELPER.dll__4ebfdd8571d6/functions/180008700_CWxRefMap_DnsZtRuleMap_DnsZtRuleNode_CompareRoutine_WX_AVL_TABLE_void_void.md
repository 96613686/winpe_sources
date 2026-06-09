# CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::_CompareRoutine(_WX_AVL_TABLE *,void *,void *)

- ea: `0x180008700`
- end: `0x18000872d`
- name: `?_CompareRoutine@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@CA?AW4_WX_GENERIC_COMPARE_RESULTS@@PEAU_WX_AVL_TABLE@@PEAX1@Z`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000eb1c`

## pseudocode

```c
__int64 __fastcall CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::_CompareRoutine(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax

  v3 = wcsicmp_ThatWorks(*(PCNZWCH *)(*(_QWORD *)a2 + 16LL), *(PCNZWCH *)(*(_QWORD *)a3 + 16LL));
  return (v3 == 0) + (unsigned int)(v3 >= 0);
}

```

## disassembly

```asm
0x180008700  sub     rsp, 28h
0x180008704  mov     rcx, [rdx]
0x180008707  mov     rdx, [r8]
0x18000870a  mov     rcx, [rcx+10h]; lpString1
0x18000870e  mov     rdx, [rdx+10h]; lpString2
0x180008712  call    wcsicmp_ThatWorks
0x180008717  xor     ecx, ecx
0x180008719  mov     edx, eax
0x18000871b  not     edx
0x18000871d  shr     edx, 1Fh
0x180008720  test    eax, eax
0x180008722  setz    cl
0x180008725  lea     eax, [rcx+rdx]
0x180008728  add     rsp, 28h
0x18000872c  retn
```
