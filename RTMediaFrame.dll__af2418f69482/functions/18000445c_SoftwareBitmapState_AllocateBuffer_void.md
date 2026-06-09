# SoftwareBitmapState::AllocateBuffer(void)

- ea: `0x18000445c`
- end: `0x1800046fb`
- name: `?AllocateBuffer@SoftwareBitmapState@@AEAAXXZ`
- size: `671`
- prototype: `void __fastcall(SoftwareBitmapState *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001fac`
- `0x180007a48`

## callees

- `0x1800019c0`
- `0x1800027c0`
- `0x180003fcc`
- `0x18000445c`
- `0x180005cd0`
- `0x180019758`
- `0x180021b44`
- `0x180026920`
- `0x180038d98`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800045d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800045d7`
- `MFPlat!MFCreate2DMediaBuffer` at `0x1800044ef`
- `MFPlat!MFCreate2DMediaBuffer` at `0x1800044ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SoftwareBitmapState::AllocateBuffer(SoftwareBitmapState *this)
{
  int v2; // r8d
  __int64 i; // rcx
  __int64 v4; // rdx
  DWORD *MFVideoFormat; // rax
  unsigned int v6; // eax
  int v7; // edx
  _QWORD *v8; // r15
  IMFMediaBuffer *v9; // rbx
  HRESULT (__stdcall *QueryInterface)(IMFMediaBuffer *, const IID *const, void **); // rdi
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // eax
  int v14; // edx
  unsigned int v15; // eax
  int v16; // edx
  IMFMediaBuffer *v17; // rcx
  _QWORD *v18; // r14
  LPVOID *v19; // rax
  unsigned int Instance; // eax
  int v21; // edx
  IMFMediaBuffer *v22; // rdi
  ULONG (__stdcall *AddRef)(IMFMediaBuffer *); // rbx
  unsigned int v24; // eax
  int v25; // edx
  unsigned int v26; // eax
  int v27; // edx
  IMFMediaBuffer *v28; // rcx
  __int64 v29; // rbx
  IMFMediaBuffer *ppBuffer; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v31; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v32[16]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v33; // [rsp+90h] [rbp+7h] BYREF

  v2 = *((_DWORD *)this + 4);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 8 )
      MF::ThrowOriginateError<15>(i, L"Invalid format");
    v4 = 28LL * (int)i;
    if ( *(_DWORD *)((char *)qword_1800716C0 + v4) == v2 )
      break;
  }
  ppBuffer = 0;
  if ( *((_BYTE *)qword_1800716C0 + v4 + 4) )
  {
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppBuffer);
    MFVideoFormat = (DWORD *)MediaFrameHelpers::GetMFVideoFormat(
                               &v33,
                               *((unsigned int *)this + 4),
                               *((unsigned int *)this + 5));
    v6 = MFCreate2DMediaBuffer(*((_DWORD *)this + 6), *((_DWORD *)this + 7), *MFVideoFormat, 0, &ppBuffer);
    MF::ThrowIfFailed((MF *)v6, v7);
    v8 = (_QWORD *)((char *)this + 88);
    v9 = ppBuffer;
    QueryInterface = ppBuffer->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease((char *)this + 88);
    v11 = ((__int64 (__fastcall *)(IMFMediaBuffer *, GUID *, char *))QueryInterface)(
            v9,
            &GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec,
            (char *)this + 88);
    MF::ThrowIfFailed((MF *)v11, v12);
    v31 = 0;
    v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v8 + 56LL))(*v8, &v31);
    MF::ThrowIfFailed((MF *)v13, v14);
    v15 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, v31);
    MF::ThrowIfFailed((MF *)v15, v16);
    v17 = ppBuffer;
    if ( ppBuffer )
    {
      ppBuffer = 0;
      ((void (__fastcall *)(IMFMediaBuffer *))v17->lpVtbl->Release)(v17);
    }
    v18 = (_QWORD *)((char *)this + 104);
  }
  else
  {
    v19 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(&ppBuffer);
    Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, v19);
    MF::ThrowIfFailed((MF *)Instance, v21);
    v22 = ppBuffer;
    AddRef = ppBuffer->lpVtbl[2].AddRef;
    v18 = (_QWORD *)((char *)this + 104);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease((char *)this + 104);
    v33 = *(_OWORD *)MediaFrameHelpers::GetWICPixelFormat(v32, *((unsigned int *)this + 4), *((unsigned int *)this + 5));
    v24 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD, _QWORD, __int128 *, int, char *))AddRef)(
            v22,
            *((unsigned int *)this + 6),
            *((unsigned int *)this + 7),
            &v33,
            1,
            (char *)this + 104);
    MF::ThrowIfFailed((MF *)v24, v25);
    v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 80LL))(*v18);
    MF::ThrowIfFailed((MF *)v26, v27);
    v28 = ppBuffer;
    if ( ppBuffer )
    {
      ppBuffer = 0;
      ((void (__fastcall *)(IMFMediaBuffer *))v28->lpVtbl->Release)(v28);
    }
    v8 = (_QWORD *)((char *)this + 88);
  }
  if ( g_wppLevels >= 0x20u )
  {
    v29 = *v18;
    if ( *v8 )
      v29 = *v8;
    WPP_SF_qqddddggdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((unsigned int *)this + 5),
      *((unsigned int *)this + 4),
      this,
      v29,
      *((_DWORD *)this + 4),
      *((_DWORD *)this + 5),
      *((_DWORD *)this + 6),
      *((_DWORD *)this + 7),
      *((_QWORD *)this + 6),
      *((_QWORD *)this + 7),
      *v8 != 0,
      *v18 != 0);
  }
}

