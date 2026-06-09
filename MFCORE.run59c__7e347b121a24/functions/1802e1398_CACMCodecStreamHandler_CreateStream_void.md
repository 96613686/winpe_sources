# CACMCodecStreamHandler::CreateStream(void)

- ea: `0x1802e1398`
- end: `0x1802e1839`
- name: `?CreateStream@CACMCodecStreamHandler@@QEAAJXZ`
- size: `1185`
- prototype: `__int64 __fastcall(CACMCodecStreamHandler *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801f5e50`
- `0x180205210`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18018566c`
- `0x180258480`
- `0x1802592a0`
- `0x1802e1398`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e17f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e1807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e17f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802e1807`
- `MFPlat!MFInitAMMediaTypeFromMFMediaType` at `0x1802e14c0`
- `MFPlat!MFInitAMMediaTypeFromMFMediaType` at `0x1802e1582`
- `MFPlat!MFInitAMMediaTypeFromMFMediaType` at `0x1802e14c0`
- `MFPlat!MFInitAMMediaTypeFromMFMediaType` at `0x1802e1582`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e141f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e14e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e15a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e16c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e1758`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e141f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e14e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e15a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e16c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802e1758`
- `ext-ms-win-mm-msacm-l1-1-0!acmStreamOpen` at `0x1802e1698`
- `ext-ms-win-mm-msacm-l1-1-0!acmStreamOpen` at `0x1802e1698`

## string_xrefs

- `0x1802e13bb`: `CACMCodecStreamHandler::CreateStream`

## pseudocode

