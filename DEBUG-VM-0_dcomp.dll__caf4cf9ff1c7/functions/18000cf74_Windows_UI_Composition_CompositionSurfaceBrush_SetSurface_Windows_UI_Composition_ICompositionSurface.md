# Windows::UI::Composition::CompositionSurfaceBrush::SetSurface(Windows::UI::Composition::ICompositionSurface *)

- ea: `0x18000cf74`
- end: `0x18000d428`
- name: `?SetSurface@CompositionSurfaceBrush@Composition@UI@Windows@@QEAAJPEAUICompositionSurface@234@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CompositionSurfaceBrush *__hidden this, struct Windows::UI::Composition::ICompositionSurface *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000cf60`

## callees

- `0x1800093f4`
- `0x18000c420`
- `0x18000c924`
- `0x18000cf74`
- `0x18000d9a0`
- `0x180012da0`
- `0x18001358c`
- `0x180073388`
- `0x1800e77ac`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d01b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d01b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000d22a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000d22a`

## string_xrefs

- `0x18000d0d4`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionsurfacebrush.cpp`
- `0x18000d0ec`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionsurfacebrush.cpp`
- `0x18000d1d4`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionsurfacebrush.cpp`
- `0x18000d350`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionsurfacebrush.cpp`
- `0x18000d3d8`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionsurfacebrush.cpp`
- `0x18000d21e`: `The given object has already been closed / disposed and may no longer be used.`
- `0x18000d3c9`: `MipmapSurface is not supported as input for CompositionSurfaceBrush`
- `0x18000d0bc`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtsurfacebindpoint.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionSurfaceBrush::SetSurface(
        Windows::UI::Composition::CompositionSurfaceBrush *this,
        struct Windows::UI::Composition::ICompositionSurface *a2)
{
  struct Windows::UI::Composition::ICompositionSurface *v2; // rdi
  struct Windows::UI::Composition::ICompositionSurface *v3; // rsi
  unsigned int v6; // r13d
  int (__fastcall **v7)(struct Windows::UI::Composition::ICompositionSurface *, GUID *, __int64 *); // rax
  int (__fastcall *v8)(struct Windows::UI::Composition::ICompositionSurface *, GUID *, __int64 *); // rbx
  __int64 v9; // rcx
  int v10; // r14d
  __int64 v11; // rbx
  int v12; // ecx
  void (__fastcall **v13)(struct Windows::UI::Composition::ICompositionSurface *, GUID *, struct Windows::UI::Composition::ICompositionSurface **); // rax
  int v14; // eax
  struct IUnknown *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r14
  __int64 (__fastcall *v20)(__int64, struct Windows::UI::Composition::ICompositionSurface **); // rbx
  int v21; // eax
  struct Windows::UI::Composition::ICompositionSurface *v22; // rbx
  int (__fastcall *v23)(struct Windows::UI::Composition::ICompositionSurface *, GUID *, __int64 *); // r14
  __int64 v24; // rdx
  struct Windows::UI::Composition::ICompositionSurface *v25; // rcx
  __int64 v26; // rcx
  struct Windows::UI::Composition::ICompositionSurface *v27; // rcx
  __int64 v28; // rcx
  struct Windows::UI::Composition::ICompositionSurface *v29; // rcx
  __int64 v30; // rcx
  struct Windows::UI::Composition::ICompositionSurface *v31; // rcx
  Microsoft::WRL2::ContextSession *v32; // rcx
  int v33; // [rsp+20h] [rbp-10h]
  int v34; // [rsp+20h] [rbp-10h]
  int v35; // [rsp+20h] [rbp-10h]
  const char *v36; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  struct Windows::UI::Composition::ICompositionSurface *v38; // [rsp+70h] [rbp+40h] BYREF
  __int64 v39; // [rsp+78h] [rbp+48h] BYREF
  __int64 v40; // [rsp+80h] [rbp+50h] BYREF

