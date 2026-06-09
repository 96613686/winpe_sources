# UbpmpRunConsumerAction(_UBPM_INPUT_ACTION_PARAMS *,_UBPM_CONSTRAINT_PRECHECK_INFO *,uchar *)

- ea: `0x18000b938`
- end: `0x18000bd53`
- name: `?UbpmpRunConsumerAction@@YAKPEAU_UBPM_INPUT_ACTION_PARAMS@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAE@Z`
- size: `1051`
- prototype: `unsigned int __fastcall(struct _UBPM_INPUT_ACTION_PARAMS *, struct _UBPM_CONSTRAINT_PRECHECK_INFO *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000aff0`

## callees

- `0x180007000`
- `0x18000a880`
- `0x18000b938`
- `0x18000c270`
- `0x18000e5b0`
- `0x18000fbf0`
- `0x18001af64`
- `0x18002399c`
- `0x180037508`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000bb7a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000bb7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000baa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000baa2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bac0`

## pseudocode

```c
__int64 __fastcall UbpmpRunConsumerAction(
        struct _UBPM_INPUT_ACTION_PARAMS *a1,
        struct _UBPM_CONSTRAINT_PRECHECK_INFO *a2,
        unsigned __int8 *a3)
{
  unsigned int v3; // edi
  struct _UBPM_INPUT_ACTION_PARAMS *v4; // r13
  __int64 v5; // rax
  const unsigned __int16 *ConsumerFriendlyName; // rbx
  int v7; // r8d
  void *v8; // rcx
  __int64 v9; // rdx
  unsigned int InteractiveUserSidAndToken; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // eax
  char *v14; // rcx
  unsigned int i; // edi
  __int64 v16; // rsi
  PSID v17; // rdi
  void *v19; // rcx
  const unsigned __int16 **v20; // rdx
  unsigned __int8 v21; // r8
  unsigned int v22; // r10d
  unsigned __int8 *v23; // r11
  unsigned int v24; // ebx
  unsigned __int8 v25; // si
  unsigned __int64 v26; // r14
  unsigned int v27; // r15d
  unsigned __int64 v28; // r12
  unsigned int v29; // [rsp+48h] [rbp-89h]
  unsigned __int16 **v30; // [rsp+70h] [rbp-61h]
  unsigned int v31; // [rsp+B8h] [rbp-19h]
  PSID pSid; // [rsp+C0h] [rbp-11h]
  char *v33; // [rsp+C8h] [rbp-9h] BYREF
  HANDLE hObject; // [rsp+D0h] [rbp-1h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp+7h] BYREF
  __int64 v39; // [rsp+150h] [rbp+7Fh] BYREF

  v3 = *((_DWORD *)a1 + 9);
  hObject = 0;
  v4 = a1;
  hMem = 0;
  pSid = 0;
  v33 = 0;
  v5 = *(_QWORD *)a1;
  v31 = v3;
  LODWORD(v39) = v3;
  ConsumerFriendlyName = UbpmpGetConsumerFriendlyName(*(PCNZWCH *)(*(_QWORD *)(v5 + 24) + 8LL));
  if ( (*((_BYTE *)v4 + 56) & 2) != 0 )
  {
    v7 = *((_DWORD *)v4 + 9);
    v8 = (void *)*((_QWORD *)v4 + 5);
    v33 = 0;
    LODWORD(v39) = 0;
    InteractiveUserSidAndToken = UbpmGetInteractiveUserSidAndToken(v8, 0, v7, &v33, (unsigned int *)&v39);
    if ( !InteractiveUserSidAndToken )
    {
      if ( (_DWORD)v39 )
      {
        hObject = (HANDLE)*((_QWORD *)v33 + 1);
        pSid = *(PSID *)v33;
        v13 = *((_DWORD *)v33 + 4);
        *((_QWORD *)v33 + 1) = 0;
        v31 = v13;
        *(_QWORD *)v33 = 0;
      }
      else
      {
        InteractiveUserSidAndToken = 1168;
      }
    }
    v14 = v33;
    if ( v33 )
    {
      for ( i = 0; i < (unsigned int)v39; ++i )
      {
        v16 = 32LL * i;
        if ( *(_QWORD *)&v14[v16 + 8] )
        {
          CloseHandle(*(HANDLE *)&v14[v16 + 8]);
          v14 = v33;
        }
        UBPM_MIDL_user_free(*(_QWORD *)&v14[v16], v9, v11, v12);
        v14 = v33;
      }
      UBPM_MIDL_user_free(v14, v9, v11, v12);
    }
    if ( InteractiveUserSidAndToken )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) + 8LL),
          *((_DWORD *)v4 + 9),
          InteractiveUserSidAndToken);
