# Windows::Media::Internal::MediaManager::Initialize(void)

- ea: `0x18007e38c`
- end: `0x18007e837`
- name: `?Initialize@MediaManager@Internal@Media@Windows@@AEAAJXZ`
- size: `1195`
- prototype: `__int64 __fastcall(Windows::Media::Internal::MediaManager *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f56a4`

## callees

- `0x18000d11c`
- `0x180010a90`
- `0x180025a04`
- `0x18002be64`
- `0x18002c3dc`
- `0x18004aab0`
- `0x18004d8a8`
- `0x18007e38c`
- `0x18007e840`
- `0x18008323c`
- `0x180087e80`
- `0x180087ed0`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800960a4`
- `0x1800994e8`
- `0x1800b0470`
- `0x1800b2bb4`
- `0x1800f61f0`
- `0x18011ddd0`
- `0x180123010`

## import_xrefs

- `MMDevAPI!__imp_RegisterForMediaCallback` at `0x18007e6ba`
- `MMDevAPI!__imp_RegisterForMediaCallback` at `0x18007e6ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e5cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e63d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e6a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e5cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e63d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007e6a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Media::Internal::MediaManager::Initialize(CAudioSrvMonitor **this)
{
  bool v2; // al
  int v3; // eax
  unsigned int v4; // edi
  struct CGuestXvmAudioObject *RootProxyAudioObjectActivator; // rdi
  void *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  void *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  CAudioSrvMonitor *v13; // rdi
  void *v14; // rcx
  int v15; // eax
  __int64 *v16; // rax
  CAudioSrvMonitor *v17; // rdx
  CAudioSrvMonitor *v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  char v28; // [rsp+60h] [rbp-A0h]
  Windows::Media::Internal::MediaManager *v29; // [rsp+68h] [rbp-98h]
  char v30; // [rsp+70h] [rbp-90h]
  _BYTE v31[1560]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v32[1568]; // [rsp+690h] [rbp+590h] BYREF
  int Src; // [rsp+CB0h] [rbp+BB0h] BYREF
  __int64 v34; // [rsp+CB4h] [rbp+BB4h]
  int v35; // [rsp+CBCh] [rbp+BBCh]
  int v36; // [rsp+CC0h] [rbp+BC0h]
  char v37[1548]; // [rsp+CC4h] [rbp+BC4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+12E8h] [rbp+11E8h]

  v29 = (Windows::Media::Internal::MediaManager *)this;
  v30 = 1;
  v2 = IsRunningInVM();
  *((_BYTE *)this + 208) = v2;
  if ( v2 )
  {
    Src = 19;
    v34 = 1;
    v35 = 0;
    v36 = 97;
    memset_0(v37, 0, 0x600u);
    v3 = XvmActivateProxyAudioObject::CastTo<XvmActivateMediaManager>(&Src, &v24);
    v4 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)(unsigned int)v3,
        v21);
      Windows::Media::Internal::MediaManager::Uninitialize((Windows::Media::Internal::MediaManager *)this);
      return v4;
    }
    RootProxyAudioObjectActivator = GetRootProxyAudioObjectActivator();
    if ( !RootProxyAudioObjectActivator )
    {
      v4 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)0x8000FFFFLL,
        v21);
      Windows::Media::Internal::MediaManager::Uninitialize((Windows::Media::Internal::MediaManager *)this);
      return v4;
    }
    pv = 0;
    *(_QWORD *)v25 = 0;
    p_pv = &pv;
    v27 = 0;
    v28 = 1;
    memcpy_0(v31, &Src, 0x614u);
    memcpy_0(v32, v31, 0x614u);
    v4 = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(
           RootProxyAudioObjectActivator,
           *((unsigned int *)RootProxyAudioObjectActivator + 12),
           v32,
           &v27);
    wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( (v4 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)v4,
        (int)v25);
      v7 = pv;
      pv = 0;
      if ( v7 )
        CoTaskMemFree(v7);
