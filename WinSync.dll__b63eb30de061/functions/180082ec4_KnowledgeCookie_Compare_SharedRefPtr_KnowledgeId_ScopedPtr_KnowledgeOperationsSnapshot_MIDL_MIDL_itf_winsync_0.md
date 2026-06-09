# KnowledgeCookie::Compare(SharedRefPtr<KnowledgeId> &,ScopedPtr<KnowledgeOperationsSnapshot> &,__MIDL___MIDL_itf_winsync_0000_0000_0011 *)

- ea: `0x180082ec4`
- end: `0x1800830aa`
- name: `?Compare@KnowledgeCookie@@AEAAJAEAV?$SharedRefPtr@VKnowledgeId@@@@AEAV?$ScopedPtr@UKnowledgeOperationsSnapshot@@@@PEAW4__MIDL___MIDL_itf_winsync_0000_0000_0011@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned __int16 **, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800217ec`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180082ec4`
- `0x18008a438`

## string_xrefs

- `0x180082f00`: `KnowledgeCookie::Compare`
- `0x18008307e`: `KnowledgeCookie::Compare`

## pseudocode

```c
__int64 __fastcall KnowledgeCookie::Compare(__int64 a1, _QWORD *a2, unsigned __int16 **a3, _DWORD *a4)
{
  __int64 v8; // r9
  unsigned __int16 *v9; // rcx
  unsigned __int16 v10; // r8
  unsigned __int16 *v11; // rdx
  unsigned __int16 v12; // r9
  unsigned __int16 v13; // ax
  _WORD *v14; // rax
  unsigned __int16 *v15; // rax
  _WORD *v16; // rax
  int v18; // [rsp+70h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids,
      "KnowledgeCookie::Compare");
  }
  *a4 = 3;
  v8 = *(_QWORD *)(a1 + 16);
  v18 = 0;
  if ( *a2 != v8 )
  {
    v14 = *(_WORD **)(a1 + 24);
    if ( *v14 || v14[1] )
    {
      if ( **a3 || (*a3)[1] || v14[1] && *v14 || !(unsigned int)KnowledgeId::CompareTo(v8, a2, &v18) )
        goto LABEL_41;
      v16 = *(_WORD **)(a1 + 24);
      if ( !v18 )
      {
        if ( *v16 )
          goto LABEL_38;
        if ( v16[1] )
          goto LABEL_40;
        goto LABEL_35;
      }
      if ( v18 <= 0 )
      {
        if ( *v16 )
          goto LABEL_41;
        goto LABEL_40;
      }
      if ( v16[1] )
        goto LABEL_41;
    }
    else
    {
      if ( **a3 && (*a3)[1] || !(unsigned int)KnowledgeId::CompareTo(v8, a2, &v18) )
        goto LABEL_41;
      v15 = *a3;
      if ( v18 )
      {
        if ( v18 <= 0 )
        {
          if ( v15[1] )
            goto LABEL_41;
          goto LABEL_40;
        }
        if ( *v15 )
          goto LABEL_41;
        goto LABEL_38;
      }
      if ( *v15 )
        goto LABEL_40;
      if ( !v15[1] )
      {
LABEL_35:
        *a4 = 0;
        goto LABEL_41;
      }
    }
LABEL_38:
    *a4 = 2;
    goto LABEL_41;
  }
  v9 = *(unsigned __int16 **)(a1 + 24);
  v10 = **a3;
  v11 = *a3 + 1;
  v12 = *v9;
  if ( *v9 == v10 && v9[1] == *v11 )
    goto LABEL_35;
  v13 = v9[1];
  if ( v13 != *v11 )
  {
    if ( v12 != v10 )
      goto LABEL_41;
    if ( v13 >= *v11 )
    {
LABEL_40:
      *a4 = 1;
      goto LABEL_41;
    }
    goto LABEL_38;
  }
  *a4 = 2 - (v12 < v10);
