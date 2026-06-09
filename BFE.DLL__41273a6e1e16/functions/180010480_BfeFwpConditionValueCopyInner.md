# BfeFwpConditionValueCopyInner

- ea: `0x180010480`
- end: `0x180010c24`
- name: `BfeFwpConditionValueCopyInner`
- size: `1956`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fb90`
- `0x1800115f0`
- `0x180013f60`
- `0x180039134`

## callees

- `0x18000fb34`
- `0x180010480`
- `0x180011510`
- `0x180012e20`
- `0x1800135ac`
- `0x1800197d0`
- `0x180024e40`
- `0x180031210`
- `0x180038ff8`
- `0x18004fb50`
- `0x180055f04`
- `0x1800560f8`
- `0x180058f84`
- `0x18005aa60`
- `0x18008ad6c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800108d9`
- `ntdll!RtlLengthSid` at `0x1800108d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800105fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010657`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001075f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800105fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010657`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001075f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800107df`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001099f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010a98`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010b4f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010b73`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010bc8`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001099f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010a98`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010b4f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010b73`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010bc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104db`

## string_xrefs

- `0x180010539`: `BfeFwpConditionValueCopyInner`
- `0x1800104ee`: `BfeFwpByteBlobCopy`

## pseudocode

```c
__int64 __fastcall BfeFwpConditionValueCopyInner(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  int v4; // ecx
  int v6; // r8d
  _QWORD *v7; // rcx
  int *v9; // r15
  void **v10; // rax
  __int64 v11; // rcx
  void **v12; // rdi
  unsigned int v13; // eax
  SIZE_T v14; // rbx
  void *v15; // rax
  __int64 v16; // rcx
  int v17; // ecx
  const void *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  const void *v22; // rax
  __int64 v23; // rcx
  ULONG v24; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  void **v31; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v32[16]; // [rsp+38h] [rbp-60h] BYREF
  const char *v33; // [rsp+48h] [rbp-50h]
  __int64 v34; // [rsp+50h] [rbp-48h]
  void ***v35; // [rsp+58h] [rbp-40h]
  __int64 v36; // [rsp+60h] [rbp-38h]

  *(_DWORD *)a2 = *(_DWORD *)a1;
  v3 = 0;
  v4 = *(_DWORD *)a1;
  if ( v4 == 1 )
  {
    *(_BYTE *)(a2 + 8) = *(_BYTE *)(a1 + 8);
    return v3;
  }
  if ( v4 > 256 )
  {
    v17 = v4 - 257;
    if ( v17 )
    {
      if ( v17 != 1 )
        return v3;
      v3 = BfeFwpRangeCopy(*(_QWORD *)(a1 + 8), a2 + 8);
      if ( !v3 )
        return v3;
    }
    else
    {
      if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
      {
        v3 = WfpMemAlloc25B(0x11u);
      }
      else
      {
        v18 = HeapAlloc(gWfpHeap, 0, 0x11u);
        *(_QWORD *)(a2 + 8) = v18;
        if ( v18 )
        {
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v18));
        }
        else
        {
          v27 = WfpReportSysErrorAsNtStatus(v19, "HeapAlloc", 3221225495LL);
          v3 = v27;
          if ( v27 )
            WfpReportError(v27, "WfpMemAlloc");
        }
      }
      if ( !v3 )
      {
        v20 = *(_QWORD *)(a1 + 8);
        v21 = *(_QWORD *)(a2 + 8);
        *(_OWORD *)v21 = *(_OWORD *)v20;
        *(_BYTE *)(v21 + 16) = *(_BYTE *)(v20 + 16);
        return v3;
      }
    }
    goto LABEL_56;
  }
  if ( v4 == 256 )
  {
    v3 = WfpMemAlloc(8u, 0);
    if ( !v3 )
    {
      **(_QWORD **)(a2 + 8) = **(_QWORD **)(a1 + 8);
      return v3;
    }
LABEL_56:
    v7 = WPP_GLOBAL_Control;
LABEL_10:
    if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 2u && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_Ssd(v7[2], 26, v6, 0, (__int64)"BfeFwpConditionValueCopyInner", v3);
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      LODWORD(v31) = v3;
      v35 = &v31;
      v33 = "BfeFwpConditionValueCopyInner";
      v34 = 30;
      v36 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v6,
        3,
        (__int64)v32);
    }
    return v3;
  }
  switch ( v4 )
  {
    case 2:
    case 6:
      *(_WORD *)(a2 + 8) = *(_WORD *)(a1 + 8);
      return v3;
    case 3:
    case 7:
    case 9:
      *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 8);
      return v3;
    case 4:
      if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
      {
        v3 = WfpMemAlloc25B(8u);
      }
      else
      {
        v22 = HeapAlloc(gWfpHeap, 0, 8u);
        *(_QWORD *)(a2 + 8) = v22;
        if ( v22 )
        {
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v22));
        }
        else
        {
          v28 = WfpReportSysErrorAsNtStatus(v23, "HeapAlloc", 3221225495LL);
          v3 = v28;
          if ( v28 )
            WfpReportError(v28, "WfpMemAlloc");
        }
      }
      if ( v3 )
        goto LABEL_56;
      **(_QWORD **)(a2 + 8) = **(_QWORD **)(a1 + 8);
      return v3;
    case 5:
      *(_BYTE *)(a2 + 8) = *(_BYTE *)(a1 + 8);
      return v3;
    case 8:
      v3 = WfpMemAlloc(8u, 0);
      if ( v3 )
        goto LABEL_56;
      **(_QWORD **)(a2 + 8) = **(_QWORD **)(a1 + 8);
      return v3;
    case 10:
      v3 = WfpMemAlloc(8u, 0);
      if ( v3 )
        goto LABEL_56;
      **(_QWORD **)(a2 + 8) = **(_QWORD **)(a1 + 8);
      return v3;
    case 11:
      v3 = WfpMemAlloc(0x10u, 0);
      if ( v3 )
        goto LABEL_56;
      *(_OWORD *)*(_QWORD *)(a2 + 8) = *(_OWORD *)*(_QWORD *)(a1 + 8);
      return v3;
    case 12:
    case 14:
    case 16:
      v9 = *(int **)(a1 + 8);
      v31 = 0;
      if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
      {
        v12 = v31;
        v3 = WfpMemAlloc25B(0x10u);
      }
      else
      {
        v10 = (void **)HeapAlloc(gWfpHeap, 0, 0x10u);
        v31 = v10;
        v12 = v10;
        if ( v10 )
        {
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v10));
        }
        else
        {
          v25 = WfpReportSysErrorAsNtStatus(v11, "HeapAlloc", 3221225495LL);
          v3 = v25;
          if ( v25 )
            WfpReportError(v25, "WfpMemAlloc");
        }
      }
      if ( v3 )
        goto LABEL_43;
      v13 = *v9;
      *(_DWORD *)v12 = *v9;
      if ( v13 )
      {
        v14 = v13;
        if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
        {
          v3 = WfpMemAlloc25B(v14);
        }
        else
        {
          v15 = HeapAlloc(gWfpHeap, 0, (unsigned int)v14);
          v12[1] = v15;
          if ( v15 )
          {
            v3 = 0;
            if ( gWfpTrackHeapBytes )
              _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v15));
          }
          else
          {
            v26 = WfpReportSysErrorAsNtStatus(v16, "HeapAlloc", 3221225495LL);
            v3 = v26;
            if ( v26 )
              WfpReportError(v26, "WfpMemAlloc");
          }
        }
        if ( v3 )
        {
LABEL_43:
          if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
          {
            WfpMemFree25B(&v31);
          }
          else
          {
            if ( gWfpTrackHeapBytes && v12 )
              _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v12));
            HeapFree(gWfpHeap, 0, v12);
          }
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v6, 0, (__int64)"BfeFwpByteBlobCopy", v3);
            v7 = WPP_GLOBAL_Control;
          }
          if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
          {
            LODWORD(v31) = v3;
            v35 = &v31;
            v33 = "BfeFwpByteBlobCopy";
            v34 = 19;
            v36 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
              (unsigned int)WFP_USERMODE_ERROR,
              v6,
              3,
              (__int64)v32);
            v7 = WPP_GLOBAL_Control;
          }
          goto LABEL_10;
        }
        memcpy_0(v12[1], *((const void **)v9 + 1), *(unsigned int *)v12);
        *(_QWORD *)(a2 + 8) = v12;
      }
      else
      {
        v12[1] = 0;
        *(_QWORD *)(a2 + 8) = v12;
      }
      break;
    case 13:
      v24 = RtlLengthSid(*(PSID *)(a1 + 8));
      v3 = WfpBufferCopy(*(void **)(a1 + 8), v24);
      if ( v3 )
        goto LABEL_56;
      return v3;
    case 15:
      v3 = BfeFwpTokenInformationCopy(*(_QWORD *)(a1 + 8), a2 + 8);
      if ( v3 )
        goto LABEL_56;
      return v3;
    case 17:
      v3 = WfpStringCopy(*(void **)(a1 + 8));
      if ( v3 )
        goto LABEL_56;
      return v3;
    case 18:
      v3 = WfpMemAlloc(6u, 0);
      if ( v3 )
        goto LABEL_56;
      v29 = *(_QWORD *)(a1 + 8);
      v30 = *(_QWORD *)(a2 + 8);
      *(_DWORD *)v30 = *(_DWORD *)v29;
      *(_WORD *)(v30 + 4) = *(_WORD *)(v29 + 4);
      return v3;
    default:
      return v3;
  }
  return v3;
}

