# Windows::UI::Composition::VisualCommon::RuntimeClassInitialize(Windows::UI::Composition::Compositor *,uint,bool,void *)

- ea: `0x1800178e4`
- end: `0x180017f46`
- name: `?RuntimeClassInitialize@VisualCommon@Composition@UI@Windows@@IEAAJPEAVCompositor@234@I_NPEAX@Z`
- size: `1634`
- prototype: `__int64 __usercall@<rax>(Windows::UI::Composition::VisualCommon *__hidden this@<rcx>, struct Windows::UI::Composition::Compositor *@<rdx>, unsigned int@<r8d>, bool@<r9b>, void *)`
- caller_count: `17`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018140`
- `0x180038018`
- `0x180038c40`
- `0x180038f38`
- `0x18003b2b0`
- `0x18003ba04`
- `0x18003bb20`
- `0x18003c2f8`
- `0x180071ae8`
- `0x18009cfd4`
- `0x1800b467c`
- `0x1800c4450`
- `0x1800ccac4`
- `0x18011b7b4`
- `0x18011e090`
- `0x1801218e8`
- `0x1801701f0`

## callees

- `0x18000b53c`
- `0x180012da0`
- `0x180013528`
- `0x18001358c`
- `0x180014e80`
- `0x180015ed0`
- `0x1800167bc`
- `0x1800178e4`
- `0x180017f4c`
- `0x180018108`
- `0x18001ff20`
- `0x180021140`
- `0x180036f90`
- `0x180051fb8`
- `0x18006c5b0`
- `0x180095e10`
- `0x1800aaf34`
- `0x1800e8210`
- `0x1800ea11c`
- `0x1800f6f10`
- `0x180107230`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017956`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017956`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180017eef`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180017eef`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800179a2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800179a2`

## string_xrefs

