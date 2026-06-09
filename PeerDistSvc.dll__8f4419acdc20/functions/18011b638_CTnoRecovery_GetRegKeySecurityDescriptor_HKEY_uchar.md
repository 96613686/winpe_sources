# CTnoRecovery::GetRegKeySecurityDescriptor(HKEY__ *,uchar * *)

- ea: `0x18011b638`
- end: `0x18011b83c`
- name: `?GetRegKeySecurityDescriptor@CTnoRecovery@@CAJPEAUHKEY__@@PEAPEAE@Z`
- size: `516`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18011b0b4`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x18001fc30`
- `0x18011b638`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18011b66d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18011b782`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18011b66d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18011b782`

## pseudocode

```c
__int64 __fastcall CTnoRecovery::GetRegKeySecurityDescriptor(HKEY hKey, unsigned __int8 **a2)
{
  int KeySecurity; // ebx
  void *v5; // rdi
  void *v6; // rcx
  DWORD cbSecurityDescriptor; // [rsp+60h] [rbp+8h] BYREF

  cbSecurityDescriptor = 0;
  if ( hKey && a2 )
  {
    KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor);
    if ( !KeySecurity )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids);
      }
      KeySecurity = -2147418113;
LABEL_22:
      v6 = 0;
LABEL_23:
      operator delete(v6);
      return (unsigned int)KeySecurity;
    }
    if ( KeySecurity != 122 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          25,
          WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
          (unsigned int)KeySecurity);
      }
      if ( KeySecurity > 0 )
        KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
      goto LABEL_22;
    }
    v5 = operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)std::nothrow);
    operator delete(0);
    if ( !v5 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          26,
          WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
          cbSecurityDescriptor);
      }
      KeySecurity = -2147024882;
      goto LABEL_22;
    }
    KeySecurity = RegGetKeySecurity(hKey, 4u, v5, &cbSecurityDescriptor);
    if ( KeySecurity )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          27,
          WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
          (unsigned int)KeySecurity);
      }
      if ( KeySecurity > 0 )
        KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
      v6 = v5;
      goto LABEL_23;
    }
    *a2 = (unsigned __int8 *)v5;
    operator delete(0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids, hKey, a2);
    }
    operator delete(0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18011b638  push    rbx
0x18011b63a  push    rbp
0x18011b63b  push    rsi
0x18011b63c  push    rdi
0x18011b63d  sub     rsp, 38h
0x18011b641  mov     [rsp+58h+cbSecurityDescriptor], 0
0x18011b649  mov     rsi, rdx
0x18011b64c  mov     rbp, rcx
0x18011b64f  test    rcx, rcx
0x18011b652  jz      loc_18011B7E8
0x18011b658  test    rdx, rdx
0x18011b65b  jz      loc_18011B7E8
0x18011b661  xor     r8d, r8d; pSecurityDescriptor
0x18011b664  lea     r9, [rsp+58h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18011b669  lea     edx, [r8+4]; SecurityInformation
0x18011b66d  call    cs:__imp_RegGetKeySecurity
0x18011b673  mov     ebx, eax
0x18011b675  test    eax, eax
0x18011b677  jnz     short loc_18011B6B8
0x18011b679  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b680  lea     rax, WPP_GLOBAL_Control
0x18011b687  cmp     rcx, rax
0x18011b68a  jz      short loc_18011B6AE
0x18011b68c  test    dword ptr [rcx+6Ch], 8000000h
0x18011b693  jz      short loc_18011B6AE
0x18011b695  cmp     byte ptr [rcx+69h], 1
0x18011b699  jb      short loc_18011B6AE
0x18011b69b  mov     rcx, [rcx+60h]
0x18011b69f  lea     edx, [rbx+18h]
0x18011b6a2  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b6a9  call    WPP_SF_
0x18011b6ae  mov     ebx, 8000FFFFh
0x18011b6b3  jmp     loc_18011B764
0x18011b6b8  cmp     ebx, 7Ah ; 'z'
0x18011b6bb  jz      short loc_18011B706
0x18011b6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b6c4  lea     rax, WPP_GLOBAL_Control
0x18011b6cb  cmp     rcx, rax
0x18011b6ce  jz      short loc_18011B6F7
0x18011b6d0  test    dword ptr [rcx+6Ch], 8000000h
0x18011b6d7  jz      short loc_18011B6F7
0x18011b6d9  cmp     byte ptr [rcx+69h], 1
0x18011b6dd  jb      short loc_18011B6F7
0x18011b6df  mov     rcx, [rcx+60h]
0x18011b6e3  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b6ea  mov     edx, 19h
0x18011b6ef  mov     r9d, ebx
0x18011b6f2  call    WPP_SF_d
0x18011b6f7  test    ebx, ebx
0x18011b6f9  jle     short loc_18011B764
0x18011b6fb  movzx   ebx, bx
0x18011b6fe  or      ebx, 80070000h
0x18011b704  jmp     short loc_18011B764
0x18011b706  mov     ecx, [rsp+58h+cbSecurityDescriptor]; unsigned __int64
0x18011b70a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18011b711  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18011b716  xor     ecx, ecx; Block
0x18011b718  mov     rdi, rax
0x18011b71b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b720  test    rdi, rdi
0x18011b723  jnz     short loc_18011B772
0x18011b725  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b72c  lea     rax, WPP_GLOBAL_Control
0x18011b733  cmp     rcx, rax
0x18011b736  jz      short loc_18011B75F
0x18011b738  test    dword ptr [rcx+6Ch], 8000000h
0x18011b73f  jz      short loc_18011B75F
0x18011b741  cmp     byte ptr [rcx+69h], 1
0x18011b745  jb      short loc_18011B75F
0x18011b747  mov     r9d, [rsp+58h+cbSecurityDescriptor]
0x18011b74c  lea     edx, [rdi+1Ah]
0x18011b74f  mov     rcx, [rcx+60h]
0x18011b753  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b75a  call    WPP_SF_d
0x18011b75f  mov     ebx, 8007000Eh
0x18011b764  xor     ecx, ecx; Block
0x18011b766  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b76b  mov     eax, ebx
0x18011b76d  jmp     loc_18011B833
0x18011b772  lea     r9, [rsp+58h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18011b777  mov     r8, rdi; pSecurityDescriptor
0x18011b77a  mov     edx, 4; SecurityInformation
0x18011b77f  mov     rcx, rbp; hKey
0x18011b782  call    cs:__imp_RegGetKeySecurity
0x18011b788  mov     ebx, eax
0x18011b78a  test    eax, eax
0x18011b78c  jz      short loc_18011B7DA
0x18011b78e  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b795  lea     rax, WPP_GLOBAL_Control
0x18011b79c  cmp     rcx, rax
0x18011b79f  jz      short loc_18011B7C8
0x18011b7a1  test    dword ptr [rcx+6Ch], 8000000h
0x18011b7a8  jz      short loc_18011B7C8
0x18011b7aa  cmp     byte ptr [rcx+69h], 1
0x18011b7ae  jb      short loc_18011B7C8
0x18011b7b0  mov     rcx, [rcx+60h]
0x18011b7b4  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b7bb  mov     edx, 1Bh
0x18011b7c0  mov     r9d, ebx
0x18011b7c3  call    WPP_SF_d
0x18011b7c8  test    ebx, ebx
0x18011b7ca  jle     short loc_18011B7D5
0x18011b7cc  movzx   ebx, bx
0x18011b7cf  or      ebx, 80070000h
0x18011b7d5  mov     rcx, rdi
0x18011b7d8  jmp     short loc_18011B766
0x18011b7da  xor     ecx, ecx; Block
0x18011b7dc  mov     [rsi], rdi
0x18011b7df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b7e4  xor     eax, eax
0x18011b7e6  jmp     short loc_18011B833
0x18011b7e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b7ef  lea     rax, WPP_GLOBAL_Control
0x18011b7f6  cmp     rcx, rax
0x18011b7f9  jz      short loc_18011B827
0x18011b7fb  test    dword ptr [rcx+6Ch], 8000000h
0x18011b802  jz      short loc_18011B827
0x18011b804  cmp     byte ptr [rcx+69h], 1
0x18011b808  jb      short loc_18011B827
0x18011b80a  mov     rcx, [rcx+60h]
0x18011b80e  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b815  mov     edx, 17h
0x18011b81a  mov     [rsp+58h+var_38], rsi
0x18011b81f  mov     r9, rbp
0x18011b822  call    WPP_SF_qq
0x18011b827  xor     ecx, ecx; Block
0x18011b829  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011b82e  mov     eax, 80070057h
0x18011b833  add     rsp, 38h
0x18011b837  pop     rdi
0x18011b838  pop     rsi
0x18011b839  pop     rbp
0x18011b83a  pop     rbx
0x18011b83b  retn
```
