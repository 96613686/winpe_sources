# Windows::Graphics::Capture::Server::CaptureSession::RuntimeClassInitialize(Windows::Graphics::Capture::Server::CapturableItem *,void *)

- ea: `0x18001ca68`
- end: `0x18001ccbf`
- name: `?RuntimeClassInitialize@CaptureSession@Server@Capture@Graphics@Windows@@QEAAJPEAVCapturableItem@2345@PEAX@Z`
- size: `599`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, struct Windows::Graphics::Capture::Server::CapturableItem *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c4d0`

## callees

- `0x18000907c`
- `0x18000ddc4`
- `0x18001881c`
- `0x18001bbf4`
- `0x18001c134`
- `0x18001ca68`
- `0x18001e128`
- `0x18001ea08`
- `0x18001f208`
- `0x18001fe88`
- `0x18001ff68`
- `0x180022010`

## string_xrefs

- `0x18001cac6`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`
- `0x18001cc89`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::RuntimeClassInitialize(
        Windows::Graphics::Capture::Server::CaptureSession *this,
        struct Windows::Graphics::Capture::Server::CapturableItem *a2,
        void *a3)
{
  __int64 v5; // rdi
  int ClientProcessId; // edi
  __int64 v7; // rdx
  Windows::Graphics::Capture::Server::CaptureSessionManager *v9; // rcx
  _QWORD *v10; // r14
  _QWORD *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 *v17; // [rsp+20h] [rbp-20h] BYREF
  struct IDCompositionCaptureRenderTargetInternal *v18; // [rsp+28h] [rbp-18h] BYREF
  char v19; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v21; // [rsp+70h] [rbp+30h] BYREF
  __int64 v22; // [rsp+78h] [rbp+38h] BYREF

  v5 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Graphics::Capture::Server::CapturableItem *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  ClientProcessId = Windows::Graphics::Capture::Server::GetClientProcessId(
                      (Windows::Graphics::Capture::Server::CaptureSession *)((char *)this + 108),
                      (unsigned int *)a2);
  if ( ClientProcessId < 0 )
  {
    v7 = 55;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
      (const char *)(unsigned int)ClientProcessId,
      (int)v17);
    return (unsigned int)ClientProcessId;
  }
  *((_BYTE *)this + 106) = !Windows::Graphics::Capture::Server::CheckCAMCapability(1, *((_DWORD *)this + 27));
  ClientProcessId = Windows::Graphics::Capture::Server::CaptureSessionManager::RegisterCaptureSession(v9, this);
  if ( ClientProcessId < 0 )
  {
    v7 = 59;
    goto LABEL_7;
  }
  ClientProcessId = Windows::Graphics::Capture::Server::DCompManager::MakeCaptureController(
                      Windows::Graphics::Capture::Server::g_DCompManager,
                      (struct IDCompositionCaptureControllerReferenceInternal **)this + 11,
                      (void **)this + 12);
  if ( ClientProcessId < 0 )
  {
    v7 = 64;
    goto LABEL_7;
  }
  v10 = (_QWORD *)((char *)this + 72);
  ClientProcessId = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(*((_QWORD *)this + 8) + 72LL) + 72LL))(
                      *(_QWORD *)(*((_QWORD *)this + 8) + 72LL),
                      (char *)this + 72);
  if ( ClientProcessId < 0 )
  {
    v7 = 67;
    goto LABEL_7;
  }
  ClientProcessId = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v10 + 48LL))(*v10, *((_QWORD *)this + 12));
  if ( ClientProcessId < 0 )
  {
    v7 = 70;
    goto LABEL_7;
  }
  v11 = (_QWORD *)((char *)this + 80);
  v17 = (__int64 *)((char *)this + 80);
  v18 = 0;
  v19 = 1;
  ClientProcessId = Windows::Graphics::Capture::Server::DCompManager::MakeCaptureRenderTarget(
                      Windows::Graphics::Capture::Server::g_DCompManager,
                      &v18);
  wil::details::out_param_t<wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>>(&v17);
  if ( ClientProcessId < 0 )
  {
    v7 = 74;
    goto LABEL_7;
  }
  LOBYTE(v12) = 1;
  ClientProcessId = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v11 + 48LL))(*v11, v12);
  if ( ClientProcessId < 0 )
  {
    v7 = 78;
    goto LABEL_7;
  }
  ClientProcessId = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v11 + 32LL))(*v11, a3);
  if ( ClientProcessId < 0 )
  {
    v7 = 79;
    goto LABEL_7;
  }
  v21 = 0;
  wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v21);
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v10)(*v10, &GUID_c0f7b3ec_fa9a_4c7b_ac48_eec1493b2d1e, &v21) < 0 )
    goto LABEL_30;
  v22 = v21;
  v13 = *((_QWORD *)this + 16);
  *((_QWORD *)this + 16) = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Internal::PlatformExtensions::Capture::IFilteredCaptureSession *>(
          (_QWORD *)this + 16,
          &v22);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v11 + 80LL))(*v11, 0);
    v15 = v14;
    if ( v14 < 0 )
    {
      v16 = 90;
      goto LABEL_29;
    }
