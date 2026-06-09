# BfeFilterConditionConvertM2S

- ea: `0x1800115f0`
- end: `0x180011c3f`
- name: `BfeFilterConditionConvertM2S`
- size: `1615`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013f60`
- `0x180026c44`

## callees

- `0x18000fb34`
- `0x180010480`
- `0x180011510`
- `0x1800115f0`
- `0x180012d8c`
- `0x1800133a0`
- `0x1800135ac`
- `0x1800197d0`
- `0x18002409c`
- `0x18004fb50`
- `0x180055f04`
- `0x1800560f8`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800119f4`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800119f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011a57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011a57`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011b61`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011bdd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011b61`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180011bdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011756`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011756`

## string_xrefs

- `0x180011b0b`: `RtlGetOwnerSecurityDescriptor`

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
  __int64 v28; // rcx
  const void *v29; // rax
  __int64 v30; // rcx
  PSECURITY_DESCRIPTOR v31; // rax
  bool v32; // zf
  __int64 v33; // rax
  ULONG v34; // [rsp+30h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR v35; // [rsp+38h] [rbp-31h] BYREF
  PSID Owner; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 OwnerDefaulted[8]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v38[16]; // [rsp+50h] [rbp-19h] BYREF
  const char *v39; // [rsp+60h] [rbp-9h]
  __int64 v40; // [rsp+68h] [rbp-1h]
  ULONG *v41; // [rsp+70h] [rbp+7h]
  __int64 v42; // [rsp+78h] [rbp+Fh]

  v4 = *a1;
  v5 = 0;
  v8 = a3;
  v35 = 0;
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
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v34 = v20;
      v41 = &v34;
      v39 = "BfeLayerLookupConditionInfo";
      v40 = 28;
      v42 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        a3,
        3,
        (__int64)v38);
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
    v32 = v14 == 1;
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
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v34 = -2144206809;
      v41 = &v34;
      v39 = "BfeFwpmFilterConditionAssocValidate";
      v40 = 36;
      v42 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        a3,
        3,
        (__int64)v38);
    }
    v20 = -2144206809;
    goto LABEL_40;
  }
  v32 = v8 == 0;
LABEL_79:
  if ( !v32 )
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
  if ( OwnerSecurityDescriptor < 0 )
  {
    v20 = WfpReportSysErrorAsNtStatus(v28, "RtlGetOwnerSecurityDescriptor", (unsigned int)OwnerSecurityDescriptor);
LABEL_22:
    if ( !v20 )
      return v20;
    goto LABEL_23;
  }
  if ( Owner || !v25 )
    goto LABEL_21;
  v34 = 0;
  v20 = CloneSecurityDescriptorWithOwner(v25, v27, &v35, &v34);
  if ( !v20 )
  {
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v19, v18, a3) )
    {
      v20 = WfpMemAlloc25B(0x10u);
    }
    else
    {
      v29 = HeapAlloc(gWfpHeap, 0, 0x10u);
      *(_QWORD *)(a4 + 16) = v29;
      if ( v29 )
      {
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v29));
      }
      else
      {
        v33 = WfpReportSysErrorAsNtStatus(v19, "HeapAlloc", 3221225495LL);
        v20 = v33;
        if ( v33 )
          WfpReportError(v33, "WfpMemAlloc");
      }
    }
    if ( !v20 )
    {
      v30 = *(_QWORD *)(a4 + 16);
      v31 = v35;
      *(_DWORD *)(a4 + 8) = 14;
      *(_QWORD *)(v30 + 8) = v31;
      **(_DWORD **)(a4 + 16) = v34;
      return v20;
    }
  }
  v5 = v35;
LABEL_23:
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v19, v18, a3) )
  {
    WfpMemFree25B(&v35);
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
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v34 = v20;
      v41 = &v34;
      v39 = "BfeFilterConditionConvertM2S";
      v40 = 29;
      v42 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v21,
        3,
        (__int64)v38);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x1800115f0  push    rbp
0x1800115f2  push    rbx
0x1800115f3  push    r12
0x1800115f5  push    r13
0x1800115f7  push    r15
0x1800115f9  lea     rbp, [rsp-37h]
0x1800115fe  sub     rsp, 0A0h
0x180011605  mov     rax, cs:__security_cookie
0x18001160c  xor     rax, rsp
0x18001160f  mov     [rbp+57h+var_40], rax
0x180011613  mov     r11, [rcx]
0x180011616  xor     r13d, r13d
0x180011619  mov     [rsp+0C0h+arg_0], rsi
0x180011621  mov     rbx, rdx
0x180011624  mov     [rsp+0C0h+var_28], rdi
0x18001162c  mov     r15, r9
0x18001162f  mov     r12d, r8d
0x180011632  mov     [rbp+57h+var_88], r13
0x180011636  movzx   edx, word ptr [r11+24h]
0x18001163b  xor     r10d, r10d
0x18001163e  mov     [rsp+0C0h+var_30], r14
0x180011646  cmp     r10w, dx
0x18001164a  jnb     loc_180011846
0x180011650  movzx   edi, r10w
0x180011654  shl     rdi, 4
0x180011658  add     rdi, [r11+28h]
0x18001165c  mov     rcx, [rdi]
0x18001165f  mov     rax, [rcx]
0x180011662  sub     rax, [rbx]
0x180011665  jnz     short loc_18001166F
0x180011667  mov     rax, [rcx+8]
0x18001166b  sub     rax, [rbx+8]
0x18001166f  test    rax, rax
0x180011672  jz      short loc_18001167A
0x180011674  inc     r10w
0x180011678  jmp     short loc_180011646
0x18001167a  test    r15, r15
0x18001167d  jz      short loc_180011683
0x18001167f  mov     [r9], r10w
0x180011683  mov     ecx, [rbx+10h]
0x180011686  cmp     ecx, 8
0x180011689  jnz     loc_180011BB6
0x18001168f  mov     eax, 1
0x180011694  mov     r9d, [rdi+8]
0x180011698  lea     r14, WPP_GLOBAL_Control
0x18001169f  cmp     r9d, 2
0x1800116a3  jz      loc_18001199E
0x1800116a9  test    eax, eax
0x1800116ab  jnz     loc_1800119B3
0x1800116b1  mov     edx, [rdi+0Ch]
0x1800116b4  xor     r10d, r10d
0x1800116b7  mov     ecx, [rbx+18h]
0x1800116ba  lea     eax, [rdx-0Fh]
0x1800116bd  cmp     eax, 1
0x1800116c0  setbe   r10b
0x1800116c4  cmp     ecx, 101h
0x1800116ca  jz      loc_1800117E5
0x1800116d0  cmp     ecx, 0Fh
0x1800116d3  jg      loc_180011916
0x1800116d9  jz      loc_1800117EE
0x1800116df  mov     r8d, ecx
0x1800116e2  test    ecx, ecx
0x1800116e4  jz      short loc_180011702
0x1800116e6  sub     r8d, 0Dh
0x1800116ea  jz      loc_180011AA7
0x1800116f0  cmp     r8d, 1
0x1800116f4  jz      loc_180011ADF
0x1800116fa  cmp     ecx, edx
0x1800116fc  jnz     loc_1800117EE
0x180011702  xor     eax, eax
0x180011704  lea     rdi, [rbx+18h]
0x180011708  mov     [r15+2], ax
0x18001170d  mov     eax, [rbx+10h]
0x180011710  mov     [r15+4], eax
0x180011714  cmp     dword ptr [rdi], 0Eh
0x180011717  jz      loc_1800119D9
0x18001171d  lea     rdx, [r15+8]
0x180011721  mov     rcx, rdi
0x180011724  call    BfeFwpConditionValueCopyInner
0x180011729  mov     rsi, rax
0x18001172c  test    rsi, rsi
0x18001172f  jz      short loc_1800117AD
0x180011731  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180011736  test    eax, eax
0x180011738  jnz     loc_180011838
0x18001173e  cmp     cs:gWfpTrackHeapBytes, eax
0x180011744  jnz     loc_180011B4C
0x18001174a  mov     rcx, cs:gWfpHeap; hHeap
0x180011751  mov     r8, r13; lpMem
0x180011754  xor     edx, edx; dwFlags
0x180011756  call    cs:__imp_HeapFree
0x18001175d  nop     dword ptr [rax+rax+00h]
0x180011762  test    rsi, rsi
0x180011765  jz      short loc_1800117AD
0x180011767  mov     rcx, cs:WPP_GLOBAL_Control
0x18001176e  lea     rbx, aBfefiltercondi; "BfeFilterConditionConvertM2S"
0x180011775  cmp     rcx, r14
0x180011778  jz      short loc_1800117A0
0x18001177a  cmp     byte ptr [rcx+19h], 2
0x18001177e  jb      short loc_1800117A0
0x180011780  test    byte ptr [rcx+1Ch], 1
0x180011784  jz      short loc_1800117A0
0x180011786  mov     rcx, [rcx+10h]
0x18001178a  mov     edx, 1Ah
0x18001178f  mov     [rsp+0C0h+var_98], esi
0x180011793  xor     r9d, r9d
0x180011796  mov     [rsp+0C0h+var_A0], rbx
0x18001179b  call    WPP_SF_Ssd
0x1800117a0  cmp     cs:gWfpLogUserModeErrors, 0
0x1800117a7  jnz     loc_18001194B
0x1800117ad  mov     r14, [rsp+0C0h+var_30]
0x1800117b5  mov     rax, rsi
0x1800117b8  mov     rsi, [rsp+0C0h+arg_0]
0x1800117c0  mov     rdi, [rsp+0C0h+var_28]
0x1800117c8  mov     rcx, [rbp+57h+var_40]
0x1800117cc  xor     rcx, rsp; StackCookie
0x1800117cf  call    __security_check_cookie
0x1800117d4  add     rsp, 0A0h
0x1800117db  pop     r15
0x1800117dd  pop     r13
0x1800117df  pop     r12
0x1800117e1  pop     rbx
0x1800117e2  pop     rbp
0x1800117e3  retn
0x1800117e5  cmp     edx, 0Bh
0x1800117e8  jz      loc_180011AD0
0x1800117ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117f5  lea     rdi, aBfefwpmfilterc_2; "BfeFwpmFilterConditionAssocValidate"
0x1800117fc  cmp     rcx, r14
0x1800117ff  jz      short loc_18001180B
0x180011801  cmp     byte ptr [rcx+19h], 2
0x180011805  jnb     loc_180011B1F
0x18001180b  cmp     cs:gWfpLogUserModeErrors, r13d
0x180011812  jz      short loc_180011821
0x180011814  test    cs:byte_1800F6115, 1
0x18001181b  jnz     loc_180011BF5
0x180011821  mov     rsi, 0FFFFFFFF80320027h
0x180011828  mov     rdx, rdi
0x18001182b  mov     rcx, rsi
0x18001182e  call    WfpReportError
0x180011833  jmp     loc_18001172C
0x180011838  lea     rcx, [rbp+57h+var_88]
0x18001183c  call    WfpMemFree25B
0x180011841  jmp     loc_180011762
0x180011846  xor     edi, edi
0x180011848  lea     rdx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x18001184f  mov     r8d, 80320002h
0x180011855  call    WfpReportSysErrorAsWinError
0x18001185a  mov     rsi, rax
0x18001185d  test    rax, rax
0x180011860  jz      loc_180011683
0x180011866  mov     rcx, cs:WPP_GLOBAL_Control
0x18001186d  lea     r14, WPP_GLOBAL_Control
0x180011874  cmp     rcx, r14
0x180011877  jz      loc_18001190D
0x18001187d  cmp     byte ptr [rcx+19h], 2
0x180011881  jb      loc_18001190D
0x180011887  test    byte ptr [rcx+1Ch], 1
0x18001188b  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180011892  jz      short loc_1800118AE
0x180011894  mov     rcx, [rcx+10h]
0x180011898  mov     edx, 1Ah
0x18001189d  mov     [rsp+0C0h+var_98], esi
0x1800118a1  xor     r9d, r9d
0x1800118a4  mov     [rsp+0C0h+var_A0], rbx
0x1800118a9  call    WPP_SF_Ssd
0x1800118ae  cmp     cs:gWfpLogUserModeErrors, edi
0x1800118b4  jz      loc_180011731
0x1800118ba  test    cs:byte_1800F6115, 1
0x1800118c1  jz      loc_180011731
0x1800118c7  lea     rax, [rbp+57h+var_90]
0x1800118cb  mov     [rbp+57h+var_90], esi
0x1800118ce  mov     [rbp+57h+var_50], rax
0x1800118d2  lea     rdx, WFP_USERMODE_ERROR
0x1800118d9  lea     rax, [rbp+57h+var_70]
0x1800118dd  mov     [rbp+57h+var_60], rbx
0x1800118e1  mov     r9d, 3
0x1800118e7  mov     [rsp+0C0h+var_A0], rax
0x1800118ec  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800118f3  mov     [rbp+57h+var_58], 1Ch
0x1800118fb  mov     [rbp+57h+var_48], 4
0x180011903  call    McGenEventWrite_EtwEventWriteTransfer
0x180011908  jmp     loc_180011731
0x18001190d  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180011914  jmp     short loc_1800118AE
0x180011916  mov     r8d, ecx
0x180011919  sub     r8d, 10h
0x18001191d  jz      loc_1800117EE
0x180011923  sub     r8d, 0F0h
0x18001192a  jz      loc_180011AC7
0x180011930  cmp     r8d, 2
0x180011934  jnz     loc_1800116FA
0x18001193a  mov     rax, [rbx+20h]
0x18001193e  cmp     [rax], edx
0x180011940  jnz     loc_1800117EE
0x180011946  jmp     loc_180011702
0x18001194b  test    cs:byte_1800F6115, 1
0x180011952  jz      loc_1800117AD
0x180011958  lea     rax, [rbp+57h+var_90]
0x18001195c  mov     [rbp+57h+var_90], esi
0x18001195f  mov     [rbp+57h+var_50], rax
0x180011963  lea     rdx, WFP_USERMODE_ERROR
0x18001196a  lea     rax, [rbp+57h+var_70]
0x18001196e  mov     [rbp+57h+var_60], rbx
0x180011972  mov     r9d, 3
0x180011978  mov     [rsp+0C0h+var_A0], rax
0x18001197d  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180011984  mov     [rbp+57h+var_58], 1Dh
0x18001198c  mov     [rbp+57h+var_48], 4
0x180011994  call    McGenEventWrite_EtwEventWriteTransfer
0x180011999  jmp     loc_1800117AD
0x18001199e  test    ecx, ecx
0x1800119a0  jz      loc_1800116B1
0x1800119a6  test    r12d, r12d
0x1800119a9  jnz     short loc_1800119B3
0x1800119ab  test    eax, eax
0x1800119ad  jnz     loc_1800116B1
0x1800119b3  lea     rdi, aBfefwpmfilterc_2; "BfeFwpmFilterConditionAssocValidate"
0x1800119ba  mov     r8d, 80320026h
0x1800119c0  mov     rdx, rdi
0x1800119c3  call    WfpReportSysErrorAsWinError
0x1800119c8  mov     rsi, rax
0x1800119cb  test    rax, rax
0x1800119ce  jz      loc_180011702
0x1800119d4  jmp     loc_180011828
0x1800119d9  mov     rax, [rbx+20h]
0x1800119dd  lea     r8, [rbp+57h+OwnerDefaulted]; OwnerDefaulted
0x1800119e1  mov     [rbp+57h+Owner], r13
0x1800119e5  lea     rdx, [rbp+57h+Owner]; Owner
0x1800119e9  mov     [rbp+57h+OwnerDefaulted], r13b
0x1800119ed  mov     rbx, [rax+8]
0x1800119f1  mov     rcx, rbx; SecurityDescriptor
0x1800119f4  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800119fb  nop     dword ptr [rax+rax+00h]
0x180011a00  test    eax, eax
0x180011a02  js      loc_180011B08
0x180011a08  cmp     [rbp+57h+Owner], r13
0x180011a0c  jnz     loc_18001171D
0x180011a12  test    rbx, rbx
0x180011a15  jz      loc_18001171D
0x180011a1b  lea     r9, [rbp+57h+var_90]
0x180011a1f  mov     [rbp+57h+var_90], r13d
0x180011a23  lea     r8, [rbp+57h+var_88]
0x180011a27  mov     rcx, rbx; Src
0x180011a2a  call    CloneSecurityDescriptorWithOwner
0x180011a2f  mov     rsi, rax
0x180011a32  test    rax, rax
0x180011a35  jnz     loc_180011BAD
0x180011a3b  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180011a40  xor     edx, edx; dwFlags
0x180011a42  test    eax, eax
0x180011a44  jnz     loc_180011AF2
0x180011a4a  mov     rcx, cs:gWfpHeap; hHeap
0x180011a51  mov     r8d, 10h; dwBytes
0x180011a57  call    cs:__imp_HeapAlloc
0x180011a5e  nop     dword ptr [rax+rax+00h]
0x180011a63  mov     [r15+10h], rax
0x180011a67  test    rax, rax
0x180011a6a  jz      loc_180011B7B
0x180011a70  cmp     cs:gWfpTrackHeapBytes, esi
0x180011a76  jnz     loc_180011BD1
0x180011a7c  test    rsi, rsi
0x180011a7f  jnz     loc_180011BAD
0x180011a85  mov     rcx, [r15+10h]
0x180011a89  mov     rax, [rbp+57h+var_88]
0x180011a8d  mov     dword ptr [r15+8], 0Eh
0x180011a95  mov     [rcx+8], rax
0x180011a99  mov     rcx, [r15+10h]
0x180011a9d  mov     eax, [rbp+57h+var_90]
0x180011aa0  mov     [rcx], eax
0x180011aa2  jmp     loc_1800117AD
0x180011aa7  cmp     edx, 0Dh
0x180011aaa  jz      loc_180011702
0x180011ab0  test    r12d, r12d
0x180011ab3  jz      loc_1800117EE
0x180011ab9  test    r10d, r10d
0x180011abc  jnz     loc_180011702
0x180011ac2  jmp     loc_1800117EE
0x180011ac7  cmp     edx, 3
0x180011aca  jnz     loc_1800117EE
0x180011ad0  cmp     r9d, 1
0x180011ad4  jz      loc_180011702
0x180011ada  jmp     loc_1800117EE
0x180011adf  cmp     edx, 0Dh
0x180011ae2  jz      short loc_180011AED
0x180011ae4  test    r10d, r10d
0x180011ae7  jz      loc_1800117EE
0x180011aed  test    r12d, r12d
0x180011af0  jmp     short loc_180011AD4
0x180011af2  lea     r8, [r15+10h]
0x180011af6  mov     ecx, 10h; dwBytes
0x180011afb  call    WfpMemAlloc25B
0x180011b00  mov     rsi, rax
0x180011b03  jmp     loc_180011A7C
0x180011b08  mov     r8d, eax
0x180011b0b  lea     rdx, aRtlgetownersec; "RtlGetOwnerSecurityDescriptor"
0x180011b12  call    WfpReportSysErrorAsNtStatus
0x180011b17  mov     rsi, rax
0x180011b1a  jmp     loc_18001172C
0x180011b1f  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
