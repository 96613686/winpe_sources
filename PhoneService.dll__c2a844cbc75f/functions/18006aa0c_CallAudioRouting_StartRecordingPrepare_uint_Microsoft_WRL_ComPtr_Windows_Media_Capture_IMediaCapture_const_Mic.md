# CallAudioRouting::_StartRecordingPrepare(uint,Microsoft::WRL::ComPtr<Windows::Media::Capture::IMediaCapture> const &,Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile> const &)

- ea: `0x18006aa0c`
- end: `0x18006ae03`
- name: `?_StartRecordingPrepare@CallAudioRouting@@AEAAJIAEBV?$ComPtr@UIMediaCapture@Capture@Media@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIStorageFile@Storage@Windows@@@34@@Z`
- size: `1015`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b2c0`

## callees

- `0x180006b44`
- `0x180006e94`
- `0x180057a10`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006aa0c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006aa3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006aa5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006aa3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006aa5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006aaf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006aaf8`

## string_xrefs

- `0x18006aa44`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_StartRecordingPrepare(
        __int64 a1,
        int a2,
        __int64 (__fastcall ****a3)(_QWORD, GUID *, __int64 *),
        __int64 *a4)
{
  __int64 v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  int v10; // eax
  BackTraceCollection *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  BackTraceCollection *v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  BackTraceCollection *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // r8
  int v26; // eax
  BackTraceCollection *v27; // rcx
  unsigned int v28; // r14d
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rdi
  int v34; // eax
  BackTraceCollection *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // [rsp+30h] [rbp-49h] BYREF
  __int64 v41; // [rsp+38h] [rbp-41h] BYREF
  __int64 v42; // [rsp+40h] [rbp-39h]
  int v43; // [rsp+48h] [rbp-31h]
  __int64 v44; // [rsp+50h] [rbp-29h] BYREF
  __int64 v45; // [rsp+58h] [rbp-21h] BYREF
  __int64 v46; // [rsp+60h] [rbp-19h] BYREF
  __int64 v47; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF

  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2035);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v9 = *a3;
  v44 = 0;
  v10 = (**v9)(v9, &GUID_9cc68260_7da1_4043_b652_21b8878daff9, &v44);
  v12 = v10;
  if ( v10 < 0 )
  {
    BackTraceCollection::Capture(v11, v10);
    Log_HREvent_17(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2039);
LABEL_6:
    v13 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v12;
  }
  v45 = 0;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  string = 0;
  v15 = WindowsCreateStringReference(
          L"Windows.Media.MediaProperties.MediaEncodingProfile",
          0x32u,
          &hstringHeader,
          &string);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    JUMPOUT(0x18006AE02LL);
  }
  v18 = (*(__int64 (__fastcall **)(HSTRING, GUID *, __int64 *))(a1 + 72))(
          string,
          &GUID_197f352c_2ede_4a45_a896_817a4854f8fe,
          &v45);
  v12 = v18;
  if ( v18 < 0 )
  {
    BackTraceCollection::Capture(v19, v18);
    Log_HREvent_17(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2043);
LABEL_12:
    v20 = v45;
    string = 0;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_6;
  }
  v46 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v45 + 48LL))(v45, 1, &v46);
  v12 = v21;
  if ( v21 < 0 )
  {
    BackTraceCollection::Capture(v22, v21);
    Log_HREvent_17(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2046);
    v23 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    goto LABEL_12;
  }
  v24 = (a1 + 8) & -(__int64)(a1 != 0);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))((a1 + 8) & -(__int64)(a1 != 0));
  v25 = *a4;
  v47 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v44 + 48LL))(v44, v46, v25, &v47);
  v28 = v26;
  if ( v26 < 0 )
  {
    BackTraceCollection::Capture(v27, v26);
    Log_HREvent_17(v28, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2052);
LABEL_21:
    v29 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v30 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v45;
    string = 0;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    return v28;
  }
  v40 = 0;
  v41 = a1;
  v42 = (a1 + 8) & -(__int64)(a1 != 0);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))((a1 + 8) & -(__int64)(a1 != 0));
  v43 = a2;
  Microsoft::WRL::Callback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Media::Capture::LowLagMediaRecording_____lambda_3cad691546eb76006eb55b0d4e5e66c4___(
    &v40,
    &v41);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  v33 = v40;
  v34 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 48LL))(v47, v40);
  v28 = v34;
  if ( v34 < 0 )
  {
    BackTraceCollection::Capture(v35, v34);
    Log_HREvent_17(v28, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 2087);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_21;
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  v36 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v37 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  v38 = v45;
  string = 0;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  return 0;
}

