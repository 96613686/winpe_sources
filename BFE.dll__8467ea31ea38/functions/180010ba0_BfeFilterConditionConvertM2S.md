# BfeFilterConditionConvertM2S

- ea: `0x180010ba0`
- end: `0x18001127e`
- name: `BfeFilterConditionConvertM2S`
- size: `1758`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013480`
- `0x180024254`

## callees

- `0x18000f1a8`
- `0x18000fad0`
- `0x180010ad0`
- `0x180010ba0`
- `0x18001236c`
- `0x180012950`
- `0x180012b54`
- `0x180018b74`
- `0x1800219c4`
- `0x18004e230`
- `0x1800540ec`
- `0x1800542bc`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180010f9d`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180010f9d`
- `ntdll!RtlNtStatusToDosError` at `0x1800110c2`
- `ntdll!RtlNtStatusToDosError` at `0x1800110c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010ffc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010ffc`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001114b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011222`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001114b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011222`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010d06`

## string_xrefs

- `0x1800110ae`: `RtlGetOwnerSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall BfeFilterConditionConvertM2S(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r11
  PSECURITY_DESCRIPTOR v5; // r13
  int v8; // r12d
  unsigned __int16 i; // r10
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rcx
  BOOL v13; // eax
  int v14; // r9d
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rdi
  __int64 v18; // rdx
  void *v19; // rcx
  __int64 v20; // rsi
  int v21; // r8d
  __int64 v23; // rax
  __int64 v24; // rax
  void *v25; // rbx
  NTSTATUS OwnerSecurityDescriptor; // eax
  __int64 v27; // rdx
  int v28; // r8d
  NTSTATUS v29; // esi
  const void *v30; // rax
  __int64 v31; // rcx
  PSECURITY_DESCRIPTOR v32; // rax
  bool v33; // zf
  ULONG v34; // eax
  signed int v35; // ebx
  __int64 v36; // rax
  ULONG v37; // [rsp+30h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR v38; // [rsp+38h] [rbp-31h] BYREF
  PSID Owner; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 OwnerDefaulted[8]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v41[16]; // [rsp+50h] [rbp-19h] BYREF
  const char *v42; // [rsp+60h] [rbp-9h]
  __int64 v43; // [rsp+68h] [rbp-1h]
  ULONG *v44; // [rsp+70h] [rbp+7h]
  __int64 v45; // [rsp+78h] [rbp+Fh]

  v4 = *a1;
  v5 = 0;
  v8 = a3;
  v38 = 0;
  for ( i = 0; i < *(_WORD *)(v4 + 36); ++i )
  {
    v10 = *(_QWORD *)(v4 + 40) + 16LL * i;
    a1 = *(__int64 **)v10;
    v11 = **(_QWORD **)v10 - *(_QWORD *)a2;
    if ( !v11 )
      v11 = a1[1] - *(_QWORD *)(a2 + 8);
    if ( !v11 )
    {
      if ( a4 )
        *(_WORD *)a4 = i;
      goto LABEL_9;
    }
  }
  v10 = 0;
  v23 = WfpReportSysErrorAsWinError(a1, "BfeLayerLookupConditionInfo", 2150760450LL);
  v20 = v23;
  if ( v23 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, a3, 0, (__int64)"BfeLayerLookupConditionInfo", v23);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v37 = v20;
      v44 = &v37;
      v42 = "BfeLayerLookupConditionInfo";
      v43 = 28;
      v45 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        a3,
        3,
        (__int64)v41);
    }
    goto LABEL_23;
  }
LABEL_9:
  v12 = *(unsigned int *)(a2 + 16);
  v13 = (_DWORD)v12 == 8 || (_DWORD)v12 == 6 || (_DWORD)v12 == 7;
  v14 = *(_DWORD *)(v10 + 8);
  if ( v14 != 2 )
  {
    if ( !v13 )
      goto LABEL_13;
LABEL_61:
    v20 = WfpReportSysErrorAsWinError(v12, "BfeFwpmFilterConditionAssocValidate", 2150760486LL);
    if ( v20 )
    {
LABEL_40:
      WfpReportError(v20, "BfeFwpmFilterConditionAssocValidate");
      goto LABEL_22;
    }
    goto LABEL_20;
  }
  if ( (_DWORD)v12 && (v8 || !v13) )
    goto LABEL_61;
LABEL_13:
  v15 = *(_DWORD *)(v10 + 12);
  v16 = *(_DWORD *)(a2 + 24);
  if ( v16 == 257 )
  {
    if ( v15 != 11 )
      goto LABEL_34;
    goto LABEL_78;
  }
  if ( v16 > 15 )
  {
    LODWORD(a3) = v16 - 16;
    if ( v16 == 16 )
      goto LABEL_34;
    LODWORD(a3) = v16 - 256;
    if ( v16 != 256 )
    {
      if ( v16 != 258 )
      {
LABEL_19:
        if ( v16 == v15 )
          goto LABEL_20;
        goto LABEL_34;
      }
      if ( **(_DWORD **)(a2 + 32) == v15 )
        goto LABEL_20;
      goto LABEL_34;
    }
    if ( v15 != 3 )
      goto LABEL_34;
LABEL_78:
    v33 = v14 == 1;
    goto LABEL_79;
  }
  if ( v16 == 15 )
    goto LABEL_34;
  if ( !v16 )
    goto LABEL_20;
  LODWORD(a3) = v16 - 13;
  if ( v16 == 13 )
  {
    if ( v15 != 13 && (!v8 || (unsigned int)(v15 - 15) > 1) )
      goto LABEL_34;
    goto LABEL_20;
  }
  if ( v16 != 14 )
    goto LABEL_19;
  if ( v15 != 13 && (unsigned int)(v15 - 15) > 1 )
  {
LABEL_34:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, a3, 0, (__int64)"BfeFwpmFilterConditionAssocValidate", 39);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v37 = -2144206809;
      v44 = &v37;
      v42 = "BfeFwpmFilterConditionAssocValidate";
      v43 = 36;
      v45 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        a3,
        3,
        (__int64)v41);
    }
    v20 = -2144206809;
    goto LABEL_40;
  }
  v33 = v8 == 0;
LABEL_79:
  if ( !v33 )
    goto LABEL_34;
LABEL_20:
  v17 = a2 + 24;
  *(_WORD *)(a4 + 2) = 0;
  *(_DWORD *)(a4 + 4) = *(_DWORD *)(a2 + 16);
  if ( *(_DWORD *)(a2 + 24) != 14 )
  {
LABEL_21:
    v20 = BfeFwpConditionValueCopyInner(v17, a4 + 8);
    goto LABEL_22;
  }
  v24 = *(_QWORD *)(a2 + 32);
  Owner = 0;
  OwnerDefaulted[0] = 0;
  v25 = *(void **)(v24 + 8);
  OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(v25, &Owner, OwnerDefaulted);
  v29 = OwnerSecurityDescriptor;
  if ( OwnerSecurityDescriptor < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        v28,
        0,
        (__int64)"RtlGetOwnerSecurityDescriptor",
        OwnerSecurityDescriptor);
    }
    v34 = RtlNtStatusToDosError(v29);
    v35 = v34;
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v37 = v34;
      v44 = &v37;
      v42 = "RtlGetOwnerSecurityDescriptor";
      v43 = 30;
      v45 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        a3,
        3,
        (__int64)v41);
    }
    if ( v35 > 0 )
      v35 = (unsigned __int16)v35 | 0x80070000;
    v20 = v35;
LABEL_22:
    if ( !v20 )
      return v20;
    goto LABEL_23;
  }
  if ( Owner || !v25 )
    goto LABEL_21;
  v37 = 0;
  v20 = CloneSecurityDescriptorWithOwner(v25, v27, &v38, &v37);
  if ( !v20 )
  {
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v19, v18, a3) )
    {
      v20 = WfpMemAlloc25B(0x10u);
    }
    else
    {
      v30 = HeapAlloc(gWfpHeap, 0, 0x10u);
      *(_QWORD *)(a4 + 16) = v30;
      if ( v30 )
      {
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v30));
      }
      else
      {
        v36 = WfpReportSysErrorAsNtStatus(v19, "HeapAlloc", 3221225495LL);
        v20 = v36;
        if ( v36 )
          WfpReportError(v36, "WfpMemAlloc");
      }
    }
    if ( !v20 )
    {
      v31 = *(_QWORD *)(a4 + 16);
      v32 = v38;
      *(_DWORD *)(a4 + 8) = 14;
      *(_QWORD *)(v31 + 8) = v32;
      **(_DWORD **)(a4 + 16) = v37;
      return v20;
    }
  }
  v5 = v38;
LABEL_23:
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v19, v18, a3) )
  {
    WfpMemFree25B(&v38);
  }
  else
  {
    if ( gWfpTrackHeapBytes && v5 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v5));
    HeapFree(gWfpHeap, 0, v5);
  }
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v21, 0, (__int64)"BfeFilterConditionConvertM2S", v20);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v37 = v20;
      v44 = &v37;
      v42 = "BfeFilterConditionConvertM2S";
      v43 = 29;
      v45 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v21,
        3,
        (__int64)v41);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x180010ba0  push    rbp
0x180010ba2  push    rbx
0x180010ba3  push    r12
0x180010ba5  push    r13
0x180010ba7  push    r15
0x180010ba9  lea     rbp, [rsp-37h]
0x180010bae  sub     rsp, 0A0h
0x180010bb5  mov     rax, cs:__security_cookie
0x180010bbc  xor     rax, rsp
0x180010bbf  mov     [rbp+57h+var_40], rax
0x180010bc3  mov     r11, [rcx]
0x180010bc6  xor     r13d, r13d
0x180010bc9  mov     [rsp+0C0h+arg_0], rsi
0x180010bd1  mov     rbx, rdx
0x180010bd4  mov     [rsp+0C0h+var_28], rdi
0x180010bdc  mov     r15, r9
0x180010bdf  mov     r12d, r8d
0x180010be2  mov     [rbp+57h+var_88], r13
0x180010be6  movzx   edx, word ptr [r11+24h]
0x180010beb  xor     r10d, r10d
0x180010bee  mov     [rsp+0C0h+var_30], r14
0x180010bf6  cmp     r10w, dx
0x180010bfa  jnb     loc_180010DEF
0x180010c00  movzx   edi, r10w
0x180010c04  shl     rdi, 4
0x180010c08  add     rdi, [r11+28h]
0x180010c0c  mov     rcx, [rdi]
0x180010c0f  mov     rax, [rcx]
0x180010c12  sub     rax, [rbx]
0x180010c15  jnz     short loc_180010C1F
0x180010c17  mov     rax, [rcx+8]
0x180010c1b  sub     rax, [rbx+8]
0x180010c1f  test    rax, rax
0x180010c22  jz      short loc_180010C2A
0x180010c24  inc     r10w
0x180010c28  jmp     short loc_180010BF6
0x180010c2a  test    r15, r15
0x180010c2d  jz      short loc_180010C33
0x180010c2f  mov     [r9], r10w
0x180010c33  mov     ecx, [rbx+10h]
0x180010c36  cmp     ecx, 8
0x180010c39  jnz     loc_1800111FB
0x180010c3f  mov     eax, 1
0x180010c44  mov     r9d, [rdi+8]
0x180010c48  lea     r14, WPP_GLOBAL_Control
0x180010c4f  cmp     r9d, 2
0x180010c53  jz      loc_180010F47
0x180010c59  test    eax, eax
0x180010c5b  jnz     loc_180010F5C
0x180010c61  mov     edx, [rdi+0Ch]
0x180010c64  xor     r10d, r10d
0x180010c67  mov     ecx, [rbx+18h]
0x180010c6a  lea     eax, [rdx-0Fh]
0x180010c6d  cmp     eax, 1
0x180010c70  setbe   r10b
0x180010c74  cmp     ecx, 101h
0x180010c7a  jz      loc_180010D8E
0x180010c80  cmp     ecx, 0Fh
0x180010c83  jg      loc_180010EBF
0x180010c89  jz      loc_180010D97
0x180010c8f  mov     r8d, ecx
0x180010c92  test    ecx, ecx
0x180010c94  jz      short loc_180010CB2
0x180010c96  sub     r8d, 0Dh
0x180010c9a  jz      loc_180011046
0x180010ca0  cmp     r8d, 1
0x180010ca4  jz      loc_18001107E
0x180010caa  cmp     ecx, edx
0x180010cac  jnz     loc_180010D97
0x180010cb2  xor     eax, eax
0x180010cb4  lea     rdi, [rbx+18h]
0x180010cb8  mov     [r15+2], ax
0x180010cbd  mov     eax, [rbx+10h]
0x180010cc0  mov     [r15+4], eax
0x180010cc4  cmp     dword ptr [rdi], 0Eh
0x180010cc7  jz      loc_180010F82
0x180010ccd  lea     rdx, [r15+8]
0x180010cd1  mov     rcx, rdi
0x180010cd4  call    BfeFwpConditionValueCopyInner
0x180010cd9  mov     rsi, rax
0x180010cdc  test    rsi, rsi
0x180010cdf  jz      short loc_180010D57
0x180010ce1  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180010ce6  test    eax, eax
0x180010ce8  jnz     loc_180010DE1
0x180010cee  cmp     cs:gWfpTrackHeapBytes, eax
0x180010cf4  jnz     loc_180011136
0x180010cfa  mov     rcx, cs:gWfpHeap; hHeap
0x180010d01  mov     r8, r13; lpMem
0x180010d04  xor     edx, edx; dwFlags
0x180010d06  call    cs:__imp_HeapFree
0x180010d0c  test    rsi, rsi
0x180010d0f  jz      short loc_180010D57
0x180010d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d18  lea     rbx, aBfefiltercondi; "BfeFilterConditionConvertM2S"
0x180010d1f  cmp     rcx, r14
0x180010d22  jz      short loc_180010D4A
0x180010d24  cmp     byte ptr [rcx+19h], 2
0x180010d28  jb      short loc_180010D4A
0x180010d2a  test    byte ptr [rcx+1Ch], 1
0x180010d2e  jz      short loc_180010D4A
0x180010d30  mov     rcx, [rcx+10h]
0x180010d34  mov     edx, 1Ah
0x180010d39  mov     [rsp+0C0h+var_98], esi
0x180010d3d  xor     r9d, r9d
0x180010d40  mov     [rsp+0C0h+var_A0], rbx
0x180010d45  call    WPP_SF_Ssd
0x180010d4a  cmp     cs:gWfpLogUserModeErrors, 0
0x180010d51  jnz     loc_180010EF4
0x180010d57  mov     r14, [rsp+0C0h+var_30]
0x180010d5f  mov     rax, rsi
0x180010d62  mov     rsi, [rsp+0C0h+arg_0]
0x180010d6a  mov     rdi, [rsp+0C0h+var_28]
0x180010d72  mov     rcx, [rbp+57h+var_40]
0x180010d76  xor     rcx, rsp; StackCookie
0x180010d79  call    __security_check_cookie
0x180010d7e  add     rsp, 0A0h
0x180010d85  pop     r15
0x180010d87  pop     r13
0x180010d89  pop     r12
0x180010d8b  pop     rbx
0x180010d8c  pop     rbp
0x180010d8d  retn
0x180010d8e  cmp     edx, 0Bh
0x180010d91  jz      loc_18001106F
0x180010d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d9e  lea     rdi, aBfefwpmfilterc_2; "BfeFwpmFilterConditionAssocValidate"
0x180010da5  cmp     rcx, r14
0x180010da8  jz      short loc_180010DB4
0x180010daa  cmp     byte ptr [rcx+19h], 2
0x180010dae  jnb     loc_1800110E7
0x180010db4  cmp     cs:gWfpLogUserModeErrors, r13d
0x180010dbb  jz      short loc_180010DCA
0x180010dbd  test    cs:byte_1800F30F5, 1
0x180010dc4  jnz     loc_180011234
0x180010dca  mov     rsi, 0FFFFFFFF80320027h
0x180010dd1  mov     rdx, rdi
0x180010dd4  mov     rcx, rsi
0x180010dd7  call    WfpReportError
0x180010ddc  jmp     loc_180010CDC
0x180010de1  lea     rcx, [rbp+57h+var_88]
0x180010de5  call    WfpMemFree25B
0x180010dea  jmp     loc_180010D0C
0x180010def  xor     edi, edi
0x180010df1  lea     rdx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180010df8  mov     r8d, 80320002h
0x180010dfe  call    WfpReportSysErrorAsWinError
0x180010e03  mov     rsi, rax
0x180010e06  test    rax, rax
0x180010e09  jz      loc_180010C33
0x180010e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e16  lea     r14, WPP_GLOBAL_Control
0x180010e1d  cmp     rcx, r14
0x180010e20  jz      loc_180010EB6
0x180010e26  cmp     byte ptr [rcx+19h], 2
0x180010e2a  jb      loc_180010EB6
0x180010e30  test    byte ptr [rcx+1Ch], 1
0x180010e34  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180010e3b  jz      short loc_180010E57
0x180010e3d  mov     rcx, [rcx+10h]
0x180010e41  mov     edx, 1Ah
0x180010e46  mov     [rsp+0C0h+var_98], esi
0x180010e4a  xor     r9d, r9d
0x180010e4d  mov     [rsp+0C0h+var_A0], rbx
0x180010e52  call    WPP_SF_Ssd
0x180010e57  cmp     cs:gWfpLogUserModeErrors, edi
0x180010e5d  jz      loc_180010CE1
0x180010e63  test    cs:byte_1800F30F5, 1
0x180010e6a  jz      loc_180010CE1
0x180010e70  lea     rax, [rbp+57h+var_90]
0x180010e74  mov     [rbp+57h+var_90], esi
0x180010e77  mov     [rbp+57h+var_50], rax
0x180010e7b  lea     rdx, WFP_USERMODE_ERROR
0x180010e82  lea     rax, [rbp+57h+var_70]
0x180010e86  mov     [rbp+57h+var_60], rbx
0x180010e8a  mov     r9d, 3
0x180010e90  mov     [rsp+0C0h+var_A0], rax
0x180010e95  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180010e9c  mov     [rbp+57h+var_58], 1Ch
0x180010ea4  mov     [rbp+57h+var_48], 4
0x180010eac  call    McGenEventWrite_EtwEventWriteTransfer
0x180010eb1  jmp     loc_180010CE1
0x180010eb6  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180010ebd  jmp     short loc_180010E57
0x180010ebf  mov     r8d, ecx
0x180010ec2  sub     r8d, 10h
0x180010ec6  jz      loc_180010D97
0x180010ecc  sub     r8d, 0F0h
0x180010ed3  jz      loc_180011066
0x180010ed9  cmp     r8d, 2
0x180010edd  jnz     loc_180010CAA
0x180010ee3  mov     rax, [rbx+20h]
0x180010ee7  cmp     [rax], edx
0x180010ee9  jnz     loc_180010D97
0x180010eef  jmp     loc_180010CB2
0x180010ef4  test    cs:byte_1800F30F5, 1
0x180010efb  jz      loc_180010D57
0x180010f01  lea     rax, [rbp+57h+var_90]
0x180010f05  mov     [rbp+57h+var_90], esi
0x180010f08  mov     [rbp+57h+var_50], rax
0x180010f0c  lea     rdx, WFP_USERMODE_ERROR
0x180010f13  lea     rax, [rbp+57h+var_70]
0x180010f17  mov     [rbp+57h+var_60], rbx
0x180010f1b  mov     r9d, 3
0x180010f21  mov     [rsp+0C0h+var_A0], rax
0x180010f26  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180010f2d  mov     [rbp+57h+var_58], 1Dh
0x180010f35  mov     [rbp+57h+var_48], 4
0x180010f3d  call    McGenEventWrite_EtwEventWriteTransfer
0x180010f42  jmp     loc_180010D57
0x180010f47  test    ecx, ecx
0x180010f49  jz      loc_180010C61
0x180010f4f  test    r12d, r12d
0x180010f52  jnz     short loc_180010F5C
0x180010f54  test    eax, eax
0x180010f56  jnz     loc_180010C61
0x180010f5c  lea     rdi, aBfefwpmfilterc_2; "BfeFwpmFilterConditionAssocValidate"
0x180010f63  mov     r8d, 80320026h
0x180010f69  mov     rdx, rdi
0x180010f6c  call    WfpReportSysErrorAsWinError
0x180010f71  mov     rsi, rax
0x180010f74  test    rax, rax
0x180010f77  jz      loc_180010CB2
0x180010f7d  jmp     loc_180010DD1
0x180010f82  mov     rax, [rbx+20h]
0x180010f86  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x180010f8a  mov     [rbp+57h+Owner], r13
0x180010f8e  lea     rdx, [rbp+57h+Owner]; Owner
0x180010f92  mov     [rbp+57h+OwnerDefaulted], r13b
0x180010f96  mov     rbx, [rax+8]
0x180010f9a  mov     rcx, rbx; SecurityDescriptor
0x180010f9d  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x180010fa3  mov     esi, eax
0x180010fa5  test    eax, eax
0x180010fa7  js      loc_1800110A7
0x180010fad  cmp     [rbp+57h+Owner], r13
0x180010fb1  jnz     loc_180010CCD
0x180010fb7  test    rbx, rbx
0x180010fba  jz      loc_180010CCD
0x180010fc0  lea     r9, [rbp+57h+var_90]
0x180010fc4  mov     [rbp+57h+var_90], r13d
0x180010fc8  lea     r8, [rbp+57h+var_88]
0x180010fcc  mov     rcx, rbx; Src
0x180010fcf  call    CloneSecurityDescriptorWithOwner
0x180010fd4  mov     rsi, rax
0x180010fd7  test    rax, rax
0x180010fda  jnz     loc_1800111F2
0x180010fe0  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180010fe5  xor     edx, edx; dwFlags
0x180010fe7  test    eax, eax
0x180010fe9  jnz     loc_180011091
0x180010fef  mov     rcx, cs:gWfpHeap; hHeap
0x180010ff6  mov     r8d, 10h; dwBytes
0x180010ffc  call    cs:__imp_HeapAlloc
0x180011002  mov     [r15+10h], rax
0x180011006  test    rax, rax
0x180011009  jz      loc_1800111C0
0x18001100f  cmp     cs:gWfpTrackHeapBytes, esi
0x180011015  jnz     loc_180011216
0x18001101b  test    rsi, rsi
0x18001101e  jnz     loc_1800111F2
0x180011024  mov     rcx, [r15+10h]
0x180011028  mov     rax, [rbp+57h+var_88]
0x18001102c  mov     dword ptr [r15+8], 0Eh
0x180011034  mov     [rcx+8], rax
0x180011038  mov     rcx, [r15+10h]
0x18001103c  mov     eax, [rbp+57h+var_90]
0x18001103f  mov     [rcx], eax
0x180011041  jmp     loc_180010D57
0x180011046  cmp     edx, 0Dh
0x180011049  jz      loc_180010CB2
0x18001104f  test    r12d, r12d
0x180011052  jz      loc_180010D97
0x180011058  test    r10d, r10d
0x18001105b  jnz     loc_180010CB2
0x180011061  jmp     loc_180010D97
0x180011066  cmp     edx, 3
0x180011069  jnz     loc_180010D97
0x18001106f  cmp     r9d, 1
0x180011073  jz      loc_180010CB2
0x180011079  jmp     loc_180010D97
0x18001107e  cmp     edx, 0Dh
0x180011081  jz      short loc_18001108C
0x180011083  test    r10d, r10d
0x180011086  jz      loc_180010D97
0x18001108c  test    r12d, r12d
0x18001108f  jmp     short loc_180011073
0x180011091  lea     r8, [r15+10h]
0x180011095  mov     ecx, 10h; dwBytes
0x18001109a  call    WfpMemAlloc25B
0x18001109f  mov     rsi, rax
0x1800110a2  jmp     loc_18001101B
0x1800110a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110ae  lea     rdi, aRtlgetownersec; "RtlGetOwnerSecurityDescriptor"
0x1800110b5  cmp     rcx, r14
0x1800110b8  jz      short loc_1800110C0
0x1800110ba  cmp     byte ptr [rcx+19h], 2
0x1800110be  jnb     short loc_180011114
0x1800110c0  mov     ecx, esi; Status
0x1800110c2  call    cs:__imp_RtlNtStatusToDosError
  ... truncated ...
```