LABEL_18:
      Windows::Media::Internal::MediaManager::Uninitialize((Windows::Media::Internal::MediaManager *)this);
      return v4;
    }
    v23 = 0;
    v24 = &v23;
    v8 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v24);
    v9 = Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(this, v8);
    v4 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)(unsigned int)v9,
        (int)v25);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v23);
      v10 = pv;
      pv = 0;
      if ( v10 )
        CoTaskMemFree(v10);
      goto LABEL_18;
    }
    v11 = CGuestXvmAudioObject::Initialize(
            (CGuestXvmAudioObject *)(this + 2),
            *(_DWORD *)(*(_QWORD *)v25 + 12LL),
            (struct Microsoft::WRL::WeakRef *)&v23,
            (struct XvmActivateProxyAudioObject *)&Src);
    v4 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)(unsigned int)v11,
        (int)v25);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v23);
      v12 = pv;
      pv = 0;
      if ( v12 )
        CoTaskMemFree(v12);
      goto LABEL_18;
    }
    v13 = this[6];
    this[6] = (CAudioSrvMonitor *)(this + 15);
    if ( this != (CAudioSrvMonitor **)-120LL )
      (*((void (__fastcall **)(char *))this[15] + 1))((char *)this + 120);
    if ( v13 )
      (*(void (__fastcall **)(CAudioSrvMonitor *))(*(_QWORD *)v13 + 16LL))(v13);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v23);
    v14 = pv;
    pv = 0;
    if ( v14 )
      CoTaskMemFree(v14);
  }
  else
  {
    v15 = RegisterForMediaCallback(0x10000, this + 15);
    v4 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)(unsigned int)v15,
        v21);
      Windows::Media::Internal::MediaManager::Uninitialize((Windows::Media::Internal::MediaManager *)this);
      return v4;
    }
    *((_BYTE *)this + 161) = 1;
    v16 = (__int64 *)operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v16;
    if ( v16 )
    {
      *v16 = (__int64)&CAudioSrvMonitor::`vftable';
      v16[1] = (__int64)(this + 18);
      *((_DWORD *)v16 + 4) = 1;
      *((_DWORD *)v16 + 5) = 1;
      v16[3] = 0;
    }
    v17 = this[24];
    this[24] = (CAudioSrvMonitor *)v16;
    if ( v17 )
      std::default_delete<CAudioSrvMonitor>::operator()();
    v18 = this[24];
    if ( !v18 )
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)0x8007000ELL,
        v21);
      Windows::Media::Internal::MediaManager::Uninitialize((Windows::Media::Internal::MediaManager *)this);
      return v4;
    }
    v19 = CAudioSrvMonitor::Start(v18);
    v4 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)(unsigned int)v19,
        v21);
      Windows::Media::Internal::MediaManager::Uninitialize((Windows::Media::Internal::MediaManager *)this);
      return v4;
    }
    if ( *((_DWORD *)this[24] + 5) == 4 )
    {
      v20 = Windows::Media::Internal::MediaManager::RegisterAppClosureNotificationClient((Windows::Media::Internal::MediaManager *)this);
      v4 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE7,
          (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
          (const char *)(unsigned int)v20,
          v21);
        Windows::Media::Internal::MediaManager::Uninitialize((Windows::Media::Internal::MediaManager *)this);
        return v4;
      }
    }
    *((_BYTE *)this + 160) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18007e38c  mov     [rsp-8+arg_8], rbx
0x18007e391  mov     [rsp-8+arg_10], rdi
0x18007e396  push    rbp
0x18007e397  lea     rbp, [rsp-11E0h]
0x18007e39f  mov     eax, 12E0h
0x18007e3a4  call    _alloca_probe
0x18007e3a9  sub     rsp, rax
0x18007e3ac  mov     rax, cs:__security_cookie
0x18007e3b3  xor     rax, rsp
0x18007e3b6  mov     [rbp+11E0h+var_10], rax
0x18007e3bd  mov     rbx, rcx
0x18007e3c0  mov     [rsp+12E0h+var_1278], rcx
0x18007e3c5  mov     [rsp+12E0h+var_1270], 1
0x18007e3ca  call    ?IsRunningInVM@@YA_NXZ; IsRunningInVM(void)
0x18007e3cf  mov     [rbx+0D0h], al
0x18007e3d5  test    al, al
0x18007e3d7  jz      loc_18007E6B1
0x18007e3dd  mov     [rbp+11E0h+Src], 13h
0x18007e3e7  mov     [rbp+11E0h+var_62C], 1
0x18007e3f2  mov     [rbp+11E0h+var_624], 0
0x18007e3fc  mov     [rbp+11E0h+var_620], 61h ; 'a'
0x18007e406  xor     edx, edx; Val
0x18007e408  mov     r8d, 600h; Size
0x18007e40e  lea     rcx, [rbp+11E0h+var_61C]; void *
0x18007e415  call    memset_0
0x18007e41a  lea     rdx, [rsp+12E0h+var_12A0]
0x18007e41f  lea     rcx, [rbp+11E0h+Src]
0x18007e426  call    ??$CastTo@UXvmActivateMediaManager@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateMediaManager@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateMediaManager>(XvmActivateMediaManager * *)
0x18007e42b  mov     edi, eax
0x18007e42d  test    eax, eax
0x18007e42f  jns     short loc_18007E45D
0x18007e431  mov     rcx, [rbp+11E8h]; this
0x18007e438  mov     r9d, eax; char *
0x18007e43b  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e442  mov     edx, 0C8h; void *
0x18007e447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e44c  nop
0x18007e44d  mov     rcx, rbx; this
0x18007e450  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e455  nop
0x18007e456  mov     eax, edi
0x18007e458  jmp     loc_18007E813
0x18007e45d  call    ?GetRootProxyAudioObjectActivator@@YAPEAVCGuestXvmAudioObject@@XZ; GetRootProxyAudioObjectActivator(void)
0x18007e462  mov     rdi, rax
0x18007e465  test    rax, rax
0x18007e468  jnz     short loc_18007E496
0x18007e46a  mov     rcx, [rbp+11E8h]; this
0x18007e471  mov     edi, 8000FFFFh
0x18007e476  mov     r9d, edi; char *
0x18007e479  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e480  mov     edx, 0CBh; void *
0x18007e485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e48a  nop
0x18007e48b  mov     rcx, rbx; this
0x18007e48e  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e493  nop
0x18007e494  jmp     short loc_18007E456
0x18007e496  mov     [rsp+12E0h+pv], 0
0x18007e49f  mov     qword ptr [rsp+12E0h+var_1298], 0
0x18007e4a8  lea     rax, [rsp+12E0h+pv]
0x18007e4ad  mov     [rsp+12E0h+var_1290], rax
0x18007e4b2  mov     [rsp+12E0h+var_1288], 0
0x18007e4bb  mov     [rsp+12E0h+var_1280], 1
0x18007e4c0  lea     rcx, [rsp+12E0h+var_1268]; void *
0x18007e4c5  lea     rdx, [rbp+11E0h+Src]; Src
0x18007e4cc  mov     r8d, 614h; Size
0x18007e4d2  call    memcpy_0
0x18007e4d7  lea     rcx, [rbp+11E0h+var_C50]; void *
0x18007e4de  lea     rdx, [rsp+12E0h+var_1268]; Src
0x18007e4e3  mov     r8d, 614h; Size
0x18007e4e9  call    memcpy_0
0x18007e4ee  lea     rax, [rsp+12E0h+var_1298]
0x18007e4f3  mov     qword ptr [rsp+12E0h+var_12C0], rax; int
0x18007e4f8  lea     r9, [rsp+12E0h+var_1288]
0x18007e4fd  lea     r8, [rbp+11E0h+var_C50]
0x18007e504  mov     edx, [rdi+30h]
0x18007e507  mov     rcx, rdi
0x18007e50a  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x18007e50f  mov     edi, eax
0x18007e511  lea     rcx, [rsp+12E0h+var_1290]
0x18007e516  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007e51b  test    edi, edi
0x18007e51d  jns     short loc_18007E563
0x18007e51f  mov     rcx, [rbp+11E8h]; this
0x18007e526  mov     r9d, edi; char *
0x18007e529  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e530  mov     edx, 0CFh; void *
0x18007e535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e53a  nop
0x18007e53b  mov     rcx, [rsp+12E0h+pv]; pv
0x18007e540  mov     [rsp+12E0h+pv], 0
0x18007e549  test    rcx, rcx
0x18007e54c  jz      short loc_18007E555
0x18007e54e  call    cs:__imp_CoTaskMemFree
0x18007e554  nop
0x18007e555  mov     rcx, rbx; this
0x18007e558  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e55d  nop
0x18007e55e  jmp     loc_18007E456
0x18007e563  mov     [rsp+12E0h+var_12A8], 0
0x18007e56c  lea     rax, [rsp+12E0h+var_12A8]
0x18007e571  mov     [rsp+12E0h+var_12A0], rax
0x18007e576  lea     rcx, [rsp+12E0h+var_12A0]
0x18007e57b  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007e580  mov     rdx, rax
0x18007e583  mov     rcx, rbx
0x18007e586  call    ??$AsWeak@VCGuestSpatialAudioClient@@@WRL@Microsoft@@YAJPEAVCGuestSpatialAudioClient@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(CGuestSpatialAudioClient *,Microsoft::WRL::WeakRef *)
0x18007e58b  mov     edi, eax
0x18007e58d  test    eax, eax
0x18007e58f  jns     short loc_18007E5E0
0x18007e591  mov     rcx, [rbp+11E8h]; this
0x18007e598  mov     r9d, eax; char *
0x18007e59b  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e5a2  mov     edx, 0D2h; void *
0x18007e5a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e5ac  nop
0x18007e5ad  lea     rcx, [rsp+12E0h+var_12A8]
0x18007e5b2  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007e5b7  nop
0x18007e5b8  mov     rcx, [rsp+12E0h+pv]; pv
0x18007e5bd  mov     [rsp+12E0h+pv], 0
0x18007e5c6  test    rcx, rcx
0x18007e5c9  jz      short loc_18007E5D2
0x18007e5cb  call    cs:__imp_CoTaskMemFree
0x18007e5d1  nop
0x18007e5d2  mov     rcx, rbx; this
0x18007e5d5  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e5da  nop
0x18007e5db  jmp     loc_18007E456
0x18007e5e0  lea     rcx, [rbx+10h]; this
0x18007e5e4  lea     r9, [rbp+11E0h+Src]; struct XvmActivateProxyAudioObject *
0x18007e5eb  lea     r8, [rsp+12E0h+var_12A8]; struct Microsoft::WRL::WeakRef *
0x18007e5f0  mov     rdx, qword ptr [rsp+12E0h+var_1298]
0x18007e5f5  mov     edx, [rdx+0Ch]; unsigned int
0x18007e5f8  call    ?Initialize@CGuestXvmAudioObject@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUXvmActivateProxyAudioObject@@@Z; CGuestXvmAudioObject::Initialize(uint,Microsoft::WRL::WeakRef &,XvmActivateProxyAudioObject *)
0x18007e5fd  mov     edi, eax
0x18007e5ff  test    eax, eax
0x18007e601  jns     short loc_18007E652
0x18007e603  mov     rcx, [rbp+11E8h]; this
0x18007e60a  mov     r9d, eax; char *
0x18007e60d  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e614  mov     edx, 0D4h; void *
0x18007e619  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e61e  nop
0x18007e61f  lea     rcx, [rsp+12E0h+var_12A8]
0x18007e624  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007e629  nop
0x18007e62a  mov     rcx, [rsp+12E0h+pv]; pv
0x18007e62f  mov     [rsp+12E0h+pv], 0
0x18007e638  test    rcx, rcx
0x18007e63b  jz      short loc_18007E644
0x18007e63d  call    cs:__imp_CoTaskMemFree
0x18007e643  nop
0x18007e644  mov     rcx, rbx; this
0x18007e647  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e64c  nop
0x18007e64d  jmp     loc_18007E456
0x18007e652  mov     rdi, [rbx+30h]
0x18007e656  lea     rcx, [rbx+78h]
0x18007e65a  mov     [rbx+30h], rcx
0x18007e65e  test    rcx, rcx
0x18007e661  jz      short loc_18007E66F
0x18007e663  mov     rax, [rcx]
0x18007e666  mov     rax, [rax+8]
0x18007e66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e66f  test    rdi, rdi
0x18007e672  jz      short loc_18007E684
0x18007e674  mov     rax, [rdi]
0x18007e677  mov     rcx, rdi
0x18007e67a  mov     rax, [rax+10h]
0x18007e67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e683  nop
0x18007e684  lea     rcx, [rsp+12E0h+var_12A8]
0x18007e689  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007e68e  nop
0x18007e68f  mov     rcx, [rsp+12E0h+pv]; pv
0x18007e694  mov     [rsp+12E0h+pv], 0
0x18007e69d  test    rcx, rcx
0x18007e6a0  jz      loc_18007E811
0x18007e6a6  call    cs:__imp_CoTaskMemFree
0x18007e6ac  jmp     loc_18007E811
0x18007e6b1  lea     rdx, [rbx+78h]
0x18007e6b5  mov     ecx, 10000h
0x18007e6ba  call    cs:__imp_RegisterForMediaCallback
0x18007e6c0  mov     edi, eax
0x18007e6c2  test    eax, eax
0x18007e6c4  jns     short loc_18007E6F0
0x18007e6c6  mov     rcx, [rbp+11E8h]; this
0x18007e6cd  mov     r9d, eax; char *
0x18007e6d0  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e6d7  mov     edx, 0DBh; void *
0x18007e6dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e6e1  nop
0x18007e6e2  mov     rcx, rbx; this
0x18007e6e5  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e6ea  nop
0x18007e6eb  jmp     loc_18007E456
0x18007e6f0  mov     byte ptr [rbx+0A1h], 1
0x18007e6f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007e6fe  mov     ecx, 20h ; ' '; unsigned __int64
0x18007e703  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007e708  mov     [rsp+12E0h+var_12A0], rax
0x18007e70d  test    rax, rax
0x18007e710  jz      short loc_18007E73D
0x18007e712  lea     rcx, ??_7CAudioSrvMonitor@@6B@; const CAudioSrvMonitor::`vftable'
0x18007e719  mov     [rax], rcx
0x18007e71c  lea     rcx, [rbx+90h]
0x18007e723  mov     [rax+8], rcx
0x18007e727  mov     dword ptr [rax+10h], 1
0x18007e72e  mov     dword ptr [rax+14h], 1
0x18007e735  mov     qword ptr [rax+18h], 0
0x18007e73d  mov     rdx, [rbx+0C0h]
0x18007e744  mov     [rbx+0C0h], rax
0x18007e74b  test    rdx, rdx
0x18007e74e  jz      short loc_18007E755
0x18007e750  call    ??R?$default_delete@VCAudioSrvMonitor@@@std@@QEBAXPEAVCAudioSrvMonitor@@@Z; std::default_delete<CAudioSrvMonitor>::operator()(CAudioSrvMonitor *)
0x18007e755  mov     rcx, [rbx+0C0h]; this
0x18007e75c  test    rcx, rcx
0x18007e75f  jnz     short loc_18007E790
0x18007e761  mov     rcx, [rbp+11E8h]; this
0x18007e768  mov     edi, 8007000Eh
0x18007e76d  mov     r9d, edi; char *
0x18007e770  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e777  mov     edx, 0E0h; void *
0x18007e77c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e781  nop
0x18007e782  mov     rcx, rbx; this
0x18007e785  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e78a  nop
0x18007e78b  jmp     loc_18007E456
0x18007e790  call    ?Start@CAudioSrvMonitor@@QEAAJXZ; CAudioSrvMonitor::Start(void)
0x18007e795  mov     edi, eax
0x18007e797  test    eax, eax
0x18007e799  jns     short loc_18007E7C5
0x18007e79b  mov     rcx, [rbp+11E8h]; this
0x18007e7a2  mov     r9d, eax; char *
0x18007e7a5  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e7ac  mov     edx, 0E3h; void *
0x18007e7b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e7b6  nop
0x18007e7b7  mov     rcx, rbx; this
0x18007e7ba  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e7bf  nop
0x18007e7c0  jmp     loc_18007E456
0x18007e7c5  mov     rax, [rbx+0C0h]
0x18007e7cc  cmp     dword ptr [rax+14h], 4
0x18007e7d0  jnz     short loc_18007E80A
0x18007e7d2  mov     rcx, rbx; this
0x18007e7d5  call    ?RegisterAppClosureNotificationClient@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::RegisterAppClosureNotificationClient(void)
0x18007e7da  mov     edi, eax
0x18007e7dc  test    eax, eax
0x18007e7de  jns     short loc_18007E80A
0x18007e7e0  mov     rcx, [rbp+11E8h]; this
0x18007e7e7  mov     r9d, eax; char *
0x18007e7ea  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18007e7f1  mov     edx, 0E7h; void *
0x18007e7f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007e7fb  nop
0x18007e7fc  mov     rcx, rbx; this
0x18007e7ff  call    ?Uninitialize@MediaManager@Internal@Media@Windows@@AEAAJXZ; Windows::Media::Internal::MediaManager::Uninitialize(void)
0x18007e804  nop
0x18007e805  jmp     loc_18007E456
0x18007e80a  mov     byte ptr [rbx+0A0h], 1
0x18007e811  xor     eax, eax
0x18007e813  mov     rcx, [rbp+11E0h+var_10]
0x18007e81a  xor     rcx, rsp; StackCookie
0x18007e81d  call    __security_check_cookie
0x18007e822  lea     r11, [rsp+12E0h+var_s0]
0x18007e82a  mov     rbx, [r11+18h]
0x18007e82e  mov     rdi, [r11+20h]
0x18007e832  mov     rsp, r11
0x18007e835  pop     rbp
0x18007e836  retn
```
