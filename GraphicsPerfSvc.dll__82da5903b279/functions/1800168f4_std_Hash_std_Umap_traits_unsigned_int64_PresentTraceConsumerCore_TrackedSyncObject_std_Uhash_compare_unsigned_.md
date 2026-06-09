# std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)

- ea: `0x1800168f4`
- end: `0x180016948`
- name: `??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KUTrackedSyncObject@PresentTraceConsumerCore@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KUTrackedSyncObject@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@AEB_K_K@Z`
- size: `84`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001740c`
- `0x180019050`
- `0x18001c7e4`
- `0x18002833c`

## callees

- `0x1800168f4`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned __int64,PresentTraceConsumerCore::TrackedSyncObject,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::TrackedSyncObject>>,0>>::_Find_last<unsigned __int64>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v4; // r11
  _QWORD *v5; // r10
  __int64 v6; // rax
  _QWORD *v7; // r9

  v4 = a1[3];
  v5 = (_QWORD *)a1[1];
  v6 = 2 * (a4 & a1[6]);
  v7 = *(_QWORD **)(v4 + 16 * (a4 & a1[6]) + 8);
  if ( v7 == v5 )
  {
    *a2 = v5;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    while ( *a3 != v7[2] )
    {
      if ( v7 == *(_QWORD **)(v4 + 8 * v6) )
      {
        *a2 = v7;
        goto LABEL_3;
      }
      v7 = (_QWORD *)v7[1];
    }
    *a2 = *v7;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x1800168f4  mov     rax, [rcx+30h]
0x1800168f8  mov     r11, [rcx+18h]
0x1800168fc  and     rax, r9
0x1800168ff  mov     r10, [rcx+8]
0x180016903  add     rax, rax
0x180016906  mov     r9, [r11+rax*8+8]
0x18001690b  cmp     r9, r10
0x18001690e  jnz     short loc_18001691D
0x180016910  mov     [rdx], r10
0x180016913  mov     qword ptr [rdx+8], 0
0x18001691b  jmp     short loc_180016944
0x18001691d  mov     rcx, [r11+rax*8]
0x180016921  mov     rax, [r8]
0x180016924  cmp     rax, [r9+10h]
0x180016928  jz      short loc_18001693A
0x18001692a  cmp     r9, rcx
0x18001692d  jz      short loc_180016935
0x18001692f  mov     r9, [r9+8]
0x180016933  jmp     short loc_180016924
0x180016935  mov     [rdx], r9
0x180016938  jmp     short loc_180016913
0x18001693a  mov     rax, [r9]
0x18001693d  mov     [rdx], rax
0x180016940  mov     [rdx+8], r9
0x180016944  mov     rax, rdx
0x180016947  retn
```
