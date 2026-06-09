# CheckIsStandardUser(bool *)

- ea: `0x18004a384`
- end: `0x18004a5d5`
- name: `?CheckIsStandardUser@@YAJPEA_N@Z`
- size: `593`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18004d7f0`
- `0x18004e620`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001a508`
- `0x180022008`
- `0x180034070`
- `0x180044408`
- `0x18004a384`
- `0x18006a200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a464`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004a454`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004a454`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004a439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004a439`

## pseudocode

```c
__int64 __fastcall CheckIsStandardUser(bool *a1)
{
  PVOID *v2; // rcx
  int v3; // ebx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v7; // rdx
  unsigned int FullToken; // eax
  bool v10; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+28h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF

  TokenHandle = 0;
  v11 = 0;
  v10 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = -2147467261;
    if ( v2 == &WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 )
      goto LABEL_33;
    v4 = 194;
    goto LABEL_8;
  }
  *a1 = 0;
  SH<void *,SH_HANDLE>::Reset(&TokenHandle);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Au, 0, &TokenHandle) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      v3 = CNgscbToken::CheckIsAdminToken((CNgscbToken *)&TokenHandle, &v10);
      if ( !v3 )
        goto LABEL_31;
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      {
LABEL_30:
        if ( v3 < 0 )
          goto LABEL_33;
LABEL_31:
        *a1 = !v10;
        goto LABEL_32;
      }
      v7 = 196;
    }
    else
    {
      FullToken = CNgscbToken::GetFullToken((CNgscbToken *)&TokenHandle, (struct CNgscbToken *)&v11);
      v3 = FullToken;
      if ( FullToken )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            197,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            FullToken);
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 < 0 )
          goto LABEL_33;
      }
      v3 = CNgscbToken::CheckIsAdminToken((CNgscbToken *)&v11, &v10);
      if ( !v3 )
        goto LABEL_31;
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_30;
      v7 = 198;
    }
    WPP_SF_d(v2[2], v7, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v3);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v4 = 195;
LABEL_8:
      WPP_SF_d(v2[2], v4, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v3);
LABEL_32:
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_33:
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
      WPP_SF_d(v2[2], 199, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v3);
  }