  v2 = 0;
  v3 = 0;
  v6 = -2147024809;
  if ( !a2 )
  {
LABEL_6:
    v10 = 0;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)a2 + 8LL))(a2);
  v7 = *(int (__fastcall ***)(struct Windows::UI::Composition::ICompositionSurface *, GUID *, __int64 *))a2;
  v39 = 0;
  v8 = *v7;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v39);
  if ( v8(a2, &GUID_e01622c8_2332_55c7_8868_a7312c5c229d, &v39) < 0 )
  {
    v3 = a2;
LABEL_4:
    v9 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_6;
  }
  v19 = v39;
  v38 = 0;
  v20 = *(__int64 (__fastcall **)(__int64, struct Windows::UI::Composition::ICompositionSurface **))(*(_QWORD *)v39 + 48LL);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v38);
  v21 = v20(v19, &v38);
  v10 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39A,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionsurfacebrush.cpp",
      (const char *)(unsigned int)v21,
      v33);
    v29 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)a2 + 16LL))(a2);
  }
  else
  {
    v40 = 0;
    v22 = v38;
    v23 = **(int (__fastcall ***)(struct Windows::UI::Composition::ICompositionSurface *, GUID *, __int64 *))v38;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v40);
    if ( v23(v22, &GUID_e01622c8_2332_55c7_8868_a7312c5c229d, &v40) < 0 )
    {
      v24 = v40;
      v25 = 0;
      v3 = v38;
      v2 = a2;
      v38 = 0;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v25 = v38;
      }
      if ( v25 )
      {
        v38 = 0;
        (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v25 + 16LL))(v25);
      }
      goto LABEL_4;
    }
    v26 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)a2 + 16LL))(a2);
    v10 = -2147024809;
  }