```

## disassembly

```asm
0x180010480  mov     [rsp+arg_10], rbx
0x180010485  push    rbp
0x180010486  push    rsi
0x180010487  push    rdi
0x180010488  push    r14
0x18001048a  push    r15
0x18001048c  sub     rsp, 70h
0x180010490  mov     rax, cs:__security_cookie
0x180010497  xor     rax, rsp
0x18001049a  mov     [rsp+98h+var_30], rax
0x18001049f  mov     eax, [rcx]
0x1800104a1  mov     rdi, rcx
0x1800104a4  mov     [rdx], eax
0x1800104a6  xor     ebx, ebx
0x1800104a8  mov     ecx, [rcx]
0x1800104aa  mov     rsi, rdx
0x1800104ad  cmp     ecx, 1
0x1800104b0  jnz     loc_18001059D
0x1800104b6  movzx   eax, byte ptr [rdi+8]
0x1800104ba  mov     [rdx+8], al
0x1800104bd  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x1800104c2  cmp     cs:gWfpTrackHeapBytes, 0
0x1800104c9  jnz     loc_18001098A
0x1800104cf  mov     rcx, cs:gWfpHeap; hHeap
0x1800104d6  mov     r8, rdi; lpMem
0x1800104d9  xor     edx, edx; dwFlags
0x1800104db  call    cs:__imp_HeapFree
0x1800104e2  nop     dword ptr [rax+rax+00h]
0x1800104e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104ee  lea     rdi, aBfefwpbyteblob; "BfeFwpByteBlobCopy"
0x1800104f5  cmp     rcx, rbp
0x1800104f8  jz      short loc_180010527
0x1800104fa  cmp     byte ptr [rcx+19h], 2
0x1800104fe  jb      short loc_180010527
0x180010500  test    byte ptr [rcx+1Ch], 1
0x180010504  jz      short loc_180010527
0x180010506  mov     rcx, [rcx+10h]
0x18001050a  mov     edx, 1Ah
0x18001050f  mov     [rsp+98h+var_70], ebx
0x180010513  xor     r9d, r9d
0x180010516  mov     [rsp+98h+var_78], rdi
0x18001051b  call    WPP_SF_Ssd
0x180010520  mov     rcx, cs:WPP_GLOBAL_Control
0x180010527  cmp     cs:gWfpLogUserModeErrors, 0
0x18001052e  jnz     loc_180010836
0x180010534  test    rbx, rbx
0x180010537  jz      short def_1800105D2; jumptable 00000001800105D2 default case
0x180010539  lea     rdi, aBfefwpconditio; "BfeFwpConditionValueCopyInner"
0x180010540  cmp     rcx, rbp
0x180010543  jz      short loc_18001056B
0x180010545  cmp     byte ptr [rcx+19h], 2
0x180010549  jb      short loc_18001056B
0x18001054b  test    byte ptr [rcx+1Ch], 1
0x18001054f  jz      short loc_18001056B
0x180010551  mov     rcx, [rcx+10h]
0x180010555  mov     edx, 1Ah
0x18001055a  mov     [rsp+98h+var_70], ebx
0x18001055e  xor     r9d, r9d
0x180010561  mov     [rsp+98h+var_78], rdi
0x180010566  call    WPP_SF_Ssd
0x18001056b  cmp     cs:gWfpLogUserModeErrors, 0
0x180010572  jnz     loc_1800106A0
0x180010578  mov     rax, rbx; jumptable 00000001800105D2 default case
0x18001057b  mov     rcx, [rsp+98h+var_30]
0x180010580  xor     rcx, rsp; StackCookie
0x180010583  call    __security_check_cookie
0x180010588  mov     rbx, [rsp+98h+arg_10]
0x180010590  add     rsp, 70h
0x180010594  pop     r15
0x180010596  pop     r14
0x180010598  pop     rdi
0x180010599  pop     rsi
0x18001059a  pop     rbp
0x18001059b  retn
0x18001059d  lea     rbp, WPP_GLOBAL_Control
0x1800105a4  cmp     ecx, 100h
0x1800105aa  jg      loc_180010737
0x1800105b0  jz      loc_1800108AD
0x1800105b6  add     ecx, 0FFFFFFFEh; switch 17 cases
0x1800105b9  cmp     ecx, 10h
0x1800105bc  ja      short def_1800105D2; jumptable 00000001800105D2 default case
0x1800105be  movsxd  rax, ecx
0x1800105c1  lea     rdx, __ImageBase
0x1800105c8  mov     ecx, ds:(jpt_1800105D2 - 180000000h)[rdx+rax*4]
0x1800105cf  add     rcx, rdx
0x1800105d2  jmp     rcx; switch jump
0x1800105d8  mov     r15, [rdi+8]; jumptable 00000001800105D2 cases 12,14,16
0x1800105dc  mov     [rsp+98h+var_68], rbx
0x1800105e1  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x1800105e6  xor     edx, edx; dwFlags
0x1800105e8  test    eax, eax
0x1800105ea  jnz     loc_180010707
0x1800105f0  mov     rcx, cs:gWfpHeap; hHeap
0x1800105f7  mov     r8d, 10h; dwBytes
0x1800105fd  call    cs:__imp_HeapAlloc
0x180010604  nop     dword ptr [rax+rax+00h]
0x180010609  mov     [rsp+98h+var_68], rax
0x18001060e  mov     rdi, rax
0x180010611  test    rax, rax
0x180010614  jz      loc_1800109B9
0x18001061a  cmp     cs:gWfpTrackHeapBytes, ebx
0x180010620  jnz     loc_180010B43
0x180010626  test    rbx, rbx
0x180010629  jnz     loc_1800107A7
0x18001062f  mov     eax, [r15]
0x180010632  mov     [rdi], eax
0x180010634  test    eax, eax
0x180010636  jz      loc_18001095B
0x18001063c  mov     ebx, eax
0x18001063e  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180010643  xor     edx, edx; dwFlags
0x180010645  test    eax, eax
0x180010647  jnz     loc_180010723
0x18001064d  mov     rcx, cs:gWfpHeap; hHeap
0x180010654  mov     r8d, ebx; dwBytes
0x180010657  call    cs:__imp_HeapAlloc
0x18001065e  nop     dword ptr [rax+rax+00h]
0x180010663  mov     [rdi+8], rax
0x180010667  test    rax, rax
0x18001066a  jz      loc_1800109EB
0x180010670  xor     ebx, ebx
0x180010672  cmp     cs:gWfpTrackHeapBytes, ebx
0x180010678  jnz     loc_180010B67
0x18001067e  test    rbx, rbx
0x180010681  jnz     loc_1800107A7
0x180010687  mov     r8d, [rdi]; Size
0x18001068a  mov     rdx, [r15+8]; Src
0x18001068e  mov     rcx, [rdi+8]; void *
0x180010692  call    memcpy_0
0x180010697  mov     [rsi+8], rdi
0x18001069b  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x1800106a0  test    cs:byte_1800F6115, 1
0x1800106a7  jz      def_1800105D2; jumptable 00000001800105D2 default case
0x1800106ad  lea     rax, [rsp+98h+var_68]
0x1800106b2  mov     dword ptr [rsp+98h+var_68], ebx
0x1800106b6  mov     [rsp+98h+var_40], rax
0x1800106bb  lea     rdx, WFP_USERMODE_ERROR
0x1800106c2  lea     rax, [rsp+98h+var_60]
0x1800106c7  mov     [rsp+98h+var_50], rdi
0x1800106cc  mov     r9d, 3
0x1800106d2  mov     [rsp+98h+var_78], rax
0x1800106d7  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800106de  mov     [rsp+98h+var_48], 1Eh
0x1800106e7  mov     [rsp+98h+var_38], 4
0x1800106f0  call    McGenEventWrite_EtwEventWriteTransfer
0x1800106f5  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x1800106fa  movzx   eax, word ptr [rdi+8]; jumptable 00000001800105D2 cases 2,6
0x1800106fe  mov     [rsi+8], ax
0x180010702  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x180010707  lea     r8, [rsp+98h+var_68]
0x18001070c  mov     ecx, 10h; dwBytes
0x180010711  call    WfpMemAlloc25B
0x180010716  mov     rdi, [rsp+98h+var_68]
0x18001071b  mov     rbx, rax
0x18001071e  jmp     loc_180010626
0x180010723  lea     r8, [rdi+8]
0x180010727  mov     rcx, rbx; dwBytes
0x18001072a  call    WfpMemAlloc25B
0x18001072f  mov     rbx, rax
0x180010732  jmp     loc_18001067E
0x180010737  sub     ecx, 101h
0x18001073d  jnz     loc_180010901
0x180010743  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180010748  xor     edx, edx; dwFlags
0x18001074a  test    eax, eax
0x18001074c  jnz     loc_180010820
0x180010752  mov     rcx, cs:gWfpHeap; hHeap
0x180010759  mov     r8d, 11h; dwBytes
0x18001075f  call    cs:__imp_HeapAlloc
0x180010766  nop     dword ptr [rax+rax+00h]
0x18001076b  mov     [rsi+8], rax
0x18001076f  test    rax, rax
0x180010772  jz      loc_180010A1D
0x180010778  cmp     cs:gWfpTrackHeapBytes, ebx
0x18001077e  jnz     loc_180010BBC
0x180010784  test    rbx, rbx
0x180010787  jnz     loc_1800108C9
0x18001078d  mov     rax, [rdi+8]
0x180010791  mov     rcx, [rsi+8]
0x180010795  movups  xmm0, xmmword ptr [rax]
0x180010798  movups  xmmword ptr [rcx], xmm0
0x18001079b  movzx   eax, byte ptr [rax+10h]
0x18001079f  mov     [rcx+10h], al
0x1800107a2  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x1800107a7  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x1800107ac  test    eax, eax
0x1800107ae  jz      loc_1800104C2
0x1800107b4  lea     rcx, [rsp+98h+var_68]
0x1800107b9  call    WfpMemFree25B
0x1800107be  jmp     loc_1800104E7
0x1800107c3  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline; jumptable 00000001800105D2 case 4
0x1800107c8  xor     edx, edx; dwFlags
0x1800107ca  test    eax, eax
0x1800107cc  jnz     loc_180010897
0x1800107d2  mov     rcx, cs:gWfpHeap; hHeap
0x1800107d9  mov     r8d, 8; dwBytes
0x1800107df  call    cs:__imp_HeapAlloc
0x1800107e6  nop     dword ptr [rax+rax+00h]
0x1800107eb  mov     [rsi+8], rax
0x1800107ef  test    rax, rax
0x1800107f2  jz      loc_180010A4F
0x1800107f8  cmp     cs:gWfpTrackHeapBytes, ebx
0x1800107fe  jnz     loc_180010A8C
0x180010804  test    rbx, rbx
0x180010807  jnz     loc_1800108C9
0x18001080d  mov     rax, [rdi+8]
0x180010811  mov     rcx, [rsi+8]
0x180010815  mov     rax, [rax]
0x180010818  mov     [rcx], rax
0x18001081b  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x180010820  lea     r8, [rsi+8]
0x180010824  mov     ecx, 11h; dwBytes
0x180010829  call    WfpMemAlloc25B
0x18001082e  mov     rbx, rax
0x180010831  jmp     loc_180010784
0x180010836  test    cs:byte_1800F6115, 1
0x18001083d  jz      loc_180010534
0x180010843  lea     rax, [rsp+98h+var_68]
0x180010848  mov     dword ptr [rsp+98h+var_68], ebx
0x18001084c  mov     [rsp+98h+var_40], rax
0x180010851  lea     rdx, WFP_USERMODE_ERROR
0x180010858  lea     rax, [rsp+98h+var_60]
0x18001085d  mov     [rsp+98h+var_50], rdi
0x180010862  mov     r9d, 3
0x180010868  mov     [rsp+98h+var_78], rax
0x18001086d  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180010874  mov     [rsp+98h+var_48], 13h
0x18001087d  mov     [rsp+98h+var_38], 4
0x180010886  call    McGenEventWrite_EtwEventWriteTransfer
0x18001088b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010892  jmp     loc_180010534
0x180010897  lea     r8, [rsi+8]
0x18001089b  mov     ecx, 8; dwBytes
0x1800108a0  call    WfpMemAlloc25B
0x1800108a5  mov     rbx, rax
0x1800108a8  jmp     loc_180010804
0x1800108ad  lea     r8, [rdx+8]
0x1800108b1  mov     ecx, 8; dwBytes
0x1800108b6  xor     edx, edx; dwFlags
0x1800108b8  call    WfpMemAlloc
0x1800108bd  mov     rbx, rax
0x1800108c0  test    rax, rax
0x1800108c3  jz      loc_180010BA9
0x1800108c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108d0  jmp     loc_180010539
0x1800108d5  mov     rcx, [rdi+8]; jumptable 00000001800105D2 case 13
0x1800108d9  call    cs:__imp_RtlLengthSid
0x1800108e0  nop     dword ptr [rax+rax+00h]
0x1800108e5  mov     rcx, [rdi+8]; Src
0x1800108e9  lea     r9, [rsi+8]
0x1800108ed  mov     edx, eax; dwBytes
0x1800108ef  call    WfpBufferCopy
0x1800108f4  mov     rbx, rax
0x1800108f7  test    rax, rax
0x1800108fa  jnz     short loc_1800108C9
0x1800108fc  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x180010901  cmp     ecx, 1
0x180010904  jnz     def_1800105D2; jumptable 00000001800105D2 default case
0x18001090a  mov     rcx, [rdi+8]
0x18001090e  add     rdx, 8
0x180010912  call    BfeFwpRangeCopy
0x180010917  mov     rbx, rax
0x18001091a  test    rax, rax
0x18001091d  jnz     short loc_1800108C9
0x18001091f  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x180010924  lea     r8, [rsi+8]; jumptable 00000001800105D2 case 11
0x180010928  xor     edx, edx; dwFlags
0x18001092a  mov     ecx, 10h; dwBytes
0x18001092f  call    WfpMemAlloc
0x180010934  mov     rbx, rax
0x180010937  test    rax, rax
0x18001093a  jnz     short loc_1800108C9
0x18001093c  mov     rax, [rdi+8]
0x180010940  mov     rcx, [rsi+8]
0x180010944  movups  xmm0, xmmword ptr [rax]
0x180010947  movups  xmmword ptr [rcx], xmm0
0x18001094a  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x18001094f  movzx   eax, byte ptr [rdi+8]; jumptable 00000001800105D2 case 5
0x180010953  mov     [rsi+8], al
0x180010956  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x18001095b  mov     qword ptr [rdi+8], 0
0x180010963  mov     [rsi+8], rdi
0x180010967  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x18001096c  mov     rcx, [rdi+8]; jumptable 00000001800105D2 case 15
0x180010970  lea     rdx, [rsi+8]
0x180010974  call    BfeFwpTokenInformationCopy
0x180010979  mov     rbx, rax
0x18001097c  test    rax, rax
0x18001097f  jnz     loc_1800108C9
0x180010985  jmp     def_1800105D2; jumptable 00000001800105D2 default case
0x18001098a  test    rdi, rdi
0x18001098d  jz      loc_1800104CF
0x180010993  mov     rcx, cs:gWfpHeap; hHeap
0x18001099a  mov     r8, rdi; lpMem
0x18001099d  xor     edx, edx; dwFlags
0x18001099f  call    cs:__imp_HeapSize
0x1800109a6  nop     dword ptr [rax+rax+00h]
0x1800109ab  neg     eax
0x1800109ad  lock add cs:gWfpHeapBytesAllocated, eax
0x1800109b4  jmp     loc_1800104CF
  ... truncated ...
```
