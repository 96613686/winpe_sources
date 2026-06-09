# SuccessfulLogon(void *,sockaddr *,uchar *,ulong,_KDC_TICKET_INFO *,_KDC_TICKET_INFO *,_UNICODE_STRING *,_KDC_AP_REQUEST_INFO *,_KDC_PKI_AUDIT_INFO *,ulong,_KERB_MESSAGE_BUFFER *,_UNICODE_STRING *,_USER_INTERNAL6_INFORMATION *,_PDC_RSO *)

- ea: `0x18001e41c`
- end: `0x18001e6f3`
- name: `?SuccessfulLogon@@YAJPEAXPEAUsockaddr@@PEAEKPEAU_KDC_TICKET_INFO@@3PEAU_UNICODE_STRING@@PEAU_KDC_AP_REQUEST_INFO@@PEAU_KDC_PKI_AUDIT_INFO@@KPEAU_KERB_MESSAGE_BUFFER@@4PEAU_USER_INTERNAL6_INFORMATION@@PEAU_PDC_RSO@@@Z`
- size: `727`
- prototype: `int(void *, struct sockaddr *, unsigned __int8 *, unsigned int, struct _KDC_TICKET_INFO *, struct _KDC_TICKET_INFO *, struct _UNICODE_STRING *, struct _KDC_AP_REQUEST_INFO *, struct _KDC_PKI_AUDIT_INFO *, unsigned int, struct _KERB_MESSAGE_BUFFER *, struct _UNICODE_STRING *, struct _USER_INTERNAL6_INFORMATION *, struct _PDC_RSO *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016148`
- `0x1800280ac`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x1800141b8`
- `0x18001c944`
- `0x18001e41c`
- `0x180037b28`
- `0x18005a090`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001e5bb`
- `ntdll!RtlInitUnicodeString` at `0x18001e5bb`
- `SAMSRV!SamIQueryServerRole` at `0x18001e587`
- `SAMSRV!SamIQueryServerRole` at `0x18001e587`
- `SAMSRV!SamIResetBadPwdCountOnPdc` at `0x18001e617`
- `SAMSRV!SamIResetBadPwdCountOnPdc` at `0x18001e617`
- `SAMSRV!SamIReplicateAccountData` at `0x18001e5cd`
- `SAMSRV!SamIReplicateAccountData` at `0x18001e5cd`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18001e539`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18001e539`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x18001e49b`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x18001e49b`

## pseudocode