LABEL_7:
  v11 = *((_QWORD *)this + 3);
  if ( *(_DWORD *)(v11 + 92) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v11 + 56) + 24LL));
  v12 = *(_DWORD *)(v11 + 64);
  if ( v12 != *(_DWORD *)(v11 + 68) + *(_DWORD *)(v11 + 72) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
  *(_DWORD *)(v11 + 64) = v12 + 1;
  if ( (*((_BYTE *)this + 48) & 2) == 0 )
  {
    v10 = -2147483629;
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
    v18 = 956;
    goto LABEL_35;
  }
  if ( v10 < 0 )
  {
    v18 = 959;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionsurfacebrush.cpp",
      (const char *)(unsigned int)v10,
      v33);
    Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v11);
    if ( v3 )
      (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v3 + 16LL))(v3);
    if ( v2 )
      (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v2 + 16LL))(v2);
    return (unsigned int)v10;
  }
  if ( v3 )
  {
    v13 = *(void (__fastcall ***)(struct Windows::UI::Composition::ICompositionSurface *, GUID *, struct Windows::UI::Composition::ICompositionSurface **))v3;
    v38 = 0;
    (*v13)(v3, &GUID_4863675c_cf4a_4b1c_9ece_c5ec0c2b2fe6, &v38);
    if ( v38 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionsurfacebrush.cpp",
        (const char *)0x80070057LL,
        (int)"MipmapSurface is not supported as input for CompositionSurfaceBrush",
        v36);
      v31 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      goto LABEL_19;
    }
  }
  if ( v3 != *((struct Windows::UI::Composition::ICompositionSurface **)this + 35) )
  {
    if ( *((_QWORD *)this + 35) )
      Windows::UI::Composition::SurfaceBindPoint::DetachSurface((Windows::UI::Composition::CompositionSurfaceBrush *)((char *)this + 256));
    if ( v3 )
    {
      v14 = Windows::UI::Composition::SurfaceBindPoint::AttachSurface(
              (Windows::UI::Composition::CompositionSurfaceBrush *)((char *)this + 256),
              v3);
      v6 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtsurfacebindpoint.cpp",
          (const char *)(unsigned int)v14,
          v33);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionsurfacebrush.cpp",
          (const char *)v6,
          v34);
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C1,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionsurfacebrush.cpp",
          (const char *)v6,
          v35);
        Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v11);
        (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v3 + 16LL))(v3);
        if ( v2 )
          (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v2 + 16LL))(v2);
        return v6;
      }
    }
  }
  v16 = (struct IUnknown *)*((_QWORD *)this + 37);
  if ( v16 )
  {
    v32 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 37) = 0;
    Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(v32, v16);
  }
  if ( *((struct Windows::UI::Composition::ICompositionSurface **)this + 37) != v2 )
  {
    if ( v2 )
      (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v2 + 8LL))(v2);
    v17 = *((_QWORD *)this + 37);
    *((_QWORD *)this + 37) = v2;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v11);
  if ( v3 )
    (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v2 )
    (*(void (__fastcall **)(struct Windows::UI::Composition::ICompositionSurface *))(*(_QWORD *)v2 + 16LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x18000cf74  mov     [rsp-38h+arg_18], rbx
0x18000cf79  push    rbp
0x18000cf7a  push    rsi
0x18000cf7b  push    rdi
0x18000cf7c  push    r12
0x18000cf7e  push    r13
0x18000cf80  push    r14
0x18000cf82  push    r15
0x18000cf84  mov     rbp, rsp
0x18000cf87  sub     rsp, 30h
0x18000cf8b  xor     edi, edi
0x18000cf8d  xor     esi, esi
0x18000cf8f  mov     r12, rdx
0x18000cf92  mov     r15, rcx
0x18000cf95  mov     r13d, 80070057h
0x18000cf9b  test    rdx, rdx
0x18000cf9e  jz      short loc_18000D001
0x18000cfa0  mov     rax, [rdx]
0x18000cfa3  mov     rcx, rdx
0x18000cfa6  mov     rax, [rax+8]
0x18000cfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfaf  mov     rax, [r12]
0x18000cfb3  lea     rcx, [rbp+arg_8]
0x18000cfb7  mov     [rbp+arg_8], rsi
0x18000cfbb  mov     rbx, [rax]
0x18000cfbe  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18000cfc3  lea     r8, [rbp+arg_8]
0x18000cfc7  mov     rcx, r12
0x18000cfca  lea     rdx, _GUID_e01622c8_2332_55c7_8868_a7312c5c229d
0x18000cfd1  mov     rax, rbx
0x18000cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfd9  test    eax, eax
0x18000cfdb  jns     loc_18000D237
0x18000cfe1  mov     rsi, r12
0x18000cfe4  mov     rcx, [rbp+arg_8]
0x18000cfe8  test    rcx, rcx
0x18000cfeb  jz      short loc_18000D001
0x18000cfed  mov     [rbp+arg_8], 0
0x18000cff5  mov     rax, [rcx]
0x18000cff8  mov     rax, [rax+10h]
0x18000cffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d001  xor     r14d, r14d
0x18000d004  mov     rbx, [r15+18h]
0x18000d008  mov     eax, [rbx+5Ch]
0x18000d00b  test    eax, eax
0x18000d00d  jnz     loc_18000D3B8
0x18000d013  mov     rcx, [rbx+38h]
0x18000d017  add     rcx, 18h; lpCriticalSection
0x18000d01b  call    cs:__imp_EnterCriticalSection
0x18000d021  mov     eax, [rbx+48h]
0x18000d024  add     eax, [rbx+44h]
0x18000d027  mov     ecx, [rbx+40h]
0x18000d02a  cmp     ecx, eax
0x18000d02c  jnz     loc_18000D3AB
0x18000d032  lea     eax, [rcx+1]
0x18000d035  mov     [rbx+40h], eax
0x18000d038  test    byte ptr [r15+30h], 2
0x18000d03d  jz      loc_18000D218
0x18000d043  test    r14d, r14d
0x18000d046  js      loc_18000D1CB
0x18000d04c  test    rsi, rsi
0x18000d04f  jz      short loc_18000D07D
0x18000d051  mov     rax, [rsi]
0x18000d054  lea     r8, [rbp+arg_0]
0x18000d058  lea     rdx, _GUID_4863675c_cf4a_4b1c_9ece_c5ec0c2b2fe6
0x18000d05f  mov     [rbp+arg_0], 0
0x18000d067  mov     rcx, rsi
0x18000d06a  mov     rax, [rax]
0x18000d06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d072  cmp     [rbp+arg_0], 0
0x18000d077  jnz     loc_18000D3C5
0x18000d07d  lea     r14, [r15+100h]
0x18000d084  cmp     rsi, [r14+18h]
0x18000d088  jz      loc_18000D135
0x18000d08e  cmp     qword ptr [r14+18h], 0
0x18000d093  jz      short loc_18000D09D
0x18000d095  mov     rcx, r14; this
0x18000d098  call    ?DetachSurface@SurfaceBindPoint@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::SurfaceBindPoint::DetachSurface(void)
0x18000d09d  test    rsi, rsi
0x18000d0a0  jz      loc_18000D135
0x18000d0a6  mov     rdx, rsi; struct Windows::UI::Composition::ICompositionSurface *
0x18000d0a9  mov     rcx, r14; this
0x18000d0ac  call    ?AttachSurface@SurfaceBindPoint@Composition@UI@Windows@@AEAAJPEAUICompositionSurface@234@@Z; Windows::UI::Composition::SurfaceBindPoint::AttachSurface(Windows::UI::Composition::ICompositionSurface *)
0x18000d0b1  mov     r13d, eax
0x18000d0b4  test    eax, eax
0x18000d0b6  jns     short loc_18000D135
0x18000d0b8  mov     rcx, [rbp+38h]; this
0x18000d0bc  lea     r8, aOnecoreuapWind_271; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18000d0c3  mov     r9d, eax; char *
0x18000d0c6  mov     edx, 0F7h; void *
0x18000d0cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0d0  mov     rcx, [rbp+38h]; this
0x18000d0d4  lea     r8, aOnecoreuapWind_277; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18000d0db  mov     r9d, r13d; char *
0x18000d0de  mov     edx, 0AAh; void *
0x18000d0e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0e8  mov     rcx, [rbp+38h]; this
0x18000d0ec  lea     r8, aOnecoreuapWind_277; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18000d0f3  mov     r9d, r13d; char *
0x18000d0f6  mov     edx, 3C1h; void *
0x18000d0fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d100  mov     rcx, rbx; this
0x18000d103  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x18000d108  test    rsi, rsi
0x18000d10b  jz      short loc_18000D11C
0x18000d10d  mov     rax, [rsi]
0x18000d110  mov     rcx, rsi
0x18000d113  mov     rax, [rax+10h]
0x18000d117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d11c  test    rdi, rdi
0x18000d11f  jz      short loc_18000D130
0x18000d121  mov     rcx, [rdi]
0x18000d124  mov     rax, [rcx+10h]
0x18000d128  mov     rcx, rdi
0x18000d12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d130  mov     eax, r13d
0x18000d133  jmp     short loc_18000D1B3
0x18000d135  mov     rdx, [r15+128h]; struct IUnknown *
0x18000d13c  test    rdx, rdx
0x18000d13f  jnz     loc_18000D40F
0x18000d145  cmp     [r15+128h], rdi
0x18000d14c  jz      short loc_18000D181
0x18000d14e  test    rdi, rdi
0x18000d151  jz      short loc_18000D162
0x18000d153  mov     rax, [rdi]
0x18000d156  mov     rcx, rdi
0x18000d159  mov     rax, [rax+8]
0x18000d15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d162  mov     rcx, [r15+128h]
0x18000d169  mov     [r15+128h], rdi
0x18000d170  test    rcx, rcx
0x18000d173  jz      short loc_18000D181
0x18000d175  mov     rax, [rcx]
0x18000d178  mov     rax, [rax+10h]
0x18000d17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d181  mov     rcx, rbx; this
0x18000d184  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x18000d189  test    rsi, rsi
0x18000d18c  jz      short loc_18000D19D
0x18000d18e  mov     rax, [rsi]
0x18000d191  mov     rcx, rsi
0x18000d194  mov     rax, [rax+10h]
0x18000d198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19d  test    rdi, rdi
0x18000d1a0  jz      short loc_18000D1B1
0x18000d1a2  mov     rax, [rdi]
0x18000d1a5  mov     rcx, rdi
0x18000d1a8  mov     rax, [rax+10h]
0x18000d1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1b1  xor     eax, eax
0x18000d1b3  mov     rbx, [rsp+30h+arg_18]
0x18000d1bb  add     rsp, 30h
0x18000d1bf  pop     r15
0x18000d1c1  pop     r14
0x18000d1c3  pop     r13
0x18000d1c5  pop     r12
0x18000d1c7  pop     rdi
0x18000d1c8  pop     rsi
0x18000d1c9  pop     rbp
0x18000d1ca  retn
0x18000d1cb  mov     edx, 3BFh; void *
0x18000d1d0  mov     rcx, [rbp+38h]; this
0x18000d1d4  lea     r8, aOnecoreuapWind_277; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18000d1db  mov     r9d, r14d; char *
0x18000d1de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d1e3  mov     rcx, rbx; this
0x18000d1e6  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x18000d1eb  test    rsi, rsi
0x18000d1ee  jz      short loc_18000D1FF
0x18000d1f0  mov     rax, [rsi]
0x18000d1f3  mov     rcx, rsi
0x18000d1f6  mov     rax, [rax+10h]
0x18000d1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ff  test    rdi, rdi
0x18000d202  jz      short loc_18000D213
0x18000d204  mov     rcx, [rdi]
0x18000d207  mov     rax, [rcx+10h]
0x18000d20b  mov     rcx, rdi
0x18000d20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d213  mov     eax, r14d
0x18000d216  jmp     short loc_18000D1B3
0x18000d218  mov     r14d, 80000013h
0x18000d21e  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18000d225  mov     ecx, r14d
0x18000d228  xor     edx, edx
0x18000d22a  call    cs:__imp_RoOriginateErrorW
0x18000d230  mov     edx, 3BCh
0x18000d235  jmp     short loc_18000D1D0
0x18000d237  mov     r14, [rbp+arg_8]
0x18000d23b  lea     rcx, [rbp+arg_0]
0x18000d23f  mov     [rbp+arg_0], rsi
0x18000d243  mov     rax, [r14]
0x18000d246  mov     rbx, [rax+30h]
0x18000d24a  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18000d24f  lea     rdx, [rbp+arg_0]
0x18000d253  mov     rcx, r14
0x18000d256  mov     rax, rbx
0x18000d259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d25e  xor     ebx, ebx
0x18000d260  mov     r14d, eax
0x18000d263  test    eax, eax
0x18000d265  js      loc_18000D34C
0x18000d26b  mov     [rbp+arg_10], rbx
0x18000d26f  lea     rcx, [rbp+arg_10]
0x18000d273  mov     rbx, [rbp+arg_0]
0x18000d277  mov     rax, [rbx]
0x18000d27a  mov     r14, [rax]
0x18000d27d  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18000d282  lea     r8, [rbp+arg_10]
0x18000d286  mov     rcx, rbx
0x18000d289  lea     rdx, _GUID_e01622c8_2332_55c7_8868_a7312c5c229d
0x18000d290  mov     rax, r14
0x18000d293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d298  xor     ebx, ebx
0x18000d29a  test    eax, eax
0x18000d29c  jns     short loc_18000D2E9
0x18000d29e  mov     rdx, [rbp+arg_10]
0x18000d2a2  mov     ecx, ebx
0x18000d2a4  mov     rsi, [rbp+arg_0]
0x18000d2a8  mov     rdi, r12
0x18000d2ab  mov     [rbp+arg_0], rbx
0x18000d2af  test    rdx, rdx
0x18000d2b2  jz      short loc_18000D2CB
0x18000d2b4  mov     [rbp+arg_10], rbx
0x18000d2b8  mov     rcx, rdx
0x18000d2bb  mov     rax, [rdx]
0x18000d2be  mov     rax, [rax+10h]
0x18000d2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2c7  mov     rcx, [rbp+arg_0]
0x18000d2cb  test    rcx, rcx
0x18000d2ce  jz      loc_18000CFE4
0x18000d2d4  mov     [rbp+arg_0], rbx
0x18000d2d8  mov     rax, [rcx]
0x18000d2db  mov     rax, [rax+10h]
0x18000d2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2e4  jmp     loc_18000CFE4
0x18000d2e9  mov     rcx, [rbp+arg_10]
0x18000d2ed  test    rcx, rcx
0x18000d2f0  jz      short loc_18000D302
0x18000d2f2  mov     [rbp+arg_10], rbx
0x18000d2f6  mov     rax, [rcx]
0x18000d2f9  mov     rax, [rax+10h]
0x18000d2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d302  mov     rcx, [rbp+arg_0]
0x18000d306  test    rcx, rcx
0x18000d309  jz      short loc_18000D31B
0x18000d30b  mov     [rbp+arg_0], rbx
0x18000d30f  mov     rax, [rcx]
0x18000d312  mov     rax, [rax+10h]
0x18000d316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d31b  mov     rcx, [rbp+arg_8]
0x18000d31f  test    rcx, rcx
0x18000d322  jz      short loc_18000D334
0x18000d324  mov     [rbp+arg_8], rbx
0x18000d328  mov     rax, [rcx]
0x18000d32b  mov     rax, [rax+10h]
0x18000d32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d334  mov     rax, [r12]
0x18000d338  mov     rcx, r12
0x18000d33b  mov     rax, [rax+10h]
0x18000d33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d344  mov     r14d, r13d
0x18000d347  jmp     loc_18000D004
0x18000d34c  mov     rcx, [rbp+38h]; this
0x18000d350  lea     r8, aOnecoreuapWind_277; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18000d357  mov     r9d, eax; char *
0x18000d35a  mov     edx, 39Ah; void *
0x18000d35f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d364  mov     rcx, [rbp+arg_0]
0x18000d368  test    rcx, rcx
0x18000d36b  jz      short loc_18000D37D
0x18000d36d  mov     [rbp+arg_0], rbx
0x18000d371  mov     rax, [rcx]
0x18000d374  mov     rax, [rax+10h]
0x18000d378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37d  mov     rcx, [rbp+arg_8]
0x18000d381  test    rcx, rcx
0x18000d384  jz      short loc_18000D396
0x18000d386  mov     [rbp+arg_8], rbx
0x18000d38a  mov     rax, [rcx]
0x18000d38d  mov     rax, [rax+10h]
0x18000d391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d396  mov     rax, [r12]
0x18000d39a  mov     rcx, r12
0x18000d39d  mov     rax, [rax+10h]
0x18000d3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a6  jmp     loc_18000D004
0x18000d3ab  lea     rcx, aContextsession; "ContextSession begin counts"
0x18000d3b2  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x18000d3b8  lea     rcx, aContextsession_0; "ContextSession RIP"
0x18000d3bf  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x18000d3c5  mov     rcx, [rbp+38h]; this
0x18000d3c9  lea     rax, aMipmapsurfaceI; "MipmapSurface is not supported as input"...
0x18000d3d0  mov     r9d, r13d; char *
0x18000d3d3  mov     qword ptr [rsp+30h+var_10], rax; int
0x18000d3d8  lea     r8, aOnecoreuapWind_277; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18000d3df  mov     edx, 0A7h; void *
0x18000d3e4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000d3e9  mov     rcx, [rbp+arg_0]
0x18000d3ed  test    rcx, rcx
  ... truncated ...
```
