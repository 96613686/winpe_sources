# GetCodecSelectionDXVASetting(_GUID *,IMFMediaType *)

- ea: `0x1802c3f18`
- end: `0x1802c4601`
- name: `?GetCodecSelectionDXVASetting@@YAHPEAU_GUID@@PEAUIMFMediaType@@@Z`
- size: `1769`
- prototype: `__int64 __fastcall(struct _GUID *, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800ad538`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x180258390`
- `0x1802583a8`
- `0x180258480`
- `0x1802796e4`
- `0x1802c3f18`
- `0x1802c4f08`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802c4015`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802c450d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802c458b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802c4015`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802c450d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802c458b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802c3fae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802c3fdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802c44c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802c3fae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802c3fdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802c44c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802c4032`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802c45ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802c45c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802c4032`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802c45ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802c45c0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1802c4128`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1802c4128`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1802c4535`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1802c4535`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4077`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c414a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4214`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c42c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4376`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4420`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4077`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c414a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4214`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c42c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4376`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802c4420`

## pseudocode

```c
_BOOL8 __fastcall GetCodecSelectionDXVASetting(struct _GUID *a1, struct IMFMediaType *a2)
{
  BOOL v4; // ebx
  unsigned __int16 *v5; // r15
  int v6; // edi
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // r8
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rsi
  unsigned __int16 *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned __int64 v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v43; // rax
  BYTE v45[4]; // [rsp+30h] [rbp-99h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-95h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-91h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-8Dh] BYREF
  HKEY v49; // [rsp+40h] [rbp-89h] BYREF
  DWORD lpcbData; // [rsp+48h] [rbp-81h] BYREF
  DWORD v51; // [rsp+4Ch] [rbp-7Dh] BYREF
  HKEY hKey; // [rsp+50h] [rbp-79h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-71h] BYREF
  GUID iid; // [rsp+60h] [rbp-69h] BYREF
  GUID rguid; // [rsp+70h] [rbp-59h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-49h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v45, "GetCodecSelectionDXVASetting", 130);
  v4 = 1;
  phkResult = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  v5 = 0;
  cbData = 4;
  Type = 4;
  rguid = GUID_00000000_0000_0000_0000_000000000000;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows Media Foundation\\CodecSelection\\Transcode\\Decoder",
          0,
          1u,
          &phkResult) )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows Media Foundation\\CodecSelection",
           0,
           1u,
           &hKey) )
    {
      goto LABEL_6;
    }
    v6 = 0;
    if ( !RegQueryValueExW(hKey, L"DisableCodecSelection", 0, &Type, Data, &cbData) )
      LOBYTE(v6) = *(_DWORD *)Data != 0;
    RegCloseKey(hKey);
    if ( !v6 )
    {
LABEL_6:
      v8 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a2->lpVtbl->GetGUID)(
             a2,
             &MF_MT_SUBTYPE,
             &rguid);
      if ( v8 >= 0 )
      {
        v8 = StringFromGUID2(&rguid, sz, 39);
        if ( v8 >= 0 )
        {
          v19 = -1;
          do
            ++v19;
          while ( sz[v19] );
          v20 = v19 + 78;
          v21 = (unsigned __int16 *)operator new(saturated_mul(v19 + 78, 2u));
          v5 = v21;
          if ( v21 )
          {
            v27 = 2 * v20;
            v8 = StringCbCopyW(
                   v21,
                   v27,
                   L"Software\\Microsoft\\Windows Media Foundation\\CodecSelection\\Transcode\\Decoder");
            if ( v8 >= 0 )
            {
              v8 = StringCbCatW(v5, v27, L"\\");
              if ( v8 >= 0 )
              {
                v8 = StringCbCatW(v5, v27, sz);
                if ( v8 >= 0 )
                {
                  v49 = 0;
                  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 1u, &v49) )
                  {
                    v51 = 2;
                    lpcbData = 78;
                    if ( !RegQueryValueExW(v49, L"DEC", 0, &v51, (LPBYTE)sz, &lpcbData) )
                    {
                      iid = GUID_00000000_0000_0000_0000_000000000000;
                      if ( !IIDFromString(sz, &iid) )
                      {
                        v43 = *(_QWORD *)&iid.Data1 - *(_QWORD *)&a1->Data1;
                        if ( *(_QWORD *)&iid.Data1 == *(_QWORD *)&a1->Data1 )
                          v43 = *(_QWORD *)iid.Data4 - *(_QWORD *)a1->Data4;
                        if ( !v43 )
                        {
                          cbData = 4;
                          if ( !RegQueryValueExW(v49, L"DXVA", 0, &Type, Data, &cbData) )
                            v4 = *(_DWORD *)Data != 0;
                        }
                      }
                    }
                    RegCloseKey(v49);
                  }
                }
                else
                {
                  v40 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
                    CallStackTracing::s_wpInstance = v41;
                    if ( v41
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                    {
                      v40 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v40 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v40 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
                      CallStackContext::TraceFailure(ThreadRelativeContext, "GetCodecSelectionDXVASetting", 182, v8);
                  }
                  if ( g_wppLevels )
                  {
                    v13 = 15;
                    goto LABEL_17;
                  }
                }
              }
              else
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
                  CallStackTracing::s_wpInstance = v36;
                  if ( v36
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                  {
                    v35 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v35 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v35 + 8) )
                {
                  v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
                  if ( *((_DWORD *)v37 + 499) != v8 )
                    CallStackContext::TraceFailure(v37, "GetCodecSelectionDXVASetting", 181, v8);
                }
                if ( g_wppLevels )
                {
                  v13 = 14;
                  goto LABEL_17;
                }
              }
            }
            else
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
                CallStackTracing::s_wpInstance = v31;
                if ( v31
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v30 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                if ( *((_DWORD *)v32 + 499) != v8 )
                  CallStackContext::TraceFailure(v32, "GetCodecSelectionDXVASetting", 180, v8);
              }
              if ( g_wppLevels )
              {
                v13 = 13;
                goto LABEL_17;
              }
            }
          }
          else
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            v8 = -2147024882;
            if ( *((_BYTE *)v24 + 8) )
            {
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)v26 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v26, "GetCodecSelectionDXVASetting", 177, -2147024882);
            }
            if ( g_wppLevels )
            {
              v13 = 12;
              goto LABEL_17;
            }
          }
        }
        else
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
            CallStackTracing::s_wpInstance = v17;
            if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
            {
              v16 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
            if ( *((_DWORD *)v18 + 499) != v8 )
              CallStackContext::TraceFailure(v18, "GetCodecSelectionDXVASetting", 170, v8);
          }
          if ( g_wppLevels )
          {
            v13 = 11;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9);
          CallStackTracing::s_wpInstance = v11;
          if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
          {
            v10 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v10 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
          if ( *((_DWORD *)v12 + 499) != v8 )
            CallStackContext::TraceFailure(v12, "GetCodecSelectionDXVASetting", 169, v8);
        }
        if ( g_wppLevels )
        {
          v13 = 10;
LABEL_17:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_958ec45f6f7939c74fc78df0e65a92c3_Traceguids, 0, v8);
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  operator delete(v5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v45);
  return v4;
}

