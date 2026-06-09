# CGuestSessionEnumerator::RuntimeClassInitialize(CGuestXvmAudioObject *,CGuestAudioSessionManager *)

- ea: `0x1800b8f30`
- end: `0x1800b9268`
- name: `?RuntimeClassInitialize@CGuestSessionEnumerator@@QEAAJPEAVCGuestXvmAudioObject@@PEAVCGuestAudioSessionManager@@@Z`
- size: `824`
- prototype: `__int64 __fastcall(CGuestSessionEnumerator *__hidden this, struct CGuestXvmAudioObject *, struct CGuestAudioSessionManager *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b808c`

## callees

- `0x18000d11c`
- `0x180010a90`
- `0x180025a04`
- `0x18004d8a8`
- `0x180087e80`
- `0x180087ed0`
- `0x18008866c`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800994e8`
- `0x1800a6ee4`
- `0x1800b0470`
- `0x1800b2bb4`
- `0x1800b7d54`
- `0x1800b8f30`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9070`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b923a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9070`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b9216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b923a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGuestSessionEnumerator::RuntimeClassInitialize(
        CGuestSessionEnumerator *this,
        struct CGuestXvmAudioObject *a2,
        struct CGuestAudioSessionManager *a3)
{
  int v6; // eax
  int v7; // edi
  void *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r14
  __int64 v13; // rdi
  unsigned __int64 v14; // rsi
  __int64 v15; // rax
  bool v16; // cf
  unsigned __int64 v17; // rax
  unsigned __int64 *v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rdi
  __int64 v21; // rdx
  void *v22; // rcx
  void *v23; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  int *v25; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  int v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v29; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID *p_pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  char v32; // [rsp+60h] [rbp-A0h]
  _BYTE v33[1568]; // [rsp+70h] [rbp-90h] BYREF
  __int64 Src; // [rsp+690h] [rbp+590h] BYREF
  unsigned int v35; // [rsp+698h] [rbp+598h]
  int v36; // [rsp+69Ch] [rbp+59Ch]
  int v37; // [rsp+6A0h] [rbp+5A0h]
  _BYTE v38[1548]; // [rsp+6A4h] [rbp+5A4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CE8h] [rbp+BE8h]

  Src = 24;
  v35 = *((_DWORD *)a2 + 12);
  v36 = 0;
  v37 = 119;
  memset_0(v38, 0, 0x600u);
  v6 = XvmActivateProxyAudioObject::CastTo<XvmActivateAudioSessionEnumerator>(&Src, &v29);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudiosessionmanager.cpp",
      (const char *)(unsigned int)v6,
      v24);
    return (unsigned int)v7;
  }
  pv = 0;
  *(_QWORD *)v28 = 0;
  p_pv = &pv;
  v31 = 0;
  v32 = 1;
  memcpy_0(v33, &Src, 0x614u);
  v25 = v28;
  v7 = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(a2, v35, v33, &v31);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudiosessionmanager.cpp",
      (const char *)(unsigned int)v7,
      (int)v28);
    goto LABEL_6;
  }
  v27 = 0;
  v29 = &v27;
  v10 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v29);
  v7 = Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(this, v10);
  if ( v7 < 0 )
  {
    v11 = 178;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudiosessionmanager.cpp",
      (const char *)(unsigned int)v7,
      (int)v28);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
LABEL_6:
    v9 = pv;
    pv = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    return (unsigned int)v7;
  }
  v12 = *(_QWORD *)v28;
  v7 = CGuestXvmAudioObject::Initialize(
         (CGuestSessionEnumerator *)((char *)this + 24),
         *(_DWORD *)(*(_QWORD *)v28 + 12LL),
         (struct Microsoft::WRL::WeakRef *)&v27,
         0);
  if ( v7 < 0 )
  {
    v11 = 180;
    goto LABEL_10;
  }
  *(_QWORD *)v28 = 0;
  v7 = XvmActivateProxyAudioObject::CastTo<XvmActivateAudioSessionEnumerator>(v12, v28);
  if ( v7 < 0 )
  {
    v11 = 183;
    goto LABEL_10;
  }
  *((_DWORD *)this + 38) = **(_DWORD **)v28;
  v13 = *((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct CGuestAudioSessionManager *))(*(_QWORD *)a3 + 8LL))(a3);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = *((int *)this + 38);
  v15 = 8 * v14;
  if ( !is_mul_ok(v14, 8u) )
    v15 = -1;
  v16 = __CFADD__(v15, 8);
  v17 = v15 + 8;
  if ( v16 )
    v17 = -1;
  v18 = (unsigned __int64 *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
  if ( v18 )
  {
    *v18 = v14;
    v20 = v18 + 1;
    `eh vector constructor iterator'(
      v18 + 1,
      8u,
      v14,
      wil::com_ptr_t<IAudioSessionControl2,wil::err_returncode_policy>::com_ptr_t<IAudioSessionControl2,wil::err_returncode_policy>,
      wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>);
  }
  else
  {
    v20 = 0;
  }
  v21 = *((_QWORD *)this + 20);
  *((_QWORD *)this + 20) = v20;
  if ( v21 )
    std::default_delete<wil::com_ptr_t<IAudioSessionControl2,wil::err_returncode_policy> [0]>::operator()<wil::com_ptr_t<IAudioSessionControl2,wil::err_returncode_policy>,0>(v19);
  if ( *((_QWORD *)this + 20) )
  {
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
    v23 = pv;
    pv = 0;
    if ( v23 )
      CoTaskMemFree(v23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudiosessionmanager.cpp",
      (const char *)0x8007000ELL,
      (int)v25);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v27);
    v22 = pv;
    pv = 0;
    if ( v22 )
      CoTaskMemFree(v22);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800b8f30  mov     [rsp-8+arg_10], rbx
