# CUserVaultMgr::IsRoamingProfilePath(ushort const *)

- ea: `0x18000d5c4`
- end: `0x18000d756`
- name: `?IsRoamingProfilePath@CUserVaultMgr@@AEAAEPEBG@Z`
- size: `402`
- prototype: `unsigned __int8 __fastcall(CUserVaultMgr *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000d3a8`
- `0x18003c62c`

## callees

- `0x180003140`
- `0x18000d5c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d6c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000d6c6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000d730`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000d730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d606`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d606`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d61c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d61c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d5ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d67d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d67d`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18000d69f`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18000d69f`

## pseudocode

```c
unsigned __int8 __fastcall CUserVaultMgr::IsRoamingProfilePath(CUserVaultMgr *this, const unsigned __int16 *a2)
{
  HANDLE CurrentThread; // rax
  void *v5; // rsi
  unsigned int v6; // edi
  const wchar_t *v7; // rax
  const wchar_t *v8; // rbx
  int v9; // eax
  __int64 v10; // [rsp+20h] [rbp-50h] BYREF
  const wchar_t *v11; // [rsp+28h] [rbp-48h]
  __int64 v12; // [rsp+30h] [rbp-40h]
  BOOL (__stdcall *v13)(HANDLE); // [rsp+38h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+48h] [rbp-28h]
  __int64 v16; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v17; // [rsp+58h] [rbp-18h]
  int v18; // [rsp+60h] [rbp-10h]

  v17 = 0;
  v18 = 0;
  v16 = 0;
  v13 = CloseHandle;
  TokenHandle = 0;
  v15 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v5 = TokenHandle;
    v11 = 0;
    LODWORD(v12) = 0;
    v10 = 0;
    v6 = 0;
    while ( 1 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
      v6 += 260;
      v7 = (const wchar_t *)LocalAlloc(0x40u, 2LL * v6);
      v8 = v7;
      v11 = v7;
      if ( !v7 )
        goto LABEL_10;
      v9 = ExpandEnvStringForUser(v5, L"%APPDATA%\\Microsoft\\Vault", v7, v6, v10, v11, v12, v13);
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v9 = (unsigned __int16)v9;
      if ( !v9 )
        break;
      if ( v9 != 122 )
        goto LABEL_10;
    }
    if ( (unsigned int)_o__wcsicmp(v8, L"%APPDATA%\\Microsoft\\Vault") )
    {
      v11 = 0;
      v17 = v8;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
      if ( wcsstr(a2, v8) )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v13);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v16);
        return 1;
      }
    }
    else
    {
LABEL_10:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v13);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v16);
    return 0;
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v13);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v16);
  return 0;
}