```

## disassembly

```asm
0x18000445c  push    rbp
0x18000445e  push    rbx
0x18000445f  push    rsi
0x180004460  push    rdi
0x180004461  push    r14
0x180004463  push    r15
0x180004465  lea     rbp, [rsp-2Fh]
0x18000446a  sub     rsp, 0B8h
0x180004471  mov     rax, cs:__security_cookie
0x180004478  xor     rax, rsp
0x18000447b  mov     [rbp+57h+var_40], rax
0x18000447f  mov     rsi, rcx
0x180004482  mov     r8d, [rcx+10h]
0x180004486  xor     ecx, ecx
0x180004488  lea     r15d, [rcx+1]
0x18000448c  cmp     ecx, 8
0x18000448f  jnb     loc_180004685
0x180004495  movsxd  rax, ecx
0x180004498  imul    rdx, rax, 1Ch
0x18000449c  lea     rax, qword_1800716C0
0x1800044a3  cmp     [rdx+rax], r8d
0x1800044a7  jz      short loc_1800044AE
0x1800044a9  add     ecx, r15d
0x1800044ac  jmp     short loc_18000448C
0x1800044ae  mov     [rbp+57h+var_70], 0
0x1800044b6  cmp     byte ptr [rdx+rax+4], 0
0x1800044bb  jz      loc_1800045B6
0x1800044c1  lea     rcx, [rbp+57h+var_70]
0x1800044c5  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800044ca  mov     r8d, [rsi+14h]
0x1800044ce  mov     edx, [rsi+10h]
0x1800044d1  lea     rcx, [rbp+57h+var_50]
0x1800044d5  call    ?GetMFVideoFormat@MediaFrameHelpers@@SA?AU_GUID@@W4BitmapPixelFormat@Imaging@Graphics@Windows@@W4BitmapAlphaMode@456@@Z; MediaFrameHelpers::GetMFVideoFormat(Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Graphics::Imaging::BitmapAlphaMode)
0x1800044da  lea     rcx, [rbp+57h+var_70]
0x1800044de  mov     [rsp+0E0h+ppBuffer], rcx; ppBuffer
0x1800044e3  xor     r9d, r9d; fBottomUp
0x1800044e6  mov     r8d, [rax]; dwFourCC
0x1800044e9  mov     edx, [rsi+1Ch]; dwHeight
0x1800044ec  mov     ecx, [rsi+18h]; dwWidth
0x1800044ef  call    cs:__imp_MFCreate2DMediaBuffer
0x1800044f5  mov     ecx, eax; this
0x1800044f7  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800044fc  lea     r15, [rsi+58h]
0x180004500  mov     rbx, [rbp+57h+var_70]
0x180004504  mov     rax, [rbx]
0x180004507  mov     rdi, [rax]
0x18000450a  mov     rcx, r15
0x18000450d  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180004512  mov     r8, r15
0x180004515  lea     rdx, _GUID_33ae5ea6_4316_436f_8ddd_d73d22f829ec
0x18000451c  mov     rcx, rbx
0x18000451f  mov     rax, rdi
0x180004522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004527  nop
0x180004528  mov     ecx, eax; this
0x18000452a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000452f  mov     [rbp+57h+var_68], 0
0x180004536  mov     rcx, [r15]
0x180004539  mov     rax, [rcx]
0x18000453c  lea     rdx, [rbp+57h+var_68]
0x180004540  mov     rax, [rax+38h]
0x180004544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004549  mov     ecx, eax; this
0x18000454b  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180004550  mov     rcx, [rbp+57h+var_70]
0x180004554  mov     rax, [rcx]
0x180004557  mov     edx, [rbp+57h+var_68]
0x18000455a  mov     rax, [rax+30h]
0x18000455e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004563  mov     ecx, eax; this
0x180004565  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000456a  nop
0x18000456b  mov     rcx, [rbp+57h+var_70]
0x18000456f  test    rcx, rcx
0x180004572  jz      short loc_180004589
0x180004574  mov     [rbp+57h+var_70], 0
0x18000457c  mov     rax, [rcx]
0x18000457f  mov     rax, [rax+10h]
0x180004583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004588  nop
0x180004589  lea     r14, [rsi+68h]
0x18000458d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180004594  jnb     loc_180004692
0x18000459a  mov     rcx, [rbp+57h+var_40]
0x18000459e  xor     rcx, rsp; StackCookie
0x1800045a1  call    __security_check_cookie
0x1800045a6  add     rsp, 0B8h
0x1800045ad  pop     r15
0x1800045af  pop     r14
0x1800045b1  pop     rdi
0x1800045b2  pop     rsi
0x1800045b3  pop     rbx
0x1800045b4  pop     rbp
0x1800045b5  retn
0x1800045b6  lea     rcx, [rbp+57h+var_70]
0x1800045ba  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICImagingFactory>>)
0x1800045bf  mov     [rsp+0E0h+ppBuffer], rax; ppv
0x1800045c4  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800045cb  mov     r8d, r15d; dwClsContext
0x1800045ce  xor     edx, edx; pUnkOuter
0x1800045d0  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800045d7  call    cs:__imp_CoCreateInstance
0x1800045dd  mov     ecx, eax; this
0x1800045df  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800045e4  mov     rdi, [rbp+57h+var_70]
0x1800045e8  mov     rax, [rdi]
0x1800045eb  mov     rbx, [rax+88h]
0x1800045f2  lea     r14, [rsi+68h]
0x1800045f6  mov     rcx, r14
0x1800045f9  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800045fe  mov     r8d, [rsi+14h]
0x180004602  mov     edx, [rsi+10h]
0x180004605  lea     rcx, [rbp+57h+var_60]
0x180004609  call    ?GetWICPixelFormat@MediaFrameHelpers@@SA?AU_GUID@@W4BitmapPixelFormat@Imaging@Graphics@Windows@@W4BitmapAlphaMode@456@@Z; MediaFrameHelpers::GetWICPixelFormat(Windows::Graphics::Imaging::BitmapPixelFormat,Windows::Graphics::Imaging::BitmapAlphaMode)
0x18000460e  movups  xmm0, xmmword ptr [rax]
0x180004611  movdqu  [rbp+57h+var_50], xmm0
0x180004616  mov     [rsp+0E0h+var_B8], r14
0x18000461b  mov     dword ptr [rsp+0E0h+ppBuffer], r15d
0x180004620  lea     r9, [rbp+57h+var_50]
0x180004624  mov     r8d, [rsi+1Ch]
0x180004628  mov     edx, [rsi+18h]
0x18000462b  mov     rcx, rdi
0x18000462e  mov     rax, rbx
0x180004631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004636  mov     ecx, eax; this
0x180004638  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000463d  mov     rcx, [r14]
0x180004640  mov     rax, [rcx]
0x180004643  movsd   xmm2, qword ptr [rsi+38h]
0x180004648  movsd   xmm1, qword ptr [rsi+30h]
0x18000464d  mov     rax, [rax+50h]
0x180004651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004656  mov     ecx, eax; this
0x180004658  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000465d  nop
0x18000465e  mov     rcx, [rbp+57h+var_70]
0x180004662  test    rcx, rcx
0x180004665  jz      short loc_18000467C
0x180004667  mov     [rbp+57h+var_70], 0
0x18000466f  mov     rax, [rcx]
0x180004672  mov     rax, [rax+10h]
0x180004676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467b  nop
0x18000467c  lea     r15, [rsi+58h]
0x180004680  jmp     loc_18000458D
0x180004685  lea     rdx, aInvalidFormat; "Invalid format"
0x18000468c  call    ??$ThrowOriginateError@$0P@@MF@@YAXJAEAY0P@$$CBG@Z; MF::ThrowOriginateError<15>(long,ushort const (&)[15])
0x180004692  mov     rbx, [r14]
0x180004695  xor     r11d, r11d
0x180004698  test    rbx, rbx
0x18000469b  setnz   r11b
0x18000469f  xor     r10d, r10d
0x1800046a2  cmp     [r15], r10
0x1800046a5  setnz   r10b
0x1800046a9  movups  xmm0, xmmword ptr [rsi+30h]
0x1800046ad  mov     eax, [rsi+1Ch]
0x1800046b0  mov     ecx, [rsi+18h]
0x1800046b3  mov     edx, [rsi+14h]
0x1800046b6  mov     r8d, [rsi+10h]
0x1800046ba  cmovnz  rbx, [r15]
0x1800046be  mov     [rsp+0E0h+var_80], r11d
0x1800046c3  mov     [rsp+0E0h+var_88], r10d
0x1800046c8  movups  [rsp+0E0h+var_98], xmm0
0x1800046cd  mov     [rsp+0E0h+var_A0], eax
0x1800046d1  mov     [rsp+0E0h+var_A8], ecx
0x1800046d5  mov     [rsp+0E0h+var_B0], edx
0x1800046d9  mov     dword ptr [rsp+0E0h+var_B8], r8d
0x1800046de  mov     [rsp+0E0h+ppBuffer], rbx
0x1800046e3  mov     r9, rsi
0x1800046e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046ed  mov     rcx, [rcx+10h]
0x1800046f1  call    WPP_SF_qqddddggdd
0x1800046f6  jmp     loc_18000459A
```
