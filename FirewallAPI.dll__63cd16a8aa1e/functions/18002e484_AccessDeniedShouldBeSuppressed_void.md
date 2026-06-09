# AccessDeniedShouldBeSuppressed(void)

- ea: `0x18002e484`
- end: `0x18002e6e2`
- name: `?AccessDeniedShouldBeSuppressed@@YAHXZ`
- size: `606`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000270c`
- `0x1800392c0`

## callees

- `0x180005954`
- `0x180008a10`
- `0x18000c130`
- `0x18000c560`
- `0x18000d850`
- `0x1800277b0`
- `0x18002e484`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e65f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e65f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002e631`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002e631`
- `fwbase!FwSidDestroy` at `0x18002e64b`
- `fwbase!FwSidDestroy` at `0x18002e6c2`
- `fwbase!FwSidDestroy` at `0x18002e64b`
- `fwbase!FwSidDestroy` at `0x18002e6c2`
- `fwbase!FwSidCreate` at `0x18002e615`
- `fwbase!FwSidCreate` at `0x18002e615`

## pseudocode

```c
__int64 AccessDeniedShouldBeSuppressed(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 LastError; // r9
  FwPolicy2 *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned __int16 v10; // ax
  int v12; // [rsp+40h] [rbp-19h]
  int v13; // [rsp+44h] [rbp-15h]
  __int64 v14; // [rsp+48h] [rbp-11h]
  __int64 v15; // [rsp+50h] [rbp-9h]
  unsigned int v16; // [rsp+58h] [rbp-1h] BYREF
  PSID SidToCheck; // [rsp+60h] [rbp+7h] BYREF
  __int64 v18; // [rsp+68h] [rbp+Fh] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp+17h] BYREF
  int v20; // [rsp+74h] [rbp+1Bh] BYREF
  int v21; // [rsp+78h] [rbp+1Fh] BYREF

  v14 = 6;
  v18 = 0;
  v21 = 0;
  v0 = 0;
  v16 = 0;
  v15 = 18;
  v20 = 4;
  v12 = 4;
  v13 = 1;
  SidToCheck = 0;
  v1 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v18);
  LastError = v1;
  if ( v1 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 73;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, LastError);
    }
  }
  else
  {
    v7 = FWGetGlobalConfig(512, 0, 5, 2, 0, (__int64)&v21, (__int64)&v20);
    LastError = v7;
    if ( v7 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 74;
        goto LABEL_5;
      }
    }
    else
    {
      IsMember = 0;
      v8 = FWGetConfig2(v18, 10, v21, 1, (__int64)&v16, (__int64)&v20, (__int64)&IsMember);
      LastError = v8;
      if ( v8 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 75;
          goto LABEL_5;
        }
      }
      else if ( !v16 )
      {
        v16 = 0;
        v9 = 0;
        while ( 1 )
        {
          if ( v9 >= 3 )
          {
            v0 = 1;
            goto LABEL_28;
          }
          v10 = FwSidCreate((unsigned int)*(&v12 + 2 * v9), 0, &SidToCheck, LastError);
          LastError = v10;
          IsMember = 0;
          if ( v10 )
            break;
          if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
          {
            LastError = GetLastError();
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 77;
              goto LABEL_5;
            }
            goto LABEL_28;
          }
          if ( IsMember != *(&v13 + 2 * v16) )
            goto LABEL_28;
          FwSidDestroy(SidToCheck);
          v9 = v16 + 1;
          SidToCheck = 0;
          ++v16;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 76;
          goto LABEL_5;
        }
      }
    }
  }
LABEL_28:
  if ( v18 )
    FWClosePolicyStore(v18, v2, v3, LastError);
  FwSidDestroy(SidToCheck);
  return v0;
}

