# CTitleBarAcc::CTitleBarAcc(IApplicationFrameTitleBarInternal *,HWND__ *,TitleBarAccFlags,TitleBarPart,TITLE_BAR_BUTTONS)

- ea: `0x18001e294`
- end: `0x18001e4b2`
- name: `??0CTitleBarAcc@@QEAA@PEAUIApplicationFrameTitleBarInternal@@PEAUHWND__@@W4TitleBarAccFlags@@W4TitleBarPart@@W4TITLE_BAR_BUTTONS@@@Z`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001de14`

## callees

- `0x18001e294`
- `0x18001e4e8`
- `0x18001e930`
- `0x18001feb0`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e3f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e3f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e457`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e48c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e48c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTitleBarAcc::CTitleBarAcc(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6)
{
  __int64 *v10; // rcx
  __int64 v11; // rax
  const unsigned __int16 *v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rcx
  LPVOID pv; // [rsp+20h] [rbp-49h] BYREF
  __int64 v17; // [rsp+28h] [rbp-41h]
  __int64 v18; // [rsp+30h] [rbp-39h]
  __int64 v19; // [rsp+38h] [rbp-31h]
  __int64 v20; // [rsp+40h] [rbp-29h]
  int v21; // [rsp+48h] [rbp-21h]
  int v22; // [rsp+4Ch] [rbp-1Dh]
  __int128 *v23; // [rsp+50h] [rbp-19h]
  LPVOID v24; // [rsp+58h] [rbp-11h]
  __int64 v25; // [rsp+60h] [rbp-9h]
  __int128 v26; // [rsp+68h] [rbp-1h] BYREF

  v25 = a1;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>(a1);
  *(_QWORD *)a1 = &CTitleBarAcc::`vftable';
  *(_QWORD *)(a1 + 8) = &CTitleBarAcc::`vftable'{for `IRawElementProviderFragment'};
  *(_QWORD *)(a1 + 16) = &CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccElementInternal>'};
  *(_QWORD *)(a1 + 136) = &CTitleBarAcc::`vftable'{for `IApplicationFrameTitleBarAccInternal'};
  *(_QWORD *)(a1 + 144) = &CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>'};
  *(_QWORD *)(a1 + 152) = &CTitleBarAcc::`vftable'{for `IValueProvider'};
  *(_QWORD *)(a1 + 160) = &CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRawElementProviderFragmentRoot>'};
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = a3;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = a2;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_WORD *)(a1 + 264) = 0;
  *(_DWORD *)(a1 + 268) = a4;
  *(_DWORD *)(a1 + 272) = a6;
  pv = 0;
  v17 = 0;
  v18 = 0;
  v10 = *(__int64 **)(a1 + 224);
  v11 = *v10;
  v17 = -1;
  v18 = -1;
  (*(void (__fastcall **)(__int64 *, LPVOID *))(v11 + 264))(v10, &pv);
  v26 = 0;
  v12 = (const unsigned __int16 *)pv;
  v19 = 0;
  v20 = 0;
  v21 = a5;
  v22 = 0;
  v23 = &v26;
  v24 = pv;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 128));
  v13 = *(_QWORD *)(a1 + 32);
  if ( v13 )
  {
    *(_QWORD *)(a1 + 32) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  *(_DWORD *)(a1 + 52) = 0;
  *(_DWORD *)(a1 + 48) = a5;
  v14 = *(_QWORD *)(a1 + 40);
  if ( v14 )
  {
    *(_QWORD *)(a1 + 40) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  *(_OWORD *)(a1 + 56) = v26;
  CTitleBarElementBase::_GenerateNameAndAutomationPropertyString((CTitleBarElementBase *)a1, v12);
  *(_BYTE *)(a1 + 120) = 1;
  if ( a1 != -128 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 128));
  *(_QWORD *)(a1 + 176) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 224) + 192LL))(*(_QWORD *)(a1 + 224));
  CTitleBarAcc::_AddChildren((CTitleBarAcc *)a1);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x18001e294  push    rbp
