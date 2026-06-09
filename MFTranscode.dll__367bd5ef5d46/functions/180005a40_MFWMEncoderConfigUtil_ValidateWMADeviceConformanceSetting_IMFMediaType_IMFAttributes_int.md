# MFWMEncoderConfigUtil::ValidateWMADeviceConformanceSetting(IMFMediaType *,IMFAttributes *,int *)

- ea: `0x180005a40`
- end: `0x180005ec4`
- name: `?ValidateWMADeviceConformanceSetting@MFWMEncoderConfigUtil@@YAJPEAUIMFMediaType@@PEAUIMFAttributes@@PEAH@Z`
- size: `1156`
- prototype: `__int64 __fastcall(MFWMEncoderConfigUtil *__hidden this, struct IMFMediaType *, struct IMFAttributes *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005290`

## callees

- `0x1800035c0`
- `0x180005a40`
- `0x180009320`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x18002bc50`
- `0x18004f3c8`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005e87`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005a9d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e10`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005a9d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005de2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005ac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005c32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005d28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005e36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005ac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005c32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005d28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005e36`

## string_xrefs

- `0x180005a7a`: `MFWMEncoderConfigUtil::ValidateWMADeviceConformanceSetting`

## pseudocode

```c
__int64 __fastcall MFWMEncoderConfigUtil::ValidateWMADeviceConformanceSetting(
        MFWMEncoderConfigUtil *this,
        struct IMFMediaType *a2,
        struct IMFAttributes *a3,
        int *a4)
{
  CallStackTracing *v7; // rbx
  char *v8; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // ebp
  __int64 v18; // rdx
  unsigned int i; // edx
  unsigned __int16 *v20; // rax
  __int64 v21; // rbx
  int v22; // r8d
  int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v34; // rbx
  CallStackContext *v35; // rdi
  DWORD v36; // esi
  CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rax
  int v42; // eax
  int v43; // eax
  LPVOID pv[9]; // [rsp+30h] [rbp-48h] BYREF
  int v46; // [rsp+88h] [rbp+10h] BYREF
  int v47; // [rsp+90h] [rbp+18h] BYREF
  int v48; // [rsp+98h] [rbp+20h] BYREF

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v7 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v8 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v7 + 3));
    if ( Value )
    {
      v8 = Value;
    }
    else if ( !GetLastError() )
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      v14 = (*(__int64 (__fastcall **)(__int64 *))*v12)(v12);
      if ( v14 )
        v8 = (char *)v14;
    }
    SetLastError(LastError);
    v15 = *((unsigned int *)v8 + 497);
    if ( (unsigned int)v15 < *((_DWORD *)v8 + 498) )
    {
      v16 = 2 * v15;
      *(_QWORD *)&v8[8 * v16] = "MFWMEncoderConfigUtil::ValidateWMADeviceConformanceSetting";
      *(_DWORD *)&v8[8 * v16 + 8] = 395;
    }
    ++*((_DWORD *)v8 + 497);
  }
  pv[0] = 0;
  v17 = 0;
  v48 = 0;
  v46 = 0;
  v47 = 0;
  LODWORD(a3->lpVtbl) = 0;
  if ( a2 )
  {
    if ( ((int (__fastcall *)(struct IMFMediaType *, const IID *, LPVOID *, int *))a2->lpVtbl->GetAllocatedString)(
           a2,
           &MF_TRANSCODE_ENCODINGPROFILE,
           pv,
           &v48) >= 0 )
    {
      for ( i = 0; i < 3; ++i )
      {
        v20 = (unsigned __int16 *)pv[0];
        v21 = 3LL * i;
        do
        {
          v22 = *(unsigned __int16 *)((char *)v20 + (char *)(&off_18005DA50)[v21] - (char *)pv[0]);
          v23 = *v20 - v22;
          if ( v23 )
            break;
          ++v20;
        }
        while ( v22 );
        if ( !v23 )
        {
          v17 = (*(__int64 (__fastcall **)(MFWMEncoderConfigUtil *, const GUID *, int *))(*(_QWORD *)this + 56LL))(
                  this,
                  &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
                  &v46);
          if ( v17 >= 0 )
          {
            v29 = (unsigned int)(8 * v46) >> 10;
            if ( v29 >= *((_DWORD *)&off_18005DA50 + 2 * v21 + 2) && v29 <= *((_DWORD *)&off_18005DA50 + 2 * v21 + 3) )
            {
              if ( !LODWORD((&off_18005DA50)[v21 + 1]) )
                goto LABEL_59;
              v17 = (*(__int64 (__fastcall **)(MFWMEncoderConfigUtil *, const GUID *, int *))(*(_QWORD *)this + 56LL))(
                      this,
                      &MF_MT_AUDIO_SAMPLES_PER_SECOND,
                      &v47);
              if ( v17 >= 0 )
              {
                if ( v47 == LODWORD((&off_18005DA50)[v21 + 1]) )
                  goto LABEL_59;
              }
              else
              {
                if ( !CallStackTracing::s_wpInstance )
                {
                  v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v31, v30);
                  CallStackTracing::s_wpInstance = v32;
                  if ( !v32
                    || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                  {
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != v17 )
                    CallStackContext::TraceFailure(
                      ThreadRelativeContext,
                      "MFWMEncoderConfigUtil::ValidateWMADeviceConformanceSetting",
                      464,
                      v17);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v28 = 36;
                  goto LABEL_40;
                }
              }
            }
          }
          else
          {
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v24);
              CallStackTracing::s_wpInstance = v26;
              if ( !v26
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v27 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v27 + 499) != v17 )
                CallStackContext::TraceFailure(
                  v27,
                  "MFWMEncoderConfigUtil::ValidateWMADeviceConformanceSetting",
                  451,
                  v17);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v28 = 35;
LABEL_40:
              WPP_SF_qd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v28,
                WPP_75ed2cd6c0a63dd9c3db1bb12c6cd391_Traceguids,
                0,
                v17);
              goto LABEL_60;
            }
          }
          goto LABEL_60;
        }
      }
      if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() < 0x10u )
        goto LABEL_59;
      v18 = 34;
      goto LABEL_58;
    }
    if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() >= 0x10u )
    {
      v18 = 33;
      goto LABEL_58;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() >= 0x10u )
  {
    v18 = 32;
LABEL_58:
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), v18, WPP_75ed2cd6c0a63dd9c3db1bb12c6cd391_Traceguids);
  }
LABEL_59:
  LODWORD(a3->lpVtbl) = 1;
LABEL_60:
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  v34 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v35 = (CallStackTracing *)((char *)CallStackTracing::s_wpInstance + 208);
    v36 = GetLastError();
    v37 = (CallStackContext *)TlsGetValue(*((_DWORD *)v34 + 3));
    if ( v37 )
    {
      v35 = v37;
    }
    else if ( !GetLastError() )
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      v41 = (*(__int64 (__fastcall **)(__int64 *))*v39)(v39);
      if ( v41 )
        v35 = (CallStackContext *)v41;
    }
    SetLastError(v36);
    v42 = *((_DWORD *)v35 + 497);
    if ( v42 )
    {
      v43 = v42 - 1;
      *((_DWORD *)v35 + 497) = v43;
      if ( !v43 )
        CallStackContext::ClearState(v35);
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180005a40  mov     [rsp+arg_0], rbx
0x180005a45  push    rbp
0x180005a46  push    rsi
0x180005a47  push    rdi
0x180005a48  push    r12
0x180005a4a  push    r13
0x180005a4c  push    r14
0x180005a4e  push    r15
0x180005a50  sub     rsp, 40h
0x180005a54  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180005a5c  mov     rsi, r8
0x180005a5f  mov     r14, rdx
0x180005a62  mov     r15, rcx
0x180005a65  jnz     short loc_180005A6C
0x180005a67  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180005a6c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005a73  lea     r13, qword_180069A90
0x180005a7a  lea     r12, aMfwmencodercon; "MFWMEncoderConfigUtil::ValidateWMADevic"...
0x180005a81  cmp     byte ptr [rbx+8], 0
0x180005a85  jz      loc_180005B3D
0x180005a8b  lea     rdi, [rbx+0D0h]
0x180005a92  call    cs:__imp_GetLastError
0x180005a98  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180005a9b  mov     ebp, eax
0x180005a9d  call    cs:__imp_TlsGetValue
0x180005aa3  test    rax, rax
0x180005aa6  jz      short loc_180005AAD
0x180005aa8  mov     rdi, rax
0x180005aab  jmp     short loc_180005B12
0x180005aad  call    cs:__imp_GetLastError
0x180005ab3  test    eax, eax
0x180005ab5  jnz     short loc_180005B12
0x180005ab7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005abe  test    rcx, rcx
0x180005ac1  jnz     short loc_180005B00
0x180005ac3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180005ac9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180005ad0  mov     rcx, rax
0x180005ad3  test    rax, rax
0x180005ad6  jz      short loc_180005AF6
0x180005ad8  mov     rax, [rax]
0x180005adb  mov     edx, 7F0h
0x180005ae0  mov     rax, [rax+8]
0x180005ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae9  test    eax, eax
0x180005aeb  jz      short loc_180005AF6
0x180005aed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005af4  jmp     short loc_180005B00
0x180005af6  mov     rcx, r13
0x180005af9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180005b00  mov     rax, [rcx]
0x180005b03  mov     rax, [rax]
0x180005b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0b  test    rax, rax
0x180005b0e  cmovnz  rdi, rax
0x180005b12  mov     ecx, ebp; dwErrCode
0x180005b14  call    cs:__imp_SetLastError
0x180005b1a  mov     eax, [rdi+7C4h]
0x180005b20  cmp     eax, [rdi+7C8h]
0x180005b26  jnb     short loc_180005B37
0x180005b28  add     rax, rax
0x180005b2b  mov     [rdi+rax*8], r12
0x180005b2f  mov     dword ptr [rdi+rax*8+8], 18Bh
0x180005b37  inc     dword ptr [rdi+7C4h]
0x180005b3d  xor     edi, edi
0x180005b3f  mov     [rsp+78h+pv], rdi
0x180005b44  mov     ebp, edi
0x180005b46  mov     [rsp+78h+arg_18], edi
0x180005b4d  mov     [rsp+78h+arg_8], edi
0x180005b54  mov     [rsp+78h+arg_10], edi
0x180005b5b  mov     [rsi], edi
0x180005b5d  test    r14, r14
0x180005b60  jnz     short loc_180005B79
0x180005b62  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x180005b67  cmp     al, 10h
0x180005b69  jb      loc_180005DD2
0x180005b6f  mov     edx, 20h ; ' '
0x180005b74  jmp     loc_180005DBB
0x180005b79  mov     rax, [r14]
0x180005b7c  lea     r9, [rsp+78h+arg_18]
0x180005b84  lea     r8, [rsp+78h+pv]
0x180005b89  mov     rcx, r14
0x180005b8c  lea     rdx, MF_TRANSCODE_ENCODINGPROFILE
0x180005b93  mov     rax, [rax+68h]
0x180005b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b9c  test    eax, eax
0x180005b9e  jns     short loc_180005BB7
0x180005ba0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x180005ba5  cmp     al, 10h
0x180005ba7  jb      loc_180005DD2
0x180005bad  mov     edx, 21h ; '!'
0x180005bb2  jmp     loc_180005DBB
0x180005bb7  mov     edx, edi
0x180005bb9  lea     r14, off_18005DA50; "L1"
0x180005bc0  cmp     edx, 3
0x180005bc3  jnb     loc_180005DAD
0x180005bc9  mov     eax, edx
0x180005bcb  lea     rcx, [rax+rax*2]
0x180005bcf  mov     rax, [rsp+78h+pv]
0x180005bd4  lea     rbx, ds:0[rcx*8]
0x180005bdc  mov     r9, [rbx+r14]
0x180005be0  sub     r9, rax
0x180005be3  movzx   ecx, word ptr [rax]
0x180005be6  movzx   r8d, word ptr [rax+r9]
0x180005beb  sub     ecx, r8d
0x180005bee  jnz     short loc_180005BF9
0x180005bf0  add     rax, 2
0x180005bf4  test    r8d, r8d
0x180005bf7  jnz     short loc_180005BE3
0x180005bf9  test    ecx, ecx
0x180005bfb  jz      short loc_180005C01
0x180005bfd  inc     edx
0x180005bff  jmp     short loc_180005BC0
0x180005c01  mov     rax, [r15]
0x180005c04  lea     r8, [rsp+78h+arg_8]
0x180005c0c  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x180005c13  mov     rcx, r15
0x180005c16  mov     rax, [rax+38h]
0x180005c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1f  mov     ebp, eax
0x180005c21  test    eax, eax
0x180005c23  jns     loc_180005CC9
0x180005c29  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180005c30  jnz     short loc_180005C63
0x180005c32  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180005c38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180005c3f  mov     rcx, rax
0x180005c42  test    rax, rax
0x180005c45  jz      short loc_180005C5C
0x180005c47  mov     rdx, [rax]
0x180005c4a  mov     rax, [rdx+8]
0x180005c4e  mov     edx, 7F0h
0x180005c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c58  test    eax, eax
0x180005c5a  jnz     short loc_180005C63
0x180005c5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180005c63  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005c6a  cmp     [rbx+8], dil
0x180005c6e  jz      short loc_180005C94
0x180005c70  mov     rcx, rbx; this
0x180005c73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180005c78  cmp     [rax+7CCh], ebp
0x180005c7e  jz      short loc_180005C94
0x180005c80  mov     r9d, ebp; int
0x180005c83  mov     r8d, 1C3h; int
0x180005c89  mov     rdx, r12; char *
0x180005c8c  mov     rcx, rax; this
0x180005c8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180005c94  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180005c99  cmp     al, 1
0x180005c9b  jb      loc_180005DD8
0x180005ca1  mov     edx, 23h ; '#'
0x180005ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cad  lea     r8, WPP_75ed2cd6c0a63dd9c3db1bb12c6cd391_Traceguids
0x180005cb4  xor     r9d, r9d
0x180005cb7  mov     [rsp+78h+var_58], ebp
0x180005cbb  mov     rcx, [rcx+10h]
0x180005cbf  call    WPP_SF_qd
0x180005cc4  jmp     loc_180005DD8
0x180005cc9  mov     eax, [rsp+78h+arg_8]
0x180005cd0  lea     eax, ds:0[rax*8]
0x180005cd7  shr     eax, 0Ah
0x180005cda  cmp     eax, [rbx+r14+8]
0x180005cdf  jb      loc_180005DD8
0x180005ce5  cmp     eax, [rbx+r14+0Ch]
0x180005cea  ja      loc_180005DD8
0x180005cf0  cmp     [rbx+r14+10h], edi
0x180005cf5  jz      loc_180005DD2
0x180005cfb  mov     rax, [r15]
0x180005cfe  lea     r8, [rsp+78h+arg_10]
0x180005d06  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180005d0d  mov     rcx, r15
0x180005d10  mov     rax, [rax+38h]
0x180005d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d19  mov     ebp, eax
0x180005d1b  test    eax, eax
0x180005d1d  jns     short loc_180005D9D
0x180005d1f  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180005d26  jnz     short loc_180005D59
0x180005d28  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180005d2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180005d35  mov     rcx, rax
0x180005d38  test    rax, rax
0x180005d3b  jz      short loc_180005D52
0x180005d3d  mov     rax, [rax]
0x180005d40  mov     edx, 7F0h
0x180005d45  mov     rax, [rax+8]
0x180005d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4e  test    eax, eax
0x180005d50  jnz     short loc_180005D59
0x180005d52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180005d59  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005d60  cmp     [rbx+8], dil
0x180005d64  jz      short loc_180005D8A
0x180005d66  mov     rcx, rbx; this
0x180005d69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180005d6e  cmp     [rax+7CCh], ebp
0x180005d74  jz      short loc_180005D8A
0x180005d76  mov     r9d, ebp; int
0x180005d79  mov     r8d, 1D0h; int
0x180005d7f  mov     rdx, r12; char *
0x180005d82  mov     rcx, rax; this
0x180005d85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180005d8a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180005d8f  cmp     al, 1
0x180005d91  jb      short loc_180005DD8
0x180005d93  mov     edx, 24h ; '$'
0x180005d98  jmp     loc_180005CA6
0x180005d9d  mov     eax, [rbx+r14+10h]
0x180005da2  cmp     [rsp+78h+arg_10], eax
0x180005da9  jz      short loc_180005DD2
0x180005dab  jmp     short loc_180005DD8
0x180005dad  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x180005db2  cmp     al, 10h
0x180005db4  jb      short loc_180005DD2
0x180005db6  mov     edx, 22h ; '"'
0x180005dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dc2  lea     r8, WPP_75ed2cd6c0a63dd9c3db1bb12c6cd391_Traceguids
0x180005dc9  mov     rcx, [rcx+38h]
0x180005dcd  call    WPP_SF_
0x180005dd2  mov     dword ptr [rsi], 1
0x180005dd8  mov     rcx, [rsp+78h+pv]; pv
0x180005ddd  test    rcx, rcx
0x180005de0  jz      short loc_180005DED
0x180005de2  call    cs:__imp_CoTaskMemFree
0x180005de8  mov     [rsp+78h+pv], rdi
0x180005ded  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005df4  cmp     [rbx+8], dil
0x180005df8  jz      loc_180005EAA
0x180005dfe  lea     rdi, [rbx+0D0h]
0x180005e05  call    cs:__imp_GetLastError
0x180005e0b  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180005e0e  mov     esi, eax
0x180005e10  call    cs:__imp_TlsGetValue
0x180005e16  test    rax, rax
0x180005e19  jz      short loc_180005E20
0x180005e1b  mov     rdi, rax
0x180005e1e  jmp     short loc_180005E85
0x180005e20  call    cs:__imp_GetLastError
0x180005e26  test    eax, eax
0x180005e28  jnz     short loc_180005E85
0x180005e2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005e31  test    rcx, rcx
0x180005e34  jnz     short loc_180005E73
0x180005e36  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180005e3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180005e43  mov     rcx, rax
0x180005e46  test    rax, rax
0x180005e49  jz      short loc_180005E69
0x180005e4b  mov     rax, [rax]
0x180005e4e  mov     edx, 7F0h
0x180005e53  mov     rax, [rax+8]
0x180005e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5c  test    eax, eax
0x180005e5e  jz      short loc_180005E69
0x180005e60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005e67  jmp     short loc_180005E73
0x180005e69  mov     rcx, r13
0x180005e6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180005e73  mov     rax, [rcx]
0x180005e76  mov     rax, [rax]
0x180005e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7e  test    rax, rax
0x180005e81  cmovnz  rdi, rax
0x180005e85  mov     ecx, esi; dwErrCode
0x180005e87  call    cs:__imp_SetLastError
0x180005e8d  mov     eax, [rdi+7C4h]
0x180005e93  test    eax, eax
0x180005e95  jz      short loc_180005EAA
0x180005e97  sub     eax, 1
0x180005e9a  mov     [rdi+7C4h], eax
0x180005ea0  jnz     short loc_180005EAA
0x180005ea2  mov     rcx, rdi; this
0x180005ea5  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180005eaa  mov     rbx, [rsp+78h+arg_0]
0x180005eb2  mov     eax, ebp
0x180005eb4  add     rsp, 40h
0x180005eb8  pop     r15
0x180005eba  pop     r14
0x180005ebc  pop     r13
0x180005ebe  pop     r12
0x180005ec0  pop     rdi
0x180005ec1  pop     rsi
0x180005ec2  pop     rbp
0x180005ec3  retn
```
