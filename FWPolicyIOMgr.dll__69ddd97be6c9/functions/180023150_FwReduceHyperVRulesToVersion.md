# FwReduceHyperVRulesToVersion

- ea: `0x180023150`
- end: `0x180023204`
- name: `FwReduceHyperVRulesToVersion`
- size: `180`
- prototype: `__int64 __fastcall(_QWORD **, unsigned __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800042c4`
- `0x180023150`

## import_xrefs

- `fwbase!Int_FwValidateComplianceAndReduceHyperVRuleToVersion` at `0x1800231a3`
- `fwbase!Int_FwValidateComplianceAndReduceHyperVRuleToVersion` at `0x1800231a3`

## pseudocode

```c
__int64 __fastcall FwReduceHyperVRulesToVersion(_QWORD **a1, unsigned __int16 a2)
{
  unsigned int v2; // ebx
  LPCOLESTR v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  _QWORD *i; // rdi
  int v8; // eax

  v2 = 0;
  if ( a1 )
  {
    for ( i = *a1; i; i = (_QWORD *)*i )
    {
      v8 = Int_FwValidateComplianceAndReduceHyperVRuleToVersion(i, 0, a2, 2);
      v2 = v8;
      if ( v8 > 0 )
        v2 = (unsigned __int16)v8 | 0x80070000;
      if ( (v2 & 0x80000000) != 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v5 = 222;
          v6 = v2;
          goto LABEL_14;
        }
        return v2;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v5 = 221;
      v6 = 0;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, v6);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180023150  mov     [rsp+arg_0], rbx
0x180023155  mov     [rsp+arg_8], rsi
0x18002315a  push    rdi
0x18002315b  sub     rsp, 20h
0x18002315f  xor     ebx, ebx
0x180023161  movzx   esi, dx
0x180023164  test    rcx, rcx
0x180023167  jnz     short loc_18002318C
0x180023169  mov     rcx, cs:WPP_GLOBAL_Control
0x180023170  lea     rax, WPP_GLOBAL_Control
0x180023177  cmp     rcx, rax
0x18002317a  jz      short loc_1800231F2
0x18002317c  test    byte ptr [rcx+1Ch], 1
0x180023180  jz      short loc_1800231F2
0x180023182  mov     edx, 0DDh
0x180023187  xor     r9d, r9d
0x18002318a  jmp     short loc_1800231E2
0x18002318c  mov     rdi, [rcx]
0x18002318f  test    rdi, rdi
0x180023192  jz      short loc_1800231F2
0x180023194  mov     r9d, 2
0x18002319a  movzx   r8d, si
0x18002319e  xor     edx, edx
0x1800231a0  mov     rcx, rdi
0x1800231a3  call    cs:__imp_Int_FwValidateComplianceAndReduceHyperVRuleToVersion
0x1800231a9  mov     ebx, eax
0x1800231ab  test    eax, eax
0x1800231ad  jle     short loc_1800231B8
0x1800231af  movzx   ebx, ax
0x1800231b2  or      ebx, 80070000h
0x1800231b8  test    ebx, ebx
0x1800231ba  js      short loc_1800231C1
0x1800231bc  mov     rdi, [rdi]
0x1800231bf  jmp     short loc_18002318F
0x1800231c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231c8  lea     rax, WPP_GLOBAL_Control
0x1800231cf  cmp     rcx, rax
0x1800231d2  jz      short loc_1800231F2
0x1800231d4  test    byte ptr [rcx+1Ch], 1
0x1800231d8  jz      short loc_1800231F2
0x1800231da  mov     edx, 0DEh
0x1800231df  mov     r9d, ebx
0x1800231e2  mov     rcx, [rcx+10h]
0x1800231e6  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x1800231ed  call    WPP_SF_d
0x1800231f2  mov     rsi, [rsp+28h+arg_8]
0x1800231f7  mov     eax, ebx
0x1800231f9  mov     rbx, [rsp+28h+arg_0]
0x1800231fe  add     rsp, 20h
0x180023202  pop     rdi
0x180023203  retn
```