```

## disassembly

```asm
0x18000d5c4  push    rbp
0x18000d5c6  push    rbx
0x18000d5c7  push    rsi
0x18000d5c8  push    rdi
0x18000d5c9  push    r14
0x18000d5cb  mov     rbp, rsp
0x18000d5ce  sub     rsp, 70h
0x18000d5d2  mov     r14, rdx
0x18000d5d5  mov     [rbp+var_18], 0
0x18000d5dd  mov     [rbp+var_10], 0
0x18000d5e4  mov     [rbp+var_20], 0
0x18000d5ec  mov     rax, cs:__imp_CloseHandle
0x18000d5f3  mov     [rbp+var_38], rax
0x18000d5f7  mov     [rbp+TokenHandle], 0
0x18000d5ff  mov     [rbp+var_28], 0
0x18000d606  call    cs:__imp_GetCurrentThread
0x18000d60c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000d610  mov     edx, 0Ch; DesiredAccess
0x18000d615  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18000d619  mov     rcx, rax; ThreadHandle
0x18000d61c  call    cs:__imp_OpenThreadToken
0x18000d622  test    eax, eax
0x18000d624  jnz     short loc_18000D647
0x18000d626  lea     rcx, [rbp+var_38]
0x18000d62a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d62f  nop
0x18000d630  lea     rcx, [rbp+var_20]
0x18000d634  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d639  nop
0x18000d63a  xor     al, al
0x18000d63c  add     rsp, 70h
0x18000d640  pop     r14
0x18000d642  pop     rdi
0x18000d643  pop     rsi
0x18000d644  pop     rbx
0x18000d645  pop     rbp
0x18000d646  retn
0x18000d647  mov     rsi, [rbp+TokenHandle]
0x18000d64b  mov     [rbp+var_48], 0
0x18000d653  mov     dword ptr [rbp+var_40], 0
0x18000d65a  mov     [rbp+var_50], 0
0x18000d662  xor     edi, edi
0x18000d664  lea     rcx, [rbp+var_50]
0x18000d668  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d66d  add     edi, 104h
0x18000d673  mov     edx, edi
0x18000d675  add     rdx, rdx; uBytes
0x18000d678  mov     ecx, 40h ; '@'; uFlags
0x18000d67d  call    cs:__imp_LocalAlloc
0x18000d683  mov     rbx, rax
0x18000d686  mov     [rbp+var_48], rax
0x18000d68a  test    rax, rax
0x18000d68d  jz      short loc_18000D708
0x18000d68f  mov     r9d, edi
0x18000d692  mov     r8, rax
0x18000d695  lea     rdx, aAppdataMicroso_0; "%APPDATA%\\Microsoft\\Vault"
0x18000d69c  mov     rcx, rsi
0x18000d69f  call    cs:__imp_ExpandEnvStringForUser
0x18000d6a5  mov     ecx, eax
0x18000d6a7  and     ecx, 1FFF0000h
0x18000d6ad  cmp     ecx, 70000h
0x18000d6b3  jnz     short loc_18000D6B8
0x18000d6b5  movzx   eax, ax
0x18000d6b8  test    eax, eax
0x18000d6ba  jnz     short loc_18000D6F3
0x18000d6bc  lea     rdx, aAppdataMicroso_0; "%APPDATA%\\Microsoft\\Vault"
0x18000d6c3  mov     rcx, rbx
0x18000d6c6  call    cs:__imp__o__wcsicmp
0x18000d6cc  test    eax, eax
0x18000d6ce  jnz     short loc_18000D714
0x18000d6d0  lea     rcx, [rbp+var_50]
0x18000d6d4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d6d9  nop
0x18000d6da  lea     rcx, [rbp+var_38]
0x18000d6de  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d6e3  nop
0x18000d6e4  lea     rcx, [rbp+var_20]
0x18000d6e8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d6ed  nop
0x18000d6ee  jmp     loc_18000D63A
0x18000d6f3  cmp     eax, 7Ah ; 'z'
0x18000d6f6  jz      loc_18000D664
0x18000d6fc  lea     rcx, [rbp+var_50]
0x18000d700  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d705  nop
0x18000d706  jmp     short loc_18000D6DA
0x18000d708  lea     rcx, [rbp+var_50]
0x18000d70c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d711  nop
0x18000d712  jmp     short loc_18000D6DA
0x18000d714  mov     [rbp+var_48], 0
0x18000d71c  mov     [rbp+var_18], rbx
0x18000d720  lea     rcx, [rbp+var_50]
0x18000d724  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d729  nop
0x18000d72a  mov     rdx, rbx; SubStr
0x18000d72d  mov     rcx, r14; Str
0x18000d730  call    cs:__imp_wcsstr
0x18000d736  test    rax, rax
0x18000d739  jz      short loc_18000D6DA
0x18000d73b  lea     rcx, [rbp+var_38]
0x18000d73f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d744  nop
0x18000d745  lea     rcx, [rbp+var_20]
0x18000d749  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000d74e  nop
0x18000d74f  mov     al, 1
0x18000d751  jmp     loc_18000D63C
```
