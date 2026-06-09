# CAPOWrapperSrv::GetPreferredOutputFormat(tWAVEFORMATEX *,tWAVEFORMATEX * *)

- ea: `0x1400669b0`
- end: `0x140066bcd`
- name: `?GetPreferredOutputFormat@CAPOWrapperSrv@@UEAAJPEAUtWAVEFORMATEX@@PEAPEAU2@@Z`
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
- `0x1400669b0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140066b76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140066b8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140066b76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140066b8b`

## pseudocode

```c
__int64 __fastcall CAPOWrapperSrv::GetPreferredOutputFormat(CAPOWrapperSrv *this, struct tWAVEFORMATEX *a2, LPVOID *a3)
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
    "SrvSystemEffect_GetPreferredOutputFormat",
    (const char *const)this + 140);
  if ( a3 )
  {
    *a3 = 0;
    if ( !a2 )
    {
      v7 = 578;
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
        (void *)0x249,
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
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, *(_QWORD *)v16, &v17);
        v8 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x251,
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
            (void *)0x258,
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
            (void *)0x25B,
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
  v7 = 575;
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
0x1400669b0  push    rbp
0x1400669b2  push    rbx
0x1400669b3  push    rsi
0x1400669b4  push    rdi
0x1400669b5  push    r14
0x1400669b7  lea     rbp, [rsp-40h]
0x1400669bc  sub     rsp, 140h
0x1400669c3  mov     rax, cs:__security_cookie
0x1400669ca  xor     rax, rsp
0x1400669cd  mov     [rbp+60h+var_30], rax
0x1400669d1  mov     rsi, r8
0x1400669d4  mov     rdi, rdx
0x1400669d7  mov     r14, rcx
0x1400669da  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x1400669df  mov     rdx, rax; struct _tlgProvider_t *
0x1400669e2  lea     r9, [r14+8Ch]; char *
0x1400669e9  lea     r8, aSrvsystemeffec_8; "SrvSystemEffect_GetPreferredOutputForma"...
0x1400669f0  lea     rcx, [rsp+160h+PerformanceCount]; lpPerformanceCount
0x1400669f5  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x1400669fa  test    rsi, rsi
0x1400669fd  jnz     short loc_140066A06
0x1400669ff  mov     edx, 23Fh
0x140066a04  jmp     short loc_140066A17
0x140066a06  mov     qword ptr [rsi], 0
0x140066a0d  test    rdi, rdi
0x140066a10  jnz     short loc_140066A34
0x140066a12  mov     edx, 242h; void *
0x140066a17  mov     rcx, [rbp+68h]; this
0x140066a1b  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140066a22  mov     ebx, 80070057h
0x140066a27  mov     r9d, ebx; char *
0x140066a2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066a2f  jmp     loc_140066BA7
0x140066a34  movzx   edx, word ptr [rdi+10h]
0x140066a38  lea     r8, [rsp+160h+var_140]
0x140066a3d  add     edx, 12h
0x140066a40  mov     qword ptr [rsp+160h+var_140], 0; int
0x140066a49  mov     rcx, rdi
0x140066a4c  call    CreateAudioMediaType_Unsafe
0x140066a51  mov     ebx, eax
0x140066a53  test    eax, eax
0x140066a55  jns     short loc_140066A7E
0x140066a57  mov     rcx, [rbp+68h]; this
0x140066a5b  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140066a62  mov     r9d, eax; char *
0x140066a65  mov     edx, 249h; void *
0x140066a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066a6f  lea     rcx, [rsp+160h+var_140]
0x140066a74  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066a79  jmp     loc_140066BA7
0x140066a7e  mov     rdx, [r14+60h]
0x140066a82  mov     [rsp+160h+var_138], 0
0x140066a8b  test    rdx, rdx
0x140066a8e  jz      loc_140066B91
0x140066a94  lea     rcx, [rsp+160h+var_130]
0x140066a99  call    ??0?$CComQIPtr@UIAudioProcessingObjectPreferredFormatSupport@@$1?_GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IAudioProcessingObjectPreferredFormatSupport,&__s_GUID const _GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3>::CComQIPtr<IAudioProcessingObjectPreferredFormatSupport,&__s_GUID const _GUID_51cbd3c4_f1f3_4d2f_a0e1_7e9c4dd0feb3>(IUnknown *)
0x140066a9e  mov     rcx, [rsp+160h+var_130]
0x140066aa3  test    rcx, rcx
0x140066aa6  jz      short loc_140066AF5
0x140066aa8  mov     rax, [rcx]
0x140066aab  lea     r8, [rsp+160h+var_138]
0x140066ab0  mov     rdx, qword ptr [rsp+160h+var_140]
0x140066ab5  mov     rax, [rax+20h]
0x140066ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066abe  mov     ebx, eax
0x140066ac0  test    eax, eax
0x140066ac2  jns     short loc_140066AF5
0x140066ac4  mov     rcx, [rbp+68h]; this
0x140066ac8  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140066acf  mov     r9d, eax; char *
0x140066ad2  mov     edx, 251h; void *
0x140066ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066adc  lea     rcx, [rsp+160h+var_130]
0x140066ae1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066ae6  lea     rcx, [rsp+160h+var_138]
0x140066aeb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066af0  jmp     loc_140066A6F
0x140066af5  lea     rcx, [rsp+160h+var_130]
0x140066afa  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066aff  mov     rcx, [rsp+160h+var_138]
0x140066b04  test    rcx, rcx
0x140066b07  jz      loc_140066B91
0x140066b0d  mov     rax, [rcx]
0x140066b10  mov     rax, [rax+28h]
0x140066b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066b19  test    rax, rax
0x140066b1c  jnz     short loc_140066B3D
0x140066b1e  mov     rcx, [rbp+68h]; this
0x140066b22  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140066b29  mov     ebx, 88890008h
0x140066b2e  mov     edx, 258h; void *
0x140066b33  mov     r9d, ebx; char *
0x140066b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066b3b  jmp     short loc_140066AE6
0x140066b3d  lea     rdx, [rsp+160h+pv]; struct tWAVEFORMATEX **
0x140066b42  mov     [rsp+160h+pv], 0
0x140066b4b  mov     rcx, rax; Src
0x140066b4e  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x140066b53  mov     ebx, eax
0x140066b55  test    eax, eax
0x140066b57  jns     short loc_140066B81
0x140066b59  mov     rcx, [rbp+68h]; this
0x140066b5d  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140066b64  mov     r9d, eax; char *
0x140066b67  mov     edx, 25Bh; void *
0x140066b6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140066b71  mov     rcx, [rsp+160h+pv]; pv
0x140066b76  call    cs:__imp_CoTaskMemFree
0x140066b7c  jmp     loc_140066AE6
0x140066b81  mov     rax, [rsp+160h+pv]
0x140066b86  xor     ecx, ecx; pv
0x140066b88  mov     [rsi], rax
0x140066b8b  call    cs:__imp_CoTaskMemFree
0x140066b91  lea     rcx, [rsp+160h+var_138]
0x140066b96  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066b9b  lea     rcx, [rsp+160h+var_140]
0x140066ba0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066ba5  xor     ebx, ebx
0x140066ba7  lea     rcx, [rsp+160h+PerformanceCount]; this
0x140066bac  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x140066bb1  mov     eax, ebx
0x140066bb3  mov     rcx, [rbp+60h+var_30]
0x140066bb7  xor     rcx, rsp; StackCookie
0x140066bba  call    __security_check_cookie
0x140066bbf  add     rsp, 140h
0x140066bc6  pop     r14
0x140066bc8  pop     rdi
0x140066bc9  pop     rsi
0x140066bca  pop     rbx
0x140066bcb  pop     rbp
0x140066bcc  retn
```
