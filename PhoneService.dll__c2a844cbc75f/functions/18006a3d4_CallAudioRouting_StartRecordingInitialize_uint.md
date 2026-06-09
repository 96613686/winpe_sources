# CallAudioRouting::_StartRecordingInitialize(uint)

- ea: `0x18006a3d4`
- end: `0x18006aa03`
- name: `?_StartRecordingInitialize@CallAudioRouting@@AEAAJI@Z`
- size: `1583`
- prototype: `__int64 __fastcall(CallAudioRouting *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b2c0`

## callees

- `0x1800056a0`
- `0x180006b44`
- `0x180006e94`
- `0x180057e48`
- `0x1800598f4`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006a3d4`
- `0x18007f9ec`
- `0x18008d936`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a404`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a404`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a424`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a4f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a5dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a696`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a4f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a5dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006a696`

## string_xrefs

- `0x18006a40a`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_StartRecordingInitialize(CallAudioRouting *this, unsigned int a2)
{
  __int64 v4; // rcx
  __int64 (__fastcall *v5)(_QWORD, int *, PCWSTR *); // rax
  int v6; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  __int64 (__fastcall *v14)(HSTRING, __int64 *); // rax
  BackTraceCollection *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  BackTraceCollection *v19; // rcx
  __int64 v20; // r9
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  HRESULT v24; // eax
  BackTraceCollection *v25; // rcx
  __int64 v26; // r9
  int v27; // eax
  BackTraceCollection *v28; // rcx
  HRESULT v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  int v32; // eax
  BackTraceCollection *v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // rbx
  int v36; // eax
  BackTraceCollection *v37; // rcx
  unsigned int v38; // r14d
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v43; // rsi
  int v44; // eax
  BackTraceCollection *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  CallAudioRouting *v50; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v51; // [rsp+38h] [rbp-C8h]
  unsigned int v52; // [rsp+40h] [rbp-C0h]
  __int64 v53; // [rsp+48h] [rbp-B8h]
  __int64 v54; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v55; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h] BYREF
  __int64 v58; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR sourceString; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v60; // [rsp+80h] [rbp-80h]
  __int16 v61; // [rsp+88h] [rbp-78h] BYREF
  __int64 v62; // [rsp+8Ah] [rbp-76h]
  int v63; // [rsp+92h] [rbp-6Eh]
  __int16 v64; // [rsp+96h] [rbp-6Ah]
  int v65; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v68; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v69; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v70; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v71; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v72; // [rsp+100h] [rbp+0h] BYREF

  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1747);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  sourceString = (PCWSTR)&v61;
  v62 = 0;
  v60 = (const WCHAR *)&v61;
  v5 = (__int64 (__fastcall *)(_QWORD, int *, PCWSTR *))*((_QWORD *)this + 7);
  v63 = 0;
  v64 = 0;
  v61 = 0;
  v65 = 0;
  v6 = v5(a2, &v65, &sourceString);
  v8 = v6;
  if ( v6 < 0 )
  {
    BackTraceCollection::Capture(v7, v6);
    v9 = 1751;
    v10 = 1;
LABEL_6:
    Log_HREvent_17(v8, v10, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v9);
LABEL_74:
    if ( sourceString != (PCWSTR)&v61 )
      operator delete((void *)sourceString);
    return v8;
  }
  if ( !v65 )
  {
    v8 = -2147418113;
    BackTraceCollection::Capture(v7, -2147418113);
    v9 = 1752;
LABEL_11:
    v10 = 0;
    goto LABEL_6;
  }
  if ( sourceString == v60 )
  {
    v9 = 1753;
    v8 = -2147418113;
    goto LABEL_11;
  }
  v56 = 0;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  string = 0;
  v11 = WindowsCreateStringReference(
          L"Windows.Media.Capture.MediaCaptureInitializationSettings",
          0x38u,
          &hstringHeader,
          &string);
  if ( v11 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
    __debugbreak();
  }
  v14 = (__int64 (__fastcall *)(HSTRING, __int64 *))*((_QWORD *)this + 8);
  v56 = 0;
  v54 = 0;
  v8 = v14(string, &v54);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_70;
  v16 = memcmp_0(&GUID_9782ba70_ea65_4900_9356_8ca887726884, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
  v17 = v54;
  if ( !v16 )
  {
    v56 = v54;
    goto LABEL_18;
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v54)(
         v54,
         &GUID_9782ba70_ea65_4900_9356_8ca887726884,
         &v56);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  if ( (v8 & 0x80000000) != 0 )
  {
LABEL_70:
    BackTraceCollection::Capture(v15, v8);
    v20 = 1758;
    goto LABEL_71;
  }
  v17 = v56;
LABEL_18:
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 80LL))(v17, 1);
  v8 = v18;
  if ( v18 < 0 )
  {
    BackTraceCollection::Capture(v19, v18);
    v20 = 1759;
LABEL_71:
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v20);
LABEL_72:
    v49 = v56;
    string = 0;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    goto LABEL_74;
  }
  memset(&v68, 0, sizeof(v68));
  v69 = 0;
  v21 = WindowsCreateStringReference(L"Windows.Media.MediaProperties.MediaEncodingProfile", 0x32u, &v68, &v69);
  if ( v21 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
    JUMPOUT(0x18006AA02LL);
  }
  v55 = 0;
  memset(&v72, 0, sizeof(v72));
  v24 = WindowsCreateStringReference(sourceString, v60 - sourceString, &v72, &v55);
  v8 = v24;
  if ( v24 < 0 )
  {
    BackTraceCollection::Capture(v25, v24);
    v26 = 1766;
LABEL_23:
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v26);
LABEL_24:
    v69 = 0;
    goto LABEL_72;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v56 + 48LL))(v56, v55);
  v8 = v27;
  if ( v27 < 0 )
  {
    BackTraceCollection::Capture(v28, v27);
    v26 = 1767;
    goto LABEL_23;
  }
  v57 = 0;
  memset(&v70, 0, sizeof(v70));
  v71 = 0;
  v29 = WindowsCreateStringReference(L"Windows.Media.Capture.MediaCapture", 0x22u, &v70, &v71);
  if ( v29 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
    __debugbreak();
  }
  v32 = CallAudioRouting::_ActivateInstance<Windows::Media::Capture::IMediaCapture>(this, v71, &v57);
  v8 = v32;
  if ( v32 < 0 )
  {
    BackTraceCollection::Capture(v33, v32);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1772);
    v34 = v57;
    v71 = 0;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    goto LABEL_24;
  }
  v35 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  if ( v35 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v35 + 8LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  v58 = 0;
  v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v57 + 56LL))(v57, v56, &v58);
  v38 = v36;
  if ( v36 < 0 )
  {
    BackTraceCollection::Capture(v37, v36);
    Log_HREvent_17(v38, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1778);
LABEL_35:
    v39 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    if ( v35 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v35 + 16LL))(v35);
    v40 = v57;
    v71 = 0;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v56;
    string = 0;
    v69 = 0;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    if ( sourceString != (PCWSTR)&v61 )
      operator delete((void *)sourceString);
    return v38;
  }
  v54 = 0;
  v50 = this;
  v51 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  if ( v35 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v35 + 8LL))(((unsigned __int64)this + 8) & -(__int64)(this != 0));
  v52 = a2;
  v53 = v57;
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 8LL))(v57);
  Microsoft::WRL::Callback_Windows::Foundation::IAsyncActionCompletedHandler__lambda_d66fa114b66bccbec792d3417aa6c740___(
    &v54,
    &v50);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( v51 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v51 + 16LL))(v51);
  v43 = v54;
  v44 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 48LL))(v58, v54);
  v38 = v44;
  if ( v44 < 0 )
  {
    BackTraceCollection::Capture(v45, v44);
    Log_HREvent_17(v38, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1811);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    goto LABEL_35;
  }
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  v46 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  if ( v35 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v35 + 16LL))(v35);
  v47 = v57;
  v71 = 0;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v56;
  v69 = 0;
  string = 0;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  if ( sourceString != (PCWSTR)&v61 )
    operator delete((void *)sourceString);
  return 0;
}

