# Microsoft::WRL::Details::Make<CTitleBarAcc,CTitleBar *,HWND__ * &,TitleBarAccFlags,TitleBarPart,TITLE_BAR_BUTTONS &>(CTitleBar * &&,HWND__ * &,TitleBarAccFlags &&,TitleBarPart &&,TITLE_BAR_BUTTONS &)

- ea: `0x180020cb4`
- end: `0x180020f77`
- name: `??$Make@VCTitleBarAcc@@PEAVCTitleBar@@AEAPEAUHWND__@@W4TitleBarAccFlags@@W4TitleBarPart@@AEAW4TITLE_BAR_BUTTONS@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCTitleBarAcc@@@12@$$QEAPEAVCTitleBar@@AEAPEAUHWND__@@$$QEAW4TitleBarAccFlags@@$$QEAW4TitleBarPart@@AEAW4TITLE_BAR_BUTTONS@@@Z`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002c164`

## callees

- `0x180003e30`
- `0x180004c98`
- `0x18001e4e8`
- `0x18001e930`
- `0x18001feb0`
- `0x180020cb4`
- `0x18002d560`
- `0x180043c30`
- `0x18004457c`
- `0x180046b0c`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020eb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020eb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020f14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f53`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
char **__fastcall Microsoft::WRL::Details::Make<CTitleBarAcc,CTitleBar *,HWND__ * &,enum TitleBarAccFlags,enum TitleBarPart,enum TITLE_BAR_BUTTONS &>(
        char **a1,
        _QWORD *a2,
        __int64 *a3,
        int *a4,
        int *a5,
        int *a6)
{
  char *v10; // rax
  char *v11; // rbx
  int v13; // r15d
  int v14; // r13d
  int v15; // r14d
  __int64 v16; // rdi
  __int64 v17; // rsi
  __int64 *v18; // rcx
  __int64 v19; // rax
  const unsigned __int16 *v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rcx
  LPVOID pv; // [rsp+28h] [rbp-71h] BYREF
  __int64 v24; // [rsp+30h] [rbp-69h]
  __int64 v25; // [rsp+38h] [rbp-61h]
  __int64 v26; // [rsp+40h] [rbp-59h] BYREF
  __int64 v27; // [rsp+48h] [rbp-51h] BYREF
  int v28; // [rsp+50h] [rbp-49h]
  int v29; // [rsp+54h] [rbp-45h]
  __int128 *v30; // [rsp+58h] [rbp-41h]
  const unsigned __int16 *v31; // [rsp+60h] [rbp-39h]
  char **v32; // [rsp+68h] [rbp-31h]
  char *v33; // [rsp+70h] [rbp-29h]
  char *v34; // [rsp+78h] [rbp-21h]
  char *v35; // [rsp+80h] [rbp-19h]
  __int128 v36; // [rsp+88h] [rbp-11h] BYREF

  v32 = a1;
  *a1 = 0;
  v10 = (char *)operator new(0x118u, (const struct std::nothrow_t *)std::nothrow);
  v11 = v10;
  v33 = v10;
  v34 = v10;
  if ( v10 )
  {
    v35 = v10;
    v13 = *a6;
    v14 = *a5;
    v15 = *a4;
    v16 = *a3;
    v17 = (*a2 + 56LL) & -(__int64)(*a2 != 0);
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>(v10);
    *(_QWORD *)v11 = &CTitleBarAcc::`vftable';
    *((_QWORD *)v11 + 1) = &CTitleBarAcc::`vftable'{for `IRawElementProviderFragment'};
    *((_QWORD *)v11 + 2) = &CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccElementInternal>'};
    *((_QWORD *)v11 + 17) = &CTitleBarAcc::`vftable'{for `IApplicationFrameTitleBarAccInternal'};
    *((_QWORD *)v11 + 18) = &CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>'};
    *((_QWORD *)v11 + 19) = &CTitleBarAcc::`vftable'{for `IValueProvider'};
    *((_QWORD *)v11 + 20) = &CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRawElementProviderFragmentRoot>'};
    *((_QWORD *)v11 + 22) = 0;
    *((_QWORD *)v11 + 23) = v16;
    *((_QWORD *)v11 + 24) = 0;
    *((_QWORD *)v11 + 25) = 0;
    *((_QWORD *)v11 + 26) = 0;
    *((_QWORD *)v11 + 27) = 0;
    *((_QWORD *)v11 + 28) = v17;
    *((_QWORD *)v11 + 29) = 0;
    *((_QWORD *)v11 + 30) = 0;
    *((_QWORD *)v11 + 31) = 0;
    *((_QWORD *)v11 + 32) = 0;
    *((_WORD *)v11 + 132) = 0;
    *((_DWORD *)v11 + 67) = v15;
    *((_DWORD *)v11 + 68) = v13;
    pv = 0;
    v24 = 0;
    v25 = 0;
    v18 = (__int64 *)*((_QWORD *)v11 + 28);
    v19 = *v18;
    v24 = -1;
    v25 = -1;
    (*(void (__fastcall **)(__int64 *, LPVOID *))(v19 + 264))(v18, &pv);
    v36 = 0;
    v20 = (const unsigned __int16 *)pv;
    v26 = 0;
    Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v26);
    v27 = 0;
    Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(&v27);
    v28 = v14;
    v29 = 0;
    v30 = &v36;
    v31 = v20;
    AcquireSRWLockExclusive((PSRWLOCK)v11 + 16);
    v21 = *((_QWORD *)v11 + 4);
    if ( v21 )
    {
      *((_QWORD *)v11 + 4) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    *((_DWORD *)v11 + 13) = 0;
    *((_DWORD *)v11 + 12) = v14;
    v22 = *((_QWORD *)v11 + 5);
    if ( v22 )
    {
      *((_QWORD *)v11 + 5) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    *(_OWORD *)(v11 + 56) = v36;
    CTitleBarElementBase::_GenerateNameAndAutomationPropertyString((CTitleBarElementBase *)v11, v20);
    v11[120] = 1;
    if ( v11 != (char *)-128LL )
      ReleaseSRWLockExclusive((PSRWLOCK)v11 + 16);
    *((_QWORD *)v11 + 22) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v11 + 28) + 192LL))(*((_QWORD *)v11 + 28));
    CTitleBarAcc::_AddChildren((CTitleBarAcc *)v11);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
    if ( pv )
      CoTaskMemFree(pv);
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::Release(*a1);
    *a1 = v11;
    v11 = 0;
  }
  if ( v11 )
    operator delete(v11);
  return a1;
}