LABEL_30:
    v15 = 0;
    goto LABEL_31;
  }
  v16 = 87;
LABEL_29:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)v14,
    (int)v17);
LABEL_31:
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v21);
  return v15;
}

```

## disassembly

```asm
0x18001ca68  mov     [rsp-28h+arg_10], rbx
0x18001ca6d  push    rbp
0x18001ca6e  push    rsi
0x18001ca6f  push    rdi
0x18001ca70  push    r14
0x18001ca72  push    r15
0x18001ca74  mov     rbp, rsp
0x18001ca77  sub     rsp, 40h
0x18001ca7b  mov     r15, r8
0x18001ca7e  mov     rbx, rcx
0x18001ca81  mov     rdi, [rcx+40h]
0x18001ca85  mov     [rcx+40h], rdx
0x18001ca89  test    rdx, rdx
0x18001ca8c  jz      short loc_18001CA9D
0x18001ca8e  mov     rax, [rdx]
0x18001ca91  mov     rcx, rdx
0x18001ca94  mov     rax, [rax+8]
0x18001ca98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca9d  test    rdi, rdi
0x18001caa0  jz      short loc_18001CAB2
0x18001caa2  mov     rax, [rdi]
0x18001caa5  mov     rcx, rdi
0x18001caa8  mov     rax, [rax+10h]
0x18001caac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cab1  nop
0x18001cab2  lea     rcx, [rbx+6Ch]; this
0x18001cab6  call    ?GetClientProcessId@Server@Capture@Graphics@Windows@@YAJPEAK@Z; Windows::Graphics::Capture::Server::GetClientProcessId(ulong *)
0x18001cabb  mov     edi, eax
0x18001cabd  test    eax, eax
0x18001cabf  jns     short loc_18001CAE0
0x18001cac1  mov     edx, 37h ; '7'; void *
0x18001cac6  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001cacd  mov     r9d, edi; char *
0x18001cad0  mov     rcx, [rbp+28h]; this
0x18001cad4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cad9  mov     eax, edi
0x18001cadb  jmp     loc_18001CCAB
0x18001cae0  mov     edx, [rbx+6Ch]
0x18001cae3  mov     ecx, 1
0x18001cae8  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@K@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,ulong)
0x18001caed  xor     al, 1
0x18001caef  mov     [rbx+6Ah], al
0x18001caf2  mov     rdx, rbx; struct Windows::Graphics::Capture::Server::CaptureSession *
0x18001caf5  call    ?RegisterCaptureSession@CaptureSessionManager@Server@Capture@Graphics@Windows@@QEAAJPEAVCaptureSession@2345@@Z; Windows::Graphics::Capture::Server::CaptureSessionManager::RegisterCaptureSession(Windows::Graphics::Capture::Server::CaptureSession *)
0x18001cafa  mov     edi, eax
0x18001cafc  test    eax, eax
0x18001cafe  jns     short loc_18001CB07
0x18001cb00  mov     edx, 3Bh ; ';'
0x18001cb05  jmp     short loc_18001CAC6
0x18001cb07  lea     rdx, [rbx+58h]; struct IDCompositionCaptureControllerReferenceInternal **
0x18001cb0b  lea     r8, [rbx+60h]; void **
0x18001cb0f  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001cb16  call    ?MakeCaptureController@DCompManager@Server@Capture@Graphics@Windows@@QEAAJPEAPEAUIDCompositionCaptureControllerReferenceInternal@@PEAPEAX@Z; Windows::Graphics::Capture::Server::DCompManager::MakeCaptureController(IDCompositionCaptureControllerReferenceInternal * *,void * *)
0x18001cb1b  mov     edi, eax
0x18001cb1d  test    eax, eax
0x18001cb1f  jns     short loc_18001CB28
0x18001cb21  mov     edx, 40h ; '@'
0x18001cb26  jmp     short loc_18001CAC6
0x18001cb28  mov     rax, [rbx+40h]
0x18001cb2c  mov     rcx, [rax+48h]
0x18001cb30  lea     r14, [rbx+48h]
0x18001cb34  mov     rax, [rcx]
0x18001cb37  mov     rdx, r14
0x18001cb3a  mov     rax, [rax+48h]
0x18001cb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb43  mov     edi, eax
0x18001cb45  test    eax, eax
0x18001cb47  jns     short loc_18001CB53
0x18001cb49  mov     edx, 43h ; 'C'
0x18001cb4e  jmp     loc_18001CAC6
0x18001cb53  mov     rcx, [r14]
0x18001cb56  mov     rax, [rcx]
0x18001cb59  mov     rdx, [rbx+60h]
0x18001cb5d  mov     rax, [rax+30h]
0x18001cb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb66  mov     edi, eax
0x18001cb68  test    eax, eax
0x18001cb6a  jns     short loc_18001CB76
0x18001cb6c  mov     edx, 46h ; 'F'
0x18001cb71  jmp     loc_18001CAC6
0x18001cb76  lea     rsi, [rbx+50h]
0x18001cb7a  mov     [rbp+var_20], rsi
0x18001cb7e  mov     [rbp+var_18], 0
0x18001cb86  mov     [rbp+var_10], 1
0x18001cb8a  lea     rdx, [rbp+var_18]; struct IDCompositionCaptureRenderTargetInternal **
0x18001cb8e  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001cb95  call    ?MakeCaptureRenderTarget@DCompManager@Server@Capture@Graphics@Windows@@QEAAJPEAPEAUIDCompositionCaptureRenderTargetInternal@@@Z; Windows::Graphics::Capture::Server::DCompManager::MakeCaptureRenderTarget(IDCompositionCaptureRenderTargetInternal * *)
0x18001cb9a  mov     edi, eax
0x18001cb9c  lea     rcx, [rbp+var_20]
0x18001cba0  call    ??1?$out_param_t@V?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>>(void)
0x18001cba5  test    edi, edi
0x18001cba7  jns     short loc_18001CBB3
0x18001cba9  mov     edx, 4Ah ; 'J'
0x18001cbae  jmp     loc_18001CAC6
0x18001cbb3  mov     rcx, [rsi]
0x18001cbb6  mov     rax, [rcx]
0x18001cbb9  mov     dl, 1
0x18001cbbb  mov     rax, [rax+30h]
0x18001cbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc4  mov     edi, eax
0x18001cbc6  test    eax, eax
0x18001cbc8  jns     short loc_18001CBD4
0x18001cbca  mov     edx, 4Eh ; 'N'
0x18001cbcf  jmp     loc_18001CAC6
0x18001cbd4  mov     rcx, [rsi]
0x18001cbd7  mov     rax, [rcx]
0x18001cbda  mov     rdx, r15
0x18001cbdd  mov     rax, [rax+20h]
0x18001cbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbe6  mov     edi, eax
0x18001cbe8  test    eax, eax
0x18001cbea  jns     short loc_18001CBF6
0x18001cbec  mov     edx, 4Fh ; 'O'
0x18001cbf1  jmp     loc_18001CAC6
0x18001cbf6  mov     [rbp+arg_0], 0
0x18001cbfe  lea     rcx, [rbp+arg_0]
0x18001cc02  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x18001cc07  mov     rcx, [r14]
0x18001cc0a  mov     rax, [rcx]
0x18001cc0d  lea     r8, [rbp+arg_0]
0x18001cc11  lea     rdx, _GUID_c0f7b3ec_fa9a_4c7b_ac48_eec1493b2d1e
0x18001cc18  mov     rax, [rax]
0x18001cc1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc20  test    eax, eax
0x18001cc22  js      short loc_18001CC9E
0x18001cc24  mov     rax, [rbp+arg_0]
0x18001cc28  mov     [rbp+arg_8], rax
0x18001cc2c  mov     rcx, [rbx+80h]
0x18001cc33  mov     qword ptr [rbx+80h], 0
0x18001cc3e  test    rcx, rcx
0x18001cc41  jz      short loc_18001CC50
0x18001cc43  mov     rax, [rcx]
0x18001cc46  mov     rax, [rax+10h]
0x18001cc4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc4f  nop
0x18001cc50  lea     rdx, [rbp+arg_8]
0x18001cc54  lea     rcx, [rbx+80h]
0x18001cc5b  call    ??$MakeAndInitialize@VCaptureWindowFilter@Server@Capture@Graphics@Windows@@V12345@PEAUIFilteredCaptureSession@3PlatformExtensions@Internal@5@@Details@WRL@Microsoft@@YAJPEAPEAVCaptureWindowFilter@Server@Capture@Graphics@Windows@@$$QEAPEAUIFilteredCaptureSession@5PlatformExtensions@Internal@7@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Graphics::Capture::Server::CaptureWindowFilter,Windows::Internal::PlatformExtensions::Capture::IFilteredCaptureSession *>(Windows::Graphics::Capture::Server::CaptureWindowFilter * *,Windows::Internal::PlatformExtensions::Capture::IFilteredCaptureSession * &&)
0x18001cc60  mov     ebx, eax
0x18001cc62  test    eax, eax
0x18001cc64  jns     short loc_18001CC6D
0x18001cc66  mov     edx, 57h ; 'W'
0x18001cc6b  jmp     short loc_18001CC89
0x18001cc6d  mov     rcx, [rsi]
0x18001cc70  mov     rax, [rcx]
0x18001cc73  xor     edx, edx
0x18001cc75  mov     rax, [rax+50h]
0x18001cc79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc7e  mov     ebx, eax
0x18001cc80  test    eax, eax
0x18001cc82  jns     short loc_18001CC9E
0x18001cc84  mov     edx, 5Ah ; 'Z'; void *
0x18001cc89  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001cc90  mov     r9d, eax; char *
0x18001cc93  mov     rcx, [rbp+28h]; this
0x18001cc97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc9c  jmp     short loc_18001CCA0
0x18001cc9e  xor     ebx, ebx
0x18001cca0  lea     rcx, [rbp+arg_0]
0x18001cca4  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001cca9  mov     eax, ebx
0x18001ccab  mov     rbx, [rsp+40h+arg_10]
0x18001ccb3  add     rsp, 40h
0x18001ccb7  pop     r15
0x18001ccb9  pop     r14
0x18001ccbb  pop     rdi
0x18001ccbc  pop     rsi
0x18001ccbd  pop     rbp
0x18001ccbe  retn
```
