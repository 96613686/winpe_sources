# BfeOptionalCreateNameResolutionInfo

- ea: `0x180033d90`
- end: `0x180034130`
- name: `BfeOptionalCreateNameResolutionInfo`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180008240`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180012a30`
- `0x180012b54`
- `0x180033d90`
- `0x180034138`
- `0x18003419c`
- `0x180034234`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18003410b`
- `ntdll!RtlEqualSid` at `0x18003410b`
- `ntdll!RtlInsertEntryHashTable` at `0x18003400e`
- `ntdll!RtlInsertEntryHashTable` at `0x18003400e`
- `ntdll!RtlLookupEntryHashTable` at `0x180033eac`
- `ntdll!RtlLookupEntryHashTable` at `0x180033eac`
- `ntdll!RtlGetNextEntryHashTable` at `0x180034125`
- `ntdll!RtlGetNextEntryHashTable` at `0x180034125`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033e5d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180033e5d`

## string_xrefs

- `0x18003408f`: `RtlCreateHashTable`
- `0x180033f36`: `BfeOptionalCreateNameResolutionInfo`

## pseudocode

```c
__int64 __fastcall BfeOptionalCreateNameResolutionInfo(__int64 *a1)
{
  _QWORD *v1; // rdx
  int v2; // r8d
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 inserted; // rbx
  __int64 v8; // rax
  unsigned __int8 *v9; // rbx
  __int64 v10; // rbp
  DWORD LengthSid; // r8d
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 i; // rax
  __int64 v17; // rdi
  int v18; // r8d
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  _QWORD *v22; // rdx
  __int64 v23; // rax
  int v24; // [rsp+30h] [rbp-58h] BYREF
  __int128 v25; // [rsp+38h] [rbp-50h] BYREF
  const char *v26; // [rsp+48h] [rbp-40h]
  __int64 v27; // [rsp+50h] [rbp-38h]
  int *v28; // [rsp+58h] [rbp-30h]
  __int64 v29; // [rsp+60h] [rbp-28h]

  v1 = (_QWORD *)*a1;
  v2 = 0;
  v4 = *(_QWORD *)(*a1 + 64) - *(_QWORD *)&FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data1;
  if ( !v4 )
    v4 = v1[9] - *(_QWORD *)FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data4;
  if ( !v4 )
    v2 = 1;
  v5 = v1[8] - *(_QWORD *)&FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data1;
  if ( !v5 )
    v5 = v1[9] - *(_QWORD *)FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data4;
  if ( !v5 || (inserted = 0, v2) )
  {
    v8 = v1[15];
    v25 = 0;
    v9 = *(unsigned __int8 **)(v8 + 32);
    v26 = 0;
    v10 = -1;
    LengthSid = GetLengthSid(v9);
    if ( !v9 )
      goto LABEL_14;
    v12 = 0;
    v13 = 0;
    if ( !LengthSid )
      goto LABEL_14;
    do
    {
      v14 = v9[v13];
      v13 = (unsigned int)(v13 + 1);
      v15 = 37 * v12 + v14;
      v12 = v15;
    }
    while ( (unsigned int)v13 < LengthSid );
    if ( !v15 )
LABEL_14:
      v12 = -1;
    for ( i = RtlLookupEntryHashTable(qword_1800F2E98, v12, &v25); ; i = RtlGetNextEntryHashTable(qword_1800F2E98, &v25) )
    {
      v17 = i;
      if ( !i )
      {
        inserted = BfeCreateAndInsertSidEntry(v9, (__int64)a1);
        if ( !inserted )
          goto LABEL_30;
LABEL_21:
        v19 = WPP_GLOBAL_Control;
        goto LABEL_22;
      }
      if ( RtlEqualSid(*(PSID *)(i + 24), v9) )
        break;
    }
    v21 = *(_QWORD *)(v17 + 32);
    v22 = (_QWORD *)(v17 + 32);
    if ( *(_QWORD *)(v21 + 8) != v17 + 32 )
      __fastfail(3u);
    a1[5] = v21;
    a1[6] = (__int64)v22;
    *(_QWORD *)(v21 + 8) = a1 + 5;
    *v22 = a1 + 5;
    ++*(_DWORD *)(v17 + 48);
LABEL_30:
    a1[10] = BfeComputeNameHashSignature(*a1);
    if ( a1[10] )
      v10 = a1[10];
    else
      a1[10] = -1;
    if ( (unsigned __int8)RtlInsertEntryHashTable(qword_1800F2EC8, a1 + 8, v10, 0)
      || (v23 = WfpReportSysErrorAsNtStatus(v20, "RtlCreateHashTable", 3221225495LL), (inserted = v23) == 0) )
    {
      *((_DWORD *)a1 + 22) = 1;
      WfpRestructureHashtable(qword_1800F2EC8);
      a1[14] = BfeComputeAddressHashSignature(*a1);
      inserted = WfpHashtableInsert(qword_1800F2EF8, a1 + 12);
      if ( !inserted )
      {
        *((_DWORD *)a1 + 30) = 1;
        WfpRestructureHashtable(qword_1800F2EF8);
        return inserted;
      }
      goto LABEL_21;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, 0, (__int64)"WfpHashtableInsert", v23);
      v19 = WPP_GLOBAL_Control;
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v24 = inserted;
      v28 = &v24;
      v26 = "WfpHashtableInsert";
      v27 = 19;
      v29 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v18,
        3,
        (__int64)&v25);
      goto LABEL_21;
    }
LABEL_22:
    if ( v19 != &WPP_GLOBAL_Control && *((_BYTE *)v19 + 25) >= 2u && (*((_BYTE *)v19 + 28) & 1) != 0 )
      WPP_SF_Ssd(v19[2], 26, v18, 0, (__int64)"BfeOptionalCreateNameResolutionInfo", inserted);
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v24 = inserted;
      v28 = &v24;
      v26 = "BfeOptionalCreateNameResolutionInfo";
      v27 = 36;
      v29 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v18,
        3,
        (__int64)&v25);
    }
  }
  return inserted;
}

```