```

## disassembly

```asm
0x180020cb4  push    rbp
0x180020cb6  push    rbx
0x180020cb7  push    rsi
0x180020cb8  push    rdi
0x180020cb9  push    r12
0x180020cbb  push    r13
0x180020cbd  push    r14
0x180020cbf  push    r15
0x180020cc1  lea     rbp, [rsp-0Fh]
0x180020cc6  sub     rsp, 0A8h
0x180020ccd  mov     rax, cs:__security_cookie
0x180020cd4  xor     rax, rsp
0x180020cd7  mov     [rbp+47h+var_48], rax
0x180020cdb  mov     r14, r9
0x180020cde  mov     rdi, r8
0x180020ce1  mov     rsi, rdx
0x180020ce4  mov     r12, rcx
0x180020ce7  mov     [rbp+47h+var_78], rcx
0x180020ceb  xor     r15d, r15d
0x180020cee  mov     [rbp+47h+var_C0], r15d
0x180020cf2  mov     [rcx], r15
0x180020cf5  mov     [rbp+47h+var_C0], 1
0x180020cfc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020d03  mov     ecx, 118h; unsigned __int64
0x180020d08  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020d0d  mov     rbx, rax
0x180020d10  mov     [rbp+47h+var_70], rax
0x180020d14  mov     [rbp+47h+var_68], rax
0x180020d18  test    rax, rax
0x180020d1b  jnz     short loc_180020D4D
0x180020d1d  test    rbx, rbx
0x180020d20  jz      short loc_180020D2A
0x180020d22  mov     rcx, rbx; Block
0x180020d25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020d2a  mov     rax, r12
0x180020d2d  mov     rcx, [rbp+47h+var_48]
0x180020d31  xor     rcx, rsp; StackCookie
0x180020d34  call    __security_check_cookie
0x180020d39  add     rsp, 0A8h
0x180020d40  pop     r15
0x180020d42  pop     r14
0x180020d44  pop     r13
0x180020d46  pop     r12
0x180020d48  pop     rdi
0x180020d49  pop     rsi
0x180020d4a  pop     rbx
0x180020d4b  pop     rbp
0x180020d4c  retn
0x180020d4d  mov     [rbp+47h+var_60], rbx
0x180020d51  mov     rax, [rbp+47h+arg_28]
0x180020d55  mov     r15d, [rax]
0x180020d58  mov     rax, [rbp+47h+arg_20]
0x180020d5c  mov     r13d, [rax]
0x180020d5f  mov     r14d, [r14]
0x180020d62  mov     rdi, [rdi]
0x180020d65  mov     rax, [rsi]
0x180020d68  lea     rcx, [rax+38h]
0x180020d6c  neg     rax
0x180020d6f  sbb     rsi, rsi
0x180020d72  and     rsi, rcx
0x180020d75  mov     rcx, rbx
0x180020d78  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccInternal@@UIApplicationFrameTitleBarAccRootInternal@@UIValueProvider@@UIRawElementProviderFragmentRoot@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>(void)
0x180020d7d  nop
0x180020d7e  lea     rax, ??_7CTitleBarAcc@@6B@; const CTitleBarAcc::`vftable'
0x180020d85  mov     [rbx], rax
0x180020d88  lea     rax, ??_7CTitleBarAcc@@6BIRawElementProviderFragment@@@; const CTitleBarAcc::`vftable'{for `IRawElementProviderFragment'}
0x180020d8f  mov     [rbx+8], rax
0x180020d93  lea     rax, ??_7CTitleBarAcc@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIApplicationFrameTitleBarAccElementInternal@@@Details@WRL@Microsoft@@@; const CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccElementInternal>'}
0x180020d9a  mov     [rbx+10h], rax
0x180020d9e  lea     rax, ??_7CTitleBarAcc@@6BIApplicationFrameTitleBarAccInternal@@@; const CTitleBarAcc::`vftable'{for `IApplicationFrameTitleBarAccInternal'}
0x180020da5  mov     [rbx+88h], rax
0x180020dac  lea     rax, ??_7CTitleBarAcc@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIApplicationFrameTitleBarAccRootInternal@@UIValueProvider@@UIRawElementProviderFragmentRoot@@@Details@WRL@Microsoft@@@; const CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>'}
0x180020db3  mov     [rbx+90h], rax
0x180020dba  lea     rax, ??_7CTitleBarAcc@@6BIValueProvider@@@; const CTitleBarAcc::`vftable'{for `IValueProvider'}
0x180020dc1  mov     [rbx+98h], rax
0x180020dc8  lea     rax, ??_7CTitleBarAcc@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIRawElementProviderFragmentRoot@@@Details@WRL@Microsoft@@@; const CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRawElementProviderFragmentRoot>'}
0x180020dcf  mov     [rbx+0A0h], rax
0x180020dd6  xor     eax, eax
0x180020dd8  mov     [rbx+0B0h], rax
0x180020ddf  mov     [rbx+0B8h], rdi
0x180020de6  mov     [rbx+0C0h], rax
0x180020ded  mov     [rbx+0C8h], rax
0x180020df4  mov     [rbx+0D0h], rax
0x180020dfb  mov     [rbx+0D8h], rax
0x180020e02  mov     [rbx+0E0h], rsi
0x180020e09  mov     [rbx+0E8h], rax
0x180020e10  mov     [rbx+0F0h], rax
0x180020e17  mov     [rbx+0F8h], rax
0x180020e1e  mov     [rbx+100h], rax
0x180020e25  mov     [rbx+108h], ax
0x180020e2c  mov     [rbx+10Ch], r14d
0x180020e33  mov     [rbx+110h], r15d
0x180020e3a  xor     r15d, r15d
0x180020e3d  mov     [rbp+47h+pv], r15
0x180020e41  mov     [rbp+47h+var_B0], r15
0x180020e45  mov     [rbp+47h+var_A8], r15
0x180020e49  mov     rcx, [rbx+0E0h]
0x180020e50  mov     rax, [rcx]
0x180020e53  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020e57  mov     [rbp+47h+var_B0], rdx
0x180020e5b  mov     [rbp+47h+var_A8], rdx
0x180020e5f  lea     rdx, [rbp+47h+pv]
0x180020e63  mov     rax, [rax+108h]
0x180020e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e6f  xorps   xmm0, xmm0
0x180020e72  movups  [rbp+47h+var_58], xmm0
0x180020e76  mov     rsi, [rbp+47h+pv]
0x180020e7a  mov     [rbp+47h+var_A0], r15
0x180020e7e  lea     rcx, [rbp+47h+var_A0]
0x180020e82  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x180020e87  mov     [rbp+47h+var_98], r15
0x180020e8b  lea     rcx, [rbp+47h+var_98]
0x180020e8f  call    ?InternalAddRef@?$ComPtr@UIApplicationFrameTitleBarAccElementInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccElementInternal>::InternalAddRef(void)
0x180020e94  mov     [rbp+47h+var_90], r13d
0x180020e98  mov     [rbp+47h+var_8C], r15d
0x180020e9c  lea     rax, [rbp+47h+var_58]
0x180020ea0  mov     [rbp+47h+var_88], rax
0x180020ea4  mov     [rbp+47h+var_80], rsi
0x180020ea8  lea     rdi, [rbx+80h]
0x180020eaf  mov     rcx, rdi; SRWLock
0x180020eb2  call    cs:__imp_AcquireSRWLockExclusive
0x180020eb8  mov     rcx, [rbx+20h]
0x180020ebc  test    rcx, rcx
0x180020ebf  jz      short loc_180020ED2
0x180020ec1  mov     [rbx+20h], r15
0x180020ec5  mov     rax, [rcx]
0x180020ec8  mov     rax, [rax+10h]
0x180020ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ed1  nop
0x180020ed2  mov     [rbx+34h], r15d
0x180020ed6  mov     [rbx+30h], r13d
0x180020eda  mov     rcx, [rbx+28h]
0x180020ede  test    rcx, rcx
0x180020ee1  jz      short loc_180020EF4
0x180020ee3  mov     [rbx+28h], r15
0x180020ee7  mov     rax, [rcx]
0x180020eea  mov     rax, [rax+10h]
0x180020eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ef3  nop
0x180020ef4  movups  xmm0, [rbp+47h+var_58]
0x180020ef8  movdqu  xmmword ptr [rbx+38h], xmm0
0x180020efd  mov     rdx, rsi; unsigned __int16 *
0x180020f00  mov     rcx, rbx; this
0x180020f03  call    ?_GenerateNameAndAutomationPropertyString@CTitleBarElementBase@@IEAAXPEBG@Z; CTitleBarElementBase::_GenerateNameAndAutomationPropertyString(ushort const *)
0x180020f08  mov     byte ptr [rbx+78h], 1
0x180020f0c  test    rdi, rdi
0x180020f0f  jz      short loc_180020F1A
0x180020f11  mov     rcx, rdi; SRWLock
0x180020f14  call    cs:__imp_ReleaseSRWLockExclusive
0x180020f1a  mov     rcx, [rbx+0E0h]
0x180020f21  mov     rax, [rcx]
0x180020f24  mov     rax, [rax+0C0h]
0x180020f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f30  mov     [rbx+0B0h], rax
0x180020f37  mov     rcx, rbx; this
0x180020f3a  call    ?_AddChildren@CTitleBarAcc@@AEAAXXZ; CTitleBarAcc::_AddChildren(void)
0x180020f3f  nop
0x180020f40  lea     rcx, [rbp+47h+var_A0]
0x180020f44  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180020f49  nop
0x180020f4a  mov     rcx, [rbp+47h+pv]; pv
0x180020f4e  test    rcx, rcx
0x180020f51  jz      short loc_180020F5A
0x180020f53  call    cs:__imp_CoTaskMemFree
0x180020f59  nop
0x180020f5a  mov     rcx, [r12]
0x180020f5e  test    rcx, rcx
0x180020f61  jnz     short loc_180020F6F
0x180020f63  mov     [r12], rbx
0x180020f67  mov     rbx, r15
0x180020f6a  jmp     loc_180020D1D
0x180020f6f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccInternal@@UIApplicationFrameTitleBarAccRootInternal@@UIValueProvider@@UIRawElementProviderFragmentRoot@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::Release(void)
0x180020f74  jmp     short loc_180020F63
```
