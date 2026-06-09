# CCoreMFT::InitializeBase(void)

- ea: `0x1801332b4`
- end: `0x18013351c`
- name: `?InitializeBase@CCoreMFT@@IEAAJXZ`
- size: `616`
- prototype: `__int64 __fastcall(CCoreMFT *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001937c`
- `0x1800afb38`

## callees

- `0x180005660`
- `0x18000b490`
- `0x18000c0f8`
- `0x18002bb98`
- `0x1801332b4`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013337b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013337b`
- `MFPlat!MFCreateAttributes` at `0x1801332e9`
- `MFPlat!MFCreateAttributes` at `0x18013346a`
- `MFPlat!MFCreateAttributes` at `0x1801332e9`
- `MFPlat!MFCreateAttributes` at `0x18013346a`

## pseudocode

```c
__int64 __fastcall CCoreMFT::InitializeBase(CCoreMFT *this)
{
  IMFAttributes **v1; // rdi
  HRESULT Instance; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v1 = (IMFAttributes **)((char *)this + 128);
  v8 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 128);
  Instance = MFCreateAttributes(v1, 3u);
  if ( Instance < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_26;
    v4 = 15;
    goto LABEL_25;
  }
  Instance = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))(*v1)->lpVtbl->SetUINT32)(
               *v1,
               MF_SA_D3D11_AWARE,
               1);
  if ( Instance < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_26;
    v4 = 16;
    goto LABEL_25;
  }
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease((char *)this + 240);
  Instance = CoCreateInstance(
               &CLSID_VideoProcessorMFT,
               0,
               1u,
               &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
               (LPVOID *)this + 30);
  if ( Instance < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_26;
    v4 = 17;
    goto LABEL_25;
  }
  v5 = *((_QWORD *)this + 30);
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  Instance = v6(v5, &v8);
  if ( Instance < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_26;
    v4 = 18;
    goto LABEL_25;
  }
  Instance = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v8 + 168LL))(
               v8,
               &MF_XVP_DISABLE_FRC,
               1);
  if ( Instance < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_26;
    v4 = 19;
    goto LABEL_25;
  }
  Instance = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v8 + 168LL))(
               v8,
               MF_XVP_CALLER_ALLOCATES_OUTPUT,
               1);
  if ( Instance < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_26;
    v4 = 20;
    goto LABEL_25;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 280);
  Instance = MFCreateAttributes((IMFAttributes **)this + 35, 1u);
  if ( Instance < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_26;
    v4 = 21;
    goto LABEL_25;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**((_QWORD **)this + 35) + 168LL))(
               *((_QWORD *)this + 35),
               MF_SA_D3D11_BINDFLAGS,
               32);
  if ( Instance < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v4 = 22;
LABEL_25:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, Instance);
  }