```

## disassembly

```asm
0x18006a3d4  mov     [rsp-8+arg_10], rbx
0x18006a3d9  push    rbp
0x18006a3da  push    rsi
0x18006a3db  push    rdi
0x18006a3dc  push    r12
0x18006a3de  push    r13
0x18006a3e0  push    r14
0x18006a3e2  push    r15
0x18006a3e4  lea     rbp, [rsp-20h]
0x18006a3e9  sub     rsp, 120h
0x18006a3f0  mov     rax, cs:__security_cookie
0x18006a3f7  xor     rax, rsp
0x18006a3fa  mov     [rbp+50h+var_38], rax
0x18006a3fe  mov     r15d, edx
0x18006a401  mov     rsi, rcx
0x18006a404  call    cs:__imp_GetCurrentThreadId
0x18006a40a  lea     r13, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006a411  cmp     [rsi+68h], eax
0x18006a414  jnz     short loc_18006A434
0x18006a416  mov     r8d, 6D3h
0x18006a41c  mov     rdx, r13
0x18006a41f  call    Log_AssertionEvent_9
0x18006a424  call    cs:__imp_GetCurrentThreadId
0x18006a42a  cmp     [rsi+68h], eax
0x18006a42d  jnz     short loc_18006A434
0x18006a42f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006a434  xor     r12d, r12d
0x18006a437  lea     rax, [rbp+50h+var_C8]
0x18006a43b  mov     [rsp+150h+sourceString], rax
0x18006a440  lea     r8, [rsp+150h+sourceString]
0x18006a445  lea     rax, [rbp+50h+var_C8]
0x18006a449  mov     [rbp+50h+var_C6], r12
0x18006a44d  mov     [rbp+50h+var_D0], rax
0x18006a451  lea     rdx, [rbp+50h+var_B8]
0x18006a455  mov     rax, [rsi+38h]
0x18006a459  mov     ecx, r15d
0x18006a45c  mov     [rbp+50h+var_BE], r12d
0x18006a460  mov     [rbp+50h+var_BA], r12w
0x18006a465  mov     [rbp+50h+var_C8], r12w
0x18006a46a  mov     [rbp+50h+var_B8], r12d
0x18006a46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a473  mov     ebx, eax
0x18006a475  test    eax, eax
0x18006a477  jns     short loc_18006A49A
0x18006a479  mov     edx, eax; int
0x18006a47b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a480  mov     r9d, 6D7h
0x18006a486  lea     edx, [r12+1]
0x18006a48b  mov     r8, r13
0x18006a48e  mov     ecx, ebx
0x18006a490  call    Log_HREvent_17
0x18006a495  jmp     loc_18006A9A8
0x18006a49a  cmp     [rbp+50h+var_B8], r12d
0x18006a49e  jnz     short loc_18006A4B4
0x18006a4a0  mov     ebx, 8000FFFFh
0x18006a4a5  mov     edx, ebx; int
0x18006a4a7  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a4ac  mov     r9d, 6D8h
0x18006a4b2  jmp     short loc_18006A4CA
0x18006a4b4  mov     rax, [rbp+50h+var_D0]
0x18006a4b8  cmp     [rsp+150h+sourceString], rax
0x18006a4bd  jnz     short loc_18006A4CE
0x18006a4bf  mov     r9d, 6D9h
0x18006a4c5  mov     ebx, 8000FFFFh
0x18006a4ca  xor     edx, edx
0x18006a4cc  jmp     short loc_18006A48B
0x18006a4ce  xorps   xmm0, xmm0
0x18006a4d1  mov     [rsp+150h+var_F0], r12
0x18006a4d6  lea     r9, [rbp+50h+string]; string
0x18006a4da  mov     qword ptr [rbp+50h+hstringHeader.Reserved], r12
0x18006a4de  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x18006a4e2  mov     [rbp+50h+string], r12
0x18006a4e6  mov     edx, 38h ; '8'; length
0x18006a4eb  lea     rcx, ?RuntimeClass_Windows_Media_Capture_MediaCaptureInitializationSettings@@3QBGB; "Windows.Media.Capture.MediaCaptureIniti"...
0x18006a4f2  movdqu  xmmword ptr [rbp+50h+hstringHeader.Reserved+8], xmm0
0x18006a4f7  call    cs:__imp_WindowsCreateStringReference
0x18006a4fd  test    eax, eax
0x18006a4ff  js      loc_18006A9F3
0x18006a505  mov     rcx, [rbp+50h+string]
0x18006a509  lea     rdx, [rsp+150h+var_100]
0x18006a50e  mov     rax, [rsi+40h]
0x18006a512  mov     [rsp+150h+var_F0], r12
0x18006a517  mov     [rsp+150h+var_100], r12
0x18006a51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a521  mov     ebx, eax
0x18006a523  test    eax, eax
0x18006a525  js      loc_18006A96D
0x18006a52b  mov     r8d, 10h; Size
0x18006a531  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18006a538  lea     rcx, _GUID_9782ba70_ea65_4900_9356_8ca887726884; Buf1
0x18006a53f  call    memcmp_0
0x18006a544  mov     rcx, [rsp+150h+var_100]
0x18006a549  test    eax, eax
0x18006a54b  jnz     short loc_18006A554
0x18006a54d  mov     [rsp+150h+var_F0], rcx
0x18006a552  jmp     short loc_18006A58B
0x18006a554  mov     rax, [rcx]
0x18006a557  lea     r8, [rsp+150h+var_F0]
0x18006a55c  lea     rdx, _GUID_9782ba70_ea65_4900_9356_8ca887726884
0x18006a563  mov     rax, [rax]
0x18006a566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a56b  mov     rcx, [rsp+150h+var_100]
0x18006a570  mov     ebx, eax
0x18006a572  mov     rax, [rcx]
0x18006a575  mov     rax, [rax+10h]
0x18006a579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a57e  test    ebx, ebx
0x18006a580  js      loc_18006A96D
0x18006a586  mov     rcx, [rsp+150h+var_F0]
0x18006a58b  mov     rax, [rcx]
0x18006a58e  mov     edi, 1
0x18006a593  mov     edx, edi
0x18006a595  mov     rax, [rax+50h]
0x18006a599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a59e  mov     ebx, eax
0x18006a5a0  test    eax, eax
0x18006a5a2  jns     short loc_18006A5B8
0x18006a5a4  mov     edx, eax; int
0x18006a5a6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a5ab  mov     r9d, 6DFh
0x18006a5b1  mov     edx, edi
0x18006a5b3  jmp     loc_18006A97F
0x18006a5b8  xorps   xmm0, xmm0
0x18006a5bb  mov     qword ptr [rbp+50h+var_90.Reserved], r12
0x18006a5bf  lea     r9, [rbp+50h+var_78]; string
0x18006a5c3  mov     [rbp+50h+var_78], r12
0x18006a5c7  lea     r8, [rbp+50h+var_90]; hstringHeader
0x18006a5cb  mov     edx, 32h ; '2'; length
0x18006a5d0  lea     rcx, ?RuntimeClass_Windows_Media_MediaProperties_MediaEncodingProfile@@3QBGB; "Windows.Media.MediaProperties.MediaEnco"...
0x18006a5d7  movdqu  xmmword ptr [rbp+50h+var_90.Reserved+8], xmm0
0x18006a5dc  call    cs:__imp_WindowsCreateStringReference
0x18006a5e2  test    eax, eax
0x18006a5e4  js      loc_18006A9FB
0x18006a5ea  mov     rcx, [rsp+150h+sourceString]; sourceString
0x18006a5ef  lea     r9, [rsp+150h+var_F8]; string
0x18006a5f4  mov     rdx, [rbp+50h+var_D0]
0x18006a5f8  lea     r8, [rbp+50h+var_50]; hstringHeader
0x18006a5fc  sub     rdx, rcx
0x18006a5ff  mov     [rsp+150h+var_F8], r12
0x18006a604  xorps   xmm0, xmm0
0x18006a607  sar     rdx, 1; length
0x18006a60a  xor     eax, eax
0x18006a60c  movups  xmmword ptr [rbp+50h+var_50.Reserved], xmm0
0x18006a610  mov     qword ptr [rbp+50h+var_50.Reserved+10h], rax
0x18006a614  call    cs:__imp_WindowsCreateStringReference
0x18006a61a  mov     ebx, eax
0x18006a61c  test    eax, eax
0x18006a61e  jns     short loc_18006A642
0x18006a620  mov     edx, eax; int
0x18006a622  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a627  mov     r9d, 6E6h
0x18006a62d  mov     r8, r13
0x18006a630  mov     edx, edi
0x18006a632  mov     ecx, ebx
0x18006a634  call    Log_HREvent_17
0x18006a639  mov     [rbp+50h+var_78], r12
0x18006a63d  jmp     loc_18006A989
0x18006a642  mov     rcx, [rsp+150h+var_F0]
0x18006a647  mov     rdx, [rsp+150h+var_F8]
0x18006a64c  mov     rax, [rcx]
0x18006a64f  mov     rax, [rax+30h]
0x18006a653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a658  mov     ebx, eax
0x18006a65a  test    eax, eax
0x18006a65c  jns     short loc_18006A66D
0x18006a65e  mov     edx, eax; int
0x18006a660  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a665  mov     r9d, 6E7h
0x18006a66b  jmp     short loc_18006A62D
0x18006a66d  xorps   xmm0, xmm0
0x18006a670  mov     [rsp+150h+var_E8], r12
0x18006a675  lea     r9, [rbp+50h+var_58]; string
0x18006a679  mov     qword ptr [rbp+50h+var_70.Reserved], r12
0x18006a67d  lea     r8, [rbp+50h+var_70]; hstringHeader
0x18006a681  mov     [rbp+50h+var_58], r12
0x18006a685  mov     edx, 22h ; '"'; length
0x18006a68a  lea     rcx, ?RuntimeClass_Windows_Media_Capture_MediaCapture@@3QBGB; "Windows.Media.Capture.MediaCapture"
0x18006a691  movdqu  xmmword ptr [rbp+50h+var_70.Reserved+8], xmm0
0x18006a696  call    cs:__imp_WindowsCreateStringReference
0x18006a69c  test    eax, eax
0x18006a69e  js      loc_18006A9EB
0x18006a6a4  mov     rdx, [rbp+50h+var_58]
0x18006a6a8  lea     r8, [rsp+150h+var_E8]
0x18006a6ad  mov     rcx, rsi
0x18006a6b0  call    ??$_ActivateInstance@UIMediaCapture@Capture@Media@Windows@@@CallAudioRouting@@IEAAJPEAUHSTRING__@@PEAPEAUIMediaCapture@Capture@Media@Windows@@@Z; CallAudioRouting::_ActivateInstance<Windows::Media::Capture::IMediaCapture>(HSTRING__ *,Windows::Media::Capture::IMediaCapture * *)
0x18006a6b5  mov     ebx, eax
0x18006a6b7  test    eax, eax
0x18006a6b9  jns     short loc_18006A6FC
0x18006a6bb  mov     edx, eax; int
0x18006a6bd  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a6c2  mov     r9d, 6ECh
0x18006a6c8  mov     r8, r13
0x18006a6cb  mov     edx, edi
0x18006a6cd  mov     ecx, ebx
0x18006a6cf  call    Log_HREvent_17
0x18006a6d4  mov     rcx, [rsp+150h+var_E8]
0x18006a6d9  mov     [rbp+50h+var_58], r12
0x18006a6dd  test    rcx, rcx
0x18006a6e0  jz      loc_18006A639
0x18006a6e6  mov     [rsp+150h+var_E8], r12
0x18006a6eb  mov     rax, [rcx]
0x18006a6ee  mov     rax, [rax+10h]
0x18006a6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6f7  jmp     loc_18006A639
0x18006a6fc  mov     rax, rsi
0x18006a6ff  lea     rcx, [rsi+8]
0x18006a703  neg     rax
0x18006a706  sbb     rbx, rbx
0x18006a709  and     rbx, rcx
0x18006a70c  jz      short loc_18006A71D
0x18006a70e  mov     rax, [rbx]
0x18006a711  mov     rcx, rbx
0x18006a714  mov     rax, [rax+8]
0x18006a718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a71d  mov     rcx, [rsp+150h+var_E8]
0x18006a722  lea     r8, [rsp+150h+var_E0]
0x18006a727  mov     rdx, [rsp+150h+var_F0]
0x18006a72c  mov     [rsp+150h+var_E0], r12
0x18006a731  mov     rax, [rcx]
0x18006a734  mov     rax, [rax+38h]
0x18006a738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a73d  mov     r14d, eax
0x18006a740  test    eax, eax
0x18006a742  jns     loc_18006A7F5
0x18006a748  mov     edx, eax; int
0x18006a74a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006a74f  mov     r9d, 6F2h
0x18006a755  mov     r8, r13
0x18006a758  mov     edx, edi
0x18006a75a  mov     ecx, r14d
0x18006a75d  call    Log_HREvent_17
0x18006a762  mov     rcx, [rsp+150h+var_E0]
0x18006a767  test    rcx, rcx
0x18006a76a  jz      short loc_18006A77D
0x18006a76c  mov     [rsp+150h+var_E0], r12
0x18006a771  mov     rax, [rcx]
0x18006a774  mov     rax, [rax+10h]
0x18006a778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a77d  test    rbx, rbx
0x18006a780  jz      short loc_18006A791
0x18006a782  mov     rax, [rbx]
0x18006a785  mov     rcx, rbx
0x18006a788  mov     rax, [rax+10h]
0x18006a78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a791  mov     rcx, [rsp+150h+var_E8]
0x18006a796  mov     [rbp+50h+var_58], r12
0x18006a79a  test    rcx, rcx
0x18006a79d  jz      short loc_18006A7B0
0x18006a79f  mov     [rsp+150h+var_E8], r12
0x18006a7a4  mov     rax, [rcx]
0x18006a7a7  mov     rax, [rax+10h]
0x18006a7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a7b0  mov     rcx, [rsp+150h+var_F0]
0x18006a7b5  mov     [rbp+50h+string], r12
0x18006a7b9  mov     [rbp+50h+var_78], r12
0x18006a7bd  test    rcx, rcx
0x18006a7c0  jz      short loc_18006A7D3
0x18006a7c2  mov     [rsp+150h+var_F0], r12
0x18006a7c7  mov     rax, [rcx]
0x18006a7ca  mov     rax, [rax+10h]
0x18006a7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a7d3  mov     rcx, [rsp+150h+sourceString]; Block
0x18006a7d8  lea     rax, [rbp+50h+var_C8]
0x18006a7dc  cmp     rcx, rax
0x18006a7df  jz      short loc_18006A7ED
0x18006a7e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18006a7e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006a7ed  mov     eax, r14d
0x18006a7f0  jmp     loc_18006A9C4
0x18006a7f5  mov     [rsp+150h+var_100], r12
0x18006a7fa  mov     [rsp+150h+var_120], rsi
0x18006a7ff  mov     [rsp+150h+var_118], rbx
0x18006a804  test    rbx, rbx
0x18006a807  jz      short loc_18006A818
0x18006a809  mov     rax, [rbx]
0x18006a80c  mov     rcx, rbx
0x18006a80f  mov     rax, [rax+8]
0x18006a813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a818  mov     rcx, [rsp+150h+var_E8]
0x18006a81d  mov     [rsp+150h+var_110], r15d
0x18006a822  mov     [rsp+150h+var_108], rcx
0x18006a827  test    rcx, rcx
0x18006a82a  jz      short loc_18006A838
0x18006a82c  mov     rax, [rcx]
0x18006a82f  mov     rax, [rax+8]
0x18006a833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a838  lea     rdx, [rsp+150h+var_120]
0x18006a83d  lea     rcx, [rsp+150h+var_100]
0x18006a842  call    Microsoft__WRL__Callback_Windows__Foundation__IAsyncActionCompletedHandler__lambda_d66fa114b66bccbec792d3417aa6c740___
0x18006a847  mov     rcx, [rsp+150h+var_108]
0x18006a84c  test    rcx, rcx
0x18006a84f  jz      short loc_18006A85D
0x18006a851  mov     rax, [rcx]
0x18006a854  mov     rax, [rax+10h]
0x18006a858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a85d  mov     rcx, [rsp+150h+var_118]
0x18006a862  test    rcx, rcx
0x18006a865  jz      short loc_18006A873
0x18006a867  mov     rax, [rcx]
0x18006a86a  mov     rax, [rax+10h]
  ... truncated ...
```
