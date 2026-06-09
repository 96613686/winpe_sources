# IkeConstructVendor

- ea: `0x18001fc40`
- end: `0x1800203a1`
- name: `IkeConstructVendor`
- size: `1889`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fab0`
- `0x180046510`
- `0x180046ab0`
- `0x180049840`
- `0x1800fdb80`

## callees

- `0x180007630`
- `0x180008388`
- `0x1800096c0`
- `0x18001fc40`
- `0x180037e90`
- `0x18004882c`
- `0x180050850`
- `0x18005c3d0`
- `0x180110d3c`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fce5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fd2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fe4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fe85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fefb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ff40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002023c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020284`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fce5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fd2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fe4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fe85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001fefb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ff40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002023c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020284`
- `ntdll!EtwEventWriteTransfer` at `0x18001fdfb`
- `ntdll!EtwEventWriteTransfer` at `0x180020044`
- `ntdll!EtwEventWriteTransfer` at `0x180020360`
- `ntdll!EtwEventWriteTransfer` at `0x18001fdfb`
- `ntdll!EtwEventWriteTransfer` at `0x180020044`
- `ntdll!EtwEventWriteTransfer` at `0x180020360`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800201d0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800201d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020197`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800201eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020197`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800201eb`
- `WS2_32!__imp_htonl` at `0x180020113`
- `WS2_32!__imp_htonl` at `0x180020113`
- `WS2_32!__imp_htons` at `0x1800200b8`
- `WS2_32!__imp_htons` at `0x1800200b8`

## pseudocode

