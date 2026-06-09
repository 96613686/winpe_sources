# CConnectJob::GetConnectionInfoFromAssociationResult(CPort const &,ulong,ulong,_WDI_ASSOCIATION_RESULT_CONTAINER &,bool *,wistd::unique_ptr<DOT11_CONNECTION_INFO,wistd::default_delete<DOT11_CONNECTION_INFO>> &)

- ea: `0x1400a8830`
- end: `0x1400a8a53`
- name: `?GetConnectionInfoFromAssociationResult@CConnectJob@@AEAAHAEBVCPort@@KKAEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEA_NAEAV?$unique_ptr@UDOT11_CONNECTION_INFO@@U?$default_delete@UDOT11_CONNECTION_INFO@@@wistd@@@wistd@@@Z`
- size: `547`
- prototype: `__int64 __usercall@<rax>(CConnectJob *this@<rcx>, struct _WDI_ASSOCIATION_RESULT_CONTAINER *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1400b0a94`

## callees

- `0x14000c778`
- `0x14000f400`
- `0x1400151e0`
- `0x1400768b0`
- `0x1400a7c7c`
- `0x1400a8830`
- `0x1400b2934`
- `0x1400b3ccc`
- `0x1400b648c`
- `0x1400b6764`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CConnectJob::GetConnectionInfoFromAssociationResult(
        CConnectJob *this,
        __int64 a2,
        int a3,
        int a4,
        struct _WDI_ASSOCIATION_RESULT_CONTAINER *a5,
        char *a6,
        struct DOT11_CONNECTION_INFO **a7)
{
  char *v7; // r13
  struct _WDI_ASSOCIATION_RESULT_CONTAINER *v9; // rsi
  struct DOT11_CONNECTION_INFO **v11; // rbx
  int ConnectedLinksInfo; // eax
  int v14; // edx
  unsigned int v15; // r14d
  unsigned int v17; // edi
  int v18; // edx
  unsigned int v19; // ecx
  struct DOT11_CONNECTION_INFO *v20; // r8
  unsigned int v21; // edi
  char v22; // al
  __int64 v23; // rdi
  int v24; // r8d
  unsigned int v25; // edx
  CConnectJob *v26; // rcx
  _QWORD v27[2]; // [rsp+50h] [rbp-61h] BYREF
  _QWORD v28[18]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v29; // [rsp+118h] [rbp+67h] BYREF

  v7 = a6;
  v9 = a5;
  v11 = a7;
  ConnectedLinksInfo = CConnectJob::GetConnectedLinksInfo(this, a2, (__int64)a5, a6, (_QWORD **)a7);
  v15 = ConnectedLinksInfo;
  if ( ConnectedLinksInfo )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        1,
        405,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        ConnectedLinksInfo);
    }
    return v15;
  }
  else
  {
    if ( *((_DWORD *)v9 + 9) )
      a4 |= 4u;
    if ( (a3 & 0x200) != 0 )
      v17 = a4 | 0x200;
    else
      v17 = a4 & 0xFFFFFDFF;
    v18 = *((_DWORD *)v9 + 16);
    v19 = v17 & 0xFFFFFBFF;
    v20 = *v11;
    v21 = v17 | 0x400;
    if ( !*v7 )
      v21 = v19;
    v22 = -*((_BYTE *)v9 + 20);
    v29 = v21;
    v23 = v22 != 0 ? 10 : 4;
    Dot11CopySSIDFromIEBlob(
      (unsigned __int8 *)(v23 + *((_QWORD *)v9 + 9)),
      v18 - v23,
      (struct _DOT11_SSID *)((char *)v20 + 12));
    if ( (unsigned int)Feature_Bugfix_56955488__private_IsEnabledDeviceUsageNoInline() )
    {
      *((_DWORD *)*v11 + 12) = 11276032;
      *((_DWORD *)*v11 + 13) = 0;
      v25 = *((_DWORD *)v9 + 16);
      if ( v25 > (unsigned int)v23 )
      {
        v27[0] = v23 + *((_QWORD *)v9 + 9);
        v27[1] = v25 - (unsigned int)v23;
        CConnectJob::SetConnectionFlagsFromAssociationRequest(v27[0], v27, v11, &v29);
      }
    }
    else
    {
      memset(v28, 0, 0x48u);
      if ( TryParseRsnIeInfo(*((_DWORD *)v9 + 16), *((unsigned __int8 **)v9 + 9), v23, (struct RSN_IE_INFO *)v28)
        && HIWORD(v28[0])
        && WORD2(v28[0]) )
      {
        *((_DWORD *)*v11 + 12) = *(_DWORD *)v28[4];
        v26 = (CConnectJob *)*(unsigned int *)v28[3];
        *((_DWORD *)*v11 + 13) = (_DWORD)v26;
        CConnectJob::UpdateConnectionFlagsIfFtAssociation(v26, v9, (const struct RSN_IE_INFO *)v28, &v29);
      }
      else
      {
        *((_DWORD *)*v11 + 12) = 11276032;
        *((_DWORD *)*v11 + 13) = 0;
      }
    }
    *((_DWORD *)*v11 + 1) = a3;
    *((_DWORD *)*v11 + 2) = v29;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_DDDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        v24,
        406,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        *((_DWORD *)*v11 + 12),
        *((_DWORD *)*v11 + 13),
        *((_DWORD *)*v11 + 1),
        *((_DWORD *)*v11 + 2));
    CConnectJob::SetPhyTypeIndicesInAssociationResult(this, v9, *v11);
    return 0;
  }
}

