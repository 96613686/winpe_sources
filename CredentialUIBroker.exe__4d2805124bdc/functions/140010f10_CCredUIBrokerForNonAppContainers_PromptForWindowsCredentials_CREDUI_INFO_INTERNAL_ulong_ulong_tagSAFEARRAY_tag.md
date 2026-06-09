# CCredUIBrokerForNonAppContainers::PromptForWindowsCredentials(CREDUI_INFO_INTERNAL *,ulong,ulong *,tagSAFEARRAY *,tagSAFEARRAY * *,int *,ulong,ulong *)

- ea: `0x140010f10`
- end: `0x1400110f9`
- name: `?PromptForWindowsCredentials@CCredUIBrokerForNonAppContainers@@UEAAJPEAUCREDUI_INFO_INTERNAL@@KPEAKPEAUtagSAFEARRAY@@PEAPEAU3@PEAHK1@Z`
- size: `489`
- prototype: `__int64 __fastcall(struct IUnknown *this, struct CREDUI_INFO_INTERNAL *, unsigned int, unsigned int *, struct tagSAFEARRAY *psa, struct tagSAFEARRAY **cElements, int *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140003620`
- `0x1400042c4`
- `0x140007b20`
- `0x140009280`
- `0x14000c8b0`
- `0x14000f14c`
- `0x140010f10`
- `0x140014730`
- `0x140014eb0`
- `0x140017e88`
- `0x140017fc0`
- `0x14001d968`

## string_xrefs

- `0x140010f4e`: `BrokerForNonAppContainersActivity`

## pseudocode

```c
__int64 __fastcall CCredUIBrokerForNonAppContainers::PromptForWindowsCredentials(
        struct IUnknown *this,
        struct CREDUI_INFO_INTERNAL *a2,
        unsigned int a3,
        unsigned int *a4,
        struct tagSAFEARRAY *psa,
        struct tagSAFEARRAY **cElements,
        int *a7,
        unsigned int a8,
        unsigned int *a9)
{
  CCredUIBrokerBase *v12; // rcx
  struct IUnknown *v13; // r9
  HWND v14; // rax
  HWND v15; // rdx
  int v16; // edi
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  unsigned int BufferSize; // ebx
  unsigned int v26; // eax
  bool v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-ACh]
  int *v30; // [rsp+58h] [rbp-A8h]
  _OWORD v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+E0h] [rbp-20h]
  _QWORD v33[42]; // [rsp+F0h] [rbp-10h] BYREF

  v30 = a7;
  v29 = a3;
  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v33);
  v33[0] = &CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::`vftable';
  CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::StartActivity((CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *)v33);
  LogOwnerWindowTelemetry(a2);
  memset_0(v31, 0, 0x88u);
  if ( !a2 )
    goto LABEL_9;
  v14 = (HWND)*((_QWORD *)a2 + 1);
  if ( !v14 )
    goto LABEL_9;
  v15 = (HWND)*((_QWORD *)a2 + 12);
  if ( !v15 )
  {
    v28 = 0;
    if ( CCredUIBrokerBase::_IsHWNDFromElevatedProcess(v12, v14, &v28) < 0 || v28 )
    {
      v17 = *(_OWORD *)a2;
      v18 = *((_OWORD *)a2 + 1);
      v32 = *((_QWORD *)a2 + 16);
      v31[0] = (unsigned __int64)v17;
      v19 = *((_OWORD *)a2 + 2);
      v31[1] = v18;
      v20 = *((_OWORD *)a2 + 3);
      v31[2] = v19;
      v21 = *((_OWORD *)a2 + 4);
      v31[3] = v20;
      v22 = *((_OWORD *)a2 + 5);
      v31[4] = v21;
      v23 = *((_OWORD *)a2 + 6);
      v31[5] = v22;
      v24 = *((_OWORD *)a2 + 7);
      a2 = (struct CREDUI_INFO_INTERNAL *)v31;
      v31[6] = v23;
      v31[7] = v24;
    }
    goto LABEL_9;
  }
  v16 = CallerIdentity::VerifyWindowIsInSpecifiedApplication(*((CallerIdentity **)a2 + 1), v15, 0, v13);
  if ( v16 >= 0 )
LABEL_9:
    v16 = CCredUIBrokerBase::_PromptForWindowsCredentials(
            (CCredUIBrokerBase *)&this[2],
            this,
            a2,
            v29,
            a4,
            psa,
            (ULONG)cElements,
            v30,
            a8,
            a9);
  BufferSize = GetBufferSize(psa);
  v26 = GetBufferSize(*cElements);
  CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::Stop(
    (CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *)v33,
    v16,
    a8,
    *a4,
    *a9,
    BufferSize,
    v26);
  CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::~BrokerForNonAppContainersActivity((CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *)v33);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140010f10  push    rbp