LABEL_36:
  SH<void *,SH_HANDLE>::Reset(&v11);
  SH<void *,SH_HANDLE>::Reset(&TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004a384  mov     [rsp-18h+arg_8], rbx
0x18004a389  mov     [rsp-18h+arg_10], rdi
0x18004a38e  push    rbp
0x18004a38f  push    r14
0x18004a391  push    r15
0x18004a393  mov     rbp, rsp
0x18004a396  sub     rsp, 40h
0x18004a39a  mov     rax, cs:__security_cookie
0x18004a3a1  xor     rax, rsp
0x18004a3a4  mov     [rbp+var_8], rax
0x18004a3a8  mov     rdi, rcx
0x18004a3ab  mov     [rbp+TokenHandle], 0
0x18004a3b3  mov     [rbp+var_18], 0
0x18004a3bb  mov     [rbp+var_20], 0
0x18004a3bf  lea     r14, WPP_GLOBAL_Control
0x18004a3c6  lea     r15, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004a3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3d4  cmp     rcx, r14
0x18004a3d7  jz      short loc_18004A3F7
0x18004a3d9  test    byte ptr [rcx+1Ch], 20h
0x18004a3dd  jz      short loc_18004A3F7
0x18004a3df  mov     edx, 0C1h
0x18004a3e4  mov     r8, r15
0x18004a3e7  mov     rcx, [rcx+10h]
0x18004a3eb  call    WPP_SF_
0x18004a3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3f7  test    rdi, rdi
0x18004a3fa  jnz     short loc_18004A42D
0x18004a3fc  mov     ebx, 80004003h
0x18004a401  cmp     rcx, r14
0x18004a404  jz      loc_18004A59F
0x18004a40a  test    byte ptr [rcx+1Ch], 40h
0x18004a40e  jz      loc_18004A57F
0x18004a414  mov     edx, 0C2h
0x18004a419  mov     r9d, ebx
0x18004a41c  mov     r8, r15
0x18004a41f  mov     rcx, [rcx+10h]
0x18004a423  call    WPP_SF_d
0x18004a428  jmp     loc_18004A578
0x18004a42d  mov     byte ptr [rdi], 0
0x18004a430  lea     rcx, [rbp+TokenHandle]
0x18004a434  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18004a439  call    cs:__imp_GetCurrentThread
0x18004a440  nop     dword ptr [rax+rax+00h]
0x18004a445  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004a449  xor     r8d, r8d; OpenAsSelf
0x18004a44c  mov     edx, 2000Ah; DesiredAccess
0x18004a451  mov     rcx, rax; ThreadHandle
0x18004a454  call    cs:__imp_OpenThreadToken
0x18004a45b  nop     dword ptr [rax+rax+00h]
0x18004a460  test    eax, eax
0x18004a462  jnz     short loc_18004A4A3
0x18004a464  call    cs:__imp_GetLastError
0x18004a46b  nop     dword ptr [rax+rax+00h]
0x18004a470  mov     ebx, eax
0x18004a472  test    eax, eax
0x18004a474  jle     short loc_18004A47F
0x18004a476  movzx   ebx, ax
0x18004a479  or      ebx, 80070000h
0x18004a47f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a486  cmp     rcx, r14
0x18004a489  jz      loc_18004A59F
0x18004a48f  test    byte ptr [rcx+1Ch], 40h
0x18004a493  jz      loc_18004A57F
0x18004a499  mov     edx, 0C3h
0x18004a49e  jmp     loc_18004A419
0x18004a4a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18004a4aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18004a4af  lea     rcx, [rbp+TokenHandle]; this
0x18004a4b3  test    al, al
0x18004a4b5  jz      short loc_18004A4EB
0x18004a4b7  lea     rdx, [rbp+var_20]; bool *
0x18004a4bb  call    ?CheckIsAdminToken@CNgscbToken@@QEBAJPEA_N@Z; CNgscbToken::CheckIsAdminToken(bool *)
0x18004a4c0  mov     ebx, eax
0x18004a4c2  test    eax, eax
0x18004a4c4  jz      loc_18004A56F
0x18004a4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4d1  cmp     rcx, r14
0x18004a4d4  jz      loc_18004A56B
0x18004a4da  test    byte ptr [rcx+1Ch], 40h
0x18004a4de  jz      loc_18004A56B
0x18004a4e4  mov     edx, 0C4h
0x18004a4e9  jmp     short loc_18004A555
0x18004a4eb  lea     rdx, [rbp+var_18]; struct CNgscbToken *
0x18004a4ef  call    ?GetFullToken@CNgscbToken@@QEBAJAEAV1@@Z; CNgscbToken::GetFullToken(CNgscbToken &)
0x18004a4f4  mov     ebx, eax
0x18004a4f6  test    eax, eax
0x18004a4f8  jz      short loc_18004A52B
0x18004a4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a501  cmp     rcx, r14
0x18004a504  jz      short loc_18004A527
0x18004a506  test    byte ptr [rcx+1Ch], 40h
0x18004a50a  jz      short loc_18004A527
0x18004a50c  mov     edx, 0C5h
0x18004a511  mov     r9d, eax
0x18004a514  mov     r8, r15
0x18004a517  mov     rcx, [rcx+10h]
0x18004a51b  call    WPP_SF_d
0x18004a520  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a527  test    ebx, ebx
0x18004a529  js      short loc_18004A57F
0x18004a52b  lea     rdx, [rbp+var_20]; bool *
0x18004a52f  lea     rcx, [rbp+var_18]; this
0x18004a533  call    ?CheckIsAdminToken@CNgscbToken@@QEBAJPEA_N@Z; CNgscbToken::CheckIsAdminToken(bool *)
0x18004a538  mov     ebx, eax
0x18004a53a  test    eax, eax
0x18004a53c  jz      short loc_18004A56F
0x18004a53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a545  cmp     rcx, r14
0x18004a548  jz      short loc_18004A56B
0x18004a54a  test    byte ptr [rcx+1Ch], 40h
0x18004a54e  jz      short loc_18004A56B
0x18004a550  mov     edx, 0C6h
0x18004a555  mov     r9d, ebx
0x18004a558  mov     r8, r15
0x18004a55b  mov     rcx, [rcx+10h]
0x18004a55f  call    WPP_SF_d
0x18004a564  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a56b  test    ebx, ebx
0x18004a56d  js      short loc_18004A57F
0x18004a56f  cmp     [rbp+var_20], 0
0x18004a573  setz    al
0x18004a576  mov     [rdi], al
0x18004a578  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a57f  cmp     rcx, r14
0x18004a582  jz      short loc_18004A59F
0x18004a584  test    byte ptr [rcx+1Ch], 20h
0x18004a588  jz      short loc_18004A59F
0x18004a58a  mov     edx, 0C7h
0x18004a58f  mov     r9d, ebx
0x18004a592  mov     r8, r15
0x18004a595  mov     rcx, [rcx+10h]
0x18004a599  call    WPP_SF_d
0x18004a59e  nop
0x18004a59f  lea     rcx, [rbp+var_18]
0x18004a5a3  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18004a5a8  nop
0x18004a5a9  lea     rcx, [rbp+TokenHandle]
0x18004a5ad  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18004a5b2  mov     eax, ebx
0x18004a5b4  mov     rcx, [rbp+var_8]
0x18004a5b8  xor     rcx, rsp; StackCookie
0x18004a5bb  call    __security_check_cookie
0x18004a5c0  mov     rbx, [rsp+40h+arg_8]
0x18004a5c5  mov     rdi, [rsp+40h+arg_10]
0x18004a5ca  add     rsp, 40h
0x18004a5ce  pop     r15
0x18004a5d0  pop     r14
0x18004a5d2  pop     rbp
0x18004a5d3  retn
```