LABEL_16:
      v17 = pSid;
      goto LABEL_17;
    }
    goto LABEL_37;
  }
  if ( (*((_BYTE *)v4 + 56) & 4) == 0 )
  {
LABEL_37:
    v20 = (const unsigned __int16 **)*((_QWORD *)v4 + 14);
    v21 = *((_BYTE *)v4 + 108);
    v22 = *((_DWORD *)v4 + 26);
    v23 = (unsigned __int8 *)*((_QWORD *)v4 + 3);
    v24 = *((_DWORD *)v4 + 8);
    v25 = *((_BYTE *)v4 + 88);
    v26 = *((_QWORD *)v4 + 10);
    v27 = *((_DWORD *)v4 + 18);
    v28 = *((_QWORD *)v4 + 8);
    v30 = (unsigned __int16 **)*((_QWORD *)v4 + 12);
    v17 = pSid;
    v29 = *((_DWORD *)v4 + 14);
    v4 = a1;
    InteractiveUserSidAndToken = UbpmpLaunchOneTask(
                                   *(struct _UBPM_TRIGGER_CONSUMER_BLOCK **)a1,
                                   a2,
                                   *((struct _UBPM_ACTION_PARAMS **)a1 + 1),
                                   v31,
                                   pSid,
                                   (void **)((unsigned __int64)&hObject & -(__int64)(hObject != 0)),
                                   hMem,
                                   *((struct _GUID **)a1 + 6),
                                   v29,
                                   v28,
                                   v27,
                                   v26,
                                   v25,
                                   (const unsigned __int16 **)v30,
                                   v24,
                                   v23,
                                   v22,
                                   0,
                                   v21,
                                   v20,
                                   a3);
    if ( InteractiveUserSidAndToken
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 24LL) + 8LL),
        *((_DWORD *)a1 + 9),
        InteractiveUserSidAndToken);
    }
    goto LABEL_17;
  }
  v19 = (void *)*((_QWORD *)v4 + 5);
  if ( (*((_BYTE *)v4 + 56) & 8) != 0 )
  {
    if ( !EqualSid(v19, ::pSid) )
    {
      InteractiveUserSidAndToken = UbpmTokenGetTokenForTask(
                                     *(_QWORD *)(*((_QWORD *)v4 + 1) + 24LL),
                                     *((void **)v4 + 5),
                                     *((_DWORD *)v4 + 9),
                                     0,
                                     ConsumerFriendlyName,
                                     &hObject,
                                     &hMem,
                                     (__int64)&v39);
      if ( InteractiveUserSidAndToken )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) + 8LL),
            InteractiveUserSidAndToken);
        goto LABEL_16;
      }
      v31 = v39;
    }
    goto LABEL_36;
  }
  InteractiveUserSidAndToken = UbpmTokenGetInteractiveToken(
                                 (_DWORD)v19,
                                 -1,
                                 (unsigned int)&hObject,
                                 (unsigned int)&v39,
                                 (__int64)&v33);
  if ( !InteractiveUserSidAndToken )
  {
    UBPM_MIDL_user_free(v33, v9, v11, v12);
    v31 = v39;
LABEL_36:
    pSid = (PSID)*((_QWORD *)v4 + 5);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 24LL) + 8LL),
      InteractiveUserSidAndToken);
  v17 = v33;