## disassembly

```asm
0x180033d90  push    rsi
0x180033d92  sub     rsp, 80h
0x180033d99  mov     rax, cs:__security_cookie
0x180033da0  xor     rax, rsp
0x180033da3  mov     [rsp+88h+var_20], rax
0x180033da8  mov     rdx, [rcx]
0x180033dab  xor     r8d, r8d
0x180033dae  mov     rsi, rcx
0x180033db1  mov     rax, [rdx+40h]
0x180033db5  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data1
0x180033dbc  jnz     short loc_180033DC9
0x180033dbe  mov     rax, [rdx+48h]
0x180033dc2  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V4.Data4
0x180033dc9  test    rax, rax
0x180033dcc  jz      loc_1800340F9
0x180033dd2  mov     rax, [rdx+40h]
0x180033dd6  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data1
0x180033ddd  jnz     short loc_180033DEA
0x180033ddf  mov     rax, [rdx+48h]
0x180033de3  sub     rax, qword ptr cs:FWPM_LAYER_NAME_RESOLUTION_CACHE_V6.Data4
0x180033dea  mov     [rsp+88h+arg_8], rbx
0x180033df2  mov     [rsp+88h+arg_10], rbp
0x180033dfa  mov     [rsp+88h+var_10], rdi
0x180033dff  mov     [rsp+88h+var_18], r14
0x180033e04  test    rax, rax
0x180033e07  jz      short loc_180033E43
0x180033e09  xor     ebx, ebx
0x180033e0b  test    r8d, r8d
0x180033e0e  jnz     short loc_180033E43
0x180033e10  mov     r14, [rsp+88h+var_18]
0x180033e15  mov     rax, rbx
0x180033e18  mov     rbx, [rsp+88h+arg_8]
0x180033e20  mov     rdi, [rsp+88h+var_10]
0x180033e25  mov     rbp, [rsp+88h+arg_10]
0x180033e2d  mov     rcx, [rsp+88h+var_20]
0x180033e32  xor     rcx, rsp; StackCookie
0x180033e35  call    __security_check_cookie
0x180033e3a  add     rsp, 80h
0x180033e41  pop     rsi
0x180033e42  retn
0x180033e43  mov     rax, [rdx+78h]
0x180033e47  xorps   xmm0, xmm0
0x180033e4a  movups  [rsp+88h+var_50], xmm0
0x180033e4f  mov     rbx, [rax+20h]
0x180033e53  xor     eax, eax
0x180033e55  mov     rcx, rbx; pSid
0x180033e58  mov     [rsp+88h+var_40], rax
0x180033e5d  call    cs:__imp_GetLengthSid
0x180033e63  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180033e6a  mov     r8d, eax
0x180033e6d  test    rbx, rbx
0x180033e70  jz      short loc_180033E9A
0x180033e72  xor     r9d, r9d
0x180033e75  xor     eax, eax
0x180033e77  test    r8d, r8d
0x180033e7a  jz      short loc_180033E9A
0x180033e7c  nop     dword ptr [rax+00h]
0x180033e80  movzx   edx, byte ptr [rax+rbx]
0x180033e84  inc     eax
0x180033e86  imul    rcx, r9, 25h ; '%'
0x180033e8a  add     rdx, rcx
0x180033e8d  mov     r9, rdx
0x180033e90  cmp     eax, r8d
0x180033e93  jb      short loc_180033E80
0x180033e95  test    rdx, rdx
0x180033e98  jnz     short loc_180033E9D
0x180033e9a  mov     r9, rbp
0x180033e9d  lea     r8, [rsp+88h+var_50]
0x180033ea2  mov     rdx, r9
0x180033ea5  lea     rcx, qword_1800F2E98
0x180033eac  call    cs:__imp_RtlLookupEntryHashTable
0x180033eb2  lea     r14, WPP_GLOBAL_Control
0x180033eb9  mov     rdi, rax
0x180033ebc  test    rax, rax
0x180033ebf  jnz     loc_180034104
0x180033ec5  mov     rdx, rsi
0x180033ec8  mov     rcx, rbx
0x180033ecb  call    BfeCreateAndInsertSidEntry
0x180033ed0  mov     rbx, rax
0x180033ed3  test    rax, rax
0x180033ed6  jz      loc_180033FE4
0x180033edc  jmp     short loc_180033F2F
0x180033ede  test    cs:byte_1800F30F5, 1
0x180033ee5  jz      short loc_180033F36
0x180033ee7  lea     rax, [rsp+88h+var_58]
0x180033eec  mov     [rsp+88h+var_58], ebx
0x180033ef0  mov     [rsp+88h+var_30], rax
0x180033ef5  lea     rdx, WFP_USERMODE_ERROR
0x180033efc  lea     rax, [rsp+88h+var_50]
0x180033f01  mov     [rsp+88h+var_40], rdi
0x180033f06  mov     r9d, 3
0x180033f0c  mov     [rsp+88h+var_68], rax
0x180033f11  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180033f18  mov     [rsp+88h+var_38], 13h
0x180033f21  mov     [rsp+88h+var_28], 4
0x180033f2a  call    McGenEventWrite_EtwEventWriteTransfer
0x180033f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f36  lea     rdi, aBfeoptionalcre; "BfeOptionalCreateNameResolutionInfo"
0x180033f3d  cmp     rcx, r14
0x180033f40  jz      short loc_180033F68
0x180033f42  cmp     byte ptr [rcx+19h], 2
0x180033f46  jb      short loc_180033F68
0x180033f48  test    byte ptr [rcx+1Ch], 1
0x180033f4c  jz      short loc_180033F68
0x180033f4e  mov     rcx, [rcx+10h]
0x180033f52  mov     edx, 1Ah
0x180033f57  mov     [rsp+88h+var_60], ebx
0x180033f5b  xor     r9d, r9d
0x180033f5e  mov     [rsp+88h+var_68], rdi
0x180033f63  call    WPP_SF_Ssd
0x180033f68  cmp     cs:gWfpLogUserModeErrors, 0
0x180033f6f  jz      loc_180033E10
0x180033f75  test    cs:byte_1800F30F5, 1
0x180033f7c  jz      loc_180033E10
0x180033f82  lea     rax, [rsp+88h+var_58]
0x180033f87  mov     [rsp+88h+var_58], ebx
0x180033f8b  mov     [rsp+88h+var_30], rax
0x180033f90  lea     rdx, WFP_USERMODE_ERROR
0x180033f97  lea     rax, [rsp+88h+var_50]
0x180033f9c  mov     [rsp+88h+var_40], rdi
0x180033fa1  mov     r9d, 3
0x180033fa7  mov     [rsp+88h+var_68], rax
0x180033fac  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180033fb3  mov     [rsp+88h+var_38], 24h ; '$'
0x180033fbc  mov     [rsp+88h+var_28], 4
0x180033fc5  call    McGenEventWrite_EtwEventWriteTransfer
0x180033fca  jmp     loc_180033E10
0x180033fcf  lea     rax, [rsi+28h]
0x180033fd3  mov     [rax], r8
0x180033fd6  mov     [rax+8], rdx
0x180033fda  mov     [r8+8], rax
0x180033fde  mov     [rdx], rax
0x180033fe1  inc     dword ptr [rdi+30h]
0x180033fe4  mov     rcx, [rsi]
0x180033fe7  call    BfeComputeNameHashSignature
0x180033fec  lea     rdx, [rsi+40h]
0x180033ff0  mov     [rsi+50h], rax
0x180033ff4  mov     rax, [rdx+10h]
0x180033ff8  test    rax, rax
0x180033ffb  jnz     short loc_18003406B
0x180033ffd  mov     [rdx+10h], rbp
0x180034001  xor     r9d, r9d
0x180034004  lea     rcx, qword_1800F2EC8
0x18003400b  mov     r8, rbp
0x18003400e  call    cs:__imp_RtlInsertEntryHashTable
0x180034014  test    al, al
0x180034016  jz      short loc_180034089
0x180034018  lea     rcx, qword_1800F2EC8
0x18003401f  mov     dword ptr [rsi+58h], 1
0x180034026  call    WfpRestructureHashtable
0x18003402b  mov     rcx, [rsi]
0x18003402e  call    BfeComputeAddressHashSignature
0x180034033  lea     rdx, [rsi+60h]
0x180034037  mov     [rsi+70h], rax
0x18003403b  lea     rcx, qword_1800F2EF8
0x180034042  call    WfpHashtableInsert
0x180034047  mov     rbx, rax
0x18003404a  test    rax, rax
0x18003404d  jnz     loc_180033F2F
0x180034053  lea     rcx, qword_1800F2EF8
0x18003405a  mov     dword ptr [rsi+78h], 1
0x180034061  call    WfpRestructureHashtable
0x180034066  jmp     loc_180033E10
0x18003406b  mov     rbp, rax
0x18003406e  jmp     short loc_180034001
0x180034070  mov     r8, [rdi+20h]
0x180034074  lea     rdx, [rdi+20h]
0x180034078  cmp     [r8+8], rdx
0x18003407c  jz      loc_180033FCF
0x180034082  mov     ecx, 3
0x180034087  int     29h; Win8: RtlFailFast(ecx)
0x180034089  mov     r8d, 0C0000017h
0x18003408f  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x180034096  call    WfpReportSysErrorAsNtStatus
0x18003409b  mov     rbx, rax
0x18003409e  test    rax, rax
0x1800340a1  jz      loc_180034018
0x1800340a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340ae  lea     rdi, aWfphashtablein; "WfpHashtableInsert"
0x1800340b5  cmp     rcx, r14
0x1800340b8  jz      short loc_1800340E7
0x1800340ba  cmp     byte ptr [rcx+19h], 2
0x1800340be  jb      short loc_1800340E7
0x1800340c0  test    byte ptr [rcx+1Ch], 1
0x1800340c4  jz      short loc_1800340E7
0x1800340c6  mov     rcx, [rcx+10h]
0x1800340ca  mov     edx, 1Ah
0x1800340cf  mov     [rsp+88h+var_60], ebx
0x1800340d3  xor     r9d, r9d
0x1800340d6  mov     [rsp+88h+var_68], rdi
0x1800340db  call    WPP_SF_Ssd
0x1800340e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340e7  cmp     cs:gWfpLogUserModeErrors, 0
0x1800340ee  jz      loc_180033F36
0x1800340f4  jmp     loc_180033EDE
0x1800340f9  mov     r8d, 1
0x1800340ff  jmp     loc_180033DD2
0x180034104  mov     rcx, [rdi+18h]; Sid1
0x180034108  mov     rdx, rbx; Sid2
0x18003410b  call    cs:__imp_RtlEqualSid
0x180034111  test    al, al
0x180034113  jnz     loc_180034070
0x180034119  lea     rdx, [rsp+88h+var_50]
0x18003411e  lea     rcx, qword_1800F2E98
0x180034125  call    cs:__imp_RtlGetNextEntryHashTable
0x18003412b  jmp     loc_180033EB2
```
