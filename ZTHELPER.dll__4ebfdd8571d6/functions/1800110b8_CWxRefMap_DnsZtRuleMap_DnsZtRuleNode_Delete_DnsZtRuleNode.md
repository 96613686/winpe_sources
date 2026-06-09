# CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Delete(DnsZtRuleNode *)

- ea: `0x1800110b8`
- end: `0x180011155`
- name: `?Delete@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAJPEAVDnsZtRuleNode@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800111cc`
- `0x180011548`

## callees

- `0x1800014b0`
- `0x180007674`
- `0x18000a04c`
- `0x18000a268`
- `0x1800110b8`

## pseudocode

```c
__int64 __fastcall CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Delete(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  struct _WX_AVL_TABLE *v4; // rcx
  DnsZtRuleNode **v5; // rdx
  DnsZtRuleNode *v6; // rsi
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF

  v9 = a2;
  if ( a2 )
  {
    v4 = *(struct _WX_AVL_TABLE **)a1;
    v8 = 0;
    v3 = 1;
    if ( (unsigned int)FindNodeOrParent(v4, &v9, &v8) == 1 )
    {
      v5 = (DnsZtRuleNode **)(v8 + 32);
      if ( v8 != -32 )
      {
        _InterlockedAdd((volatile signed __int32 *)(a1 + 8), 1u);
        v6 = *v5;
        if ( WxDeleteElementGenericTableAvl(*(struct _WX_AVL_TABLE **)a1, v5) == 1 )
        {
          v3 = 0;
          DnsZtRuleNode::Release(v6);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x1800110b8  mov     [rsp+arg_10], rbx
0x1800110bd  mov     [rsp+arg_18], rsi
0x1800110c2  push    rdi
0x1800110c3  sub     rsp, 40h
0x1800110c7  mov     rax, cs:__security_cookie
0x1800110ce  xor     rax, rsp
0x1800110d1  mov     [rsp+48h+var_18], rax
0x1800110d6  mov     [rsp+48h+var_20], rdx
0x1800110db  mov     rdi, rcx
0x1800110de  test    rdx, rdx
0x1800110e1  jnz     short loc_1800110EA
0x1800110e3  mov     ebx, 80070057h
0x1800110e8  jmp     short loc_180011136
0x1800110ea  mov     rcx, [rcx]
0x1800110ed  lea     r8, [rsp+48h+var_28]
0x1800110f2  lea     rdx, [rsp+48h+var_20]
0x1800110f7  mov     [rsp+48h+var_28], 0
0x180011100  call    ?FindNodeOrParent@@YA?AW4_WX_TABLE_SEARCH_RESULT@@PEAU_WX_AVL_TABLE@@PEAXPEAPEAU_WX_BALANCED_LINKS@@@Z; FindNodeOrParent(_WX_AVL_TABLE *,void *,_WX_BALANCED_LINKS * *)
0x180011105  mov     ebx, 1
0x18001110a  cmp     eax, ebx
0x18001110c  jnz     short loc_180011136
0x18001110e  mov     rdx, [rsp+48h+var_28]
0x180011113  add     rdx, 20h ; ' '; void *
0x180011117  jz      short loc_180011136
0x180011119  lock add [rdi+8], ebx
0x18001111d  mov     rcx, [rdi]; struct _WX_AVL_TABLE *
0x180011120  mov     rsi, [rdx]
0x180011123  call    ?WxDeleteElementGenericTableAvl@@YAEPEAU_WX_AVL_TABLE@@PEAX@Z; WxDeleteElementGenericTableAvl(_WX_AVL_TABLE *,void *)
0x180011128  cmp     al, bl
0x18001112a  jnz     short loc_180011136
0x18001112c  xor     ebx, ebx
0x18001112e  mov     rcx, rsi; this
0x180011131  call    ?Release@DnsZtRuleNode@@QEAAKXZ; DnsZtRuleNode::Release(void)
0x180011136  mov     eax, ebx
0x180011138  mov     rcx, [rsp+48h+var_18]
0x18001113d  xor     rcx, rsp; StackCookie
0x180011140  call    __security_check_cookie
0x180011145  mov     rbx, [rsp+48h+arg_10]
0x18001114a  mov     rsi, [rsp+48h+arg_18]
0x18001114f  add     rsp, 40h
0x180011153  pop     rdi
0x180011154  retn
```