```c
__int64 __fastcall IkeConstructVendor(__int64 *a1, int a2, int a3, u_long a4, unsigned __int16 a5)
{
  __int64 v5; // r13
  __int64 v8; // rbx
  LPCRITICAL_SECTION v9; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v12; // rcx
  DWORD v13; // ecx
  char *v14; // rax
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  bool v17; // zf
  int v18; // eax
  _QWORD *v19; // rcx
  LPCRITICAL_SECTION v20; // rdx
  DWORD v21; // eax
  LPVOID v22; // rax
  LPVOID v23; // r8
  __int64 v24; // rdi
  DWORD v25; // eax
  __int64 *v26; // rax
  __int64 v27; // r9
  LPCRITICAL_SECTION v28; // rax
  DWORD v29; // ecx
  __int64 *v30; // rax
  __int64 v31; // rcx
  DWORD v32; // ecx
  char *v33; // rax
  const WCHAR *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  __int16 *v37; // rdx
  __int64 v38; // rax
  unsigned int v39; // eax
  char v40; // al
  __int64 VendorIdHash; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  void *v45; // r15
  __int64 v46; // r12
  int v47; // eax
  unsigned int v48; // edi
  int v49; // r14d
  u_long v50; // ecx
  u_long v51; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  BOOL v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  LPCRITICAL_SECTION v57; // rax
  DWORD v58; // ecx
  __int64 *v59; // rax
  __int64 v60; // rcx
  DWORD v61; // ecx
  char *v62; // rax
  const WCHAR *v63; // rdx
  int v64; // ebx
  int v67; // [rsp+38h] [rbp-79h]
  void *Src[2]; // [rsp+40h] [rbp-71h] BYREF
  __int64 v69; // [rsp+50h] [rbp-61h] BYREF
  int v70; // [rsp+58h] [rbp-59h] BYREF
  int v71; // [rsp+5Ch] [rbp-55h]
  __int64 v72; // [rsp+60h] [rbp-51h]
  char *v73; // [rsp+70h] [rbp-41h] BYREF
  int v74; // [rsp+78h] [rbp-39h]
  int v75; // [rsp+7Ch] [rbp-35h]
  int *v76; // [rsp+80h] [rbp-31h]
  int v77; // [rsp+88h] [rbp-29h]
  int v78; // [rsp+8Ch] [rbp-25h]
  __int64 *v79; // [rsp+90h] [rbp-21h]
  __int64 v80; // [rsp+98h] [rbp-19h]
  const WCHAR *v81; // [rsp+A0h] [rbp-11h]
  int v82; // [rsp+A8h] [rbp-9h]
  int v83; // [rsp+ACh] [rbp-5h]
  const char *v84; // [rsp+B0h] [rbp-1h]
  __int64 v85; // [rsp+B8h] [rbp+7h]

  v5 = a2;
  LOWORD(v67) = 0;
  v8 = -1;
  *(_OWORD *)Src = 0;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v9 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v9 = gIkeExtGlobals;
LABEL_9:
    v12 = 0;
    goto LABEL_10;
  }
  v12 = *Value;
  v9 = gIkeExtGlobals;
LABEL_10:
  v69 = v12;
  v79 = &v69;
  v80 = 8;
  if ( !v9 )
    goto LABEL_18;
  v13 = (DWORD)v9[86].LockSemaphore;
  if ( v13 == -1 )
    goto LABEL_18;
  v14 = (char *)TlsGetValue(v13);
  v15 = (const WCHAR *)(v14 + 8);
  if ( !v14 )
    v15 = 0;
  if ( v15 )
  {
    v16 = -1;
    do
      v17 = v15[++v16] == 0;
    while ( !v17 );
    v18 = 2 * v16 + 2;
  }
  else
  {
LABEL_18:
    v15 = &LocaleName;
    v18 = 2;
  }
  v82 = v18;
  v71 = 5;
  v73 = off_180173280;
  v81 = v15;
  v83 = 0;
  v84 = "IkeConstructVendor";
  v85 = 19;
  v70 = 184549376;
  v72 = 1;
  v74 = *(unsigned __int16 *)off_180173280;
  v76 = &dword_180166EA4;
  v75 = 2;
  v77 = 45;
  v78 = 1;
  EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
LABEL_20:
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v20 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v21 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v21 == -1) )
    {
      v23 = 0;
    }
    else
    {
      v22 = TlsGetValue(v21);
      v19 = WPP_GLOBAL_Control;
      v23 = v22;
      v20 = gIkeExtGlobals;
    }
    v24 = (__int64)v23 + 8;
    if ( !v23 )
      v24 = 0;
    if ( v20
      && (v25 = (DWORD)v20[86].LockSemaphore, v25 != -1)
      && (v26 = (__int64 *)TlsGetValue(v25), v19 = WPP_GLOBAL_Control, v26) )
    {
      v27 = *v26;
    }
    else
    {
      LODWORD(v27) = 0;
    }
    WPP_SF_iSs(
      v19[2],
      17,
      (unsigned int)WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids,
      v27,
      v24,
      vendorIdMapping[3 * v5 + 1]);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v28 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v29 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v29 != -1 )
      {
        v30 = (__int64 *)TlsGetValue(v29);
        if ( v30 )
        {
          v31 = *v30;
          v28 = gIkeExtGlobals;
LABEL_42:
          v69 = v31;
          v79 = &v69;
          v80 = 8;
          if ( !v28 )
            goto LABEL_50;
          v32 = (DWORD)v28[86].LockSemaphore;
          if ( v32 == -1 )
            goto LABEL_50;
          v33 = (char *)TlsGetValue(v32);
          v34 = (const WCHAR *)(v33 + 8);
          if ( !v33 )
            v34 = 0;
          if ( v34 )
          {
            v35 = -1;
            do
              v17 = v34[++v35] == 0;
            while ( !v17 );
            v36 = 2 * v35 + 2;
          }
          else
          {
LABEL_50:
            v34 = &LocaleName;
            v36 = 2;
          }
          v81 = v34;
          v82 = v36;
          v83 = 0;
          v37 = (__int16 *)vendorIdMapping[3 * v5 + 1];
          if ( v37 )
          {
            v38 = -1;
            do
              ++v38;
            while ( *((_BYTE *)v37 + v38) );
            v39 = v38 + 1;
          }
          else
          {
            v37 = word_180122432;
            v39 = 1;
          }
          v85 = v39;
          v71 = 4;
          v73 = off_180173280;
          v84 = (const char *)v37;
          v70 = 184549376;
          v72 = 0;
          v74 = *(unsigned __int16 *)off_180173280;
          v76 = &dword_1801646FC;
          v75 = 2;
          v77 = 56;
          v78 = 1;
          EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
          goto LABEL_57;
        }
        v28 = gIkeExtGlobals;
      }
    }
    v31 = 0;
    goto LABEL_42;
  }
LABEL_57:
  v40 = 43;
  if ( !a3 )
    v40 = 13;
  *(_BYTE *)(*a1 + *((unsigned __int16 *)a1 + 7)) = v40;
  VendorIdHash = IkeGetVendorIdHash((unsigned int)v5, Src);
  v45 = Src[1];
  v46 = VendorIdHash;
  if ( !VendorIdHash )
  {
    if ( (unsigned int)v5 <= 0xD && (v47 = 11265, _bittest(&v47, v5)) )
    {
      v48 = (unsigned int)Src[0];
      v49 = LODWORD(Src[0]) + 4;
    }
    else
    {
      v48 = (unsigned int)Src[0];
      v49 = (int)Src[0];
    }
    v46 = IkeExpandPacket(a1, (unsigned int)(v49 + 4));
    if ( !v46 )
    {
      *((_WORD *)a1 + 7) = *((_WORD *)a1 + 6);
      HIWORD(v67) = htons(v49 + 4);
      *(_DWORD *)(*((unsigned __int16 *)a1 + 6) + *a1) = v67;
      *((_WORD *)a1 + 6) += 4;
      memcpy_0((void *)(*a1 + *((unsigned __int16 *)a1 + 6)), v45, v48);
      *((_WORD *)a1 + 6) += v48;
      if ( (_DWORD)v5 )
      {
        if ( (_DWORD)v5 == 10 )
        {
          v50 = a4;
        }
        else
        {
          if ( (_DWORD)v5 != 11 )
            goto LABEL_72;
          v50 = (unsigned __int16)IkeMMDhInternalToDoi(a5, v42, v44);
        }
      }
      else
      {
        v50 = 9;
      }
      v51 = htonl(v50);
      v42 = *((unsigned __int16 *)a1 + 6);
      v43 = *a1;
      *(_DWORD *)(v42 + *a1) = v51;
      *((_WORD *)a1 + 6) += 4;
    }
  }
LABEL_72:
  if ( v45 )
  {
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( gWfpTrackHeapAllocs && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
      {
        if ( !gMisalignedHeapTelemFired )
        {
          if ( gWfpNumHeapAllocs <= 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v43, v42, v44);
          gMisalignedHeapTelemFired = 1;
        }
        _InterlockedIncrement(&gWfpNumHeapAllocs);
      }
      else
      {
        v53 = HeapFree(gWfpHeap, 0, v45);
        if ( !gHeapFreeFailedFired && !v53 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v55, v54, v56);
          gHeapFreeFailedFired = 1;
        }
      }
    }
    else
    {
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v45));
      HeapFree(gWfpHeap, 0, v45);
    }
  }
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v57 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v58 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v58 != -1 )
      {
        v59 = (__int64 *)TlsGetValue(v58);
        if ( v59 )
        {
          v60 = *v59;
          v57 = gIkeExtGlobals;
LABEL_99:
          v69 = v60;
          v79 = &v69;
          v80 = 8;
          if ( !v57 )
            goto LABEL_106;
          v61 = (DWORD)v57[86].LockSemaphore;
          if ( v61 == -1 )
            goto LABEL_106;
          v62 = (char *)TlsGetValue(v61);
          v63 = (const WCHAR *)(v62 + 8);
          if ( !v62 )
            v63 = 0;
          if ( v63 )
          {
            do
              v17 = v63[++v8] == 0;
            while ( !v17 );
            v64 = 2 * v8 + 2;
          }
          else
          {
LABEL_106:
            v63 = &LocaleName;
            v64 = 2;
          }
          v71 = 5;
          v73 = off_180173280;
          v82 = v64;
          v81 = v63;
          v83 = 0;
          v84 = "IkeConstructVendor";
          v85 = 19;
          v70 = 184549376;
          v72 = 1;
          v74 = *(unsigned __int16 *)off_180173280;
          v76 = (int *)byte_180166E6B;
          v75 = 2;
          v77 = 45;
          v78 = 1;
          EtwEventWriteTransfer(qword_180173298, &v70, 0, 0, 5, &v73);
          return IkeReturnError(v46, "IkeConstructVendor");
        }
        v57 = gIkeExtGlobals;
      }
    }
    v60 = 0;
    goto LABEL_99;
  }
  return IkeReturnError(v46, "IkeConstructVendor");
}

```