```

## disassembly

```asm
0x1400a8830  push    rbp
0x1400a8832  push    rbx
0x1400a8833  push    rsi
0x1400a8834  push    rdi
0x1400a8835  push    r12
0x1400a8837  push    r13
0x1400a8839  push    r14
0x1400a883b  push    r15
0x1400a883d  lea     rbp, [rsp-7]
0x1400a8842  sub     rsp, 0B8h
0x1400a8849  mov     r13, [rbp+3Fh+arg_28]
0x1400a884d  mov     edi, r9d
0x1400a8850  mov     rsi, [rbp+3Fh+arg_20]
0x1400a8854  mov     r15d, r8d
0x1400a8857  mov     rbx, [rbp+3Fh+arg_30]
0x1400a885b  mov     r9, r13
0x1400a885e  mov     r8, rsi
0x1400a8861  mov     [rsp+0F0h+var_D0], rbx
0x1400a8866  mov     r12, rcx
0x1400a8869  call    ?GetConnectedLinksInfo@CConnectJob@@AEAAHAEBVCPort@@AEBU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEA_NAEAV?$unique_ptr@UDOT11_CONNECTION_INFO@@U?$default_delete@UDOT11_CONNECTION_INFO@@@wistd@@@wistd@@@Z; CConnectJob::GetConnectedLinksInfo(CPort const &,_WDI_ASSOCIATION_RESULT_CONTAINER const &,bool *,wistd::unique_ptr<DOT11_CONNECTION_INFO,wistd::default_delete<DOT11_CONNECTION_INFO>> &)
0x1400a886e  mov     r14d, eax
0x1400a8871  test    eax, eax
0x1400a8873  jz      short loc_1400A88BB
0x1400a8875  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a887c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a8883  jz      short loc_1400A88B3
0x1400a8885  lea     rcx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a888c  mov     [rsp+0F0h+var_C8], eax
0x1400a8890  mov     [rsp+0F0h+var_D0], rcx
0x1400a8895  mov     r9d, 195h
0x1400a889b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a88a2  mov     r8d, 1
0x1400a88a8  mov     dl, 2
0x1400a88aa  mov     rcx, [rcx+40h]
0x1400a88ae  call    WPP_RECORDER_SF_d
0x1400a88b3  mov     eax, r14d
0x1400a88b6  jmp     loc_1400A8A3E
0x1400a88bb  xor     r14d, r14d
0x1400a88be  cmp     [rsi+24h], r14d
0x1400a88c2  jz      short loc_1400A88C7
0x1400a88c4  or      edi, 4
0x1400a88c7  mov     eax, 200h
0x1400a88cc  test    eax, r15d
0x1400a88cf  jz      short loc_1400A88D5
0x1400a88d1  or      edi, eax
0x1400a88d3  jmp     short loc_1400A88D9
0x1400a88d5  btr     edi, 9
0x1400a88d9  mov     al, [rsi+14h]
0x1400a88dc  mov     ecx, edi
0x1400a88de  mov     edx, [rsi+40h]
0x1400a88e1  btr     ecx, 0Ah
0x1400a88e5  mov     r8, [rbx]
0x1400a88e8  bts     edi, 0Ah
0x1400a88ec  cmp     [r13+0], r14b
0x1400a88f0  cmovz   edi, ecx
0x1400a88f3  neg     al
0x1400a88f5  mov     [rbp+3Fh+arg_18], edi
0x1400a88f8  sbb     ecx, ecx
0x1400a88fa  add     r8, 0Ch; struct _DOT11_SSID *
0x1400a88fe  and     ecx, 6
0x1400a8901  add     ecx, 4
0x1400a8904  mov     edi, ecx
0x1400a8906  sub     edx, ecx; unsigned int
0x1400a8908  mov     rcx, [rsi+48h]
0x1400a890c  add     rcx, rdi; unsigned __int8 *
0x1400a890f  call    ?Dot11CopySSIDFromIEBlob@@YAHPEAEKPEAU_DOT11_SSID@@@Z; Dot11CopySSIDFromIEBlob(uchar *,ulong,_DOT11_SSID *)
0x1400a8914  call    Feature_Bugfix_56955488__private_IsEnabledDeviceUsageNoInline
0x1400a8919  test    eax, eax
0x1400a891b  jz      short loc_1400A895E
0x1400a891d  mov     rax, [rbx]
0x1400a8920  mov     dword ptr [rax+30h], 0AC0F00h
0x1400a8927  mov     rax, [rbx]
0x1400a892a  mov     [rax+34h], r14d
0x1400a892e  mov     edx, [rsi+40h]
0x1400a8931  cmp     edx, edi
0x1400a8933  jbe     loc_1400A89CD
0x1400a8939  mov     rcx, [rsi+48h]
0x1400a893d  lea     r9, [rbp+3Fh+arg_18]
0x1400a8941  sub     edx, edi
0x1400a8943  add     rcx, rdi
0x1400a8946  mov     eax, edx
0x1400a8948  mov     r8, rbx
0x1400a894b  lea     rdx, [rbp+3Fh+var_A0]
0x1400a894f  mov     [rbp+3Fh+var_A0], rcx
0x1400a8953  mov     [rbp+3Fh+var_98], rax
0x1400a8957  call    ?SetConnectionFlagsFromAssociationRequest@CConnectJob@@AEAAXV?$span@$$CBE$0?0@utl@@AEAV?$unique_ptr@UDOT11_CONNECTION_INFO@@U?$default_delete@UDOT11_CONNECTION_INFO@@@wistd@@@wistd@@AEAK@Z; CConnectJob::SetConnectionFlagsFromAssociationRequest(utl::span<uchar const,-1>,wistd::unique_ptr<DOT11_CONNECTION_INFO,wistd::default_delete<DOT11_CONNECTION_INFO>> &,ulong &)
0x1400a895c  jmp     short loc_1400A89CD
0x1400a895e  xor     edx, edx; Val
0x1400a8960  lea     rcx, [rbp+3Fh+var_90]; void *
0x1400a8964  lea     r8d, [rdx+48h]; Size
0x1400a8968  call    memset
0x1400a896d  mov     rdx, [rsi+48h]; unsigned __int8 *
0x1400a8971  lea     r9, [rbp+3Fh+var_90]; struct RSN_IE_INFO *
0x1400a8975  mov     ecx, [rsi+40h]; unsigned int
0x1400a8978  mov     r8d, edi; unsigned int
0x1400a897b  call    ?TryParseRsnIeInfo@@YA_NKPEAEKPEAURSN_IE_INFO@@@Z; TryParseRsnIeInfo(ulong,uchar *,ulong,RSN_IE_INFO *)
0x1400a8980  test    al, al
0x1400a8982  jz      short loc_1400A89BC
0x1400a8984  cmp     [rbp+3Fh+var_8A], r14w
0x1400a8989  jbe     short loc_1400A89BC
0x1400a898b  cmp     [rbp+3Fh+var_8C], r14w
0x1400a8990  jbe     short loc_1400A89BC
0x1400a8992  mov     rax, [rbp+3Fh+var_70]
0x1400a8996  lea     r9, [rbp+3Fh+arg_18]; unsigned int *
0x1400a899a  mov     rdx, [rbx]
0x1400a899d  lea     r8, [rbp+3Fh+var_90]; struct RSN_IE_INFO *
0x1400a89a1  mov     ecx, [rax]
0x1400a89a3  mov     [rdx+30h], ecx
0x1400a89a6  mov     rax, [rbp+3Fh+var_78]
0x1400a89aa  mov     rdx, [rbx]
0x1400a89ad  mov     ecx, [rax]; this
0x1400a89af  mov     [rdx+34h], ecx
0x1400a89b2  mov     rdx, rsi; struct _WDI_ASSOCIATION_RESULT_CONTAINER *
0x1400a89b5  call    ?UpdateConnectionFlagsIfFtAssociation@CConnectJob@@AEAAXAEBU_WDI_ASSOCIATION_RESULT_CONTAINER@@AEBURSN_IE_INFO@@AEAK@Z; CConnectJob::UpdateConnectionFlagsIfFtAssociation(_WDI_ASSOCIATION_RESULT_CONTAINER const &,RSN_IE_INFO const &,ulong &)
0x1400a89ba  jmp     short loc_1400A89CD
0x1400a89bc  mov     rax, [rbx]
0x1400a89bf  mov     dword ptr [rax+30h], 0AC0F00h
0x1400a89c6  mov     rax, [rbx]
0x1400a89c9  mov     [rax+34h], r14d
0x1400a89cd  mov     rax, [rbx]
0x1400a89d0  mov     [rax+4], r15d
0x1400a89d4  mov     rcx, [rbx]
0x1400a89d7  mov     eax, [rbp+3Fh+arg_18]
0x1400a89da  mov     [rcx+8], eax
0x1400a89dd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400a89e4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400a89eb  jz      short loc_1400A8A2E
0x1400a89ed  mov     rcx, [rbx]
0x1400a89f0  mov     r9d, 196h
0x1400a89f6  mov     eax, [rcx+8]
0x1400a89f9  mov     [rsp+0F0h+var_B0], eax
0x1400a89fd  mov     eax, [rcx+4]
0x1400a8a00  mov     [rsp+0F0h+var_B8], eax
0x1400a8a04  mov     eax, [rcx+34h]
0x1400a8a07  mov     [rsp+0F0h+var_C0], eax
0x1400a8a0b  mov     eax, [rcx+30h]
0x1400a8a0e  lea     rcx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a8a15  mov     [rsp+0F0h+var_C8], eax
0x1400a8a19  mov     [rsp+0F0h+var_D0], rcx
0x1400a8a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8a25  mov     rcx, [rcx+40h]
0x1400a8a29  call    WPP_RECORDER_SF_DDDD
0x1400a8a2e  mov     r8, [rbx]; struct DOT11_CONNECTION_INFO *
0x1400a8a31  mov     rdx, rsi; struct _WDI_ASSOCIATION_RESULT_CONTAINER *
0x1400a8a34  mov     rcx, r12; this
0x1400a8a37  call    ?SetPhyTypeIndicesInAssociationResult@CConnectJob@@AEAAXPEAU_WDI_ASSOCIATION_RESULT_CONTAINER@@PEAUDOT11_CONNECTION_INFO@@@Z; CConnectJob::SetPhyTypeIndicesInAssociationResult(_WDI_ASSOCIATION_RESULT_CONTAINER *,DOT11_CONNECTION_INFO *)
0x1400a8a3c  xor     eax, eax
0x1400a8a3e  add     rsp, 0B8h
0x1400a8a45  pop     r15
0x1400a8a47  pop     r14
0x1400a8a49  pop     r13
0x1400a8a4b  pop     r12
0x1400a8a4d  pop     rdi
0x1400a8a4e  pop     rsi
0x1400a8a4f  pop     rbx
0x1400a8a50  pop     rbp
0x1400a8a51  retn
```
