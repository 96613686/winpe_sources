# UbpmpTokenGetNonInteractiveToken

- ea: `0x180023b50`
- end: `0x180023f7e`
- name: `UbpmpTokenGetNonInteractiveToken`
- size: `1070`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000aff0`
- `0x18000f284`
- `0x18002399c`

## callees

- `0x18000fbf0`
- `0x18001bcdc`
- `0x180023b50`
- `0x180023f84`
- `0x1800245a8`
- `0x180024630`
- `0x180024740`
- `0x180037440`
- `0x180040098`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023ba3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023bc1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023ba3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ebf`
- `SspiCli!LogonUserExExW` at `0x180023c6d`
- `SspiCli!LogonUserExExW` at `0x180023c6d`

## string_xrefs

- `0x180023bdc`: `LocalService`
- `0x180023ce1`: `NetworkService`

## pseudocode

```c
__int64 __fastcall UbpmpTokenGetNonInteractiveToken(
        __int64 a1,
        void *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        void **a5,
        void **a6)
{
  const unsigned __int16 *v6; // r15
  __int64 *v7; // rdi
  const unsigned __int16 *v8; // r14
  void *v12; // rbx
  const unsigned __int16 *v13; // rbx
  const unsigned __int16 *v14; // rbp
  const wchar_t *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // ecx
  const wchar_t *v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  DWORD S4UToken; // esi
  SECURITY_LOGON_TYPE v24; // ecx
  int v25; // r8d
  int v26; // r8d
  const wchar_t *v27; // r9
  const wchar_t *v28; // rax
  const unsigned __int16 *v29; // r9
  const wchar_t *v30; // r9
  const wchar_t *v31; // r9
  int v32; // r8d
  int v33; // r8d
  const wchar_t *v34; // r9
  const wchar_t *v35; // rax
  const unsigned __int16 *v36; // [rsp+A0h] [rbp+8h] BYREF
  const unsigned __int16 *v37; // [rsp+A8h] [rbp+10h] BYREF

  v6 = 0;
  v7 = (__int64 *)(a1 + 32);
  v8 = 0;
  v37 = 0;
  v36 = 0;
  if ( a2 )
    v12 = a2;
  else
    v12 = *(void **)(*(_QWORD *)(*v7 + 8) + 8LL);
  if ( *v7 )
  {
    v14 = *(const unsigned __int16 **)(*v7 + 16);
    if ( v14 )
    {
      v13 = 0;
      goto LABEL_10;
    }
  }
  if ( EqualSid(v12, qword_18004FF68) )
  {
    v13 = L"NT AUTHORITY";
    v14 = L"NetworkService";
    goto LABEL_10;
  }
  if ( EqualSid(v12, pSid2) )
  {
    v13 = L"NT AUTHORITY";
    v14 = L"LocalService";
LABEL_10:
    v15 = 0;
    goto LABEL_11;
  }
  if ( UbpmUtilsIsServiceSid(v12) )
    return (unsigned int)UbpmpTokenGetServiceAccountToken(v12, a5);
  UbpmUtilsGetAccountNamesFromSid((_DWORD)v12, 1, (unsigned int)&v36, (unsigned int)&v37, 0);
  v8 = v36;
  v6 = v37;
  v13 = v36;
  v14 = v37;
  if ( !*v7 )
    goto LABEL_10;
  v15 = *(const wchar_t **)(*v7 + 24);
LABEL_11:
  v16 = *v7;
  if ( (*(_DWORD *)(*v7 + 76) & 1) != 0 )
  {
    if ( a2 )
      v24 = Service;
    else
      v24 = *(_DWORD *)(v16 + 32);
    S4UToken = UbpmpTokenGetS4UToken(v14, v13, v24, a5, a6);
    if ( !S4UToken )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        if ( *v7 )
          v25 = *(_DWORD *)(*v7 + 32);
        else
          LOBYTE(v25) = 0;
        if ( v13 )
        {
          LODWORD(v31) = (_DWORD)v14;
        }
        else
        {
          v31 = L"NULL";
          v13 = L"NULL";
        }
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
          (_DWORD)v31,
          (__int64)v13,
          v25);
      }
      goto LABEL_20;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *v7 )
        v26 = *(_DWORD *)(*v7 + 32);
      else
        v26 = 0;
      v27 = L"NULL";
      v28 = L"NULL";
      if ( v13 )
        v28 = v13;
      if ( v14 )
        v27 = v14;
      WPP_SF_dSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v26, S4UToken, (__int64)v27, (__int64)v28, v26);
    }
    v29 = L"LogonUserS4U";
  }
  else
  {
    if ( a2 )
      v17 = 5;
    else
      v17 = *(_DWORD *)(v16 + 32);
    v18 = L"_SA_{262E99C9-6160-4871-ACEC-4E61736B6F21}";
    if ( (*(_DWORD *)(*v7 + 76) & 2) == 0 )
      v18 = v15;
    if ( (unsigned int)LogonUserExExW(v14, v13, v18, v17, 0, a3, a5, a6, 0, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        if ( *v7 )
          v33 = *(_DWORD *)(*v7 + 32);
        else
          LOBYTE(v33) = 0;
        v34 = L"NULL";
        v35 = L"NULL";
        if ( v13 )
          v35 = v13;
        if ( v14 )
          LODWORD(v34) = (_DWORD)v14;
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
          (_DWORD)v34,
          (__int64)v35,
          v33);
      }
      S4UToken = 0;
      goto LABEL_20;
    }
    S4UToken = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *v7 )
        v32 = *(_DWORD *)(*v7 + 32);
      else
        v32 = 0;
      if ( v13 )
      {
        v30 = v14;
      }
      else
      {
        v30 = L"NULL";
        v13 = L"NULL";
      }
      WPP_SF_dSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v32, S4UToken, (__int64)v30, (__int64)v13, v32);
    }
    v29 = L"LogonUserExEx";
  }
  ReportTaskEvent(g_hTaskEventManager, &LOGON_FAILURE, a4, v29, S4UToken);
LABEL_20:
  if ( v6 )
    UBPM_MIDL_user_free(v6, v19, v20, v21);
  if ( v8 )
    UBPM_MIDL_user_free(v8, v19, v20, v21);
  return S4UToken;
}

```