- `0x180017994`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180017d94`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`
- `0x180017e5a`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtvisual.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::VisualCommon::RuntimeClassInitialize(
        Windows::UI::Composition::VisualCommon *this,
        struct Windows::UI::Composition::Compositor *a2,
        unsigned int a3,
        unsigned __int8 a4,
        void *a5)
{
  Microsoft::WRL2::ContextSession *v8; // rbx
  int v9; // edi
  struct Windows::UI::Composition::Compositor **v10; // rdx
  int v11; // ebx
  unsigned int *v12; // r12
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  Windows::UI::Composition::VisualCommon **v16; // rax
  void *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  void *v20; // rcx
  bool v21; // zf
  unsigned int v22; // ebx
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  __int64 v25; // rax
  __int64 result; // rax
  char v27; // al
  int v28; // eax
  char v29; // al
  __int64 v30; // rdi
  __int64 *v31; // r14
  unsigned int v32; // eax
  unsigned int v33; // r12d
  __int64 i; // rdx
  __int64 v35; // r9
  int v36; // r10d
  unsigned int v37; // edx
  __int64 v38; // rdx
  int v39; // r13d
  _DWORD *v40; // rax
  unsigned int v41; // r12d
  unsigned int v42; // edx
  int v43; // [rsp+20h] [rbp-C1h]
  char v44[8]; // [rsp+30h] [rbp-B1h] BYREF
  unsigned int v45; // [rsp+38h] [rbp-A9h] BYREF
  unsigned int v46; // [rsp+40h] [rbp-A1h] BYREF
  void *v47; // [rsp+48h] [rbp-99h] BYREF
  unsigned int v48; // [rsp+50h] [rbp-91h] BYREF
  int v49; // [rsp+58h] [rbp-89h] BYREF
  Windows::UI::Composition::VisualCommon *v50; // [rsp+60h] [rbp-81h] BYREF
  Windows::UI::Composition::VisualCommon *v51; // [rsp+68h] [rbp-79h] BYREF
  void **v52; // [rsp+80h] [rbp-61h]
  __int64 v53; // [rsp+88h] [rbp-59h]
  unsigned int *v54; // [rsp+90h] [rbp-51h]
  __int64 v55; // [rsp+98h] [rbp-49h]
  Windows::UI::Composition::VisualCommon **v56; // [rsp+A0h] [rbp-41h]
  __int64 v57; // [rsp+A8h] [rbp-39h]
  unsigned int *v58; // [rsp+B0h] [rbp-31h]
  __int64 v59; // [rsp+B8h] [rbp-29h]
  unsigned int *v60; // [rsp+C0h] [rbp-21h]
  __int64 v61; // [rsp+C8h] [rbp-19h]
  void *v62; // [rsp+D0h] [rbp-11h]
  __int64 v63; // [rsp+D8h] [rbp-9h]
  Windows::UI::Composition::VisualCommon **v64; // [rsp+E0h] [rbp-1h]
  __int64 v65; // [rsp+E8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+57h]

  v44[0] = a4;
  v46 = a3;
  if ( !a5 )
  {
    *((_QWORD *)this + 3) = a2;
    if ( a2 != this )
    {
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)a2 + 4, 1u) )
        (*(void (__fastcall **)(struct Windows::UI::Composition::Compositor *))(*(_QWORD *)a2 + 80LL))(a2);
      v8 = 0;
      v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 56LL) + 40LL);
      if ( v9 == GetCurrentThreadId()
        || (Microsoft::WRL2::ContextSession::BeginApiEntry(*((Microsoft::WRL2::ContextSession **)a2 + 3)),
            v8 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)a2 + 3),
            (*((_BYTE *)a2 + 48) & 2) != 0) )
      {
        v10 = (struct Windows::UI::Composition::Compositor **)*((_QWORD *)a2 + 5);
        if ( *v10 != (struct Windows::UI::Composition::Compositor *)((char *)a2 + 32) )
          __fastfail(3u);
        *((_QWORD *)this + 4) = (char *)a2 + 32;
        *((_QWORD *)this + 5) = v10;
        *v10 = (Windows::UI::Composition::VisualCommon *)((char *)this + 32);
        *((_QWORD *)a2 + 5) = (char *)this + 32;
        if ( v8 )
          Microsoft::WRL2::ContextSession::EndApiEntry(v8);
      }
      else
      {
        Microsoft::WRL2::ContextSession::EndApiEntry(*((Microsoft::WRL2::ContextSession **)a2 + 3));
        RoOriginateErrorW(
          2147483667LL,
          0,
          L"The given object has already been closed / disposed and may no longer be used.");
      }
    }
    v27 = *((_BYTE *)this + 49);
    *((_BYTE *)this + 48) = 31;
    *((_BYTE *)this + 49) ^= (*((_BYTE *)a2 + 49) ^ v27) & 1;
    v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, Windows::UI::Composition::VisualCommon *, char *))(**(_QWORD **)(*((_QWORD *)a2 + 51) + 32LL) + 24LL))(
            *(_QWORD *)(*((_QWORD *)a2 + 51) + 32LL),
            *(unsigned int *)(*((_QWORD *)a2 + 51) + 64LL),
            this,
            (char *)this + 136);
    v11 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
        (const char *)(unsigned int)v28,
        v43);
      v37 = 55;
