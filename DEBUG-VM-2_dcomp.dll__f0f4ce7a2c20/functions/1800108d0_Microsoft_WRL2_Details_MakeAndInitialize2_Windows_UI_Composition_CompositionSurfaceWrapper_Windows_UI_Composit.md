# Microsoft::WRL2::Details::MakeAndInitialize2<Windows::UI::Composition::CompositionSurfaceWrapper,Windows::UI::Composition::CompositionSurfaceWrapper,Windows::UI::Composition::Compositor *,IDCompositionSurface * &>(Windows::UI::Composition::CompositionSurfaceWrapper * *,Windows::UI::Composition::Compositor * &&,IDCompositionSurface * &)

- ea: `0x1800108d0`
- end: `0x180010c8d`
- name: `??$MakeAndInitialize2@VCompositionSurfaceWrapper@Composition@UI@Windows@@V1234@PEAVCompositor@234@AEAPEAUIDCompositionSurface@@@Details@WRL2@Microsoft@@YAJPEAPEAVCompositionSurfaceWrapper@Composition@UI@Windows@@$$QEAPEAVCompositor@456@AEAPEAUIDCompositionSurface@@@Z`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180010760`

## callees

- `0x18000f810`
- `0x18000fe80`
- `0x1800108d0`
- `0x180010c94`
- `0x180010fc0`
- `0x180012da0`
- `0x18001358c`
- `0x180036f90`
- `0x180039590`
- `0x1800395e4`
- `0x1800a4dd4`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010906`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010906`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800108f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800109c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800109c2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010a08`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180010a08`

## string_xrefs

- `0x1800109fa`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180010b99`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x180010bb2`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionsurfacewrapper.cpp`
- `0x180010bda`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionsurfacewrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL2::Details::MakeAndInitialize2<Windows::UI::Composition::CompositionSurfaceWrapper,Windows::UI::Composition::CompositionSurfaceWrapper,Windows::UI::Composition::Compositor *,IDCompositionSurface * &>(
        Windows::UI::Composition::CompositionObject **a1,
        Windows::UI::Composition::CompositorCommon **a2,
        __int64 *a3)
{
  HANDLE ProcessHeap; // rax
  void *v7; // rax
  Windows::UI::Composition::CompositionObject *v8; // rax
  Windows::UI::Composition::CompositionObject *v9; // rdi
  Windows::UI::Composition::CompositorCommon *v10; // rsi
  __int64 (__fastcall ***v11)(__int64, GUID *, __int64 *); // r14
  int v12; // ebx
  Microsoft::WRL2::ContextSession *v13; // rcx
  Windows::UI::Composition::CompositorCommon **v14; // r8
  char v16; // al
  int v17; // eax
  unsigned int v18; // ebx
  __int64 (__fastcall **v19)(__int64, GUID *, __int64 *); // rax
  __int64 v20; // rbx
  int v21; // esi
  bool v22; // zf
  __int64 v23; // rcx
  Windows::UI::Composition::SurfaceBindPoint **v24; // rsi
  Windows::UI::Composition::SurfaceBindPoint **i; // rbx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // [rsp+20h] [rbp-28h]
  int v30; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v32; // [rsp+50h] [rbp+8h] BYREF
  __int64 v33; // [rsp+68h] [rbp+20h] BYREF

  *a1 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, 0xD0u);
  if ( !v7 )
    return 2147942414LL;
  v8 = (Windows::UI::Composition::CompositionObject *)memset_0(v7, 0, 0xD0u);
  v9 = v8;
  if ( v8 )
  {
    Windows::UI::Composition::CompositionObject::CompositionObject(v8);
    *((_QWORD *)v9 + 18) = 0;
    *((_QWORD *)v9 + 19) = 0;
    *((_QWORD *)v9 + 20) = 0;
    *(_QWORD *)v9 = &Windows::UI::Composition::CompositionSurfaceWrapper::`vftable';
    Windows::UI::Composition::CompositionSurfaceWrapper::Api::Api((Windows::UI::Composition::CompositionObject *)((char *)v9 + 168));
    Windows::UI::Composition::CompositionSurfaceWrapper::Partner::Partner((Windows::UI::Composition::CompositionObject *)((char *)v9 + 184));
    *((_QWORD *)v9 + 25) = 0;
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)v9 + 1) = &Windows::UI::Composition::CompositionSurfaceWrapper::s_InterfaceType;
  v10 = *a2;
  v11 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 *))*a3;
  *((_QWORD *)v9 + 3) = v10;
  if ( v10 != v9 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)v10 + 4) == 1 )
      (*(void (__fastcall **)(Windows::UI::Composition::CompositorCommon *))(*(_QWORD *)v10 + 80LL))(v10);
    v12 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 3) + 56LL) + 40LL);
    if ( v12 == GetCurrentThreadId() )
    {
      v13 = 0;
    }
    else
    {
      Microsoft::WRL2::ContextSession::BeginApiEntry(*((Microsoft::WRL2::ContextSession **)v10 + 3));
      v13 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)v10 + 3);
      if ( (*((_BYTE *)v10 + 48) & 2) == 0 )
      {
        Microsoft::WRL2::ContextSession::EndApiEntry(v13);
        RoOriginateErrorW(
          2147483667LL,
          0,
          L"The given object has already been closed / disposed and may no longer be used.");
        goto LABEL_16;
      }
    }
    v14 = (Windows::UI::Composition::CompositorCommon **)*((_QWORD *)v10 + 5);
    if ( *v14 != (Windows::UI::Composition::CompositorCommon *)((char *)v10 + 32) )
      __fastfail(3u);
    *((_QWORD *)v9 + 4) = (char *)v10 + 32;
    *((_QWORD *)v9 + 5) = v14;
    *v14 = (Windows::UI::Composition::CompositionObject *)((char *)v9 + 32);
    *((_QWORD *)v10 + 5) = (char *)v9 + 32;
    if ( v13 )
      Microsoft::WRL2::ContextSession::EndApiEntry(v13);
  }
LABEL_16:
  v16 = *((_BYTE *)v9 + 49);
  *((_BYTE *)v9 + 48) = 31;
  *((_BYTE *)v9 + 49) ^= (*((_BYTE *)v10 + 49) ^ v16) & 1;
  v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, Windows::UI::Composition::CompositionObject *, __int64))(**(_QWORD **)(*((_QWORD *)v10 + 51) + 32LL) + 24LL))(
          *(_QWORD *)(*((_QWORD *)v10 + 51) + 32LL),
          *(unsigned int *)(*((_QWORD *)v10 + 51) + 64LL),
          v9,
          (__int64)v9 + 136);
  v18 = v17;
  if ( v17 >= 0 )
  {
    Windows::UI::Composition::CompositorCommon::MarkDirty(v10);
    *((_DWORD *)v9 + 35) |= 1u;
    if ( !v11 )
    {
LABEL_32:
      *a1 = v9;
      return 0;
    }
    Windows::UI::Composition::CompositionSurfaceWrapper::ClearDCompSurface(v9);
    v19 = *v11;
    v20 = 0;
    v32 = 0;
    v33 = 0;
    v21 = (*v19)((__int64)v11, &GUID_c9f54a6b_06fb_4465_9edc_590cacccb47a, &v33);
    if ( v21 >= 0 )
      v20 = v33;
    if ( v33 )
    {
      (*(void (**)(void))(*(_QWORD *)v33 + 16LL))();
      v33 = 0;
    }
    if ( v21 < 0 )
    {
      if ( (int)(**v11)((__int64)v11, &GUID_ae471c51_5f53_4a24_8d3e_d0c39c30b3f0, &v32) < 0 )
      {
LABEL_35:
        v18 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionsurfacewrapper.cpp",
          (const char *)0x80070057LL,
          v29);
        v28 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v27 = 52;
        goto LABEL_34;
      }
      v22 = *(_QWORD *)(*((_QWORD *)v9 + 3) + 440LL) == *(_QWORD *)(*(_QWORD *)(v32 + 104) + 24LL);
    }
    else
    {
      v22 = *(_QWORD *)(*((_QWORD *)v9 + 3) + 440LL) == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 40) + 24LL) + 24LL);
    }
    if ( v22 )
    {
      if ( *((__int64 (__fastcall ****)(__int64, GUID *, __int64 *))v9 + 25) != v11 )
      {
        ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v11)[1])(v11);
        v23 = *((_QWORD *)v9 + 25);
        *((_QWORD *)v9 + 25) = v11;
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = (Windows::UI::Composition::SurfaceBindPoint **)*((_QWORD *)v9 + 19);
      for ( i = (Windows::UI::Composition::SurfaceBindPoint **)*((_QWORD *)v9 + 18); i != v24; ++i )
        Windows::UI::Composition::SurfaceBindPoint::NotifyUnderlyingContentChange(*i);
      v26 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      goto LABEL_32;
    }
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x55,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
    (const char *)(unsigned int)v17,
    v29);
  v27 = 48;
LABEL_34:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionsurfacewrapper.cpp",
    (const char *)v18,
    v30);
  Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v9);
  return v18;
}

```

## disassembly

```asm
0x1800108d0  mov     [rsp+arg_8], rbx
0x1800108d5  mov     [rsp+arg_10], rsi
0x1800108da  push    rdi
0x1800108db  push    r14
0x1800108dd  push    r15
0x1800108df  sub     rsp, 30h
0x1800108e3  mov     r14, r8
0x1800108e6  mov     qword ptr [rcx], 0
0x1800108ed  mov     rsi, rdx
0x1800108f0  mov     r15, rcx
0x1800108f3  call    cs:__imp_GetProcessHeap
0x1800108f9  mov     ebx, 0D0h
0x1800108fe  xor     edx, edx; dwFlags
0x180010900  mov     rcx, rax; hHeap
0x180010903  mov     r8d, ebx; dwBytes
0x180010906  call    cs:__imp_HeapAlloc
0x18001090c  test    rax, rax
0x18001090f  jz      loc_180010A10
0x180010915  mov     r8d, ebx; Size
0x180010918  xor     edx, edx; Val
0x18001091a  mov     rcx, rax; void *
0x18001091d  call    memset_0
0x180010922  mov     rdi, rax
0x180010925  test    rax, rax
0x180010928  jz      loc_180010C86
0x18001092e  mov     rcx, rax; this
0x180010931  call    ??0CompositionObject@Composition@UI@Windows@@IEAA@XZ; Windows::UI::Composition::CompositionObject::CompositionObject(void)
0x180010936  lea     rax, ??_7CompositionSurfaceWrapper@Composition@UI@Windows@@6B@; const Windows::UI::Composition::CompositionSurfaceWrapper::`vftable'
0x18001093d  mov     qword ptr [rdi+90h], 0
0x180010948  mov     qword ptr [rdi+98h], 0
0x180010953  lea     rcx, [rdi+0A8h]; this
0x18001095a  mov     qword ptr [rdi+0A0h], 0
0x180010965  mov     [rdi], rax
0x180010968  call    ??0Api@CompositionSurfaceWrapper@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::CompositionSurfaceWrapper::Api::Api(void)
0x18001096d  lea     rcx, [rdi+0B8h]; this
0x180010974  call    ??0Partner@CompositionSurfaceWrapper@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::CompositionSurfaceWrapper::Partner::Partner(void)
0x180010979  mov     qword ptr [rdi+0C8h], 0
0x180010984  lea     rax, ?s_InterfaceType@CompositionSurfaceWrapper@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::CompositionSurfaceWrapper::s_InterfaceType
0x18001098b  mov     [rdi+8], rax
0x18001098f  mov     rsi, [rsi]
0x180010992  mov     r14, [r14]
0x180010995  mov     [rdi+18h], rsi
0x180010999  cmp     rsi, rdi
0x18001099c  jz      loc_180010A35
0x1800109a2  mov     eax, 1
0x1800109a7  lock xadd [rsi+10h], eax
0x1800109ac  inc     eax
0x1800109ae  cmp     eax, 1
0x1800109b1  jz      loc_180010C68
0x1800109b7  mov     rax, [rsi+18h]
0x1800109bb  mov     rcx, [rax+38h]
0x1800109bf  mov     ebx, [rcx+28h]
0x1800109c2  call    cs:__imp_GetCurrentThreadId
0x1800109c8  cmp     ebx, eax
0x1800109ca  jnz     short loc_1800109E2
0x1800109cc  xor     ecx, ecx; this
0x1800109ce  lea     rdx, [rsi+20h]
0x1800109d2  mov     r8, [rdx+8]
0x1800109d6  cmp     [r8], rdx
0x1800109d9  jz      short loc_180010A1A
0x1800109db  mov     ecx, 3
0x1800109e0  int     29h; Win8: RtlFailFast(ecx)
0x1800109e2  mov     rcx, [rsi+18h]; this
0x1800109e6  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x1800109eb  test    byte ptr [rsi+30h], 2
0x1800109ef  mov     rcx, [rsi+18h]; this
0x1800109f3  jnz     short loc_1800109CE
0x1800109f5  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1800109fa  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180010a01  xor     edx, edx
0x180010a03  mov     ecx, 80000013h
0x180010a08  call    cs:__imp_RoOriginateErrorW
0x180010a0e  jmp     short loc_180010A35
0x180010a10  mov     eax, 8007000Eh
0x180010a15  jmp     loc_180010B80
0x180010a1a  lea     rax, [rdi+20h]
0x180010a1e  mov     [rax], rdx
0x180010a21  mov     [rax+8], r8
0x180010a25  mov     [r8], rax
0x180010a28  mov     [rdx+8], rax
0x180010a2c  test    rcx, rcx
0x180010a2f  jnz     loc_180010C7C
0x180010a35  mov     al, [rdi+31h]
0x180010a38  lea     r9, [rdi+88h]
0x180010a3f  mov     byte ptr [rdi+30h], 1Fh
0x180010a43  mov     r8, rdi
0x180010a46  xor     al, [rsi+31h]
0x180010a49  and     al, 1
0x180010a4b  xor     [rdi+31h], al
0x180010a4e  mov     rdx, [rsi+198h]
0x180010a55  mov     rcx, [rdx+20h]
0x180010a59  mov     edx, [rdx+40h]
0x180010a5c  mov     rax, [rcx]
0x180010a5f  mov     rax, [rax+18h]
0x180010a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a68  mov     ebx, eax
0x180010a6a  test    eax, eax
0x180010a6c  js      loc_180010B94
0x180010a72  mov     rcx, rsi; this
0x180010a75  call    ?MarkDirty@CompositorCommon@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositorCommon::MarkDirty(void)
0x180010a7a  or      dword ptr [rdi+8Ch], 1
0x180010a81  test    r14, r14
0x180010a84  jz      loc_180010B7B
0x180010a8a  mov     rcx, rdi; this
0x180010a8d  call    ?ClearDCompSurface@CompositionSurfaceWrapper@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::CompositionSurfaceWrapper::ClearDCompSurface(void)
0x180010a92  mov     rax, [r14]
0x180010a95  lea     r8, [rsp+48h+arg_18]
0x180010a9a  xor     ebx, ebx
0x180010a9c  mov     [rsp+48h+arg_0], 0
0x180010aa5  lea     rdx, _GUID_c9f54a6b_06fb_4465_9edc_590cacccb47a
0x180010aac  mov     [rsp+48h+arg_18], rbx
0x180010ab1  mov     rcx, r14
0x180010ab4  mov     rax, [rax]
0x180010ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010abc  mov     rcx, [rsp+48h+arg_18]
0x180010ac1  test    eax, eax
0x180010ac3  mov     esi, eax
0x180010ac5  cmovns  rbx, rcx
0x180010ac9  test    rcx, rcx
0x180010acc  jz      short loc_180010AE3
0x180010ace  mov     rdx, [rcx]
0x180010ad1  mov     rax, [rdx+10h]
0x180010ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ada  mov     [rsp+48h+arg_18], 0
0x180010ae3  xor     eax, eax
0x180010ae5  test    esi, esi
0x180010ae7  cmovs   rbx, rax
0x180010aeb  js      loc_180010C2D
0x180010af1  mov     rax, [rdi+18h]
0x180010af5  mov     rdx, [rax+1B8h]
0x180010afc  mov     rax, [rbx+28h]
0x180010b00  mov     rcx, [rax+18h]
0x180010b04  cmp     rdx, [rcx+18h]
0x180010b08  jnz     loc_180010BD5
0x180010b0e  cmp     [rdi+0C8h], r14
0x180010b15  jz      short loc_180010B45
0x180010b17  mov     rax, [r14]
0x180010b1a  mov     rcx, r14
0x180010b1d  mov     rax, [rax+8]
0x180010b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b26  mov     rcx, [rdi+0C8h]
0x180010b2d  mov     [rdi+0C8h], r14
0x180010b34  test    rcx, rcx
0x180010b37  jz      short loc_180010B45
0x180010b39  mov     rax, [rcx]
0x180010b3c  mov     rax, [rax+10h]
0x180010b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b45  mov     rsi, [rdi+98h]
0x180010b4c  mov     rbx, [rdi+90h]
0x180010b53  cmp     rbx, rsi
0x180010b56  jnz     loc_180010C1C
0x180010b5c  mov     rcx, [rsp+48h+arg_0]
0x180010b61  test    rcx, rcx
0x180010b64  jz      short loc_180010B7B
0x180010b66  mov     [rsp+48h+arg_0], 0
0x180010b6f  mov     rax, [rcx]
0x180010b72  mov     rax, [rax+10h]
0x180010b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b7b  mov     [r15], rdi
0x180010b7e  xor     eax, eax
0x180010b80  mov     rbx, [rsp+48h+arg_8]
0x180010b85  mov     rsi, [rsp+48h+arg_10]
0x180010b8a  add     rsp, 30h
0x180010b8e  pop     r15
0x180010b90  pop     r14
0x180010b92  pop     rdi
0x180010b93  retn
0x180010b94  mov     rcx, [rsp+48h]; this
0x180010b99  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180010ba0  mov     r9d, ebx; char *
0x180010ba3  mov     edx, 55h ; 'U'; void *
0x180010ba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bad  mov     edx, 30h ; '0'; void *
0x180010bb2  lea     rsi, aOnecoreuapWind_66; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180010bb9  mov     rcx, [rsp+48h]; this
0x180010bbe  mov     r9d, ebx; char *
0x180010bc1  mov     r8, rsi; unsigned int
0x180010bc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bc9  mov     rcx, rdi; this
0x180010bcc  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180010bd1  mov     eax, ebx
0x180010bd3  jmp     short loc_180010B80
0x180010bd5  mov     rcx, [rsp+48h]; this
0x180010bda  lea     rsi, aOnecoreuapWind_66; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180010be1  mov     ebx, 80070057h
0x180010be6  mov     r8, rsi; unsigned int
0x180010be9  mov     r9d, ebx; char *
0x180010bec  mov     edx, 8Eh; void *
0x180010bf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bf6  mov     rcx, [rsp+48h+arg_0]
0x180010bfb  test    rcx, rcx
0x180010bfe  jz      short loc_180010C15
0x180010c00  mov     [rsp+48h+arg_0], 0
0x180010c09  mov     rax, [rcx]
0x180010c0c  mov     rax, [rax+10h]
0x180010c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c15  mov     edx, 34h ; '4'
0x180010c1a  jmp     short loc_180010BB9
0x180010c1c  mov     rcx, [rbx]; this
0x180010c1f  call    ?NotifyUnderlyingContentChange@SurfaceBindPoint@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::SurfaceBindPoint::NotifyUnderlyingContentChange(void)
0x180010c24  add     rbx, 8
0x180010c28  jmp     loc_180010B53
0x180010c2d  mov     rax, [r14]
0x180010c30  lea     r8, [rsp+48h+arg_0]
0x180010c35  lea     rdx, _GUID_ae471c51_5f53_4a24_8d3e_d0c39c30b3f0
0x180010c3c  mov     rcx, r14
0x180010c3f  mov     rax, [rax]
0x180010c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c47  test    eax, eax
0x180010c49  js      short loc_180010BD5
0x180010c4b  mov     rax, [rsp+48h+arg_0]
0x180010c50  mov     rcx, [rdi+18h]
0x180010c54  mov     rax, [rax+68h]
0x180010c58  mov     rax, [rax+18h]
0x180010c5c  cmp     [rcx+1B8h], rax
0x180010c63  jmp     loc_180010B08
0x180010c68  mov     rax, [rsi]
0x180010c6b  mov     rcx, rsi
0x180010c6e  mov     rax, [rax+50h]
0x180010c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c77  jmp     loc_1800109B7
0x180010c7c  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180010c81  jmp     loc_180010A35
0x180010c86  xor     edi, edi
0x180010c88  jmp     loc_180010984
```
