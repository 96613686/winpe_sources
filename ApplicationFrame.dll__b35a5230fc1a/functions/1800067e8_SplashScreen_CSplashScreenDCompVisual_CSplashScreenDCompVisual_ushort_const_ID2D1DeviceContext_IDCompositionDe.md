# SplashScreen::CSplashScreenDCompVisual::CSplashScreenDCompVisual(ushort const *,ID2D1DeviceContext *,IDCompositionDevice *,std::shared_ptr<SplashScreen::CSplashScreenConfiguration> const &,std::shared_ptr<SplashScreen::CBasicSplashScreenLayout> const &)

- ea: `0x1800067e8`
- end: `0x180006922`
- name: `??0CSplashScreenDCompVisual@SplashScreen@@QEAA@PEBGPEAUID2D1DeviceContext@@PEAUIDCompositionDevice@@AEBV?$shared_ptr@VCSplashScreenConfiguration@SplashScreen@@@std@@AEBV?$shared_ptr@VCBasicSplashScreenLayout@SplashScreen@@@5@@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800547b4`

## callees

- `0x1800067e8`
- `0x180007010`
- `0x180007034`
- `0x180042bd4`
- `0x18004bb84`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800068e1`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800068e1`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x1800068ce`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x1800068ce`

## string_xrefs

- `0x180006904`: `shellcommondesktopbase\splashscreen\splashscreendcompvisual.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall SplashScreen::CSplashScreenDCompVisual::CSplashScreenDCompVisual(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v9 = std::_WChar_traits<unsigned short>::length(a2);
  std::wstring::_Construct<1,unsigned short const *>(a1, v10, v9);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  *(_QWORD *)(a1 + 48) = a4;
  if ( a4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v11 = a5[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 88) = *a5;
  *(_QWORD *)(a1 + 96) = a5[1];
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  v12 = a6[1];
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  *(_QWORD *)(a1 + 104) = *a6;
  *(_QWORD *)(a1 + 112) = a6[1];
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_DWORD *)(a1 + 152) = SHTaskPoolGetUniqueContext();
  InitializeSRWLock((PSRWLOCK)(a1 + 160));
  v13 = ImageLoaders::CDCompVisualImageLoader::Initialize(
          (ImageLoaders::CDCompVisualImageLoader *)(a1 + 120),
          *(struct ID2D1DeviceContext **)(a1 + 40),
          *(struct IDCompositionDevice **)(a1 + 48));
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"shellcommondesktopbase\\splashscreen\\splashscreendcompvisual.cpp",
      (const char *)(unsigned int)v13,
      v15);
  return a1;
}

```

## disassembly

```asm
0x1800067e8  mov     [rsp+arg_0], rcx
0x1800067ed  push    rbx
0x1800067ee  push    rbp
0x1800067ef  push    rsi
0x1800067f0  push    rdi
0x1800067f1  sub     rsp, 28h
0x1800067f5  mov     rbx, r9
0x1800067f8  mov     rsi, r8
0x1800067fb  mov     rdi, rcx
0x1800067fe  xorps   xmm0, xmm0
0x180006801  movups  xmmword ptr [rcx], xmm0
0x180006804  xor     ebp, ebp
0x180006806  mov     [rcx+10h], rbp
0x18000680a  mov     [rcx+18h], rbp
0x18000680e  mov     rcx, rdx
0x180006811  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006816  mov     r8, rax
0x180006819  mov     rcx, rdi
0x18000681c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180006821  nop
0x180006822  xor     eax, eax
0x180006824  mov     [rdi+20h], rax
0x180006828  mov     [rdi+28h], rsi
0x18000682c  test    rsi, rsi
0x18000682f  jz      short loc_180006841
0x180006831  mov     rax, [rsi]
0x180006834  mov     rcx, rsi
0x180006837  mov     rax, [rax+8]
0x18000683b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006840  nop
0x180006841  mov     [rdi+30h], rbx
0x180006845  test    rbx, rbx
0x180006848  jz      short loc_18000685A
0x18000684a  mov     rax, [rbx]
0x18000684d  mov     rcx, rbx
0x180006850  mov     rax, [rax+8]
0x180006854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006859  nop
0x18000685a  mov     [rdi+38h], rbp
0x18000685e  mov     [rdi+40h], rbp
0x180006862  mov     [rdi+48h], rbp
0x180006866  mov     [rdi+50h], rbp
0x18000686a  mov     [rdi+58h], rbp
0x18000686e  mov     [rdi+60h], rbp
0x180006872  mov     rcx, [rsp+48h+arg_20]
0x180006877  mov     rax, [rcx+8]
0x18000687b  test    rax, rax
0x18000687e  jz      short loc_180006884
0x180006880  lock inc dword ptr [rax+8]
0x180006884  mov     rax, [rcx]
0x180006887  mov     [rdi+58h], rax
0x18000688b  mov     rax, [rcx+8]
0x18000688f  mov     [rdi+60h], rax
0x180006893  mov     [rdi+68h], rbp
0x180006897  mov     [rdi+70h], rbp
0x18000689b  mov     rcx, [rsp+48h+arg_28]
0x1800068a0  mov     rax, [rcx+8]
0x1800068a4  test    rax, rax
0x1800068a7  jz      short loc_1800068AD
0x1800068a9  lock inc dword ptr [rax+8]
0x1800068ad  mov     rax, [rcx]
0x1800068b0  mov     [rdi+68h], rax
0x1800068b4  mov     rax, [rcx+8]
0x1800068b8  mov     [rdi+70h], rax
0x1800068bc  mov     [rdi+78h], rbp
0x1800068c0  mov     [rdi+80h], rbp
0x1800068c7  mov     [rdi+88h], rbp
0x1800068ce  call    cs:__imp_SHTaskPoolGetUniqueContext
0x1800068d4  mov     [rdi+98h], eax
0x1800068da  lea     rcx, [rdi+0A0h]; SRWLock
0x1800068e1  call    cs:__imp_InitializeSRWLock
0x1800068e7  mov     r8, [rdi+30h]; struct IDCompositionDevice *
0x1800068eb  mov     rdx, [rdi+28h]; struct ID2D1DeviceContext *
0x1800068ef  lea     rcx, [rdi+78h]; this
0x1800068f3  call    ?Initialize@CDCompVisualImageLoader@ImageLoaders@@QEAAJPEAUID2D1DeviceContext@@PEAUIDCompositionDevice@@@Z; ImageLoaders::CDCompVisualImageLoader::Initialize(ID2D1DeviceContext *,IDCompositionDevice *)
0x1800068f8  mov     rcx, [rsp+48h]; this
0x1800068fd  test    eax, eax
0x1800068ff  jns     short loc_180006916
0x180006901  mov     r9d, eax; char *
0x180006904  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\splashscreen\\s"...
0x18000690b  mov     edx, 25h ; '%'; void *
0x180006910  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006916  mov     rax, rdi
0x180006919  add     rsp, 28h
0x18000691d  pop     rdi
0x18000691e  pop     rsi
0x18000691f  pop     rbp
0x180006920  pop     rbx
0x180006921  retn
```
