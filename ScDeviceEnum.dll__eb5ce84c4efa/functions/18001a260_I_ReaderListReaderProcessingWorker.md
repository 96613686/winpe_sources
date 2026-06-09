# I_ReaderListReaderProcessingWorker

- ea: `0x18001a260`
- end: `0x18001aaa8`
- name: `I_ReaderListReaderProcessingWorker`
- size: `2120`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, __int64 *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001178`
- `0x1800011b4`
- `0x1800011e4`
- `0x180007178`
- `0x1800071d4`
- `0x180016d74`
- `0x18001a260`
- `0x18001cc6c`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aa4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aa4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aa2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aa2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a5d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a5f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a5d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a5f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a562`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a562`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a2f7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a306`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a642`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a2f7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a306`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a642`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x18001a54a`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x18001a54a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a96f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a96f`

## pseudocode

```c
void __fastcall I_ReaderListReaderProcessingWorker(PTP_CALLBACK_INSTANCE Instance, __int64 *Context, PTP_WORK Work)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbx
  char v12; // al
  void *v13; // r8
  void *v14; // r8
  PVOID v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // r15d
  __int64 *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rbx
  char LastError; // al
  struct _RTL_CRITICAL_SECTION *v24; // rbx
  __int64 *i; // rdi
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  int v27; // [rsp+34h] [rbp-CCh] BYREF
  int v28; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+3Ch] [rbp-C4h] BYREF
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+4Ch] [rbp-B4h] BYREF
  int v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+54h] [rbp-ACh] BYREF
  int v36; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+5Ch] [rbp-A4h] BYREF
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+64h] [rbp-9Ch] BYREF
  int v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+6Ch] [rbp-94h] BYREF
  int v42; // [rsp+70h] [rbp-90h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp-88h] BYREF
  GUID v44; // [rsp+88h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v45[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v46[16]; // [rsp+C0h] [rbp-40h] BYREF
  int *v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  _BYTE v49[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v50[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v51[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v52[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v53[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v54[16]; // [rsp+130h] [rbp+30h] BYREF
  int *v55; // [rsp+140h] [rbp+40h]
  __int64 v56; // [rsp+148h] [rbp+48h]
  int *v57; // [rsp+150h] [rbp+50h]
  __int64 v58; // [rsp+158h] [rbp+58h]
  int *v59; // [rsp+160h] [rbp+60h]
  __int64 v60; // [rsp+168h] [rbp+68h]
  int *v61; // [rsp+170h] [rbp+70h]
  __int64 v62; // [rsp+178h] [rbp+78h]
  int *v63; // [rsp+180h] [rbp+80h]
  __int64 v64; // [rsp+188h] [rbp+88h]
  int *v65; // [rsp+190h] [rbp+90h]
  __int64 v66; // [rsp+198h] [rbp+98h]
  int *v67; // [rsp+1A0h] [rbp+A0h]
  __int64 v68; // [rsp+1A8h] [rbp+A8h]
  int *v69; // [rsp+1B0h] [rbp+B0h]
  __int64 v70; // [rsp+1B8h] [rbp+B8h]
  int *v71; // [rsp+1C0h] [rbp+C0h]
  __int64 v72; // [rsp+1C8h] [rbp+C8h]
  int *v73; // [rsp+1D0h] [rbp+D0h]
  __int64 v74; // [rsp+1D8h] [rbp+D8h]
  int *v75; // [rsp+1E0h] [rbp+E0h]
  __int64 v76; // [rsp+1E8h] [rbp+E8h]
  int *v77; // [rsp+1F0h] [rbp+F0h]
  __int64 v78; // [rsp+1F8h] [rbp+F8h]
  int *v79; // [rsp+200h] [rbp+100h]
  __int64 v80; // [rsp+208h] [rbp+108h]
  int *v81; // [rsp+210h] [rbp+110h]
  __int64 v82; // [rsp+218h] [rbp+118h]
  int *v83; // [rsp+220h] [rbp+120h]
  __int64 v84; // [rsp+228h] [rbp+128h]
  int *v85; // [rsp+230h] [rbp+130h]
  __int64 v86; // [rsp+238h] [rbp+138h]
  struct _EVENT_DATA_DESCRIPTOR v87[2]; // [rsp+240h] [rbp+140h] BYREF

  WppTraceIndent(Instance, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v44 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v44);
  if ( (unsigned int)dword_18002B008 > 5 )
    tlgWriteTransfer_EventWriteTransfer(v5, (unsigned __int8 *)byte_1800261C9, &v44, &ActivityId, 2u, v87);
  if ( Context )
  {
    v6 = *Context;
    if ( *Context )
    {
      v7 = Context[1];
      if ( v7 )
      {
        if ( (unsigned int)dword_18002B008 > 5 )
        {
          tlgCreate1Sz_wchar_t((__int64)v46, *(__int64 **)v7);
          v8 = *(__int64 **)(v7 + 16);
          v26 = *(_DWORD *)(v7 + 8);
          v47 = &v26;
          v48 = 4;
          tlgCreate1Sz_wchar_t((__int64)v49, v8);
          tlgCreate1Sz_wchar_t((__int64)v50, *(__int64 **)(v7 + 80));
          tlgCreate1Sz_wchar_t((__int64)v51, *(__int64 **)(v7 + 88));
          tlgCreate1Sz_wchar_t((__int64)v52, *(__int64 **)(v7 + 96));
          tlgCreate1Sz_wchar_t((__int64)v53, *(__int64 **)(v7 + 104));
          tlgCreate1Sz_wchar_t((__int64)v54, *(__int64 **)(v7 + 112));
          v9 = *(unsigned int *)(v7 + 120);
          v55 = &v27;
          v28 = *(_DWORD *)(v7 + 160);
          v57 = &v28;
          v29 = *(_DWORD *)(v6 + 256);
          v59 = &v29;
          v30 = *(_DWORD *)v6;
          v61 = &v30;
          v31 = *(_DWORD *)(v6 + 4);
          v63 = &v31;
          v32 = *(_DWORD *)(v6 + 8);
          v65 = &v32;
          v33 = *(_DWORD *)(v6 + 12);
          v67 = &v33;
          v34 = *(_DWORD *)(v6 + 16);
          v69 = &v34;
          v35 = *(_DWORD *)(v6 + 20);
          v71 = &v35;
          v36 = *(_DWORD *)(v6 + 40);
          v73 = &v36;
          v37 = *(_DWORD *)(v6 + 24);
          v75 = &v37;
          v27 = v9;
          v56 = 4;
          v58 = 4;
          v60 = 4;
          v62 = 4;
          v64 = 4;
          v66 = 4;
          v68 = 4;
          v70 = 4;
          v72 = 4;
          v74 = 4;
          v76 = 4;
          tlgWriteTransfer_EventWriteTransfer(v9, (unsigned __int8 *)word_180025F4A, &v44, &ActivityId, 0x15u, v45);
        }
        SetEventWhenCallbackReturns(Instance, *(HANDLE *)(v6 + 352));
        if ( !*(_DWORD *)v6 || SetThreadToken(0, *(HANDLE *)(v6 + 248)) )
        {
          *(_QWORD *)(v7 + 216) = 0;
          v17 = I_ReaderListCollectCertificates(
                  (int *)v6,
                  v7,
                  *((_DWORD *)Context + 4),
                  (const void *)Context[3],
                  *((_DWORD *)Context + 8));
          v18 = (unsigned int)dword_18002B008;
          v19 = v17;
          if ( (unsigned int)dword_18002B008 > 5
            && (unsigned __int8)tlgKeywordOn((unsigned int)dword_18002B008, 0x200000000000LL) )
          {
            tlgCreate1Sz_wchar_t((__int64)v46, *(__int64 **)v7);
            v20 = *(__int64 **)(v7 + 16);
            v37 = *(_DWORD *)(v7 + 8);
            v47 = &v37;
            v48 = 4;
            tlgCreate1Sz_wchar_t((__int64)v49, v20);
            tlgCreate1Sz_wchar_t((__int64)v50, *(__int64 **)(v7 + 80));
            tlgCreate1Sz_wchar_t((__int64)v51, *(__int64 **)(v7 + 88));
            tlgCreate1Sz_wchar_t((__int64)v52, *(__int64 **)(v7 + 96));
            tlgCreate1Sz_wchar_t((__int64)v53, *(__int64 **)(v7 + 104));
            tlgCreate1Sz_wchar_t((__int64)v54, *(__int64 **)(v7 + 112));
            v21 = *(unsigned int *)(v7 + 120);
            v55 = &v36;
            v35 = *(_DWORD *)(v7 + 160);
            v57 = &v35;
            v34 = *(_DWORD *)(v6 + 256);
            v59 = &v34;
            v33 = *(_DWORD *)v6;
            v61 = &v33;
            v32 = *(_DWORD *)(v6 + 4);
            v63 = &v32;
            v31 = *(_DWORD *)(v6 + 8);
            v65 = &v31;
            v30 = *(_DWORD *)(v6 + 12);
            v67 = &v30;
            v29 = *(_DWORD *)(v6 + 16);
            v69 = &v29;
            v28 = *(_DWORD *)(v6 + 20);
            v71 = &v28;
            v27 = *(_DWORD *)(v6 + 40);
            v73 = &v27;
            v26 = *(_DWORD *)(v6 + 24);
            v75 = &v26;
            v36 = v21;
            v56 = 4;
            v58 = 4;
            v60 = 4;
            v62 = 4;
            v64 = 4;
            v66 = 4;
            v68 = 4;
            v70 = 4;
            v72 = 4;
            v74 = 4;
            v76 = 4;
            v38 = v19;
            v77 = &v38;
            v39 = *(_DWORD *)(v7 + 216);
            v78 = 4;
            v79 = &v39;
            v40 = *(_DWORD *)(v7 + 220);
            v81 = &v40;
            v41 = *(_DWORD *)(v7 + 224);
            v83 = &v41;
            v42 = *(_DWORD *)(v7 + 228);
            v85 = &v42;
            v80 = 4;
            v82 = 4;
            v84 = 4;
            v86 = 4;
            tlgWriteTransfer_EventWriteTransfer(v21, (unsigned __int8 *)byte_180025C61, &v44, &ActivityId, 0x1Au, v45);
          }
          if ( *(_DWORD *)v6 )
          {
            if ( !RevertToSelf() )
            {
              WppTraceIndent(v18, 2);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v22 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                LastError = GetLastError();
                WPP_SF_sd(
                  v22,
                  205,
                  (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
                  WPP_pszIndent,
                  LastError);
              }
            }
          }
          if ( v19 )
          {
            WppTraceIndent(v18, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                206,
                (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
                WPP_pszIndent,
                v19);
            }
          }
          v24 = (struct _RTL_CRITICAL_SECTION *)(v6 + 48);
          *(_DWORD *)(v7 + 160) = v19;
          *(_QWORD *)(v7 + 240) = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
          for ( i = (__int64 *)(v6 + 368); *i; i = (__int64 *)(*i + 240) )
            ;
          *i = v7;
          LeaveCriticalSection(v24);
          Context[1] = 0;
        }
        else
        {
          WppTraceIndent(v10, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v12 = GetLastError();
            WPP_SF_sd(v11, 204, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, v12);
          }
        }
LABEL_18:
        v13 = (void *)Context[1];
        if ( v13 )
          HeapFree(hHeap, 0, v13);
        v14 = (void *)Context[3];
        if ( v14 )
          HeapFree(hHeap, 0, v14);
        HeapFree(hHeap, 0, Context);
        goto LABEL_23;
      }
    }
  }
  WppTraceIndent(v5, 2);
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( Context )
    goto LABEL_18;
LABEL_23:
  if ( (unsigned int)dword_18002B008 > 5 )
    tlgWriteTransfer_EventWriteTransfer((__int64)v15, (unsigned __int8 *)byte_1800250EB, &v44, &ActivityId, 2u, v87);
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v16, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
}

```

## disassembly

```asm
0x18001a260  mov     [rsp-8+arg_10], rbx
0x18001a265  push    rbp
0x18001a266  push    rsi
0x18001a267  push    rdi
0x18001a268  push    r12
0x18001a26a  push    r13
0x18001a26c  push    r14
0x18001a26e  push    r15
0x18001a270  lea     rbp, [rsp-170h]
0x18001a278  sub     rsp, 270h
0x18001a27f  mov     rax, cs:__security_cookie
0x18001a286  xor     rax, rsp
0x18001a289  mov     [rbp+1A0h+var_40], rax
0x18001a290  mov     r14, rdx
0x18001a293  mov     r15, rcx
0x18001a296  xor     edx, edx
0x18001a298  call    WppTraceIndent
0x18001a29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2a4  lea     rbx, WPP_GLOBAL_Control
0x18001a2ab  mov     r13d, 2
0x18001a2b1  cmp     rcx, rbx
0x18001a2b4  jz      short loc_18001A2DE
0x18001a2b6  test    [rcx+1Ch], r13b
0x18001a2ba  jz      short loc_18001A2DE
0x18001a2bc  cmp     byte ptr [rcx+19h], 5
0x18001a2c0  jb      short loc_18001A2DE
0x18001a2c2  mov     r9, cs:WPP_pszIndent
0x18001a2c9  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001a2d0  mov     rcx, [rcx+10h]
0x18001a2d4  mov     edx, 0CAh
0x18001a2d9  call    WPP_SF_s
0x18001a2de  xorps   xmm0, xmm0
0x18001a2e1  lea     rdx, [rsp+2A0h+ActivityId]; ActivityId
0x18001a2e6  xorps   xmm1, xmm1
0x18001a2e9  mov     ecx, 5; ControlCode
0x18001a2ee  movups  xmmword ptr [rsp+2A0h+ActivityId.Data1], xmm0
0x18001a2f3  movups  xmmword ptr [rbp+1A0h+var_218.Data1], xmm1
0x18001a2f7  call    cs:__imp_EventActivityIdControl
0x18001a2fd  lea     rdx, [rbp+1A0h+var_218]; ActivityId
0x18001a301  mov     ecx, 1; ControlCode
0x18001a306  call    cs:__imp_EventActivityIdControl
0x18001a30c  mov     eax, cs:dword_18002B008
0x18001a312  cmp     eax, 5
0x18001a315  jbe     short loc_18001A33D
0x18001a317  lea     rax, [rbp+1A0h+var_60]
0x18001a31e  mov     [rsp+2A0h+var_278], rax
0x18001a323  lea     r9, [rsp+2A0h+ActivityId]
0x18001a328  lea     r8, [rbp+1A0h+var_218]
0x18001a32c  mov     [rsp+2A0h+var_280], r13d
0x18001a331  lea     rdx, byte_1800261C9
0x18001a338  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a33d  xor     r12d, r12d
0x18001a340  test    r14, r14
0x18001a343  jz      loc_18001AA5E
0x18001a349  mov     rdi, [r14]
0x18001a34c  test    rdi, rdi
0x18001a34f  jz      loc_18001AA5E
0x18001a355  mov     rsi, [r14+8]
0x18001a359  test    rsi, rsi
0x18001a35c  jz      loc_18001AA5E
0x18001a362  mov     eax, cs:dword_18002B008
0x18001a368  cmp     eax, 5
0x18001a36b  jbe     loc_18001A540
0x18001a371  mov     rdx, [rsi]
0x18001a374  lea     rcx, [rbp+1A0h+var_1E0]
0x18001a378  call    _tlgCreate1Sz_wchar_t
0x18001a37d  mov     ecx, [rsi+8]
0x18001a380  lea     rax, [rsp+2A0h+var_270]
0x18001a385  mov     rdx, [rsi+10h]
0x18001a389  mov     [rsp+2A0h+var_270], ecx
0x18001a38d  lea     rcx, [rbp+1A0h+var_1C0]
0x18001a391  mov     [rbp+1A0h+var_1D0], rax
0x18001a395  mov     [rbp+1A0h+var_1C8], 4
0x18001a39d  call    _tlgCreate1Sz_wchar_t
0x18001a3a2  mov     rdx, [rsi+50h]
0x18001a3a6  lea     rcx, [rbp+1A0h+var_1B0]
0x18001a3aa  call    _tlgCreate1Sz_wchar_t
0x18001a3af  mov     rdx, [rsi+58h]
0x18001a3b3  lea     rcx, [rbp+1A0h+var_1A0]
0x18001a3b7  call    _tlgCreate1Sz_wchar_t
0x18001a3bc  mov     rdx, [rsi+60h]
0x18001a3c0  lea     rcx, [rbp+1A0h+var_190]
0x18001a3c4  call    _tlgCreate1Sz_wchar_t
0x18001a3c9  mov     rdx, [rsi+68h]
0x18001a3cd  lea     rcx, [rbp+1A0h+var_180]
0x18001a3d1  call    _tlgCreate1Sz_wchar_t
0x18001a3d6  mov     rdx, [rsi+70h]
0x18001a3da  lea     rcx, [rbp+1A0h+var_170]
0x18001a3de  call    _tlgCreate1Sz_wchar_t
0x18001a3e3  mov     ecx, [rsi+78h]
0x18001a3e6  lea     rax, [rsp+2A0h+var_26C]
0x18001a3eb  mov     [rbp+1A0h+var_160], rax
0x18001a3ef  mov     eax, [rsi+0A0h]
0x18001a3f5  mov     [rsp+2A0h+var_268], eax
0x18001a3f9  lea     rax, [rsp+2A0h+var_268]
0x18001a3fe  mov     [rbp+1A0h+var_150], rax
0x18001a402  mov     eax, [rdi+100h]
0x18001a408  mov     [rsp+2A0h+var_264], eax
0x18001a40c  lea     rax, [rsp+2A0h+var_264]
0x18001a411  mov     [rbp+1A0h+var_140], rax
0x18001a415  mov     eax, [rdi]
0x18001a417  mov     [rsp+2A0h+var_260], eax
0x18001a41b  lea     rax, [rsp+2A0h+var_260]
0x18001a420  mov     [rbp+1A0h+var_130], rax
0x18001a424  mov     eax, [rdi+4]
0x18001a427  mov     [rsp+2A0h+var_25C], eax
0x18001a42b  lea     rax, [rsp+2A0h+var_25C]
0x18001a430  mov     [rbp+1A0h+var_120], rax
0x18001a437  mov     eax, [rdi+8]
0x18001a43a  mov     [rsp+2A0h+var_258], eax
0x18001a43e  lea     rax, [rsp+2A0h+var_258]
0x18001a443  mov     [rbp+1A0h+var_110], rax
0x18001a44a  mov     eax, [rdi+0Ch]
0x18001a44d  mov     [rsp+2A0h+var_254], eax
0x18001a451  lea     rax, [rsp+2A0h+var_254]
0x18001a456  mov     [rbp+1A0h+var_100], rax
0x18001a45d  mov     eax, [rdi+10h]
0x18001a460  mov     [rsp+2A0h+var_250], eax
0x18001a464  lea     rax, [rsp+2A0h+var_250]
0x18001a469  mov     [rbp+1A0h+var_F0], rax
0x18001a470  mov     eax, [rdi+14h]
0x18001a473  mov     [rsp+2A0h+var_24C], eax
0x18001a477  lea     rax, [rsp+2A0h+var_24C]
0x18001a47c  mov     [rbp+1A0h+var_E0], rax
0x18001a483  mov     eax, [rdi+28h]
0x18001a486  mov     [rsp+2A0h+var_248], eax
0x18001a48a  lea     rax, [rsp+2A0h+var_248]
0x18001a48f  mov     [rbp+1A0h+var_D0], rax
0x18001a496  mov     eax, [rdi+18h]
0x18001a499  mov     [rsp+2A0h+var_244], eax
0x18001a49d  lea     rax, [rsp+2A0h+var_244]
0x18001a4a2  mov     [rbp+1A0h+var_C0], rax
0x18001a4a9  mov     [rsp+2A0h+var_26C], ecx
0x18001a4ad  mov     [rbp+1A0h+var_158], 4
0x18001a4b5  mov     [rbp+1A0h+var_148], 4
0x18001a4bd  mov     [rbp+1A0h+var_138], 4
0x18001a4c5  mov     [rbp+1A0h+var_128], 4
0x18001a4cd  mov     [rbp+1A0h+var_118], 4
0x18001a4d8  mov     [rbp+1A0h+var_108], 4
0x18001a4e3  mov     [rbp+1A0h+var_F8], 4
0x18001a4ee  mov     [rbp+1A0h+var_E8], 4
0x18001a4f9  mov     [rbp+1A0h+var_D8], 4
0x18001a504  mov     [rbp+1A0h+var_C8], 4
0x18001a50f  mov     [rbp+1A0h+var_B8], 4
0x18001a51a  lea     rax, [rbp+1A0h+var_200]
0x18001a51e  mov     [rsp+2A0h+var_278], rax
0x18001a523  lea     r9, [rsp+2A0h+ActivityId]
0x18001a528  lea     r8, [rbp+1A0h+var_218]
0x18001a52c  mov     [rsp+2A0h+var_280], 15h
0x18001a534  lea     rdx, word_180025F4A
0x18001a53b  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a540  mov     rdx, [rdi+160h]; evt
0x18001a547  mov     rcx, r15; pci
0x18001a54a  call    cs:__imp_SetEventWhenCallbackReturns
0x18001a550  cmp     [rdi], r12d
0x18001a553  jz      loc_18001A6B0
0x18001a559  mov     rdx, [rdi+0F8h]; Token
0x18001a560  xor     ecx, ecx; Thread
0x18001a562  call    cs:__imp_SetThreadToken
0x18001a568  test    eax, eax
0x18001a56a  jnz     loc_18001A6B0
0x18001a570  mov     edx, r13d
0x18001a573  call    WppTraceIndent
0x18001a578  mov     rbx, cs:WPP_GLOBAL_Control
0x18001a57f  lea     rax, WPP_GLOBAL_Control
0x18001a586  cmp     rbx, rax
0x18001a589  jz      short loc_18001A5C0
0x18001a58b  test    byte ptr [rbx+1Ch], 1
0x18001a58f  jz      short loc_18001A5C0
0x18001a591  cmp     byte ptr [rbx+19h], 3
0x18001a595  jb      short loc_18001A5C0
0x18001a597  mov     rbx, [rbx+10h]
0x18001a59b  call    cs:__imp_GetLastError
0x18001a5a1  mov     r9, cs:WPP_pszIndent
0x18001a5a8  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001a5af  mov     edx, 0CCh
0x18001a5b4  mov     [rsp+2A0h+var_280], eax
0x18001a5b8  mov     rcx, rbx
0x18001a5bb  call    WPP_SF_sd
0x18001a5c0  lea     rbx, WPP_GLOBAL_Control
0x18001a5c7  mov     r8, [r14+8]; lpMem
0x18001a5cb  test    r8, r8
0x18001a5ce  jz      short loc_18001A5DF
0x18001a5d0  mov     rcx, cs:hHeap; hHeap
0x18001a5d7  xor     edx, edx; dwFlags
0x18001a5d9  call    cs:__imp_HeapFree
0x18001a5df  mov     r8, [r14+18h]; lpMem
0x18001a5e3  test    r8, r8
0x18001a5e6  jz      short loc_18001A5F7
0x18001a5e8  mov     rcx, cs:hHeap; hHeap
0x18001a5ef  xor     edx, edx; dwFlags
0x18001a5f1  call    cs:__imp_HeapFree
0x18001a5f7  mov     rcx, cs:hHeap; hHeap
0x18001a5fe  mov     r8, r14; lpMem
0x18001a601  xor     edx, edx; dwFlags
0x18001a603  call    cs:__imp_HeapFree
0x18001a609  mov     eax, cs:dword_18002B008
0x18001a60f  cmp     eax, 5
0x18001a612  jbe     short loc_18001A63A
0x18001a614  lea     rax, [rbp+1A0h+var_60]
0x18001a61b  mov     [rsp+2A0h+var_278], rax
0x18001a620  lea     r9, [rsp+2A0h+ActivityId]
0x18001a625  lea     r8, [rbp+1A0h+var_218]
0x18001a629  mov     [rsp+2A0h+var_280], r13d
0x18001a62e  lea     rdx, byte_1800250EB
0x18001a635  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a63a  lea     rdx, [rsp+2A0h+ActivityId]; ActivityId
0x18001a63f  mov     ecx, r13d; ControlCode
0x18001a642  call    cs:__imp_EventActivityIdControl
0x18001a648  mov     edx, 1
0x18001a64d  call    WppTraceIndent
0x18001a652  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a659  cmp     rcx, rbx
0x18001a65c  jz      short loc_18001A686
0x18001a65e  test    [rcx+1Ch], r13b
0x18001a662  jz      short loc_18001A686
0x18001a664  cmp     byte ptr [rcx+19h], 5
0x18001a668  jb      short loc_18001A686
0x18001a66a  mov     r9, cs:WPP_pszIndent
0x18001a671  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001a678  mov     rcx, [rcx+10h]
0x18001a67c  mov     edx, 0CFh
0x18001a681  call    WPP_SF_s
0x18001a686  mov     rcx, [rbp+1A0h+var_40]
0x18001a68d  xor     rcx, rsp; StackCookie
0x18001a690  call    __security_check_cookie
0x18001a695  mov     rbx, [rsp+2A0h+arg_10]
0x18001a69d  add     rsp, 270h
0x18001a6a4  pop     r15
0x18001a6a6  pop     r14
0x18001a6a8  pop     r13
0x18001a6aa  pop     r12
0x18001a6ac  pop     rdi
0x18001a6ad  pop     rsi
0x18001a6ae  pop     rbp
0x18001a6af  retn
0x18001a6b0  mov     [rsi+0D8h], r12
0x18001a6b7  mov     rdx, rsi
0x18001a6ba  mov     eax, [r14+20h]
0x18001a6be  mov     rcx, rdi
0x18001a6c1  mov     r9, [r14+18h]
0x18001a6c5  mov     r8d, [r14+10h]
0x18001a6c9  mov     [rsp+2A0h+var_280], eax
0x18001a6cd  call    I_ReaderListCollectCertificates
0x18001a6d2  mov     ecx, cs:dword_18002B008
0x18001a6d8  mov     r15d, eax
0x18001a6db  cmp     ecx, 5
0x18001a6de  jbe     loc_18001A96A
0x18001a6e4  mov     rdx, 200000000000h
0x18001a6ee  call    _tlgKeywordOn
0x18001a6f3  test    al, al
0x18001a6f5  jz      loc_18001A96A
0x18001a6fb  mov     rdx, [rsi]
0x18001a6fe  lea     rcx, [rbp+1A0h+var_1E0]
0x18001a702  call    _tlgCreate1Sz_wchar_t
0x18001a707  mov     ecx, [rsi+8]
0x18001a70a  lea     rax, [rsp+2A0h+var_244]
0x18001a70f  mov     rdx, [rsi+10h]
0x18001a713  mov     [rsp+2A0h+var_244], ecx
0x18001a717  lea     rcx, [rbp+1A0h+var_1C0]
0x18001a71b  mov     [rbp+1A0h+var_1D0], rax
0x18001a71f  mov     [rbp+1A0h+var_1C8], 4
0x18001a727  call    _tlgCreate1Sz_wchar_t
0x18001a72c  mov     rdx, [rsi+50h]
0x18001a730  lea     rcx, [rbp+1A0h+var_1B0]
0x18001a734  call    _tlgCreate1Sz_wchar_t
0x18001a739  mov     rdx, [rsi+58h]
0x18001a73d  lea     rcx, [rbp+1A0h+var_1A0]
0x18001a741  call    _tlgCreate1Sz_wchar_t
0x18001a746  mov     rdx, [rsi+60h]
0x18001a74a  lea     rcx, [rbp+1A0h+var_190]
0x18001a74e  call    _tlgCreate1Sz_wchar_t
0x18001a753  mov     rdx, [rsi+68h]
0x18001a757  lea     rcx, [rbp+1A0h+var_180]
0x18001a75b  call    _tlgCreate1Sz_wchar_t
0x18001a760  mov     rdx, [rsi+70h]
0x18001a764  lea     rcx, [rbp+1A0h+var_170]
0x18001a768  call    _tlgCreate1Sz_wchar_t
0x18001a76d  mov     ecx, [rsi+78h]
0x18001a770  lea     rax, [rsp+2A0h+var_248]
0x18001a775  mov     [rbp+1A0h+var_160], rax
0x18001a779  mov     eax, [rsi+0A0h]
0x18001a77f  mov     [rsp+2A0h+var_24C], eax
0x18001a783  lea     rax, [rsp+2A0h+var_24C]
0x18001a788  mov     [rbp+1A0h+var_150], rax
0x18001a78c  mov     eax, [rdi+100h]
0x18001a792  mov     [rsp+2A0h+var_250], eax
0x18001a796  lea     rax, [rsp+2A0h+var_250]
0x18001a79b  mov     [rbp+1A0h+var_140], rax
0x18001a79f  mov     eax, [rdi]
0x18001a7a1  mov     [rsp+2A0h+var_254], eax
0x18001a7a5  lea     rax, [rsp+2A0h+var_254]
0x18001a7aa  mov     [rbp+1A0h+var_130], rax
0x18001a7ae  mov     eax, [rdi+4]
0x18001a7b1  mov     [rsp+2A0h+var_258], eax
0x18001a7b5  lea     rax, [rsp+2A0h+var_258]
0x18001a7ba  mov     [rbp+1A0h+var_120], rax
0x18001a7c1  mov     eax, [rdi+8]
0x18001a7c4  mov     [rsp+2A0h+var_25C], eax
0x18001a7c8  lea     rax, [rsp+2A0h+var_25C]
  ... truncated ...
```
