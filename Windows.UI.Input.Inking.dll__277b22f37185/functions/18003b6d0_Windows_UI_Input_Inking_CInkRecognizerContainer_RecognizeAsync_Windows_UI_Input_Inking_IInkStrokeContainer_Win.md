# Windows::UI::Input::Inking::CInkRecognizerContainer::RecognizeAsync(Windows::UI::Input::Inking::IInkStrokeContainer *,Windows::UI::Input::Inking::InkRecognitionTarget,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::UI::Input::Inking::InkRecognitionResult *> *> * *)

- ea: `0x18003b6d0`
- end: `0x18003b985`
- name: `?RecognizeAsync@CInkRecognizerContainer@Inking@Input@UI@Windows@@UEAAJPEAUIInkStrokeContainer@2345@W4InkRecognitionTarget@2345@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@Collections@Foundation@Windows@@@Foundation@5@@Z`
- size: `693`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001043c`
- `0x18001332c`
- `0x180019248`
- `0x18001b64c`
- `0x1800386dc`
- `0x18003b6d0`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b92e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b92e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003b79e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003b941`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003b79e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003b941`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b7d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003b7d9`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkRecognizerContainer::RecognizeAsync(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v5; // r12d
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 *v11; // rsi
  __int64 v12; // rax
  HRESULT v13; // edi
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int ppv; // [rsp+20h] [rbp-59h]
  __int64 v21; // [rsp+40h] [rbp-39h] BYREF
  LPVOID v22; // [rsp+48h] [rbp-31h] BYREF
  __int64 v23; // [rsp+50h] [rbp-29h] BYREF
  __int64 v24; // [rsp+58h] [rbp-21h] BYREF
  int v25; // [rsp+60h] [rbp-19h] BYREF
  __int64 v26; // [rsp+68h] [rbp-11h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-9h] BYREF
  LARGE_INTEGER v28; // [rsp+78h] [rbp-1h] BYREF
  LPVOID v29; // [rsp+80h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR SRWLock; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = a3;
  if ( !a2 )
  {
    v8 = 602;
LABEL_3:
    v9 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\recognizercollection.cpp",
      (const char *)v9,
      ppv);
    return v9;
  }
  if ( !a4 )
  {
    v8 = 603;
    goto LABEL_3;
  }
  if ( (unsigned int)a3 > 2 )
  {
    v9 = -2147024809;
    v8 = 609;
    goto LABEL_4;
  }
  v11 = (__int64 *)(a1 + 104);
  v12 = *(_QWORD *)(a1 + 104);
  if ( v12 )
  {
    if ( *(_BYTE *)(v12 + 112) )
      return 2147483662LL;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 104);
  }
  PerformanceCount.QuadPart = 0;
  v28.QuadPart = 0;
  if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)&Inking_IRecognizerCollection_Recognize_Start,
      a3,
      (__int64)a4,
      &SRWLock);
  QueryPerformanceCounter(&PerformanceCount);
  v25 = 0;
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  v13 = CoCreateInstance(&stru_1801170B0, 0, 3u, &stru_1801170E0, &v22);
  if ( v13 >= 0 )
  {
    v14 = *a2;
    v26 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, _QWORD, __int64 *))(v14 + 184))(a2, v22, v5, &v26);
    if ( v13 >= 0 )
    {
      if ( v26 )
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 56LL))(v26, &v25);
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 112);
      v23 = *(_QWORD *)(a1 + 64);
      v24 = *(_QWORD *)(a1 + 56);
      v29 = v22;
      v21 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      v13 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Input::Inking::CInkRecognizeOperation,Windows::UI::Input::Inking::CInkRecognizeOperation,unsigned int &,IInkDisp *,IInkStrokes * &,IInkRecognizerContext * &,HSTRING__ *,Windows::UI::Input::Internal::Inking::CInputGuide *,enum Windows::UI::Input::Internal::Inking::InkRecognizerTextSeparator &>(
              (unsigned int)&v21,
              (int)a1 + 128,
              (unsigned int)&v29,
              (unsigned int)&v26,
              a1 + 88,
              (__int64)&v24,
              (__int64)&v23,
              a1 + 132);
      if ( v13 >= 0 )
      {
        v15 = v21;
        ++*(_DWORD *)(a1 + 128);
        LODWORD(v24) = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v15 + 16) + 56LL))(v15 + 16, &v24);
        if ( v13 >= 0 )
        {
          if ( (_DWORD)v24 == 3 )
          {
            v13 = -2147467259;
          }
          else
          {
            v16 = v21;
            if ( *v11 != v21 )
            {
              v23 = v21;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v23);
              v23 = *v11;
              *v11 = v16;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
              v16 = v21;
            }
            v21 = 0;
            *a4 = v16;
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
      if ( SRWLock.Ptr )
        ReleaseSRWLockExclusive((PSRWLOCK)SRWLock.Ptr);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  QueryPerformanceCounter(&v28);
  if ( (Microsoft_Windows_UI_Input_InkingEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v17,
      (const EVENT_DESCRIPTOR *)&Inking_IRecognizerCollection_Recognize_Stop,
      v18,
      v19,
      &SRWLock);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18003b6d0  push    rbp
0x18003b6d2  push    rbx
0x18003b6d3  push    rsi
0x18003b6d4  push    rdi
0x18003b6d5  push    r12
0x18003b6d7  push    r14
0x18003b6d9  push    r15
0x18003b6db  lea     rbp, [rsp-27h]
0x18003b6e0  sub     rsp, 0A0h
0x18003b6e7  mov     rax, cs:__security_cookie
0x18003b6ee  xor     rax, rsp
0x18003b6f1  mov     [rbp+57h+var_38], rax
0x18003b6f5  mov     r14, r9
0x18003b6f8  mov     r12d, r8d
0x18003b6fb  mov     r15, rdx
0x18003b6fe  mov     rbx, rcx
0x18003b701  test    rdx, rdx
0x18003b704  jnz     short loc_18003B72A
0x18003b706  mov     edx, 25Ah; void *
0x18003b70b  mov     ebx, 80004003h
0x18003b710  mov     rcx, [rbp+5Fh]; this
0x18003b714  lea     r8, aOnecoreuapWind_41; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18003b71b  mov     r9d, ebx; char *
0x18003b71e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b723  mov     eax, ebx
0x18003b725  jmp     loc_18003B967
0x18003b72a  test    r14, r14
0x18003b72d  jnz     short loc_18003B736
0x18003b72f  mov     edx, 25Bh
0x18003b734  jmp     short loc_18003B70B
0x18003b736  cmp     r12d, 2
0x18003b73a  jbe     short loc_18003B748
0x18003b73c  mov     ebx, 80070057h
0x18003b741  mov     edx, 261h
0x18003b746  jmp     short loc_18003B710
0x18003b748  lea     rsi, [rcx+68h]
0x18003b74c  mov     rax, [rsi]
0x18003b74f  test    rax, rax
0x18003b752  jz      short loc_18003B76C
0x18003b754  cmp     byte ptr [rax+70h], 0
0x18003b758  jz      short loc_18003B764
0x18003b75a  mov     eax, 8000000Eh
0x18003b75f  jmp     loc_18003B967
0x18003b764  mov     rcx, rsi
0x18003b767  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b76c  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, 2
0x18003b773  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x18003b77b  mov     qword ptr [rbp+57h+var_58], 0
0x18003b783  jz      short loc_18003B79A
0x18003b785  lea     rax, [rbp+57h+SRWLock]
0x18003b789  lea     rdx, Inking_IRecognizerCollection_Recognize_Start; int
0x18003b790  mov     [rsp+0D0h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18003b795  call    McGenEventWrite_EventWriteTransfer
0x18003b79a  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18003b79e  call    cs:__imp_QueryPerformanceCounter
0x18003b7a4  lea     rcx, [rbp+57h+var_88]
0x18003b7a8  mov     [rbp+57h+var_70], 0
0x18003b7af  mov     [rbp+57h+var_88], 0
0x18003b7b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b7bc  xor     edx, edx; pUnkOuter
0x18003b7be  lea     rax, [rbp+57h+var_88]
0x18003b7c2  lea     r9, stru_1801170E0; riid
0x18003b7c9  mov     [rsp+0D0h+ppv], rax; ppv
0x18003b7ce  lea     rcx, stru_1801170B0; rclsid
0x18003b7d5  lea     r8d, [rdx+3]; dwClsContext
0x18003b7d9  call    cs:__imp_CoCreateInstance
0x18003b7df  mov     edi, eax
0x18003b7e1  test    eax, eax
0x18003b7e3  js      loc_18003B934
0x18003b7e9  mov     rax, [r15]
0x18003b7ec  lea     r9, [rbp+57h+var_68]
0x18003b7f0  mov     rdx, [rbp+57h+var_88]
0x18003b7f4  mov     r8d, r12d
0x18003b7f7  mov     rcx, r15
0x18003b7fa  mov     [rbp+57h+var_68], 0
0x18003b802  mov     rax, [rax+0B8h]
0x18003b809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b80e  mov     edi, eax
0x18003b810  test    eax, eax
0x18003b812  js      loc_18003B934
0x18003b818  mov     rcx, [rbp+57h+var_68]
0x18003b81c  test    rcx, rcx
0x18003b81f  jz      short loc_18003B831
0x18003b821  mov     rax, [rcx]
0x18003b824  lea     rdx, [rbp+57h+var_70]
0x18003b828  mov     rax, [rax+38h]
0x18003b82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b831  lea     rdx, [rbx+70h]
0x18003b835  lea     rcx, [rbp+57h+SRWLock]
0x18003b839  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003b83e  mov     rax, [rbx+40h]
0x18003b842  lea     rcx, [rbp+57h+var_90]
0x18003b846  mov     [rbp+57h+var_80], rax
0x18003b84a  mov     rax, [rbx+38h]
0x18003b84e  mov     [rbp+57h+var_78], rax
0x18003b852  mov     rax, [rbp+57h+var_88]
0x18003b856  mov     [rbp+57h+var_50], rax
0x18003b85a  mov     [rbp+57h+var_90], 0
0x18003b862  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b867  lea     rax, [rbx+84h]
0x18003b86e  mov     [rsp+0D0h+var_98], rax
0x18003b873  lea     rcx, [rbx+58h]
0x18003b877  lea     rax, [rbp+57h+var_80]
0x18003b87b  mov     [rsp+0D0h+var_A0], rax
0x18003b880  lea     r15, [rbx+80h]
0x18003b887  lea     rax, [rbp+57h+var_78]
0x18003b88b  mov     rdx, r15
0x18003b88e  mov     [rsp+0D0h+var_A8], rax
0x18003b893  lea     r9, [rbp+57h+var_68]
0x18003b897  mov     [rsp+0D0h+ppv], rcx
0x18003b89c  lea     r8, [rbp+57h+var_50]
0x18003b8a0  lea     rcx, [rbp+57h+var_90]
0x18003b8a4  call    ??$MakeAndInitialize@VCInkRecognizeOperation@Inking@Input@UI@Windows@@V12345@AEAIPEAUIInkDisp@@AEAPEAUIInkStrokes@@AEAPEAUIInkRecognizerContext@@PEAUHSTRING__@@PEAVCInputGuide@2Internal@345@AEAW4InkRecognizerTextSeparator@2Internal@345@@Details@WRL@Microsoft@@YAJPEAPEAVCInkRecognizeOperation@Inking@Input@UI@Windows@@AEAI$$QEAPEAUIInkDisp@@AEAPEAUIInkStrokes@@AEAPEAUIInkRecognizerContext@@$$QEAPEAUHSTRING__@@$$QEAPEAVCInputGuide@4Internal@567@AEAW4InkRecognizerTextSeparator@4Internal@567@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Input::Inking::CInkRecognizeOperation,Windows::UI::Input::Inking::CInkRecognizeOperation,uint &,IInkDisp *,IInkStrokes * &,IInkRecognizerContext * &,HSTRING__ *,Windows::UI::Input::Internal::Inking::CInputGuide *,Windows::UI::Input::Internal::Inking::InkRecognizerTextSeparator &>(Windows::UI::Input::Inking::CInkRecognizeOperation * *,uint &,IInkDisp * &&,IInkStrokes * &,IInkRecognizerContext * &,HSTRING__ * &&,Windows::UI::Input::Internal::Inking::CInputGuide * &&,Windows::UI::Input::Internal::Inking::InkRecognizerTextSeparator &)
0x18003b8a9  mov     edi, eax
0x18003b8ab  test    eax, eax
0x18003b8ad  js      short loc_18003B91C
0x18003b8af  mov     rcx, [rbp+57h+var_90]
0x18003b8b3  lea     rdx, [rbp+57h+var_78]
0x18003b8b7  inc     dword ptr [r15]
0x18003b8ba  add     rcx, 10h
0x18003b8be  mov     dword ptr [rbp+57h+var_78], 0
0x18003b8c5  mov     rax, [rcx]
0x18003b8c8  mov     rax, [rax+38h]
0x18003b8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8d1  mov     edi, eax
0x18003b8d3  test    eax, eax
0x18003b8d5  js      short loc_18003B91C
0x18003b8d7  cmp     dword ptr [rbp+57h+var_78], 3
0x18003b8db  jz      short loc_18003B917
0x18003b8dd  mov     rbx, [rbp+57h+var_90]
0x18003b8e1  cmp     [rsi], rbx
0x18003b8e4  jz      short loc_18003B90A
0x18003b8e6  lea     rcx, [rbp+57h+var_80]
0x18003b8ea  mov     [rbp+57h+var_80], rbx
0x18003b8ee  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x18003b8f3  mov     rax, [rsi]
0x18003b8f6  lea     rcx, [rbp+57h+var_80]
0x18003b8fa  mov     [rbp+57h+var_80], rax
0x18003b8fe  mov     [rsi], rbx
0x18003b901  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b906  mov     rbx, [rbp+57h+var_90]
0x18003b90a  mov     [rbp+57h+var_90], 0
0x18003b912  mov     [r14], rbx
0x18003b915  jmp     short loc_18003B91C
0x18003b917  mov     edi, 80004005h
0x18003b91c  lea     rcx, [rbp+57h+var_90]
0x18003b920  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b925  mov     rcx, qword ptr [rbp+57h+SRWLock]; SRWLock
0x18003b929  test    rcx, rcx
0x18003b92c  jz      short loc_18003B934
0x18003b92e  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b934  lea     rcx, [rbp+57h+var_88]
0x18003b938  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b93d  lea     rcx, [rbp+57h+var_58]; lpPerformanceCount
0x18003b941  call    cs:__imp_QueryPerformanceCounter
0x18003b947  test    byte ptr cs:Microsoft_Windows_UI_Input_InkingEnableBits, 2
0x18003b94e  jz      short loc_18003B965
0x18003b950  lea     rax, [rbp+57h+SRWLock]
0x18003b954  lea     rdx, Inking_IRecognizerCollection_Recognize_Stop; int
0x18003b95b  mov     [rsp+0D0h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18003b960  call    McGenEventWrite_EventWriteTransfer
0x18003b965  mov     eax, edi
0x18003b967  mov     rcx, [rbp+57h+var_38]
0x18003b96b  xor     rcx, rsp; StackCookie
0x18003b96e  call    __security_check_cookie
0x18003b973  add     rsp, 0A0h
0x18003b97a  pop     r15
0x18003b97c  pop     r14
0x18003b97e  pop     r12
0x18003b980  pop     rdi
0x18003b981  pop     rsi
0x18003b982  pop     rbx
0x18003b983  pop     rbp
0x18003b984  retn
```
