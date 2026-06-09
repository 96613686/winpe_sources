# UbpmpQueueActionInstance

- ea: `0x1800038d0`
- end: `0x180003d97`
- name: `UbpmpQueueActionInstance`
- size: `1223`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008b30`
- `0x18000ab30`
- `0x18002e500`
- `0x180030914`

## callees

- `0x180003790`
- `0x1800038d0`
- `0x180004280`
- `0x18000fbf0`
- `0x1800150c0`
- `0x18001af64`
- `0x18002d16c`
- `0x180035184`
- `0x1800351ec`
- `0x180037d54`
- `0x1800386a8`
- `0x18003873c`
- `0x180040222`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003b50`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003b50`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003c20`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003c20`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003b37`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cd4`
- `RPCRT4!UuidEqual` at `0x180003999`
- `RPCRT4!UuidEqual` at `0x180003999`

## pseudocode

```c
DWORD __fastcall UbpmpQueueActionInstance(int a1, _QWORD *a2, int a3)
{
  void *v4; // rcx
  __int64 *v6; // rbx
  DWORD LengthSid; // ebp
  void *v8; // rcx
  DWORD result; // eax
  const unsigned __int16 ***v10; // rax
  const unsigned __int16 ***v11; // rbx
  DWORD v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  const unsigned __int16 ****v17; // rcx
  int v18; // r8d
  void *v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  char LastError; // al
  __int64 v31; // rdx
  const unsigned __int16 **v32; // rax
  RPC_STATUS Status; // [rsp+68h] [rbp+10h] BYREF

  v4 = (void *)a2[5];
  v6 = *(__int64 **)(*a2 + 256LL);
  if ( v4 )
    LengthSid = GetLengthSid(v4);
  else
    LengthSid = 0;
  Status = 0;
  while ( v6 != (__int64 *)(*a2 + 256LL) )
  {
    if ( !a1 )
    {
      result = UuidEqual((UUID *)((char *)v6 + 20), (UUID *)a2[6], &Status);
      if ( result )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          return WPP_SF_iS(
                   *((_QWORD *)WPP_GLOBAL_Control + 2),
                   *(_QWORD *)(*a2 + 24LL),
                   a3,
                   a2[8],
                   *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL));
        return result;
      }
    }
    if ( *((_DWORD *)v6 + 4) == a1 && *((_DWORD *)v6 + 12) == *((_DWORD *)a2 + 9) )
    {
      v8 = (void *)v6[7];
      if ( v8 )
      {
        v19 = (void *)a2[5];
        if ( !v19 || !EqualSid(v8, v19) )
          goto LABEL_7;
      }
      else if ( a2[5] )
      {
        goto LABEL_7;
      }
      result = a1 - 2;
      if ( (unsigned int)(a1 - 2) <= 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          return WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, a3, a1, *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL));
        return result;
      }
    }
