# KdcGetUserPac

- ea: `0x18004b680`
- end: `0x18004b88e`
- name: `KdcGetUserPac`
- size: `526`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, struct KERB_EXT_ERROR *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003908`
- `0x18000e9a4`
- `0x18002005c`
- `0x180045b50`
- `0x18004b498`
- `0x18004b680`
- `0x18005c2a4`
- `0x18005c560`
- `0x180060b5c`
- `0x18007e71c`

## import_xrefs

- `SAMSRV!SamIFree_UserInternal6Information` at `0x18004b79f`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18004b852`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18004b79f`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18004b852`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18004b7a9`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18004b85c`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18004b7a9`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18004b85c`

## pseudocode

```c
__int64 __fastcall KdcGetUserPac(
        struct _UNICODE_STRING *a1,
        struct _PACTYPE **a2,
        _QWORD *a3,
        _DWORD *a4,
        struct KERB_EXT_ERROR *a5)
{
  int v9; // ebx
  int *v10; // rdi
  int TicketInfo; // ebx
  CSecurityData *v12; // rcx
  int v13; // edx
  __int128 v15; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[60]; // [rsp+90h] [rbp-70h] BYREF
  int v17; // [rsp+CCh] [rbp-34h]
  int v18; // [rsp+E1h] [rbp-1Fh]
  __int16 v19; // [rsp+E5h] [rbp-1Bh]
  char v20; // [rsp+E7h] [rbp-19h]
  __int16 v21; // [rsp+F9h] [rbp-7h]
  char v22; // [rsp+FBh] [rbp-5h]
  int v23; // [rsp+104h] [rbp+4h]
  __int64 v24; // [rsp+128h] [rbp+28h] BYREF
  __int128 v25; // [rsp+130h] [rbp+30h]
  struct _USER_INTERNAL6_INFORMATION *v26; // [rsp+190h] [rbp+90h] BYREF

  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  memset_0(v16, 0, 0x98u);
  *a3 = 0;
  v25 = 0;
  v15 = 0;
  *a4 = 0;
  v24 = 0;
  v26 = 0;
  v9 = EnterApiCall(0);
  if ( v9 >= 0 )
  {
    v10 = (int *)a5;
    TicketInfo = KdcGetTicketInfo(
                   a1,
                   0,
                   0,
                   0,
                   0,
                   (struct _KDC_TICKET_INFO *)v16,
                   a5,
                   0,
                   0x213FCBCFu,
                   0,
                   &v26,
                   (struct _SID_AND_ATTRIBUTES_LIST *)&v15,
                   0);
    if ( TicketInfo )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_7;
      v13 = 29;
    }
    else
    {
      TicketInfo = GetPacAndSuppCred((__int64)v26, (unsigned int *)&v15, 0, 0, 0, 0, 0, 0, 0, 0, 0, 2, 1u, 0, a2, v10);
      if ( !TicketInfo )
      {
        SamIFree_UserInternal6Information(v26);
        SamIFreeSidAndAttributesList(&v15);
        FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
        LeaveApiCall();
        v9 = 0;
        goto LABEL_13;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_7;
      v13 = 30;
    }
    WPP_SF_Zd(
      *((_QWORD *)v12 + 2),
      v13,
      (unsigned int)WPP_3875113a630833a3e73becf979560e87_Traceguids,
      (_DWORD)a1,
      TicketInfo);
LABEL_7:
    v9 = KerbMapKerbError(TicketInfo);
    SamIFree_UserInternal6Information(v26);
    SamIFreeSidAndAttributesList(&v15);
    FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
    LeaveApiCall();
  }
LABEL_13:
  std::vector<unsigned int>::_Tidy((__int64)&v24);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004b680  push    rbp
0x18004b682  push    rbx
0x18004b683  push    rsi
0x18004b684  push    rdi
0x18004b685  push    r14
0x18004b687  push    r15
0x18004b689  lea     rbp, [rsp-48h]
0x18004b68e  sub     rsp, 148h
0x18004b695  xor     eax, eax
0x18004b697  mov     rbx, r8
0x18004b69a  mov     r14, rdx
0x18004b69d  mov     [rbp+70h+var_A4], eax
0x18004b6a0  mov     rsi, rcx
0x18004b6a3  mov     [rbp+70h+var_8F], eax
0x18004b6a6  xor     edx, edx; Val
0x18004b6a8  mov     [rbp+70h+var_8B], ax
0x18004b6ac  mov     r8d, 98h; Size
0x18004b6b2  mov     [rbp+70h+var_89], al
0x18004b6b5  lea     rcx, [rbp+70h+var_E0]; void *
0x18004b6b9  mov     [rbp+70h+var_77], ax
0x18004b6bd  mov     [rbp+70h+var_75], al
0x18004b6c0  mov     rdi, r9
0x18004b6c3  mov     [rbp+70h+var_6C], eax
0x18004b6c6  call    memset_0
0x18004b6cb  xor     r15d, r15d
0x18004b6ce  xorps   xmm0, xmm0
0x18004b6d1  xorps   xmm1, xmm1
0x18004b6d4  mov     [rbx], r15
0x18004b6d7  xor     ecx, ecx
0x18004b6d9  movdqa  [rbp+70h+var_40], xmm0
0x18004b6de  movups  [rbp+70h+var_F0], xmm1
0x18004b6e2  mov     [rdi], r15d
0x18004b6e5  mov     [rbp+70h+var_48], r15
0x18004b6e9  mov     [rbp+70h+arg_10], r15
0x18004b6f0  call    ?EnterApiCall@@YAJW4NeededKdcState@@@Z; EnterApiCall(NeededKdcState)
0x18004b6f5  mov     ebx, eax
0x18004b6f7  test    eax, eax
0x18004b6f9  js      loc_18004B873
0x18004b6ff  mov     rdi, [rbp+70h+arg_20]
0x18004b706  lea     rax, [rbp+70h+var_F0]
0x18004b70a  mov     [rsp+170h+var_110], r15; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x18004b70f  xor     r9d, r9d; struct _KERB_INTERNAL_NAME *
0x18004b712  mov     [rsp+170h+var_118], rax; struct _SID_AND_ATTRIBUTES_LIST *
0x18004b717  xor     r8d, r8d; unsigned int
0x18004b71a  lea     rax, [rbp+70h+arg_10]
0x18004b721  xor     edx, edx; unsigned int
0x18004b723  mov     [rsp+170h+var_120], rax; struct _USER_INTERNAL6_INFORMATION **
0x18004b728  mov     rcx, rsi; struct _UNICODE_STRING *
0x18004b72b  mov     [rsp+170h+var_128], r15d; unsigned int
0x18004b730  lea     rax, [rbp+70h+var_E0]
0x18004b734  mov     [rsp+170h+var_130], 213FCBCFh; unsigned int
0x18004b73c  mov     [rsp+170h+var_138], r15; void **
0x18004b741  mov     [rsp+170h+var_140], rdi; struct KERB_EXT_ERROR *
0x18004b746  mov     [rsp+170h+var_148], rax; struct _KDC_TICKET_INFO *
0x18004b74b  mov     [rsp+170h+var_150], r15; char **
0x18004b750  call    ?KdcGetTicketInfo@@YAJPEAU_UNICODE_STRING@@KKPEAU_KERB_INTERNAL_NAME@@PEAPEADPEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z; KdcGetTicketInfo(_UNICODE_STRING *,ulong,ulong,_KERB_INTERNAL_NAME *,char * *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,_SAM_MAPPED_ATTRIBUTE_SET *)
0x18004b755  mov     ebx, eax
0x18004b757  test    eax, eax
0x18004b759  jz      short loc_18004B7C2
0x18004b75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b762  lea     rdx, WPP_GLOBAL_Control
0x18004b769  cmp     rcx, rdx
0x18004b76c  jz      short loc_18004B78F
0x18004b76e  test    byte ptr [rcx+1Ch], 2
0x18004b772  jz      short loc_18004B78F
0x18004b774  lea     edx, [r15+1Dh]
0x18004b778  mov     rcx, [rcx+10h]
0x18004b77c  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004b783  mov     r9, rsi
0x18004b786  mov     dword ptr [rsp+170h+var_150], ebx
0x18004b78a  call    WPP_SF_Zd
0x18004b78f  mov     ecx, ebx; int
0x18004b791  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18004b796  mov     rcx, [rbp+70h+arg_10]
0x18004b79d  mov     ebx, eax
0x18004b79f  call    cs:__imp_SamIFree_UserInternal6Information
0x18004b7a5  lea     rcx, [rbp+70h+var_F0]
0x18004b7a9  call    cs:__imp_SamIFreeSidAndAttributesList
0x18004b7af  lea     rcx, [rbp+70h+var_E0]; struct _KDC_TICKET_INFO *
0x18004b7b3  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18004b7b8  call    ?LeaveApiCall@@YAXXZ; LeaveApiCall(void)
0x18004b7bd  jmp     loc_18004B873
0x18004b7c2  mov     rcx, [rbp+70h+arg_10]
0x18004b7c9  lea     rdx, [rbp+70h+var_F0]
0x18004b7cd  mov     [rsp+170h+var_F8], rdi
0x18004b7d2  xor     r9d, r9d
0x18004b7d5  mov     [rsp+170h+var_100], r14
0x18004b7da  xor     r8d, r8d
0x18004b7dd  mov     [rsp+170h+var_108], r15
0x18004b7e2  mov     dword ptr [rsp+170h+var_110], 1
0x18004b7ea  mov     dword ptr [rsp+170h+var_118], 2
0x18004b7f2  mov     [rsp+170h+var_120], r15
0x18004b7f7  mov     qword ptr [rsp+170h+var_128], r15
0x18004b7fc  mov     qword ptr [rsp+170h+var_130], r15
0x18004b801  mov     [rsp+170h+var_138], r15
0x18004b806  mov     [rsp+170h+var_140], r15
0x18004b80b  mov     [rsp+170h+var_148], r15
0x18004b810  mov     [rsp+170h+var_150], r15
0x18004b815  call    ?GetPacAndSuppCred@@YAJPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@KKPEAU_KERB_ENCRYPTION_KEY@@PEAUPKERB_AUTHORIZATION_DATA_s@@PEAT_LARGE_INTEGER@@PEAU_UNICODE_STRING@@44PEAU_SAM_CLAIMS_BLOB@@KW4PacRequestType@@PEAXPEAPEAU_PACTYPE@@PEAUKERB_EXT_ERROR@@@Z; GetPacAndSuppCred(_USER_INTERNAL6_INFORMATION *,_SID_AND_ATTRIBUTES_LIST *,ulong,ulong,_KERB_ENCRYPTION_KEY *,PKERB_AUTHORIZATION_DATA_s *,_LARGE_INTEGER *,_UNICODE_STRING *,_LARGE_INTEGER *,_LARGE_INTEGER *,_SAM_CLAIMS_BLOB *,ulong,PacRequestType,void *,_PACTYPE * *,KERB_EXT_ERROR *)
0x18004b81a  mov     ebx, eax
0x18004b81c  test    eax, eax
0x18004b81e  jz      short loc_18004B84B
0x18004b820  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b827  lea     rdx, WPP_GLOBAL_Control
0x18004b82e  cmp     rcx, rdx
0x18004b831  jz      loc_18004B78F
0x18004b837  test    byte ptr [rcx+1Ch], 1
0x18004b83b  jz      loc_18004B78F
0x18004b841  mov     edx, 1Eh
0x18004b846  jmp     loc_18004B778
0x18004b84b  mov     rcx, [rbp+70h+arg_10]
0x18004b852  call    cs:__imp_SamIFree_UserInternal6Information
0x18004b858  lea     rcx, [rbp+70h+var_F0]
0x18004b85c  call    cs:__imp_SamIFreeSidAndAttributesList
0x18004b862  lea     rcx, [rbp+70h+var_E0]; struct _KDC_TICKET_INFO *
0x18004b866  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18004b86b  call    ?LeaveApiCall@@YAXXZ; LeaveApiCall(void)
0x18004b870  mov     ebx, r15d
0x18004b873  lea     rcx, [rbp+70h+var_48]
0x18004b877  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18004b87c  mov     eax, ebx
0x18004b87e  add     rsp, 148h
0x18004b885  pop     r15
0x18004b887  pop     r14
0x18004b889  pop     rdi
0x18004b88a  pop     rsi
0x18004b88b  pop     rbx
0x18004b88c  pop     rbp
0x18004b88d  retn
```
