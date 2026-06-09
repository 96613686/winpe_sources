# CAPOWrapperSrv::GetPreferredInputFormat(tWAVEFORMATEX *,tWAVEFORMATEX * *)

- ea: `0x140066780`
- end: `0x14006699d`
- name: `?GetPreferredInputFormat@CAPOWrapperSrv@@UEAAJPEAUtWAVEFORMATEX@@PEAPEAU2@@Z`
- size: `541`
- prototype: `__int64 __fastcall(CAPOWrapperSrv *__hidden this, struct tWAVEFORMATEX *, struct tWAVEFORMATEX **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x14000c360`
- `0x14000e11c`
- `0x14000e280`
- `0x14000e404`
- `0x140035fcc`
- `0x14005d0e0`
- `0x14005f0b8`
- `0x140066780`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140066946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006695b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140066946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14006695b`

## pseudocode

```c
__int64 __fastcall CAPOWrapperSrv::GetPreferredInputFormat(CAPOWrapperSrv *this, struct tWAVEFORMATEX *a2, LPVOID *a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int AudioMediaType_Unsafe; // eax
  __int64 v11; // rdx
  int v12; // eax
  const struct tWAVEFORMATEX *v13; // rax
  int v14; // eax
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v6 = AudioDgTelemetryProvider::Provider();
  CPerfTracker::CPerfTracker(
    &PerformanceCount,
    v6,
    "SrvSystemEffect_GetPreferredInputFormat",
    (const char *const)this + 140);
  if ( a3 )
  {
    *a3 = 0;
    if ( !a2 )
    {
      v7 = 539;
      goto LABEL_5;
    }
    v9 = (unsigned int)a2->cbSize + 18;
    *(_QWORD *)v16 = 0;
    AudioMediaType_Unsafe = CreateAudioMediaType_Unsafe(a2, v9, v16);
    v8 = AudioMediaType_Unsafe;
    if ( AudioMediaType_Unsafe < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x222,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
        (const char *)(unsigned int)AudioMediaType_Unsafe,
        v16[0]);
LABEL_8:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
      goto LABEL_21;
    }
    v11 = *((_QWORD *)this + 12);
    v17 = 0;
    if ( v11 )
    {
      ATL::CComQIPtr<IAudioProcessingObjectPreferredFormatSupport,&__s_GUID const _GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3>::CComQIPtr<IAudioProcessingObjectPreferredFormatSupport,&__s_GUID const _GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3>(&v18);
      if ( v18 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, *(_QWORD *)v16, &v17);
        v8 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22A,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
            (const char *)(unsigned int)v12,
            v16[0]);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
LABEL_13:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
          goto LABEL_8;
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
      if ( v17 )
      {
        v13 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
        if ( !v13 )
        {
          v8 = -2004287480;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x231,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
            (const char *)0x88890008LL,
            v16[0]);
          goto LABEL_13;
        }
        pv = 0;
        v14 = CloneWaveFormat(v13, (struct tWAVEFORMATEX **)&pv);
        v8 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x234,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
            (const char *)(unsigned int)v14,
            v16[0]);
          CoTaskMemFree(pv);
          goto LABEL_13;
        }
        *a3 = pv;
        CoTaskMemFree(0);
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v16);
    v8 = 0;
    goto LABEL_21;
  }
  v7 = 536;
LABEL_5:
  v8 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
    (const char *)0x80070057LL,
    v16[0]);
LABEL_21:
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  return v8;
}