LABEL_41:
      DoStackCaptureDirect(v11, v37);
      if ( v11 >= 0 )
        goto LABEL_25;
      Microsoft::WRL2::ContextRuntimeClass::Dispose(this);
      v38 = 99;
      goto LABEL_48;
    }
    v29 = *((_BYTE *)a2 + 436);
    if ( (v29 & 1) == 0 )
    {
      v21 = *((_DWORD *)a2 + 108) == 0;
      *((_BYTE *)a2 + 436) = v29 | 1;
      if ( v21 )
        Windows::UI::Composition::CompositorCommon::EnableMessageGroup(a2);
    }
    *((_DWORD *)this + 35) |= 1u;
    v30 = *(_QWORD *)(*((_QWORD *)this + 3) + 440LL);
    v31 = (__int64 *)(v30 + 208);
    v32 = *(_DWORD *)(v30 + 368);
    if ( v32 == -1 )
    {
      v11 = -2147024882;
    }
    else
    {
      v33 = *(_DWORD *)(v30 + 232);
      if ( v32 >> 5 < v33 )
      {
        for ( i = *(unsigned int *)(v30 + 372); *(_DWORD *)(*v31 + 4 * i) == -1; i = ((int)i + 1) % v33 )
          ;
        *(_DWORD *)(v30 + 372) = i;
        goto LABEL_38;
      }
      LODWORD(v47) = 0;
      v11 = DynArray<unsigned int,1>::AddMultipleAndSet(v30 + 208, &v47);
      if ( v11 >= 0 )
      {
        LODWORD(i) = v33;
LABEL_38:
        v35 = *v31;
        LODWORD(v47) = 0;
        v21 = !_BitScanForward((unsigned int *)&v36, ~*(_DWORD *)(v35 + 4LL * (unsigned int)i));
        if ( v21 )
          Microsoft::WRL2::FailFast::Do();
        *(_DWORD *)(v35 + 4LL * (unsigned int)i) |= *(_DWORD *)(v35 + 4LL * (unsigned int)i) + 1;
        v39 = 32 * i + v36 + 1;
        ++*(_DWORD *)(v30 + 368);
        v47 = 0;
        DirectComposition::CDevice::BeginKernelCommand((DirectComposition::CDevice *)v30, 0x10u, &v47, 0);
        v40 = v47;
        v22 = v46;
        v41 = (unsigned __int8)v44[0];
        *(_DWORD *)v47 = 2;
        v40[1] = v39;
        v40[2] = v22;
        v40[3] = v41;
        if ( *(_QWORD *)(v30 + 88) )
        {
LABEL_21:
          *((_DWORD *)this + 36) = v39;
          if ( (Microsoft_Windows_DirectCompositionEnableBits & 1) != 0 )
          {
            v23 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 440LL) + 168LL);
            v24 = ((unsigned __int64)(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23) << 32)
                | *((unsigned int *)this + 36);
            v49 = *((_DWORD *)this + 36);
            v25 = *((_QWORD *)this + 3);
            v51 = (Windows::UI::Composition::VisualCommon *)(v24 | 0x8000000000000000uLL);
            LODWORD(v47) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v25 + 440) + 168LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(v25 + 440) + 168LL));
            v54 = (unsigned int *)&v49;
            v52 = &v47;
            v56 = &v51;
            v16 = &v50;
            v50 = this;
            v58 = &v48;
            v60 = &v46;
            v17 = &v45;
            v45 = 0;
            v46 = v41;
            v48 = v22;
            goto LABEL_23;
          }
          goto LABEL_24;
        }
        DirectComposition::CDeviceLock::AssertIsOwned((DirectComposition::CDeviceLock *)(v30 + 104));
        v18 = *(_QWORD *)(v30 + 168);
        v19 = (unsigned int)(*(_DWORD *)(v30 + 184) - *(_DWORD *)(v30 + 188));
        v45 = 0;
        v44[0] = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, char *))(*(_QWORD *)v18 + 16LL))(
                v18,
                v19,
                &v45,
                v44);
        if ( v45 != *(_DWORD *)(v30 + 192) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SeparateOOMDCompKBatchFailures>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SeparateOOMDCompKBatchFailures>::GetImpl'::`2'::impl)
            && IsOOM(v11) )
          {
            TerminateProcessOnMemoryExhaustion(0);
          }
          DirectComposition::CDevice::FailFastForKernelBatchFailure((DirectComposition::CDevice *)v30, v45);
        }
        v20 = *(void **)(v30 + 200);
        if ( v20 )
        {
          operator delete(v20);
          *(_QWORD *)(v30 + 200) = 0;
        }
        v21 = v44[0] == 0;
        *(_QWORD *)(v30 + 188) = *(unsigned int *)(v30 + 184);
        if ( !v21 )
          DirectComposition::CDevice::CheckForDelayedDestructionObjects((DirectComposition::CDevice *)v30);
        if ( v11 >= 0 )
        {
          v22 = v46;
          goto LABEL_21;
        }
        *(_DWORD *)(*v31 + 4 * ((unsigned __int64)(unsigned int)(v39 - 1) >> 5)) &= ~(1 << (v39 - 1));
        --*(_DWORD *)(v30 + 368);
      }
    }
    v37 = 64;
    goto LABEL_41;
  }
  v11 = Windows::UI::Composition::CompositionObject::RuntimeClassInitialize(this, a2);
  if ( v11 < 0 )
  {
    v42 = 122;
  }
  else
  {
    v12 = (unsigned int *)((char *)this + 144);
    v11 = DirectComposition::CDevice::ChannelOpenSharedResource(
            *((DirectComposition::CDevice **)a2 + 55),
            a5,
            a3,
            1,
            (unsigned int *)this + 36);
    if ( v11 >= 0 )
    {
      if ( (Microsoft_Windows_DirectCompositionEnableBits & 1) != 0 )
      {
        v13 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 440LL) + 168LL);
        v14 = ((unsigned __int64)(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) << 32) | *v12;
        v45 = *v12;
        v15 = *((_QWORD *)this + 3);
        v50 = (Windows::UI::Composition::VisualCommon *)(v14 | 0x8000000000000000uLL);
        v46 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v15 + 440) + 168LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(v15 + 440) + 168LL));
        v54 = &v45;
        v52 = (void **)&v46;
        v56 = &v50;
        v16 = &v51;
        v51 = this;
        v58 = &v48;
        v60 = (unsigned int *)&v49;
        v17 = &v47;
        LODWORD(v47) = 1;
        v49 = 0;
        v48 = a3;
