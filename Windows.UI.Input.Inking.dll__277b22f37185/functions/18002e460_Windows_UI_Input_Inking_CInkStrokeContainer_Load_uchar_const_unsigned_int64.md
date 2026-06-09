# Windows::UI::Input::Inking::CInkStrokeContainer::Load(uchar const *,unsigned __int64)

- ea: `0x18002e460`
- end: `0x18002e9df`
- name: `?Load@CInkStrokeContainer@Inking@Input@UI@Windows@@UEAAJPEBE_K@Z`
- size: `1407`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStrokeContainer *__hidden this, const unsigned __int8 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800101bc`
- `0x18001332c`
- `0x18001c138`
- `0x18001c2f8`
- `0x18002e460`
- `0x180031e40`
- `0x1800337d0`
- `0x1800338e8`
- `0x18005efa4`
- `0x18005f664`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e4a1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e8da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e958`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e4a1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e8da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e958`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002e8d0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002e8d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e561`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e561`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::CInkStrokeContainer::Load(
        Windows::UI::Input::Inking::CInkStrokeContainer *this,
        const unsigned __int8 *a2,
        __int64 a3)
{
  unsigned int v6; // r15d
  int v7; // ebx
  __int64 v8; // rdx
  bool v10; // r12
  unsigned int v11; // edi
  char v12; // r13
  HRESULT v13; // esi
  __int64 v14; // rcx
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int64 *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  __int64 v21; // r12
  _QWORD *v22; // r15
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 (__fastcall *v25)(_QWORD *, __int64 *); // rbx
  int v26; // ebx
  unsigned int v27; // edi
  unsigned int v28; // eax
  int (__fastcall *v29)(Windows::UI::Input::Inking::CInkStrokeContainer *, __int64 *); // rbx
  double DurationInMs; // xmm7_8
  double v31; // xmm6_8
  double v32; // xmm0_8
  int ppv; // [rsp+28h] [rbp-B9h]
  unsigned int v34; // [rsp+38h] [rbp-A9h]
  unsigned int v35; // [rsp+3Ch] [rbp-A5h]
  __int64 v36; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v37; // [rsp+48h] [rbp-99h] BYREF
  int v38; // [rsp+50h] [rbp-91h] BYREF
  int v39; // [rsp+54h] [rbp-8Dh] BYREF
  __int64 v40; // [rsp+58h] [rbp-89h]
  __int64 v41; // [rsp+60h] [rbp-81h] BYREF
  LPVOID v42; // [rsp+68h] [rbp-79h] BYREF
  __int64 v43; // [rsp+70h] [rbp-71h] BYREF
  __int64 v44; // [rsp+78h] [rbp-69h] BYREF
  LARGE_INTEGER v45; // [rsp+80h] [rbp-61h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-59h] BYREF
  LARGE_INTEGER v47; // [rsp+90h] [rbp-51h] BYREF
  _QWORD *v48; // [rsp+98h] [rbp-49h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-41h] BYREF
  SAFEARRAY *psa[2]; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-29h]
  __int128 v52; // [rsp+C8h] [rbp-19h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]
  __int64 v55; // [rsp+148h] [rbp+67h] BYREF
  bool v56; // [rsp+160h] [rbp+7Fh]

  v6 = 0;
  PerformanceCount.QuadPart = 0;
  v45.QuadPart = 0;
  v47.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  LODWORD(v36) = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 30) + 56LL))(*((_QWORD *)this + 30), &v36);
  if ( v7 < 0 )
  {
    v8 = 1131;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    return (unsigned int)v7;
  }
  v10 = (_DWORD)v36 == 0;
  v56 = (_DWORD)v36 == 0;
  *(_OWORD *)psa = 0;
  v51 = 0;
  v7 = (*(__int64 (__fastcall **)(Windows::UI::Input::Inking::CInkStrokeContainer *, const unsigned __int8 *, __int64, SAFEARRAY **))(*(_QWORD *)this + 344LL))(
         this,
         a2,
         a3,
         psa);
  if ( v7 < 0 )
  {
    v8 = 1138;
    goto LABEL_3;
  }
  v11 = 0;
  v34 = 0;
  v12 = 0;
  v42 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v13 = CoCreateInstance(&rclsid, 0, 3u, &riid, &v42);
  if ( v13 >= 0 )
  {
    v52 = *(_OWORD *)psa;
    v53 = v51;
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v42 + 208LL))(v42, &v52);
    if ( v13 >= 0 )
    {
      (*(void (__fastcall **)(Windows::UI::Input::Inking::CInkStrokeContainer *))(*(_QWORD *)this + 320LL))(this);
      v14 = *((_QWORD *)this + 32);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 120LL))(v14);
      v12 = 1;
      v41 = 0;
      v15 = v42;
      v16 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v42 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v13 = v16(v15, &v41);
      if ( v13 < 0
        || (v38 = 0, v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 56LL))(v41, &v38), v13 < 0) )
      {
        v11 = 0;
      }
      else
      {
        v11 = v38;
        v35 = v38;
        if ( v38 > 0 )
        {
          LOBYTE(v55) = 0;
          LODWORD(v40) = 0;
          while ( 1 )
          {
            v37 = 0;
            v17 = v41;
            v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 96LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
            v13 = v18(v17, v6, &v37);
            if ( v13 < 0 )
              break;
            v44 = 0;
            v19 = v37;
            v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 72LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            v13 = v20(v19, &v44);
            if ( v13 >= 0 )
            {
              Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkDrawingAttributes,>(&v49);
              v21 = v49;
              if ( v49 )
              {
                v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 136LL))(v49, v44);
                if ( v13 >= 0 )
                {
                  Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkStroke,>(&v48);
                  v22 = v48;
                  if ( v48 )
                  {
                    v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _QWORD, _QWORD))(*v48 + 128LL))(
                            v48,
                            v37,
                            v21,
                            0,
                            0);
                    if ( v13 >= 0 )
                    {
                      LOBYTE(v23) = 1;
                      wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrokeIdAndTimestamp>::ReportUsage(
                        `wil::Feature<__WilFeatureTraits_Feature_StrokeIdAndTimestamp>::GetImpl'::`2'::impl,
                        v23);
                      v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v22 + 216LL))(v22, v37);
                      if ( v13 >= 0 )
                      {
                        LOBYTE(v24) = 1;
                        wil::details::FeatureImpl<__WilFeatureTraits_Feature_InkPointTimestamp>::ReportUsage(
                          `wil::Feature<__WilFeatureTraits_Feature_InkPointTimestamp>::GetImpl'::`2'::impl,
                          v24);
                        v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v22 + 224LL))(v22, v37);
                        if ( v13 >= 0 )
                        {
                          (*(void (__fastcall **)(_QWORD *))(*v22 + 176LL))(v22);
                          v13 = (*(__int64 (__fastcall **)(Windows::UI::Input::Inking::CInkStrokeContainer *, _QWORD *, __int64))(*(_QWORD *)this + 304LL))(
                                  this,
                                  v22,
                                  0xFFFFFFFFLL);
                          if ( v13 >= 0 && !(_BYTE)v55 )
                          {
                            v39 = 0;
                            v43 = 0;
                            v25 = *(__int64 (__fastcall **)(_QWORD *, __int64 *))(v22[2] + 64LL);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
                            v26 = v25(v22 + 2, &v43);
                            if ( v26 < 0
                              || (v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 56LL))(v43, &v39),
                                  v26 < 0) )
                            {
                              LOBYTE(v55) = 1;
                              v27 = v34;
                            }
                            else
                            {
                              v27 = v39 + v34;
                            }
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
                            v28 = 0;
                            if ( v26 >= 0 )
                              v28 = v27;
                            v34 = v28;
                          }
                        }
                      }
                    }
                  }
                  else
                  {
                    v13 = -2147024882;
                  }
                  if ( v22 )
                  {
                    v48 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
                  }
                  v6 = v40;
                }
              }
              else
              {
                v13 = -2147024882;
              }
              if ( v21 )
              {
                v49 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            if ( v13 < 0 )
              break;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
            LODWORD(v40) = ++v6;
            if ( (int)v6 >= v38 )
              goto LABEL_40;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
LABEL_40:
          v6 = v34;
          v11 = v35;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v10 = v56;
    }
  }
  SafeArrayDestroy(psa[1]);
  QueryPerformanceCounter(&v45);
  if ( v12
    && (!v10
     || (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 30) + 56LL))(*((_QWORD *)this + 30), &v36) >= 0
     && (_DWORD)v36) )
  {
    v55 = 0;
    v29 = *(int (__fastcall **)(Windows::UI::Input::Inking::CInkStrokeContainer *, __int64 *))(*(_QWORD *)this + 296LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    if ( v29(this, &v55) >= 0 )
      CInkStrokeContainerEventHelper::RaiseEvent((char *)this + 112, 4, this, v55);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  }
  QueryPerformanceCounter(&v47);
  if ( v13 >= 0 )
  {
    DurationInMs = GetDurationInMs(&v45, &v47);
    v31 = GetDurationInMs(&PerformanceCount, &v45);
    v32 = GetDurationInMs((union _LARGE_INTEGER *)this + 34, &PerformanceCount);
    LogStrokeCollection(*((_QWORD *)this + 34), v32, v31, DurationInMs, v11, v6);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002e460  mov     rax, rsp
0x18002e463  mov     [rax+10h], rbx
0x18002e467  push    rbp
0x18002e468  push    rsi
0x18002e469  push    rdi
0x18002e46a  push    r12
0x18002e46c  push    r13
0x18002e46e  push    r14
0x18002e470  push    r15
0x18002e472  lea     rbp, [rax-5Fh]
0x18002e476  sub     rsp, 100h
0x18002e47d  movaps  xmmword ptr [rax-48h], xmm6
0x18002e481  movaps  xmmword ptr [rax-58h], xmm7
0x18002e485  mov     rdi, r8
0x18002e488  mov     rsi, rdx
0x18002e48b  mov     r14, rcx
0x18002e48e  xor     r15d, r15d
0x18002e491  mov     qword ptr [rbp+57h+PerformanceCount], r15
0x18002e495  mov     qword ptr [rbp+57h+var_B8], r15
0x18002e499  mov     qword ptr [rbp+57h+var_A8], r15
0x18002e49d  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18002e4a1  call    cs:__imp_QueryPerformanceCounter
0x18002e4a7  mov     dword ptr [rsp+130h+var_F8], r15d
0x18002e4ac  mov     rcx, [r14+0F0h]
0x18002e4b3  mov     rax, [rcx]
0x18002e4b6  lea     rdx, [rsp+130h+var_F8]
0x18002e4bb  mov     rax, [rax+38h]
0x18002e4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4c4  mov     ebx, eax
0x18002e4c6  test    eax, eax
0x18002e4c8  jns     short loc_18002E4E9
0x18002e4ca  mov     edx, 46Bh; void *
0x18002e4cf  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18002e4d6  mov     r9d, ebx; char *
0x18002e4d9  mov     rcx, [rbp+5Fh]; this
0x18002e4dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4e2  mov     eax, ebx
0x18002e4e4  jmp     loc_18002E9BA
0x18002e4e9  cmp     dword ptr [rsp+130h+var_F8], r15d
0x18002e4ee  setz    r12b
0x18002e4f2  mov     [rbp+57h+arg_18], r12b
0x18002e4f6  xorps   xmm0, xmm0
0x18002e4f9  xor     eax, eax
0x18002e4fb  movups  xmmword ptr [rbp+57h+psa], xmm0
0x18002e4ff  mov     [rbp+57h+var_80], rax
0x18002e503  mov     rax, [r14]
0x18002e506  lea     r9, [rbp+57h+psa]
0x18002e50a  mov     r8, rdi
0x18002e50d  mov     rdx, rsi
0x18002e510  mov     rcx, r14
0x18002e513  mov     rax, [rax+158h]
0x18002e51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e51f  mov     ebx, eax
0x18002e521  test    eax, eax
0x18002e523  jns     short loc_18002E52C
0x18002e525  mov     edx, 472h
0x18002e52a  jmp     short loc_18002E4CF
0x18002e52c  xor     ebx, ebx
0x18002e52e  mov     edi, ebx
0x18002e530  mov     [rsp+130h+var_100], ebx
0x18002e534  mov     r13b, bl
0x18002e537  mov     [rbp+57h+var_D0], rbx
0x18002e53b  lea     rcx, [rbp+57h+var_D0]
0x18002e53f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e544  lea     rax, [rbp+57h+var_D0]
0x18002e548  mov     [rsp+130h+ppv], rax; ppv
0x18002e54d  lea     r9, riid; riid
0x18002e554  xor     edx, edx; pUnkOuter
0x18002e556  lea     r8d, [rbx+3]; dwClsContext
0x18002e55a  lea     rcx, rclsid; rclsid
0x18002e561  call    cs:__imp_CoCreateInstance
0x18002e567  mov     esi, eax
0x18002e569  test    eax, eax
0x18002e56b  js      loc_18002E8CC
0x18002e571  mov     rcx, [rbp+57h+var_D0]
0x18002e575  movups  xmm0, xmmword ptr [rbp+57h+psa]
0x18002e579  movaps  [rbp+57h+var_70], xmm0
0x18002e57d  movsd   xmm1, [rbp+57h+var_80]
0x18002e582  movsd   [rbp+57h+var_60], xmm1
0x18002e587  mov     rax, [rcx]
0x18002e58a  lea     rdx, [rbp+57h+var_70]
0x18002e58e  mov     rax, [rax+0D0h]
0x18002e595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e59a  mov     esi, eax
0x18002e59c  test    eax, eax
0x18002e59e  js      loc_18002E8CC
0x18002e5a4  mov     rax, [r14]
0x18002e5a7  mov     rcx, r14
0x18002e5aa  mov     rax, [rax+140h]
0x18002e5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5b6  mov     rcx, [r14+100h]
0x18002e5bd  test    rcx, rcx
0x18002e5c0  jz      short loc_18002E5CE
0x18002e5c2  mov     rax, [rcx]
0x18002e5c5  mov     rax, [rax+78h]
0x18002e5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5ce  mov     r13d, 1
0x18002e5d4  mov     [rsp+130h+var_D8], rbx
0x18002e5d9  mov     rdi, [rbp+57h+var_D0]
0x18002e5dd  mov     rax, [rdi]
0x18002e5e0  mov     rbx, [rax+38h]
0x18002e5e4  lea     rcx, [rsp+130h+var_D8]
0x18002e5e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e5ee  lea     rdx, [rsp+130h+var_D8]
0x18002e5f3  mov     rcx, rdi
0x18002e5f6  mov     rax, rbx
0x18002e5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5fe  mov     esi, eax
0x18002e600  xor     ebx, ebx
0x18002e602  test    eax, eax
0x18002e604  js      loc_18002E8BC
0x18002e60a  mov     [rsp+130h+var_E8], ebx
0x18002e60e  mov     rcx, [rsp+130h+var_D8]
0x18002e613  mov     rax, [rcx]
0x18002e616  lea     rdx, [rsp+130h+var_E8]
0x18002e61b  mov     rax, [rax+38h]
0x18002e61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e624  mov     esi, eax
0x18002e626  test    eax, eax
0x18002e628  js      loc_18002E8BC
0x18002e62e  mov     edi, [rsp+130h+var_E8]
0x18002e632  mov     [rsp+130h+var_FC], edi
0x18002e636  test    edi, edi
0x18002e638  jle     loc_18002E8BE
0x18002e63e  mov     byte ptr [rbp+57h+arg_0], bl
0x18002e641  mov     dword ptr [rsp+130h+var_E0], r15d
0x18002e646  mov     [rsp+130h+var_F0], rbx
0x18002e64b  mov     rdi, [rsp+130h+var_D8]
0x18002e650  mov     rax, [rdi]
0x18002e653  mov     rbx, [rax+60h]
0x18002e657  lea     rcx, [rsp+130h+var_F0]
0x18002e65c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e661  lea     r8, [rsp+130h+var_F0]
0x18002e666  mov     edx, r15d
0x18002e669  mov     rcx, rdi
0x18002e66c  mov     rax, rbx
0x18002e66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e674  mov     esi, eax
0x18002e676  xor     ebx, ebx
0x18002e678  test    eax, eax
0x18002e67a  js      loc_18002E8B0
0x18002e680  mov     [rbp+57h+var_C0], rbx
0x18002e684  mov     rdi, [rsp+130h+var_F0]
0x18002e689  mov     rax, [rdi]
0x18002e68c  mov     rbx, [rax+48h]
0x18002e690  lea     rcx, [rbp+57h+var_C0]
0x18002e694  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e699  lea     rdx, [rbp+57h+var_C0]
0x18002e69d  mov     rcx, rdi
0x18002e6a0  mov     rax, rbx
0x18002e6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6a8  mov     esi, eax
0x18002e6aa  xor     ebx, ebx
0x18002e6ac  test    eax, eax
0x18002e6ae  js      loc_18002E87B
0x18002e6b4  lea     rcx, [rbp+57h+var_98]
0x18002e6b8  call    ??$Make@VCInkDrawingAttributes@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkDrawingAttributes@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkDrawingAttributes,>(void)
0x18002e6bd  mov     r12, [rbp+57h+var_98]
0x18002e6c1  test    r12, r12
0x18002e6c4  jz      loc_18002E85C
0x18002e6ca  mov     rax, [r12]
0x18002e6ce  mov     rdx, [rbp+57h+var_C0]
0x18002e6d2  mov     rcx, r12
0x18002e6d5  mov     rax, [rax+88h]
0x18002e6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6e1  mov     esi, eax
0x18002e6e3  test    eax, eax
0x18002e6e5  js      loc_18002E861
0x18002e6eb  lea     rcx, [rbp+57h+var_A0]
0x18002e6ef  call    ??$Make@VCInkStroke@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkStroke@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkStroke,>(void)
0x18002e6f4  mov     r15, [rbp+57h+var_A0]
0x18002e6f8  test    r15, r15
0x18002e6fb  jz      loc_18002E837
0x18002e701  mov     rax, [r15]
0x18002e704  mov     [rsp+130h+ppv], rbx
0x18002e709  xor     r9d, r9d
0x18002e70c  mov     r8, r12
0x18002e70f  mov     rdx, [rsp+130h+var_F0]
0x18002e714  mov     rcx, r15
0x18002e717  mov     rax, [rax+80h]
0x18002e71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e723  mov     esi, eax
0x18002e725  test    eax, eax
0x18002e727  js      loc_18002E83C
0x18002e72d  mov     dl, r13b
0x18002e730  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StrokeIdAndTimestamp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StrokeIdAndTimestamp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrokeIdAndTimestamp> `wil::Feature<__WilFeatureTraits_Feature_StrokeIdAndTimestamp>::GetImpl(void)'::`2'::impl
0x18002e737  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StrokeIdAndTimestamp@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StrokeIdAndTimestamp>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002e73c  mov     rax, [r15]
0x18002e73f  mov     rdx, [rsp+130h+var_F0]
0x18002e744  mov     rcx, r15
0x18002e747  mov     rax, [rax+0D8h]
0x18002e74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e753  mov     esi, eax
0x18002e755  test    eax, eax
0x18002e757  js      loc_18002E83C
0x18002e75d  mov     dl, r13b
0x18002e760  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InkPointTimestamp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InkPointTimestamp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InkPointTimestamp> `wil::Feature<__WilFeatureTraits_Feature_InkPointTimestamp>::GetImpl(void)'::`2'::impl
0x18002e767  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_InkPointTimestamp@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InkPointTimestamp>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002e76c  mov     rax, [r15]
0x18002e76f  mov     rdx, [rsp+130h+var_F0]
0x18002e774  mov     rcx, r15
0x18002e777  mov     rax, [rax+0E0h]
0x18002e77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e783  mov     esi, eax
0x18002e785  test    eax, eax
0x18002e787  js      loc_18002E83C
0x18002e78d  mov     rax, [r15]
0x18002e790  mov     rcx, r15
0x18002e793  mov     rax, [rax+0B0h]
0x18002e79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e79f  mov     rax, [r14]
0x18002e7a2  or      r8d, 0FFFFFFFFh
0x18002e7a6  mov     rdx, r15
0x18002e7a9  mov     rcx, r14
0x18002e7ac  mov     rax, [rax+130h]
0x18002e7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7b8  mov     esi, eax
0x18002e7ba  test    eax, eax
0x18002e7bc  js      short loc_18002E83C
0x18002e7be  cmp     byte ptr [rbp+57h+arg_0], bl
0x18002e7c1  jnz     short loc_18002E83C
0x18002e7c3  mov     [rsp+130h+var_E4], ebx
0x18002e7c7  mov     [rbp+57h+var_C8], rbx
0x18002e7cb  mov     rax, [r15+10h]
0x18002e7cf  mov     rbx, [rax+40h]
0x18002e7d3  lea     rcx, [rbp+57h+var_C8]
0x18002e7d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e7dc  lea     rdx, [rbp+57h+var_C8]
0x18002e7e0  lea     rcx, [r15+10h]
0x18002e7e4  mov     rax, rbx
0x18002e7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7ec  mov     ebx, eax
0x18002e7ee  test    eax, eax
0x18002e7f0  js      short loc_18002E817
0x18002e7f2  mov     rcx, [rbp+57h+var_C8]
0x18002e7f6  mov     rax, [rcx]
0x18002e7f9  lea     rdx, [rsp+130h+var_E4]
0x18002e7fe  mov     rax, [rax+38h]
0x18002e802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e807  mov     ebx, eax
0x18002e809  test    eax, eax
0x18002e80b  js      short loc_18002E817
0x18002e80d  mov     edi, [rsp+130h+var_100]
0x18002e811  add     edi, [rsp+130h+var_E4]
0x18002e815  jmp     short loc_18002E81F
0x18002e817  mov     byte ptr [rbp+57h+arg_0], r13b
0x18002e81b  mov     edi, [rsp+130h+var_100]
0x18002e81f  lea     rcx, [rbp+57h+var_C8]
0x18002e823  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e828  xor     eax, eax
0x18002e82a  test    ebx, ebx
0x18002e82c  cmovns  eax, edi
0x18002e82f  mov     [rsp+130h+var_100], eax
0x18002e833  xor     ebx, ebx
0x18002e835  jmp     short loc_18002E83C
0x18002e837  mov     esi, 8007000Eh
0x18002e83c  test    r15, r15
0x18002e83f  jz      short loc_18002E855
0x18002e841  mov     [rbp+57h+var_A0], rbx
0x18002e845  mov     rax, [r15]
0x18002e848  mov     rcx, r15
0x18002e84b  mov     rax, [rax+10h]
0x18002e84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e854  nop
0x18002e855  mov     r15d, dword ptr [rsp+130h+var_E0]
0x18002e85a  jmp     short loc_18002E861
0x18002e85c  mov     esi, 8007000Eh
0x18002e861  test    r12, r12
0x18002e864  jz      short loc_18002E87B
0x18002e866  mov     [rbp+57h+var_98], rbx
0x18002e86a  mov     rax, [r12]
0x18002e86e  mov     rcx, r12
0x18002e871  mov     rax, [rax+10h]
0x18002e875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e87a  nop
0x18002e87b  lea     rcx, [rbp+57h+var_C0]
0x18002e87f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e884  test    esi, esi
0x18002e886  js      short loc_18002E8B0
0x18002e888  lea     rcx, [rsp+130h+var_F0]
0x18002e88d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e892  add     r15d, r13d
0x18002e895  mov     dword ptr [rsp+130h+var_E0], r15d
0x18002e89a  cmp     r15d, [rsp+130h+var_E8]
0x18002e89f  jl      loc_18002E646
0x18002e8a5  mov     r15d, [rsp+130h+var_100]
0x18002e8aa  mov     edi, [rsp+130h+var_FC]
0x18002e8ae  jmp     short loc_18002E8BE
0x18002e8b0  lea     rcx, [rsp+130h+var_F0]
0x18002e8b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e8ba  jmp     short loc_18002E8A5
0x18002e8bc  mov     edi, ebx
0x18002e8be  lea     rcx, [rsp+130h+var_D8]
0x18002e8c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002e8c8  mov     r12b, [rbp+57h+arg_18]
0x18002e8cc  mov     rcx, [rbp+57h+psa+8]; psa
0x18002e8d0  call    cs:__imp_SafeArrayDestroy
0x18002e8d6  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x18002e8da  call    cs:__imp_QueryPerformanceCounter
0x18002e8e0  test    r13b, r13b
  ... truncated ...
```
