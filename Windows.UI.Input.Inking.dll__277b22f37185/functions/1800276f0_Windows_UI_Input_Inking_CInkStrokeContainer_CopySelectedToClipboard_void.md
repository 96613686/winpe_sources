# Windows::UI::Input::Inking::CInkStrokeContainer::CopySelectedToClipboard(void)

- ea: `0x1800276f0`
- end: `0x180027b8b`
- name: `?CopySelectedToClipboard@CInkStrokeContainer@Inking@Input@UI@Windows@@UEAAJXZ`
- size: `1179`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStrokeContainer *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001332c`
- `0x18001b64c`
- `0x18001f9a4`
- `0x180020774`
- `0x180021348`
- `0x1800229d8`
- `0x1800276f0`
- `0x1800328b0`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027948`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027948`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002792f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002792f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002776d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002776d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027969`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027969`

## string_xrefs

- `0x180027928`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::CInkStrokeContainer::CopySelectedToClipboard(
        Windows::UI::Input::Inking::CInkStrokeContainer *this,
        __int64 a2,
        int a3,
        int a4)
{
  HRESULT ActivationFactory; // ebx
  __int64 v6; // rdx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int64 (__fastcall *v11)(Windows::UI::Input::Inking::CInkStrokeContainer *, __int64 *); // rbx
  char v12; // r15
  unsigned int v13; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, LPVOID, __int64 *); // rbx
  int v18; // eax
  HSTRING v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, __int64, __int64 *); // rsi
  __int64 *v24; // rax
  __int64 v25; // rdi
  const unsigned __int16 *v26; // rdx
  _QWORD *v27; // rax
  __int64 v28; // rdx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int ppv; // [rsp+20h] [rbp-79h]
  _BYTE v33[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v34; // [rsp+38h] [rbp-61h] BYREF
  LPVOID v35; // [rsp+40h] [rbp-59h] BYREF
  __int64 v36; // [rsp+48h] [rbp-51h] BYREF
  __int64 v37; // [rsp+50h] [rbp-49h] BYREF
  __int64 v38; // [rsp+58h] [rbp-41h] BYREF
  __int64 v39; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v40; // [rsp+68h] [rbp-31h] BYREF
  HSTRING string; // [rsp+70h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer((int)this, (int)&Inking_IStrokeCollection_Copy_Start, a3, a4, &v43);
  v36 = 0;
  v35 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  ActivationFactory = CoCreateInstance(&rclsid, 0, 3u, &riid, &v35);
  if ( ActivationFactory < 0 )
  {
    v6 = 2407;
    goto LABEL_5;
  }
  v40 = 0;
  v11 = *(__int64 (__fastcall **)(Windows::UI::Input::Inking::CInkStrokeContainer *, __int64 *))(*(_QWORD *)this + 296LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  ActivationFactory = v11(this, &v36);
  if ( ActivationFactory < 0 )
  {
    v6 = 2411;
    goto LABEL_5;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 30) + 56LL))(
                        *((_QWORD *)this + 30),
                        &v40);
  if ( ActivationFactory < 0 )
  {
    v6 = 2413;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)ActivationFactory,
      ppv);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v7, (int)&Inking_IStrokeCollection_Copy_Stop, v8, v9, &v43);
    return (unsigned int)ActivationFactory;
  }
  v12 = 0;
  v13 = 0;
  if ( !v40 )
    goto LABEL_44;
  do
  {
    v34 = 0;
    v14 = *((_QWORD *)this + 30);
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    ActivationFactory = v15(v14, v13, &v34);
    if ( ActivationFactory < 0 )
    {
      v21 = 2417;
      goto LABEL_49;
    }
    v33[0] = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v34 + 72LL))(v34, v33);
    if ( ActivationFactory < 0 )
    {
      v21 = 2419;
LABEL_49:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)ActivationFactory,
        ppv);
      goto LABEL_50;
    }
    if ( !v33[0] )
      goto LABEL_20;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 104LL))(v36, v34);
    if ( ActivationFactory < 0 )
    {
      v21 = 2422;
      goto LABEL_49;
    }
    v16 = v34;
    v37 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v34 + 136LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    v18 = v17(v16, v35, &v37);
    ActivationFactory = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97A,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v18,
        ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
LABEL_50:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      goto LABEL_6;
    }
    v12 = 1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    ++v13;
  }
  while ( v13 < v40 );
  if ( !v12 )
    goto LABEL_44;
  v39 = 0;
  v38 = 0;
  v34 = 0;
  if ( WindowsCreateStringReference(L"Windows.System.Threading.ThreadPool", 0x23u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v19 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  ActivationFactory = RoGetActivationFactory(v19, &GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91, &v38);
  if ( ActivationFactory < 0 )
  {
    v20 = 2441;
    goto LABEL_26;
  }
  v22 = v38;
  v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v38 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  string = (HSTRING)&v39;
  hstringHeader.Reserved.Reserved1 = &v35;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = this;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v36;
  v24 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::System::Threading::IWorkItemHandler::___Windows::Foundation::IAsyncAction____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::System::Threading::IWorkItemHandler_Microsoft::WRL::FtmBase___lambda_818f522777cb716420471763d80b0bb9___1_Windows::Foundation::IAsyncAction_____lambda_818f522777cb716420471763d80b0bb9___(
                     &v43,
                     &string);
  v25 = *v24;
  *v24 = 0;
  if ( v43.Ptr )
  {
    v43.Ptr = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release();
  }
  ActivationFactory = v23(v22, v25, &v34);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( ActivationFactory < 0 )
  {
    v20 = 2482;
    goto LABEL_26;
  }
  ActivationFactory = Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction *>(v34);
  if ( ActivationFactory < 0 )
  {
    v20 = 2484;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)ActivationFactory,
      ppv);
LABEL_27:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    goto LABEL_6;
  }
  v37 = 0;
  v27 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[48])v26);
  ActivationFactory = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>(
                        *v27,
                        &v37);
  if ( ActivationFactory < 0 )
  {
    v28 = 2488;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)ActivationFactory,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    goto LABEL_27;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 56LL))(v37, v39);
  if ( ActivationFactory < 0 )
  {
    v28 = 2489;
    goto LABEL_40;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
LABEL_44:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v29, (int)&Inking_IStrokeCollection_Copy_Stop, v30, v31, &v43);
  return 0;
}

```