LABEL_23:
        v64 = v16;
        v63 = 4;
        v62 = v17;
        v61 = 4;
        v59 = 4;
        v57 = 8;
        v55 = 4;
        v53 = 4;
        v65 = 8;
        McGenEventWrite_EventWriteTransfer(v17, &DCOMPEVENT_RESOURCE_CREATION);
      }
LABEL_24:
      Windows::UI::Composition::ProxyObject::RegisterConversationWithDCompK(this);
LABEL_25:
      *((_DWORD *)this + 67) &= 0xFFFFFE00;
      result = 0;
      *((_WORD *)this + 136) = 256;
      return result;
    }
    v42 = 133;
  }
  DoStackCaptureDirect(v11, v42);
  Microsoft::WRL2::ContextRuntimeClass::Dispose(this);
  v38 = 95;
LABEL_48:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v38,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtvisual.cpp",
    (const char *)(unsigned int)v11,
    v43);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800178e4  push    rbp
0x1800178e6  push    rbx
0x1800178e7  push    rsi
0x1800178e8  push    rdi
0x1800178e9  push    r12
0x1800178eb  push    r13
0x1800178ed  push    r14
0x1800178ef  lea     rbp, [rsp-1Fh]
0x1800178f4  sub     rsp, 100h
0x1800178fb  mov     rax, cs:__security_cookie
0x180017902  xor     rax, rsp
0x180017905  mov     [rbp+4Fh+var_40], rax
0x180017909  mov     rdi, [rbp+4Fh+arg_20]
0x18001790d  mov     r13d, r8d
0x180017910  mov     [rsp+130h+var_100], r9b
0x180017915  mov     r14, rdx
0x180017918  mov     [rsp+130h+var_F0], r8d
0x18001791d  mov     rsi, rcx
0x180017920  test    rdi, rdi
0x180017923  jnz     loc_1800179AD
0x180017929  mov     [rcx+18h], rdx
0x18001792d  cmp     rdx, rcx
0x180017930  jz      loc_180017CAA
0x180017936  lea     eax, [rdi+1]
0x180017939  lock xadd [rdx+10h], eax
0x18001793e  inc     eax
0x180017940  cmp     eax, 1
0x180017943  jz      loc_180017E9A
0x180017949  mov     rax, [r14+18h]
0x18001794d  xor     ebx, ebx
0x18001794f  mov     rcx, [rax+38h]
0x180017953  mov     edi, [rcx+28h]
0x180017956  call    cs:__imp_GetCurrentThreadId
0x18001795c  cmp     edi, eax
0x18001795e  jnz     short loc_180017978
0x180017960  lea     rcx, [r14+20h]
0x180017964  mov     rdx, [rcx+8]
0x180017968  cmp     [rdx], rcx
0x18001796b  jz      loc_180017C8F
0x180017971  mov     ecx, 3
0x180017976  int     29h; Win8: RtlFailFast(ecx)
0x180017978  mov     rcx, [r14+18h]; this
0x18001797c  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180017981  test    byte ptr [r14+30h], 2
0x180017986  mov     rbx, [r14+18h]
0x18001798a  jnz     short loc_180017960
0x18001798c  mov     rcx, rbx; this
0x18001798f  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180017994  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18001799b  xor     edx, edx
0x18001799d  mov     ecx, 80000013h
0x1800179a2  call    cs:__imp_RoOriginateErrorW
0x1800179a8  jmp     loc_180017CAA
0x1800179ad  call    ?RuntimeClassInitialize@CompositionObject@Composition@UI@Windows@@QEAAJPEAVCompositor@234@@Z; Windows::UI::Composition::CompositionObject::RuntimeClassInitialize(Windows::UI::Composition::Compositor *)
0x1800179b2  mov     ebx, eax
0x1800179b4  test    eax, eax
0x1800179b6  js      loc_180017E3D
0x1800179bc  mov     rcx, [r14+1B8h]; this
0x1800179c3  lea     r12, [rsi+90h]
0x1800179ca  mov     r9b, 1; bool
0x1800179cd  mov     qword ptr [rsp+130h+var_110], r12; unsigned int *
0x1800179d2  mov     r8d, r13d; unsigned int
0x1800179d5  mov     rdx, rdi; void *
0x1800179d8  call    ?ChannelOpenSharedResource@CDevice@DirectComposition@@QEAAJPEAXI_NPEAI@Z; DirectComposition::CDevice::ChannelOpenSharedResource(void *,uint,bool,uint *)
0x1800179dd  mov     ebx, eax
0x1800179df  test    eax, eax
0x1800179e1  js      loc_180017E70
0x1800179e7  test    byte ptr cs:Microsoft_Windows_DirectCompositionEnableBits, 1
0x1800179ee  jz      loc_180017C54
0x1800179f4  mov     rax, [rsi+18h]
0x1800179f8  mov     rcx, [rax+1B8h]
0x1800179ff  mov     rcx, [rcx+0A8h]
0x180017a06  mov     rax, [rcx]
0x180017a09  mov     rax, [rax+8]
0x180017a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a12  mov     edx, [r12]
0x180017a16  mov     eax, eax
0x180017a18  mov     ecx, edx
0x180017a1a  shl     rax, 20h
0x180017a1e  or      rcx, rax
0x180017a21  mov     [rsp+130h+var_F8], edx
0x180017a25  mov     rax, 8000000000000000h
0x180017a2f  or      rcx, rax
0x180017a32  mov     rax, [rsi+18h]
0x180017a36  mov     [rsp+130h+var_D0], rcx
0x180017a3b  mov     rcx, [rax+1B8h]
0x180017a42  mov     rcx, [rcx+0A8h]
0x180017a49  mov     rax, [rcx]
0x180017a4c  mov     rax, [rax+8]
0x180017a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a55  lea     rcx, [rsp+130h+var_F8]
0x180017a5a  mov     [rsp+130h+var_F0], eax
0x180017a5e  mov     [rbp+4Fh+var_A0], rcx
0x180017a62  lea     rax, [rsp+130h+var_F0]
0x180017a67  lea     rcx, [rsp+130h+var_D0]
0x180017a6c  mov     [rbp+4Fh+var_B0], rax
0x180017a70  mov     [rbp+4Fh+var_90], rcx
0x180017a74  lea     rax, [rbp+4Fh+var_C8]
0x180017a78  lea     rcx, [rsp+130h+var_E0]
0x180017a7d  mov     [rbp+4Fh+var_C8], rsi
0x180017a81  mov     [rbp+4Fh+var_80], rcx
0x180017a85  lea     rcx, [rsp+130h+var_D8]
0x180017a8a  mov     [rbp+4Fh+var_70], rcx
0x180017a8e  lea     rcx, [rsp+130h+var_E8]
0x180017a93  mov     dword ptr [rsp+130h+var_E8], 1
0x180017a9b  mov     [rsp+130h+var_D8], 0
0x180017aa3  mov     [rsp+130h+var_E0], r13d
0x180017aa8  jmp     loc_180017C01
0x180017aad  lea     rcx, [rdi+68h]; this
0x180017ab1  call    ?AssertIsOwned@CDeviceLock@DirectComposition@@QEBAXXZ; DirectComposition::CDeviceLock::AssertIsOwned(void)
0x180017ab6  mov     rcx, [rdi+0A8h]
0x180017abd  lea     r9, [rsp+130h+var_100]
0x180017ac2  mov     edx, [rdi+0B8h]
0x180017ac8  lea     r8, [rsp+130h+var_F8]
0x180017acd  sub     edx, [rdi+0BCh]
0x180017ad3  mov     [rsp+130h+var_F8], 0
0x180017adb  mov     [rsp+130h+var_100], 0
0x180017ae0  mov     rax, [rcx]
0x180017ae3  mov     rax, [rax+10h]
0x180017ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aec  mov     ebx, eax
0x180017aee  mov     eax, [rdi+0C0h]
0x180017af4  cmp     [rsp+130h+var_F8], eax
0x180017af8  jnz     loc_180017ECA
0x180017afe  mov     rcx, [rdi+0C8h]; lpMem
0x180017b05  test    rcx, rcx
0x180017b08  jnz     loc_180017EFB
0x180017b0e  cmp     [rsp+130h+var_100], 0
0x180017b13  mov     eax, [rdi+0B8h]
0x180017b19  mov     [rdi+0BCh], eax
0x180017b1f  mov     dword ptr [rdi+0C0h], 0
0x180017b29  jnz     loc_180017F10
0x180017b2f  test    ebx, ebx
0x180017b31  js      loc_180017F1D
0x180017b37  mov     ebx, [rsp+130h+var_F0]
0x180017b3b  mov     [rsi+90h], r13d
0x180017b42  test    byte ptr cs:Microsoft_Windows_DirectCompositionEnableBits, 1
0x180017b49  jz      loc_180017C54
0x180017b4f  mov     rax, [rsi+18h]
0x180017b53  mov     rcx, [rax+1B8h]
0x180017b5a  mov     rcx, [rcx+0A8h]
0x180017b61  mov     rax, [rcx]
0x180017b64  mov     rax, [rax+8]
0x180017b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b6d  mov     edx, [rsi+90h]
0x180017b73  mov     eax, eax
0x180017b75  mov     ecx, edx
0x180017b77  shl     rax, 20h
0x180017b7b  or      rcx, rax
0x180017b7e  mov     [rsp+130h+var_D8], edx
0x180017b82  mov     rax, 8000000000000000h
0x180017b8c  or      rcx, rax
0x180017b8f  mov     rax, [rsi+18h]
0x180017b93  mov     [rbp+4Fh+var_C8], rcx
0x180017b97  mov     rcx, [rax+1B8h]
0x180017b9e  mov     rcx, [rcx+0A8h]
0x180017ba5  mov     rax, [rcx]
0x180017ba8  mov     rax, [rax+8]
0x180017bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb1  lea     rcx, [rsp+130h+var_D8]
0x180017bb6  mov     dword ptr [rsp+130h+var_E8], eax
0x180017bba  mov     [rbp+4Fh+var_A0], rcx
0x180017bbe  lea     rax, [rsp+130h+var_E8]
0x180017bc3  lea     rcx, [rbp+4Fh+var_C8]
0x180017bc7  mov     [rbp+4Fh+var_B0], rax
0x180017bcb  mov     [rbp+4Fh+var_90], rcx
0x180017bcf  lea     rax, [rsp+130h+var_D0]
0x180017bd4  lea     rcx, [rsp+130h+var_E0]
0x180017bd9  mov     [rsp+130h+var_D0], rsi
0x180017bde  mov     [rbp+4Fh+var_80], rcx
0x180017be2  lea     rcx, [rsp+130h+var_F0]
0x180017be7  mov     [rbp+4Fh+var_70], rcx
0x180017beb  lea     rcx, [rsp+130h+var_F8]
0x180017bf0  mov     [rsp+130h+var_F8], 0
0x180017bf8  mov     [rsp+130h+var_F0], r12d
0x180017bfd  mov     [rsp+130h+var_E0], ebx
0x180017c01  mov     r9d, 8
0x180017c07  mov     [rbp+4Fh+var_50], rax
0x180017c0b  lea     rax, [rbp+4Fh+var_C0]
0x180017c0f  mov     [rbp+4Fh+var_58], 4
0x180017c17  lea     rdx, DCOMPEVENT_RESOURCE_CREATION
0x180017c1e  mov     qword ptr [rsp+130h+var_110], rax
0x180017c23  mov     [rbp+4Fh+var_60], rcx
0x180017c27  mov     [rbp+4Fh+var_68], 4
0x180017c2f  mov     [rbp+4Fh+var_78], 4
0x180017c37  mov     [rbp+4Fh+var_88], r9
0x180017c3b  mov     [rbp+4Fh+var_98], 4
0x180017c43  mov     [rbp+4Fh+var_A8], 4
0x180017c4b  mov     [rbp+4Fh+var_48], r9
0x180017c4f  call    McGenEventWrite_EventWriteTransfer
0x180017c54  mov     rcx, rsi; this
0x180017c57  call    ?RegisterConversationWithDCompK@ProxyObject@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::ProxyObject::RegisterConversationWithDCompK(void)
0x180017c5c  and     dword ptr [rsi+10Ch], 0FFFFFE00h
0x180017c66  xor     eax, eax
0x180017c68  mov     word ptr [rsi+110h], 100h
0x180017c71  mov     rcx, [rbp+4Fh+var_40]
0x180017c75  xor     rcx, rsp; StackCookie
0x180017c78  call    __security_check_cookie
0x180017c7d  add     rsp, 100h
0x180017c84  pop     r14
0x180017c86  pop     r13
0x180017c88  pop     r12
0x180017c8a  pop     rdi
0x180017c8b  pop     rsi
0x180017c8c  pop     rbx
0x180017c8d  pop     rbp
0x180017c8e  retn
0x180017c8f  lea     rax, [rsi+20h]
0x180017c93  mov     [rax], rcx
0x180017c96  mov     [rax+8], rdx
0x180017c9a  mov     [rdx], rax
0x180017c9d  mov     [rcx+8], rax
0x180017ca1  test    rbx, rbx
0x180017ca4  jnz     loc_180017EAE
0x180017caa  mov     al, [rsi+31h]
0x180017cad  lea     r9, [rsi+88h]
0x180017cb4  mov     byte ptr [rsi+30h], 1Fh
0x180017cb8  mov     r8, rsi
0x180017cbb  xor     al, [r14+31h]
0x180017cbf  and     al, 1
0x180017cc1  xor     [rsi+31h], al
0x180017cc4  mov     rdx, [r14+198h]
0x180017ccb  mov     rcx, [rdx+20h]
0x180017ccf  mov     edx, [rdx+40h]
0x180017cd2  mov     rax, [rcx]
0x180017cd5  mov     rax, [rax+18h]
0x180017cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cde  mov     ebx, eax
0x180017ce0  test    eax, eax
0x180017ce2  js      loc_180017D90
0x180017ce8  mov     al, [r14+1B4h]
0x180017cef  test    al, 1
0x180017cf1  jnz     short loc_180017D0E
0x180017cf3  or      al, 1
0x180017cf5  cmp     dword ptr [r14+1B0h], 0
0x180017cfd  mov     [r14+1B4h], al
0x180017d04  jnz     short loc_180017D0E
0x180017d06  mov     rcx, r14; this
0x180017d09  call    ?EnableMessageGroup@CompositorCommon@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::CompositorCommon::EnableMessageGroup(void)
0x180017d0e  or      dword ptr [rsi+8Ch], 1
0x180017d15  or      r8d, 0FFFFFFFFh
0x180017d19  mov     rax, [rsi+18h]
0x180017d1d  mov     rdi, [rax+1B8h]
0x180017d24  lea     r14, [rdi+0D0h]
0x180017d2b  mov     eax, [r14+0A0h]
0x180017d32  cmp     eax, r8d
0x180017d35  jz      loc_180017EBB
0x180017d3b  mov     r12d, [r14+18h]
0x180017d3f  shr     eax, 5
0x180017d42  cmp     eax, r12d
0x180017d45  jnb     loc_180017E77
0x180017d4b  mov     edx, [r14+0A4h]
0x180017d52  xor     ebx, ebx
0x180017d54  mov     rcx, [r14]
0x180017d57  jmp     short loc_180017D61
0x180017d59  lea     eax, [rdx+1]
0x180017d5c  xor     edx, edx
0x180017d5e  div     r12d
0x180017d61  cmp     [rcx+rdx*4], r8d
0x180017d65  jz      short loc_180017D59
0x180017d67  mov     [r14+0A4h], edx
0x180017d6e  mov     r9, [r14]
0x180017d71  mov     r8d, edx
0x180017d74  mov     dword ptr [rsp+130h+var_E8], 0
0x180017d7c  mov     ecx, [r9+r8*4]
0x180017d80  mov     eax, ecx
0x180017d82  not     eax
0x180017d84  bsf     r10d, eax
0x180017d88  jnz     short loc_180017DCE
0x180017d8a  call    ?Do@FailFast@WRL2@Microsoft@@SAXXZ; Microsoft::WRL2::FailFast::Do(void)
0x180017d90  mov     rcx, [rbp+57h]; this
0x180017d94  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180017d9b  mov     r9d, eax; char *
0x180017d9e  mov     edx, 55h ; 'U'; void *
0x180017da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017da8  mov     edx, 37h ; '7'; unsigned int
0x180017dad  mov     ecx, ebx; int
0x180017daf  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180017db4  test    ebx, ebx
0x180017db6  jns     loc_180017C5C
0x180017dbc  mov     rcx, rsi; this
0x180017dbf  call    ?Dispose@ContextRuntimeClass@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextRuntimeClass::Dispose(void)
0x180017dc4  mov     edx, 63h ; 'c'
0x180017dc9  jmp     loc_180017E56
0x180017dce  shl     edx, 5
0x180017dd1  lea     eax, [rcx+1]
0x180017dd4  or      eax, ecx
0x180017dd6  lea     r13d, [r10+1]
0x180017dda  mov     [r9+r8*4], eax
0x180017dde  add     r13d, edx
0x180017de1  inc     dword ptr [r14+0A0h]
0x180017de8  test    ebx, ebx
0x180017dea  js      loc_180017EC0
0x180017df0  xor     r9d, r9d; bool
0x180017df3  mov     [rsp+130h+var_E8], 0
0x180017dfc  lea     r8, [rsp+130h+var_E8]; void **
0x180017e01  mov     rcx, rdi; this
0x180017e04  lea     edx, [r9+10h]; unsigned int
0x180017e08  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x180017e0d  mov     rax, [rsp+130h+var_E8]
  ... truncated ...
```