LABEL_7:
    v6 = (__int64 *)*v6;
  }
  v10 = (const unsigned __int16 ***)UbpmAlloc(LengthSid + 144);
  v11 = v10;
  if ( v10 )
  {
    v12 = UbpmUtilsCloneStringArray(*((_BYTE *)a2 + 88), (const unsigned __int16 **)a2[12], v10 + 14);
    if ( v12 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v31 = 88;
        goto LABEL_55;
      }
    }
    else
    {
      v12 = UbpmUtilsCloneStringArray(*((_BYTE *)a2 + 108), (const unsigned __int16 **)a2[14], v11 + 16);
      if ( v12 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v31 = 89;
          goto LABEL_55;
        }
      }
      else
      {
        if ( a2[5] )
        {
          v11[7] = (const unsigned __int16 **)(v11 + 18);
          if ( !CopySid(LengthSid, v11 + 18, (PSID)a2[5]) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                90,
                (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL),
                LastError);
            goto LABEL_37;
          }
        }
        *((_DWORD *)v11 + 4) = a1;
        *((_DWORD *)v11 + 22) = *((_DWORD *)a2 + 26);
        if ( !a2[3] )
        {
LABEL_24:
          _InterlockedIncrement64((volatile signed __int64 *)(*a2 + 64LL));
          *(_OWORD *)((char *)v11 + 20) = *(_OWORD *)a2[6];
          v11[5] = (const unsigned __int16 **)a2[8];
          *((_DWORD *)v11 + 12) = *((_DWORD *)a2 + 9);
          v11[8] = (const unsigned __int16 **)a2[1];
          *((_DWORD *)v11 + 18) = *((_DWORD *)a2 + 18);
          v11[10] = (const unsigned __int16 **)a2[10];
          *((_BYTE *)v11 + 104) = *((_BYTE *)a2 + 88);
          *((_BYTE *)v11 + 124) = *((_BYTE *)a2 + 108);
          *((_DWORD *)v11 + 30) = *((_DWORD *)a2 + 14);
          v11[17] = (const unsigned __int16 **)*a2;
          v16 = *a2 + 256LL;
          v17 = *(const unsigned __int16 *****)(*a2 + 264LL);
          if ( *v17 != (const unsigned __int16 ***)v16 )
            __fastfail(3u);
          *v11 = (const unsigned __int16 **)v16;
          v11[1] = (const unsigned __int16 **)v17;
          *v17 = v11;
          *(_QWORD *)(v16 + 8) = v11;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              92,
              WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
              *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL));
          result = UbpmTriggerConsumerPublishStateChange(*a2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            return WPP_SF_iSddi(
                     *((_QWORD *)WPP_GLOBAL_Control + 2),
                     *(_QWORD *)(*a2 + 24LL),
                     v18,
                     a2[8],
                     *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL),
                     *((_DWORD *)a2 + 9),
                     *((_DWORD *)a2 + 18),
                     a2[10]);
          return result;
        }
        v32 = (const unsigned __int16 **)UbpmAlloc(*((unsigned int *)a2 + 8));
        v11[12] = v32;
        if ( v32 )
        {
          memcpy_0(v32, (const void *)a2[3], *((unsigned int *)a2 + 8));
          *((_DWORD *)v11 + 23) = *((_DWORD *)a2 + 8);
          goto LABEL_24;
        }
        v12 = GetLastError();
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v31 = 91;
LABEL_55:
          WPP_SF_d(v20[2], v31, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, v12);
        }
      }
    }
LABEL_37:
    UBPM_MIDL_user_free(v11[14], v13, v14, v15);
    UBPM_MIDL_user_free(v11[16], v21, v22, v23);
    UBPM_MIDL_user_free(v11[12], v24, v25, v26);
    return UBPM_MIDL_user_free(v11, v27, v28, v29);
  }
  result = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_iSd(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             87,
             (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
             a2[8],
             *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL),
             result);
  return result;
}