0x1800b8f35  push    rbp
0x1800b8f36  push    rsi
0x1800b8f37  push    rdi
0x1800b8f38  push    r14
0x1800b8f3a  push    r15
0x1800b8f3c  lea     rbp, [rsp-0BC0h]
0x1800b8f44  sub     rsp, 0CC0h
0x1800b8f4b  mov     rax, cs:__security_cookie
0x1800b8f52  xor     rax, rsp
0x1800b8f55  mov     [rbp+0BE0h+var_30], rax
0x1800b8f5c  mov     rsi, r8
0x1800b8f5f  mov     r14, rdx
0x1800b8f62  mov     rbx, rcx
0x1800b8f65  mov     [rbp+0BE0h+Src], 18h
0x1800b8f70  xor     r15d, r15d
0x1800b8f73  mov     eax, [rdx+30h]
0x1800b8f76  mov     [rbp+0BE0h+var_648], eax
0x1800b8f7c  mov     [rbp+0BE0h+var_644], r15d
0x1800b8f83  mov     [rbp+0BE0h+var_640], 77h ; 'w'
0x1800b8f8d  xor     edx, edx; Val
0x1800b8f8f  mov     r8d, 600h; Size
0x1800b8f95  lea     rcx, [rbp+0BE0h+var_63C]; void *
0x1800b8f9c  call    memset_0
0x1800b8fa1  lea     rdx, [rsp+0CE0h+var_C98]
0x1800b8fa6  lea     rcx, [rbp+0BE0h+Src]
0x1800b8fad  call    ??$CastTo@UXvmActivateAudioSessionEnumerator@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateAudioSessionEnumerator@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateAudioSessionEnumerator>(XvmActivateAudioSessionEnumerator * *)
0x1800b8fb2  mov     edi, eax
0x1800b8fb4  test    eax, eax
0x1800b8fb6  jns     short loc_1800B8FDA
0x1800b8fb8  mov     rcx, [rbp+0BE8h]; this
0x1800b8fbf  mov     r9d, eax; char *
0x1800b8fc2  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\client\\audioclient"...
0x1800b8fc9  mov     edx, 0ABh; void *
0x1800b8fce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8fd3  mov     eax, edi
0x1800b8fd5  jmp     loc_1800B9242
0x1800b8fda  mov     [rsp+0CE0h+pv], r15
0x1800b8fdf  mov     qword ptr [rsp+0CE0h+var_CA0], r15
0x1800b8fe4  lea     rax, [rsp+0CE0h+pv]
0x1800b8fe9  mov     [rsp+0CE0h+var_C90], rax
0x1800b8fee  mov     [rsp+0CE0h+var_C88], r15
0x1800b8ff3  mov     [rsp+0CE0h+var_C80], 1
0x1800b8ff8  lea     rcx, [rsp+0CE0h+var_C70]; void *
0x1800b8ffd  lea     rdx, [rbp+0BE0h+Src]; Src
0x1800b9004  mov     r8d, 614h; Size
0x1800b900a  call    memcpy_0
0x1800b900f  lea     rax, [rsp+0CE0h+var_CA0]
0x1800b9014  mov     [rsp+0CE0h+var_CC0], rax; int
0x1800b9019  lea     r9, [rsp+0CE0h+var_C88]
0x1800b901e  lea     r8, [rsp+0CE0h+var_C70]
0x1800b9023  mov     edx, [rbp+0BE0h+var_648]
0x1800b9029  mov     rcx, r14
0x1800b902c  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x1800b9031  mov     edi, eax
0x1800b9033  lea     rcx, [rsp+0CE0h+var_C90]
0x1800b9038  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800b903d  test    edi, edi
0x1800b903f  jns     short loc_1800B907B
0x1800b9041  mov     rcx, [rbp+0BE8h]; this
0x1800b9048  mov     r9d, edi; char *
0x1800b904b  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\client\\audioclient"...
0x1800b9052  mov     edx, 0AFh; void *
0x1800b9057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b905c  nop
0x1800b905d  mov     rcx, [rsp+0CE0h+pv]; pv
0x1800b9062  mov     [rsp+0CE0h+pv], r15
0x1800b9067  test    rcx, rcx
0x1800b906a  jz      loc_1800B8FD3
0x1800b9070  call    cs:__imp_CoTaskMemFree
0x1800b9076  jmp     loc_1800B8FD3
0x1800b907b  mov     [rsp+0CE0h+var_CA8], r15
0x1800b9080  lea     rax, [rsp+0CE0h+var_CA8]
0x1800b9085  mov     [rsp+0CE0h+var_C98], rax
0x1800b908a  lea     rcx, [rsp+0CE0h+var_C98]
0x1800b908f  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x1800b9094  mov     rdx, rax
0x1800b9097  mov     rcx, rbx
0x1800b909a  call    ??$AsWeak@VCGuestSpatialAudioClient@@@WRL@Microsoft@@YAJPEAVCGuestSpatialAudioClient@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestSpatialAudioClient>(CGuestSpatialAudioClient *,Microsoft::WRL::WeakRef *)
0x1800b909f  mov     edi, eax
0x1800b90a1  test    eax, eax
0x1800b90a3  jns     short loc_1800B90CD
0x1800b90a5  mov     edx, 0B2h; void *
0x1800b90aa  mov     rcx, [rbp+0BE8h]; this
0x1800b90b1  mov     r9d, edi; char *
0x1800b90b4  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\client\\audioclient"...
0x1800b90bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b90c0  nop
0x1800b90c1  lea     rcx, [rsp+0CE0h+var_CA8]
0x1800b90c6  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b90cb  jmp     short loc_1800B905D
0x1800b90cd  lea     rcx, [rbx+18h]; this
0x1800b90d1  xor     r9d, r9d; struct XvmActivateProxyAudioObject *
0x1800b90d4  lea     r8, [rsp+0CE0h+var_CA8]; struct Microsoft::WRL::WeakRef *
0x1800b90d9  mov     r14, qword ptr [rsp+0CE0h+var_CA0]
0x1800b90de  mov     edx, [r14+0Ch]; unsigned int
0x1800b90e2  call    ?Initialize@CGuestXvmAudioObject@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUXvmActivateProxyAudioObject@@@Z; CGuestXvmAudioObject::Initialize(uint,Microsoft::WRL::WeakRef &,XvmActivateProxyAudioObject *)
0x1800b90e7  mov     edi, eax
0x1800b90e9  test    eax, eax
0x1800b90eb  jns     short loc_1800B90F4
0x1800b90ed  mov     edx, 0B4h
0x1800b90f2  jmp     short loc_1800B90AA
0x1800b90f4  mov     qword ptr [rsp+0CE0h+var_CA0], r15
0x1800b90f9  lea     rdx, [rsp+0CE0h+var_CA0]
0x1800b90fe  mov     rcx, r14
0x1800b9101  call    ??$CastTo@UXvmActivateAudioSessionEnumerator@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateAudioSessionEnumerator@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateAudioSessionEnumerator>(XvmActivateAudioSessionEnumerator * *)
0x1800b9106  mov     edi, eax
0x1800b9108  test    eax, eax
0x1800b910a  jns     short loc_1800B9113
0x1800b910c  mov     edx, 0B7h
0x1800b9111  jmp     short loc_1800B90AA
0x1800b9113  mov     rax, qword ptr [rsp+0CE0h+var_CA0]
0x1800b9118  mov     ecx, [rax]
0x1800b911a  mov     [rbx+98h], ecx
0x1800b9120  mov     rdi, [rbx+0A8h]
0x1800b9127  mov     [rbx+0A8h], rsi
0x1800b912e  test    rsi, rsi
0x1800b9131  jz      short loc_1800B9142
0x1800b9133  mov     rax, [rsi]
0x1800b9136  mov     rcx, rsi
0x1800b9139  mov     rax, [rax+8]
0x1800b913d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9142  test    rdi, rdi
0x1800b9145  jz      short loc_1800B9157
0x1800b9147  mov     rax, [rdi]
0x1800b914a  mov     rcx, rdi
0x1800b914d  mov     rax, [rax+10h]
0x1800b9151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9156  nop
0x1800b9157  movsxd  rsi, dword ptr [rbx+98h]
0x1800b915e  mov     r14d, 8
0x1800b9164  mov     eax, r14d
0x1800b9167  mul     rsi
0x1800b916a  lea     rcx, [r14-9]
0x1800b916e  cmovb   rax, rcx
0x1800b9172  add     rax, r14
0x1800b9175  cmovb   rax, rcx
0x1800b9179  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b9180  mov     rcx, rax; unsigned __int64
0x1800b9183  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b9188  test    rax, rax
0x1800b918b  jz      short loc_1800B91B7
0x1800b918d  mov     [rax], rsi
0x1800b9190  lea     rdi, [rax+8]
0x1800b9194  lea     rax, ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800b919b  mov     [rsp+0CE0h+var_CC0], rax; void (*)(void *)
0x1800b91a0  lea     r9, ??0?$com_ptr_t@UIAudioSessionControl2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1800b91a7  mov     r8, rsi; unsigned __int64
0x1800b91aa  mov     edx, r14d; unsigned __int64
0x1800b91ad  mov     rcx, rdi; void *
0x1800b91b0  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800b91b5  jmp     short loc_1800B91BA
0x1800b91b7  mov     rdi, r15
0x1800b91ba  mov     rdx, [rbx+0A0h]
0x1800b91c1  mov     [rbx+0A0h], rdi
0x1800b91c8  test    rdx, rdx
0x1800b91cb  jz      short loc_1800B91D2
0x1800b91cd  call    ??$?RV?$com_ptr_t@UIAudioSessionControl2@@Uerr_returncode_policy@wil@@@wil@@$0A@@?$default_delete@$$BY0A@V?$com_ptr_t@UIAudioSessionControl2@@Uerr_returncode_policy@wil@@@wil@@@std@@QEBAXPEAV?$com_ptr_t@UIAudioSessionControl2@@Uerr_returncode_policy@wil@@@wil@@@Z; std::default_delete<wil::com_ptr_t<IAudioSessionControl2,wil::err_returncode_policy> [0]>::operator()<wil::com_ptr_t<IAudioSessionControl2,wil::err_returncode_policy>,0>(wil::com_ptr_t<IAudioSessionControl2,wil::err_returncode_policy> *)
0x1800b91d2  cmp     [rbx+0A0h], r15
0x1800b91d9  jnz     short loc_1800B9220
0x1800b91db  mov     rcx, [rbp+0BE8h]; this
0x1800b91e2  mov     ebx, 8007000Eh
0x1800b91e7  mov     r9d, ebx; char *
0x1800b91ea  lea     r8, aAvcoreAudiocor_73; "avcore\\audiocore\\client\\audioclient"...
0x1800b91f1  mov     edx, 0BDh; void *
0x1800b91f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b91fb  nop
0x1800b91fc  lea     rcx, [rsp+0CE0h+var_CA8]
0x1800b9201  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b9206  nop
0x1800b9207  mov     rcx, [rsp+0CE0h+pv]; pv
0x1800b920c  mov     [rsp+0CE0h+pv], r15
0x1800b9211  test    rcx, rcx
0x1800b9214  jz      short loc_1800B921C
0x1800b9216  call    cs:__imp_CoTaskMemFree
0x1800b921c  mov     eax, ebx
0x1800b921e  jmp     short loc_1800B9242
0x1800b9220  lea     rcx, [rsp+0CE0h+var_CA8]
0x1800b9225  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b922a  nop
0x1800b922b  mov     rcx, [rsp+0CE0h+pv]; pv
0x1800b9230  mov     [rsp+0CE0h+pv], r15
0x1800b9235  test    rcx, rcx
0x1800b9238  jz      short loc_1800B9240
0x1800b923a  call    cs:__imp_CoTaskMemFree
0x1800b9240  xor     eax, eax
0x1800b9242  mov     rcx, [rbp+0BE0h+var_30]
0x1800b9249  xor     rcx, rsp; StackCookie
0x1800b924c  call    __security_check_cookie
0x1800b9251  mov     rbx, [rsp+0CE0h+arg_10]
0x1800b9259  add     rsp, 0CC0h
0x1800b9260  pop     r15
0x1800b9262  pop     r14
0x1800b9264  pop     rdi
0x1800b9265  pop     rsi
0x1800b9266  pop     rbp
0x1800b9267  retn
```