## disassembly

```asm
0x18001fc40  mov     [rsp-8+arg_10], rbx
0x18001fc45  push    rbp
0x18001fc46  push    rsi
0x18001fc47  push    rdi
0x18001fc48  push    r12
0x18001fc4a  push    r13
0x18001fc4c  push    r14
0x18001fc4e  push    r15
0x18001fc50  lea     rbp, [rsp-1Fh]
0x18001fc55  sub     rsp, 0D0h
0x18001fc5c  mov     rax, cs:__security_cookie
0x18001fc63  xor     rax, rsp
0x18001fc66  mov     [rbp+4Fh+var_40], rax
0x18001fc6a  mov     eax, cs:dword_180173278
0x18001fc70  lea     r12, aIkeconstructve; "IkeConstructVendor"
0x18001fc77  xor     r15d, r15d
0x18001fc7a  mov     [rbp+4Fh+var_CC], r9d
0x18001fc7e  movsxd  r13, edx
0x18001fc81  xorps   xmm0, xmm0
0x18001fc84  mov     [rbp+4Fh+var_C8], r15d
0x18001fc88  mov     r14d, r8d
0x18001fc8b  lea     rdi, _TraceLoggingMetadataEnd
0x18001fc92  mov     rsi, rcx
0x18001fc95  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001fc9c  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x18001fca0  cmp     eax, 5
0x18001fca3  jbe     loc_18001FE01
0x18001fca9  mov     rcx, cs:qword_180173290
0x18001fcb0  mov     rax, cs:qword_180173288
0x18001fcb7  test    al, 1
0x18001fcb9  jz      loc_18001FE01
0x18001fcbf  mov     rax, rcx
0x18001fcc2  and     eax, 1
0x18001fcc5  cmp     rax, rcx
0x18001fcc8  jnz     loc_18001FE01
0x18001fcce  mov     rax, cs:gIkeExtGlobals
0x18001fcd5  test    rax, rax
0x18001fcd8  jz      short loc_18001FD03
0x18001fcda  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001fce0  cmp     ecx, 0FFFFFFFFh
0x18001fce3  jz      short loc_18001FD03
0x18001fce5  call    cs:__imp_TlsGetValue
0x18001fceb  test    rax, rax
0x18001fcee  jz      short loc_18001FCFC
0x18001fcf0  mov     rcx, [rax]
0x18001fcf3  mov     rax, cs:gIkeExtGlobals
0x18001fcfa  jmp     short loc_18001FD06
0x18001fcfc  mov     rax, cs:gIkeExtGlobals
0x18001fd03  mov     rcx, r15
0x18001fd06  mov     [rbp+4Fh+var_B0], rcx
0x18001fd0a  lea     rcx, [rbp+4Fh+var_B0]
0x18001fd0e  mov     [rbp+4Fh+var_70], rcx
0x18001fd12  mov     [rbp+4Fh+var_68], 8
0x18001fd1a  test    rax, rax
0x18001fd1d  jz      short loc_18001FD58
0x18001fd1f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001fd25  cmp     ecx, 0FFFFFFFFh
0x18001fd28  jz      short loc_18001FD58
0x18001fd2a  call    cs:__imp_TlsGetValue
0x18001fd30  test    rax, rax
0x18001fd33  lea     rdx, [rax+8]
0x18001fd37  cmovz   rdx, r15
0x18001fd3b  test    rdx, rdx
0x18001fd3e  jz      short loc_18001FD58
0x18001fd40  mov     rax, rbx
0x18001fd43  cmp     [rdx+rax*2+2], r15w
0x18001fd49  lea     rax, [rax+1]
0x18001fd4d  jnz     short loc_18001FD43
0x18001fd4f  lea     eax, ds:2[rax*2]
0x18001fd56  jmp     short loc_18001FD64
0x18001fd58  lea     rdx, LocaleName
0x18001fd5f  mov     eax, 2
0x18001fd64  mov     [rbp+4Fh+var_58], eax
0x18001fd67  lea     rcx, _TraceLoggingMetadata
0x18001fd6e  movzx   eax, cs:word_180166E9A
0x18001fd75  xor     r9d, r9d
0x18001fd78  mov     [rbp+4Fh+var_A4], eax
0x18001fd7b  xor     r8d, r8d
0x18001fd7e  mov     rax, cs:off_180173280
0x18001fd85  mov     [rbp+4Fh+var_90], rax
0x18001fd89  mov     [rbp+4Fh+var_60], rdx
0x18001fd8d  lea     rdx, [rbp+4Fh+var_A8]
0x18001fd91  mov     [rbp+4Fh+var_54], r15d
0x18001fd95  mov     [rbp+4Fh+var_50], r12
0x18001fd99  mov     [rbp+4Fh+var_48], 13h
0x18001fda1  mov     [rbp+4Fh+var_A8], 0B000000h
0x18001fda8  mov     [rbp+4Fh+var_A0], 1
0x18001fdb0  movzx   eax, word ptr [rax]
0x18001fdb3  mov     [rbp+4Fh+var_88], eax
0x18001fdb6  lea     rax, dword_180166EA4
0x18001fdbd  mov     [rbp+4Fh+var_80], rax
0x18001fdc1  mov     rax, rdi
0x18001fdc4  sub     eax, ecx
0x18001fdc6  mov     [rbp+4Fh+var_84], 2
0x18001fdcd  mov     [rbp+4Fh+var_78], 2Dh ; '-'
0x18001fdd4  mov     [rbp+4Fh+var_74], 1
0x18001fddb  mov     [rsp+100h+var_D0], eax
0x18001fddf  mov     eax, [rsp+100h+var_D0]
0x18001fde3  mov     rcx, cs:qword_180173298
0x18001fdea  lea     rax, [rbp+4Fh+var_90]
0x18001fdee  mov     [rsp+100h+var_D8], rax
0x18001fdf3  mov     dword ptr [rsp+100h+var_E0], 5
0x18001fdfb  call    cs:__imp_EtwEventWriteTransfer
0x18001fe01  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe08  lea     rax, WPP_GLOBAL_Control
0x18001fe0f  lea     r12, vendorIdMapping
0x18001fe16  cmp     rcx, rax
0x18001fe19  jz      loc_18001FED5
0x18001fe1f  cmp     byte ptr [rcx+19h], 4
0x18001fe23  jb      loc_18001FED5
0x18001fe29  test    byte ptr [rcx+1Ch], 10h
0x18001fe2d  jz      loc_18001FED5
0x18001fe33  mov     rdx, cs:gIkeExtGlobals
0x18001fe3a  test    rdx, rdx
0x18001fe3d  jz      short loc_18001FE65
0x18001fe3f  mov     eax, [rdx+0D88h]
0x18001fe45  cmp     eax, 0FFFFFFFFh
0x18001fe48  jz      short loc_18001FE65
0x18001fe4a  mov     ecx, eax; dwTlsIndex
0x18001fe4c  call    cs:__imp_TlsGetValue
0x18001fe52  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe59  mov     r8, rax
0x18001fe5c  mov     rdx, cs:gIkeExtGlobals
0x18001fe63  jmp     short loc_18001FE68
0x18001fe65  mov     r8, r15
0x18001fe68  test    r8, r8
0x18001fe6b  lea     rdi, [r8+8]
0x18001fe6f  cmovz   rdi, r15
0x18001fe73  test    rdx, rdx
0x18001fe76  jz      short loc_18001FE9C
0x18001fe78  mov     eax, [rdx+0D88h]
0x18001fe7e  cmp     eax, 0FFFFFFFFh
0x18001fe81  jz      short loc_18001FE9C
0x18001fe83  mov     ecx, eax; dwTlsIndex
0x18001fe85  call    cs:__imp_TlsGetValue
0x18001fe8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe92  test    rax, rax
0x18001fe95  jz      short loc_18001FE9C
0x18001fe97  mov     r9, [rax]
0x18001fe9a  jmp     short loc_18001FE9F
0x18001fe9c  mov     r9, r15
0x18001fe9f  mov     rcx, [rcx+10h]
0x18001fea3  lea     rax, ds:0[r13*2]
0x18001feab  add     rax, r13
0x18001feae  lea     r8, WPP_654feddb4d903c5f7d7e848d4643eb5d_Traceguids
0x18001feb5  mov     edx, 11h
0x18001feba  mov     rax, [r12+rax*8+8]
0x18001febf  mov     [rsp+100h+var_D8], rax
0x18001fec4  mov     [rsp+100h+var_E0], rdi
0x18001fec9  call    WPP_SF_iSs
0x18001fece  lea     rdi, _TraceLoggingMetadataEnd
0x18001fed5  mov     eax, cs:dword_180173278
0x18001fedb  cmp     eax, 4
0x18001fede  jbe     loc_18002004A
0x18001fee4  mov     rax, cs:gIkeExtGlobals
0x18001feeb  test    rax, rax
0x18001feee  jz      short loc_18001FF19
0x18001fef0  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001fef6  cmp     ecx, 0FFFFFFFFh
0x18001fef9  jz      short loc_18001FF19
0x18001fefb  call    cs:__imp_TlsGetValue
0x18001ff01  test    rax, rax
0x18001ff04  jz      short loc_18001FF12
0x18001ff06  mov     rcx, [rax]
0x18001ff09  mov     rax, cs:gIkeExtGlobals
0x18001ff10  jmp     short loc_18001FF1C
0x18001ff12  mov     rax, cs:gIkeExtGlobals
0x18001ff19  mov     rcx, r15
0x18001ff1c  mov     [rbp+4Fh+var_B0], rcx
0x18001ff20  lea     rcx, [rbp+4Fh+var_B0]
0x18001ff24  mov     [rbp+4Fh+var_70], rcx
0x18001ff28  mov     [rbp+4Fh+var_68], 8
0x18001ff30  test    rax, rax
0x18001ff33  jz      short loc_18001FF75
0x18001ff35  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001ff3b  cmp     ecx, 0FFFFFFFFh
0x18001ff3e  jz      short loc_18001FF75
0x18001ff40  call    cs:__imp_TlsGetValue
0x18001ff46  test    rax, rax
0x18001ff49  lea     rdx, [rax+8]
0x18001ff4d  cmovz   rdx, r15
0x18001ff51  test    rdx, rdx
0x18001ff54  jz      short loc_18001FF75
0x18001ff56  mov     rax, rbx
0x18001ff59  nop     dword ptr [rax+00000000h]
0x18001ff60  cmp     [rdx+rax*2+2], r15w
0x18001ff66  lea     rax, [rax+1]
0x18001ff6a  jnz     short loc_18001FF60
0x18001ff6c  lea     eax, ds:2[rax*2]
0x18001ff73  jmp     short loc_18001FF81
0x18001ff75  lea     rdx, LocaleName
0x18001ff7c  mov     eax, 2
0x18001ff81  lea     rcx, ds:0[r13*2]
0x18001ff89  mov     [rbp+4Fh+var_60], rdx
0x18001ff8d  add     rcx, r13
0x18001ff90  mov     [rbp+4Fh+var_58], eax
0x18001ff93  mov     [rbp+4Fh+var_54], r15d
0x18001ff97  mov     rdx, [r12+rcx*8+8]
0x18001ff9c  test    rdx, rdx
0x18001ff9f  jz      short loc_18001FFB1
0x18001ffa1  mov     rax, rbx
0x18001ffa4  inc     rax
0x18001ffa7  cmp     [rdx+rax], r15b
0x18001ffab  jnz     short loc_18001FFA4
0x18001ffad  inc     eax
0x18001ffaf  jmp     short loc_18001FFBD
0x18001ffb1  lea     rdx, word_180122432
0x18001ffb8  mov     eax, 1
0x18001ffbd  mov     dword ptr [rbp+4Fh+var_48], eax
0x18001ffc0  lea     rcx, _TraceLoggingMetadata
0x18001ffc7  movzx   eax, cs:word_1801646F2
0x18001ffce  xor     r9d, r9d
0x18001ffd1  mov     [rbp+4Fh+var_A4], eax
0x18001ffd4  xor     r8d, r8d
0x18001ffd7  mov     rax, cs:off_180173280
0x18001ffde  mov     [rbp+4Fh+var_90], rax
0x18001ffe2  mov     [rbp+4Fh+var_50], rdx
0x18001ffe6  lea     rdx, [rbp+4Fh+var_A8]
0x18001ffea  mov     dword ptr [rbp+4Fh+var_48+4], r15d
0x18001ffee  mov     [rbp+4Fh+var_A8], 0B000000h
0x18001fff5  mov     [rbp+4Fh+var_A0], r15
0x18001fff9  movzx   eax, word ptr [rax]
0x18001fffc  mov     [rbp+4Fh+var_88], eax
0x18001ffff  lea     rax, dword_1801646FC
0x180020006  mov     [rbp+4Fh+var_80], rax
0x18002000a  mov     rax, rdi
0x18002000d  sub     eax, ecx
0x18002000f  mov     [rbp+4Fh+var_84], 2
0x180020016  mov     [rbp+4Fh+var_78], 38h ; '8'
0x18002001d  mov     [rbp+4Fh+var_74], 1
0x180020024  mov     [rsp+100h+var_D0], eax
0x180020028  mov     eax, [rsp+100h+var_D0]
0x18002002c  mov     rcx, cs:qword_180173298
0x180020033  lea     rax, [rbp+4Fh+var_90]
0x180020037  mov     [rsp+100h+var_D8], rax
0x18002003c  mov     dword ptr [rsp+100h+var_E0], 5
0x180020044  call    cs:__imp_EtwEventWriteTransfer
0x18002004a  movzx   edx, word ptr [rsi+0Eh]
0x18002004e  mov     al, 2Bh ; '+'
0x180020050  add     rdx, [rsi]
0x180020053  test    r14d, r14d
0x180020056  jnz     short loc_18002005A
0x180020058  mov     al, 0Dh
0x18002005a  mov     [rdx], al
0x18002005c  mov     ecx, r13d
0x18002005f  lea     rdx, [rbp+4Fh+Src]
0x180020063  call    IkeGetVendorIdHash
0x180020068  mov     r15, [rbp+4Fh+Src+8]
0x18002006c  mov     r12, rax
0x18002006f  test    rax, rax
0x180020072  jnz     loc_180020128
0x180020078  cmp     r13d, 0Dh
0x18002007c  ja      short loc_180020092
0x18002007e  mov     eax, 2C01h
0x180020083  bt      eax, r13d
0x180020087  jnb     short loc_180020092
0x180020089  mov     edi, dword ptr [rbp+4Fh+Src]
0x18002008c  lea     r14d, [rdi+4]
0x180020090  jmp     short loc_180020098
0x180020092  mov     edi, dword ptr [rbp+4Fh+Src]
0x180020095  mov     r14d, edi
0x180020098  lea     edx, [r14+4]
0x18002009c  mov     rcx, rsi
0x18002009f  call    IkeExpandPacket
0x1800200a4  mov     r12, rax
0x1800200a7  test    rax, rax
0x1800200aa  jnz     short loc_180020128
0x1800200ac  movzx   eax, word ptr [rsi+0Ch]
0x1800200b0  lea     ecx, [r14+4]; hostshort
0x1800200b4  mov     [rsi+0Eh], ax
0x1800200b8  call    cs:__imp_htons
0x1800200be  movzx   edx, word ptr [rsi+0Ch]
0x1800200c2  mov     rcx, [rsi]
0x1800200c5  mov     word ptr [rbp+4Fh+var_C8+2], ax
0x1800200c9  mov     eax, [rbp+4Fh+var_C8]
0x1800200cc  mov     r8d, edi; Size
0x1800200cf  mov     [rdx+rcx], eax
0x1800200d2  mov     rdx, r15; Src
0x1800200d5  add     word ptr [rsi+0Ch], 4
0x1800200da  movzx   ecx, word ptr [rsi+0Ch]
0x1800200de  add     rcx, [rsi]; void *
0x1800200e1  call    memcpy_0
0x1800200e6  add     [rsi+0Ch], di
0x1800200ea  test    r13d, r13d
0x1800200ed  jnz     short loc_1800200F6
0x1800200ef  mov     ecx, 9
0x1800200f4  jmp     short loc_180020113
0x1800200f6  cmp     r13d, 0Ah
0x1800200fa  jnz     short loc_180020101
0x1800200fc  mov     ecx, [rbp+4Fh+var_CC]
0x1800200ff  jmp     short loc_180020113
0x180020101  cmp     r13d, 0Bh
0x180020105  jnz     short loc_180020128
0x180020107  movzx   ecx, [rbp+4Fh+arg_20]
0x18002010b  call    IkeMMDhInternalToDoi
0x180020110  movzx   ecx, ax; hostlong
0x180020113  call    cs:__imp_htonl
0x180020119  movzx   edx, word ptr [rsi+0Ch]
0x18002011d  mov     rcx, [rsi]
0x180020120  mov     [rdx+rcx], eax
  ... truncated ...
```
