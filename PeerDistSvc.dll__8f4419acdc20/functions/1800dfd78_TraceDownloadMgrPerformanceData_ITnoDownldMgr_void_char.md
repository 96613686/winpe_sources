# TraceDownloadMgrPerformanceData(ITnoDownldMgr *,void (*)(char *,...))

- ea: `0x1800dfd78`
- end: `0x1800e04ec`
- name: `?TraceDownloadMgrPerformanceData@@YAXPEAVITnoDownldMgr@@P6AXPEADZZ@Z`
- size: `1908`
- prototype: `void __fastcall(struct ITnoDownldMgr *, void (*)(char *, ...))`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800bb020`
- `0x1800bc790`
- `0x1800bfa84`

## callees

- `0x180008d10`
- `0x1800dfd78`
- `0x1800e04f4`
- `0x1800e0844`
- `0x18012d3e4`
- `0x18012da74`
- `0x180144882`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800dff87`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800dffa3`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800dff87`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800dffa3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dff95`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dffb1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dff95`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800dffb1`

## string_xrefs

- `0x1800e008b`: `    Completed Data Downloads:                     %I64u`
- `0x1800e00ab`: `    Completed SegmentList Downloads:              %I64u`
- `0x1800e0107`: `    Completed Uploads:                            %I64u`
- `0x1800e01d5`: `    Attempted Network Discoveries:                %I64u`
- `0x1800e01e8`: `    Attempted V1 Network Discoveries:             %I64u`
- `0x1800e020f`: `    Attempted V2 Network Discoveries:             %I64u`
- `0x1800e029f`: `    Discovery Cache Entries:                      %I64u`
- `0x1800e02b2`: `    Discovery Cache Hits:                         %I64u`
- `0x1800e036d`: `  Protocol Messages:`

## pseudocode

```c
void __fastcall TraceDownloadMgrPerformanceData(struct ITnoDownldMgr *a1, void (*a2)(char *, ...))
{
  int v3; // ecx
  int v4; // edx
  __int64 v5; // rdx
  __int64 v6; // rdx
  struct _FILETIME LocalFileTime; // [rsp+D0h] [rbp-80h] BYREF
  __int64 v8; // [rsp+D8h] [rbp-78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+E0h] [rbp-70h] BYREF
  struct _SYSTEMTIME v10; // [rsp+F0h] [rbp-60h] BYREF
  FILETIME FileTime; // [rsp+100h] [rbp-50h] BYREF
  FILETIME v12; // [rsp+108h] [rbp-48h] BYREF
  __int64 v13; // [rsp+110h] [rbp-40h]
  __int64 v14; // [rsp+118h] [rbp-38h]
  __int64 v15; // [rsp+120h] [rbp-30h]
  __int64 v16; // [rsp+128h] [rbp-28h]
  __int64 v17; // [rsp+130h] [rbp-20h]
  __int64 v18; // [rsp+138h] [rbp-18h]
  __int64 v19; // [rsp+140h] [rbp-10h]
  __int64 v20; // [rsp+148h] [rbp-8h]
  __int64 v21; // [rsp+150h] [rbp+0h]
  int v22; // [rsp+158h] [rbp+8h]
  __int64 v23; // [rsp+160h] [rbp+10h]
  __int64 v24; // [rsp+168h] [rbp+18h]
  __int64 v25; // [rsp+170h] [rbp+20h]
  __int64 v26; // [rsp+178h] [rbp+28h]
  __int64 v27; // [rsp+180h] [rbp+30h]
  __int64 v28; // [rsp+188h] [rbp+38h]
  __int64 v29; // [rsp+190h] [rbp+40h]
  __int64 v30; // [rsp+198h] [rbp+48h]
  __int64 v31; // [rsp+1A0h] [rbp+50h]
  __int64 v32; // [rsp+1A8h] [rbp+58h]
  __int64 v33; // [rsp+1B0h] [rbp+60h]
  __int64 v34; // [rsp+1B8h] [rbp+68h]
  __int64 v35; // [rsp+1C0h] [rbp+70h]
  __int64 v36; // [rsp+1C8h] [rbp+78h]
  unsigned __int64 v37; // [rsp+1D0h] [rbp+80h]
  unsigned __int64 v38; // [rsp+1D8h] [rbp+88h]
  unsigned __int64 v39; // [rsp+1E0h] [rbp+90h]
  unsigned __int64 v40; // [rsp+1E8h] [rbp+98h]
  __int64 v41; // [rsp+1F0h] [rbp+A0h]
  __int64 v42; // [rsp+1F8h] [rbp+A8h]
  __int64 v43; // [rsp+200h] [rbp+B0h]
  __int64 v44; // [rsp+208h] [rbp+B8h]
  __int64 v45; // [rsp+210h] [rbp+C0h]
  __int64 v46; // [rsp+218h] [rbp+C8h]
  __int64 v47; // [rsp+220h] [rbp+D0h]
  __int64 v48; // [rsp+228h] [rbp+D8h]
  __int64 v49; // [rsp+230h] [rbp+E0h]
  __int64 v50; // [rsp+238h] [rbp+E8h]
  __int64 v51; // [rsp+240h] [rbp+F0h]
  __int64 v52; // [rsp+248h] [rbp+F8h]
  __int64 v53; // [rsp+250h] [rbp+100h]
  __int64 v54; // [rsp+258h] [rbp+108h]
  __int64 v55; // [rsp+260h] [rbp+110h]
  __int64 v56; // [rsp+268h] [rbp+118h]
  __int64 v57; // [rsp+270h] [rbp+120h]
  __int64 v58; // [rsp+278h] [rbp+128h]
  __int64 v59; // [rsp+280h] [rbp+130h]
  __int64 v60; // [rsp+288h] [rbp+138h]
  __int64 v61; // [rsp+290h] [rbp+140h]
  __int64 v62; // [rsp+298h] [rbp+148h]
  __int64 v63; // [rsp+2A0h] [rbp+150h]
  __int64 v64; // [rsp+2A8h] [rbp+158h]
  int v65; // [rsp+2B0h] [rbp+160h]
  int v66; // [rsp+2B4h] [rbp+164h]

  if ( dword_1801A60A0 || IsDiagnosticTracingEnabled() || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    v8 = 0;
    LocalFileTime = 0;
    SystemTime = 0;
    v10 = 0;
    memset_0(&FileTime, 0, 0x1B8u);
    if ( (*(int (__fastcall **)(struct ITnoDownldMgr *, GUID *, __int64 *))(*(_QWORD *)a1 + 16LL))(
           a1,
           &IID_DownloadManagerInternal,
           &v8) >= 0 )
    {
      (*(void (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v8 + 72LL))(v8, &FileTime);
      if ( (Microsoft_Windows_BranchCacheMonitoringEnableBits & 1) != 0 )
      {
        if ( v39 <= v40 )
          v3 = 0;
        else
          v3 = v39 - v40;
        if ( v37 <= v38 )
          v4 = 0;
        else
          v4 = v37 - v38;
        McTemplateU0xxxxxxxqqggxxxxxxxxxggxx_EventWriteTransfer(
          v3,
          v4,
          v27,
          v33,
          v31,
          v21,
          v32,
          v33,
          v34,
          v22,
          v65,
          v25,
          v26,
          v20,
          v37,
          v38,
          v4,
          v39,
          v40,
          v3,
          v41,
          v35,
          v23,
          v24,
          v43,
          v44);
      }
      PeerDistTelemetryReportPerfCounters();
      PeerDistTelemetryPCCRRPerformanceData((const struct DownloadMgrSnapshot_tag *)&FileTime);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0
        && (*(int (__fastcall **)(struct ITnoDownldMgr *, GUID *, __int64 *))(*(_QWORD *)a1 + 16LL))(
             a1,
             &IID_DownloadManagerInternal,
             &v8) >= 0 )
      {
        FileTimeToLocalFileTime(&FileTime, &LocalFileTime);
        FileTimeToSystemTime(&LocalFileTime, &SystemTime);
        FileTimeToLocalFileTime(&v12, &LocalFileTime);
        FileTimeToSystemTime(&LocalFileTime, &v10);
        TraceInfoLevelA("Download Manager Performance Snapshot:");
        TraceInfoLevelA("{");
        TraceInfoLevelA(
          "    Startup Timestamp:                            %04u/%02u/%02u %02u:%02u:%02u.%03u",
          SystemTime.wYear,
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
        TraceInfoLevelA(
          "    Snapshot Timestamp:                           %04u/%02u/%02u %02u:%02u:%02u.%03u",
          v10.wYear,
          v10.wMonth,
          v10.wDay,
          v10.wHour,
          v10.wMinute,
          v10.wSecond,
          v10.wMilliseconds);
        TraceInfoLevelA("  Downloads:");
        TraceInfoLevelA("    Pending Downloads:                            %I64u", v13);
        TraceInfoLevelA("    Request-To-Download Associations:             %I64u", v14);
        TraceInfoLevelA("    Average Block Download Byte Rate:             %I64u byte/s", v21);
        TraceInfoLevelA("    Completed Data Downloads:                     %I64u", v27);
        TraceInfoLevelA("    Successful Data Downloads:                    %I64u", v28);
        TraceInfoLevelA("    Completed SegmentList Downloads:              %I64u", v29);
        TraceInfoLevelA("    Successful SegmentList Downloads:             %I64u", v30);
        TraceInfoLevelA("    Max Observed Simultaneous Downloads:          %I64u", v31);
        TraceInfoLevelA("  Uploads:");
        TraceInfoLevelA("    Pending Uploads:                              %I64u", v15);
        TraceInfoLevelA("    Request-To-Upload Associations:               %I64u", v16);
        TraceInfoLevelA("    Completed Uploads:                            %I64u", v32);
        TraceInfoLevelA("    Successful Uploads:                           %I64u", v33);
        TraceInfoLevelA("    Max Observed Simultaneous Uploads:            %I64u", v34);
        TraceInfoLevelA("    Average Serving Latency:                      %u micros", v22);
        TraceInfoLevelA("    Min Observed Serving Latency:                 %u micros", v65);
        TraceInfoLevelA("    Max Observed Serving Latency:                 %u micros", v66);
        TraceInfoLevelA("    Current Average Inbound Request Frequency:    %g Hz", v25);
        TraceInfoLevelA("    Max Observed Inbound Request Frequency:       %g Hz", v26);
        TraceInfoLevelA("  Discovery:");
        TraceInfoLevelA("    Active Discoveries:                           %I64u", v17);
        TraceInfoLevelA("    Archived Discoveries:                         %I64u", v18);
        TraceInfoLevelA("    Average Discovery Time:                       %I64u micros", v20);
        TraceInfoLevelA("    Attempted Network Discoveries:                %I64u", v37);
        TraceInfoLevelA("    Attempted V1 Network Discoveries:             %I64u", v38);
        if ( v37 <= v38 )
          v5 = 0;
        else
          v5 = v37 - v38;
        TraceInfoLevelA("    Attempted V2 Network Discoveries:             %I64u", v5);
        TraceInfoLevelA("    Successful Network Discoveries:               %I64u", v39);
        TraceInfoLevelA("    Successful V1 Network Discoveries:            %I64u", v40);
        if ( v39 <= v40 )
          v6 = 0;
        else
          v6 = v39 - v40;
        TraceInfoLevelA("    Successful V2 Network Discoveries:            %I64u", v6);
        TraceInfoLevelA("    Suppressed Discoveries:                       %I64u", v41);
        TraceInfoLevelA("    PreDiscoveries:                               %I64u", v35);
        TraceInfoLevelA("    Download Inline Discoveries:                  %I64u", v36);
        TraceInfoLevelA("    Discovery Cache Entries:                      %I64u", v19);
        TraceInfoLevelA("    Discovery Cache Hits:                         %I64u", v42);
        TraceInfoLevelA("    Current Average Inbound Discovery Frequency:  %g Hz", v23);
        TraceInfoLevelA("    Max Observed Inbound Discovery Frequency:     %g Hz", v24);
        TraceInfoLevelA("  Peers:");
        TraceInfoLevelA("    Quarantined Peers                             %I64u", v62);
        TraceInfoLevelA("    Min Observed PUI Value                        %g", v63);
        TraceInfoLevelA("    Max Observed PUI Value                        %g", v64);
        TraceInfoLevelA("  Data:");
        TraceInfoLevelA("    Total Bytes Served:                           %I64u", v43);
        TraceInfoLevelA("    Total Bytes Retrieved:                        %I64u", v44);
        TraceInfoLevelA("  Protocol Messages:");
        TraceInfoLevelA("    Get Block List Msgs Sent                      %I64u", v45);
        TraceInfoLevelA("    Get Block List Msgs Recvd                     %I64u", v46);
        TraceInfoLevelA("    Get Blocks Msgs Sent                          %I64u", v47);
        TraceInfoLevelA("    Get Blocks Msgs Recvd                         %I64u", v48);
        TraceInfoLevelA("    Get Segment List Msgs Sent                    %I64u", v49);
        TraceInfoLevelA("    Get Segment List Msgs Recvd                   %I64u", v50);
        TraceInfoLevelA("    Block List Msgs Sent                          %I64u", v51);
        TraceInfoLevelA("    Block List Msgs Recvd                         %I64u", v52);
        TraceInfoLevelA("    Block Msgs Sent                               %I64u", v53);
        TraceInfoLevelA("    Empty Block Msgs Sent                         %I64u", v54);
        TraceInfoLevelA("    Block Msgs Recvd                              %I64u", v55);
        TraceInfoLevelA("    Segment List Msgs Sent                        %I64u", v56);
        TraceInfoLevelA("    Segment List Msgs Recvd                       %I64u", v57);
        TraceInfoLevelA("    Negotiation Req Msgs Sent                     %I64u", v58);
        TraceInfoLevelA("    Negotiation Req Msgs Recvd                    %I64u", v59);
        TraceInfoLevelA("    Negotiation Rsp Msgs Sent                     %I64u", v60);
        TraceInfoLevelA("    Negotiation Rsp Msgs Recvd                    %I64u", v61);
        TraceInfoLevelA("}");
      }
    }
  }
}

```

## disassembly

```asm
0x1800dfd78  mov     [rsp-8+arg_8], rbx
0x1800dfd7d  mov     [rsp-8+arg_10], rdi
0x1800dfd82  push    rbp
0x1800dfd83  lea     rbp, [rsp-180h]
0x1800dfd8b  sub     rsp, 2D0h
0x1800dfd92  mov     rax, cs:__security_cookie
0x1800dfd99  xor     rax, rsp
0x1800dfd9c  mov     [rbp+180h+var_10], rax
0x1800dfda3  mov     eax, cs:dword_1801A60A0
0x1800dfda9  mov     rbx, rcx
0x1800dfdac  test    eax, eax
0x1800dfdae  jnz     short loc_1800DFDCA
0x1800dfdb0  call    ?IsDiagnosticTracingEnabled@@YA_NXZ; IsDiagnosticTracingEnabled(void)
0x1800dfdb5  test    al, al
0x1800dfdb7  jnz     short loc_1800DFDCA
0x1800dfdb9  mov     rax, cs:WPP_GLOBAL_Control
0x1800dfdc0  test    byte ptr [rax+6Ch], 8
0x1800dfdc4  jz      loc_1800E04C8
0x1800dfdca  xorps   xmm0, xmm0
0x1800dfdcd  mov     [rbp+180h+var_1F8], 0
0x1800dfdd5  xorps   xmm1, xmm1
0x1800dfdd8  mov     qword ptr [rbp+180h+LocalFileTime.dwLowDateTime], 0
0x1800dfde0  xor     edx, edx; Val
0x1800dfde2  lea     rcx, [rbp+180h+FileTime]; void *
0x1800dfde6  mov     r8d, 1B8h; Size
0x1800dfdec  movups  xmmword ptr [rbp+180h+SystemTime.wYear], xmm0
0x1800dfdf0  movups  xmmword ptr [rbp+180h+var_1E0.wYear], xmm1
0x1800dfdf4  call    memset_0
0x1800dfdf9  mov     rax, [rbx]
0x1800dfdfc  lea     r8, [rbp+180h+var_1F8]
0x1800dfe00  lea     rdx, IID_DownloadManagerInternal
0x1800dfe07  mov     rcx, rbx
0x1800dfe0a  mov     rax, [rax+10h]
0x1800dfe0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe13  test    eax, eax
0x1800dfe15  js      loc_1800E04C8
0x1800dfe1b  mov     rcx, [rbp+180h+var_1F8]
0x1800dfe1f  lea     rdx, [rbp+180h+FileTime]
0x1800dfe23  mov     rax, [rcx]
0x1800dfe26  mov     rax, [rax+48h]
0x1800dfe2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe2f  test    cs:Microsoft_Windows_BranchCacheMonitoringEnableBits, 1
0x1800dfe36  jz      loc_1800DFF3E
0x1800dfe3c  mov     r8, [rbp+180h+var_F0]
0x1800dfe43  mov     r9, [rbp+180h+var_E8]
0x1800dfe4a  mov     rdi, [rbp+180h+var_E0]
0x1800dfe51  cmp     r8, r9
0x1800dfe54  jbe     short loc_1800DFE5E
0x1800dfe56  mov     rcx, r8
0x1800dfe59  sub     rcx, r9
0x1800dfe5c  jmp     short loc_1800DFE60
0x1800dfe5e  xor     ecx, ecx
0x1800dfe60  mov     r10, [rbp+180h+var_100]
0x1800dfe67  mov     r11, [rbp+180h+var_F8]
0x1800dfe6e  cmp     r10, r11
0x1800dfe71  jbe     short loc_1800DFE7B
0x1800dfe73  mov     rdx, r10
0x1800dfe76  sub     rdx, r11
0x1800dfe79  jmp     short loc_1800DFE7D
0x1800dfe7b  xor     edx, edx
0x1800dfe7d  mov     rax, [rbp+180h+var_C8]
0x1800dfe84  movaps  xmm0, [rbp+180h+var_170]
0x1800dfe88  mov     [rsp+2D0h+var_208], rax
0x1800dfe90  mov     rax, [rbp+180h+var_D0]
0x1800dfe97  mov     [rsp+2D0h+var_210], rax
0x1800dfe9f  mov     rax, [rbp+180h+var_110]
0x1800dfea3  movups  [rsp+2D0h+var_220], xmm0
0x1800dfeab  mov     [rsp+2D0h+var_228], rax
0x1800dfeb3  mov     rax, [rbp+180h+var_188]
0x1800dfeb7  movaps  xmm0, [rbp+180h+var_160]
0x1800dfebb  mov     [rsp+2D0h+var_230], rdi
0x1800dfec3  mov     [rsp+2D0h+var_238], rcx
0x1800dfecb  mov     [rsp+2D0h+var_240], r9
0x1800dfed3  mov     r9, [rbp+180h+var_120]
0x1800dfed7  mov     [rsp+2D0h+var_248], r8
0x1800dfedf  mov     r8, [rbp+180h+var_150]
0x1800dfee3  mov     [rsp+2D0h+var_250], rdx
0x1800dfeeb  mov     [rsp+2D0h+var_258], r11
0x1800dfef0  mov     [rsp+2D0h+var_260], r10
0x1800dfef5  mov     [rsp+2D0h+var_268], rax
0x1800dfefa  mov     eax, [rbp+180h+var_20]
0x1800dff00  movups  [rsp+2D0h+var_278], xmm0
0x1800dff05  mov     [rsp+2D0h+var_280], eax
0x1800dff09  mov     eax, [rbp+180h+var_178]
0x1800dff0c  mov     [rsp+2D0h+var_288], eax
0x1800dff10  mov     rax, [rbp+180h+var_118]
0x1800dff14  mov     [rsp+2D0h+var_290], rax
0x1800dff19  mov     rax, [rbp+180h+var_128]
0x1800dff1d  mov     [rsp+2D0h+var_298], r9
0x1800dff22  mov     [rsp+2D0h+var_2A0], rax
0x1800dff27  mov     rax, [rbp+180h+var_180]
0x1800dff2b  mov     [rsp+2D0h+var_2A8], rax
0x1800dff30  mov     rax, [rbp+180h+var_130]
0x1800dff34  mov     [rsp+2D0h+var_2B0], rax
0x1800dff39  call    McTemplateU0xxxxxxxqqggxxxxxxxxxggxx_EventWriteTransfer
0x1800dff3e  call    ?PeerDistTelemetryReportPerfCounters@@YAXXZ; PeerDistTelemetryReportPerfCounters(void)
0x1800dff43  lea     rcx, [rbp+180h+FileTime]; struct DownloadMgrSnapshot_tag *
0x1800dff47  call    ?PeerDistTelemetryPCCRRPerformanceData@@YAXPEBUDownloadMgrSnapshot_tag@@@Z; PeerDistTelemetryPCCRRPerformanceData(DownloadMgrSnapshot_tag const *)
0x1800dff4c  mov     rax, cs:WPP_GLOBAL_Control
0x1800dff53  test    byte ptr [rax+6Ch], 8
0x1800dff57  jz      loc_1800E04C8
0x1800dff5d  mov     rax, [rbx]
0x1800dff60  lea     r8, [rbp+180h+var_1F8]
0x1800dff64  lea     rdx, IID_DownloadManagerInternal
0x1800dff6b  mov     rcx, rbx
0x1800dff6e  mov     rax, [rax+10h]
0x1800dff72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dff77  test    eax, eax
0x1800dff79  js      loc_1800E04C8
0x1800dff7f  lea     rdx, [rbp+180h+LocalFileTime]; lpLocalFileTime
0x1800dff83  lea     rcx, [rbp+180h+FileTime]; lpFileTime
0x1800dff87  call    cs:__imp_FileTimeToLocalFileTime
0x1800dff8d  lea     rdx, [rbp+180h+SystemTime]; lpSystemTime
0x1800dff91  lea     rcx, [rbp+180h+LocalFileTime]; lpFileTime
0x1800dff95  call    cs:__imp_FileTimeToSystemTime
0x1800dff9b  lea     rdx, [rbp+180h+LocalFileTime]; lpLocalFileTime
0x1800dff9f  lea     rcx, [rbp+180h+var_1C8]; lpFileTime
0x1800dffa3  call    cs:__imp_FileTimeToLocalFileTime
0x1800dffa9  lea     rdx, [rbp+180h+var_1E0]; lpSystemTime
0x1800dffad  lea     rcx, [rbp+180h+LocalFileTime]; lpFileTime
0x1800dffb1  call    cs:__imp_FileTimeToSystemTime
0x1800dffb7  lea     rcx, aDownloadManage; "Download Manager Performance Snapshot:"
0x1800dffbe  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800dffc3  lea     rcx, asc_18017D5A0; "{"
0x1800dffca  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800dffcf  movzx   ecx, [rbp+180h+SystemTime.wSecond]
0x1800dffd3  movzx   eax, [rbp+180h+SystemTime.wMilliseconds]
0x1800dffd7  movzx   r10d, [rbp+180h+SystemTime.wMinute]
0x1800dffdc  movzx   r11d, [rbp+180h+SystemTime.wHour]
0x1800dffe1  movzx   r9d, [rbp+180h+SystemTime.wDay]
0x1800dffe6  movzx   r8d, [rbp+180h+SystemTime.wMonth]
0x1800dffeb  movzx   edx, [rbp+180h+SystemTime.wYear]
0x1800dffef  mov     dword ptr [rsp+2D0h+var_298], eax
0x1800dfff3  mov     dword ptr [rsp+2D0h+var_2A0], ecx
0x1800dfff7  lea     rcx, aStartupTimesta; "    Startup Timestamp:                 "...
0x1800dfffe  mov     dword ptr [rsp+2D0h+var_2A8], r10d
0x1800e0003  mov     dword ptr [rsp+2D0h+var_2B0], r11d
0x1800e0008  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e000d  movzx   ecx, [rbp+180h+var_1E0.wSecond]
0x1800e0011  movzx   eax, [rbp+180h+var_1E0.wMilliseconds]
0x1800e0015  movzx   r10d, [rbp+180h+var_1E0.wMinute]
0x1800e001a  movzx   r11d, [rbp+180h+var_1E0.wHour]
0x1800e001f  movzx   r9d, [rbp+180h+var_1E0.wDay]
0x1800e0024  movzx   r8d, [rbp+180h+var_1E0.wMonth]
0x1800e0029  movzx   edx, [rbp+180h+var_1E0.wYear]
0x1800e002d  mov     dword ptr [rsp+2D0h+var_298], eax
0x1800e0031  mov     dword ptr [rsp+2D0h+var_2A0], ecx
0x1800e0035  lea     rcx, aSnapshotTimest; "    Snapshot Timestamp:                "...
0x1800e003c  mov     dword ptr [rsp+2D0h+var_2A8], r10d
0x1800e0041  mov     dword ptr [rsp+2D0h+var_2B0], r11d
0x1800e0046  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e004b  lea     rcx, aDownloads; "  Downloads:"
0x1800e0052  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0057  mov     rdx, [rbp+180h+var_1C0]
0x1800e005b  lea     rcx, aPendingDownloa; "    Pending Downloads:                 "...
0x1800e0062  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0067  mov     rdx, [rbp+180h+var_1B8]
0x1800e006b  lea     rcx, aRequestToDownl; "    Request-To-Download Associations:  "...
0x1800e0072  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0077  mov     rdx, [rbp+180h+var_180]
0x1800e007b  lea     rcx, aAverageBlockDo; "    Average Block Download Byte Rate:  "...
0x1800e0082  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0087  mov     rdx, [rbp+180h+var_150]
0x1800e008b  lea     rcx, aCompletedDataD; "    Completed Data Downloads:          "...
0x1800e0092  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0097  mov     rdx, [rbp+180h+var_148]
0x1800e009b  lea     rcx, aSuccessfulData; "    Successful Data Downloads:         "...
0x1800e00a2  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e00a7  mov     rdx, [rbp+180h+var_140]
0x1800e00ab  lea     rcx, aCompletedSegme; "    Completed SegmentList Downloads:   "...
0x1800e00b2  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e00b7  mov     rdx, [rbp+180h+var_138]
0x1800e00bb  lea     rcx, aSuccessfulSegm; "    Successful SegmentList Downloads:  "...
0x1800e00c2  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e00c7  mov     rdx, [rbp+180h+var_130]
0x1800e00cb  lea     rcx, aMaxObservedSim_0; "    Max Observed Simultaneous Downloads"...
0x1800e00d2  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e00d7  lea     rcx, aUploads; "  Uploads:"
0x1800e00de  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e00e3  mov     rdx, [rbp+180h+var_1B0]
0x1800e00e7  lea     rcx, aPendingUploads; "    Pending Uploads:                   "...
0x1800e00ee  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e00f3  mov     rdx, [rbp+180h+var_1A8]
0x1800e00f7  lea     rcx, aRequestToUploa; "    Request-To-Upload Associations:    "...
0x1800e00fe  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0103  mov     rdx, [rbp+180h+var_128]
0x1800e0107  lea     rcx, aCompletedUploa; "    Completed Uploads:                 "...
0x1800e010e  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0113  mov     rdx, [rbp+180h+var_120]
0x1800e0117  lea     rcx, aSuccessfulUplo; "    Successful Uploads:                "...
0x1800e011e  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0123  mov     rdx, [rbp+180h+var_118]
0x1800e0127  lea     rcx, aMaxObservedSim; "    Max Observed Simultaneous Uploads: "...
0x1800e012e  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0133  mov     edx, [rbp+180h+var_178]
0x1800e0136  lea     rcx, aAverageServing; "    Average Serving Latency:           "...
0x1800e013d  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0142  mov     edx, [rbp+180h+var_20]
0x1800e0148  lea     rcx, aMinObservedSer; "    Min Observed Serving Latency:      "...
0x1800e014f  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0154  mov     edx, [rbp+180h+var_1C]
0x1800e015a  lea     rcx, aMaxObservedSer; "    Max Observed Serving Latency:      "...
0x1800e0161  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0166  movsd   xmm1, qword ptr [rbp+180h+var_160]
0x1800e016b  lea     rcx, aCurrentAverage; "    Current Average Inbound Request Fre"...
0x1800e0172  movq    rdx, xmm1
0x1800e0177  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e017c  movsd   xmm1, qword ptr [rbp+180h+var_160+8]
0x1800e0181  lea     rcx, aMaxObservedInb_0; "    Max Observed Inbound Request Freque"...
0x1800e0188  movq    rdx, xmm1
0x1800e018d  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0192  lea     rcx, aDiscovery; "  Discovery:"
0x1800e0199  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e019e  mov     rdx, [rbp+180h+var_1A0]
0x1800e01a2  lea     rcx, aActiveDiscover; "    Active Discoveries:                "...
0x1800e01a9  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e01ae  mov     rdx, [rbp+180h+var_198]
0x1800e01b2  lea     rcx, aArchivedDiscov; "    Archived Discoveries:              "...
0x1800e01b9  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e01be  mov     rdx, [rbp+180h+var_188]
0x1800e01c2  lea     rcx, aAverageDiscove; "    Average Discovery Time:            "...
0x1800e01c9  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e01ce  mov     rdx, [rbp+180h+var_100]
0x1800e01d5  lea     rcx, aAttemptedNetwo; "    Attempted Network Discoveries:     "...
0x1800e01dc  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e01e1  mov     rdx, [rbp+180h+var_F8]
0x1800e01e8  lea     rcx, aAttemptedV1Net; "    Attempted V1 Network Discoveries:  "...
0x1800e01ef  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e01f4  mov     rdx, [rbp+180h+var_100]
0x1800e01fb  cmp     rdx, [rbp+180h+var_F8]
0x1800e0202  jbe     short loc_1800E020D
0x1800e0204  sub     rdx, [rbp+180h+var_F8]
0x1800e020b  jmp     short loc_1800E020F
0x1800e020d  xor     edx, edx
0x1800e020f  lea     rcx, aAttemptedV2Net; "    Attempted V2 Network Discoveries:  "...
0x1800e0216  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e021b  mov     rdx, [rbp+180h+var_F0]
0x1800e0222  lea     rcx, aSuccessfulNetw; "    Successful Network Discoveries:    "...
0x1800e0229  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e022e  mov     rdx, [rbp+180h+var_E8]
0x1800e0235  lea     rcx, aSuccessfulV1Ne; "    Successful V1 Network Discoveries: "...
0x1800e023c  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0241  mov     rdx, [rbp+180h+var_F0]
0x1800e0248  cmp     rdx, [rbp+180h+var_E8]
0x1800e024f  jbe     short loc_1800E025A
0x1800e0251  sub     rdx, [rbp+180h+var_E8]
0x1800e0258  jmp     short loc_1800E025C
0x1800e025a  xor     edx, edx
0x1800e025c  lea     rcx, aSuccessfulV2Ne; "    Successful V2 Network Discoveries: "...
0x1800e0263  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0268  mov     rdx, [rbp+180h+var_E0]
0x1800e026f  lea     rcx, aSuppressedDisc; "    Suppressed Discoveries:            "...
0x1800e0276  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e027b  mov     rdx, [rbp+180h+var_110]
0x1800e027f  lea     rcx, aPrediscoveries; "    PreDiscoveries:                    "...
0x1800e0286  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e028b  mov     rdx, [rbp+180h+var_108]
0x1800e028f  lea     rcx, aDownloadInline; "    Download Inline Discoveries:       "...
0x1800e0296  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e029b  mov     rdx, [rbp+180h+var_190]
0x1800e029f  lea     rcx, aDiscoveryCache; "    Discovery Cache Entries:           "...
0x1800e02a6  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e02ab  mov     rdx, [rbp+180h+var_D8]
0x1800e02b2  lea     rcx, aDiscoveryCache_0; "    Discovery Cache Hits:              "...
0x1800e02b9  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e02be  movsd   xmm1, qword ptr [rbp+180h+var_170]
0x1800e02c3  lea     rcx, aCurrentAverage_0; "    Current Average Inbound Discovery F"...
0x1800e02ca  movq    rdx, xmm1
0x1800e02cf  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e02d4  movsd   xmm1, qword ptr [rbp+180h+var_170+8]
0x1800e02d9  lea     rcx, aMaxObservedInb; "    Max Observed Inbound Discovery Freq"...
0x1800e02e0  movq    rdx, xmm1
0x1800e02e5  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e02ea  lea     rcx, aPeers; "  Peers:"
0x1800e02f1  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e02f6  mov     rdx, [rbp+180h+var_38]
0x1800e02fd  lea     rcx, aQuarantinedPee; "    Quarantined Peers                  "...
0x1800e0304  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0309  movsd   xmm1, [rbp+180h+var_30]
0x1800e0311  lea     rcx, aMinObservedPui; "    Min Observed PUI Value             "...
0x1800e0318  movq    rdx, xmm1
0x1800e031d  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0322  movsd   xmm1, [rbp+180h+var_28]
0x1800e032a  lea     rcx, aMaxObservedPui; "    Max Observed PUI Value             "...
0x1800e0331  movq    rdx, xmm1
0x1800e0336  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e033b  lea     rcx, aData; "  Data:"
0x1800e0342  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0347  mov     rdx, [rbp+180h+var_D0]
0x1800e034e  lea     rcx, aTotalBytesServ; "    Total Bytes Served:                "...
0x1800e0355  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e035a  mov     rdx, [rbp+180h+var_C8]
0x1800e0361  lea     rcx, aTotalBytesRetr; "    Total Bytes Retrieved:             "...
0x1800e0368  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e036d  lea     rcx, aProtocolMessag; "  Protocol Messages:"
0x1800e0374  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e0379  mov     rdx, [rbp+180h+var_C0]
0x1800e0380  lea     rcx, aGetBlockListMs; "    Get Block List Msgs Sent           "...
0x1800e0387  call    ?TraceInfoLevelA@@YAXPEADZZ; TraceInfoLevelA(char *,...)
0x1800e038c  mov     rdx, [rbp+180h+var_B8]
  ... truncated ...
```
