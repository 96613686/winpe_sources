# Windows::UI::Input::Inking::CInkStrokeContainer::PasteFromClipboard(Windows::Foundation::Point,Windows::Foundation::Rect *)

- ea: `0x180030750`
- end: `0x180030ef2`
- name: `?PasteFromClipboard@CInkStrokeContainer@Inking@Input@UI@Windows@@UEAAJUPoint@Foundation@5@PEAURect@75@@Z`
- size: `1954`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001332c`
- `0x18001b64c`
- `0x18001f73c`
- `0x18001f958`
- `0x18001f9a4`
- `0x18001ff0c`
- `0x18002004c`
- `0x180020774`
- `0x1800223fc`
- `0x1800227e4`
- `0x180030750`
- `0x18005efa4`
- `0x18005f504`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003094f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030a45`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003094f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030a45`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800307a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180030daf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180030e40`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800307a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180030daf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180030e40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030a5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030a5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030c02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030c02`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkStrokeContainer::PasteFromClipboard(
        LARGE_INTEGER *a1,
        __int64 a2,
        _QWORD *a3)
{
  union _LARGE_INTEGER *v3; // r13
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  LONGLONG QuadPart; // rax
  __int64 (__fastcall *v15)(LARGE_INTEGER *, __int64 *); // rbx
  int v16; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  struct _EVENT_DATA_DESCRIPTOR *p_string; // rax
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64 *); // rbx
  __int64 v26; // r14
  unsigned __int64 v27; // rbx
  unsigned __int64 v28; // rcx
  __int64 (__fastcall *v29)(__int64, HSTRING, __int64 *); // r12
  const ULONG_PTR *v30; // r9
  int v31; // edi
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // r14
  __int64 (__fastcall *v36)(__int64, HSTRING, __int64 *); // r12
  const ULONG_PTR *v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, __int64 *); // rbx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v45)[31]; // rdx
  __int64 v46; // rbx
  int ActivationFactory; // eax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, _QWORD, __int64 *); // rbx
  int v50; // eax
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, __int64, _QWORD, _QWORD); // rbx
  __int64 v53; // rdx
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64 *); // rbx
  int v56; // eax
  __int64 v57; // rdx
  double DurationInMs; // xmm7_8
  double v59; // xmm6_8
  double v60; // xmm0_8
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  int v64; // [rsp+28h] [rbp-E0h]
  int *v65; // [rsp+28h] [rbp-E0h]
  __int64 v66; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v67; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v68; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v69; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v70; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v72; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+70h] [rbp-98h] BYREF
  __int64 v74; // [rsp+78h] [rbp-90h] BYREF
  UINT32 length; // [rsp+80h] [rbp-88h] BYREF
  int v76[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v77; // [rsp+90h] [rbp-78h] BYREF
  __int64 v78; // [rsp+98h] [rbp-70h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v80; // [rsp+A8h] [rbp-60h] BYREF
  LARGE_INTEGER v81; // [rsp+B0h] [rbp-58h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B8h] [rbp-50h] BYREF
  HSTRING string; // [rsp+C0h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v85; // [rsp+E0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v3 = a1 + 34;
  PerformanceCount.QuadPart = 0;
  v81.QuadPart = 0;
  QueryPerformanceCounter(a1 + 34);
  if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v7, (int)&Inking_IStrokeCollection_Paste_Start, v8, v9, &v85);
  if ( !a3 )
  {
    v10 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9CB,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)0x80004003LL,
      v64);
    if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer((int)&v85, (int)&Inking_IStrokeCollection_Paste_Stop, v11, v12, &v85);
    return (unsigned int)v10;
  }
  a3[1] = 0;
  *a3 = 0;
  QuadPart = a1->QuadPart;
  v68 = 0;
  v15 = *(__int64 (__fastcall **)(LARGE_INTEGER *, __int64 *))(QuadPart + 296);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  v16 = v15(a1, &v68);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D1,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v16,
      v64);
LABEL_9:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) == 0 )
      return (unsigned int)v10;
    p_string = &v85;
LABEL_11:
    McGenEventWrite_EventWriteTransfer(v18, (int)&Inking_IStrokeCollection_Paste_Stop, v19, v20, p_string);
    return (unsigned int)v10;
  }
  v69 = 0;
  v67 = 0;
  LOBYTE(v66) = 0;
  v22 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[48])v17);
  v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>(
          *v22,
          &v69);
  if ( v10 < 0 )
  {
    v23 = 2519;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v10,
      v64);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    goto LABEL_9;
  }
  v24 = v69;
  v25 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  v10 = v25(v24, &v67);
  if ( v10 < 0 )
  {
    v23 = 2520;
    goto LABEL_14;
  }
  v26 = v67;
  v27 = -1;
  length = 0;
  v28 = -1;
  v29 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v67 + 80LL);
  do
    ++v28;
  while ( aInkSerializedF[v28] );
  if ( (int)ULongLongToUInt(v28, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v30);
  WindowsCreateStringReference(L"Ink Serialized Format", length, &hstringHeader, &string);
  v31 = v29(v26, string, &v66);
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9DA,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v31,
      v64);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v32, (int)&Inking_IStrokeCollection_Paste_Stop, v33, v34, &v85);
    return (unsigned int)v31;
  }
  if ( (_BYTE)v66 )
  {
    v35 = v67;
    v70 = 0;
    v80 = 0;
    v71 = 0;
    v36 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v67 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    length = 0;
    do
      ++v27;
    while ( aInkSerializedF[v27] );
    if ( (int)ULongLongToUInt(v27, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v37);
    WindowsCreateStringReference(L"Ink Serialized Format", length, &hstringHeader, &string);
    v10 = v36(v35, string, &v70);
    if ( v10 < 0 )
    {
      v38 = 2531;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v10,
        v64);
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) == 0 )
        return (unsigned int)v10;
      p_string = (struct _EVENT_DATA_DESCRIPTOR *)&string;
      goto LABEL_11;
    }
    v10 = Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::Foundation::IAsyncOperation<IInspectable *> *>(v70);
    if ( v10 < 0 )
    {
      v38 = 2532;
      goto LABEL_32;
    }
    v39 = v70;
    v72 = 0;
    v40 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    v41 = v40(v39, &v72);
    v10 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E6,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v41,
        v64);
LABEL_39:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      goto LABEL_33;
    }
    v73 = 0;
    v10 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Storage::Streams::IRandomAccessStream>(&v72, &v73);
    if ( v10 < 0 )
    {
      v42 = 2536;
LABEL_42:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v10,
        v64);
LABEL_43:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
      goto LABEL_39;
    }
    v43 = v73;
    v44 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v73 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    v10 = v44(v43, 0, &v71);
    if ( v10 < 0 )
    {
      v42 = 2537;
      goto LABEL_42;
    }
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 48LL))(v73, &v80);
    v85.Ptr = 0;
    v74 = 0;
    v46 = *(_QWORD *)Windows::Internal::StringReference::StringReference(&string, v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    ActivationFactory = RoGetActivationFactory(v46, &GUID_71af914d_c10f_484b_bc50_14bc623b3a27, &v74);
    v10 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F0,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v64);
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
      goto LABEL_43;
    }
    v48 = v74;
    v77 = 0;
    v49 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v74 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
    v50 = v49(v48, (unsigned int)v80, &v77);
    v10 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F3,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v50,
        v64);
LABEL_51:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      goto LABEL_48;
    }
    v51 = v71;
    *(_QWORD *)v76 = 0;
    v52 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v71 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v76);
    v65 = v76;
    v10 = v52(v51, v77, (unsigned int)v80, 0);
    if ( v10 < 0 )
    {
      v53 = 2550;
LABEL_54:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v53,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v10,
        (int)v76);
LABEL_55:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v76);
      goto LABEL_51;
    }
    v10 = Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int> *>(*(_QWORD *)v76);
    if ( v10 < 0 )
    {
      v53 = 2551;
      goto LABEL_54;
    }
    v54 = *(_QWORD *)v76;
    v78 = 0;
    v55 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v76 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    v56 = v55(v54, &v78);
    v10 = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9FA,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v56,
        (int)v76);
LABEL_60:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
      goto LABEL_55;
    }
    v79 = 0;
    v10 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
            &v78,
            &v79);
    if ( v10 < 0 )
    {
      v57 = 2557;
LABEL_63:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v57,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v10,
        (int)v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
      goto LABEL_60;
    }
    v10 = (*(__int64 (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v79 + 24LL))(v79, &v85);
    if ( v10 < 0 )
    {
      v57 = 2558;
      goto LABEL_63;
    }
    QueryPerformanceCounter(&PerformanceCount);
    LODWORD(v65) = (_DWORD)a3;
    v10 = (*(__int64 (__fastcall **)(LARGE_INTEGER *, ULONGLONG, __int64, __int64))(a1->QuadPart + 328))(
            a1,
            v85.Ptr,
            v80,
            a2);
    if ( v10 < 0 )
    {
      v57 = 2562;
      goto LABEL_63;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  }
  QueryPerformanceCounter(&v81);
  DurationInMs = GetDurationInMs(v3, &v81);
  v59 = GetDurationInMs(&PerformanceCount, &v81);
  v60 = GetDurationInMs(v3, &PerformanceCount);
  LogPasteFromClipboard(v3->QuadPart, v60, v59, DurationInMs);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v61,
      (int)&Inking_IStrokeCollection_Paste_Stop,
      v62,
      v63,
      (PEVENT_DATA_DESCRIPTOR)&string);
  return 0;
}

```

