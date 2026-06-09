# CGuestAudioEndpointVolume::RuntimeClassInitialize(ushort const *)

- ea: `0x18007f86c`
- end: `0x18007fb38`
- name: `?RuntimeClassInitialize@CGuestAudioEndpointVolume@@QEAAJPEBG@Z`
- size: `716`
- prototype: `__int64 __fastcall(CGuestAudioEndpointVolume *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009dc48`

## callees

- `0x18000cd10`
- `0x18000d11c`
- `0x180010a90`
- `0x180025a04`
- `0x18004d8a8`
- `0x18007f86c`
- `0x18008323c`
- `0x180087e80`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095ed0`
- `0x1800994e8`
- `0x1800af1c8`
- `0x1800b0470`
- `0x1800b2bb4`
- `0x1800b2d9c`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fb09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fa21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fb09`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18007f8a6`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18007f8a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGuestAudioEndpointVolume::RuntimeClassInitialize(
        CGuestAudioEndpointVolume *this,
        const unsigned __int16 *a2)
{
  int v4; // edi
  __int64 v5; // rdx
  struct CGuestXvmAudioObject *RootProxyAudioObjectActivator; // rdi
  unsigned int v8; // ebx
  void *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // eax
  void *v13; // rcx
  bool v14; // zf
  int v15; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  struct XvmEndpointId *v18; // [rsp+40h] [rbp-C0h] BYREF
  CGuestAudioEndpointVolume *v19; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  char v22; // [rsp+60h] [rbp-A0h]
  _BYTE v23[1560]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[1568]; // [rsp+680h] [rbp+580h] BYREF
  int Src; // [rsp+CA0h] [rbp+BA0h] BYREF
  __int64 v26; // [rsp+CA4h] [rbp+BA4h]
  int v27; // [rsp+CACh] [rbp+BACh]
  int v28; // [rsp+CB0h] [rbp+BB0h]
  _BYTE v29[1548]; // [rsp+CB4h] [rbp+BB4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+12E8h] [rbp+11E8h]

  *((_DWORD *)this + 38) = SHTaskPoolGetUniqueContext();
  Src = 18;
  v26 = 1;
  v27 = 0;
  v28 = 78;
  memset_0(v29, 0, 0x600u);
  v18 = 0;
  v4 = XvmActivateProxyAudioObject::CastTo<XvmActivateAudioEndpointVolume>(&Src, &v18);
  if ( v4 < 0 )
  {
    v5 = 23;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
      (const char *)(unsigned int)v4,
      v15);
    return (unsigned int)v4;
  }
  v4 = CopyToXvmEndpointId(a2, v18);
  if ( v4 < 0 )
  {
    v5 = 25;
    goto LABEL_3;
  }
  RootProxyAudioObjectActivator = GetRootProxyAudioObjectActivator();
  if ( RootProxyAudioObjectActivator )
  {
    pv = 0;
    v18 = 0;
    p_pv = &pv;
    v21 = 0;
    v22 = 1;
    memcpy_0(v23, &Src, 0x614u);
    memcpy_0(v24, v23, 0x614u);
    v4 = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(
           RootProxyAudioObjectActivator,
           *((unsigned int *)RootProxyAudioObjectActivator + 12),
           v24,
           &v21);
    wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v4 >= 0 )
    {
      v17 = 0;
      v19 = (CGuestAudioEndpointVolume *)&v17;
      v10 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v19);
      v4 = Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(this, v10);
      if ( v4 >= 0 )
      {
        v4 = CGuestXvmAudioObject::Initialize(
               (CGuestAudioEndpointVolume *)((char *)this + 24),
               *((_DWORD *)v18 + 3),
               (struct Microsoft::WRL::WeakRef *)&v17,
               (struct XvmActivateProxyAudioObject *)&Src);
        if ( v4 >= 0 )
        {
          v19 = this;
          wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset((char *)this + 56);
          v12 = Microsoft::WRL::Details::MakeAndInitialize<CGuestAudioEndpointVolume::MediaNotificationDelegator,IMediaNotificationCallback,CGuestAudioEndpointVolume *>(
                  (char *)this + 56,
                  &v19);
          v8 = v12;
          if ( v12 >= 0 )
            v8 = *((_DWORD *)pv + 1);
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x26,
              (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
              (const char *)(unsigned int)v12,
              (int)&v18);
          Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
          v13 = pv;
          v14 = pv == 0;
          pv = 0;
          if ( !v14 )
            CoTaskMemFree(v13);
          return v8;
        }
        v11 = 37;
      }
      else
      {
        v11 = 35;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
        (const char *)(unsigned int)v4,
        (int)&v18);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
        (const char *)(unsigned int)v4,
        (int)&v18);
    }
    v9 = pv;
    pv = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    return (unsigned int)v4;
  }
  v8 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C,
    (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
    (const char *)0x8000FFFFLL,
    v15);
  return v8;
}

```

## disassembly