```

## disassembly

```asm
0x140066780  push    rbp
0x140066782  push    rbx
0x140066783  push    rsi
0x140066784  push    rdi
0x140066785  push    r14
0x140066787  lea     rbp, [rsp-40h]
0x14006678c  sub     rsp, 140h
0x140066793  mov     rax, cs:__security_cookie
0x14006679a  xor     rax, rsp
0x14006679d  mov     [rbp+60h+var_30], rax
0x1400667a1  mov     rsi, r8
0x1400667a4  mov     rdi, rdx
0x1400667a7  mov     r14, rcx
0x1400667aa  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x1400667af  mov     rdx, rax; struct _tlgProvider_t *
0x1400667b2  lea     r9, [r14+8Ch]; char *
0x1400667b9  lea     r8, aSrvsystemeffec_1; "SrvSystemEffect_GetPreferredInputFormat"
0x1400667c0  lea     rcx, [rsp+160h+PerformanceCount]; lpPerformanceCount
0x1400667c5  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x1400667ca  test    rsi, rsi
0x1400667cd  jnz     short loc_1400667D6
0x1400667cf  mov     edx, 218h
0x1400667d4  jmp     short loc_1400667E7
0x1400667d6  mov     qword ptr [rsi], 0
0x1400667dd  test    rdi, rdi
0x1400667e0  jnz     short loc_140066804
0x1400667e2  mov     edx, 21Bh; void *
0x1400667e7  mov     rcx, [rbp+68h]; this
0x1400667eb  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400667f2  mov     ebx, 80070057h
0x1400667f7  mov     r9d, ebx; char *
0x1400667fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400667ff  jmp     loc_140066977
0x140066804  movzx   edx, word ptr [rdi+10h]
0x140066808  lea     r8, [rsp+160h+var_140]
0x14006680d  add     edx, 12h
0x140066810  mov     qword ptr [rsp+160h+var_140], 0; int
0x140066819  mov     rcx, rdi
0x14006681c  call    CreateAudioMediaType_Unsafe
0x140066821  mov     ebx, eax
0x140066823  test    eax, eax
0x140066825  jns     short loc_14006684E
0x140066827  mov     rcx, [rbp+68h]; this
0x14006682b  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140066832  mov     r9d, eax; char *
0x140066835  mov     edx, 222h; void *
0x14006683a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006683f  lea     rcx, [rsp+160h+var_140]
0x140066844  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066849  jmp     loc_140066977
0x14006684e  mov     rdx, [r14+60h]
0x140066852  mov     [rsp+160h+var_138], 0
0x14006685b  test    rdx, rdx
0x14006685e  jz      loc_140066961
0x140066864  lea     rcx, [rsp+160h+var_130]
0x140066869  call    ??0?$CComQIPtr@UIAudioProcessingObjectPreferredFormatSupport@@$1?_GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IAudioProcessingObjectPreferredFormatSupport,&__s_GUID const _GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3>::CComQIPtr<IAudioProcessingObjectPreferredFormatSupport,&__s_GUID const _GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3>(IUnknown *)
0x14006686e  mov     rcx, [rsp+160h+var_130]
0x140066873  test    rcx, rcx
0x140066876  jz      short loc_1400668C5
0x140066878  mov     rax, [rcx]
0x14006687b  lea     r8, [rsp+160h+var_138]
0x140066880  mov     rdx, qword ptr [rsp+160h+var_140]
0x140066885  mov     rax, [rax+18h]
0x140066889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006688e  mov     ebx, eax
0x140066890  test    eax, eax
0x140066892  jns     short loc_1400668C5
0x140066894  mov     rcx, [rbp+68h]; this
0x140066898  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14006689f  mov     r9d, eax; char *
0x1400668a2  mov     edx, 22Ah; void *
0x1400668a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400668ac  lea     rcx, [rsp+160h+var_130]
0x1400668b1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400668b6  lea     rcx, [rsp+160h+var_138]
0x1400668bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400668c0  jmp     loc_14006683F
0x1400668c5  lea     rcx, [rsp+160h+var_130]
0x1400668ca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400668cf  mov     rcx, [rsp+160h+var_138]
0x1400668d4  test    rcx, rcx
0x1400668d7  jz      loc_140066961
0x1400668dd  mov     rax, [rcx]
0x1400668e0  mov     rax, [rax+28h]
0x1400668e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400668e9  test    rax, rax
0x1400668ec  jnz     short loc_14006690D
0x1400668ee  mov     rcx, [rbp+68h]; this
0x1400668f2  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400668f9  mov     ebx, 88890008h
0x1400668fe  mov     edx, 231h; void *
0x140066903  mov     r9d, ebx; char *
0x140066906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006690b  jmp     short loc_1400668B6
0x14006690d  lea     rdx, [rsp+160h+pv]; struct tWAVEFORMATEX **
0x140066912  mov     [rsp+160h+pv], 0
0x14006691b  mov     rcx, rax; Src
0x14006691e  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x140066923  mov     ebx, eax
0x140066925  test    eax, eax
0x140066927  jns     short loc_140066951
0x140066929  mov     rcx, [rbp+68h]; this
0x14006692d  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140066934  mov     r9d, eax; char *
0x140066937  mov     edx, 234h; void *
0x14006693c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066941  mov     rcx, [rsp+160h+pv]; pv
0x140066946  call    cs:__imp_CoTaskMemFree
0x14006694c  jmp     loc_1400668B6
0x140066951  mov     rax, [rsp+160h+pv]
0x140066956  xor     ecx, ecx; pv
0x140066958  mov     [rsi], rax
0x14006695b  call    cs:__imp_CoTaskMemFree
0x140066961  lea     rcx, [rsp+160h+var_138]
0x140066966  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006696b  lea     rcx, [rsp+160h+var_140]
0x140066970  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066975  xor     ebx, ebx
0x140066977  lea     rcx, [rsp+160h+PerformanceCount]; this
0x14006697c  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x140066981  mov     eax, ebx
0x140066983  mov     rcx, [rbp+60h+var_30]
0x140066987  xor     rcx, rsp; StackCookie
0x14006698a  call    __security_check_cookie
0x14006698f  add     rsp, 140h
0x140066996  pop     r14
0x140066998  pop     rdi
0x140066999  pop     rsi
0x14006699a  pop     rbx
0x14006699b  pop     rbp
0x14006699c  retn
```