## disassembly

```asm
0x180030750  mov     rax, rsp
0x180030753  mov     [rax+20h], rbx
0x180030757  push    rbp
0x180030758  push    rsi
0x180030759  push    rdi
0x18003075a  push    r12
0x18003075c  push    r13
0x18003075e  push    r14
0x180030760  push    r15
0x180030762  lea     rbp, [rax-48h]
0x180030766  sub     rsp, 110h
0x18003076d  movaps  xmmword ptr [rax-48h], xmm6
0x180030771  movaps  xmmword ptr [rax-58h], xmm7
0x180030775  mov     rax, cs:__security_cookie
0x18003077c  xor     rax, rsp
0x18003077f  mov     [rbp+40h+var_58], rax
0x180030783  lea     r13, [rcx+110h]
0x18003078a  mov     r15, rcx
0x18003078d  xor     r14d, r14d
0x180030790  mov     rcx, r13; lpPerformanceCount
0x180030793  mov     rsi, r8
0x180030796  mov     qword ptr [rbp+40h+PerformanceCount], r14
0x18003079a  movq    xmm6, rdx
0x18003079f  mov     qword ptr [rbp+40h+var_98], r14
0x1800307a3  call    cs:__imp_QueryPerformanceCounter
0x1800307a9  mov     r12b, 2
0x1800307ac  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, r12b
0x1800307b3  jz      short loc_1800307CA
0x1800307b5  lea     rax, [rbp+40h+var_68]
0x1800307b9  lea     rdx, Inking_IStrokeCollection_Paste_Start; int
0x1800307c0  mov     [rsp+140h+var_120], rax; int
0x1800307c5  call    McGenEventWrite_EventWriteTransfer
0x1800307ca  test    rsi, rsi
0x1800307cd  jnz     short loc_180030811
0x1800307cf  mov     rcx, [rbp+48h]; this
0x1800307d3  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800307da  mov     ebx, 80004003h
0x1800307df  mov     edx, 9CBh; void *
0x1800307e4  mov     r9d, ebx; char *
0x1800307e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800307ec  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, r12b
0x1800307f3  jz      short loc_18003080A
0x1800307f5  lea     rcx, [rbp+40h+var_68]; int
0x1800307f9  mov     [rsp+140h+var_120], rcx; PEVENT_DATA_DESCRIPTOR
0x1800307fe  lea     rdx, Inking_IStrokeCollection_Paste_Stop; int
0x180030805  call    McGenEventWrite_EventWriteTransfer
0x18003080a  mov     eax, ebx
0x18003080c  jmp     loc_180030EC1
0x180030811  mov     [rsi+8], r14
0x180030815  lea     rcx, [rsp+140h+var_100]
0x18003081a  mov     [rsi], r14
0x18003081d  mov     rax, [r15]
0x180030820  mov     [rsp+140h+var_100], r14
0x180030825  mov     rbx, [rax+128h]
0x18003082c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030831  lea     rdx, [rsp+140h+var_100]
0x180030836  mov     rcx, r15
0x180030839  mov     rax, rbx
0x18003083c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030841  mov     ebx, eax
0x180030843  test    eax, eax
0x180030845  jns     short loc_18003087D
0x180030847  mov     rcx, [rbp+48h]; this
0x18003084b  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180030852  mov     r9d, eax; char *
0x180030855  mov     edx, 9D1h; void *
0x18003085a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003085f  lea     rcx, [rsp+140h+var_100]
0x180030864  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030869  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, r12b
0x180030870  jz      short loc_18003080A
0x180030872  lea     rax, [rbp+40h+var_68]
0x180030876  mov     [rsp+140h+var_120], rax
0x18003087b  jmp     short loc_1800307FE
0x18003087d  lea     rcx, [rbp+40h+string]; string
0x180030881  mov     [rsp+140h+var_F8], r14
0x180030886  mov     [rsp+140h+var_108], r14
0x18003088b  mov     byte ptr [rsp+140h+var_110], r14b
0x180030890  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x180030895  lea     rdx, [rsp+140h+var_F8]
0x18003089a  mov     rcx, [rax]
0x18003089d  call    ??$GetActivationFactory@V?$ComPtr@UIClipboardStatics@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIClipboardStatics@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>)
0x1800308a2  mov     ebx, eax
0x1800308a4  test    eax, eax
0x1800308a6  jns     short loc_1800308D6
0x1800308a8  mov     edx, 9D7h; void *
0x1800308ad  mov     rcx, [rbp+48h]; this
0x1800308b1  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800308b8  mov     r9d, ebx; char *
0x1800308bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800308c0  lea     rcx, [rsp+140h+var_108]
0x1800308c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800308ca  lea     rcx, [rsp+140h+var_F8]
0x1800308cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800308d4  jmp     short loc_18003085F
0x1800308d6  mov     rdi, [rsp+140h+var_F8]
0x1800308db  lea     rcx, [rsp+140h+var_108]
0x1800308e0  mov     rax, [rdi]
0x1800308e3  mov     rbx, [rax+30h]
0x1800308e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800308ec  lea     rdx, [rsp+140h+var_108]
0x1800308f1  mov     rcx, rdi
0x1800308f4  mov     rax, rbx
0x1800308f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308fc  mov     ebx, eax
0x1800308fe  test    eax, eax
0x180030900  jns     short loc_180030909
0x180030902  mov     edx, 9D8h
0x180030907  jmp     short loc_1800308AD
0x180030909  mov     r14, [rsp+140h+var_108]
0x18003090e  xor     r9d, r9d
0x180030911  mov     rdi, cs:sourceString
0x180030918  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003091c  mov     [rsp+140h+length], r9d
0x180030921  mov     rcx, rbx
0x180030924  mov     rax, [r14]
0x180030927  mov     r12, [rax+50h]
0x18003092b  inc     rcx; unsigned __int64
0x18003092e  cmp     [rdi+rcx*2], r9w
0x180030933  jnz     short loc_18003092B
0x180030935  lea     rdx, [rsp+140h+length]; unsigned int *
0x18003093a  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003093f  test    eax, eax
0x180030941  jns     short loc_180030955
0x180030943  xor     r8d, r8d; nNumberOfArguments
0x180030946  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003094b  lea     edx, [r8+1]; dwExceptionFlags
0x18003094f  call    cs:__imp_RaiseException
0x180030955  mov     edx, [rsp+140h+length]; length
0x180030959  lea     r9, [rbp+40h+string]; string
0x18003095d  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x180030961  mov     rcx, rdi; sourceString
0x180030964  call    cs:__imp_WindowsCreateStringReference
0x18003096a  mov     rdx, [rbp+40h+string]
0x18003096e  lea     r8, [rsp+140h+var_110]
0x180030973  mov     rcx, r14
0x180030976  mov     rax, r12
0x180030979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003097e  mov     edi, eax
0x180030980  xor     eax, eax
0x180030982  test    edi, edi
0x180030984  jns     short loc_1800309E1
0x180030986  mov     rcx, [rbp+48h]; this
0x18003098a  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180030991  mov     r9d, edi; char *
0x180030994  mov     edx, 9DAh; void *
0x180030999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003099e  lea     rcx, [rsp+140h+var_108]
0x1800309a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800309a8  lea     rcx, [rsp+140h+var_F8]
0x1800309ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800309b2  lea     rcx, [rsp+140h+var_100]
0x1800309b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800309bc  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, 2
0x1800309c3  jz      short loc_1800309DA
0x1800309c5  lea     rax, [rbp+40h+var_68]
0x1800309c9  lea     rdx, Inking_IStrokeCollection_Paste_Stop; int
0x1800309d0  mov     [rsp+140h+var_120], rax; PEVENT_DATA_DESCRIPTOR
0x1800309d5  call    McGenEventWrite_EventWriteTransfer
0x1800309da  mov     eax, edi
0x1800309dc  jmp     loc_180030EC1
0x1800309e1  cmp     byte ptr [rsp+140h+var_110], al
0x1800309e5  jz      loc_180030E3C
0x1800309eb  mov     r14, [rsp+140h+var_108]
0x1800309f0  lea     rcx, [rsp+140h+var_F0]
0x1800309f5  mov     [rsp+140h+var_F0], rax
0x1800309fa  mov     [rbp+40h+var_A0], rax
0x1800309fe  mov     [rsp+140h+var_E8], rax
0x180030a03  mov     rax, [r14]
0x180030a06  mov     r12, [rax+58h]
0x180030a0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030a0f  mov     rdi, cs:sourceString
0x180030a16  xor     r9d, r9d
0x180030a19  mov     [rsp+140h+length], r9d
0x180030a1e  inc     rbx
0x180030a21  cmp     [rdi+rbx*2], r9w
0x180030a26  jnz     short loc_180030A1E
0x180030a28  lea     rdx, [rsp+140h+length]; unsigned int *
0x180030a2d  mov     rcx, rbx; unsigned __int64
0x180030a30  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180030a35  test    eax, eax
0x180030a37  jns     short loc_180030A4B
0x180030a39  xor     r8d, r8d; nNumberOfArguments
0x180030a3c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180030a41  lea     edx, [r8+1]; dwExceptionFlags
0x180030a45  call    cs:__imp_RaiseException
0x180030a4b  mov     edx, [rsp+140h+length]; length
0x180030a4f  lea     r9, [rbp+40h+string]; string
0x180030a53  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x180030a57  mov     rcx, rdi; sourceString
0x180030a5a  call    cs:__imp_WindowsCreateStringReference
0x180030a60  mov     rdx, [rbp+40h+string]
0x180030a64  lea     r8, [rsp+140h+var_F0]
0x180030a69  mov     rcx, r14
0x180030a6c  mov     rax, r12
0x180030a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a74  xor     r14d, r14d
0x180030a77  mov     ebx, eax
0x180030a79  test    eax, eax
0x180030a7b  jns     short loc_180030ADD
0x180030a7d  mov     edx, 9E3h; void *
0x180030a82  mov     rcx, [rbp+48h]; this
0x180030a86  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180030a8d  mov     r9d, ebx; char *
0x180030a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a95  lea     rcx, [rsp+140h+var_E8]
0x180030a9a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030a9f  lea     rcx, [rsp+140h+var_F0]
0x180030aa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030aa9  lea     rcx, [rsp+140h+var_108]
0x180030aae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030ab3  lea     rcx, [rsp+140h+var_F8]
0x180030ab8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030abd  lea     rcx, [rsp+140h+var_100]
0x180030ac2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030ac7  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, 2
0x180030ace  jz      loc_18003080A
0x180030ad4  lea     rax, [rbp+40h+string]
0x180030ad8  jmp     loc_180030876
0x180030add  mov     rcx, [rsp+140h+var_F0]
0x180030ae2  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@Foundation@Windows@@PEAU?$IAsyncOperation@PEAUIInspectable@@@23@@Inking@Input@UI@Windows@@YAJPEAU?$IAsyncOperation@PEAUIInspectable@@@Foundation@3@@Z; Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::Foundation::IAsyncOperation<IInspectable *> *>(Windows::Foundation::IAsyncOperation<IInspectable *> *)
0x180030ae7  mov     ebx, eax
0x180030ae9  test    eax, eax
0x180030aeb  jns     short loc_180030AF4
0x180030aed  mov     edx, 9E4h
0x180030af2  jmp     short loc_180030A82
0x180030af4  mov     rdi, [rsp+140h+var_F0]
0x180030af9  lea     rcx, [rsp+140h+var_E0]
0x180030afe  mov     [rsp+140h+var_E0], r14
0x180030b03  mov     rax, [rdi]
0x180030b06  mov     rbx, [rax+40h]
0x180030b0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030b0f  lea     rdx, [rsp+140h+var_E0]
0x180030b14  mov     rcx, rdi
0x180030b17  mov     rax, rbx
0x180030b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b1f  mov     ebx, eax
0x180030b21  test    eax, eax
0x180030b23  jns     short loc_180030B4C
0x180030b25  mov     rcx, [rbp+48h]; this
0x180030b29  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180030b30  mov     r9d, eax; char *
0x180030b33  mov     edx, 9E6h; void *
0x180030b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b3d  lea     rcx, [rsp+140h+var_E0]
0x180030b42  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030b47  jmp     loc_180030A95
0x180030b4c  lea     rdx, [rsp+140h+var_D8]
0x180030b51  mov     [rsp+140h+var_D8], r14
0x180030b56  lea     rcx, [rsp+140h+var_E0]
0x180030b5b  call    ??$As@UIRandomAccessStream@Streams@Storage@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Storage::Streams::IRandomAccessStream>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>)
0x180030b60  mov     ebx, eax
0x180030b62  test    eax, eax
0x180030b64  jns     short loc_180030B8A
0x180030b66  mov     edx, 9E8h; void *
0x180030b6b  mov     rcx, [rbp+48h]; this
0x180030b6f  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180030b76  mov     r9d, ebx; char *
0x180030b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b7e  lea     rcx, [rsp+140h+var_D8]
0x180030b83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030b88  jmp     short loc_180030B3D
0x180030b8a  mov     rdi, [rsp+140h+var_D8]
0x180030b8f  lea     rcx, [rsp+140h+var_E8]
0x180030b94  mov     rax, [rdi]
0x180030b97  mov     rbx, [rax+40h]
0x180030b9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030ba0  lea     r8, [rsp+140h+var_E8]
0x180030ba5  xor     edx, edx
0x180030ba7  mov     rcx, rdi
0x180030baa  mov     rax, rbx
0x180030bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bb2  mov     ebx, eax
0x180030bb4  test    eax, eax
0x180030bb6  jns     short loc_180030BBF
0x180030bb8  mov     edx, 9E9h
0x180030bbd  jmp     short loc_180030B6B
0x180030bbf  mov     rcx, [rsp+140h+var_D8]
0x180030bc4  lea     rdx, [rbp+40h+var_A0]
0x180030bc8  mov     rax, [rcx]
0x180030bcb  mov     rax, [rax+30h]
0x180030bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bd4  lea     rcx, [rbp+40h+string]; string
0x180030bd8  mov     [rbp+40h+var_68.Ptr], r14
0x180030bdc  mov     [rsp+140h+var_D0], r14
0x180030be1  call    ??$?0$0BP@@StringReference@Internal@Windows@@QEAA@AEAY0BP@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[31])
0x180030be6  lea     rcx, [rsp+140h+var_D0]
0x180030beb  mov     rbx, [rax]
0x180030bee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180030bf3  lea     r8, [rsp+140h+var_D0]
0x180030bf8  mov     rcx, rbx
0x180030bfb  lea     rdx, _GUID_71af914d_c10f_484b_bc50_14bc623b3a27
0x180030c02  call    cs:__imp_RoGetActivationFactory
0x180030c08  mov     ebx, eax
0x180030c0a  test    eax, eax
0x180030c0c  jns     short loc_180030C35
0x180030c0e  mov     rcx, [rbp+48h]; this
0x180030c12  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180030c19  mov     r9d, eax; char *
0x180030c1c  mov     edx, 9F0h; void *
  ... truncated ...
```
