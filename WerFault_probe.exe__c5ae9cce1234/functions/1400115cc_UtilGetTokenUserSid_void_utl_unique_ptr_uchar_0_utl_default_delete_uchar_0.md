# UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x1400115cc`
- end: `0x140011835`
- name: `?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001114c`

## callees

- `0x140002494`
- `0x140002728`
- `0x140002d24`
- `0x14000f930`
- `0x1400115cc`
- `0x14001444c`
- `0x140014474`
- `0x140015b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001163c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001163c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001162e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400116d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001162e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400116d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenUserSid(HANDLE TokenHandle, const struct std::nothrow_t *a2)
{
  PSID *v4; // rsi
  PSID v5; // r15
  void *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  signed int LastError; // eax
  int v12; // ebx
  CUserModeHangReport *v13; // rcx
  __int64 v14; // rdx
  signed int v15; // eax
  void *v16; // rcx
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  PSID v19; // [rsp+70h] [rbp+40h] BYREF
  __int64 v20; // [rsp+78h] [rbp+48h]

  v4 = 0;
  v20 = 0;
  TokenInformationLength = 0;
  v5 = 0;
  v19 = 0;
  if ( !a2 || !TokenHandle )
  {
    v12 = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
    goto LABEL_39;
  }
  v6 = *(void **)a2;
  *(_QWORD *)a2 = 0;
  if ( v6 )
    operator delete(v6, a2);
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v12 = -2147418113;
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
    goto LABEL_39;
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( v12 >= 0 )
  {
    v12 = -2147467259;
LABEL_11:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 11;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v12);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  if ( (_WORD)v12 != 122 )
    goto LABEL_11;
  v4 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
    {
      v12 = UtilDuplicateSid(*v4, &v19);
      if ( v12 >= 0 )
      {
        v5 = 0;
        v16 = *(void **)a2;
        *(_QWORD *)a2 = v19;
        if ( v16 )
          operator delete(v16, a2);
        v12 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            (unsigned int)v12);
        }
        v5 = v19;
      }
    }
    else
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      if ( v15 >= 0 )
        v15 = -2147467259;
      v12 = v15;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 13;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v4 = 0;
    v12 = -2147024882;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
        TokenInformationLength);
    }
  }
LABEL_39:
  if ( v5 )
    operator delete(v5, a2);
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400115cc  mov     [rsp-28h+arg_0], rbx
0x1400115d1  push    rbp
0x1400115d2  push    rsi
0x1400115d3  push    r12
0x1400115d5  push    r14
0x1400115d7  push    r15
0x1400115d9  mov     rbp, rsp
0x1400115dc  sub     rsp, 30h
0x1400115e0  mov     r14, rdx
0x1400115e3  mov     r12, rcx
0x1400115e6  xor     esi, esi
0x1400115e8  mov     [rbp+arg_18], rsi
0x1400115ec  mov     [rbp+TokenInformationLength], esi
0x1400115ef  xor     r15d, r15d
0x1400115f2  mov     [rbp+arg_10], r15
0x1400115f6  test    rdx, rdx
0x1400115f9  jz      loc_1400117D2
0x1400115ff  test    rcx, rcx
0x140011602  jz      loc_1400117D2
0x140011608  mov     rcx, [rdx]; void *
0x14001160b  mov     [rdx], r15
0x14001160e  test    rcx, rcx
0x140011611  jz      short loc_140011618
0x140011613  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011618  lea     rax, [rbp+TokenInformationLength]
0x14001161c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140011621  xor     r9d, r9d; TokenInformationLength
0x140011624  xor     r8d, r8d; TokenInformation
0x140011627  lea     edx, [r9+1]; TokenInformationClass
0x14001162b  mov     rcx, r12; TokenHandle
0x14001162e  call    cs:__imp_GetTokenInformation
0x140011634  test    eax, eax
0x140011636  jnz     loc_1400117C6
0x14001163c  call    cs:__imp_GetLastError
0x140011642  mov     ebx, eax
0x140011644  test    eax, eax
0x140011646  jle     short loc_140011651
0x140011648  movzx   ebx, ax
0x14001164b  or      ebx, 80070000h
0x140011651  test    ebx, ebx
0x140011653  js      short loc_14001165C
0x140011655  mov     ebx, 80004005h
0x14001165a  jmp     short loc_140011662
0x14001165c  cmp     bx, 7Ah ; 'z'
0x140011660  jz      short loc_1400116A0
0x140011662  lea     rax, WPP_GLOBAL_Control
0x140011669  mov     rcx, cs:WPP_GLOBAL_Control
0x140011670  cmp     rcx, rax
0x140011673  jz      loc_140011806
0x140011679  test    byte ptr [rcx+1Ch], 1
0x14001167d  jz      loc_140011806
0x140011683  mov     edx, 0Bh
0x140011688  mov     r9d, ebx
0x14001168b  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140011692  mov     rcx, [rcx+10h]
0x140011696  call    WPP_SF_d
0x14001169b  jmp     loc_140011806
0x1400116a0  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1400116a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400116aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400116af  mov     rsi, rax
0x1400116b2  test    rax, rax
0x1400116b5  jz      loc_14001178D
0x1400116bb  lea     rax, [rbp+TokenInformationLength]
0x1400116bf  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1400116c4  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400116c8  mov     r8, rsi; TokenInformation
0x1400116cb  mov     edx, 1; TokenInformationClass
0x1400116d0  mov     rcx, r12; TokenHandle
0x1400116d3  call    cs:__imp_GetTokenInformation
0x1400116d9  test    eax, eax
0x1400116db  jnz     short loc_140011726
0x1400116dd  call    cs:__imp_GetLastError
0x1400116e3  test    eax, eax
0x1400116e5  jle     short loc_1400116EF
0x1400116e7  movzx   eax, ax
0x1400116ea  or      eax, 80070000h
0x1400116ef  mov     ebx, 80004005h
0x1400116f4  test    eax, eax
0x1400116f6  cmovns  eax, ebx
0x1400116f9  mov     ebx, eax
0x1400116fb  lea     rax, WPP_GLOBAL_Control
0x140011702  mov     rcx, cs:WPP_GLOBAL_Control
0x140011709  cmp     rcx, rax
0x14001170c  jz      loc_140011806
0x140011712  test    byte ptr [rcx+1Ch], 1
0x140011716  jz      loc_140011806
0x14001171c  mov     edx, 0Dh
0x140011721  jmp     loc_140011688
0x140011726  lea     rdx, [rbp+arg_10]
0x14001172a  mov     rcx, [rsi]; pSourceSid
0x14001172d  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x140011732  mov     ebx, eax
0x140011734  test    eax, eax
0x140011736  jns     short loc_140011772
0x140011738  lea     rax, WPP_GLOBAL_Control
0x14001173f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011746  cmp     rcx, rax
0x140011749  jz      short loc_140011769
0x14001174b  test    byte ptr [rcx+1Ch], 1
0x14001174f  jz      short loc_140011769
0x140011751  mov     edx, 0Eh
0x140011756  mov     r9d, ebx
0x140011759  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140011760  mov     rcx, [rcx+10h]
0x140011764  call    WPP_SF_d
0x140011769  mov     r15, [rbp+arg_10]
0x14001176d  jmp     loc_140011806
0x140011772  mov     rax, [rbp+arg_10]
0x140011776  xor     r15d, r15d
0x140011779  mov     rcx, [r14]; void *
0x14001177c  mov     [r14], rax
0x14001177f  test    rcx, rcx
0x140011782  jz      short loc_140011789
0x140011784  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011789  xor     ebx, ebx
0x14001178b  jmp     short loc_140011806
0x14001178d  xor     esi, esi
0x14001178f  mov     ebx, 8007000Eh
0x140011794  lea     rax, WPP_GLOBAL_Control
0x14001179b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117a2  cmp     rcx, rax
0x1400117a5  jz      short loc_140011806
0x1400117a7  test    byte ptr [rcx+1Ch], 1
0x1400117ab  jz      short loc_140011806
0x1400117ad  lea     edx, [rsi+0Ch]
0x1400117b0  mov     r9d, [rbp+TokenInformationLength]
0x1400117b4  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400117bb  mov     rcx, [rcx+10h]
0x1400117bf  call    WPP_SF_d
0x1400117c4  jmp     short loc_140011806
0x1400117c6  mov     ebx, 8000FFFFh
0x1400117cb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400117d0  jmp     short loc_140011806
0x1400117d2  mov     ebx, 80070057h
0x1400117d7  lea     rax, WPP_GLOBAL_Control
0x1400117de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117e5  cmp     rcx, rax
0x1400117e8  jz      short loc_140011806
0x1400117ea  test    byte ptr [rcx+1Ch], 1
0x1400117ee  jz      short loc_140011806
0x1400117f0  mov     edx, 0Ah
0x1400117f5  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400117fc  mov     rcx, [rcx+10h]
0x140011800  call    WPP_SF_
0x140011805  nop
0x140011806  test    r15, r15
0x140011809  jz      short loc_140011814
0x14001180b  mov     rcx, r15; void *
0x14001180e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011813  nop
0x140011814  test    rsi, rsi
0x140011817  jz      short loc_140011821
0x140011819  mov     rcx, rsi; Block
0x14001181c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011821  mov     eax, ebx
0x140011823  mov     rbx, [rsp+30h+arg_0]
0x140011828  add     rsp, 30h
0x14001182c  pop     r15
0x14001182e  pop     r14
0x140011830  pop     r12
0x140011832  pop     rsi
0x140011833  pop     rbp
0x140011834  retn
```