LABEL_17:
  if ( hObject )
    CloseHandle(hObject);
  if ( v17 != *((PSID *)v4 + 5) )
    UBPM_MIDL_user_free(v17, v9, v11, v12);
  LocalFree(hMem);
  return InteractiveUserSidAndToken;
}

```

## disassembly

```asm
0x18000b938  mov     rax, rsp
0x18000b93b  mov     [rax+18h], r8
0x18000b93f  mov     [rax+10h], rdx
0x18000b943  mov     [rax+8], rcx
0x18000b947  push    rbp
0x18000b948  push    rbx
0x18000b949  push    rsi
0x18000b94a  push    rdi
0x18000b94b  push    r12
0x18000b94d  push    r13
0x18000b94f  push    r14
0x18000b951  push    r15
0x18000b953  lea     rbp, [rax-5Fh]
0x18000b957  sub     rsp, 0E8h
0x18000b95e  mov     edi, [rcx+24h]
0x18000b961  xor     r14d, r14d
0x18000b964  mov     eax, r14d
0x18000b967  mov     [rbp+57h+hObject], r14
0x18000b96b  mov     r13, rcx
0x18000b96e  mov     [rbp+57h+hMem], r14
0x18000b972  mov     [rbp+57h+var_68], rax
0x18000b976  mov     [rbp+57h+var_60], rax
0x18000b97a  mov     rax, [rcx]
0x18000b97d  mov     [rbp+57h+var_70], edi
0x18000b980  mov     dword ptr [rbp+57h+arg_18], edi
0x18000b983  mov     rcx, [rax+18h]
0x18000b987  mov     rcx, [rcx+8]; lpString1
0x18000b98b  call    ?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z; UbpmpGetConsumerFriendlyName(ushort const *)
0x18000b990  test    byte ptr [r13+38h], 2
0x18000b995  mov     rbx, rax
0x18000b998  jz      loc_18000BAE3
0x18000b99e  mov     r8d, [r13+24h]
0x18000b9a2  lea     rax, [rbp+57h+arg_18]
0x18000b9a6  mov     rcx, [r13+28h]; pSid2
0x18000b9aa  lea     r9, [rbp+57h+var_60]
0x18000b9ae  xor     edx, edx; SidToCheck
0x18000b9b0  mov     [rsp+120h+pSid], rax; __int64
0x18000b9b5  mov     [rbp+57h+var_60], r14
0x18000b9b9  mov     dword ptr [rbp+57h+arg_18], r14d
0x18000b9bd  call    UbpmGetInteractiveUserSidAndToken
0x18000b9c2  mov     ebx, eax
0x18000b9c4  test    eax, eax
0x18000b9c6  jnz     short loc_18000B9F9
0x18000b9c8  cmp     dword ptr [rbp+57h+arg_18], r14d
0x18000b9cc  jnz     short loc_18000B9D5
0x18000b9ce  mov     ebx, 490h
0x18000b9d3  jmp     short loc_18000B9F9
0x18000b9d5  mov     rcx, [rbp+57h+var_60]
0x18000b9d9  mov     rax, [rcx+8]
0x18000b9dd  mov     [rbp+57h+hObject], rax
0x18000b9e1  mov     rax, [rcx]
0x18000b9e4  mov     [rbp+57h+var_68], rax
0x18000b9e8  mov     eax, [rcx+10h]
0x18000b9eb  mov     [rcx+8], r14
0x18000b9ef  mov     [rbp+57h+var_70], eax
0x18000b9f2  mov     rax, [rbp+57h+var_60]
0x18000b9f6  mov     [rax], r14
0x18000b9f9  mov     rcx, [rbp+57h+var_60]
0x18000b9fd  test    rcx, rcx
0x18000ba00  jz      short loc_18000BA47
0x18000ba02  mov     edi, r14d
0x18000ba05  cmp     dword ptr [rbp+57h+arg_18], r14d
0x18000ba09  jbe     short loc_18000BA42
0x18000ba0b  mov     esi, edi
0x18000ba0d  shl     rsi, 5
0x18000ba11  mov     rax, [rsi+rcx+8]
0x18000ba16  test    rax, rax
0x18000ba19  jz      short loc_18000BA2E
0x18000ba1b  mov     rcx, rax; hObject
0x18000ba1e  call    cs:__imp_CloseHandle
0x18000ba25  nop     dword ptr [rax+rax+00h]
0x18000ba2a  mov     rcx, [rbp+57h+var_60]
0x18000ba2e  mov     rcx, [rsi+rcx]
0x18000ba32  call    UBPM_MIDL_user_free
0x18000ba37  mov     rcx, [rbp+57h+var_60]
0x18000ba3b  inc     edi
0x18000ba3d  cmp     edi, dword ptr [rbp+57h+arg_18]
0x18000ba40  jb      short loc_18000BA0B
0x18000ba42  call    UBPM_MIDL_user_free
0x18000ba47  test    ebx, ebx
0x18000ba49  jz      loc_18000BC25
0x18000ba4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba56  lea     rax, WPP_GLOBAL_Control
0x18000ba5d  cmp     rcx, rax
0x18000ba60  jz      short loc_18000BA95
0x18000ba62  test    byte ptr [rcx+1Ch], 1
0x18000ba66  jz      short loc_18000BA95
0x18000ba68  mov     rax, [r13+0]
0x18000ba6c  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000ba73  mov     rcx, [rcx+10h]
0x18000ba77  mov     edx, 4Dh ; 'M'
0x18000ba7c  mov     dword ptr [rsp+120h+var_F8], ebx
0x18000ba80  mov     r9, [rax+18h]
0x18000ba84  mov     eax, [r13+24h]
0x18000ba88  mov     dword ptr [rsp+120h+pSid], eax
0x18000ba8c  mov     r9, [r9+8]
0x18000ba90  call    WPP_SF_Sdd
0x18000ba95  mov     rdi, [rbp+57h+var_68]
0x18000ba99  mov     rcx, [rbp+57h+hObject]; hObject
0x18000ba9d  test    rcx, rcx
0x18000baa0  jz      short loc_18000BAAE
0x18000baa2  call    cs:__imp_CloseHandle
0x18000baa9  nop     dword ptr [rax+rax+00h]
0x18000baae  cmp     rdi, [r13+28h]
0x18000bab2  jz      short loc_18000BABC
0x18000bab4  mov     rcx, rdi
0x18000bab7  call    UBPM_MIDL_user_free
0x18000babc  mov     rcx, [rbp+57h+hMem]; hMem
0x18000bac0  call    cs:__imp_LocalFree
0x18000bac7  nop     dword ptr [rax+rax+00h]
0x18000bacc  mov     eax, ebx
0x18000bace  add     rsp, 0E8h
0x18000bad5  pop     r15
0x18000bad7  pop     r14
0x18000bad9  pop     r13
0x18000badb  pop     r12
0x18000badd  pop     rdi
0x18000bade  pop     rsi
0x18000badf  pop     rbx
0x18000bae0  pop     rbp
0x18000bae1  retn
0x18000bae3  test    byte ptr [r13+38h], 4
0x18000bae8  jz      loc_18000BC25
0x18000baee  test    byte ptr [r13+38h], 8
0x18000baf3  mov     rcx, [r13+28h]; pSid1
0x18000baf7  jnz     short loc_18000BB73
0x18000baf9  lea     rax, [rbp+57h+var_60]
0x18000bafd  or      edx, 0FFFFFFFFh
0x18000bb00  lea     r9, [rbp+57h+arg_18]
0x18000bb04  mov     [rsp+120h+pSid], rax
0x18000bb09  lea     r8, [rbp+57h+hObject]
0x18000bb0d  call    UbpmTokenGetInteractiveToken
0x18000bb12  mov     ebx, eax
0x18000bb14  test    eax, eax
0x18000bb16  jz      short loc_18000BB5F
0x18000bb18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb1f  lea     rax, WPP_GLOBAL_Control
0x18000bb26  cmp     rcx, rax
0x18000bb29  jz      short loc_18000BB56
0x18000bb2b  test    byte ptr [rcx+1Ch], 1
0x18000bb2f  jz      short loc_18000BB56
0x18000bb31  mov     rax, [r13+0]
0x18000bb35  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000bb3c  mov     rcx, [rcx+10h]
0x18000bb40  mov     edx, 4Eh ; 'N'
0x18000bb45  mov     dword ptr [rsp+120h+pSid], ebx
0x18000bb49  mov     r9, [rax+18h]
0x18000bb4d  mov     r9, [r9+8]
0x18000bb51  call    WPP_SF_Sd
0x18000bb56  mov     rdi, [rbp+57h+var_60]
0x18000bb5a  jmp     loc_18000BA99
0x18000bb5f  mov     rcx, [rbp+57h+var_60]
0x18000bb63  call    UBPM_MIDL_user_free
0x18000bb68  mov     ecx, dword ptr [rbp+57h+arg_18]
0x18000bb6b  mov     [rbp+57h+var_70], ecx
0x18000bb6e  jmp     loc_18000BC1D
0x18000bb73  mov     rdx, cs:pSid; pSid2
0x18000bb7a  call    cs:__imp_EqualSid
0x18000bb81  nop     dword ptr [rax+rax+00h]
0x18000bb86  test    eax, eax
0x18000bb88  jnz     loc_18000BC1D
0x18000bb8e  mov     rcx, [r13+8]
0x18000bb92  lea     rax, [rbp+57h+arg_18]
0x18000bb96  mov     r8d, [r13+24h]
0x18000bb9a  xor     r9d, r9d
0x18000bb9d  mov     rdx, [r13+28h]
0x18000bba1  mov     [rsp+120h+var_E8], rax
0x18000bba6  lea     rax, [rbp+57h+hMem]
0x18000bbaa  mov     rcx, [rcx+18h]
0x18000bbae  mov     [rsp+120h+var_F0], rax
0x18000bbb3  lea     rax, [rbp+57h+hObject]
0x18000bbb7  mov     [rsp+120h+var_F8], rax
0x18000bbbc  mov     [rsp+120h+pSid], rbx
0x18000bbc1  call    UbpmTokenGetTokenForTask
0x18000bbc6  mov     ebx, eax
0x18000bbc8  test    eax, eax
0x18000bbca  jz      short loc_18000BC17
0x18000bbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbd3  lea     rax, WPP_GLOBAL_Control
0x18000bbda  cmp     rcx, rax
0x18000bbdd  jz      loc_18000BA95
0x18000bbe3  test    byte ptr [rcx+1Ch], 1
0x18000bbe7  jz      loc_18000BA95
0x18000bbed  mov     rax, [r13+0]
0x18000bbf1  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000bbf8  mov     rcx, [rcx+10h]
0x18000bbfc  mov     edx, 4Fh ; 'O'
0x18000bc01  mov     dword ptr [rsp+120h+pSid], ebx
0x18000bc05  mov     r9, [rax+18h]
0x18000bc09  mov     r9, [r9+8]
0x18000bc0d  call    WPP_SF_Sd
0x18000bc12  jmp     loc_18000BA95
0x18000bc17  mov     eax, dword ptr [rbp+57h+arg_18]
0x18000bc1a  mov     [rbp+57h+var_70], eax
0x18000bc1d  mov     rax, [r13+28h]
0x18000bc21  mov     [rbp+57h+var_68], rax
0x18000bc25  mov     rdx, [r13+70h]
0x18000bc29  mov     r8b, [r13+6Ch]
0x18000bc2d  mov     rdi, [r13+60h]
0x18000bc31  mov     r10d, [r13+68h]
0x18000bc35  mov     r11, [r13+18h]
0x18000bc39  mov     ebx, [r13+20h]
0x18000bc3d  mov     sil, [r13+58h]
0x18000bc41  mov     r14, [r13+50h]
0x18000bc45  mov     r15d, [r13+48h]
0x18000bc49  mov     r12, [r13+40h]
0x18000bc4d  mov     r13d, [r13+38h]
0x18000bc51  mov     rax, [rbp+57h+hObject]
0x18000bc55  mov     r9, [rbp+57h+arg_0]
0x18000bc59  neg     rax
0x18000bc5c  lea     rax, [rbp+57h+hObject]
0x18000bc60  sbb     rcx, rcx
0x18000bc63  and     rcx, rax
0x18000bc66  mov     rax, [rbp+57h+arg_10]
0x18000bc6a  mov     r9, [r9+30h]
0x18000bc6e  mov     [rsp+0A0h], rax; unsigned __int8 *
0x18000bc76  mov     rax, [rbp+57h+hMem]
0x18000bc7a  mov     [rsp+120h+var_88], rdx; unsigned __int16 **
0x18000bc82  mov     rdx, [rbp+57h+arg_8]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18000bc86  mov     [rsp+120h+var_90], r8b; unsigned __int8
0x18000bc8e  mov     [rsp+120h+var_98], 0; void *
0x18000bc9a  mov     [rsp+120h+var_A0], r10d; unsigned int
0x18000bca2  mov     [rsp+120h+var_A8], r11; unsigned __int8 *
0x18000bca7  mov     [rsp+120h+var_B0], ebx; unsigned int
0x18000bcab  mov     [rsp+120h+var_B8], rdi; unsigned __int16 **
0x18000bcb0  mov     rdi, [rbp+57h+var_68]
0x18000bcb4  mov     [rsp+120h+var_C0], sil; char
0x18000bcb9  mov     [rsp+120h+var_C8], r14; unsigned __int64
0x18000bcbe  mov     [rsp+120h+var_D0], r15d; unsigned int
0x18000bcc3  mov     [rsp+120h+var_D8], r12; unsigned __int64
0x18000bcc8  mov     [rsp+120h+var_E0], r13d; unsigned int
0x18000bccd  mov     r13, [rbp+57h+arg_0]
0x18000bcd1  mov     [rsp+120h+var_E8], r9; struct _GUID *
0x18000bcd6  mov     r9d, [rbp+57h+var_70]; unsigned int
0x18000bcda  mov     [rsp+120h+var_F0], rax; void *
0x18000bcdf  mov     r8, [r13+8]; struct _UBPM_ACTION_PARAMS *
0x18000bce3  mov     [rsp+120h+var_F8], rcx; void **
0x18000bce8  mov     rcx, [r13+0]; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000bcec  mov     [rsp+120h+pSid], rdi; pSid
0x18000bcf1  call    ?UbpmpLaunchOneTask@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@PEAU_UBPM_ACTION_PARAMS@@KPEAXPEAPEAX3PEAU_GUID@@K_KK6EPEAPEBGKPEAEK3E78@Z; UbpmpLaunchOneTask(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,_UBPM_ACTION_PARAMS *,ulong,void *,void * *,void *,_GUID *,ulong,unsigned __int64,ulong,unsigned __int64,uchar,ushort const * *,ulong,uchar *,ulong,void *,uchar,ushort const * *,uchar *)
0x18000bcf6  mov     ebx, eax
0x18000bcf8  test    eax, eax
0x18000bcfa  jz      loc_18000BA99
0x18000bd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd07  lea     rax, WPP_GLOBAL_Control
0x18000bd0e  cmp     rcx, rax
0x18000bd11  jz      loc_18000BA99
0x18000bd17  test    byte ptr [rcx+1Ch], 1
0x18000bd1b  jz      loc_18000BA99
0x18000bd21  mov     rax, [r13+0]
0x18000bd25  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000bd2c  mov     rcx, [rcx+10h]
0x18000bd30  mov     edx, 50h ; 'P'
0x18000bd35  mov     dword ptr [rsp+120h+var_F8], ebx
0x18000bd39  mov     r9, [rax+18h]
0x18000bd3d  mov     eax, [r13+24h]
0x18000bd41  mov     dword ptr [rsp+120h+pSid], eax
0x18000bd45  mov     r9, [r9+8]
0x18000bd49  call    WPP_SF_Sdd
0x18000bd4e  jmp     loc_18000BA99
```