```

## disassembly

```asm
0x1802c3f18  push    rbp
0x1802c3f1a  push    rbx
0x1802c3f1b  push    rsi
0x1802c3f1c  push    rdi
0x1802c3f1d  push    r12
0x1802c3f1f  push    r13
0x1802c3f21  push    r14
0x1802c3f23  push    r15
0x1802c3f25  lea     rbp, [rsp-1Fh]
0x1802c3f2a  sub     rsp, 0E8h
0x1802c3f31  mov     rax, cs:__security_cookie
0x1802c3f38  xor     rax, rsp
0x1802c3f3b  mov     [rbp+57h+var_50], rax
0x1802c3f3f  mov     rsi, rdx
0x1802c3f42  lea     r13, aGetcodecselect; "GetCodecSelectionDXVASetting"
0x1802c3f49  mov     r14, rcx
0x1802c3f4c  mov     rdx, r13; char *
0x1802c3f4f  mov     r8d, 82h; int
0x1802c3f55  lea     rcx, [rsp+120h+var_F0]; this
0x1802c3f5a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802c3f5f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1802c3f66  xor     r12d, r12d
0x1802c3f69  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows Media Foun"...
0x1802c3f70  mov     ebx, 1
0x1802c3f75  mov     [rbp+57h+var_C8], r12
0x1802c3f79  mov     rdi, 0FFFFFFFF80000002h
0x1802c3f80  mov     [rbp+57h+hKey], r12
0x1802c3f84  mov     r9d, ebx; samDesired
0x1802c3f87  mov     dword ptr [rsp+120h+Data], r12d
0x1802c3f8c  xor     r8d, r8d; ulOptions
0x1802c3f8f  mov     rcx, rdi; hKey
0x1802c3f92  lea     eax, [rbx+3]
0x1802c3f95  mov     r15d, r12d
0x1802c3f98  mov     [rsp+120h+cbData], eax
0x1802c3f9c  mov     [rsp+120h+Type], eax
0x1802c3fa0  lea     rax, [rbp+57h+var_C8]
0x1802c3fa4  mov     [rsp+120h+phkResult], rax; phkResult
0x1802c3fa9  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1802c3fae  call    cs:__imp_RegOpenKeyExW
0x1802c3fb5  nop     dword ptr [rax+rax+00h]
0x1802c3fba  test    eax, eax
0x1802c3fbc  jnz     loc_1802C45B7
0x1802c3fc2  lea     rax, [rbp+57h+hKey]
0x1802c3fc6  mov     r9d, ebx; samDesired
0x1802c3fc9  xor     r8d, r8d; ulOptions
0x1802c3fcc  mov     [rsp+120h+phkResult], rax; phkResult
0x1802c3fd1  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows Media Foun"...
0x1802c3fd8  mov     rcx, rdi; hKey
0x1802c3fdb  call    cs:__imp_RegOpenKeyExW
0x1802c3fe2  nop     dword ptr [rax+rax+00h]
0x1802c3fe7  test    eax, eax
0x1802c3fe9  jnz     short loc_1802C4046
0x1802c3feb  mov     rcx, [rbp+57h+hKey]; hKey
0x1802c3fef  lea     rax, [rsp+120h+cbData]
0x1802c3ff4  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1802c3ff9  lea     r9, [rsp+120h+Type]; lpType
0x1802c3ffe  lea     rax, [rsp+120h+Data]
0x1802c4003  xor     r8d, r8d; lpReserved
0x1802c4006  lea     rdx, aDisablecodecse; "DisableCodecSelection"
0x1802c400d  mov     [rsp+120h+phkResult], rax; lpData
0x1802c4012  mov     edi, r12d
0x1802c4015  call    cs:__imp_RegQueryValueExW
0x1802c401c  nop     dword ptr [rax+rax+00h]
0x1802c4021  test    eax, eax
0x1802c4023  jnz     short loc_1802C402E
0x1802c4025  cmp     dword ptr [rsp+120h+Data], r12d
0x1802c402a  setnz   dil
0x1802c402e  mov     rcx, [rbp+57h+hKey]; hKey
0x1802c4032  call    cs:__imp_RegCloseKey
0x1802c4039  nop     dword ptr [rax+rax+00h]
0x1802c403e  test    edi, edi
0x1802c4040  jnz     loc_1802C45B7
0x1802c4046  mov     rax, [rsi]
0x1802c4049  lea     r8, [rbp+57h+rguid]
0x1802c404d  lea     rdx, MF_MT_SUBTYPE
0x1802c4054  mov     rcx, rsi
0x1802c4057  mov     rax, [rax+50h]
0x1802c405b  call    cs:__guard_dispatch_icall_fptr
0x1802c4061  mov     edi, eax
0x1802c4063  test    eax, eax
0x1802c4065  jns     loc_1802C411A
0x1802c406b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4072  test    rcx, rcx
0x1802c4075  jnz     short loc_1802C40BF
0x1802c4077  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802c407e  nop     dword ptr [rax+rax+00h]
0x1802c4083  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c408a  mov     rcx, rax
0x1802c408d  test    rax, rax
0x1802c4090  jz      short loc_1802C40B1
0x1802c4092  mov     rax, [rax]
0x1802c4095  mov     edx, 7F0h
0x1802c409a  mov     rax, [rax+8]
0x1802c409e  call    cs:__guard_dispatch_icall_fptr
0x1802c40a4  test    eax, eax
0x1802c40a6  jz      short loc_1802C40B1
0x1802c40a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c40af  jmp     short loc_1802C40BF
0x1802c40b1  lea     rcx, qword_1803CE250; this
0x1802c40b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c40bf  cmp     [rcx+8], r12b
0x1802c40c3  jz      short loc_1802C40E6
0x1802c40c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802c40ca  cmp     [rax+7CCh], edi
0x1802c40d0  jz      short loc_1802C40E6
0x1802c40d2  mov     r9d, edi; int
0x1802c40d5  mov     r8d, 0A9h; int
0x1802c40db  mov     rdx, r13; char *
0x1802c40de  mov     rcx, rax; this
0x1802c40e1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802c40e6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1802c40ec  jb      loc_1802C45B7
0x1802c40f2  mov     edx, 0Ah
0x1802c40f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c40fe  lea     r8, WPP_958ec45f6f7939c74fc78df0e65a92c3_Traceguids
0x1802c4105  xor     r9d, r9d
0x1802c4108  mov     dword ptr [rsp+120h+phkResult], edi
0x1802c410c  mov     rcx, [rcx+10h]
0x1802c4110  call    WPP_SF_qD
0x1802c4115  jmp     loc_1802C45B7
0x1802c411a  mov     r8d, 27h ; '''; cchMax
0x1802c4120  lea     rdx, [rbp+57h+sz]; lpsz
0x1802c4124  lea     rcx, [rbp+57h+rguid]; rguid
0x1802c4128  call    cs:__imp_StringFromGUID2
0x1802c412f  nop     dword ptr [rax+rax+00h]
0x1802c4134  mov     edi, eax
0x1802c4136  test    eax, eax
0x1802c4138  jns     loc_1802C41CF
0x1802c413e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4145  test    rcx, rcx
0x1802c4148  jnz     short loc_1802C4192
0x1802c414a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802c4151  nop     dword ptr [rax+rax+00h]
0x1802c4156  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c415d  mov     rcx, rax
0x1802c4160  test    rax, rax
0x1802c4163  jz      short loc_1802C4184
0x1802c4165  mov     rax, [rax]
0x1802c4168  mov     edx, 7F0h
0x1802c416d  mov     rax, [rax+8]
0x1802c4171  call    cs:__guard_dispatch_icall_fptr
0x1802c4177  test    eax, eax
0x1802c4179  jz      short loc_1802C4184
0x1802c417b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4182  jmp     short loc_1802C4192
0x1802c4184  lea     rcx, qword_1803CE250; this
0x1802c418b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4192  cmp     [rcx+8], r12b
0x1802c4196  jz      short loc_1802C41B9
0x1802c4198  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802c419d  cmp     [rax+7CCh], edi
0x1802c41a3  jz      short loc_1802C41B9
0x1802c41a5  mov     r9d, edi; int
0x1802c41a8  mov     r8d, 0AAh; int
0x1802c41ae  mov     rdx, r13; char *
0x1802c41b1  mov     rcx, rax; this
0x1802c41b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802c41b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1802c41bf  jb      loc_1802C45B7
0x1802c41c5  mov     edx, 0Bh
0x1802c41ca  jmp     loc_1802C40F7
0x1802c41cf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1802c41d3  lea     rdx, [rbp+57h+sz]
0x1802c41d7  mov     rax, rcx
0x1802c41da  inc     rax
0x1802c41dd  cmp     [rdx+rax*2], r12w
0x1802c41e2  jnz     short loc_1802C41DA
0x1802c41e4  lea     rsi, [rax+4Eh]
0x1802c41e8  mov     eax, 2
0x1802c41ed  mul     rsi
0x1802c41f0  cmovb   rax, rcx
0x1802c41f4  mov     rcx, rax; Size
0x1802c41f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802c41fc  mov     r15, rax
0x1802c41ff  test    rax, rax
0x1802c4202  jnz     loc_1802C429E
0x1802c4208  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c420f  test    rcx, rcx
0x1802c4212  jnz     short loc_1802C425C
0x1802c4214  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802c421b  nop     dword ptr [rax+rax+00h]
0x1802c4220  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4227  mov     rcx, rax
0x1802c422a  test    rax, rax
0x1802c422d  jz      short loc_1802C424E
0x1802c422f  mov     rax, [rax]
0x1802c4232  mov     edx, 7F0h
0x1802c4237  mov     rax, [rax+8]
0x1802c423b  call    cs:__guard_dispatch_icall_fptr
0x1802c4241  test    eax, eax
0x1802c4243  jz      short loc_1802C424E
0x1802c4245  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c424c  jmp     short loc_1802C425C
0x1802c424e  lea     rcx, qword_1803CE250; this
0x1802c4255  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c425c  mov     edi, 8007000Eh
0x1802c4261  cmp     [rcx+8], r12b
0x1802c4265  jz      short loc_1802C4288
0x1802c4267  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802c426c  cmp     [rax+7CCh], edi
0x1802c4272  jz      short loc_1802C4288
0x1802c4274  mov     r9d, edi; int
0x1802c4277  mov     r8d, 0B1h; int
0x1802c427d  mov     rdx, r13; char *
0x1802c4280  mov     rcx, rax; this
0x1802c4283  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802c4288  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1802c428e  jb      loc_1802C45B7
0x1802c4294  mov     edx, 0Ch
0x1802c4299  jmp     loc_1802C40F7
0x1802c429e  add     rsi, rsi
0x1802c42a1  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\Windows Media Foun"...
0x1802c42a8  mov     rdx, rsi; unsigned __int64
0x1802c42ab  mov     rcx, r15; unsigned __int16 *
0x1802c42ae  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1802c42b3  mov     edi, eax
0x1802c42b5  test    eax, eax
0x1802c42b7  jns     loc_1802C434E
0x1802c42bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c42c4  test    rcx, rcx
0x1802c42c7  jnz     short loc_1802C4311
0x1802c42c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802c42d0  nop     dword ptr [rax+rax+00h]
0x1802c42d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c42dc  mov     rcx, rax
0x1802c42df  test    rax, rax
0x1802c42e2  jz      short loc_1802C4303
0x1802c42e4  mov     rax, [rax]
0x1802c42e7  mov     edx, 7F0h
0x1802c42ec  mov     rax, [rax+8]
0x1802c42f0  call    cs:__guard_dispatch_icall_fptr
0x1802c42f6  test    eax, eax
0x1802c42f8  jz      short loc_1802C4303
0x1802c42fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4301  jmp     short loc_1802C4311
0x1802c4303  lea     rcx, qword_1803CE250; this
0x1802c430a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4311  cmp     [rcx+8], r12b
0x1802c4315  jz      short loc_1802C4338
0x1802c4317  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802c431c  cmp     [rax+7CCh], edi
0x1802c4322  jz      short loc_1802C4338
0x1802c4324  mov     r9d, edi; int
0x1802c4327  mov     r8d, 0B4h; int
0x1802c432d  mov     rdx, r13; char *
0x1802c4330  mov     rcx, rax; this
0x1802c4333  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802c4338  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1802c433e  jb      loc_1802C45B7
0x1802c4344  mov     edx, 0Dh
0x1802c4349  jmp     loc_1802C40F7
0x1802c434e  lea     r8, asc_18037A36C; "\\"
0x1802c4355  mov     rdx, rsi; unsigned __int64
0x1802c4358  mov     rcx, r15; unsigned __int16 *
0x1802c435b  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1802c4360  mov     edi, eax
0x1802c4362  test    eax, eax
0x1802c4364  jns     loc_1802C43FB
0x1802c436a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4371  test    rcx, rcx
0x1802c4374  jnz     short loc_1802C43BE
0x1802c4376  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802c437d  nop     dword ptr [rax+rax+00h]
0x1802c4382  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c4389  mov     rcx, rax
0x1802c438c  test    rax, rax
0x1802c438f  jz      short loc_1802C43B0
0x1802c4391  mov     rax, [rax]
0x1802c4394  mov     edx, 7F0h
0x1802c4399  mov     rax, [rax+8]
0x1802c439d  call    cs:__guard_dispatch_icall_fptr
0x1802c43a3  test    eax, eax
0x1802c43a5  jz      short loc_1802C43B0
0x1802c43a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c43ae  jmp     short loc_1802C43BE
0x1802c43b0  lea     rcx, qword_1803CE250; this
0x1802c43b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c43be  cmp     [rcx+8], r12b
0x1802c43c2  jz      short loc_1802C43E5
0x1802c43c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802c43c9  cmp     [rax+7CCh], edi
0x1802c43cf  jz      short loc_1802C43E5
0x1802c43d1  mov     r9d, edi; int
0x1802c43d4  mov     r8d, 0B5h; int
0x1802c43da  mov     rdx, r13; char *
0x1802c43dd  mov     rcx, rax; this
0x1802c43e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802c43e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1802c43eb  jb      loc_1802C45B7
0x1802c43f1  mov     edx, 0Eh
0x1802c43f6  jmp     loc_1802C40F7
0x1802c43fb  lea     r8, [rbp+57h+sz]; unsigned __int16 *
0x1802c43ff  mov     rdx, rsi; unsigned __int64
0x1802c4402  mov     rcx, r15; unsigned __int16 *
0x1802c4405  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1802c440a  mov     edi, eax
0x1802c440c  test    eax, eax
0x1802c440e  jns     loc_1802C44A5
0x1802c4414  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802c441b  test    rcx, rcx
  ... truncated ...
```