LABEL_41:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids,
      (unsigned int)"KnowledgeCookie::Compare",
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180082ec4  push    rbx
0x180082ec6  push    rbp
0x180082ec7  push    rsi
0x180082ec8  push    rdi
0x180082ec9  push    r14
0x180082ecb  push    r15
0x180082ecd  sub     rsp, 38h
0x180082ed1  mov     rsi, r9
0x180082ed4  mov     rbx, r8
0x180082ed7  mov     rbp, rdx
0x180082eda  mov     rdi, rcx
0x180082edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180082ee4  lea     r15, WPP_GLOBAL_Control
0x180082eeb  cmp     rcx, r15
0x180082eee  jz      short loc_180082F18
0x180082ef0  test    byte ptr [rcx+1Ch], 40h
0x180082ef4  jz      short loc_180082F18
0x180082ef6  cmp     byte ptr [rcx+19h], 5
0x180082efa  jb      short loc_180082F18
0x180082efc  mov     rcx, [rcx+10h]
0x180082f00  lea     r9, aKnowledgecooki; "KnowledgeCookie::Compare"
0x180082f07  mov     edx, 10h
0x180082f0c  lea     r8, WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids
0x180082f13  call    WPP_SF_s
0x180082f18  mov     dword ptr [rsi], 3
0x180082f1e  xor     r14d, r14d
0x180082f21  mov     r9, [rdi+10h]
0x180082f25  mov     [rsp+68h+arg_0], r14d
0x180082f2a  cmp     [rbp+0], r9
0x180082f2e  jnz     short loc_180082F87
0x180082f30  mov     rax, [rbx]
0x180082f33  mov     rcx, [rdi+18h]
0x180082f37  movzx   r8d, word ptr [rax]
0x180082f3b  lea     rdx, [rax+2]
0x180082f3f  movzx   r9d, word ptr [rcx]
0x180082f43  cmp     r9w, r8w
0x180082f47  jnz     short loc_180082F56
0x180082f49  movzx   eax, word ptr [rdx]
0x180082f4c  cmp     [rcx+2], ax
0x180082f50  jz      loc_180083040
0x180082f56  movzx   eax, word ptr [rcx+2]
0x180082f5a  cmp     ax, [rdx]
0x180082f5d  jnz     short loc_180082F6F
0x180082f5f  cmp     r9w, r8w
0x180082f63  sbb     eax, eax
0x180082f65  add     eax, 2
0x180082f68  mov     [rsi], eax
0x180082f6a  jmp     loc_180083062
0x180082f6f  cmp     r9w, r8w
0x180082f73  jnz     loc_180083062
0x180082f79  cmp     ax, [rdx]
0x180082f7c  jb      loc_18008304E
0x180082f82  jmp     loc_18008305C
0x180082f87  mov     rax, [rdi+18h]
0x180082f8b  movzx   edx, word ptr [rax]
0x180082f8e  test    dx, dx
0x180082f91  jnz     short loc_180082FF7
0x180082f93  cmp     [rax+2], r14w
0x180082f98  jnz     short loc_180082FF7
0x180082f9a  mov     rax, [rbx]
0x180082f9d  cmp     [rax], r14w
0x180082fa1  jz      short loc_180082FAE
0x180082fa3  cmp     [rax+2], r14w
0x180082fa8  jnz     loc_180083062
0x180082fae  lea     r8, [rsp+68h+arg_0]
0x180082fb3  mov     rdx, rbp
0x180082fb6  mov     rcx, r9
0x180082fb9  call    ?CompareTo@KnowledgeId@@QEAAHAEAV?$SharedRefPtr@VKnowledgeId@@@@PEAH@Z; KnowledgeId::CompareTo(SharedRefPtr<KnowledgeId> &,int *)
0x180082fbe  test    eax, eax
0x180082fc0  jz      loc_180083062
0x180082fc6  mov     ecx, [rsp+68h+arg_0]
0x180082fca  mov     rax, [rbx]
0x180082fcd  test    ecx, ecx
0x180082fcf  jnz     short loc_180082FE4
0x180082fd1  cmp     [rax], r14w
0x180082fd5  jnz     loc_18008305C
0x180082fdb  cmp     [rax+2], r14w
0x180082fe0  jnz     short loc_18008304E
0x180082fe2  jmp     short loc_180083040
0x180082fe4  jle     short loc_180082FEE
0x180082fe6  cmp     [rax], r14w
0x180082fea  jz      short loc_18008304E
0x180082fec  jmp     short loc_180083062
0x180082fee  cmp     [rax+2], r14w
0x180082ff3  jz      short loc_18008305C
0x180082ff5  jmp     short loc_180083062
0x180082ff7  mov     rcx, [rbx]
0x180082ffa  cmp     [rcx], r14w
0x180082ffe  jnz     short loc_180083062
0x180083000  cmp     [rcx+2], r14w
0x180083005  jnz     short loc_180083062
0x180083007  cmp     [rax+2], r14w
0x18008300c  jz      short loc_180083013
0x18008300e  test    dx, dx
0x180083011  jnz     short loc_180083062
0x180083013  lea     r8, [rsp+68h+arg_0]
0x180083018  mov     rdx, rbp
0x18008301b  mov     rcx, r9
0x18008301e  call    ?CompareTo@KnowledgeId@@QEAAHAEAV?$SharedRefPtr@VKnowledgeId@@@@PEAH@Z; KnowledgeId::CompareTo(SharedRefPtr<KnowledgeId> &,int *)
0x180083023  test    eax, eax
0x180083025  jz      short loc_180083062
0x180083027  mov     ecx, [rsp+68h+arg_0]
0x18008302b  mov     rax, [rdi+18h]
0x18008302f  test    ecx, ecx
0x180083031  jnz     short loc_180083045
0x180083033  cmp     [rax], r14w
0x180083037  jnz     short loc_18008304E
0x180083039  cmp     [rax+2], r14w
0x18008303e  jnz     short loc_18008305C
0x180083040  mov     [rsi], r14d
0x180083043  jmp     short loc_180083062
0x180083045  jle     short loc_180083056
0x180083047  cmp     [rax+2], r14w
0x18008304c  jnz     short loc_180083062
0x18008304e  mov     dword ptr [rsi], 2
0x180083054  jmp     short loc_180083062
0x180083056  cmp     [rax], r14w
0x18008305a  jnz     short loc_180083062
0x18008305c  mov     dword ptr [rsi], 1
0x180083062  mov     rcx, cs:WPP_GLOBAL_Control
0x180083069  cmp     rcx, r15
0x18008306c  jz      short loc_18008309B
0x18008306e  test    byte ptr [rcx+1Ch], 40h
0x180083072  jz      short loc_18008309B
0x180083074  cmp     byte ptr [rcx+19h], 5
0x180083078  jb      short loc_18008309B
0x18008307a  mov     rcx, [rcx+10h]
0x18008307e  lea     r9, aKnowledgecooki; "KnowledgeCookie::Compare"
0x180083085  mov     edx, 11h
0x18008308a  mov     [rsp+68h+var_48], r14d
0x18008308f  lea     r8, WPP_98ca5cf25e833a9fb458cde358e2579e_Traceguids
0x180083096  call    WPP_SF_sD
0x18008309b  xor     eax, eax
0x18008309d  add     rsp, 38h
0x1800830a1  pop     r15
0x1800830a3  pop     r14
0x1800830a5  pop     rdi
0x1800830a6  pop     rsi
0x1800830a7  pop     rbp
0x1800830a8  pop     rbx
0x1800830a9  retn
```