## disassembly

```asm
0x1800276f0  push    rbp
0x1800276f2  push    rbx
0x1800276f3  push    rsi
0x1800276f4  push    rdi
0x1800276f5  push    r12
0x1800276f7  push    r13
0x1800276f9  push    r14
0x1800276fb  push    r15
0x1800276fd  lea     rbp, [rsp-1Fh]
0x180027702  sub     rsp, 0B8h
0x180027709  mov     rax, cs:__security_cookie
0x180027710  xor     rax, rsp
0x180027713  mov     [rbp+57h+var_50], rax
0x180027717  mov     r14, rcx
0x18002771a  mov     r13b, 2
0x18002771d  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, r13b
0x180027724  jz      short loc_18002773B
0x180027726  lea     rax, [rbp+57h+var_60]
0x18002772a  mov     qword ptr [rsp+0F0h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18002772f  lea     rdx, Inking_IStrokeCollection_Copy_Start; int
0x180027736  call    McGenEventWrite_EventWriteTransfer
0x18002773b  xor     r12d, r12d
0x18002773e  mov     [rbp+57h+var_A8], r12
0x180027742  mov     [rbp+57h+var_B0], r12
0x180027746  lea     rcx, [rbp+57h+var_B0]
0x18002774a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002774f  lea     rax, [rbp+57h+var_B0]
0x180027753  mov     qword ptr [rsp+0F0h+ppv], rax; int
0x180027758  lea     r9, riid; riid
0x18002775f  xor     edx, edx; pUnkOuter
0x180027761  lea     r8d, [r12+3]; dwClsContext
0x180027766  lea     rcx, rclsid; rclsid
0x18002776d  call    cs:__imp_CoCreateInstance
0x180027773  mov     ebx, eax
0x180027775  test    eax, eax
0x180027777  jns     short loc_1800277C8
0x180027779  mov     edx, 967h; void *
0x18002777e  mov     rcx, [rbp+5Fh]; this
0x180027782  mov     r9d, ebx; char *
0x180027785  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18002778c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027791  lea     rcx, [rbp+57h+var_B0]
0x180027795  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002779a  lea     rcx, [rbp+57h+var_A8]
0x18002779e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800277a3  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, r13b
0x1800277aa  jz      short loc_1800277C1
0x1800277ac  lea     rax, [rbp+57h+var_60]
0x1800277b0  mov     qword ptr [rsp+0F0h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x1800277b5  lea     rdx, Inking_IStrokeCollection_Copy_Stop; int
0x1800277bc  call    McGenEventWrite_EventWriteTransfer
0x1800277c1  mov     eax, ebx
0x1800277c3  jmp     loc_180027B3E
0x1800277c8  mov     [rbp+57h+var_88], r12d
0x1800277cc  mov     rax, [r14]
0x1800277cf  mov     rbx, [rax+128h]
0x1800277d6  lea     rcx, [rbp+57h+var_A8]
0x1800277da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800277df  lea     rdx, [rbp+57h+var_A8]
0x1800277e3  mov     rcx, r14
0x1800277e6  mov     rax, rbx
0x1800277e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277ee  mov     ebx, eax
0x1800277f0  test    eax, eax
0x1800277f2  jns     short loc_1800277FB
0x1800277f4  mov     edx, 96Bh
0x1800277f9  jmp     short loc_18002777E
0x1800277fb  mov     rcx, [r14+0F0h]
0x180027802  mov     rax, [rcx]
0x180027805  lea     rdx, [rbp+57h+var_88]
0x180027809  mov     rax, [rax+38h]
0x18002780d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027812  mov     ebx, eax
0x180027814  test    eax, eax
0x180027816  jns     short loc_180027822
0x180027818  mov     edx, 96Dh
0x18002781d  jmp     loc_18002777E
0x180027822  mov     r15b, r12b
0x180027825  mov     esi, r12d
0x180027828  cmp     [rbp+57h+var_88], r12d
0x18002782c  jbe     loc_180027B0C
0x180027832  mov     [rbp+57h+var_B8], r12
0x180027836  mov     rdi, [r14+0F0h]
0x18002783d  mov     rax, [rdi]
0x180027840  mov     rbx, [rax+30h]
0x180027844  lea     rcx, [rbp+57h+var_B8]
0x180027848  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002784d  lea     r8, [rbp+57h+var_B8]
0x180027851  mov     edx, esi
0x180027853  mov     rcx, rdi
0x180027856  mov     rax, rbx
0x180027859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002785e  mov     ebx, eax
0x180027860  test    eax, eax
0x180027862  js      loc_180027B65
0x180027868  mov     [rbp+57h+var_C0], r12b
0x18002786c  mov     rcx, [rbp+57h+var_B8]
0x180027870  mov     rax, [rcx]
0x180027873  lea     rdx, [rbp+57h+var_C0]
0x180027877  mov     rax, [rax+48h]
0x18002787b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027880  mov     ebx, eax
0x180027882  test    eax, eax
0x180027884  js      loc_180027B5E
0x18002788a  cmp     [rbp+57h+var_C0], r12b
0x18002788e  jz      short loc_1800278F2
0x180027890  mov     rcx, [rbp+57h+var_A8]
0x180027894  mov     rax, [rcx]
0x180027897  mov     rdx, [rbp+57h+var_B8]
0x18002789b  mov     rax, [rax+68h]
0x18002789f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278a4  mov     ebx, eax
0x1800278a6  test    eax, eax
0x1800278a8  js      loc_1800279D3
0x1800278ae  mov     rdi, [rbp+57h+var_B8]
0x1800278b2  mov     [rbp+57h+var_A0], r12
0x1800278b6  mov     rax, [rdi]
0x1800278b9  mov     rbx, [rax+88h]
0x1800278c0  lea     rcx, [rbp+57h+var_A0]
0x1800278c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800278c9  lea     r8, [rbp+57h+var_A0]
0x1800278cd  mov     rdx, [rbp+57h+var_B0]
0x1800278d1  mov     rcx, rdi
0x1800278d4  mov     rax, rbx
0x1800278d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278dc  mov     ebx, eax
0x1800278de  test    eax, eax
0x1800278e0  js      loc_1800279AD
0x1800278e6  mov     r15b, 1
0x1800278e9  lea     rcx, [rbp+57h+var_A0]
0x1800278ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800278f2  lea     rcx, [rbp+57h+var_B8]
0x1800278f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800278fb  inc     esi
0x1800278fd  cmp     esi, [rbp+57h+var_88]
0x180027900  jb      loc_180027832
0x180027906  test    r15b, r15b
0x180027909  jz      loc_180027B0C
0x18002790f  mov     [rbp+57h+var_90], r12
0x180027913  mov     [rbp+57h+var_98], r12
0x180027917  mov     [rbp+57h+var_B8], r12
0x18002791b  lea     r9, [rbp+57h+string]; string
0x18002791f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180027923  mov     edx, 23h ; '#'; length
0x180027928  lea     rcx, ?RuntimeClass_Windows_System_Threading_ThreadPool@@3QBGB; "Windows.System.Threading.ThreadPool"
0x18002792f  call    cs:__imp_WindowsCreateStringReference
0x180027935  test    eax, eax
0x180027937  jns     short loc_18002794E
0x180027939  xor     r9d, r9d; lpArguments
0x18002793c  xor     r8d, r8d; nNumberOfArguments
0x18002793f  lea     edx, [r9+1]; dwExceptionFlags
0x180027943  mov     ecx, 0C000000Dh; dwExceptionCode
0x180027948  call    cs:__imp_RaiseException
0x18002794e  mov     rbx, [rbp+57h+string]
0x180027952  lea     rcx, [rbp+57h+var_98]
0x180027956  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002795b  lea     r8, [rbp+57h+var_98]
0x18002795f  lea     rdx, _GUID_b6bf67dd_84bd_44f8_ac1c_93ebcb9dba91
0x180027966  mov     rcx, rbx
0x180027969  call    cs:__imp_RoGetActivationFactory
0x18002796f  mov     ebx, eax
0x180027971  test    eax, eax
0x180027973  jns     short loc_1800279DD
0x180027975  mov     edx, 989h; void *
0x18002797a  mov     rcx, [rbp+5Fh]; this
0x18002797e  mov     r9d, ebx; char *
0x180027981  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180027988  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002798d  lea     rcx, [rbp+57h+var_B8]
0x180027991  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027996  lea     rcx, [rbp+57h+var_98]
0x18002799a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002799f  lea     rcx, [rbp+57h+var_90]
0x1800279a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800279a8  jmp     loc_180027791
0x1800279ad  mov     rcx, [rbp+5Fh]; this
0x1800279b1  mov     r9d, ebx; char *
0x1800279b4  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800279bb  mov     edx, 97Ah; void *
0x1800279c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279c5  lea     rcx, [rbp+57h+var_A0]
0x1800279c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800279ce  jmp     loc_180027B7D
0x1800279d3  mov     edx, 976h
0x1800279d8  jmp     loc_180027B6A
0x1800279dd  mov     rbx, [rbp+57h+var_98]
0x1800279e1  mov     rax, [rbx]
0x1800279e4  mov     rsi, [rax+30h]
0x1800279e8  lea     rcx, [rbp+57h+var_B8]
0x1800279ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800279f1  lea     rax, [rbp+57h+var_90]
0x1800279f5  mov     [rbp+57h+string], rax
0x1800279f9  lea     rax, [rbp+57h+var_B0]
0x1800279fd  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180027a01  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r14
0x180027a05  lea     rax, [rbp+57h+var_A8]
0x180027a09  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x180027a0d  lea     rdx, [rbp+57h+string]
0x180027a11  lea     rcx, [rbp+57h+var_60]
0x180027a15  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__System__Threading__IWorkItemHandler_____Windows__Foundation__IAsyncAction______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__System__Threading__IWorkItemHandler_Microsoft__WRL__FtmBase___lambda_818f522777cb716420471763d80b0bb9___1_Windows__Foundation__IAsyncAction_____lambda_818f522777cb716420471763d80b0bb9___
0x180027a1a  mov     rdi, [rax]
0x180027a1d  mov     [rax], r12
0x180027a20  mov     rcx, [rbp+57h+var_60.Ptr]
0x180027a24  test    rcx, rcx
0x180027a27  jz      short loc_180027A32
0x180027a29  mov     [rbp+57h+var_60.Ptr], r12
0x180027a2d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x180027a32  lea     r8, [rbp+57h+var_B8]
0x180027a36  mov     rdx, rdi
0x180027a39  mov     rcx, rbx
0x180027a3c  mov     rax, rsi
0x180027a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a44  mov     ebx, eax
0x180027a46  test    rdi, rdi
0x180027a49  jz      short loc_180027A5B
0x180027a4b  mov     rdx, [rdi]
0x180027a4e  mov     rcx, rdi
0x180027a51  mov     rax, [rdx+10h]
0x180027a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a5a  nop
0x180027a5b  test    ebx, ebx
0x180027a5d  jns     short loc_180027A69
0x180027a5f  mov     edx, 9B2h
0x180027a64  jmp     loc_18002797A
0x180027a69  mov     rcx, [rbp+57h+var_B8]
0x180027a6d  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@PEAUIAsyncAction@23@@Inking@Input@UI@Windows@@YAJPEAUIAsyncAction@Foundation@3@@Z; Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *)
0x180027a72  mov     ebx, eax
0x180027a74  test    eax, eax
0x180027a76  jns     short loc_180027A82
0x180027a78  mov     edx, 9B4h
0x180027a7d  jmp     loc_18002797A
0x180027a82  mov     [rbp+57h+var_A0], r12
0x180027a86  lea     rcx, [rbp+57h+string]; string
0x180027a8a  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x180027a8f  lea     rdx, [rbp+57h+var_A0]
0x180027a93  mov     rcx, [rax]
0x180027a96  call    ??$GetActivationFactory@V?$ComPtr@UIClipboardStatics@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIClipboardStatics@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>)
0x180027a9b  mov     ebx, eax
0x180027a9d  test    eax, eax
0x180027a9f  jns     short loc_180027AC7
0x180027aa1  mov     edx, 9B8h; void *
0x180027aa6  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180027aad  mov     r9d, ebx; char *
0x180027ab0  mov     rcx, [rbp+5Fh]; this
0x180027ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ab9  lea     rcx, [rbp+57h+var_A0]
0x180027abd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027ac2  jmp     loc_18002798D
0x180027ac7  mov     rcx, [rbp+57h+var_A0]
0x180027acb  mov     rax, [rcx]
0x180027ace  mov     rdx, [rbp+57h+var_90]
0x180027ad2  mov     rax, [rax+38h]
0x180027ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027adb  mov     ebx, eax
0x180027add  test    eax, eax
0x180027adf  jns     short loc_180027AE8
0x180027ae1  mov     edx, 9B9h
0x180027ae6  jmp     short loc_180027AA6
0x180027ae8  lea     rcx, [rbp+57h+var_A0]
0x180027aec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027af1  lea     rcx, [rbp+57h+var_B8]
0x180027af5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027afa  lea     rcx, [rbp+57h+var_98]
0x180027afe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027b03  lea     rcx, [rbp+57h+var_90]
0x180027b07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027b0c  lea     rcx, [rbp+57h+var_B0]
0x180027b10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027b15  lea     rcx, [rbp+57h+var_A8]
0x180027b19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027b1e  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, r13b
0x180027b25  jz      short loc_180027B3C
0x180027b27  lea     rax, [rbp+57h+var_60]
0x180027b2b  mov     qword ptr [rsp+0F0h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x180027b30  lea     rdx, Inking_IStrokeCollection_Copy_Stop; int
0x180027b37  call    McGenEventWrite_EventWriteTransfer
0x180027b3c  xor     eax, eax
0x180027b3e  mov     rcx, [rbp+57h+var_50]
0x180027b42  xor     rcx, rsp; StackCookie
0x180027b45  call    __security_check_cookie
0x180027b4a  add     rsp, 0B8h
0x180027b51  pop     r15
0x180027b53  pop     r14
0x180027b55  pop     r13
0x180027b57  pop     r12
0x180027b59  pop     rdi
0x180027b5a  pop     rsi
0x180027b5b  pop     rbx
0x180027b5c  pop     rbp
0x180027b5d  retn
0x180027b5e  mov     edx, 973h
0x180027b63  jmp     short loc_180027B6A
0x180027b65  mov     edx, 971h; void *
0x180027b6a  mov     rcx, [rbp+5Fh]; this
0x180027b6e  mov     r9d, ebx; char *
0x180027b71  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180027b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b7d  lea     rcx, [rbp+57h+var_B8]
0x180027b81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027b86  jmp     loc_180027791
  ... truncated ...
```