```

## disassembly

```asm
0x18002e484  push    rbp
0x18002e486  push    rbx
0x18002e487  push    rsi
0x18002e488  push    rdi
0x18002e489  lea     rbp, [rsp-3Fh]
0x18002e48e  sub     rsp, 98h
0x18002e495  mov     rax, cs:__security_cookie
0x18002e49c  xor     rax, rsp
0x18002e49f  mov     [rbp+57h+var_30], rax
0x18002e4a3  xor     edi, edi
0x18002e4a5  mov     [rbp+57h+var_68], 6
0x18002e4ad  mov     ecx, 221h
0x18002e4b2  mov     [rbp+57h+var_48], rdi
0x18002e4b6  xor     edx, edx
0x18002e4b8  mov     [rbp+57h+var_38], edi
0x18002e4bb  mov     ebx, edi
0x18002e4bd  mov     [rbp+57h+var_58], edi
0x18002e4c0  lea     eax, [rdi+4]
0x18002e4c3  mov     [rbp+57h+var_60], 12h
0x18002e4cb  mov     [rbp+57h+var_3C], eax
0x18002e4ce  lea     esi, [rdi+1]
0x18002e4d1  mov     [rbp+57h+var_70], eax
0x18002e4d4  lea     r8d, [rdi+5]
0x18002e4d8  lea     rax, [rbp+57h+var_48]
0x18002e4dc  mov     [rbp+57h+var_6C], esi
0x18002e4df  mov     [rsp+0B0h+var_88], rax
0x18002e4e4  mov     r9d, esi
0x18002e4e7  mov     dword ptr [rsp+0B0h+var_90], edi
0x18002e4eb  mov     [rbp+57h+SidToCheck], rdi
0x18002e4ef  call    FWOpenPolicyStore
0x18002e4f4  mov     r9d, eax
0x18002e4f7  test    eax, eax
0x18002e4f9  jz      short loc_18002E534
0x18002e4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e502  lea     rax, WPP_GLOBAL_Control
0x18002e509  cmp     rcx, rax
0x18002e50c  jz      loc_18002E6B0
0x18002e512  test    [rcx+1Ch], sil
0x18002e516  jz      loc_18002E6B0
0x18002e51c  lea     edx, [rdi+49h]
0x18002e51f  mov     rcx, [rcx+10h]
0x18002e523  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18002e52a  call    WPP_SF_d
0x18002e52f  jmp     loc_18002E6B0
0x18002e534  xor     edx, edx
0x18002e536  lea     rax, [rbp+57h+var_3C]
0x18002e53a  mov     [rsp+0B0h+var_80], rax
0x18002e53f  mov     ecx, 200h
0x18002e544  lea     rax, [rbp+57h+var_38]
0x18002e548  mov     [rsp+0B0h+var_88], rax
0x18002e54d  lea     r9d, [rdx+2]
0x18002e551  mov     dword ptr [rsp+0B0h+var_90], edi
0x18002e555  lea     r8d, [rdx+5]
0x18002e559  call    FWGetGlobalConfig
0x18002e55e  mov     r9d, eax
0x18002e561  test    eax, eax
0x18002e563  jz      short loc_18002E58D
0x18002e565  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e56c  lea     rax, WPP_GLOBAL_Control
0x18002e573  cmp     rcx, rax
0x18002e576  jz      loc_18002E6B0
0x18002e57c  test    [rcx+1Ch], sil
0x18002e580  jz      loc_18002E6B0
0x18002e586  mov     edx, 4Ah ; 'J'
0x18002e58b  jmp     short loc_18002E51F
0x18002e58d  mov     r8d, [rbp+57h+var_38]
0x18002e591  lea     rax, [rbp+57h+IsMember]
0x18002e595  mov     rcx, [rbp+57h+var_48]
0x18002e599  mov     r9d, esi
0x18002e59c  mov     [rsp+0B0h+var_80], rax
0x18002e5a1  mov     edx, 0Ah
0x18002e5a6  lea     rax, [rbp+57h+var_3C]
0x18002e5aa  mov     [rbp+57h+IsMember], edi
0x18002e5ad  mov     [rsp+0B0h+var_88], rax
0x18002e5b2  lea     rax, [rbp+57h+var_58]
0x18002e5b6  mov     [rsp+0B0h+var_90], rax
0x18002e5bb  call    FWGetConfig2
0x18002e5c0  mov     r9d, eax
0x18002e5c3  test    eax, eax
0x18002e5c5  jz      short loc_18002E5F2
0x18002e5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e5ce  lea     rax, WPP_GLOBAL_Control
0x18002e5d5  cmp     rcx, rax
0x18002e5d8  jz      loc_18002E6B0
0x18002e5de  test    [rcx+1Ch], sil
0x18002e5e2  jz      loc_18002E6B0
0x18002e5e8  mov     edx, 4Bh ; 'K'
0x18002e5ed  jmp     loc_18002E51F
0x18002e5f2  cmp     [rbp+57h+var_58], edi
0x18002e5f5  jnz     loc_18002E6B0
0x18002e5fb  mov     [rbp+57h+var_58], edi
0x18002e5fe  mov     eax, edi
0x18002e600  cmp     eax, 3
0x18002e603  jnb     loc_18002E6AE
0x18002e609  mov     ecx, eax
0x18002e60b  lea     r8, [rbp+57h+SidToCheck]
0x18002e60f  xor     edx, edx
0x18002e611  mov     ecx, [rbp+rcx*8+57h+var_70]
0x18002e615  call    cs:__imp_FwSidCreate
0x18002e61b  movzx   r9d, ax
0x18002e61f  mov     [rbp+57h+IsMember], edi
0x18002e622  test    r9d, r9d
0x18002e625  jnz     short loc_18002E68B
0x18002e627  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18002e62b  lea     r8, [rbp+57h+IsMember]; IsMember
0x18002e62f  xor     ecx, ecx; TokenHandle
0x18002e631  call    cs:__imp_CheckTokenMembership
0x18002e637  test    eax, eax
0x18002e639  jz      short loc_18002E65F
0x18002e63b  mov     eax, [rbp+57h+var_58]
0x18002e63e  mov     ecx, [rbp+rax*8+57h+var_6C]
0x18002e642  cmp     [rbp+57h+IsMember], ecx
0x18002e645  jnz     short loc_18002E6B0
0x18002e647  mov     rcx, [rbp+57h+SidToCheck]
0x18002e64b  call    cs:__imp_FwSidDestroy
0x18002e651  mov     eax, [rbp+57h+var_58]
0x18002e654  add     eax, esi
0x18002e656  mov     [rbp+57h+SidToCheck], rdi
0x18002e65a  mov     [rbp+57h+var_58], eax
0x18002e65d  jmp     short loc_18002E600
0x18002e65f  call    cs:__imp_GetLastError
0x18002e665  mov     r9d, eax
0x18002e668  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e66f  lea     rax, WPP_GLOBAL_Control
0x18002e676  cmp     rcx, rax
0x18002e679  jz      short loc_18002E6B0
0x18002e67b  test    [rcx+1Ch], sil
0x18002e67f  jz      short loc_18002E6B0
0x18002e681  mov     edx, 4Dh ; 'M'
0x18002e686  jmp     loc_18002E51F
0x18002e68b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e692  lea     rax, WPP_GLOBAL_Control
0x18002e699  cmp     rcx, rax
0x18002e69c  jz      short loc_18002E6B0
0x18002e69e  test    [rcx+1Ch], sil
0x18002e6a2  jz      short loc_18002E6B0
0x18002e6a4  mov     edx, 4Ch ; 'L'
0x18002e6a9  jmp     loc_18002E51F
0x18002e6ae  mov     ebx, esi
0x18002e6b0  mov     rcx, [rbp+57h+var_48]
0x18002e6b4  test    rcx, rcx
0x18002e6b7  jz      short loc_18002E6BE
0x18002e6b9  call    FWClosePolicyStore
0x18002e6be  mov     rcx, [rbp+57h+SidToCheck]
0x18002e6c2  call    cs:__imp_FwSidDestroy
0x18002e6c8  mov     eax, ebx
0x18002e6ca  mov     rcx, [rbp+57h+var_30]
0x18002e6ce  xor     rcx, rsp; StackCookie
0x18002e6d1  call    __security_check_cookie
0x18002e6d6  add     rsp, 98h
0x18002e6dd  pop     rdi
0x18002e6de  pop     rsi
0x18002e6df  pop     rbx
0x18002e6e0  pop     rbp
0x18002e6e1  retn
```