```

## disassembly

```asm
0x18006aa0c  push    rbp
0x18006aa0e  push    rbx
0x18006aa0f  push    rdi
0x18006aa10  push    r12
0x18006aa12  push    r13
0x18006aa14  push    r14
0x18006aa16  push    r15
0x18006aa18  lea     rbp, [rsp-27h]
0x18006aa1d  sub     rsp, 0A0h
0x18006aa24  mov     rax, cs:__security_cookie
0x18006aa2b  xor     rax, rsp
0x18006aa2e  mov     [rbp+57h+var_40], rax
0x18006aa32  mov     r14, r9
0x18006aa35  mov     rbx, r8
0x18006aa38  mov     r15d, edx
0x18006aa3b  mov     rdi, rcx
0x18006aa3e  call    cs:__imp_GetCurrentThreadId
0x18006aa44  lea     r13, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006aa4b  cmp     [rdi+68h], eax
0x18006aa4e  jnz     short loc_18006AA6E
0x18006aa50  mov     r8d, 7F3h
0x18006aa56  mov     rdx, r13
0x18006aa59  call    Log_AssertionEvent_9
0x18006aa5e  call    cs:__imp_GetCurrentThreadId
0x18006aa64  cmp     [rdi+68h], eax
0x18006aa67  jnz     short loc_18006AA6E
0x18006aa69  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006aa6e  mov     rcx, [rbx]
0x18006aa71  lea     r8, [rbp+57h+var_80]
0x18006aa75  xor     r12d, r12d
0x18006aa78  lea     rdx, _GUID_9cc68260_7da1_4043_b652_21b8878daff9
0x18006aa7f  mov     [rbp+57h+var_80], r12
0x18006aa83  mov     rax, [rcx]
0x18006aa86  mov     rax, [rax]
0x18006aa89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa8e  mov     ebx, eax
0x18006aa90  test    eax, eax
0x18006aa92  jns     short loc_18006AAD0
0x18006aa94  mov     edx, eax; int
0x18006aa96  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006aa9b  mov     r9d, 7F7h
0x18006aaa1  lea     edx, [r12+1]
0x18006aaa6  mov     r8, r13
0x18006aaa9  mov     ecx, ebx
0x18006aaab  call    Log_HREvent_17
0x18006aab0  mov     rcx, [rbp+57h+var_80]
0x18006aab4  test    rcx, rcx
0x18006aab7  jz      short loc_18006AAC9
0x18006aab9  mov     [rbp+57h+var_80], r12
0x18006aabd  mov     rax, [rcx]
0x18006aac0  mov     rax, [rax+10h]
0x18006aac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aac9  mov     eax, ebx
0x18006aacb  jmp     loc_18006ADDC
0x18006aad0  xorps   xmm0, xmm0
0x18006aad3  mov     [rbp+57h+var_78], r12
0x18006aad7  lea     r9, [rbp+57h+string]; string
0x18006aadb  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x18006aadf  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006aae3  mov     [rbp+57h+string], r12
0x18006aae7  mov     edx, 32h ; '2'; length
0x18006aaec  lea     rcx, ?RuntimeClass_Windows_Media_MediaProperties_MediaEncodingProfile@@3QBGB; "Windows.Media.MediaProperties.MediaEnco"...
0x18006aaf3  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved+8], xmm0
0x18006aaf8  call    cs:__imp_WindowsCreateStringReference
0x18006aafe  test    eax, eax
0x18006ab00  js      loc_18006ADFB
0x18006ab06  mov     rcx, [rbp+57h+string]
0x18006ab0a  lea     r8, [rbp+57h+var_78]
0x18006ab0e  mov     rax, [rdi+48h]
0x18006ab12  lea     rdx, _GUID_197f352c_2ede_4a45_a896_817a4854f8fe
0x18006ab19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab1e  mov     ebx, eax
0x18006ab20  test    eax, eax
0x18006ab22  jns     short loc_18006AB66
0x18006ab24  mov     edx, eax; int
0x18006ab26  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006ab2b  mov     r9d, 7FBh
0x18006ab31  mov     r8, r13
0x18006ab34  mov     edx, 1
0x18006ab39  mov     ecx, ebx
0x18006ab3b  call    Log_HREvent_17
0x18006ab40  mov     rcx, [rbp+57h+var_78]
0x18006ab44  mov     [rbp+57h+string], r12
0x18006ab48  test    rcx, rcx
0x18006ab4b  jz      loc_18006AAB0
0x18006ab51  mov     [rbp+57h+var_78], r12
0x18006ab55  mov     rax, [rcx]
0x18006ab58  mov     rax, [rax+10h]
0x18006ab5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab61  jmp     loc_18006AAB0
0x18006ab66  mov     rcx, [rbp+57h+var_78]
0x18006ab6a  lea     r8, [rbp+57h+var_70]
0x18006ab6e  mov     [rbp+57h+var_70], r12
0x18006ab72  mov     edx, 1
0x18006ab77  mov     rax, [rcx]
0x18006ab7a  mov     rax, [rax+30h]
0x18006ab7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab83  mov     ebx, eax
0x18006ab85  test    eax, eax
0x18006ab87  jns     short loc_18006ABC0
0x18006ab89  mov     edx, eax; int
0x18006ab8b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006ab90  mov     r9d, 7FEh
0x18006ab96  mov     r8, r13
0x18006ab99  mov     edx, 1
0x18006ab9e  mov     ecx, ebx
0x18006aba0  call    Log_HREvent_17
0x18006aba5  mov     rcx, [rbp+57h+var_70]
0x18006aba9  test    rcx, rcx
0x18006abac  jz      short loc_18006AB40
0x18006abae  mov     [rbp+57h+var_70], r12
0x18006abb2  mov     rax, [rcx]
0x18006abb5  mov     rax, [rax+10h]
0x18006abb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abbe  jmp     short loc_18006AB40
0x18006abc0  mov     rax, rdi
0x18006abc3  lea     rcx, [rdi+8]
0x18006abc7  neg     rax
0x18006abca  sbb     rbx, rbx
0x18006abcd  and     rbx, rcx
0x18006abd0  jz      short loc_18006ABE1
0x18006abd2  mov     rax, [rbx]
0x18006abd5  mov     rcx, rbx
0x18006abd8  mov     rax, [rax+8]
0x18006abdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abe1  mov     rcx, [rbp+57h+var_80]
0x18006abe5  lea     r9, [rbp+57h+var_68]
0x18006abe9  mov     r8, [r14]
0x18006abec  mov     rdx, [rbp+57h+var_70]
0x18006abf0  mov     [rbp+57h+var_68], r12
0x18006abf4  mov     rax, [rcx]
0x18006abf7  mov     rax, [rax+30h]
0x18006abfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac00  mov     r14d, eax
0x18006ac03  test    eax, eax
0x18006ac05  jns     loc_18006ACAC
0x18006ac0b  mov     edx, eax; int
0x18006ac0d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006ac12  mov     r9d, 804h
0x18006ac18  mov     r8, r13
0x18006ac1b  mov     edx, 1
0x18006ac20  mov     ecx, r14d
0x18006ac23  call    Log_HREvent_17
0x18006ac28  mov     rcx, [rbp+57h+var_68]
0x18006ac2c  test    rcx, rcx
0x18006ac2f  jz      short loc_18006AC41
0x18006ac31  mov     [rbp+57h+var_68], r12
0x18006ac35  mov     rax, [rcx]
0x18006ac38  mov     rax, [rax+10h]
0x18006ac3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac41  test    rbx, rbx
0x18006ac44  jz      short loc_18006AC55
0x18006ac46  mov     rax, [rbx]
0x18006ac49  mov     rcx, rbx
0x18006ac4c  mov     rax, [rax+10h]
0x18006ac50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac55  mov     rcx, [rbp+57h+var_70]
0x18006ac59  test    rcx, rcx
0x18006ac5c  jz      short loc_18006AC6E
0x18006ac5e  mov     [rbp+57h+var_70], r12
0x18006ac62  mov     rax, [rcx]
0x18006ac65  mov     rax, [rax+10h]
0x18006ac69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac6e  mov     rcx, [rbp+57h+var_78]
0x18006ac72  mov     [rbp+57h+string], r12
0x18006ac76  test    rcx, rcx
0x18006ac79  jz      short loc_18006AC8B
0x18006ac7b  mov     [rbp+57h+var_78], r12
0x18006ac7f  mov     rax, [rcx]
0x18006ac82  mov     rax, [rax+10h]
0x18006ac86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac8b  mov     rcx, [rbp+57h+var_80]
0x18006ac8f  test    rcx, rcx
0x18006ac92  jz      short loc_18006ACA4
0x18006ac94  mov     [rbp+57h+var_80], r12
0x18006ac98  mov     rax, [rcx]
0x18006ac9b  mov     rax, [rax+10h]
0x18006ac9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aca4  mov     eax, r14d
0x18006aca7  jmp     loc_18006ADDC
0x18006acac  mov     [rbp+57h+var_A0], r12
0x18006acb0  mov     [rbp+57h+var_98], rdi
0x18006acb4  mov     [rbp+57h+var_90], rbx
0x18006acb8  test    rbx, rbx
0x18006acbb  jz      short loc_18006ACCC
0x18006acbd  mov     rax, [rbx]
0x18006acc0  mov     rcx, rbx
0x18006acc3  mov     rax, [rax+8]
0x18006acc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006accc  lea     rdx, [rbp+57h+var_98]
0x18006acd0  mov     [rbp+57h+var_88], r15d
0x18006acd4  lea     rcx, [rbp+57h+var_A0]
0x18006acd8  call    Microsoft__WRL__Callback_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Media__Capture__LowLagMediaRecording_____lambda_3cad691546eb76006eb55b0d4e5e66c4___
0x18006acdd  mov     rcx, [rbp+57h+var_90]
0x18006ace1  test    rcx, rcx
0x18006ace4  jz      short loc_18006ACF2
0x18006ace6  mov     rax, [rcx]
0x18006ace9  mov     rax, [rax+10h]
0x18006aced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acf2  mov     rcx, [rbp+57h+var_68]
0x18006acf6  mov     rdi, [rbp+57h+var_A0]
0x18006acfa  mov     rdx, rdi
0x18006acfd  mov     rax, [rcx]
0x18006ad00  mov     rax, [rax+30h]
0x18006ad04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad09  mov     r14d, eax
0x18006ad0c  test    eax, eax
0x18006ad0e  jns     short loc_18006AD4A
0x18006ad10  mov     edx, eax; int
0x18006ad12  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006ad17  mov     r9d, 827h
0x18006ad1d  mov     r8, r13
0x18006ad20  mov     edx, 1
0x18006ad25  mov     ecx, r14d
0x18006ad28  call    Log_HREvent_17
0x18006ad2d  test    rdi, rdi
0x18006ad30  jz      loc_18006AC28
0x18006ad36  mov     rax, [rdi]
0x18006ad39  mov     rcx, rdi
0x18006ad3c  mov     rax, [rax+10h]
0x18006ad40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad45  jmp     loc_18006AC28
0x18006ad4a  test    rdi, rdi
0x18006ad4d  jz      short loc_18006AD5E
0x18006ad4f  mov     rax, [rdi]
0x18006ad52  mov     rcx, rdi
0x18006ad55  mov     rax, [rax+10h]
0x18006ad59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad5e  mov     rcx, [rbp+57h+var_68]
0x18006ad62  test    rcx, rcx
0x18006ad65  jz      short loc_18006AD77
0x18006ad67  mov     [rbp+57h+var_68], r12
0x18006ad6b  mov     rax, [rcx]
0x18006ad6e  mov     rax, [rax+10h]
0x18006ad72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad77  test    rbx, rbx
0x18006ad7a  jz      short loc_18006AD8B
0x18006ad7c  mov     rax, [rbx]
0x18006ad7f  mov     rcx, rbx
0x18006ad82  mov     rax, [rax+10h]
0x18006ad86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad8b  mov     rcx, [rbp+57h+var_70]
0x18006ad8f  test    rcx, rcx
0x18006ad92  jz      short loc_18006ADA4
0x18006ad94  mov     [rbp+57h+var_70], r12
0x18006ad98  mov     rax, [rcx]
0x18006ad9b  mov     rax, [rax+10h]
0x18006ad9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ada4  mov     rcx, [rbp+57h+var_78]
0x18006ada8  mov     [rbp+57h+string], r12
0x18006adac  test    rcx, rcx
0x18006adaf  jz      short loc_18006ADC1
0x18006adb1  mov     [rbp+57h+var_78], r12
0x18006adb5  mov     rax, [rcx]
0x18006adb8  mov     rax, [rax+10h]
0x18006adbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adc1  mov     rcx, [rbp+57h+var_80]
0x18006adc5  test    rcx, rcx
0x18006adc8  jz      short loc_18006ADDA
0x18006adca  mov     [rbp+57h+var_80], r12
0x18006adce  mov     rax, [rcx]
0x18006add1  mov     rax, [rax+10h]
0x18006add5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adda  xor     eax, eax
0x18006addc  mov     rcx, [rbp+57h+var_40]
0x18006ade0  xor     rcx, rsp; StackCookie
0x18006ade3  call    __security_check_cookie
0x18006ade8  add     rsp, 0A0h
0x18006adef  pop     r15
0x18006adf1  pop     r14
0x18006adf3  pop     r13
0x18006adf5  pop     r12
0x18006adf7  pop     rdi
0x18006adf8  pop     rbx
0x18006adf9  pop     rbp
0x18006adfa  retn
0x18006adfb  mov     ecx, eax; this
0x18006adfd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
