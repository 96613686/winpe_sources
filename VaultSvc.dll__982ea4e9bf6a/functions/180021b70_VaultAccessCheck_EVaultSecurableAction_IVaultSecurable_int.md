# VaultAccessCheck(EVaultSecurableAction,IVaultSecurable *,int *)

- ea: `0x180021b70`
- end: `0x180021d7a`
- name: `?VaultAccessCheck@@YAHW4EVaultSecurableAction@@PEAVIVaultSecurable@@PEAH@Z`
- size: `522`
- prototype: `unsigned int __fastcall(int, __int64, _DWORD *)`
- caller_count: `21`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800135d0`
- `0x180015e30`
- `0x180016250`
- `0x180021468`
- `0x180021650`
- `0x1800219a0`
- `0x180026a80`
- `0x180029690`
- `0x18002f958`
- `0x180034460`
- `0x1800358a0`
- `0x1800416f0`
- `0x180041818`
- `0x180045df0`
- `0x180046040`
- `0x180046920`
- `0x180046d90`
- `0x180047610`
- `0x180047e90`
- `0x180048140`
- `0x1800483f0`

## callees

- `0x180021b70`
- `0x180021d80`
- `0x18003b7b0`
- `0x18003da30`
- `0x18004d010`

## pseudocode

```c
unsigned int __fastcall VaultAccessCheck(int a1, __int64 a2, _DWORD *a3)
{
  __int64 v3; // rsi
  __int64 v6; // r14
  __int64 *v7; // r15
  __int64 *v8; // r13
  PVOID *v9; // rcx
  unsigned int result; // eax
  int v11; // ebx
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // [rsp+68h] [rbp+10h] BYREF

  v3 = a1;
  if ( a2 )
  {
    v6 = 4LL * (*(int (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    v7 = (&off_18005F000)[v6 + 2];
    v8 = &(&off_18005F000)[v6][2 * v3];
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
        (unsigned int)(&off_18005F000)[v6 + 2],
        v8[1]);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a3 && *a3 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
        WPP_SF_(v9[2], 21, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
    }
    else
    {
      v14 = 0;
      result = VaultIsDominantCaller(&v14);
      if ( result )
        return result;
      if ( !v14 )
      {
        v11 = ((__int64 (__fastcall *)(_QWORD, __int64))(&off_18005F000)[v6 + 3])((unsigned int)v3, a2);
        if ( v11 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            return v11;
          v13 = 23;
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            return v11;
          v13 = 24;
        }
        WPP_SF_SS(v12[2], v13, (unsigned int)WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids, (_DWORD)v7, v8[1]);
        return v11;
      }
      if ( a3 )
        *a3 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids,
          (_DWORD)v7,
          v8[1]);
    }
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x180021b70  push    rbx
0x180021b72  push    rbp
0x180021b73  push    rsi
0x180021b74  push    rdi
0x180021b75  sub     rsp, 38h
0x180021b79  movsxd  rsi, ecx
0x180021b7c  mov     rdi, r8
0x180021b7f  mov     rbx, rdx
0x180021b82  test    rdx, rdx
0x180021b85  jz      loc_180021CC6
0x180021b8b  mov     rax, [rdx]
0x180021b8e  mov     rcx, rdx
0x180021b91  mov     [rsp+58h+arg_0], r12
0x180021b96  mov     [rsp+58h+arg_10], r13
0x180021b9b  mov     [rsp+58h+arg_18], r14
0x180021ba0  mov     rax, [rax+10h]
0x180021ba4  mov     [rsp+58h+var_28], r15
0x180021ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bae  lea     r12, off_18005F000
0x180021bb5  movsxd  r14, eax
0x180021bb8  shl     r14, 5
0x180021bbc  mov     rcx, rsi
0x180021bbf  shl     rcx, 4
0x180021bc3  mov     r13, [r14+r12]
0x180021bc7  mov     r15, [r14+r12+10h]
0x180021bcc  add     r13, rcx
0x180021bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bd6  lea     rbp, WPP_GLOBAL_Control
0x180021bdd  cmp     rcx, rbp
0x180021be0  jz      short loc_180021BEC
0x180021be2  test    byte ptr [rcx+1Ch], 8
0x180021be6  jnz     loc_180021D01
0x180021bec  test    rdi, rdi
0x180021bef  jz      short loc_180021BFA
0x180021bf1  cmp     dword ptr [rdi], 0
0x180021bf4  jnz     loc_180021C88
0x180021bfa  lea     rcx, [rsp+58h+arg_8]; int *
0x180021bff  mov     [rsp+58h+arg_8], 0
0x180021c07  call    ?VaultIsDominantCaller@@YAKPEAH@Z; VaultIsDominantCaller(int *)
0x180021c0c  test    eax, eax
0x180021c0e  jnz     short loc_180021C6B
0x180021c10  cmp     [rsp+58h+arg_8], eax
0x180021c14  jnz     short loc_180021C45
0x180021c16  mov     rax, [r14+r12+18h]
0x180021c1b  mov     rdx, rbx
0x180021c1e  mov     ecx, esi
0x180021c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c25  mov     ebx, eax
0x180021c27  test    eax, eax
0x180021c29  jnz     short loc_180021CAA
0x180021c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c32  cmp     rcx, rbp
0x180021c35  jz      short loc_180021C41
0x180021c37  test    byte ptr [rcx+1Ch], 8
0x180021c3b  jnz     loc_180021D54
0x180021c41  mov     eax, ebx
0x180021c43  jmp     short loc_180021C6B
0x180021c45  test    rdi, rdi
0x180021c48  jz      short loc_180021C50
0x180021c4a  mov     dword ptr [rdi], 1
0x180021c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c57  cmp     rcx, rbp
0x180021c5a  jz      short loc_180021C66
0x180021c5c  test    byte ptr [rcx+1Ch], 8
0x180021c60  jnz     loc_180021D2E
0x180021c66  mov     eax, 1
0x180021c6b  mov     r14, [rsp+58h+arg_18]
0x180021c70  mov     r13, [rsp+58h+arg_10]
0x180021c75  mov     r12, [rsp+58h+arg_0]
0x180021c7a  mov     r15, [rsp+58h+var_28]
0x180021c7f  add     rsp, 38h
0x180021c83  pop     rdi
0x180021c84  pop     rsi
0x180021c85  pop     rbp
0x180021c86  pop     rbx
0x180021c87  retn
0x180021c88  cmp     rcx, rbp
0x180021c8b  jz      short loc_180021C66
0x180021c8d  test    byte ptr [rcx+1Ch], 8
0x180021c91  jz      short loc_180021C66
0x180021c93  mov     rcx, [rcx+10h]
0x180021c97  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021c9e  mov     edx, 15h
0x180021ca3  call    WPP_SF_
0x180021ca8  jmp     short loc_180021C66
0x180021caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cb1  cmp     rcx, rbp
0x180021cb4  jz      short loc_180021C41
0x180021cb6  test    byte ptr [rcx+1Ch], 8
0x180021cba  jz      short loc_180021C41
0x180021cbc  mov     edx, 17h
0x180021cc1  jmp     loc_180021D59
0x180021cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ccd  lea     rbp, WPP_GLOBAL_Control
0x180021cd4  cmp     rcx, rbp
0x180021cd7  jnz     short loc_180021CE4
0x180021cd9  xor     eax, eax
0x180021cdb  add     rsp, 38h
0x180021cdf  pop     rdi
0x180021ce0  pop     rsi
0x180021ce1  pop     rbp
0x180021ce2  pop     rbx
0x180021ce3  retn
0x180021ce4  test    byte ptr [rcx+1Ch], 2
0x180021ce8  jz      short loc_180021CD9
0x180021cea  mov     rcx, [rcx+10h]
0x180021cee  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021cf5  mov     edx, 13h
0x180021cfa  call    WPP_SF_
0x180021cff  jmp     short loc_180021CD9
0x180021d01  mov     rax, [r13+8]
0x180021d05  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021d0c  mov     rcx, [rcx+10h]
0x180021d10  mov     edx, 14h
0x180021d15  mov     r9, r15
0x180021d18  mov     [rsp+58h+var_38], rax
0x180021d1d  call    WPP_SF_SS
0x180021d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d29  jmp     loc_180021BEC
0x180021d2e  mov     r8, [r13+8]
0x180021d32  mov     edx, 16h
0x180021d37  mov     rcx, [rcx+10h]
0x180021d3b  mov     r9, r15
0x180021d3e  mov     [rsp+58h+var_38], r8
0x180021d43  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021d4a  call    WPP_SF_SS
0x180021d4f  jmp     loc_180021C66
0x180021d54  mov     edx, 18h
0x180021d59  mov     rax, [r13+8]
0x180021d5d  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180021d64  mov     rcx, [rcx+10h]
0x180021d68  mov     r9, r15
0x180021d6b  mov     [rsp+58h+var_38], rax
0x180021d70  call    WPP_SF_SS
0x180021d75  jmp     loc_180021C41
```