0x140010f12  push    rbx
0x140010f13  push    rsi
0x140010f14  push    rdi
0x140010f15  push    r12
0x140010f17  push    r13
0x140010f19  push    r14
0x140010f1b  push    r15
0x140010f1d  lea     rbp, [rsp-158h]
0x140010f25  sub     rsp, 258h
0x140010f2c  mov     rax, cs:__security_cookie
0x140010f33  xor     rax, rsp
0x140010f36  mov     [rbp+190h+var_50], rax
0x140010f3d  mov     rax, [rbp+190h+arg_30]
0x140010f44  mov     rbx, rdx
0x140010f47  mov     r15, [rbp+190h+psa]
0x140010f4e  lea     rdx, aBrokerfornonap; "BrokerForNonAppContainersActivity"
0x140010f55  mov     r12, [rbp+190h+arg_28]
0x140010f5c  mov     rsi, rcx
0x140010f5f  mov     r13, [rbp+190h+arg_40]
0x140010f66  lea     rcx, [rbp+190h+var_1A0]; struct wil::details::IFailureCallback *
0x140010f6a  mov     [rsp+290h+var_238], rax
0x140010f6f  mov     r14, r9
0x140010f72  mov     [rsp+290h+var_23C], r8d
0x140010f77  call    ??0?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140010f7c  lea     rax, ??_7BrokerForNonAppContainersActivity@CredUIBrokerTelemetry@@6B@; const CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::`vftable'
0x140010f83  lea     rcx, [rbp+190h+var_1A0]; this
0x140010f87  mov     [rbp+190h+var_1A0], rax
0x140010f8b  call    ?StartActivity@BrokerForNonAppContainersActivity@CredUIBrokerTelemetry@@QEAAXXZ; CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::StartActivity(void)
0x140010f90  mov     rcx, rbx; struct CREDUI_INFO_INTERNAL *
0x140010f93  call    ?LogOwnerWindowTelemetry@@YAXPEAUCREDUI_INFO_INTERNAL@@@Z; LogOwnerWindowTelemetry(CREDUI_INFO_INTERNAL *)
0x140010f98  xor     edx, edx; Val
0x140010f9a  lea     rcx, [rsp+290h+var_230]; void *
0x140010f9f  mov     r8d, 88h; Size
0x140010fa5  call    memset_0
0x140010faa  xor     edi, edi
0x140010fac  test    rbx, rbx
0x140010faf  jz      loc_140011055
0x140010fb5  mov     rax, [rbx+8]
0x140010fb9  test    rax, rax
0x140010fbc  jz      loc_140011055
0x140010fc2  mov     rdx, [rbx+60h]; HWND
0x140010fc6  test    rdx, rdx
0x140010fc9  jz      short loc_140010FE2
0x140010fcb  xor     r8d, r8d; unsigned __int16 *
0x140010fce  mov     rcx, rax; this
0x140010fd1  call    ?VerifyWindowIsInSpecifiedApplication@CallerIdentity@@YAJPEAUHWND__@@PEBGPEAUIUnknown@@@Z; CallerIdentity::VerifyWindowIsInSpecifiedApplication(HWND__ *,ushort const *,IUnknown *)
0x140010fd6  mov     edi, eax
0x140010fd8  test    eax, eax
0x140010fda  js      loc_140011093
0x140010fe0  jmp     short loc_140011055
0x140010fe2  lea     r8, [rsp+290h+var_240]; bool *
0x140010fe7  mov     [rsp+290h+var_240], dil
0x140010fec  mov     rdx, rax; HWND
0x140010fef  call    ?_IsHWNDFromElevatedProcess@CCredUIBrokerBase@@IEAAJPEAUHWND__@@PEA_N@Z; CCredUIBrokerBase::_IsHWNDFromElevatedProcess(HWND__ *,bool *)
0x140010ff4  test    eax, eax
0x140010ff6  js      short loc_140010FFF
0x140010ff8  cmp     [rsp+290h+var_240], dil
0x140010ffd  jz      short loc_140011055
0x140010fff  movups  xmm0, xmmword ptr [rbx]
0x140011002  mov     rax, [rbx+80h]
0x140011009  movups  xmm1, xmmword ptr [rbx+10h]
0x14001100d  mov     [rbp+190h+var_1B0], rax
0x140011011  movups  [rsp+290h+var_230], xmm0
0x140011016  mov     qword ptr [rsp+290h+var_230+8], rdi
0x14001101b  movups  xmm0, xmmword ptr [rbx+20h]
0x14001101f  movups  [rsp+290h+var_220], xmm1
0x140011024  movups  xmm1, xmmword ptr [rbx+30h]
0x140011028  movups  [rbp+190h+var_210], xmm0
0x14001102c  movups  xmm0, xmmword ptr [rbx+40h]
0x140011030  movups  [rbp+190h+var_200], xmm1
0x140011034  movups  xmm1, xmmword ptr [rbx+50h]
0x140011038  movups  [rbp+190h+var_1F0], xmm0
0x14001103c  movups  xmm0, xmmword ptr [rbx+60h]
0x140011040  movups  [rbp+190h+var_1E0], xmm1
0x140011044  movups  xmm1, xmmword ptr [rbx+70h]
0x140011048  lea     rbx, [rsp+290h+var_230]
0x14001104d  movups  [rbp+190h+var_1D0], xmm0
0x140011051  movups  [rbp+190h+var_1C0], xmm1
0x140011055  mov     eax, [rbp+190h+arg_38]
0x14001105b  lea     rcx, [rsi+10h]; this
0x14001105f  mov     r9d, [rsp+290h+var_23C]; unsigned int
0x140011064  mov     r8, rbx; struct CREDUI_INFO_INTERNAL *
0x140011067  mov     [rsp+290h+var_248], r13; unsigned int *
0x14001106c  mov     rdx, rsi; struct IUnknown *
0x14001106f  mov     [rsp+290h+var_250], eax; unsigned int
0x140011073  mov     rax, [rsp+290h+var_238]
0x140011078  mov     [rsp+290h+var_258], rax; int *
0x14001107d  mov     qword ptr [rsp+290h+cElements], r12; cElements
0x140011082  mov     [rsp+290h+var_268], r15; psa
0x140011087  mov     [rsp+290h+var_270], r14; unsigned int *
0x14001108c  call    ?_PromptForWindowsCredentials@CCredUIBrokerBase@@IEAAJPEAUIUnknown@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEAUtagSAFEARRAY@@PEAPEAU4@PEAHK2@Z; CCredUIBrokerBase::_PromptForWindowsCredentials(IUnknown *,CREDUI_INFO_INTERNAL *,ulong,ulong *,tagSAFEARRAY *,tagSAFEARRAY * *,int *,ulong,ulong *)
0x140011091  mov     edi, eax
0x140011093  mov     rcx, r15; psa
0x140011096  call    ?GetBufferSize@@YAKPEAUtagSAFEARRAY@@@Z; GetBufferSize(tagSAFEARRAY *)
0x14001109b  mov     rcx, [r12]; psa
0x14001109f  mov     ebx, eax
0x1400110a1  call    ?GetBufferSize@@YAKPEAUtagSAFEARRAY@@@Z; GetBufferSize(tagSAFEARRAY *)
0x1400110a6  mov     ecx, [r13+0]
0x1400110aa  mov     edx, edi; int
0x1400110ac  mov     r9d, [r14]; unsigned int
0x1400110af  mov     r8d, [rbp+190h+arg_38]; unsigned int
0x1400110b6  mov     [rsp+290h+cElements], eax; unsigned int
0x1400110ba  mov     dword ptr [rsp+290h+var_268], ebx; unsigned int
0x1400110be  mov     dword ptr [rsp+290h+var_270], ecx; unsigned int
0x1400110c2  lea     rcx, [rbp+190h+var_1A0]; this
0x1400110c6  call    ?Stop@BrokerForNonAppContainersActivity@CredUIBrokerTelemetry@@QEAAXJKKKKK@Z; CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::Stop(long,ulong,ulong,ulong,ulong,ulong)
0x1400110cb  lea     rcx, [rbp+190h+var_1A0]; this
0x1400110cf  call    ??1BrokerForNonAppContainersActivity@CredUIBrokerTelemetry@@QEAA@XZ; CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::~BrokerForNonAppContainersActivity(void)
0x1400110d4  mov     eax, edi
0x1400110d6  mov     rcx, [rbp+190h+var_50]
0x1400110dd  xor     rcx, rsp; StackCookie
0x1400110e0  call    __security_check_cookie
0x1400110e5  add     rsp, 258h
0x1400110ec  pop     r15
0x1400110ee  pop     r14
0x1400110f0  pop     r13
0x1400110f2  pop     r12
0x1400110f4  pop     rdi
0x1400110f5  pop     rsi
0x1400110f6  pop     rbx
0x1400110f7  pop     rbp
0x1400110f8  retn
```