## disassembly

```asm
0x180023b50  mov     rax, rsp
0x180023b53  mov     [rax+18h], rbx
0x180023b57  push    rbp
0x180023b58  push    rsi
0x180023b59  push    rdi
0x180023b5a  push    r12
0x180023b5c  push    r13
0x180023b5e  push    r14
0x180023b60  push    r15
0x180023b62  sub     rsp, 60h
0x180023b66  xor     r15d, r15d
0x180023b69  lea     rdi, [rcx+20h]
0x180023b6d  xor     r14d, r14d
0x180023b70  mov     [rax+10h], r15
0x180023b74  mov     [rax+8], r14
0x180023b78  mov     r12, r9
0x180023b7b  mov     r13, r8
0x180023b7e  mov     rsi, rdx
0x180023b81  test    rdx, rdx
0x180023b84  jnz     short loc_180023BE5
0x180023b86  mov     rax, [rdi]
0x180023b89  mov     rcx, [rax+8]
0x180023b8d  mov     rbx, [rcx+8]
0x180023b91  mov     rbp, [rdi]
0x180023b94  test    rbp, rbp
0x180023b97  jnz     short loc_180023BEA
0x180023b99  mov     rdx, cs:qword_18004FF68; pSid2
0x180023ba0  mov     rcx, rbx; pSid1
0x180023ba3  call    cs:__imp_EqualSid
0x180023baa  nop     dword ptr [rax+rax+00h]
0x180023baf  test    eax, eax
0x180023bb1  jnz     loc_180023CDA
0x180023bb7  mov     rdx, cs:pSid2; pSid2
0x180023bbe  mov     rcx, rbx; pSid1
0x180023bc1  call    cs:__imp_EqualSid
0x180023bc8  nop     dword ptr [rax+rax+00h]
0x180023bcd  test    eax, eax
0x180023bcf  jz      loc_180023CED
0x180023bd5  lea     rbx, aNtAuthority; "NT AUTHORITY"
0x180023bdc  lea     rbp, Src; "LocalService"
0x180023be3  jmp     short loc_180023BF5
0x180023be5  mov     rbx, rsi
0x180023be8  jmp     short loc_180023B91
0x180023bea  mov     rbp, [rbp+10h]
0x180023bee  test    rbp, rbp
0x180023bf1  jz      short loc_180023B99
0x180023bf3  xor     ebx, ebx
0x180023bf5  xor     eax, eax
0x180023bf7  mov     rcx, [rdi]
0x180023bfa  mov     edx, [rcx+4Ch]
0x180023bfd  test    dl, 1
0x180023c00  jnz     loc_180023D11
0x180023c06  and     edx, 2
0x180023c09  test    rsi, rsi
0x180023c0c  jnz     loc_180023CD0
0x180023c12  mov     ecx, [rcx+20h]
0x180023c15  mov     [rsp+98h+var_48], 0
0x180023c1e  lea     r8, aSa262e99c96160; "_SA_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x180023c25  mov     [rsp+98h+var_50], 0
0x180023c2e  test    edx, edx
0x180023c30  mov     [rsp+98h+var_58], 0
0x180023c39  mov     r9d, ecx
0x180023c3c  cmovz   r8, rax
0x180023c40  mov     rdx, rbx
0x180023c43  mov     rax, [rsp+98h+arg_28]
0x180023c4b  mov     rcx, rbp
0x180023c4e  mov     [rsp+98h+var_60], rax
0x180023c53  mov     rax, [rsp+98h+arg_20]
0x180023c5b  mov     [rsp+98h+var_68], rax
0x180023c60  mov     [rsp+98h+var_70], r13
0x180023c65  mov     dword ptr [rsp+98h+var_78], 0
0x180023c6d  call    cs:__imp_LogonUserExExW
0x180023c74  nop     dword ptr [rax+rax+00h]
0x180023c79  test    eax, eax
0x180023c7b  jz      loc_180023EBF
0x180023c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c88  lea     rax, WPP_GLOBAL_Control
0x180023c8f  cmp     rcx, rax
0x180023c92  jz      short loc_180023CA1
0x180023c94  test    dword ptr [rcx+1Ch], 100h
0x180023c9b  jnz     loc_180023F17
0x180023ca1  xor     esi, esi
0x180023ca3  test    r15, r15
0x180023ca6  jnz     loc_180023F64
0x180023cac  test    r14, r14
0x180023caf  jnz     loc_180023F71
0x180023cb5  mov     rbx, [rsp+98h+arg_10]
0x180023cbd  mov     eax, esi
0x180023cbf  add     rsp, 60h
0x180023cc3  pop     r15
0x180023cc5  pop     r14
0x180023cc7  pop     r13
0x180023cc9  pop     r12
0x180023ccb  pop     rdi
0x180023ccc  pop     rsi
0x180023ccd  pop     rbp
0x180023cce  retn
0x180023cd0  mov     ecx, 5
0x180023cd5  jmp     loc_180023C15
0x180023cda  lea     rbx, aNtAuthority; "NT AUTHORITY"
0x180023ce1  lea     rbp, aNetworkservice; "NetworkService"
0x180023ce8  jmp     loc_180023BF5
0x180023ced  mov     rcx, rbx; pSid
0x180023cf0  call    ?UbpmUtilsIsServiceSid@@YAEPEAX@Z; UbpmUtilsIsServiceSid(void *)
0x180023cf5  mov     rcx, rbx; void *
0x180023cf8  test    al, al
0x180023cfa  jz      loc_180023D86
0x180023d00  mov     rdx, [rsp+98h+arg_20]; void **
0x180023d08  call    ?UbpmpTokenGetServiceAccountToken@@YAKPEAXPEAPEAX@Z; UbpmpTokenGetServiceAccountToken(void *,void * *)
0x180023d0d  mov     esi, eax
0x180023d0f  jmp     short loc_180023CB5
0x180023d11  test    rsi, rsi
0x180023d14  jz      short loc_180023D81
0x180023d16  mov     ecx, 5
0x180023d1b  mov     rax, [rsp+98h+arg_28]
0x180023d23  mov     r8d, ecx; LogonType
0x180023d26  mov     r9, [rsp+98h+arg_20]; void **
0x180023d2e  mov     rcx, rbp; Src
0x180023d31  mov     rdx, rbx; unsigned __int16 *
0x180023d34  mov     [rsp+98h+var_78], rax; void **
0x180023d39  call    ?UbpmpTokenGetS4UToken@@YAKPEBG0KPEAPEAX1@Z; UbpmpTokenGetS4UToken(ushort const *,ushort const *,ulong,void * *,void * *)
0x180023d3e  mov     esi, eax
0x180023d40  test    eax, eax
0x180023d42  jnz     loc_180023DD0
0x180023d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d4f  lea     rax, WPP_GLOBAL_Control
0x180023d56  cmp     rcx, rax
0x180023d59  jz      loc_180023CA3
0x180023d5f  test    dword ptr [rcx+1Ch], 100h
0x180023d66  jz      loc_180023CA3
0x180023d6c  mov     rax, [rdi]
0x180023d6f  test    rax, rax
0x180023d72  jz      loc_180023E84
0x180023d78  mov     r8d, [rax+20h]
0x180023d7c  jmp     loc_180023E87
0x180023d81  mov     ecx, [rcx+20h]
0x180023d84  jmp     short loc_180023D1B
0x180023d86  lea     r9, [rsp+98h+arg_8]
0x180023d8e  mov     [rsp+98h+var_78], r14
0x180023d93  lea     r8, [rsp+98h+arg_0]
0x180023d9b  mov     edx, 1
0x180023da0  call    UbpmUtilsGetAccountNamesFromSid
0x180023da5  mov     rax, [rdi]
0x180023da8  mov     r14, [rsp+98h+arg_0]
0x180023db0  mov     r15, [rsp+98h+arg_8]
0x180023db8  mov     rbx, r14
0x180023dbb  mov     rbp, r15
0x180023dbe  test    rax, rax
0x180023dc1  jz      loc_180023BF5
0x180023dc7  mov     rax, [rax+18h]
0x180023dcb  jmp     loc_180023BF7
0x180023dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023dd7  lea     rax, WPP_GLOBAL_Control
0x180023dde  cmp     rcx, rax
0x180023de1  jz      short loc_180023E32
0x180023de3  test    byte ptr [rcx+1Ch], 1
0x180023de7  jz      short loc_180023E32
0x180023de9  mov     rax, [rdi]
0x180023dec  test    rax, rax
0x180023def  jz      short loc_180023DF7
0x180023df1  mov     r8d, [rax+20h]
0x180023df5  jmp     short loc_180023DFA
0x180023df7  xor     r8d, r8d
0x180023dfa  mov     rcx, [rcx+10h]
0x180023dfe  lea     r9, aNull_0; "NULL"
0x180023e05  mov     rax, r9
0x180023e08  mov     dword ptr [rsp+98h+var_68], r8d
0x180023e0d  test    rbx, rbx
0x180023e10  mov     edx, 1Ch
0x180023e15  cmovnz  rax, rbx
0x180023e19  test    rbp, rbp
0x180023e1c  mov     [rsp+98h+var_70], rax
0x180023e21  cmovnz  r9, rbp
0x180023e25  mov     [rsp+98h+var_78], r9
0x180023e2a  mov     r9d, esi
0x180023e2d  call    WPP_SF_dSSd
0x180023e32  lea     r9, aLogonusers4u; "LogonUserS4U"
0x180023e39  jmp     short loc_180023E65
0x180023e3b  mov     r9, rbp
0x180023e3e  mov     rcx, [rcx+10h]
0x180023e42  mov     edx, 1Eh
0x180023e47  mov     dword ptr [rsp+98h+var_68], r8d
0x180023e4c  mov     [rsp+98h+var_70], rbx
0x180023e51  mov     [rsp+98h+var_78], r9
0x180023e56  mov     r9d, esi
0x180023e59  call    WPP_SF_dSSd
0x180023e5e  lea     r9, aLogonuserexex; "LogonUserExEx"
0x180023e65  mov     rcx, cs:g_hTaskEventManager; void *
0x180023e6c  lea     rdx, LOGON_FAILURE; struct _EVENT_DESCRIPTOR *
0x180023e73  mov     r8, r12; unsigned __int16 *
0x180023e76  mov     dword ptr [rsp+98h+var_78], esi; unsigned int
0x180023e7a  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2K@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong)
0x180023e7f  jmp     loc_180023CA3
0x180023e84  xor     r8d, r8d
0x180023e87  test    rbx, rbx
0x180023e8a  jnz     short loc_180023E98
0x180023e8c  lea     r9, aNull_0; "NULL"
0x180023e93  mov     rbx, r9
0x180023e96  jmp     short loc_180023E9B
0x180023e98  mov     r9, rbp
0x180023e9b  mov     rcx, [rcx+10h]
0x180023e9f  mov     edx, 1Dh
0x180023ea4  mov     dword ptr [rsp+98h+var_70], r8d
0x180023ea9  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180023eb0  mov     [rsp+98h+var_78], rbx
0x180023eb5  call    WPP_SF_SSd
0x180023eba  jmp     loc_180023CA3
0x180023ebf  call    cs:__imp_GetLastError
0x180023ec6  nop     dword ptr [rax+rax+00h]
0x180023ecb  mov     esi, eax
0x180023ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ed4  lea     rax, WPP_GLOBAL_Control
0x180023edb  cmp     rcx, rax
0x180023ede  jz      loc_180023E5E
0x180023ee4  test    byte ptr [rcx+1Ch], 1
0x180023ee8  jz      loc_180023E5E
0x180023eee  mov     rax, [rdi]
0x180023ef1  test    rax, rax
0x180023ef4  jz      short loc_180023EFC
0x180023ef6  mov     r8d, [rax+20h]
0x180023efa  jmp     short loc_180023EFF
0x180023efc  xor     r8d, r8d
0x180023eff  test    rbx, rbx
0x180023f02  jnz     loc_180023E3B
0x180023f08  lea     r9, aNull_0; "NULL"
0x180023f0f  mov     rbx, r9
0x180023f12  jmp     loc_180023E3E
0x180023f17  mov     rax, [rdi]
0x180023f1a  test    rax, rax
0x180023f1d  jz      short loc_180023F25
0x180023f1f  mov     r8d, [rax+20h]
0x180023f23  jmp     short loc_180023F28
0x180023f25  xor     r8d, r8d
0x180023f28  mov     rcx, [rcx+10h]
0x180023f2c  lea     r9, aNull_0; "NULL"
0x180023f33  test    rbx, rbx
0x180023f36  mov     dword ptr [rsp+98h+var_70], r8d
0x180023f3b  mov     rax, r9
0x180023f3e  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180023f45  cmovnz  rax, rbx
0x180023f49  mov     edx, 1Fh
0x180023f4e  test    rbp, rbp
0x180023f51  mov     [rsp+98h+var_78], rax
0x180023f56  cmovnz  r9, rbp
0x180023f5a  call    WPP_SF_SSd
0x180023f5f  jmp     loc_180023CA1
0x180023f64  mov     rcx, r15
0x180023f67  call    UBPM_MIDL_user_free
0x180023f6c  jmp     loc_180023CAC
0x180023f71  mov     rcx, r14
0x180023f74  call    UBPM_MIDL_user_free
0x180023f79  jmp     loc_180023CB5
```
