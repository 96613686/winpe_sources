# CreateOpenPortRuleFromBuiltInPort(FW_BUILTIN_PORT_ const *,_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)

- ea: `0x1800210a8`
- end: `0x18002122b`
- name: `?CreateOpenPortRuleFromBuiltInPort@@YAJPEBUFW_BUILTIN_PORT_@@PEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002ad4c`

## callees

- `0x1800042c4`
- `0x180006f50`
- `0x18001ea60`
- `0x180020990`
- `0x1800210a8`

## import_xrefs

- `fwbase!FwStringCopy` at `0x1800211cd`
- `fwbase!FwStringCopy` at `0x1800211cd`
- `fwbase!FwBuildIndirectString` at `0x18002110b`
- `fwbase!FwBuildIndirectString` at `0x18002110b`

## pseudocode

```c
__int64 __fastcall CreateOpenPortRuleFromBuiltInPort(unsigned int *a1, void **a2)
{
  int DefaultOpenPortRule; // edi
  LPCOLESTR v5; // rcx
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  int v8; // eax

  *a2 = 0;
  DefaultOpenPortRule = CreateDefaultOpenPortRule(a2, 0x7FFFFFFF);
  if ( DefaultOpenPortRule < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_17;
    v6 = 144;
LABEL_16:
    WPP_SF_d(
      *((_QWORD *)v5 + 2),
      v6,
      WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids,
      (unsigned int)DefaultOpenPortRule);
LABEL_17:
    FwFreeWFRule(*a2);
    *a2 = 0;
    return (unsigned int)DefaultOpenPortRule;
  }
  DefaultOpenPortRule = FwBuildIndirectString(*a1, (char *)*a2 + 24);
  if ( DefaultOpenPortRule < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_17;
    v6 = 145;
    goto LABEL_16;
  }
  *((_DWORD *)*a2 + 16) = 1;
  *(_WORD *)(*((_QWORD *)*a2 + 9) + 2LL) = *((_WORD *)a1 + 2);
  **((_WORD **)*a2 + 9) = *(_WORD *)(*((_QWORD *)*a2 + 9) + 2LL);
  v7 = *a2;
  v8 = *((_DWORD *)*a2 + 44);
  if ( a1[3] )
  {
    v7[44] = v8 | 1;
    *((_DWORD *)*a2 + 45) |= 1u;
  }
  else
  {
    v7[44] = v8 & 0xFFFFFFFE;
    *((_DWORD *)*a2 + 45) &= ~1u;
  }
  FwICFProtocolToWfProtocol(a1[2], (char *)*a2 + 48);
  *((_DWORD *)*a2 + 72) = 2;
  DefaultOpenPortRule = FwStringCopy(*((_QWORD *)a1 + 3), (char *)*a2 + 312);
  if ( DefaultOpenPortRule < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_17;
    v6 = 146;
    goto LABEL_16;
  }
  return (unsigned int)DefaultOpenPortRule;
}

```

## disassembly

```asm
0x1800210a8  mov     [rsp+arg_0], rbx
0x1800210ad  mov     [rsp+arg_8], rsi
0x1800210b2  push    rdi
0x1800210b3  sub     rsp, 20h
0x1800210b7  mov     rbx, rdx
0x1800210ba  mov     qword ptr [rdx], 0
0x1800210c1  mov     rsi, rcx
0x1800210c4  mov     edx, 7FFFFFFFh
0x1800210c9  mov     rcx, rbx
0x1800210cc  call    ?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x1800210d1  mov     edi, eax
0x1800210d3  test    eax, eax
0x1800210d5  jns     short loc_180021102
0x1800210d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210de  lea     rax, WPP_GLOBAL_Control
0x1800210e5  cmp     rcx, rax
0x1800210e8  jz      loc_18002120A
0x1800210ee  test    byte ptr [rcx+1Ch], 1
0x1800210f2  jz      loc_18002120A
0x1800210f8  mov     edx, 90h
0x1800210fd  jmp     loc_1800211F7
0x180021102  mov     rdx, [rbx]
0x180021105  mov     ecx, [rsi]
0x180021107  add     rdx, 18h
0x18002110b  call    cs:__imp_FwBuildIndirectString
0x180021111  mov     edi, eax
0x180021113  test    eax, eax
0x180021115  jns     short loc_180021142
0x180021117  mov     rcx, cs:WPP_GLOBAL_Control
0x18002111e  lea     rax, WPP_GLOBAL_Control
0x180021125  cmp     rcx, rax
0x180021128  jz      loc_18002120A
0x18002112e  test    byte ptr [rcx+1Ch], 1
0x180021132  jz      loc_18002120A
0x180021138  mov     edx, 91h
0x18002113d  jmp     loc_1800211F7
0x180021142  mov     rax, [rbx]
0x180021145  mov     dword ptr [rax+40h], 1
0x18002114c  mov     rax, [rbx]
0x18002114f  mov     rcx, [rax+48h]
0x180021153  movzx   eax, word ptr [rsi+4]
0x180021157  mov     [rcx+2], ax
0x18002115b  mov     rax, [rbx]
0x18002115e  mov     rcx, [rax+48h]
0x180021162  movzx   eax, word ptr [rcx+2]
0x180021166  mov     [rcx], ax
0x180021169  cmp     dword ptr [rsi+0Ch], 0
0x18002116d  mov     rcx, [rbx]
0x180021170  mov     eax, [rcx+0B0h]
0x180021176  jnz     short loc_180021190
0x180021178  mov     edx, 0FFFFFFFEh
0x18002117d  and     eax, edx
0x18002117f  mov     [rcx+0B0h], eax
0x180021185  mov     rax, [rbx]
0x180021188  and     [rax+0B4h], edx
0x18002118e  jmp     short loc_1800211A3
0x180021190  or      eax, 1
0x180021193  mov     [rcx+0B0h], eax
0x180021199  mov     rax, [rbx]
0x18002119c  or      dword ptr [rax+0B4h], 1
0x1800211a3  mov     rdx, [rbx]
0x1800211a6  mov     ecx, [rsi+8]
0x1800211a9  add     rdx, 30h ; '0'
0x1800211ad  call    FwICFProtocolToWfProtocol
0x1800211b2  mov     rax, [rbx]
0x1800211b5  mov     dword ptr [rax+120h], 2
0x1800211bf  mov     rdx, [rbx]
0x1800211c2  mov     rcx, [rsi+18h]
0x1800211c6  add     rdx, 138h
0x1800211cd  call    cs:__imp_FwStringCopy
0x1800211d3  mov     edi, eax
0x1800211d5  test    eax, eax
0x1800211d7  jns     short loc_180021219
0x1800211d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211e0  lea     rax, WPP_GLOBAL_Control
0x1800211e7  cmp     rcx, rax
0x1800211ea  jz      short loc_18002120A
0x1800211ec  test    byte ptr [rcx+1Ch], 1
0x1800211f0  jz      short loc_18002120A
0x1800211f2  mov     edx, 92h
0x1800211f7  mov     rcx, [rcx+10h]
0x1800211fb  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180021202  mov     r9d, edi
0x180021205  call    WPP_SF_d
0x18002120a  mov     rcx, [rbx]; void *
0x18002120d  call    FwFreeWFRule
0x180021212  mov     qword ptr [rbx], 0
0x180021219  mov     rbx, [rsp+28h+arg_0]
0x18002121e  mov     eax, edi
0x180021220  mov     rsi, [rsp+28h+arg_8]
0x180021225  add     rsp, 20h
0x180021229  pop     rdi
0x18002122a  retn
```