LABEL_26:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, Instance);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801332b4  mov     [rsp+arg_8], rbx
0x1801332b9  mov     [rsp+arg_10], rbp
0x1801332be  push    rsi
0x1801332bf  push    rdi
0x1801332c0  push    r14
0x1801332c2  sub     rsp, 30h
0x1801332c6  lea     rdi, [rcx+80h]
0x1801332cd  mov     [rsp+48h+arg_0], 0
0x1801332d6  mov     rbp, rcx
0x1801332d9  mov     rcx, rdi
0x1801332dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801332e1  mov     edx, 3; cInitialSize
0x1801332e6  mov     rcx, rdi; ppMFAttributes
0x1801332e9  call    cs:__imp_MFCreateAttributes
0x1801332ef  lea     r14, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x1801332f6  mov     ebx, eax
0x1801332f8  test    eax, eax
0x1801332fa  jns     short loc_180133317
0x1801332fc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133301  mov     esi, 1
0x180133306  cmp     al, sil
0x180133309  jb      loc_1801334D5
0x18013330f  lea     edx, [rsi+0Eh]
0x180133312  jmp     loc_1801334BB
0x180133317  mov     rcx, [rdi]
0x18013331a  lea     rdx, MF_SA_D3D11_AWARE
0x180133321  mov     esi, 1
0x180133326  mov     r8d, esi
0x180133329  mov     rax, [rcx]
0x18013332c  mov     rax, [rax+0A8h]
0x180133333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133338  mov     ebx, eax
0x18013333a  test    eax, eax
0x18013333c  jns     short loc_180133354
0x18013333e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133343  cmp     al, sil
0x180133346  jb      loc_1801334D5
0x18013334c  lea     edx, [rsi+0Fh]
0x18013334f  jmp     loc_1801334BB
0x180133354  lea     rdi, [rbp+0F0h]
0x18013335b  mov     rcx, rdi
0x18013335e  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180133363  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x18013336a  mov     [rsp+48h+ppv], rdi; ppv
0x18013336f  mov     r8d, esi; dwClsContext
0x180133372  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x180133379  xor     edx, edx; pUnkOuter
0x18013337b  call    cs:__imp_CoCreateInstance
0x180133381  mov     ebx, eax
0x180133383  test    eax, eax
0x180133385  jns     short loc_18013339F
0x180133387  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013338c  cmp     al, sil
0x18013338f  jb      loc_1801334D5
0x180133395  mov     edx, 11h
0x18013339a  jmp     loc_1801334BB
0x18013339f  mov     rdi, [rdi]
0x1801333a2  lea     rcx, [rsp+48h+arg_0]
0x1801333a7  mov     rax, [rdi]
0x1801333aa  mov     rbx, [rax+40h]
0x1801333ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801333b3  lea     rdx, [rsp+48h+arg_0]
0x1801333b8  mov     rcx, rdi
0x1801333bb  mov     rax, rbx
0x1801333be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801333c3  mov     ebx, eax
0x1801333c5  test    eax, eax
0x1801333c7  jns     short loc_1801333E1
0x1801333c9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801333ce  cmp     al, sil
0x1801333d1  jb      loc_1801334D5
0x1801333d7  mov     edx, 12h
0x1801333dc  jmp     loc_1801334BB
0x1801333e1  mov     rcx, [rsp+48h+arg_0]
0x1801333e6  lea     rdx, MF_XVP_DISABLE_FRC
0x1801333ed  mov     r8d, esi
0x1801333f0  mov     rax, [rcx]
0x1801333f3  mov     rax, [rax+0A8h]
0x1801333fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801333ff  mov     ebx, eax
0x180133401  test    eax, eax
0x180133403  jns     short loc_18013341D
0x180133405  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013340a  cmp     al, sil
0x18013340d  jb      loc_1801334D5
0x180133413  mov     edx, 13h
0x180133418  jmp     loc_1801334BB
0x18013341d  mov     rcx, [rsp+48h+arg_0]
0x180133422  lea     rdx, MF_XVP_CALLER_ALLOCATES_OUTPUT
0x180133429  mov     r8d, esi
0x18013342c  mov     rax, [rcx]
0x18013342f  mov     rax, [rax+0A8h]
0x180133436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013343b  mov     ebx, eax
0x18013343d  test    eax, eax
0x18013343f  jns     short loc_180133456
0x180133441  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180133446  cmp     al, sil
0x180133449  jb      loc_1801334D5
0x18013344f  mov     edx, 14h
0x180133454  jmp     short loc_1801334BB
0x180133456  lea     rdi, [rbp+118h]
0x18013345d  mov     rcx, rdi
0x180133460  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180133465  mov     edx, esi; cInitialSize
0x180133467  mov     rcx, rdi; ppMFAttributes
0x18013346a  call    cs:__imp_MFCreateAttributes
0x180133470  mov     ebx, eax
0x180133472  test    eax, eax
0x180133474  jns     short loc_180133487
0x180133476  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013347b  cmp     al, sil
0x18013347e  jb      short loc_1801334D5
0x180133480  mov     edx, 15h
0x180133485  jmp     short loc_1801334BB
0x180133487  mov     rcx, [rdi]
0x18013348a  lea     rdx, MF_SA_D3D11_BINDFLAGS
0x180133491  mov     r8d, 20h ; ' '
0x180133497  mov     rax, [rcx]
0x18013349a  mov     rax, [rax+0A8h]
0x1801334a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801334a6  mov     ebx, eax
0x1801334a8  test    eax, eax
0x1801334aa  jns     short loc_1801334D5
0x1801334ac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801334b1  cmp     al, sil
0x1801334b4  jb      short loc_1801334D5
0x1801334b6  mov     edx, 16h
0x1801334bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801334c2  mov     r9, rbp
0x1801334c5  mov     r8, r14
0x1801334c8  mov     dword ptr [rsp+48h+ppv], ebx
0x1801334cc  mov     rcx, [rcx+10h]
0x1801334d0  call    WPP_SF_qD
0x1801334d5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801334da  cmp     al, 20h ; ' '
0x1801334dc  jb      short loc_1801334FD
0x1801334de  mov     rcx, cs:WPP_GLOBAL_Control
0x1801334e5  mov     edx, 17h
0x1801334ea  mov     r9, rbp
0x1801334ed  mov     dword ptr [rsp+48h+ppv], ebx
0x1801334f1  mov     r8, r14
0x1801334f4  mov     rcx, [rcx+10h]
0x1801334f8  call    WPP_SF_qD
0x1801334fd  lea     rcx, [rsp+48h+arg_0]
0x180133502  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180133507  mov     rbp, [rsp+48h+arg_10]
0x18013350c  mov     eax, ebx
0x18013350e  mov     rbx, [rsp+48h+arg_8]
0x180133513  add     rsp, 30h
0x180133517  pop     r14
0x180133519  pop     rdi
0x18013351a  pop     rsi
0x18013351b  retn
```
