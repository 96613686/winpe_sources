# CLocationProviderComposite::GetAcquireForSession(ILocationSession *,ILocationAcquire * *)

- ea: `0x180027860`
- end: `0x180027ca1`
- name: `?GetAcquireForSession@CLocationProviderComposite@@UEAAJPEAUILocationSession@@PEAPEAUILocationAcquire@@@Z`
- size: `1089`
- prototype: `__int64 __fastcall(CLocationProviderComposite *__hidden this, struct ILocationSession *, struct ILocationAcquire **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012194`
- `0x180012398`
- `0x18001be08`
- `0x180027860`
- `0x180027ca8`
- `0x18003dda0`
- `0x180054398`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800d0468`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027a69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027963`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027963`

## string_xrefs

- `0x1800279e6`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationprovidercpe.cpp`
- `0x180027b1b`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationprovidercpe.cpp`
- `0x180027b9c`: `onecoreuap\drivers\mobilepc\location\product\core\pe\composite\locationprovidercpe.cpp`
- `0x1800279df`: `CLocationProviderComposite::GetAcquireForSession`
- `0x180027b14`: `CLocationProviderComposite::GetAcquireForSession`
- `0x180027ba3`: `CLocationProviderComposite::GetAcquireForSession`
- `0x1800279d3`: `pAcquire->get_AcquireComponentType(&acquireType)`
- `0x180027b08`: `pSessionInternal->get_UserContext(&sessionUserSid)`
- `0x180027b7e`: `m_cachedAcquires.size() >= MAX_ACQUIREOBJECT_LIMIT`
- `0x180027b90`: `pAcquireComponent->put_AcquireComponentType(desiredAcquireType)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocationProviderComposite::GetAcquireForSession(
        CLocationProviderComposite *this,
        struct ILocationSession *a2,
        struct ILocationAcquire **a3)
{
  int AcquireTypeForRequest; // ebx
  int v7; // eax
  _QWORD *v8; // rdi
  _QWORD *i; // rbx
  struct ILocationAcquire *v10; // rsi
  int v11; // eax
  struct ILocationAcquire *v12; // rax
  const char *v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // esi
  struct ILocationAcquire *v17; // rdi
  __int64 (__fastcall *v18)(struct ILocationAcquire *, CLocationProviderComposite *); // rbx
  int v19; // eax
  wil::details *v20; // [rsp+28h] [rbp-81h]
  int v21; // [rsp+30h] [rbp-79h] BYREF
  char *v22; // [rsp+38h] [rbp-71h] BYREF
  char v23; // [rsp+40h] [rbp-69h]
  __int64 *v24; // [rsp+48h] [rbp-61h]
  __int128 v25[2]; // [rsp+50h] [rbp-59h] BYREF
  int v26; // [rsp+70h] [rbp-39h]
  __int64 v27; // [rsp+80h] [rbp-29h] BYREF
  struct ILocationAcquire *v28; // [rsp+88h] [rbp-21h] BYREF
  CLocationProviderComposite *v29; // [rsp+90h] [rbp-19h] BYREF
  __int64 v30; // [rsp+98h] [rbp-11h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v32; // [rsp+B0h] [rbp+7h]
  int v33; // [rsp+C0h] [rbp+17h]
  wil::details::in1diag5 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( !a2 || !a3 )
    return 2147942487LL;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  *a3 = 0;
  AcquireTypeForRequest = (*(__int64 (__fastcall **)(struct ILocationSession *, __int128 *))(*(_QWORD *)a2 + 72LL))(
                            a2,
                            &v31);
  if ( AcquireTypeForRequest < 0 )
  {
    if ( v28 )
      (*(void (__fastcall **)(struct ILocationAcquire *))(*(_QWORD *)v28 + 16LL))(v28);
    return (unsigned int)AcquireTypeForRequest;
  }
  v27 = 0;
  v30 = 0;
  (**(void (__fastcall ***)(struct ILocationSession *, GUID *, __int64 *))a2)(
    a2,
    &GUID_3f4d1267_2b57_415a_976f_95904cf38334,
    &v30);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 176LL))(v30, &v27);
  AcquireTypeForRequest = v7;
  if ( v7 < 0 )
  {
    LODWORD(v20) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationprovidercpe.cpp",
      "CLocationProviderComposite::GetAcquireForSession",
      "pSessionInternal->get_UserContext(&sessionUserSid)",
      v20,
      v21);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v28 )
      (*(void (__fastcall **)(struct ILocationAcquire *))(*(_QWORD *)v28 + 16LL))(v28);
    return (unsigned int)AcquireTypeForRequest;
  }
  v21 = 0;
  v25[0] = v31;
  v25[1] = v32;
  v26 = v33;
  AcquireTypeForRequest = CLocationProviderComposite::GetAcquireTypeForRequest(
                            (__int64)this,
                            v25,
                            v27,
                            (unsigned int *)&v21);
  if ( AcquireTypeForRequest < 0 )
  {
LABEL_41:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
    return (unsigned int)AcquireTypeForRequest;
  }
  v22 = (char *)this + 632;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  v23 = 1;
  if ( *((_BYTE *)this + 609) )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v22);
    AcquireTypeForRequest = -2147467260;
    goto LABEL_41;
  }
  v24 = (__int64 *)((char *)this + 616);
  v8 = (_QWORD *)*((_QWORD *)this + 77);
  for ( i = (_QWORD *)*v8; ; i = (_QWORD *)*i )
  {
    if ( i == v8 )
    {
      v12 = v28;
      goto LABEL_19;
    }
    v10 = (struct ILocationAcquire *)i[2];
    if ( v10 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(i[2]);
    LODWORD(v29) = 0;
    v11 = (*(__int64 (__fastcall **)(struct ILocationAcquire *, CLocationProviderComposite **))(*(_QWORD *)v10 + 64LL))(
            v10,
            &v29);
    if ( v11 < 0 )
    {
      LODWORD(v20) = v11;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x218,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationprovidercpe.cpp",
        "CLocationProviderComposite::GetAcquireForSession",
        "pAcquire->get_AcquireComponentType(&acquireType)",
        (const char *)v20,
        v21);
    }
    if ( (_DWORD)v29 == v21
      && (*(int (__fastcall **)(struct ILocationAcquire *, struct ILocationSession *))(*(_QWORD *)v10 + 24LL))(v10, a2) >= 0 )
    {
      break;
    }
    (*(void (__fastcall **)(struct ILocationAcquire *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v12 = v28;
  if ( v28 != v10 )
  {
    (*(void (__fastcall **)(struct ILocationAcquire *))(*(_QWORD *)v10 + 8LL))(v10);
    if ( v28 )
      (*(void (__fastcall **)(struct ILocationAcquire *))(*(_QWORD *)v28 + 16LL))(v28);
    v12 = v10;
    v28 = v10;
  }
LABEL_19:
  if ( v12 )
    goto LABEL_20;
  if ( *((_QWORD *)this + 78) >= 0x32u )
  {
    AcquireTypeForRequest = -2147467260;
    LODWORD(v20) = -2147467260;
    v14 = "m_cachedAcquires.size() >= MAX_ACQUIREOBJECT_LIMIT";
    v15 = 550;
LABEL_39:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\pe\\composite\\locationprovidercpe.cpp",
      "CLocationProviderComposite::GetAcquireForSession",
      v14,
      v20,
      v21);
LABEL_40:
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v22);
    goto LABEL_41;
  }
  v16 = v21;
  AcquireTypeForRequest = LocationHelper::CreateLocationComponent((unsigned int)v21, &IID_ILocationAcquire, &v28);
  if ( AcquireTypeForRequest < 0 )
    goto LABEL_40;
  v17 = v28;
  v18 = *(__int64 (__fastcall **)(struct ILocationAcquire *, CLocationProviderComposite *))(*(_QWORD *)v28 + 40LL);
  v29 = this;
  (*(void (__fastcall **)(CLocationProviderComposite *))(*(_QWORD *)this + 8LL))(this);
  AcquireTypeForRequest = v18(v17, this);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  if ( AcquireTypeForRequest < 0 )
    goto LABEL_40;
  v19 = (*(__int64 (__fastcall **)(struct ILocationAcquire *, _QWORD))(*(_QWORD *)v28 + 56LL))(v28, v16);
  AcquireTypeForRequest = v19;
  if ( v19 < 0 )
  {
    LODWORD(v20) = v19;
    v14 = "pAcquireComponent->put_AcquireComponentType(desiredAcquireType)";
    v15 = 559;
    goto LABEL_39;
  }
  AcquireTypeForRequest = (*(__int64 (__fastcall **)(struct ILocationAcquire *, struct ILocationSession *))(*(_QWORD *)v28 + 24LL))(
                            v28,
                            a2);
  if ( AcquireTypeForRequest < 0 )
    goto LABEL_40;
  ATL::CAdapt<ATL::CComPtr<ILocationAdapterBluetoothSink>>::CAdapt<ATL::CComPtr<ILocationAdapterBluetoothSink>>(
    &v29,
    &v28);
  std::list<ATL::CAdapt<ATL::CComPtr<ILocationAcquire>>>::_Emplace<ATL::CAdapt<ATL::CComPtr<ILocationAcquire>>>(
    (__int64)v24,
    *v24,
    (__int64)&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  v12 = v28;
LABEL_20:
  v28 = 0;
  *a3 = v12;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v28 )
    (*(void (__fastcall **)(struct ILocationAcquire *))(*(_QWORD *)v28 + 16LL))(v28);
  return 0;
}

```

## disassembly

```asm
0x180027860  mov     [rsp-8+arg_18], rbx
0x180027865  push    rbp
0x180027866  push    rsi
0x180027867  push    rdi
0x180027868  push    r12
0x18002786a  push    r13
0x18002786c  push    r14
0x18002786e  push    r15
0x180027870  lea     rbp, [rsp-27h]
0x180027875  sub     rsp, 0D0h
0x18002787c  mov     rax, cs:__security_cookie
0x180027883  xor     rax, rsp
0x180027886  mov     [rbp+57h+var_38], rax
0x18002788a  mov     r13, r8
0x18002788d  mov     r15, rdx
0x180027890  mov     r14, rcx
0x180027893  xor     edi, edi
0x180027895  test    rdx, rdx
0x180027898  jz      loc_180027C97
0x18002789e  test    r8, r8
0x1800278a1  jz      loc_180027C97
0x1800278a7  mov     [rbp+57h+var_78], rdi
0x1800278ab  xorps   xmm0, xmm0
0x1800278ae  xor     eax, eax
0x1800278b0  movups  [rbp+57h+var_60], xmm0
0x1800278b4  movups  [rbp+57h+var_50], xmm0
0x1800278b8  mov     [rbp+57h+var_40], eax
0x1800278bb  mov     [r8], rdi
0x1800278be  mov     rax, [rdx]
0x1800278c1  lea     rdx, [rbp+57h+var_60]
0x1800278c5  mov     rcx, r15
0x1800278c8  mov     rax, [rax+48h]
0x1800278cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278d1  mov     ebx, eax
0x1800278d3  test    eax, eax
0x1800278d5  js      loc_180027ADD
0x1800278db  mov     [rbp+57h+var_80], rdi
0x1800278df  mov     [rbp+57h+var_68], rdi
0x1800278e3  mov     rax, [r15]
0x1800278e6  lea     r8, [rbp+57h+var_68]
0x1800278ea  lea     rdx, _GUID_3f4d1267_2b57_415a_976f_95904cf38334
0x1800278f1  mov     rcx, r15
0x1800278f4  mov     rax, [rax]
0x1800278f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278fc  nop
0x1800278fd  mov     rcx, [rbp+57h+var_68]
0x180027901  mov     rax, [rcx]
0x180027904  lea     rdx, [rbp+57h+var_80]
0x180027908  mov     rax, [rax+0B0h]
0x18002790f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027914  mov     ebx, eax
0x180027916  test    eax, eax
0x180027918  js      loc_180027B00
0x18002791e  mov     [rbp+57h+var_D0], edi
0x180027921  movups  xmm0, [rbp+57h+var_60]
0x180027925  movaps  [rbp+57h+var_B0], xmm0
0x180027929  movups  xmm1, [rbp+57h+var_50]
0x18002792d  movaps  [rbp+57h+var_A0], xmm1
0x180027931  mov     eax, [rbp+57h+var_40]
0x180027934  mov     [rbp+57h+var_90], eax
0x180027937  lea     r9, [rbp+57h+var_D0]
0x18002793b  mov     r8, [rbp+57h+var_80]
0x18002793f  lea     rdx, [rbp+57h+var_B0]
0x180027943  mov     rcx, r14
0x180027946  call    ?GetAcquireTypeForRequest@CLocationProviderComposite@@AEAAJULOCATIONREQUEST@@PEAGPEAW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@@Z; CLocationProviderComposite::GetAcquireTypeForRequest(LOCATIONREQUEST,ushort *,__MIDL___MIDL_itf_locationframework_0000_0000_0001 *)
0x18002794b  mov     ebx, eax
0x18002794d  test    eax, eax
0x18002794f  js      loc_180027BC1
0x180027955  lea     r12, [r14+278h]
0x18002795c  mov     [rbp+57h+var_C8], r12
0x180027960  mov     rcx, r12; lpCriticalSection
0x180027963  call    cs:__imp_EnterCriticalSection
0x180027969  mov     [rbp+57h+var_C0], 1
0x18002796d  cmp     [r14+261h], dil
0x180027974  jnz     loc_180027B5B
0x18002797a  lea     rsi, [r14+268h]
0x180027981  mov     [rbp+57h+var_B8], rsi
0x180027985  mov     rdi, [rsi]
0x180027988  mov     rbx, [rdi]
0x18002798b  cmp     rbx, rdi
0x18002798e  jz      loc_180027AF7
0x180027994  mov     rsi, [rbx+10h]
0x180027998  test    rsi, rsi
0x18002799b  jz      short loc_1800279AD
0x18002799d  mov     rax, [rsi]
0x1800279a0  mov     rcx, rsi
0x1800279a3  mov     rax, [rax+8]
0x1800279a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279ac  nop
0x1800279ad  mov     dword ptr [rbp+57h+var_70], 0
0x1800279b4  mov     rax, [rsi]
0x1800279b7  lea     rdx, [rbp+57h+var_70]
0x1800279bb  mov     rcx, rsi
0x1800279be  mov     rax, [rax+40h]
0x1800279c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279c7  mov     rcx, [rbp+5Fh]; this
0x1800279cb  test    eax, eax
0x1800279cd  jns     short loc_1800279F7
0x1800279cf  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x1800279d3  lea     rax, aPacquireGetAcq; "pAcquire->get_AcquireComponentType(&acq"...
0x1800279da  mov     [rsp+100h+var_E0], rax; char *
0x1800279df  lea     r9, aClocationprovi_1; "CLocationProviderComposite::GetAcquireF"...
0x1800279e6  lea     r8, aOnecoreuapDriv_53; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800279ed  mov     edx, 218h; void *
0x1800279f2  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800279f7  mov     eax, [rbp+57h+var_D0]
0x1800279fa  cmp     dword ptr [rbp+57h+var_70], eax
0x1800279fd  jnz     loc_180027AC5
0x180027a03  mov     rax, [rsi]
0x180027a06  mov     rdx, r15
0x180027a09  mov     rcx, rsi
0x180027a0c  mov     rax, [rax+18h]
0x180027a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a15  test    eax, eax
0x180027a17  js      loc_180027AC5
0x180027a1d  mov     rax, [rbp+57h+var_78]
0x180027a21  cmp     rax, rsi
0x180027a24  jz      short loc_180027A51
0x180027a26  mov     rax, [rsi]
0x180027a29  mov     rcx, rsi
0x180027a2c  mov     rax, [rax+8]
0x180027a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a35  mov     rcx, [rbp+57h+var_78]
0x180027a39  test    rcx, rcx
0x180027a3c  jz      short loc_180027A4A
0x180027a3e  mov     rax, [rcx]
0x180027a41  mov     rax, [rax+10h]
0x180027a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a4a  mov     rax, rsi
0x180027a4d  mov     [rbp+57h+var_78], rax
0x180027a51  test    rax, rax
0x180027a54  jz      loc_180027B6B
0x180027a5a  mov     [rbp+57h+var_78], 0
0x180027a62  mov     [r13+0], rax
0x180027a66  mov     rcx, r12; lpCriticalSection
0x180027a69  call    cs:__imp_LeaveCriticalSection
0x180027a6f  nop
0x180027a70  mov     rcx, [rbp+57h+var_68]
0x180027a74  test    rcx, rcx
0x180027a77  jz      short loc_180027A86
0x180027a79  mov     rax, [rcx]
0x180027a7c  mov     rax, [rax+10h]
0x180027a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a85  nop
0x180027a86  mov     rcx, [rbp+57h+var_78]
0x180027a8a  test    rcx, rcx
0x180027a8d  jz      short loc_180027A9C
0x180027a8f  mov     rax, [rcx]
0x180027a92  mov     rax, [rax+10h]
0x180027a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a9b  nop
0x180027a9c  xor     eax, eax
0x180027a9e  mov     rcx, [rbp+57h+var_38]
0x180027aa2  xor     rcx, rsp; StackCookie
0x180027aa5  call    __security_check_cookie
0x180027aaa  mov     rbx, [rsp+100h+arg_18]
0x180027ab2  add     rsp, 0D0h
0x180027ab9  pop     r15
0x180027abb  pop     r14
0x180027abd  pop     r13
0x180027abf  pop     r12
0x180027ac1  pop     rdi
0x180027ac2  pop     rsi
0x180027ac3  pop     rbp
0x180027ac4  retn
0x180027ac5  mov     rax, [rsi]
0x180027ac8  mov     rcx, rsi
0x180027acb  mov     rax, [rax+10h]
0x180027acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ad4  nop
0x180027ad5  mov     rbx, [rbx]
0x180027ad8  jmp     loc_18002798B
0x180027add  mov     rcx, [rbp+57h+var_78]
0x180027ae1  test    rcx, rcx
0x180027ae4  jz      short loc_180027AF3
0x180027ae6  mov     rdx, [rcx]
0x180027ae9  mov     rax, [rdx+10h]
0x180027aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027af2  nop
0x180027af3  mov     eax, ebx
0x180027af5  jmp     short loc_180027A9E
0x180027af7  mov     rax, [rbp+57h+var_78]
0x180027afb  jmp     loc_180027A51
0x180027b00  mov     rcx, [rbp+5Fh]; this
0x180027b04  mov     dword ptr [rsp+100h+var_D8], ebx; wil::details *
0x180027b08  lea     rax, aPsessionintern; "pSessionInternal->get_UserContext(&sess"...
0x180027b0f  mov     [rsp+100h+var_E0], rax; char *
0x180027b14  lea     r9, aClocationprovi_1; "CLocationProviderComposite::GetAcquireF"...
0x180027b1b  lea     r8, aOnecoreuapDriv_53; "onecoreuap\\drivers\\mobilepc\\location"...
0x180027b22  mov     edx, 207h; void *
0x180027b27  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180027b2c  nop
0x180027b2d  mov     rcx, [rbp+57h+var_68]
0x180027b31  test    rcx, rcx
0x180027b34  jz      short loc_180027B43
0x180027b36  mov     rax, [rcx]
0x180027b39  mov     rax, [rax+10h]
0x180027b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b42  nop
0x180027b43  mov     rcx, [rbp+57h+var_78]
0x180027b47  test    rcx, rcx
0x180027b4a  jz      short loc_180027B59
0x180027b4c  mov     rax, [rcx]
0x180027b4f  mov     rax, [rax+10h]
0x180027b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b58  nop
0x180027b59  jmp     short loc_180027AF3
0x180027b5b  lea     rcx, [rbp+57h+var_C8]
0x180027b5f  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180027b64  mov     ebx, 80004004h
0x180027b69  jmp     short loc_180027BC1
0x180027b6b  cmp     qword ptr [r14+270h], 32h ; '2'
0x180027b73  jb      short loc_180027BD8
0x180027b75  mov     ebx, 80004004h
0x180027b7a  mov     dword ptr [rsp+100h+var_D8], ebx
0x180027b7e  lea     rax, aMCachedacquire; "m_cachedAcquires.size() >= MAX_ACQUIREO"...
0x180027b85  mov     edx, 226h
0x180027b8a  jmp     short loc_180027B9C
0x180027b8c  mov     dword ptr [rsp+100h+var_D8], eax; wil::details *
0x180027b90  lea     rax, aPacquirecompon; "pAcquireComponent->put_AcquireComponent"...
0x180027b97  mov     edx, 22Fh; void *
0x180027b9c  lea     r8, aOnecoreuapDriv_53; "onecoreuap\\drivers\\mobilepc\\location"...
0x180027ba3  lea     r9, aClocationprovi_1; "CLocationProviderComposite::GetAcquireF"...
0x180027baa  mov     [rsp+100h+var_E0], rax; char *
0x180027baf  mov     rcx, [rbp+5Fh]; this
0x180027bb3  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180027bb8  lea     rcx, [rbp+57h+var_C8]
0x180027bbc  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180027bc1  lea     rcx, [rbp+57h+var_68]
0x180027bc5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027bca  lea     rcx, [rbp+57h+var_78]
0x180027bce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027bd3  jmp     loc_180027AF3
0x180027bd8  lea     r8, [rbp+57h+var_78]
0x180027bdc  lea     rdx, IID_ILocationAcquire
0x180027be3  mov     esi, [rbp+57h+var_D0]
0x180027be6  mov     ecx, esi
0x180027be8  call    ?CreateLocationComponent@LocationHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; LocationHelper::CreateLocationComponent(__MIDL___MIDL_itf_locationframework_0000_0000_0001,_GUID const &,IUnknown * *)
0x180027bed  mov     ebx, eax
0x180027bef  test    eax, eax
0x180027bf1  js      short loc_180027BB8
0x180027bf3  mov     rdi, [rbp+57h+var_78]
0x180027bf7  mov     rax, [rdi]
0x180027bfa  mov     rbx, [rax+28h]
0x180027bfe  mov     [rbp+57h+var_70], r14
0x180027c02  mov     r8, [r14]
0x180027c05  mov     rcx, r14
0x180027c08  mov     rax, [r8+8]
0x180027c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c11  nop
0x180027c12  mov     rdx, r14
0x180027c15  mov     rcx, rdi
0x180027c18  mov     rax, rbx
0x180027c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c20  mov     ebx, eax
0x180027c22  lea     rcx, [rbp+57h+var_70]
0x180027c26  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027c2b  test    ebx, ebx
0x180027c2d  js      short loc_180027BB8
0x180027c2f  mov     rcx, [rbp+57h+var_78]
0x180027c33  mov     rax, [rcx]
0x180027c36  mov     edx, esi
0x180027c38  mov     rax, [rax+38h]
0x180027c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c41  mov     ebx, eax
0x180027c43  test    eax, eax
0x180027c45  js      loc_180027B8C
0x180027c4b  mov     rcx, [rbp+57h+var_78]
0x180027c4f  mov     rax, [rcx]
0x180027c52  mov     rdx, r15
0x180027c55  mov     rax, [rax+18h]
0x180027c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c5e  mov     ebx, eax
0x180027c60  test    eax, eax
0x180027c62  js      loc_180027BB8
0x180027c68  lea     rdx, [rbp+57h+var_78]
0x180027c6c  lea     rcx, [rbp+57h+var_70]
0x180027c70  call    ??0?$CAdapt@V?$CComPtr@UILocationAdapterBluetoothSink@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CAdapt<ATL::CComPtr<ILocationAdapterBluetoothSink>>::CAdapt<ATL::CComPtr<ILocationAdapterBluetoothSink>>(ATL::CAdapt<ATL::CComPtr<ILocationAdapterBluetoothSink>> const &)
0x180027c75  lea     r8, [rbp+57h+var_70]
0x180027c79  mov     rcx, [rbp+57h+var_B8]
0x180027c7d  mov     rdx, [rcx]
0x180027c80  call    ??$_Emplace@V?$CAdapt@V?$CComPtr@UILocationAcquire@@@ATL@@@ATL@@@?$list@V?$CAdapt@V?$CComPtr@UILocationAcquire@@@ATL@@@ATL@@V?$allocator@V?$CAdapt@V?$CComPtr@UILocationAcquire@@@ATL@@@ATL@@@std@@@std@@QEAAPEAU?$_List_node@V?$CAdapt@V?$CComPtr@UILocationAcquire@@@ATL@@@ATL@@PEAX@1@QEAU21@$$QEAV?$CAdapt@V?$CComPtr@UILocationAcquire@@@ATL@@@ATL@@@Z; std::list<ATL::CAdapt<ATL::CComPtr<ILocationAcquire>>>::_Emplace<ATL::CAdapt<ATL::CComPtr<ILocationAcquire>>>(std::_List_node<ATL::CAdapt<ATL::CComPtr<ILocationAcquire>>,void *> * const,ATL::CAdapt<ATL::CComPtr<ILocationAcquire>> &&)
0x180027c85  lea     rcx, [rbp+57h+var_70]
0x180027c89  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027c8e  mov     rax, [rbp+57h+var_78]
0x180027c92  jmp     loc_180027A5A
0x180027c97  mov     eax, 80070057h
0x180027c9c  jmp     loc_180027A9E
```
