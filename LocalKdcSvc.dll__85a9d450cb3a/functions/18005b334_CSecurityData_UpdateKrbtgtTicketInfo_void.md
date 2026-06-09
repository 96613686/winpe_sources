# CSecurityData::UpdateKrbtgtTicketInfo(void)

- ea: `0x18005b334`
- end: `0x18005b55d`
- name: `?UpdateKrbtgtTicketInfo@CSecurityData@@QEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(CSecurityData *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005a5fc`
- `0x18005b570`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18000ab40`
- `0x18000e9a4`
- `0x1800210a8`
- `0x18005b334`
- `0x18005c2a4`
- `0x180060b5c`
- `0x1800660d4`
- `0x18007e71c`
- `0x180080a90`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18005b520`
- `ntdll!RtlReleaseResource` at `0x18005b520`
- `ntdll!WinSqmSetDWORD` at `0x18005b4fb`
- `ntdll!WinSqmSetDWORD` at `0x18005b4fb`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005b3d9`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005b3d9`
- `SAMSRV!SamIQueryServerRole` at `0x18005b4d7`
- `SAMSRV!SamIQueryServerRole` at `0x18005b4d7`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18005b508`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18005b508`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSecurityData::UpdateKrbtgtTicketInfo(CSecurityData *this)
{
  KerberosCryptoPolicy *v1; // rbx
  unsigned int v2; // ebx
  unsigned int v3; // edi
  int TicketInfo; // eax
  int v6; // [rsp+70h] [rbp-90h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v7; // [rsp+78h] [rbp-88h] BYREF
  KerberosCryptoPolicy *v8[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v9[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v10[44]; // [rsp+A0h] [rbp-60h] BYREF
  int v11; // [rsp+CCh] [rbp-34h]
  int v12; // [rsp+E1h] [rbp-1Fh]
  __int16 v13; // [rsp+E5h] [rbp-1Bh]
  char v14; // [rsp+E7h] [rbp-19h]
  __int16 v15; // [rsp+F9h] [rbp-7h]
  char v16; // [rsp+FBh] [rbp-5h]
  int v17; // [rsp+104h] [rbp+4h]
  __int64 v18; // [rsp+128h] [rbp+28h] BYREF
  __int128 v19; // [rsp+130h] [rbp+30h]
  __int64 v20; // [rsp+140h] [rbp+40h] BYREF
  int v21; // [rsp+148h] [rbp+48h]

  v9[0] = 0;
  v9[1] = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  memset_0(v10, 0, 0x88u);
  v18 = 0;
  v19 = 0;
  v7 = 0;
  v20 = 0;
  v21 = 0;
  v6 = 0;
  KerberosCryptoPolicy::ForKrbtgtPolicy((__int64 **)v8);
  v1 = v8[0];
  if ( v8[0] )
  {
    v3 = 0;
    RtlAcquireResourceExclusive(&Resource, 1u);
    LOBYTE(word_1800B2F08) = 0;
    if ( KdcGlobalCDC )
      v3 = 4096;
    TicketInfo = KdcGetTicketInfo(
                   &String2,
                   v3,
                   0,
                   0,
                   0,
                   (struct _KDC_TICKET_INFO *)v9,
                   (struct KERB_EXT_ERROR *)&v20,
                   0,
                   0x40000u,
                   0x20u,
                   &v7,
                   0,
                   0);
    if ( TicketInfo )
    {
      v2 = KerbMapKerbError(TicketInfo);
    }
    else
    {
      FreeTicketInfo((struct _KDC_TICKET_INFO *)&stru_1800B2E58);
      _KDC_TICKET_INFO::operator=(&stru_1800B2E58, v9);
      LOBYTE(word_1800B2F08) = 1;
      qword_1800B2F10 = *((_QWORD *)v7 + 2);
      if ( KdcGlobalCDC )
      {
        KdcGlobalBranchID = *((_WORD *)v7 + 185);
        KdcGlobalBranchTgtRid = *((_DWORD *)v7 + 68);
      }
      if ( !KerberosCryptoPolicy::SetKdcTicketInfo(v1, (const struct _KDC_TICKET_INFO *)&stru_1800B2E58) )
      {
        v2 = -1073741823;
        goto LABEL_16;
      }
      if ( (int)SamIQueryServerRole(GlobalAccountDomainHandle, &v6) >= 0 && v6 == 3 )
        WinSqmSetDWORD(0, 10664, *((unsigned int *)v7 + 95));
      v2 = 0;
      SamIFree_UserInternal6Information(v7);
    }
    RtlReleaseResource(&Resource);
    goto LABEL_16;
  }
  v2 = -1073741670;
LABEL_16:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v8);
  std::vector<unsigned int>::_Tidy((__int64)&v18);
  return v2;
}

```

## disassembly

```asm
0x18005b334  mov     [rsp-8+arg_0], rbx
0x18005b339  mov     [rsp-8+arg_8], rdi
0x18005b33e  push    rbp
0x18005b33f  lea     rbp, [rsp-60h]
0x18005b344  sub     rsp, 160h
0x18005b34b  mov     rax, cs:__security_cookie
0x18005b352  xor     rax, rsp
0x18005b355  mov     [rbp+60h+var_10], rax
0x18005b359  xor     eax, eax
0x18005b35b  mov     [rbp+60h+var_D0], rax
0x18005b35f  mov     [rbp+60h+var_C8], rax
0x18005b363  mov     [rbp+60h+var_94], eax
0x18005b366  mov     [rbp+60h+var_7F], eax
0x18005b369  mov     [rbp+60h+var_7B], ax
0x18005b36d  mov     [rbp+60h+var_79], al
0x18005b370  mov     [rbp+60h+var_67], ax
0x18005b374  mov     [rbp+60h+var_65], al
0x18005b377  mov     [rbp+60h+var_5C], eax
0x18005b37a  xor     edx, edx; Val
0x18005b37c  mov     r8d, 88h; Size
0x18005b382  lea     rcx, [rbp+60h+var_C0]; void *
0x18005b386  call    memset_0
0x18005b38b  mov     [rbp+60h+var_38], 0
0x18005b393  xorps   xmm0, xmm0
0x18005b396  movdqa  [rbp+60h+var_30], xmm0
0x18005b39b  mov     [rsp+160h+var_E8], 0
0x18005b3a4  xor     eax, eax
0x18005b3a6  mov     [rbp+60h+var_20], rax
0x18005b3aa  mov     [rbp+60h+var_18], eax
0x18005b3ad  mov     [rsp+160h+var_F0], eax
0x18005b3b1  lea     rcx, [rbp+60h+var_E0]
0x18005b3b5  call    ?ForKrbtgtPolicy@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@XZ; KerberosCryptoPolicy::ForKrbtgtPolicy(void)
0x18005b3ba  nop
0x18005b3bb  mov     rbx, [rbp+60h+var_E0]
0x18005b3bf  test    rbx, rbx
0x18005b3c2  jnz     short loc_18005B3CE
0x18005b3c4  mov     ebx, 0C000009Ah
0x18005b3c9  jmp     loc_18005B527
0x18005b3ce  xor     edi, edi
0x18005b3d0  mov     dl, 1; Wait
0x18005b3d2  lea     rcx, Resource; Resource
0x18005b3d9  call    cs:__imp_RtlAcquireResourceExclusive
0x18005b3df  mov     byte ptr cs:word_1800B2F08, dil
0x18005b3e6  mov     eax, 1000h
0x18005b3eb  cmp     cs:?KdcGlobalCDC@@3HA, edi; int KdcGlobalCDC
0x18005b3f1  cmovnz  edi, eax
0x18005b3f4  mov     [rsp+160h+var_100], 0; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x18005b3fd  mov     [rsp+160h+var_108], 0; struct _SID_AND_ATTRIBUTES_LIST *
0x18005b406  lea     rax, [rsp+160h+var_E8]
0x18005b40b  mov     [rsp+160h+var_110], rax; struct _USER_INTERNAL6_INFORMATION **
0x18005b410  mov     [rsp+160h+var_118], 20h ; ' '; unsigned int
0x18005b418  mov     [rsp+160h+var_120], 40000h; unsigned int
0x18005b420  mov     [rsp+160h+var_128], 0; void **
0x18005b429  lea     rax, [rbp+60h+var_20]
0x18005b42d  mov     [rsp+160h+var_130], rax; struct KERB_EXT_ERROR *
0x18005b432  lea     rax, [rbp+60h+var_D0]
0x18005b436  mov     [rsp+160h+var_138], rax; struct _KDC_TICKET_INFO *
0x18005b43b  mov     [rsp+160h+var_140], 0; char **
0x18005b444  xor     r9d, r9d; struct _KERB_INTERNAL_NAME *
0x18005b447  xor     r8d, r8d; unsigned int
0x18005b44a  mov     edx, edi; unsigned int
0x18005b44c  lea     rcx, String2; struct _UNICODE_STRING *
0x18005b453  call    ?KdcGetTicketInfo@@YAJPEAU_UNICODE_STRING@@KKPEAU_KERB_INTERNAL_NAME@@PEAPEADPEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z; KdcGetTicketInfo(_UNICODE_STRING *,ulong,ulong,_KERB_INTERNAL_NAME *,char * *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,_SAM_MAPPED_ATTRIBUTE_SET *)
0x18005b458  test    eax, eax
0x18005b45a  jnz     loc_18005B510
0x18005b460  lea     rdi, stru_1800B2E58
0x18005b467  mov     rcx, rdi; struct _KDC_TICKET_INFO *
0x18005b46a  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18005b46f  lea     rdx, [rbp+60h+var_D0]
0x18005b473  mov     rcx, rdi
0x18005b476  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@AEBU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO const &)
0x18005b47b  mov     byte ptr cs:word_1800B2F08, 1
0x18005b482  mov     rcx, [rsp+160h+var_E8]
0x18005b487  mov     rax, [rcx+10h]
0x18005b48b  mov     cs:qword_1800B2F10, rax
0x18005b492  cmp     cs:?KdcGlobalCDC@@3HA, 0; int KdcGlobalCDC
0x18005b499  jz      short loc_18005B4B5
0x18005b49b  movzx   eax, word ptr [rcx+172h]
0x18005b4a2  mov     cs:?KdcGlobalBranchID@@3GA, ax; ushort KdcGlobalBranchID
0x18005b4a9  mov     eax, [rcx+110h]
0x18005b4af  mov     cs:?KdcGlobalBranchTgtRid@@3KA, eax; ulong KdcGlobalBranchTgtRid
0x18005b4b5  mov     rdx, rdi; struct _KDC_TICKET_INFO *
0x18005b4b8  mov     rcx, rbx; this
0x18005b4bb  call    ?SetKdcTicketInfo@KerberosCryptoPolicy@@QEAA_NPEBU_KDC_TICKET_INFO@@@Z; KerberosCryptoPolicy::SetKdcTicketInfo(_KDC_TICKET_INFO const *)
0x18005b4c0  test    al, al
0x18005b4c2  jnz     short loc_18005B4CB
0x18005b4c4  mov     ebx, 0C0000001h
0x18005b4c9  jmp     short loc_18005B527
0x18005b4cb  lea     rdx, [rsp+160h+var_F0]
0x18005b4d0  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x18005b4d7  call    cs:__imp_SamIQueryServerRole
0x18005b4dd  test    eax, eax
0x18005b4df  js      short loc_18005B501
0x18005b4e1  cmp     [rsp+160h+var_F0], 3
0x18005b4e6  jnz     short loc_18005B501
0x18005b4e8  mov     r8, [rsp+160h+var_E8]
0x18005b4ed  mov     r8d, [r8+17Ch]
0x18005b4f4  mov     edx, 29A8h
0x18005b4f9  xor     ecx, ecx
0x18005b4fb  call    cs:__imp_WinSqmSetDWORD
0x18005b501  xor     ebx, ebx
0x18005b503  mov     rcx, [rsp+160h+var_E8]
0x18005b508  call    cs:__imp_SamIFree_UserInternal6Information
0x18005b50e  jmp     short loc_18005B519
0x18005b510  mov     ecx, eax; int
0x18005b512  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18005b517  mov     ebx, eax
0x18005b519  lea     rcx, Resource; Resource
0x18005b520  call    cs:__imp_RtlReleaseResource
0x18005b526  nop
0x18005b527  lea     rcx, [rbp+60h+var_E0]
0x18005b52b  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18005b530  nop
0x18005b531  lea     rcx, [rbp+60h+var_38]
0x18005b535  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005b53a  mov     eax, ebx
0x18005b53c  mov     rcx, [rbp+60h+var_10]
0x18005b540  xor     rcx, rsp; StackCookie
0x18005b543  call    __security_check_cookie
0x18005b548  lea     r11, [rsp+160h+var_s0]
0x18005b550  mov     rbx, [r11+10h]
0x18005b554  mov     rdi, [r11+18h]
0x18005b558  mov     rsp, r11
0x18005b55b  pop     rbp
0x18005b55c  retn
```
