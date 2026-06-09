# FwDeleteAllSets

- ea: `0x18002ef50`
- end: `0x18002f02c`
- name: `FwDeleteAllSets`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x1800165e8`
- `0x18001e9ac`
- `0x18002ef50`

## import_xrefs

- `fwbase!FwRegDeleteKey` at `0x18002efd9`
- `fwbase!FwRegDeleteKey` at `0x18002efd9`

## pseudocode

```c
__int64 __fastcall FwDeleteAllSets(__int64 a1, int a2, int a3)
{
  unsigned int v6; // ebx
  __int64 AppropiateSetHive; // rbp
  unsigned int i; // edi
  __int64 v9; // rax
  unsigned int v10; // eax

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v6 = 0;
  if ( a2 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  AppropiateSetHive = FwGetAppropiateSetHive(a1, a2);
  for ( i = 0; i < *(_DWORD *)AppropiateSetHive; ++i )
  {
    v9 = *(_QWORD *)(AppropiateSetHive + 8);
    if ( *(_DWORD *)(v9 + 16LL * i + 8) == (a3 != 1) + 6 )
    {
      v10 = FwRegDeleteKey(*(_QWORD *)(a1 + 40), *(_QWORD *)(v9 + 16LL * i));
      v6 = 0;
      if ( v10 != -2147024894 )
        v6 = v10;
      if ( (v6 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 345, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v6);
        return v6;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002ef50  push    rbx
0x18002ef52  push    rbp
0x18002ef53  push    rsi
0x18002ef54  push    rdi
0x18002ef55  push    r12
0x18002ef57  push    r14
0x18002ef59  push    r15
0x18002ef5b  sub     rsp, 20h
0x18002ef5f  mov     r14d, r8d
0x18002ef62  mov     edi, edx
0x18002ef64  mov     r15, rcx
0x18002ef67  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef6e  lea     r12, WPP_GLOBAL_Control
0x18002ef75  cmp     rcx, r12
0x18002ef78  jz      short loc_18002EF95
0x18002ef7a  test    byte ptr [rcx+1Ch], 8
0x18002ef7e  jz      short loc_18002EF95
0x18002ef80  mov     rcx, [rcx+10h]
0x18002ef84  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002ef8b  mov     edx, 158h
0x18002ef90  call    WPP_SF_
0x18002ef95  xor     ebx, ebx
0x18002ef97  cmp     edi, 1
0x18002ef9a  jle     short loc_18002EFA1
0x18002ef9c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002efa1  mov     edx, edi
0x18002efa3  mov     rcx, r15
0x18002efa6  call    ?FwGetAppropiateSetHive@@YAPEAU_tag_WF_POLICY_STORE_HIVE_LIST@@PEAU_tag_WF_POLICY_STORE@@W4FW_SET_TYPE@@@Z; FwGetAppropiateSetHive(_tag_WF_POLICY_STORE *,FW_SET_TYPE)
0x18002efab  xor     esi, esi
0x18002efad  mov     rbp, rax
0x18002efb0  cmp     r14d, 1
0x18002efb4  setnz   sil
0x18002efb8  add     esi, 6
0x18002efbb  xor     edi, edi
0x18002efbd  cmp     edi, [rbp+0]
0x18002efc0  jnb     short loc_18002F01B
0x18002efc2  mov     rax, [rbp+8]
0x18002efc6  mov     edx, edi
0x18002efc8  add     rdx, rdx
0x18002efcb  cmp     [rax+rdx*8+8], esi
0x18002efcf  jnz     short loc_18002EFED
0x18002efd1  mov     rdx, [rax+rdx*8]
0x18002efd5  mov     rcx, [r15+28h]
0x18002efd9  call    cs:__imp_FwRegDeleteKey
0x18002efdf  xor     ebx, ebx
0x18002efe1  cmp     eax, 80070002h
0x18002efe6  cmovnz  ebx, eax
0x18002efe9  test    ebx, ebx
0x18002efeb  js      short loc_18002EFF1
0x18002efed  inc     edi
0x18002efef  jmp     short loc_18002EFBD
0x18002eff1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eff8  cmp     rcx, r12
0x18002effb  jz      short loc_18002F01B
0x18002effd  test    byte ptr [rcx+1Ch], 1
0x18002f001  jz      short loc_18002F01B
0x18002f003  mov     rcx, [rcx+10h]
0x18002f007  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002f00e  mov     edx, 159h
0x18002f013  mov     r9d, ebx
0x18002f016  call    WPP_SF_d
0x18002f01b  mov     eax, ebx
0x18002f01d  add     rsp, 20h
0x18002f021  pop     r15
0x18002f023  pop     r14
0x18002f025  pop     r12
0x18002f027  pop     rdi
0x18002f028  pop     rsi
0x18002f029  pop     rbp
0x18002f02a  pop     rbx
0x18002f02b  retn
```