```c
__int64 __fastcall CACMCodecStreamHandler::CreateStream(CACMCodecStreamHandler *this)
{
  __int64 v2; // rdx
  HRESULT v3; // ebx
  __int64 v4; // r8
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  IMFMediaType *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  IMFMediaType *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  MMRESULT v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  _BYTE v33[16]; // [rsp+40h] [rbp-C0h] BYREF
  GUID guidFormatBlockType; // [rsp+50h] [rbp-B0h] BYREF
  AM_MEDIA_TYPE pAMType; // [rsp+60h] [rbp-A0h] BYREF
  AM_MEDIA_TYPE Buf1; // [rsp+C0h] [rbp-40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v33, "CACMCodecStreamHandler::CreateStream", 1313);
  memset_0(&pAMType, 0, sizeof(pAMType));
  memset_0(&Buf1, 0, sizeof(Buf1));
  if ( *((_DWORD *)this + 6) || (v3 = HRESULTFromMMRESULT(8u), v3 >= 0) )
  {
    v9 = (IMFMediaType *)*((_QWORD *)this + 4);
    guidFormatBlockType = GUID_00000000_0000_0000_0000_000000000000;
    v3 = MFInitAMMediaTypeFromMFMediaType(v9, &guidFormatBlockType, &pAMType);
    if ( v3 >= 0 )
    {
      v15 = (IMFMediaType *)*((_QWORD *)this + 5);
      guidFormatBlockType = GUID_00000000_0000_0000_0000_000000000000;
      v3 = MFInitAMMediaTypeFromMFMediaType(v15, &guidFormatBlockType, &Buf1);
      if ( v3 >= 0 )
      {
        if ( !memcmp_0(&pAMType.formattype, &FORMAT_WaveFormatEx, 0x10u)
          && !memcmp_0(&Buf1.formattype, &FORMAT_WaveFormatEx, 0x10u) )
        {
          v23 = acmStreamOpen(
                  (LPHACMSTREAM)this + 2,
                  *((HACMDRIVER *)this + 1),
                  (LPWAVEFORMATEX)pAMType.pbFormat,
                  (LPWAVEFORMATEX)Buf1.pbFormat,
                  0,
                  0,
                  0,
                  4u);
          v3 = HRESULTFromMMRESULT(v23);
          if ( v3 < 0 )
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CACMCodecStreamHandler::CreateStream", 1336, v3);
            }
            if ( g_wppLevels )
            {
              v8 = 117;
              goto LABEL_58;
            }
          }
        }
        else
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          v3 = -1072875852;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)v31 + 499) != -1072875852 )
              CallStackContext::TraceFailure(v31, "CACMCodecStreamHandler::CreateStream", 1332, -1072875852);
          }
          if ( g_wppLevels )
          {
            v8 = 116;
            goto LABEL_58;
          }
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != v3 )
            CallStackContext::TraceFailure(v20, "CACMCodecStreamHandler::CreateStream", 1328, v3);
        }
        if ( g_wppLevels )
        {
          v8 = 115;
          goto LABEL_58;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != v3 )
          CallStackContext::TraceFailure(v14, "CACMCodecStreamHandler::CreateStream", 1327, v3);
      }
      if ( g_wppLevels )
      {
        v8 = 114;
        goto LABEL_58;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v4);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != v3 )
        CallStackContext::TraceFailure(v7, "CACMCodecStreamHandler::CreateStream", 1324, v3);
    }
    if ( g_wppLevels )
    {
      v8 = 113;
LABEL_58:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids, this, v3);
    }
  }
  CoTaskMemFree(pAMType.pbFormat);
  CoTaskMemFree(Buf1.pbFormat);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802e1398  push    rbp
0x1802e139a  push    rbx
0x1802e139b  push    rdi
0x1802e139c  push    r14
0x1802e139e  lea     rbp, [rsp-38h]
0x1802e13a3  sub     rsp, 138h
0x1802e13aa  mov     rax, cs:__security_cookie
0x1802e13b1  xor     rax, rsp
0x1802e13b4  mov     [rbp+50h+var_30], rax
0x1802e13b8  mov     rdi, rcx
0x1802e13bb  lea     r14, aCacmcodecstrea_2; "CACMCodecStreamHandler::CreateStream"
0x1802e13c2  mov     rdx, r14; char *
0x1802e13c5  lea     rcx, [rsp+150h+var_110]; this
0x1802e13ca  mov     r8d, 521h; int
0x1802e13d0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802e13d5  mov     ebx, 58h ; 'X'
0x1802e13da  lea     rcx, [rsp+150h+pAMType]; void *
0x1802e13df  mov     r8d, ebx; Size
0x1802e13e2  xor     edx, edx; Val
0x1802e13e4  call    memset_0
0x1802e13e9  mov     r8d, ebx; Size
0x1802e13ec  lea     rcx, [rbp+50h+Buf1]; void *
0x1802e13f0  xor     edx, edx; Val
0x1802e13f2  call    memset_0
0x1802e13f7  cmp     dword ptr [rdi+18h], 0
0x1802e13fb  jnz     loc_1802E14A5
0x1802e1401  lea     ecx, [rbx-50h]; unsigned int
0x1802e1404  call    ?HRESULTFromMMRESULT@@YAJI@Z; HRESULTFromMMRESULT(uint)
0x1802e1409  mov     ebx, eax
0x1802e140b  test    eax, eax
0x1802e140d  jns     loc_1802E14A5
0x1802e1413  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e141a  test    rcx, rcx
0x1802e141d  jnz     short loc_1802E1467
0x1802e141f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e1426  nop     dword ptr [rax+rax+00h]
0x1802e142b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e1432  mov     rcx, rax
0x1802e1435  test    rax, rax
0x1802e1438  jz      short loc_1802E1459
0x1802e143a  mov     rax, [rax]
0x1802e143d  mov     edx, 7F0h
0x1802e1442  mov     rax, [rax+8]
0x1802e1446  call    cs:__guard_dispatch_icall_fptr
0x1802e144c  test    eax, eax
0x1802e144e  jz      short loc_1802E1459
0x1802e1450  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e1457  jmp     short loc_1802E1467
0x1802e1459  lea     rcx, qword_1803CE250; this
0x1802e1460  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e1467  cmp     byte ptr [rcx+8], 0
0x1802e146b  jz      short loc_1802E148E
0x1802e146d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e1472  cmp     [rax+7CCh], ebx
0x1802e1478  jz      short loc_1802E148E
0x1802e147a  mov     r9d, ebx; int
0x1802e147d  mov     r8d, 52Ch; int
0x1802e1483  mov     rdx, r14; char *
0x1802e1486  mov     rcx, rax; this
0x1802e1489  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e148e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e1495  jb      loc_1802E17F3
0x1802e149b  mov     edx, 71h ; 'q'
0x1802e14a0  jmp     loc_1802E17D5
0x1802e14a5  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1802e14ac  mov     rcx, [rdi+20h]; pMFType
0x1802e14b0  lea     r8, [rsp+150h+pAMType]; pAMType
0x1802e14b5  lea     rdx, [rsp+150h+guidFormatBlockType]; guidFormatBlockType
0x1802e14ba  movdqu  xmmword ptr [rsp+150h+guidFormatBlockType.Data1], xmm0
0x1802e14c0  call    cs:__imp_MFInitAMMediaTypeFromMFMediaType
0x1802e14c7  nop     dword ptr [rax+rax+00h]
0x1802e14cc  mov     ebx, eax
0x1802e14ce  test    eax, eax
0x1802e14d0  jns     loc_1802E1568
0x1802e14d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e14dd  test    rcx, rcx
0x1802e14e0  jnz     short loc_1802E152A
0x1802e14e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e14e9  nop     dword ptr [rax+rax+00h]
0x1802e14ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e14f5  mov     rcx, rax
0x1802e14f8  test    rax, rax
0x1802e14fb  jz      short loc_1802E151C
0x1802e14fd  mov     rax, [rax]
0x1802e1500  mov     edx, 7F0h
0x1802e1505  mov     rax, [rax+8]
0x1802e1509  call    cs:__guard_dispatch_icall_fptr
0x1802e150f  test    eax, eax
0x1802e1511  jz      short loc_1802E151C
0x1802e1513  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e151a  jmp     short loc_1802E152A
0x1802e151c  lea     rcx, qword_1803CE250; this
0x1802e1523  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e152a  cmp     byte ptr [rcx+8], 0
0x1802e152e  jz      short loc_1802E1551
0x1802e1530  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e1535  cmp     [rax+7CCh], ebx
0x1802e153b  jz      short loc_1802E1551
0x1802e153d  mov     r9d, ebx; int
0x1802e1540  mov     r8d, 52Fh; int
0x1802e1546  mov     rdx, r14; char *
0x1802e1549  mov     rcx, rax; this
0x1802e154c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e1551  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e1558  jb      loc_1802E17F3
0x1802e155e  mov     edx, 72h ; 'r'
0x1802e1563  jmp     loc_1802E17D5
0x1802e1568  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1802e156f  mov     rcx, [rdi+28h]; pMFType
0x1802e1573  lea     r8, [rbp+50h+Buf1]; pAMType
0x1802e1577  lea     rdx, [rsp+150h+guidFormatBlockType]; guidFormatBlockType
0x1802e157c  movdqu  xmmword ptr [rsp+150h+guidFormatBlockType.Data1], xmm0
0x1802e1582  call    cs:__imp_MFInitAMMediaTypeFromMFMediaType
0x1802e1589  nop     dword ptr [rax+rax+00h]
0x1802e158e  mov     ebx, eax
0x1802e1590  test    eax, eax
0x1802e1592  jns     loc_1802E162A
0x1802e1598  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e159f  test    rcx, rcx
0x1802e15a2  jnz     short loc_1802E15EC
0x1802e15a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e15ab  nop     dword ptr [rax+rax+00h]
0x1802e15b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e15b7  mov     rcx, rax
0x1802e15ba  test    rax, rax
0x1802e15bd  jz      short loc_1802E15DE
0x1802e15bf  mov     rax, [rax]
0x1802e15c2  mov     edx, 7F0h
0x1802e15c7  mov     rax, [rax+8]
0x1802e15cb  call    cs:__guard_dispatch_icall_fptr
0x1802e15d1  test    eax, eax
0x1802e15d3  jz      short loc_1802E15DE
0x1802e15d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e15dc  jmp     short loc_1802E15EC
0x1802e15de  lea     rcx, qword_1803CE250; this
0x1802e15e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e15ec  cmp     byte ptr [rcx+8], 0
0x1802e15f0  jz      short loc_1802E1613
0x1802e15f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e15f7  cmp     [rax+7CCh], ebx
0x1802e15fd  jz      short loc_1802E1613
0x1802e15ff  mov     r9d, ebx; int
0x1802e1602  mov     r8d, 530h; int
0x1802e1608  mov     rdx, r14; char *
0x1802e160b  mov     rcx, rax; this
0x1802e160e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e1613  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e161a  jb      loc_1802E17F3
0x1802e1620  mov     edx, 73h ; 's'
0x1802e1625  jmp     loc_1802E17D5
0x1802e162a  mov     ebx, 10h
0x1802e162f  lea     rdx, FORMAT_WaveFormatEx; Buf2
0x1802e1636  mov     r8d, ebx; Size
0x1802e1639  lea     rcx, [rbp+50h+pAMType.formattype]; Buf1
0x1802e163d  call    memcmp_0
0x1802e1642  test    eax, eax
0x1802e1644  jnz     loc_1802E1747
0x1802e164a  mov     r8d, ebx; Size
0x1802e164d  lea     rdx, FORMAT_WaveFormatEx; Buf2
0x1802e1654  lea     rcx, [rbp+50h+Buf1.formattype]; Buf1
0x1802e1658  call    memcmp_0
0x1802e165d  test    eax, eax
0x1802e165f  jnz     loc_1802E1747
0x1802e1665  mov     r9, [rbp+50h+Buf1.pbFormat]; pwfxDst
0x1802e1669  lea     rcx, [rdi+10h]; phas
0x1802e166d  mov     r8, [rbp+50h+pAMType.pbFormat]; pwfxSrc
0x1802e1671  mov     rdx, [rdi+8]; had
0x1802e1675  mov     [rsp+150h+fdwOpen], 4; fdwOpen
0x1802e167d  mov     [rsp+150h+dwInstance], 0; dwInstance
0x1802e1686  mov     [rsp+150h+dwCallback], 0; dwCallback
0x1802e168f  mov     [rsp+150h+pwfltr], 0; pwfltr
0x1802e1698  call    cs:__imp_acmStreamOpen
0x1802e169f  nop     dword ptr [rax+rax+00h]
0x1802e16a4  mov     ecx, eax; unsigned int
0x1802e16a6  call    ?HRESULTFromMMRESULT@@YAJI@Z; HRESULTFromMMRESULT(uint)
0x1802e16ab  mov     ebx, eax
0x1802e16ad  test    eax, eax
0x1802e16af  jns     loc_1802E17F3
0x1802e16b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e16bc  test    rcx, rcx
0x1802e16bf  jnz     short loc_1802E1709
0x1802e16c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e16c8  nop     dword ptr [rax+rax+00h]
0x1802e16cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e16d4  mov     rcx, rax
0x1802e16d7  test    rax, rax
0x1802e16da  jz      short loc_1802E16FB
0x1802e16dc  mov     rax, [rax]
0x1802e16df  mov     edx, 7F0h
0x1802e16e4  mov     rax, [rax+8]
0x1802e16e8  call    cs:__guard_dispatch_icall_fptr
0x1802e16ee  test    eax, eax
0x1802e16f0  jz      short loc_1802E16FB
0x1802e16f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e16f9  jmp     short loc_1802E1709
0x1802e16fb  lea     rcx, qword_1803CE250; this
0x1802e1702  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e1709  cmp     byte ptr [rcx+8], 0
0x1802e170d  jz      short loc_1802E1730
0x1802e170f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e1714  cmp     [rax+7CCh], ebx
0x1802e171a  jz      short loc_1802E1730
0x1802e171c  mov     r9d, ebx; int
0x1802e171f  mov     r8d, 538h; int
0x1802e1725  mov     rdx, r14; char *
0x1802e1728  mov     rcx, rax; this
0x1802e172b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e1730  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e1737  jb      loc_1802E17F3
0x1802e173d  mov     edx, 75h ; 'u'
0x1802e1742  jmp     loc_1802E17D5
0x1802e1747  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e174e  mov     ebx, 0C00D36B4h
0x1802e1753  test    rcx, rcx
0x1802e1756  jnz     short loc_1802E17A0
0x1802e1758  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802e175f  nop     dword ptr [rax+rax+00h]
0x1802e1764  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e176b  mov     rcx, rax
0x1802e176e  test    rax, rax
0x1802e1771  jz      short loc_1802E1792
0x1802e1773  mov     rax, [rax]
0x1802e1776  mov     edx, 7F0h
0x1802e177b  mov     rax, [rax+8]
0x1802e177f  call    cs:__guard_dispatch_icall_fptr
0x1802e1785  test    eax, eax
0x1802e1787  jz      short loc_1802E1792
0x1802e1789  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e1790  jmp     short loc_1802E17A0
0x1802e1792  lea     rcx, qword_1803CE250; this
0x1802e1799  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802e17a0  cmp     byte ptr [rcx+8], 0
0x1802e17a4  jz      short loc_1802E17C7
0x1802e17a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802e17ab  cmp     [rax+7CCh], ebx
0x1802e17b1  jz      short loc_1802E17C7
0x1802e17b3  mov     r9d, ebx; int
0x1802e17b6  mov     r8d, 534h; int
0x1802e17bc  mov     rdx, r14; char *
0x1802e17bf  mov     rcx, rax; this
0x1802e17c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802e17c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802e17ce  jb      short loc_1802E17F3
0x1802e17d0  mov     edx, 74h ; 't'
0x1802e17d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1802e17dc  lea     r8, WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids
0x1802e17e3  mov     r9, rdi
0x1802e17e6  mov     dword ptr [rsp+150h+pwfltr], ebx
0x1802e17ea  mov     rcx, [rcx+10h]
0x1802e17ee  call    WPP_SF_qD
0x1802e17f3  mov     rcx, [rbp+50h+pAMType.pbFormat]; pv
0x1802e17f7  call    cs:__imp_CoTaskMemFree
0x1802e17fe  nop     dword ptr [rax+rax+00h]
0x1802e1803  mov     rcx, [rbp+50h+Buf1.pbFormat]; pv
0x1802e1807  call    cs:__imp_CoTaskMemFree
0x1802e180e  nop     dword ptr [rax+rax+00h]
0x1802e1813  lea     rcx, [rsp+150h+var_110]; this
0x1802e1818  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1802e181d  mov     eax, ebx
0x1802e181f  mov     rcx, [rbp+50h+var_30]
0x1802e1823  xor     rcx, rsp; StackCookie
0x1802e1826  call    __security_check_cookie
0x1802e182b  add     rsp, 138h
0x1802e1832  pop     r14
0x1802e1834  pop     rdi
0x1802e1835  pop     rbx
0x1802e1836  pop     rbp
0x1802e1837  retn
```