0x18001e296  push    rbx
0x18001e297  push    rsi
0x18001e298  push    rdi
0x18001e299  push    r14
0x18001e29b  push    r15
0x18001e29d  lea     rbp, [rsp-1Fh]
0x18001e2a2  sub     rsp, 88h
0x18001e2a9  mov     rax, cs:__security_cookie
0x18001e2b0  xor     rax, rsp
0x18001e2b3  mov     [rbp+47h+var_38], rax
0x18001e2b7  mov     esi, r9d
0x18001e2ba  mov     rbx, r8
0x18001e2bd  mov     rdi, rdx
0x18001e2c0  mov     r14, rcx
0x18001e2c3  mov     [rbp+47h+var_50], rcx
0x18001e2c7  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCTitleBarElementBase@@UIApplicationFrameTitleBarAccInternal@@UIApplicationFrameTitleBarAccRootInternal@@UIValueProvider@@UIRawElementProviderFragmentRoot@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CTitleBarElementBase,IApplicationFrameTitleBarAccInternal,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>(void)
0x18001e2cc  nop
0x18001e2cd  lea     rax, ??_7CTitleBarAcc@@6B@; const CTitleBarAcc::`vftable'
0x18001e2d4  mov     [r14], rax
0x18001e2d7  lea     rax, ??_7CTitleBarAcc@@6BIRawElementProviderFragment@@@; const CTitleBarAcc::`vftable'{for `IRawElementProviderFragment'}
0x18001e2de  mov     [r14+8], rax
0x18001e2e2  lea     rax, ??_7CTitleBarAcc@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIApplicationFrameTitleBarAccElementInternal@@@Details@WRL@Microsoft@@@; const CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccElementInternal>'}
0x18001e2e9  mov     [r14+10h], rax
0x18001e2ed  lea     rax, ??_7CTitleBarAcc@@6BIApplicationFrameTitleBarAccInternal@@@; const CTitleBarAcc::`vftable'{for `IApplicationFrameTitleBarAccInternal'}
0x18001e2f4  mov     [r14+88h], rax
0x18001e2fb  lea     rax, ??_7CTitleBarAcc@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIApplicationFrameTitleBarAccRootInternal@@UIValueProvider@@UIRawElementProviderFragmentRoot@@@Details@WRL@Microsoft@@@; const CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IApplicationFrameTitleBarAccRootInternal,IValueProvider,IRawElementProviderFragmentRoot>'}
0x18001e302  mov     [r14+90h], rax
0x18001e309  lea     rax, ??_7CTitleBarAcc@@6BIValueProvider@@@; const CTitleBarAcc::`vftable'{for `IValueProvider'}
0x18001e310  mov     [r14+98h], rax
0x18001e317  lea     rax, ??_7CTitleBarAcc@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIRawElementProviderFragmentRoot@@@Details@WRL@Microsoft@@@; const CTitleBarAcc::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IRawElementProviderFragmentRoot>'}
0x18001e31e  mov     [r14+0A0h], rax
0x18001e325  xor     r15d, r15d
0x18001e328  mov     [r14+0B0h], r15
0x18001e32f  mov     [r14+0B8h], rbx
0x18001e336  mov     [r14+0C0h], r15
0x18001e33d  mov     [r14+0C8h], r15
0x18001e344  mov     [r14+0D0h], r15
0x18001e34b  mov     [r14+0D8h], r15
0x18001e352  mov     [r14+0E0h], rdi
0x18001e359  mov     [r14+0E8h], r15
0x18001e360  mov     [r14+0F0h], r15
0x18001e367  mov     [r14+0F8h], r15
0x18001e36e  mov     [r14+100h], r15
0x18001e375  mov     [r14+108h], r15w
0x18001e37d  mov     [r14+10Ch], esi
0x18001e384  mov     eax, [rbp+47h+arg_28]
0x18001e387  mov     [r14+110h], eax
0x18001e38e  mov     [rbp+47h+pv], r15
0x18001e392  mov     [rbp+47h+var_88], r15
0x18001e396  mov     [rbp+47h+var_80], r15
0x18001e39a  mov     rcx, [r14+0E0h]
0x18001e3a1  mov     rax, [rcx]
0x18001e3a4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001e3a8  mov     [rbp+47h+var_88], rdx
0x18001e3ac  mov     [rbp+47h+var_80], rdx
0x18001e3b0  lea     rdx, [rbp+47h+pv]
0x18001e3b4  mov     rax, [rax+108h]
0x18001e3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3c0  xorps   xmm0, xmm0
0x18001e3c3  movups  [rbp+47h+var_48], xmm0
0x18001e3c7  mov     rsi, [rbp+47h+pv]
0x18001e3cb  mov     [rbp+47h+var_78], r15
0x18001e3cf  mov     [rbp+47h+var_70], r15
0x18001e3d3  mov     edi, [rbp+47h+arg_20]
0x18001e3d6  mov     [rbp+47h+var_68], edi
0x18001e3d9  mov     [rbp+47h+var_64], r15d
0x18001e3dd  lea     rax, [rbp+47h+var_48]
0x18001e3e1  mov     [rbp+47h+var_60], rax
0x18001e3e5  mov     [rbp+47h+var_58], rsi
0x18001e3e9  lea     rbx, [r14+80h]
0x18001e3f0  mov     rcx, rbx; SRWLock
0x18001e3f3  call    cs:__imp_AcquireSRWLockExclusive
0x18001e3f9  mov     rcx, [r14+20h]
0x18001e3fd  test    rcx, rcx
0x18001e400  jz      short loc_18001E413
0x18001e402  mov     [r14+20h], r15
0x18001e406  mov     rax, [rcx]
0x18001e409  mov     rax, [rax+10h]
0x18001e40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e412  nop
0x18001e413  mov     [r14+34h], r15d
0x18001e417  mov     [r14+30h], edi
0x18001e41b  mov     rcx, [r14+28h]
0x18001e41f  test    rcx, rcx
0x18001e422  jz      short loc_18001E435
0x18001e424  mov     [r14+28h], r15
0x18001e428  mov     rax, [rcx]
0x18001e42b  mov     rax, [rax+10h]
0x18001e42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e434  nop
0x18001e435  movups  xmm0, [rbp+47h+var_48]
0x18001e439  movdqu  xmmword ptr [r14+38h], xmm0
0x18001e43f  mov     rdx, rsi; unsigned __int16 *
0x18001e442  mov     rcx, r14; this
0x18001e445  call    ?_GenerateNameAndAutomationPropertyString@CTitleBarElementBase@@IEAAXPEBG@Z; CTitleBarElementBase::_GenerateNameAndAutomationPropertyString(ushort const *)
0x18001e44a  mov     byte ptr [r14+78h], 1
0x18001e44f  test    rbx, rbx
0x18001e452  jz      short loc_18001E45D
0x18001e454  mov     rcx, rbx; SRWLock
0x18001e457  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e45d  mov     rcx, [r14+0E0h]
0x18001e464  mov     rax, [rcx]
0x18001e467  mov     rax, [rax+0C0h]
0x18001e46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e473  mov     [r14+0B0h], rax
0x18001e47a  mov     rcx, r14; this
0x18001e47d  call    ?_AddChildren@CTitleBarAcc@@AEAAXXZ; CTitleBarAcc::_AddChildren(void)
0x18001e482  nop
0x18001e483  mov     rcx, [rbp+47h+pv]; pv
0x18001e487  test    rcx, rcx
0x18001e48a  jz      short loc_18001E493
0x18001e48c  call    cs:__imp_CoTaskMemFree
0x18001e492  nop
0x18001e493  mov     rax, r14
0x18001e496  mov     rcx, [rbp+47h+var_38]
0x18001e49a  xor     rcx, rsp; StackCookie
0x18001e49d  call    __security_check_cookie
0x18001e4a2  add     rsp, 88h
0x18001e4a9  pop     r15
0x18001e4ab  pop     r14
0x18001e4ad  pop     rdi
0x18001e4ae  pop     rsi
0x18001e4af  pop     rbx
0x18001e4b0  pop     rbp
0x18001e4b1  retn
```