```c
__int64 __fastcall SuccessfulLogon(
        void *a1,
        struct sockaddr_storage *a2,
        unsigned __int8 *a3,
        __int64 a4,
        struct _KDC_TICKET_INFO *a5,
        struct _KDC_TICKET_INFO *a6,
        struct _UNICODE_STRING *a7,
        struct _KDC_AP_REQUEST_INFO *a8,
        struct _KDC_PKI_AUDIT_INFO *a9,
        unsigned int a10,
        struct _KERB_MESSAGE_BUFFER *a11,
        struct _UNICODE_STRING *a12,
        struct _USER_INTERNAL6_INFORMATION *a13,
        struct _PDC_RSO *a14)
{
  int v17; // eax
  struct sockaddr v18; // xmm1
  struct sockaddr v19; // xmm0
  struct sockaddr v20; // xmm1
  struct sockaddr v21; // xmm0
  struct sockaddr v22; // xmm1
  struct sockaddr v23; // xmm0
  struct sockaddr v24; // xmm1
  CSecurityData **v25; // rdx
  int v26; // eax
  int v27; // eax
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  void *v31[2]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v32[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+A0h] [rbp-60h]
  struct sockaddr v34; // [rsp+B0h] [rbp-50h]
  struct sockaddr v35; // [rsp+C0h] [rbp-40h]
  struct sockaddr v36; // [rsp+D0h] [rbp-30h]
  struct sockaddr v37; // [rsp+E0h] [rbp-20h]
  struct sockaddr v38; // [rsp+F0h] [rbp-10h]
  struct sockaddr v39; // [rsp+100h] [rbp+0h]
  struct sockaddr v40; // [rsp+110h] [rbp+10h]

  v29 = 0;
  *(_OWORD *)v31 = 0;
  DestinationString = 0;
  memset_0(v32, 0, 0xC0u);
  if ( !(unsigned int)KdcIsLHFunctionalLevel()
    || !(unsigned int)LsaIIsLastInteractiveLogonInfoEnabled() && !KdcGlobalEmitLILI
    || (v17 = 84148224, (*((_DWORD *)a13 + 70) & 0x1C0) != 0) )
  {
    v17 = 83886080;
  }
  v32[0] = v17;
  if ( !a2 || a2->ss_family == 2 || a2->ss_family == 23 )
  {
    v32[14] = 1;
    if ( !a2 )
      a2 = &GlobalLocalhostAddress;
    v18 = *(struct sockaddr *)a2->__ss_pad2;
    v33 = *(_OWORD *)&a2->ss_family;
    v19 = *(struct sockaddr *)&a2->__ss_pad2[16];
    v34 = v18;
    v20 = *(struct sockaddr *)&a2->__ss_pad2[32];
    v35 = v19;
    v21 = *(struct sockaddr *)&a2->__ss_pad2[48];
    v36 = v20;
    v22 = *(struct sockaddr *)&a2->__ss_pad2[64];
    v37 = v21;
    v23 = *(struct sockaddr *)&a2->__ss_pad2[80];
    v38 = v22;
    v24 = *(struct sockaddr *)&a2->__ss_pad2[96];
    v39 = v23;
    v40 = v24;
  }
  SamIUpdateLogonStatistics(a1, v32);
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
      67306948,
      v32[0]);
  if ( (int)SamIQueryServerRole(GlobalAccountDomainHandle, &v29) >= 0 && v29 == 2 )
  {
    if ( *(_BYTE *)a14 )
    {
      v25 = (CSecurityData **)*((_QWORD *)a14 + 1);
      if ( v25 )
      {
        RtlInitUnicodeString(&DestinationString, (PCWSTR)*v25 + 2);
        v26 = SamIReplicateAccountData(a1, &DestinationString, 1);
        if ( v26 < 0 )
        {
          v25 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              47,
              WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
              (unsigned int)v26);
          }
        }
      }
    }
    if ( *((_WORD *)a13 + 152) )
    {
      v27 = SamIResetBadPwdCountOnPdc(a1);
      if ( v27 < 0 )
      {
        if ( v27 == -1073741736 )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
          }
          if ( !*(_BYTE *)a14 )
          {
            KdcForwardMessage(1, 0, 0, a11, v31);
            if ( v31[1] )
              MIDL_user_free(v31[1]);
          }
        }
        else
        {
          v25 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
              (unsigned int)v27);
          }
        }
      }
    }
    AsNegCacheDelete(a3, (__int64)v25, a12->Buffer, a12->Length);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e41c  mov     [rsp-8+arg_10], rbx
0x18001e421  push    rbp
0x18001e422  push    rsi
0x18001e423  push    rdi
0x18001e424  push    r12
0x18001e426  push    r13
0x18001e428  push    r14
0x18001e42a  push    r15
0x18001e42c  lea     rbp, [rsp-30h]
0x18001e431  sub     rsp, 130h
0x18001e438  mov     rax, cs:__security_cookie
0x18001e43f  xor     rax, rsp
0x18001e442  mov     [rbp+60h+var_40], rax
0x18001e446  mov     r15, [rbp+60h+arg_58]
0x18001e44d  xorps   xmm0, xmm0
0x18001e450  mov     rdi, [rbp+60h+arg_68]
0x18001e457  mov     r12, r8
0x18001e45a  mov     r13, [rbp+60h+arg_50]
0x18001e461  mov     rbx, rdx
0x18001e464  mov     rsi, rcx
0x18001e467  mov     [rsp+160h+var_130], 0
0x18001e46f  xor     edx, edx; Val
0x18001e471  lea     rcx, [rsp+160h+var_100]; void *
0x18001e476  mov     r8d, 0C0h; Size
0x18001e47c  movups  xmmword ptr [rsp+160h+var_118], xmm0
0x18001e481  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x18001e486  call    memset_0
0x18001e48b  call    ?KdcIsLHFunctionalLevel@@YAHXZ; KdcIsLHFunctionalLevel(void)
0x18001e490  mov     r14, [rbp+60h+arg_60]
0x18001e497  test    eax, eax
0x18001e499  jz      short loc_18001E4BF
0x18001e49b  call    cs:__imp_LsaIIsLastInteractiveLogonInfoEnabled
0x18001e4a1  test    eax, eax
0x18001e4a3  jnz     short loc_18001E4AD
0x18001e4a5  cmp     cs:?KdcGlobalEmitLILI@@3KA, eax; ulong KdcGlobalEmitLILI
0x18001e4ab  jz      short loc_18001E4BF
0x18001e4ad  test    dword ptr [r14+118h], 1C0h
0x18001e4b8  mov     eax, 5040000h
0x18001e4bd  jz      short loc_18001E4C4
0x18001e4bf  mov     eax, 5000000h
0x18001e4c4  mov     [rsp+160h+var_100], eax
0x18001e4c8  mov     eax, 2
0x18001e4cd  test    rbx, rbx
0x18001e4d0  jz      short loc_18001E4DD
0x18001e4d2  cmp     [rbx], ax
0x18001e4d5  jz      short loc_18001E4DD
0x18001e4d7  cmp     word ptr [rbx], 17h
0x18001e4db  jnz     short loc_18001E531
0x18001e4dd  test    rbx, rbx
0x18001e4e0  mov     [rbp+60h+var_C8], 1
0x18001e4e7  lea     rax, ?GlobalLocalhostAddress@@3Usockaddr_storage@@A; sockaddr_storage GlobalLocalhostAddress
0x18001e4ee  cmovz   rbx, rax
0x18001e4f2  movups  xmm0, xmmword ptr [rbx]
0x18001e4f5  movups  xmm1, xmmword ptr [rbx+10h]
0x18001e4f9  movaps  [rbp+60h+var_C0], xmm0
0x18001e4fd  movups  xmm0, xmmword ptr [rbx+20h]
0x18001e501  movaps  [rbp+60h+var_B0], xmm1
0x18001e505  movups  xmm1, xmmword ptr [rbx+30h]
0x18001e509  movaps  [rbp+60h+var_A0], xmm0
0x18001e50d  movups  xmm0, xmmword ptr [rbx+40h]
0x18001e511  movaps  [rbp+60h+var_90], xmm1
0x18001e515  movups  xmm1, xmmword ptr [rbx+50h]
0x18001e519  movaps  [rbp+60h+var_80], xmm0
0x18001e51d  movups  xmm0, xmmword ptr [rbx+60h]
0x18001e521  movaps  [rbp+60h+var_70], xmm1
0x18001e525  movups  xmm1, xmmword ptr [rbx+70h]
0x18001e529  movaps  [rbp+60h+var_60], xmm0
0x18001e52d  movaps  [rbp+60h+var_50], xmm1
0x18001e531  lea     rdx, [rsp+160h+var_100]
0x18001e536  mov     rcx, rsi
0x18001e539  call    cs:__imp_SamIUpdateLogonStatistics
0x18001e53f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e546  lea     rax, WPP_GLOBAL_Control
0x18001e54d  cmp     rcx, rax
0x18001e550  jz      short loc_18001E57B
0x18001e552  test    byte ptr [rcx+1Ch], 4
0x18001e556  jz      short loc_18001E57B
0x18001e558  mov     eax, [rsp+160h+var_100]
0x18001e55c  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001e563  mov     rcx, [rcx+10h]
0x18001e567  mov     edx, 2Eh ; '.'
0x18001e56c  mov     r9d, 40305C4h
0x18001e572  mov     dword ptr [rsp+160h+var_140], eax
0x18001e576  call    WPP_SF_Dd
0x18001e57b  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x18001e582  lea     rdx, [rsp+160h+var_130]
0x18001e587  call    cs:__imp_SamIQueryServerRole
0x18001e58d  xor     ebx, ebx
0x18001e58f  test    eax, eax
0x18001e591  js      loc_18001E6CA
0x18001e597  cmp     [rsp+160h+var_130], 2
0x18001e59c  jnz     loc_18001E6CA
0x18001e5a2  cmp     [rdi], bl
0x18001e5a4  jz      short loc_18001E606
0x18001e5a6  mov     rdx, [rdi+8]
0x18001e5aa  test    rdx, rdx
0x18001e5ad  jz      short loc_18001E606
0x18001e5af  mov     rdx, [rdx]
0x18001e5b2  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x18001e5b7  add     rdx, 4; SourceString
0x18001e5bb  call    cs:__imp_RtlInitUnicodeString
0x18001e5c1  lea     r8d, [rbx+1]
0x18001e5c5  mov     rcx, rsi
0x18001e5c8  lea     rdx, [rsp+160h+DestinationString]
0x18001e5cd  call    cs:__imp_SamIReplicateAccountData
0x18001e5d3  test    eax, eax
0x18001e5d5  jns     short loc_18001E606
0x18001e5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5de  lea     rdx, WPP_GLOBAL_Control
0x18001e5e5  cmp     rcx, rdx
0x18001e5e8  jz      short loc_18001E606
0x18001e5ea  test    byte ptr [rcx+1Ch], 1
0x18001e5ee  jz      short loc_18001E606
0x18001e5f0  mov     rcx, [rcx+10h]
0x18001e5f4  lea     edx, [rbx+2Fh]
0x18001e5f7  mov     r9d, eax
0x18001e5fa  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001e601  call    WPP_SF_d
0x18001e606  cmp     [r14+130h], bx
0x18001e60e  jz      loc_18001E6BA
0x18001e614  mov     rcx, rsi
0x18001e617  call    cs:__imp_SamIResetBadPwdCountOnPdc
0x18001e61d  test    eax, eax
0x18001e61f  jns     loc_18001E6BA
0x18001e625  cmp     eax, 0C0000058h
0x18001e62a  jnz     short loc_18001E689
0x18001e62c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e633  lea     rax, WPP_GLOBAL_Control
0x18001e63a  cmp     rcx, rax
0x18001e63d  jz      short loc_18001E65A
0x18001e63f  test    byte ptr [rcx+1Ch], 1
0x18001e643  jz      short loc_18001E65A
0x18001e645  mov     rcx, [rcx+10h]
0x18001e649  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001e650  mov     edx, 30h ; '0'
0x18001e655  call    WPP_SF_
0x18001e65a  cmp     [rdi], bl
0x18001e65c  jnz     short loc_18001E6BA
0x18001e65e  xor     edx, edx
0x18001e660  lea     rax, [rsp+160h+var_118]
0x18001e665  mov     r9, r13
0x18001e668  mov     [rsp+160h+var_140], rax
0x18001e66d  xor     r8d, r8d
0x18001e670  lea     ecx, [rdx+1]
0x18001e673  call    ?KdcForwardMessage@@YAJW4_KERB_KDC_TYPE@@EKPEAU_KERB_MESSAGE_BUFFER@@1@Z; KdcForwardMessage(_KERB_KDC_TYPE,uchar,ulong,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *)
0x18001e678  mov     rcx, [rsp+160h+var_118+8]; void *
0x18001e67d  test    rcx, rcx
0x18001e680  jz      short loc_18001E6BA
0x18001e682  call    MIDL_user_free
0x18001e687  jmp     short loc_18001E6BA
0x18001e689  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e690  lea     rdx, WPP_GLOBAL_Control
0x18001e697  cmp     rcx, rdx
0x18001e69a  jz      short loc_18001E6BA
0x18001e69c  test    byte ptr [rcx+1Ch], 1
0x18001e6a0  jz      short loc_18001E6BA
0x18001e6a2  mov     rcx, [rcx+10h]
0x18001e6a6  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001e6ad  mov     edx, 31h ; '1'
0x18001e6b2  mov     r9d, eax
0x18001e6b5  call    WPP_SF_d
0x18001e6ba  movzx   r9d, word ptr [r15]; unsigned int
0x18001e6be  mov     rcx, r12; void *
0x18001e6c1  mov     r8, [r15+8]; void *
0x18001e6c5  call    ?AsNegCacheDelete@@YAJPEAXK0K@Z; AsNegCacheDelete(void *,ulong,void *,ulong)
0x18001e6ca  xor     eax, eax
0x18001e6cc  mov     rcx, [rbp+60h+var_40]
0x18001e6d0  xor     rcx, rsp; StackCookie
0x18001e6d3  call    __security_check_cookie
0x18001e6d8  mov     rbx, [rsp+160h+arg_10]
0x18001e6e0  add     rsp, 130h
0x18001e6e7  pop     r15
0x18001e6e9  pop     r14
0x18001e6eb  pop     r13
0x18001e6ed  pop     r12
0x18001e6ef  pop     rdi
0x18001e6f0  pop     rsi
0x18001e6f1  pop     rbp
0x18001e6f2  retn
```