```

## disassembly

```asm
0x1800038d0  mov     [rsp+arg_10], rbx
0x1800038d5  push    rbp
0x1800038d6  push    rsi
0x1800038d7  push    rdi
0x1800038d8  sub     rsp, 40h
0x1800038dc  mov     rbx, [rdx]
0x1800038df  mov     esi, ecx
0x1800038e1  mov     rcx, [rdx+28h]; pSid
0x1800038e5  mov     rdi, rdx
0x1800038e8  mov     rbx, [rbx+100h]
0x1800038ef  test    rcx, rcx
0x1800038f2  jnz     loc_180003B50
0x1800038f8  xor     ebp, ebp
0x1800038fa  mov     [rsp+58h+Status], 0
0x180003902  mov     rax, [rdi]
0x180003905  add     rax, 100h
0x18000390b  cmp     rbx, rax
0x18000390e  jz      loc_1800039F0
0x180003914  test    esi, esi
0x180003916  jz      short loc_18000398C
0x180003918  cmp     [rbx+10h], esi
0x18000391b  jz      short loc_180003922
0x18000391d  mov     rbx, [rbx]
0x180003920  jmp     short loc_180003902
0x180003922  mov     eax, [rdi+24h]
0x180003925  cmp     [rbx+30h], eax
0x180003928  jnz     short loc_18000391D
0x18000392a  mov     rcx, [rbx+38h]; pSid1
0x18000392e  test    rcx, rcx
0x180003931  jnz     loc_180003B2A
0x180003937  cmp     [rdi+28h], rcx
0x18000393b  jnz     short loc_18000391D
0x18000393d  lea     eax, [rsi-2]
0x180003940  cmp     eax, 1
0x180003943  ja      short loc_18000391D
0x180003945  mov     rcx, cs:WPP_GLOBAL_Control
0x18000394c  lea     rbp, WPP_GLOBAL_Control
0x180003953  cmp     rcx, rbp
0x180003956  jz      loc_180003B1C
0x18000395c  test    byte ptr [rcx+1Ch], 1
0x180003960  jz      loc_180003B1C
0x180003966  mov     rax, [rdi]
0x180003969  mov     edx, 56h ; 'V'
0x18000396e  mov     rcx, [rcx+10h]
0x180003972  mov     r9d, esi
0x180003975  mov     rax, [rax+18h]
0x180003979  mov     rax, [rax+8]
0x18000397d  mov     [rsp+58h+var_38], rax
0x180003982  call    WPP_SF_dS
0x180003987  jmp     loc_180003B1C
0x18000398c  mov     rdx, [rdi+30h]; Uuid2
0x180003990  lea     rcx, [rbx+14h]; Uuid1
0x180003994  lea     r8, [rsp+58h+Status]; Status
0x180003999  call    cs:__imp_UuidEqual
0x1800039a0  nop     dword ptr [rax+rax+00h]
0x1800039a5  test    eax, eax
0x1800039a7  jz      loc_180003918
0x1800039ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039b4  lea     rbp, WPP_GLOBAL_Control
0x1800039bb  cmp     rcx, rbp
0x1800039be  jz      loc_180003B1C
0x1800039c4  test    byte ptr [rcx+1Ch], 1
0x1800039c8  jz      loc_180003B1C
0x1800039ce  mov     rax, [rdi]
0x1800039d1  mov     r9, [rdi+40h]
0x1800039d5  mov     rcx, [rcx+10h]
0x1800039d9  mov     rdx, [rax+18h]
0x1800039dd  mov     rax, [rdx+8]
0x1800039e1  mov     [rsp+58h+var_38], rax
0x1800039e6  call    WPP_SF_iS
0x1800039eb  jmp     loc_180003B1C
0x1800039f0  lea     ecx, [rbp+90h]; Size
0x1800039f6  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800039fb  mov     rbx, rax
0x1800039fe  test    rax, rax
0x180003a01  jz      loc_180003BA5
0x180003a07  mov     rdx, [rdi+60h]; unsigned __int16 **
0x180003a0b  lea     r8, [rax+70h]; unsigned __int16 ***
0x180003a0f  movzx   ecx, byte ptr [rdi+58h]; unsigned __int8
0x180003a13  mov     [rsp+58h+arg_0], r14
0x180003a18  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x180003a1d  test    eax, eax
0x180003a1f  jnz     loc_180003C8A
0x180003a25  mov     rdx, [rdi+70h]; unsigned __int16 **
0x180003a29  lea     r8, [rbx+80h]; unsigned __int16 ***
0x180003a30  movzx   ecx, byte ptr [rdi+6Ch]; unsigned __int8
0x180003a34  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x180003a39  test    eax, eax
0x180003a3b  jnz     loc_180003B63
0x180003a41  cmp     qword ptr [rdi+28h], 0
0x180003a46  jnz     loc_180003C0F
0x180003a4c  mov     [rbx+10h], esi
0x180003a4f  mov     eax, [rdi+68h]
0x180003a52  mov     [rbx+58h], eax
0x180003a55  cmp     qword ptr [rdi+18h], 0
0x180003a5a  jnz     loc_180003CC3
0x180003a60  mov     rax, [rdi]
0x180003a63  lock inc qword ptr [rax+40h]
0x180003a68  mov     rax, [rdi+30h]
0x180003a6c  movups  xmm0, xmmword ptr [rax]
0x180003a6f  movups  xmmword ptr [rbx+14h], xmm0
0x180003a73  mov     rax, [rdi+40h]
0x180003a77  mov     [rbx+28h], rax
0x180003a7b  mov     eax, [rdi+24h]
0x180003a7e  mov     [rbx+30h], eax
0x180003a81  mov     rax, [rdi+8]
0x180003a85  mov     [rbx+40h], rax
0x180003a89  mov     eax, [rdi+48h]
0x180003a8c  mov     [rbx+48h], eax
0x180003a8f  mov     rax, [rdi+50h]
0x180003a93  mov     [rbx+50h], rax
0x180003a97  movzx   eax, byte ptr [rdi+58h]
0x180003a9b  mov     [rbx+68h], al
0x180003a9e  movzx   eax, byte ptr [rdi+6Ch]
0x180003aa2  mov     [rbx+7Ch], al
0x180003aa5  mov     eax, [rdi+38h]
0x180003aa8  mov     [rbx+78h], eax
0x180003aab  mov     rax, [rdi]
0x180003aae  mov     [rbx+88h], rax
0x180003ab5  mov     rax, [rdi]
0x180003ab8  add     rax, 100h
0x180003abe  mov     rcx, [rax+8]
0x180003ac2  cmp     [rcx], rax
0x180003ac5  jnz     loc_180003C08
0x180003acb  mov     [rbx], rax
0x180003ace  mov     [rbx+8], rcx
0x180003ad2  mov     [rcx], rbx
0x180003ad5  mov     [rax+8], rbx
0x180003ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ae0  lea     rbp, WPP_GLOBAL_Control
0x180003ae7  cmp     rcx, rbp
0x180003aea  jz      short loc_180003AF6
0x180003aec  test    byte ptr [rcx+1Ch], 20h
0x180003af0  jnz     loc_180003D39
0x180003af6  mov     rcx, [rdi]
0x180003af9  call    UbpmTriggerConsumerPublishStateChange
0x180003afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b05  cmp     rcx, rbp
0x180003b08  jz      short loc_180003B17
0x180003b0a  test    dword ptr [rcx+1Ch], 200h
0x180003b11  jnz     loc_180003D5E
0x180003b17  mov     r14, [rsp+58h+arg_0]
0x180003b1c  mov     rbx, [rsp+58h+arg_10]
0x180003b21  add     rsp, 40h
0x180003b25  pop     rdi
0x180003b26  pop     rsi
0x180003b27  pop     rbp
0x180003b28  retn
0x180003b2a  mov     rdx, [rdi+28h]; pSid2
0x180003b2e  test    rdx, rdx
0x180003b31  jz      loc_18000391D
0x180003b37  call    cs:__imp_EqualSid
0x180003b3e  nop     dword ptr [rax+rax+00h]
0x180003b43  test    eax, eax
0x180003b45  jnz     loc_18000393D
0x180003b4b  jmp     loc_18000391D
0x180003b50  call    cs:__imp_GetLengthSid
0x180003b57  nop     dword ptr [rax+rax+00h]
0x180003b5c  mov     ebp, eax
0x180003b5e  jmp     loc_1800038FA
0x180003b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b6a  lea     rbp, WPP_GLOBAL_Control
0x180003b71  cmp     rcx, rbp
0x180003b74  jnz     loc_180003CB2
0x180003b7a  mov     rcx, [rbx+70h]
0x180003b7e  call    UBPM_MIDL_user_free
0x180003b83  mov     rcx, [rbx+80h]
0x180003b8a  call    UBPM_MIDL_user_free
0x180003b8f  mov     rcx, [rbx+60h]
0x180003b93  call    UBPM_MIDL_user_free
0x180003b98  mov     rcx, rbx
0x180003b9b  call    UBPM_MIDL_user_free
0x180003ba0  jmp     loc_180003B17
0x180003ba5  call    cs:__imp_GetLastError
0x180003bac  nop     dword ptr [rax+rax+00h]
0x180003bb1  mov     r8d, eax
0x180003bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bbb  lea     rbp, WPP_GLOBAL_Control
0x180003bc2  cmp     rcx, rbp
0x180003bc5  jz      loc_180003B1C
0x180003bcb  test    byte ptr [rcx+1Ch], 1
0x180003bcf  jz      loc_180003B1C
0x180003bd5  mov     rdx, [rdi]
0x180003bd8  mov     r9, [rdi+40h]
0x180003bdc  mov     rcx, [rcx+10h]
0x180003be0  mov     [rsp+58h+var_30], r8d
0x180003be5  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003bec  mov     rax, [rdx+18h]
0x180003bf0  mov     edx, 57h ; 'W'
0x180003bf5  mov     rax, [rax+8]
0x180003bf9  mov     [rsp+58h+var_38], rax
0x180003bfe  call    WPP_SF_iSd
0x180003c03  jmp     loc_180003B1C
0x180003c08  mov     ecx, 3
0x180003c0d  int     29h; Win8: RtlFailFast(ecx)
0x180003c0f  lea     rdx, [rbx+90h]; pDestinationSid
0x180003c16  mov     ecx, ebp; nDestinationSidLength
0x180003c18  mov     [rbx+38h], rdx
0x180003c1c  mov     r8, [rdi+28h]; pSourceSid
0x180003c20  call    cs:__imp_CopySid
0x180003c27  nop     dword ptr [rax+rax+00h]
0x180003c2c  test    eax, eax
0x180003c2e  jnz     loc_180003A4C
0x180003c34  call    cs:__imp_GetLastError
0x180003c3b  nop     dword ptr [rax+rax+00h]
0x180003c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c47  lea     rbp, WPP_GLOBAL_Control
0x180003c4e  cmp     rcx, rbp
0x180003c51  jz      loc_180003B7A
0x180003c57  test    byte ptr [rcx+1Ch], 1
0x180003c5b  jz      loc_180003B7A
0x180003c61  mov     rdx, [rdi]
0x180003c64  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003c6b  mov     rcx, [rcx+10h]
0x180003c6f  mov     dword ptr [rsp+58h+var_38], eax
0x180003c73  mov     r9, [rdx+18h]
0x180003c77  mov     edx, 5Ah ; 'Z'
0x180003c7c  mov     r9, [r9+8]
0x180003c80  call    WPP_SF_Sd
0x180003c85  jmp     loc_180003B7A
0x180003c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c91  lea     rbp, WPP_GLOBAL_Control
0x180003c98  cmp     rcx, rbp
0x180003c9b  jz      loc_180003B7A
0x180003ca1  test    byte ptr [rcx+1Ch], 1
0x180003ca5  jz      loc_180003B7A
0x180003cab  mov     edx, 58h ; 'X'
0x180003cb0  jmp     short loc_180003D06
0x180003cb2  test    byte ptr [rcx+1Ch], 1
0x180003cb6  jz      loc_180003B7A
0x180003cbc  mov     edx, 59h ; 'Y'
0x180003cc1  jmp     short loc_180003D06
0x180003cc3  mov     ecx, [rdi+20h]; Size
0x180003cc6  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180003ccb  mov     [rbx+60h], rax
0x180003ccf  test    rax, rax
0x180003cd2  jnz     short loc_180003D1E
0x180003cd4  call    cs:__imp_GetLastError
0x180003cdb  nop     dword ptr [rax+rax+00h]
0x180003ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ce7  lea     rbp, WPP_GLOBAL_Control
0x180003cee  cmp     rcx, rbp
0x180003cf1  jz      loc_180003B7A
0x180003cf7  test    byte ptr [rcx+1Ch], 1
0x180003cfb  jz      loc_180003B7A
0x180003d01  mov     edx, 5Bh ; '['
0x180003d06  mov     rcx, [rcx+10h]
0x180003d0a  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003d11  mov     r9d, eax
0x180003d14  call    WPP_SF_d
0x180003d19  jmp     loc_180003B7A
0x180003d1e  mov     r8d, [rdi+20h]; Size
0x180003d22  mov     rcx, rax; void *
0x180003d25  mov     rdx, [rdi+18h]; Src
0x180003d29  call    memcpy_0
0x180003d2e  mov     eax, [rdi+20h]
0x180003d31  mov     [rbx+5Ch], eax
0x180003d34  jmp     loc_180003A60
0x180003d39  mov     rax, [rdi]
0x180003d3c  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003d43  mov     rcx, [rcx+10h]
0x180003d47  mov     edx, 5Ch ; '\'
0x180003d4c  mov     r9, [rax+18h]
0x180003d50  mov     r9, [r9+8]
0x180003d54  call    WPP_SF_S
0x180003d59  jmp     loc_180003AF6
0x180003d5e  mov     rax, [rdi]
0x180003d61  mov     r9, [rdi+40h]
0x180003d65  mov     rcx, [rcx+10h]
0x180003d69  mov     rdx, [rax+18h]
0x180003d6d  mov     rax, [rdi+50h]
0x180003d71  mov     [rsp+58h+var_20], rax
0x180003d76  mov     eax, [rdi+48h]
0x180003d79  mov     [rsp+58h+var_28], eax
0x180003d7d  mov     eax, [rdi+24h]
0x180003d80  mov     [rsp+58h+var_30], eax
0x180003d84  mov     rax, [rdx+8]
0x180003d88  mov     [rsp+58h+var_38], rax
0x180003d8d  call    WPP_SF_iSddi
0x180003d92  jmp     loc_180003B17
```