```asm
0x18007f86c  mov     [rsp-8+arg_10], rbx
0x18007f871  mov     [rsp-8+arg_18], rsi
0x18007f876  push    rbp
0x18007f877  push    rdi
0x18007f878  push    r14
0x18007f87a  lea     rbp, [rsp-11D0h]
0x18007f882  mov     eax, 12D0h
0x18007f887  call    _alloca_probe
0x18007f88c  sub     rsp, rax
0x18007f88f  mov     rax, cs:__security_cookie
0x18007f896  xor     rax, rsp
0x18007f899  mov     [rbp+11E0h+var_20], rax
0x18007f8a0  mov     rsi, rdx
0x18007f8a3  mov     rbx, rcx
0x18007f8a6  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18007f8ac  mov     [rbx+98h], eax
0x18007f8b2  mov     [rbp+11E0h+Src], 12h
0x18007f8bc  mov     [rbp+11E0h+var_63C], 1
0x18007f8c7  xor     r14d, r14d
0x18007f8ca  mov     [rbp+11E0h+var_634], r14d
0x18007f8d1  mov     [rbp+11E0h+var_630], 4Eh ; 'N'
0x18007f8db  xor     edx, edx; Val
0x18007f8dd  mov     r8d, 600h; Size
0x18007f8e3  lea     rcx, [rbp+11E0h+var_62C]; void *
0x18007f8ea  call    memset_0
0x18007f8ef  mov     [rsp+12E0h+var_12A0], r14
0x18007f8f4  lea     rdx, [rsp+12E0h+var_12A0]
0x18007f8f9  lea     rcx, [rbp+11E0h+Src]
0x18007f900  call    ??$CastTo@UXvmActivateAudioEndpointVolume@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateAudioEndpointVolume@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateAudioEndpointVolume>(XvmActivateAudioEndpointVolume * *)
0x18007f905  mov     edi, eax
0x18007f907  test    eax, eax
0x18007f909  jns     short loc_18007F92C
0x18007f90b  lea     edx, [r14+17h]; void *
0x18007f90f  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x18007f916  mov     r9d, edi; char *
0x18007f919  mov     rcx, [rbp+11E8h]; this
0x18007f920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f925  mov     eax, edi
0x18007f927  jmp     loc_18007FB11
0x18007f92c  mov     rdx, [rsp+12E0h+var_12A0]; struct XvmEndpointId *
0x18007f931  mov     rcx, rsi; unsigned __int16 *
0x18007f934  call    ?CopyToXvmEndpointId@@YAJPEBGPEAUXvmEndpointId@@@Z; CopyToXvmEndpointId(ushort const *,XvmEndpointId *)
0x18007f939  mov     edi, eax
0x18007f93b  test    eax, eax
0x18007f93d  jns     short loc_18007F946
0x18007f93f  mov     edx, 19h
0x18007f944  jmp     short loc_18007F90F
0x18007f946  call    ?GetRootProxyAudioObjectActivator@@YAPEAVCGuestXvmAudioObject@@XZ; GetRootProxyAudioObjectActivator(void)
0x18007f94b  mov     rdi, rax
0x18007f94e  test    rax, rax
0x18007f951  jnz     short loc_18007F976
0x18007f953  mov     rcx, [rbp+11E8h]; this
0x18007f95a  mov     ebx, 8000FFFFh
0x18007f95f  mov     r9d, ebx; char *
0x18007f962  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x18007f969  lea     edx, [rax+1Ch]; void *
0x18007f96c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f971  jmp     loc_18007FB0F
0x18007f976  mov     [rsp+12E0h+pv], r14
0x18007f97b  mov     [rsp+12E0h+var_12A0], r14
0x18007f980  lea     rax, [rsp+12E0h+pv]
0x18007f985  mov     [rsp+12E0h+var_1290], rax
0x18007f98a  mov     [rsp+12E0h+var_1288], r14
0x18007f98f  mov     [rsp+12E0h+var_1280], 1
0x18007f994  lea     rcx, [rsp+12E0h+var_1278]; void *
0x18007f999  lea     rdx, [rbp+11E0h+Src]; Src
0x18007f9a0  mov     esi, 614h
0x18007f9a5  mov     r8d, esi; Size
0x18007f9a8  call    memcpy_0
0x18007f9ad  lea     rcx, [rbp+11E0h+var_C60]; void *
0x18007f9b4  lea     rdx, [rsp+12E0h+var_1278]; Src
0x18007f9b9  mov     r8d, esi; Size
0x18007f9bc  call    memcpy_0
0x18007f9c1  lea     rax, [rsp+12E0h+var_12A0]
0x18007f9c6  mov     qword ptr [rsp+12E0h+var_12C0], rax; int
0x18007f9cb  lea     r9, [rsp+12E0h+var_1288]
0x18007f9d0  lea     r8, [rbp+11E0h+var_C60]
0x18007f9d7  mov     edx, [rdi+30h]
0x18007f9da  mov     rcx, rdi
0x18007f9dd  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x18007f9e2  mov     edi, eax
0x18007f9e4  lea     rcx, [rsp+12E0h+var_1290]
0x18007f9e9  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007f9ee  test    edi, edi
0x18007f9f0  jns     short loc_18007FA2C
0x18007f9f2  mov     rcx, [rbp+11E8h]; this
0x18007f9f9  mov     r9d, edi; char *
0x18007f9fc  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x18007fa03  mov     edx, 20h ; ' '; void *
0x18007fa08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fa0d  nop
0x18007fa0e  mov     rcx, [rsp+12E0h+pv]; pv
0x18007fa13  mov     [rsp+12E0h+pv], r14
0x18007fa18  test    rcx, rcx
0x18007fa1b  jz      loc_18007F925
0x18007fa21  call    cs:__imp_CoTaskMemFree
0x18007fa27  jmp     loc_18007F925
0x18007fa2c  mov     [rsp+12E0h+var_12A8], r14
0x18007fa31  lea     rax, [rsp+12E0h+var_12A8]
0x18007fa36  mov     [rsp+12E0h+var_1298], rax
0x18007fa3b  lea     rcx, [rsp+12E0h+var_1298]
0x18007fa40  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007fa45  mov     rdx, rax
0x18007fa48  mov     rcx, rbx
0x18007fa4b  call    ??$AsWeak@VCGuestSpatialAudioClient@@@WRL@Microsoft@@YAJPEAVCGuestSpatialAudioClient@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(CGuestSpatialAudioClient *,Microsoft::WRL::WeakRef *)
0x18007fa50  mov     edi, eax
0x18007fa52  test    eax, eax
0x18007fa54  jns     short loc_18007FA7E
0x18007fa56  mov     edx, 23h ; '#'; void *
0x18007fa5b  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x18007fa62  mov     r9d, edi; char *
0x18007fa65  mov     rcx, [rbp+11E8h]; this
0x18007fa6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fa71  nop
0x18007fa72  lea     rcx, [rsp+12E0h+var_12A8]
0x18007fa77  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007fa7c  jmp     short loc_18007FA0E
0x18007fa7e  lea     rcx, [rbx+18h]; this
0x18007fa82  lea     r9, [rbp+11E0h+Src]; struct XvmActivateProxyAudioObject *
0x18007fa89  lea     r8, [rsp+12E0h+var_12A8]; struct Microsoft::WRL::WeakRef *
0x18007fa8e  mov     rdx, [rsp+12E0h+var_12A0]
0x18007fa93  mov     edx, [rdx+0Ch]; unsigned int
0x18007fa96  call    ?Initialize@CGuestXvmAudioObject@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUXvmActivateProxyAudioObject@@@Z; CGuestXvmAudioObject::Initialize(uint,Microsoft::WRL::WeakRef &,XvmActivateProxyAudioObject *)
0x18007fa9b  mov     edi, eax
0x18007fa9d  test    eax, eax
0x18007fa9f  jns     short loc_18007FAA8
0x18007faa1  mov     edx, 25h ; '%'
0x18007faa6  jmp     short loc_18007FA5B
0x18007faa8  mov     [rsp+12E0h+var_1298], rbx
0x18007faad  lea     rcx, [rbx+38h]
0x18007fab1  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x18007fab6  lea     rdx, [rsp+12E0h+var_1298]
0x18007fabb  lea     rcx, [rbx+38h]
0x18007fabf  call    ??$MakeAndInitialize@VMediaNotificationDelegator@CGuestAudioEndpointVolume@@UIMediaNotificationCallback@@PEAV2@@Details@WRL@Microsoft@@YAJPEAPEAUIMediaNotificationCallback@@$$QEAPEAVCGuestAudioEndpointVolume@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CGuestAudioEndpointVolume::MediaNotificationDelegator,IMediaNotificationCallback,CGuestAudioEndpointVolume *>(IMediaNotificationCallback * *,CGuestAudioEndpointVolume * &&)
0x18007fac4  mov     ebx, eax
0x18007fac6  test    eax, eax
0x18007fac8  jns     short loc_18007FAE7
0x18007faca  mov     rcx, [rbp+11E8h]; this
0x18007fad1  mov     r9d, eax; char *
0x18007fad4  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x18007fadb  mov     edx, 26h ; '&'; void *
0x18007fae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fae5  jmp     short loc_18007FAEF
0x18007fae7  mov     rax, [rsp+12E0h+pv]
0x18007faec  mov     ebx, [rax+4]
0x18007faef  lea     rcx, [rsp+12E0h+var_12A8]
0x18007faf4  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007faf9  nop
0x18007fafa  mov     rcx, [rsp+12E0h+pv]; pv
0x18007faff  test    rcx, rcx
0x18007fb02  mov     [rsp+12E0h+pv], r14
0x18007fb07  jz      short loc_18007FB0F
0x18007fb09  call    cs:__imp_CoTaskMemFree
0x18007fb0f  mov     eax, ebx
0x18007fb11  mov     rcx, [rbp+11E0h+var_20]
0x18007fb18  xor     rcx, rsp; StackCookie
0x18007fb1b  call    __security_check_cookie
0x18007fb20  lea     r11, [rsp+12E0h+var_10]
0x18007fb28  mov     rbx, [r11+30h]
0x18007fb2c  mov     rsi, [r11+38h]
0x18007fb30  mov     rsp, r11
0x18007fb33  pop     r14
0x18007fb35  pop     rdi
0x18007fb36  pop     rbp
0x18007fb37  retn
```
