# std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(void)

- ea: `0x18001534c`
- end: `0x180015392`
- name: `??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ`
- size: `70`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a5c0`
- `0x18001a784`
- `0x18001b104`
- `0x18001de94`
- `0x18001e634`
- `0x18001f2a0`
- `0x180020704`

## callees

- `0x18001534c`
- `0x180020cdc`

## pseudocode

```c
__int64 *__fastcall std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>,std::_Iterator_base0>::operator++(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 *v4; // r8
  __int64 v5; // rcx
  __int64 i; // rax

  v4 = a1;
  v5 = *a1;
  if ( *(_BYTE *)(*(_QWORD *)(v5 + 16) + 25LL) )
  {
    for ( i = *(_QWORD *)(v5 + 8); !*(_BYTE *)(i + 25) && v5 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
    {
      v5 = i;
      *v4 = i;
    }
  }
  else
  {
    i = std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Min(
          *(_QWORD *)(v5 + 16),
          0,
          v4,
          a4);
  }
  *v4 = i;
  return v4;
}

```

## disassembly

```asm
0x18001534c  sub     rsp, 28h
0x180015350  mov     r8, rcx
0x180015353  xor     edx, edx
0x180015355  mov     rcx, [rcx]
0x180015358  mov     rax, [rcx+10h]
0x18001535c  cmp     [rax+19h], dl
0x18001535f  jz      short loc_18001537E
0x180015361  mov     rax, [rcx+8]
0x180015365  jmp     short loc_180015377
0x180015367  cmp     rcx, [rax+10h]
0x18001536b  jnz     short loc_180015386
0x18001536d  mov     rcx, rax
0x180015370  mov     [r8], rax
0x180015373  mov     rax, [rax+8]
0x180015377  cmp     [rax+19h], dl
0x18001537a  jz      short loc_180015367
0x18001537c  jmp     short loc_180015386
0x18001537e  mov     rcx, rax
0x180015381  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Min(std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x180015386  mov     [r8], rax
0x180015389  mov     rax, r8
0x18001538c  add     rsp, 28h
0x180015390  retn
```
