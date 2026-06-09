# BfeFwpConditionValueCopyInner

- ea: `0x18000fad0`
- end: `0x180010230`
- name: `BfeFwpConditionValueCopyInner`
- size: `1888`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f200`
- `0x180010ba0`
- `0x180013480`
- `0x18003aa24`

## callees

- `0x18000f1a8`
- `0x18000fad0`
- `0x180010ad0`
- `0x180012400`
- `0x180012b54`
- `0x180018b74`
- `0x180022730`
- `0x18002f724`
- `0x18003a8f4`
- `0x18004e230`
- `0x1800540ec`
- `0x1800542bc`
- `0x1800570a0`
- `0x180058b30`
- `0x180087dcc`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000ff06`
- `ntdll!RtlLengthSid` at `0x18000ff06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fe12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fc96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fe12`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000ffc6`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800100b9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001016a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010188`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800101d7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000ffc6`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800100b9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001016a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180010188`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800101d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb2b`

## string_xrefs

- `0x18000fb83`: `BfeFwpConditionValueCopyInner`
- `0x18000fb38`: `BfeFwpByteBlobCopy`

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
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
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
          if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
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
0x18000fad0  mov     [rsp+arg_10], rbx
0x18000fad5  push    rbp
0x18000fad6  push    rsi
0x18000fad7  push    rdi
0x18000fad8  push    r14
0x18000fada  push    r15
0x18000fadc  sub     rsp, 70h
0x18000fae0  mov     rax, cs:__security_cookie
0x18000fae7  xor     rax, rsp
0x18000faea  mov     [rsp+98h+var_30], rax
0x18000faef  mov     eax, [rcx]
0x18000faf1  mov     rdi, rcx
0x18000faf4  mov     [rdx], eax
0x18000faf6  xor     ebx, ebx
0x18000faf8  mov     ecx, [rcx]
0x18000fafa  mov     rsi, rdx
0x18000fafd  cmp     ecx, 1
0x18000fb00  jnz     loc_18000FBE6
0x18000fb06  movzx   eax, byte ptr [rdi+8]
0x18000fb0a  mov     [rdx+8], al
0x18000fb0d  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fb12  cmp     cs:gWfpTrackHeapBytes, 0
0x18000fb19  jnz     loc_18000FFB1
0x18000fb1f  mov     rcx, cs:gWfpHeap; hHeap
0x18000fb26  mov     r8, rdi; lpMem
0x18000fb29  xor     edx, edx; dwFlags
0x18000fb2b  call    cs:__imp_HeapFree
0x18000fb31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb38  lea     rdi, aBfefwpbyteblob; "BfeFwpByteBlobCopy"
0x18000fb3f  cmp     rcx, rbp
0x18000fb42  jz      short loc_18000FB71
0x18000fb44  cmp     byte ptr [rcx+19h], 2
0x18000fb48  jb      short loc_18000FB71
0x18000fb4a  test    byte ptr [rcx+1Ch], 1
0x18000fb4e  jz      short loc_18000FB71
0x18000fb50  mov     rcx, [rcx+10h]
0x18000fb54  mov     edx, 1Ah
0x18000fb59  mov     [rsp+98h+var_70], ebx
0x18000fb5d  xor     r9d, r9d
0x18000fb60  mov     [rsp+98h+var_78], rdi
0x18000fb65  call    WPP_SF_Ssd
0x18000fb6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb71  cmp     cs:gWfpLogUserModeErrors, 0
0x18000fb78  jnz     loc_18000FE63
0x18000fb7e  test    rbx, rbx
0x18000fb81  jz      short def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fb83  lea     rdi, aBfefwpconditio; "BfeFwpConditionValueCopyInner"
0x18000fb8a  cmp     rcx, rbp
0x18000fb8d  jz      short loc_18000FBB5
0x18000fb8f  cmp     byte ptr [rcx+19h], 2
0x18000fb93  jb      short loc_18000FBB5
0x18000fb95  test    byte ptr [rcx+1Ch], 1
0x18000fb99  jz      short loc_18000FBB5
0x18000fb9b  mov     rcx, [rcx+10h]
0x18000fb9f  mov     edx, 1Ah
0x18000fba4  mov     [rsp+98h+var_70], ebx
0x18000fba8  xor     r9d, r9d
0x18000fbab  mov     [rsp+98h+var_78], rdi
0x18000fbb0  call    WPP_SF_Ssd
0x18000fbb5  cmp     cs:gWfpLogUserModeErrors, 0
0x18000fbbc  jnz     loc_18000FCD9
0x18000fbc2  mov     rax, rbx; jumptable 000000018000FC1B default case
0x18000fbc5  mov     rcx, [rsp+98h+var_30]
0x18000fbca  xor     rcx, rsp; StackCookie
0x18000fbcd  call    __security_check_cookie
0x18000fbd2  mov     rbx, [rsp+98h+arg_10]
0x18000fbda  add     rsp, 70h
0x18000fbde  pop     r15
0x18000fbe0  pop     r14
0x18000fbe2  pop     rdi
0x18000fbe3  pop     rsi
0x18000fbe4  pop     rbp
0x18000fbe5  retn
0x18000fbe6  lea     rbp, WPP_GLOBAL_Control
0x18000fbed  cmp     ecx, 100h
0x18000fbf3  jg      loc_18000FD70
0x18000fbf9  jz      loc_18000FEDA
0x18000fbff  add     ecx, 0FFFFFFFEh; switch 17 cases
0x18000fc02  cmp     ecx, 10h
0x18000fc05  ja      short def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fc07  movsxd  rax, ecx
0x18000fc0a  lea     rdx, __ImageBase
0x18000fc11  mov     ecx, ds:(jpt_18000FC1B - 180000000h)[rdx+rax*4]
0x18000fc18  add     rcx, rdx
0x18000fc1b  jmp     rcx; switch jump
0x18000fc1d  mov     r15, [rdi+8]; jumptable 000000018000FC1B cases 12,14,16
0x18000fc21  mov     [rsp+98h+var_68], rbx
0x18000fc26  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000fc2b  xor     edx, edx; dwFlags
0x18000fc2d  test    eax, eax
0x18000fc2f  jnz     loc_18000FD40
0x18000fc35  mov     rcx, cs:gWfpHeap; hHeap
0x18000fc3c  mov     r8d, 10h; dwBytes
0x18000fc42  call    cs:__imp_HeapAlloc
0x18000fc48  mov     [rsp+98h+var_68], rax
0x18000fc4d  mov     rdi, rax
0x18000fc50  test    rax, rax
0x18000fc53  jz      loc_18000FFDA
0x18000fc59  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000fc5f  jnz     loc_18001015E
0x18000fc65  test    rbx, rbx
0x18000fc68  jnz     loc_18000FDDA
0x18000fc6e  mov     eax, [r15]
0x18000fc71  mov     [rdi], eax
0x18000fc73  test    eax, eax
0x18000fc75  jz      loc_18000FF82
0x18000fc7b  mov     ebx, eax
0x18000fc7d  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000fc82  xor     edx, edx; dwFlags
0x18000fc84  test    eax, eax
0x18000fc86  jnz     loc_18000FD5C
0x18000fc8c  mov     rcx, cs:gWfpHeap; hHeap
0x18000fc93  mov     r8d, ebx; dwBytes
0x18000fc96  call    cs:__imp_HeapAlloc
0x18000fc9c  mov     [rdi+8], rax
0x18000fca0  test    rax, rax
0x18000fca3  jz      loc_18001000C
0x18000fca9  xor     ebx, ebx
0x18000fcab  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000fcb1  jnz     loc_18001017C
0x18000fcb7  test    rbx, rbx
0x18000fcba  jnz     loc_18000FDDA
0x18000fcc0  mov     r8d, [rdi]; Size
0x18000fcc3  mov     rdx, [r15+8]; Src
0x18000fcc7  mov     rcx, [rdi+8]; void *
0x18000fccb  call    memcpy_0
0x18000fcd0  mov     [rsi+8], rdi
0x18000fcd4  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fcd9  test    cs:byte_1800F30F5, 1
0x18000fce0  jz      def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fce6  lea     rax, [rsp+98h+var_68]
0x18000fceb  mov     dword ptr [rsp+98h+var_68], ebx
0x18000fcef  mov     [rsp+98h+var_40], rax
0x18000fcf4  lea     rdx, WFP_USERMODE_ERROR
0x18000fcfb  lea     rax, [rsp+98h+var_60]
0x18000fd00  mov     [rsp+98h+var_50], rdi
0x18000fd05  mov     r9d, 3
0x18000fd0b  mov     [rsp+98h+var_78], rax
0x18000fd10  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000fd17  mov     [rsp+98h+var_48], 1Eh
0x18000fd20  mov     [rsp+98h+var_38], 4
0x18000fd29  call    McGenEventWrite_EtwEventWriteTransfer
0x18000fd2e  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fd33  movzx   eax, word ptr [rdi+8]; jumptable 000000018000FC1B cases 2,6
0x18000fd37  mov     [rsi+8], ax
0x18000fd3b  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fd40  lea     r8, [rsp+98h+var_68]
0x18000fd45  mov     ecx, 10h; dwBytes
0x18000fd4a  call    WfpMemAlloc25B
0x18000fd4f  mov     rdi, [rsp+98h+var_68]
0x18000fd54  mov     rbx, rax
0x18000fd57  jmp     loc_18000FC65
0x18000fd5c  lea     r8, [rdi+8]
0x18000fd60  mov     rcx, rbx; dwBytes
0x18000fd63  call    WfpMemAlloc25B
0x18000fd68  mov     rbx, rax
0x18000fd6b  jmp     loc_18000FCB7
0x18000fd70  sub     ecx, 101h
0x18000fd76  jnz     loc_18000FF28
0x18000fd7c  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000fd81  xor     edx, edx; dwFlags
0x18000fd83  test    eax, eax
0x18000fd85  jnz     loc_18000FE4D
0x18000fd8b  mov     rcx, cs:gWfpHeap; hHeap
0x18000fd92  mov     r8d, 11h; dwBytes
0x18000fd98  call    cs:__imp_HeapAlloc
0x18000fd9e  mov     [rsi+8], rax
0x18000fda2  test    rax, rax
0x18000fda5  jz      loc_18001003E
0x18000fdab  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000fdb1  jnz     loc_1800101CB
0x18000fdb7  test    rbx, rbx
0x18000fdba  jnz     loc_18000FEF6
0x18000fdc0  mov     rax, [rdi+8]
0x18000fdc4  mov     rcx, [rsi+8]
0x18000fdc8  movups  xmm0, xmmword ptr [rax]
0x18000fdcb  movups  xmmword ptr [rcx], xmm0
0x18000fdce  movzx   eax, byte ptr [rax+10h]
0x18000fdd2  mov     [rcx+10h], al
0x18000fdd5  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fdda  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000fddf  test    eax, eax
0x18000fde1  jz      loc_18000FB12
0x18000fde7  lea     rcx, [rsp+98h+var_68]
0x18000fdec  call    WfpMemFree25B
0x18000fdf1  jmp     loc_18000FB31
0x18000fdf6  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline; jumptable 000000018000FC1B case 4
0x18000fdfb  xor     edx, edx; dwFlags
0x18000fdfd  test    eax, eax
0x18000fdff  jnz     loc_18000FEC4
0x18000fe05  mov     rcx, cs:gWfpHeap; hHeap
0x18000fe0c  mov     r8d, 8; dwBytes
0x18000fe12  call    cs:__imp_HeapAlloc
0x18000fe18  mov     [rsi+8], rax
0x18000fe1c  test    rax, rax
0x18000fe1f  jz      loc_180010070
0x18000fe25  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000fe2b  jnz     loc_1800100AD
0x18000fe31  test    rbx, rbx
0x18000fe34  jnz     loc_18000FEF6
0x18000fe3a  mov     rax, [rdi+8]
0x18000fe3e  mov     rcx, [rsi+8]
0x18000fe42  mov     rax, [rax]
0x18000fe45  mov     [rcx], rax
0x18000fe48  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000fe4d  lea     r8, [rsi+8]
0x18000fe51  mov     ecx, 11h; dwBytes
0x18000fe56  call    WfpMemAlloc25B
0x18000fe5b  mov     rbx, rax
0x18000fe5e  jmp     loc_18000FDB7
0x18000fe63  test    cs:byte_1800F30F5, 1
0x18000fe6a  jz      loc_18000FB7E
0x18000fe70  lea     rax, [rsp+98h+var_68]
0x18000fe75  mov     dword ptr [rsp+98h+var_68], ebx
0x18000fe79  mov     [rsp+98h+var_40], rax
0x18000fe7e  lea     rdx, WFP_USERMODE_ERROR
0x18000fe85  lea     rax, [rsp+98h+var_60]
0x18000fe8a  mov     [rsp+98h+var_50], rdi
0x18000fe8f  mov     r9d, 3
0x18000fe95  mov     [rsp+98h+var_78], rax
0x18000fe9a  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000fea1  mov     [rsp+98h+var_48], 13h
0x18000feaa  mov     [rsp+98h+var_38], 4
0x18000feb3  call    McGenEventWrite_EtwEventWriteTransfer
0x18000feb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000febf  jmp     loc_18000FB7E
0x18000fec4  lea     r8, [rsi+8]
0x18000fec8  mov     ecx, 8; dwBytes
0x18000fecd  call    WfpMemAlloc25B
0x18000fed2  mov     rbx, rax
0x18000fed5  jmp     loc_18000FE31
0x18000feda  lea     r8, [rdx+8]
0x18000fede  mov     ecx, 8; dwBytes
0x18000fee3  xor     edx, edx; dwFlags
0x18000fee5  call    WfpMemAlloc
0x18000feea  mov     rbx, rax
0x18000feed  test    rax, rax
0x18000fef0  jz      loc_1800101B8
0x18000fef6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fefd  jmp     loc_18000FB83
0x18000ff02  mov     rcx, [rdi+8]; jumptable 000000018000FC1B case 13
0x18000ff06  call    cs:__imp_RtlLengthSid
0x18000ff0c  mov     rcx, [rdi+8]; Src
0x18000ff10  lea     r9, [rsi+8]
0x18000ff14  mov     edx, eax; dwBytes
0x18000ff16  call    WfpBufferCopy
0x18000ff1b  mov     rbx, rax
0x18000ff1e  test    rax, rax
0x18000ff21  jnz     short loc_18000FEF6
0x18000ff23  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000ff28  cmp     ecx, 1
0x18000ff2b  jnz     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000ff31  mov     rcx, [rdi+8]
0x18000ff35  add     rdx, 8
0x18000ff39  call    BfeFwpRangeCopy
0x18000ff3e  mov     rbx, rax
0x18000ff41  test    rax, rax
0x18000ff44  jnz     short loc_18000FEF6
0x18000ff46  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000ff4b  lea     r8, [rsi+8]; jumptable 000000018000FC1B case 11
0x18000ff4f  xor     edx, edx; dwFlags
0x18000ff51  mov     ecx, 10h; dwBytes
0x18000ff56  call    WfpMemAlloc
0x18000ff5b  mov     rbx, rax
0x18000ff5e  test    rax, rax
0x18000ff61  jnz     short loc_18000FEF6
0x18000ff63  mov     rax, [rdi+8]
0x18000ff67  mov     rcx, [rsi+8]
0x18000ff6b  movups  xmm0, xmmword ptr [rax]
0x18000ff6e  movups  xmmword ptr [rcx], xmm0
0x18000ff71  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000ff76  movzx   eax, byte ptr [rdi+8]; jumptable 000000018000FC1B case 5
0x18000ff7a  mov     [rsi+8], al
0x18000ff7d  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000ff82  mov     qword ptr [rdi+8], 0
0x18000ff8a  mov     [rsi+8], rdi
0x18000ff8e  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000ff93  mov     rcx, [rdi+8]; jumptable 000000018000FC1B case 15
0x18000ff97  lea     rdx, [rsi+8]
0x18000ff9b  call    BfeFwpTokenInformationCopy
0x18000ffa0  mov     rbx, rax
0x18000ffa3  test    rax, rax
0x18000ffa6  jnz     loc_18000FEF6
0x18000ffac  jmp     def_18000FC1B; jumptable 000000018000FC1B default case
0x18000ffb1  test    rdi, rdi
0x18000ffb4  jz      loc_18000FB1F
0x18000ffba  mov     rcx, cs:gWfpHeap; hHeap
0x18000ffc1  mov     r8, rdi; lpMem
0x18000ffc4  xor     edx, edx; dwFlags
0x18000ffc6  call    cs:__imp_HeapSize
0x18000ffcc  neg     eax
0x18000ffce  lock add cs:gWfpHeapBytesAllocated, eax
0x18000ffd5  jmp     loc_18000FB1F
0x18000ffda  mov     r8d, 0C0000017h
0x18000ffe0  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000ffe7  call    WfpReportSysErrorAsNtStatus
0x18000ffec  mov     rbx, rax
0x18000ffef  test    rax, rax
0x18000fff2  jz      loc_18000FC65
0x18000fff8  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
  ... truncated ...
```
