# ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::Stop(ushort const *,int,__int64,long)

- ea: `0x1800169c0`
- end: `0x180016e3e`
- name: `?Stop@AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBGH_JJ@Z`
- size: `1150`
- prototype: `void __fastcall(ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *__hidden this, const unsigned __int16 *, int, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180014c5c`

## callees

- `0x18000163c`
- `0x1800018c0`
- `0x1800045b0`
- `0x180015898`
- `0x1800159d4`
- `0x180015a50`
- `0x180016284`
- `0x1800169c0`
- `0x180017488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016a43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016a43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016c5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016cdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016cdc`

## string_xrefs

- `0x180016a96`: `taskArgument null`
- `0x180016caf`: `taskArgument null`

## pseudocode

```c
void __fastcall ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::Stop(
        ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *this,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        int a5)
{
  __int64 v5; // rdi
  int v10; // eax
  __int64 v11; // rdi
  RTL_SRWLOCK *v12; // rcx
  const struct _tlgProvider_t *v13; // rax
  const struct _tlgProvider_t *v14; // r14
  __int64 v15; // rax
  _QWORD *AutopilotCorrelationVector; // rax
  int v17; // r9d
  __int64 v18; // r8
  RTL_SRWLOCK *v19; // rcx
  const struct _tlgProvider_t *v20; // rax
  const struct _tlgProvider_t *v21; // r14
  __int64 v22; // rax
  __int64 v23; // rax
  const unsigned __int16 *v24; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // ecx
  int v30; // [rsp+D0h] [rbp-80h] BYREF
  DWORD v31; // [rsp+D4h] [rbp-7Ch] BYREF
  int v32; // [rsp+D8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-70h] BYREF
  PSRWLOCK v34; // [rsp+E8h] [rbp-68h] BYREF
  int v35; // [rsp+F0h] [rbp-60h] BYREF
  int v36; // [rsp+F4h] [rbp-5Ch] BYREF
  int v37; // [rsp+F8h] [rbp-58h] BYREF
  int v38; // [rsp+FCh] [rbp-54h] BYREF
  __int64 v39; // [rsp+100h] [rbp-50h] BYREF
  __int64 v40; // [rsp+108h] [rbp-48h] BYREF
  __int64 v41; // [rsp+110h] [rbp-40h] BYREF
  __int64 v42; // [rsp+118h] [rbp-38h] BYREF
  const unsigned __int16 *v43; // [rsp+120h] [rbp-30h] BYREF
  _QWORD *v44; // [rsp+128h] [rbp-28h] BYREF
  __int64 v45; // [rsp+130h] [rbp-20h] BYREF
  __int64 v46; // [rsp+138h] [rbp-18h] BYREF
  __int64 v47; // [rsp+140h] [rbp-10h] BYREF
  __int64 v48; // [rsp+148h] [rbp-8h] BYREF
  __int64 v49; // [rsp+150h] [rbp+0h] BYREF
  __int64 v50; // [rsp+158h] [rbp+8h] BYREF
  __int64 v51; // [rsp+160h] [rbp+10h] BYREF
  _BYTE v52[40]; // [rsp+168h] [rbp+18h] BYREF
  char v53[32]; // [rsp+190h] [rbp+40h] BYREF
  __int64 *v54; // [rsp+1B0h] [rbp+60h]
  __int64 v55; // [rsp+1B8h] [rbp+68h]
  int *v56; // [rsp+1C0h] [rbp+70h]
  __int64 v57; // [rsp+1C8h] [rbp+78h]
  DWORD *v58; // [rsp+1D0h] [rbp+80h]
  __int64 v59; // [rsp+1D8h] [rbp+88h]
  const unsigned __int16 *v60; // [rsp+1E0h] [rbp+90h]
  int v61; // [rsp+1E8h] [rbp+98h]
  int v62; // [rsp+1ECh] [rbp+9Ch]
  const unsigned __int16 *v63; // [rsp+1F0h] [rbp+A0h]
  int v64; // [rsp+1F8h] [rbp+A8h]
  int v65; // [rsp+1FCh] [rbp+ACh]
  int *v66; // [rsp+200h] [rbp+B0h]
  __int64 v67; // [rsp+208h] [rbp+B8h]
  __int64 *v68; // [rsp+210h] [rbp+C0h]
  __int64 v69; // [rsp+218h] [rbp+C8h]
  PSRWLOCK *p_SRWLock; // [rsp+220h] [rbp+D0h]
  __int64 v71; // [rsp+228h] [rbp+D8h]
  PSRWLOCK *v72; // [rsp+230h] [rbp+E0h]
  __int64 v73; // [rsp+238h] [rbp+E8h]

  v5 = *((_QWORD *)this + 34);
  v10 = *(_DWORD *)(v5 + 72);
  if ( v10 < 0 && (v11 = v5 + 80, v10 == *(_DWORD *)(v11 + 8)) && v11 )
  {
    wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v12 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    v13 = AutoPilotTelemProvider::Provider();
    v14 = v13;
    if ( *(_DWORD *)v13 > 5u )
    {
      v15 = *((_QWORD *)v13 + 3);
      if ( (*((_QWORD *)v14 + 2) & 0x800000000000LL) != 0 && (v15 & 0x800000000000LL) == v15 )
      {
        v35 = a5;
        v41 = 0x2000000;
        if ( !a2 )
          a2 = L"taskArgument null";
        v42 = a4;
        v43 = a2;
        v36 = a3;
        AutopilotCorrelationVector = (_QWORD *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v52);
        if ( AutopilotCorrelationVector[3] > 0xFu )
          AutopilotCorrelationVector = (_QWORD *)*AutopilotCorrelationVector;
        v44 = AutopilotCorrelationVector;
        v45 = *(_QWORD *)(v11 + 120);
        v46 = *(_QWORD *)(v11 + 112);
        v37 = *(_DWORD *)(v11 + 104);
        v47 = *(_QWORD *)(v11 + 96);
        v48 = *(_QWORD *)(v11 + 88);
        v18 = *((_QWORD *)this + 34);
        v38 = *(_DWORD *)(v11 + 80);
        v49 = *(_QWORD *)(v11 + 72);
        v30 = *(_DWORD *)(v11 + 32);
        v50 = *(_QWORD *)(v11 + 24);
        v31 = *(_DWORD *)v11;
        v51 = *(_QWORD *)(v11 + 128);
        v32 = *(_DWORD *)(v11 + 64);
        v39 = *(_QWORD *)(v11 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v11 + 8);
        v40 = 0x1000000;
        v34 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (_DWORD)v14,
          (unsigned int)&dword_18003A65C,
          v18 + 8,
          v17,
          (__int64)&v34,
          (__int64)&v40,
          (__int64)&SRWLock,
          (__int64)&v39,
          (__int64)&v32,
          (__int64)&v51,
          (__int64)&v31,
          (__int64)&v50,
          (__int64)&v30,
          (__int64)&v49,
          (__int64)&v38,
          (__int64)&v48,
          (__int64)&v47,
          (__int64)&v37,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v35,
          (__int64)&v41);
LABEL_30:
        std::string::_Tidy_deallocate(v52);
      }
    }
  }
  else
  {
    wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v34);
    v19 = v34;
    **((_DWORD **)this + 34) = 2;
    if ( v19 )
      ReleaseSRWLockExclusive(v19);
    v20 = AutoPilotTelemProvider::Provider();
    v21 = v20;
    if ( *(_DWORD *)v20 > 5u )
    {
      v22 = *((_QWORD *)v20 + 3);
      if ( (*((_QWORD *)v21 + 2) & 0x800000000000LL) != 0 && (v22 & 0x800000000000LL) == v22 )
      {
        LODWORD(SRWLock) = a5;
        v34 = (PSRWLOCK)0x2000000;
        if ( !a2 )
          a2 = L"taskArgument null";
        v40 = a4;
        v32 = a3;
        v23 = ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v52);
        v24 = (const unsigned __int16 *)v23;
        if ( *(_QWORD *)(v23 + 24) > 0xFu )
          v24 = *(const unsigned __int16 **)v23;
        CurrentThreadId = GetCurrentThreadId();
        v26 = *((_QWORD *)this + 34);
        v27 = -1;
        v31 = CurrentThreadId;
        v73 = 8;
        v71 = 4;
        v30 = *(_DWORD *)(v26 + 72);
        v72 = &v34;
        p_SRWLock = &SRWLock;
        v68 = &v40;
        v66 = &v32;
        v28 = -1;
        v39 = 0;
        v69 = 8;
        v67 = 4;
        do
          ++v28;
        while ( a2[v28] );
        v63 = a2;
        v64 = 2 * v28 + 2;
        v65 = 0;
        if ( v24 )
        {
          do
            ++v27;
          while ( *((_BYTE *)v24 + v27) );
          v29 = v27 + 1;
        }
        else
        {
          v24 = &byte_1800360F0;
          v29 = 1;
        }
        v61 = v29;
        v58 = &v31;
        v60 = v24;
        v56 = &v30;
        v62 = 0;
        v54 = &v39;
        v59 = 4;
        v57 = 4;
        v55 = 8;
        tlgWriteTransfer_EventWriteTransfer(v21, byte_18003AB1D, v26 + 8, 0, 11, v53);
        goto LABEL_30;
      }
    }
  }
  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800169c0  push    rbp
0x1800169c2  push    rbx
0x1800169c3  push    rsi
0x1800169c4  push    rdi
0x1800169c5  push    r12
0x1800169c7  push    r13
0x1800169c9  push    r14
0x1800169cb  push    r15
0x1800169cd  lea     rbp, [rsp-108h]
0x1800169d5  sub     rsp, 258h
0x1800169dc  mov     rax, cs:__security_cookie
0x1800169e3  xor     rax, rsp
0x1800169e6  mov     [rbp+140h+var_50], rax
0x1800169ed  mov     rdi, [rcx+110h]
0x1800169f4  xor     r13d, r13d
0x1800169f7  mov     r15, r9
0x1800169fa  mov     r12d, r8d
0x1800169fd  mov     rbx, rdx
0x180016a00  mov     rsi, rcx
0x180016a03  mov     eax, [rdi+48h]
0x180016a06  test    eax, eax
0x180016a08  jns     loc_180016C3D
0x180016a0e  add     rdi, 50h ; 'P'
0x180016a12  cmp     eax, [rdi+8]
0x180016a15  jnz     loc_180016C3D
0x180016a1b  test    rdi, rdi
0x180016a1e  jz      loc_180016C3D
0x180016a24  lea     rdx, [rbp+140h+SRWLock]
0x180016a28  call    ?LockExclusive@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016a2d  mov     rax, [rsi+110h]
0x180016a34  mov     rcx, [rbp+140h+SRWLock]; SRWLock
0x180016a38  mov     dword ptr [rax], 2
0x180016a3e  test    rcx, rcx
0x180016a41  jz      short loc_180016A49
0x180016a43  call    cs:__imp_ReleaseSRWLockExclusive
0x180016a49  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180016a4e  mov     r14, rax
0x180016a51  mov     ecx, [rax]
0x180016a53  cmp     ecx, 5
0x180016a56  jbe     loc_180016E13
0x180016a5c  mov     rax, [rax+18h]
0x180016a60  mov     rdx, 800000000000h
0x180016a6a  mov     rcx, [r14+10h]
0x180016a6e  test    rdx, rcx
0x180016a71  jz      loc_180016E13
0x180016a77  mov     rcx, rax
0x180016a7a  and     rcx, rdx
0x180016a7d  cmp     rcx, rax
0x180016a80  jnz     loc_180016E13
0x180016a86  mov     eax, [rbp+140h+arg_20]
0x180016a8c  lea     rcx, [rbp+140h+var_128]
0x180016a90  mov     [rbp+140h+var_1A0], eax
0x180016a93  test    rbx, rbx
0x180016a96  lea     rax, aTaskargumentNu; "taskArgument null"
0x180016a9d  mov     [rbp+140h+var_180], 2000000h
0x180016aa5  cmovz   rbx, rax
0x180016aa9  mov     [rbp+140h+var_178], r15
0x180016aad  mov     [rbp+140h+var_170], rbx
0x180016ab1  mov     [rbp+140h+var_19C], r12d
0x180016ab5  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180016aba  cmp     qword ptr [rax+18h], 0Fh
0x180016abf  jbe     short loc_180016AC4
0x180016ac1  mov     rax, [rax]
0x180016ac4  mov     [rbp+140h+var_168], rax
0x180016ac8  lea     rdx, dword_18003A65C
0x180016acf  mov     rax, [rdi+78h]
0x180016ad3  mov     rcx, r14
0x180016ad6  mov     [rbp+140h+var_160], rax
0x180016ada  mov     rax, [rdi+70h]
0x180016ade  mov     [rbp+140h+var_158], rax
0x180016ae2  mov     eax, [rdi+68h]
0x180016ae5  mov     [rbp+140h+var_198], eax
0x180016ae8  mov     rax, [rdi+60h]
0x180016aec  mov     [rbp+140h+var_150], rax
0x180016af0  mov     rax, [rdi+58h]
0x180016af4  mov     [rbp+140h+var_148], rax
0x180016af8  mov     eax, [rdi+50h]
0x180016afb  mov     r8, [rsi+110h]
0x180016b02  mov     [rbp+140h+var_194], eax
0x180016b05  add     r8, 8
0x180016b09  mov     rax, [rdi+48h]
0x180016b0d  mov     [rbp+140h+var_140], rax
0x180016b11  mov     eax, [rdi+20h]
0x180016b14  mov     [rbp+140h+var_1C0], eax
0x180016b17  mov     rax, [rdi+18h]
0x180016b1b  mov     [rbp+140h+var_138], rax
0x180016b1f  mov     eax, [rdi]
0x180016b21  mov     [rbp+140h+var_1BC], eax
0x180016b24  mov     rax, [rdi+80h]
0x180016b2b  mov     [rbp+140h+var_130], rax
0x180016b2f  mov     eax, [rdi+40h]
0x180016b32  mov     [rbp+140h+var_1B8], eax
0x180016b35  mov     rax, [rdi+38h]
0x180016b39  mov     [rbp+140h+var_190], rax
0x180016b3d  mov     eax, [rdi+8]
0x180016b40  mov     dword ptr [rbp+140h+SRWLock], eax
0x180016b43  lea     rax, [rbp+140h+var_180]
0x180016b47  mov     [rsp+290h+var_1C8], rax
0x180016b4f  lea     rax, [rbp+140h+var_1A0]
0x180016b53  mov     [rsp+290h+var_1D0], rax
0x180016b5b  lea     rax, [rbp+140h+var_178]
0x180016b5f  mov     [rsp+290h+var_1D8], rax
0x180016b67  lea     rax, [rbp+140h+var_19C]
0x180016b6b  mov     [rsp+290h+var_1E0], rax
0x180016b73  lea     rax, [rbp+140h+var_170]
0x180016b77  mov     [rsp+290h+var_1E8], rax
0x180016b7f  lea     rax, [rbp+140h+var_168]
0x180016b83  mov     [rsp+290h+var_1F0], rax
0x180016b8b  lea     rax, [rbp+140h+var_160]
0x180016b8f  mov     [rsp+290h+var_1F8], rax
0x180016b97  lea     rax, [rbp+140h+var_158]
0x180016b9b  mov     [rsp+290h+var_200], rax
0x180016ba3  lea     rax, [rbp+140h+var_198]
0x180016ba7  mov     [rsp+290h+var_208], rax
0x180016baf  lea     rax, [rbp+140h+var_150]
0x180016bb3  mov     [rsp+290h+var_210], rax
0x180016bbb  lea     rax, [rbp+140h+var_148]
0x180016bbf  mov     [rsp+290h+var_218], rax
0x180016bc4  lea     rax, [rbp+140h+var_194]
0x180016bc8  mov     [rsp+290h+var_220], rax
0x180016bcd  lea     rax, [rbp+140h+var_140]
0x180016bd1  mov     [rsp+290h+var_228], rax
0x180016bd6  lea     rax, [rbp+140h+var_1C0]
0x180016bda  mov     [rsp+290h+var_230], rax
0x180016bdf  lea     rax, [rbp+140h+var_138]
0x180016be3  mov     [rsp+290h+var_238], rax
0x180016be8  lea     rax, [rbp+140h+var_1BC]
0x180016bec  mov     [rsp+290h+var_240], rax
0x180016bf1  lea     rax, [rbp+140h+var_130]
0x180016bf5  mov     [rsp+290h+var_248], rax
0x180016bfa  lea     rax, [rbp+140h+var_1B8]
0x180016bfe  mov     [rsp+290h+var_250], rax
0x180016c03  lea     rax, [rbp+140h+var_190]
0x180016c07  mov     [rsp+290h+var_258], rax
0x180016c0c  lea     rax, [rbp+140h+SRWLock]
0x180016c10  mov     [rsp+290h+var_260], rax
0x180016c15  lea     rax, [rbp+140h+var_188]
0x180016c19  mov     [rsp+290h+var_268], rax
0x180016c1e  lea     rax, [rbp+140h+var_1A8]
0x180016c22  mov     [rsp+290h+var_270], rax
0x180016c27  mov     [rbp+140h+var_188], 1000000h
0x180016c2f  mov     [rbp+140h+var_1A8], r13
0x180016c33  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U3@U4@U2@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456564343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180016c38  jmp     loc_180016E0A
0x180016c3d  lea     rdx, [rbp+140h+var_1A8]
0x180016c41  call    ?LockExclusive@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016c46  mov     rax, [rsi+110h]
0x180016c4d  mov     rcx, [rbp+140h+var_1A8]; SRWLock
0x180016c51  mov     dword ptr [rax], 2
0x180016c57  test    rcx, rcx
0x180016c5a  jz      short loc_180016C62
0x180016c5c  call    cs:__imp_ReleaseSRWLockExclusive
0x180016c62  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180016c67  mov     r14, rax
0x180016c6a  mov     ecx, [rax]
0x180016c6c  cmp     ecx, 5
0x180016c6f  jbe     loc_180016E13
0x180016c75  mov     rax, [rax+18h]
0x180016c79  mov     rdx, 800000000000h
0x180016c83  mov     rcx, [r14+10h]
0x180016c87  test    rdx, rcx
0x180016c8a  jz      loc_180016E13
0x180016c90  mov     rcx, rax
0x180016c93  and     rcx, rdx
0x180016c96  cmp     rcx, rax
0x180016c99  jnz     loc_180016E13
0x180016c9f  mov     eax, [rbp+140h+arg_20]
0x180016ca5  lea     rcx, [rbp+140h+var_128]
0x180016ca9  mov     dword ptr [rbp+140h+SRWLock], eax
0x180016cac  test    rbx, rbx
0x180016caf  lea     rax, aTaskargumentNu; "taskArgument null"
0x180016cb6  mov     [rbp+140h+var_1A8], 2000000h
0x180016cbe  cmovz   rbx, rax
0x180016cc2  mov     [rbp+140h+var_188], r15
0x180016cc6  mov     [rbp+140h+var_1B8], r12d
0x180016cca  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180016ccf  mov     rdi, rax
0x180016cd2  cmp     qword ptr [rax+18h], 0Fh
0x180016cd7  jbe     short loc_180016CDC
0x180016cd9  mov     rdi, [rax]
0x180016cdc  call    cs:__imp_GetCurrentThreadId
0x180016ce2  mov     r8, [rsi+110h]
0x180016ce9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180016ced  mov     [rbp+140h+var_1BC], eax
0x180016cf0  mov     [rbp+140h+var_58], 8
0x180016cfb  mov     [rbp+140h+var_68], 4
0x180016d06  mov     eax, [r8+48h]
0x180016d0a  mov     [rbp+140h+var_1C0], eax
0x180016d0d  lea     rax, [rbp+140h+var_1A8]
0x180016d11  mov     [rbp+140h+var_60], rax
0x180016d18  lea     rax, [rbp+140h+SRWLock]
0x180016d1c  mov     [rbp+140h+var_70], rax
0x180016d23  lea     rax, [rbp+140h+var_188]
0x180016d27  mov     [rbp+140h+var_80], rax
0x180016d2e  lea     rax, [rbp+140h+var_1B8]
0x180016d32  mov     [rbp+140h+var_90], rax
0x180016d39  mov     rax, rcx
0x180016d3c  mov     [rbp+140h+var_190], r13
0x180016d40  mov     [rbp+140h+var_78], 8
0x180016d4b  mov     [rbp+140h+var_88], 4
0x180016d56  inc     rax
0x180016d59  cmp     [rbx+rax*2], r13w
0x180016d5e  jnz     short loc_180016D56
0x180016d60  mov     [rbp+140h+var_A0], rbx
0x180016d67  lea     eax, ds:2[rax*2]
0x180016d6e  mov     [rbp+140h+var_98], eax
0x180016d74  mov     [rbp+140h+var_94], r13d
0x180016d7b  test    rdi, rdi
0x180016d7e  jz      short loc_180016D8D
0x180016d80  inc     rcx
0x180016d83  cmp     [rdi+rcx], r13b
0x180016d87  jnz     short loc_180016D80
0x180016d89  inc     ecx
0x180016d8b  jmp     short loc_180016D99
0x180016d8d  lea     rdi, byte_1800360F0
0x180016d94  mov     ecx, 1
0x180016d99  lea     rax, [rbp+140h+var_1BC]
0x180016d9d  mov     [rbp+140h+var_A8], ecx
0x180016da3  mov     [rbp+140h+var_C0], rax
0x180016daa  lea     rdx, byte_18003AB1D
0x180016db1  lea     rax, [rbp+140h+var_1C0]
0x180016db5  mov     [rbp+140h+var_B0], rdi
0x180016dbc  mov     [rbp+140h+var_D0], rax
0x180016dc0  add     r8, 8
0x180016dc4  lea     rax, [rbp+140h+var_190]
0x180016dc8  mov     [rbp+140h+var_A4], r13d
0x180016dcf  mov     [rbp+140h+var_E0], rax
0x180016dd3  xor     r9d, r9d
0x180016dd6  lea     rax, [rbp+140h+var_100]
0x180016dda  mov     [rbp+140h+var_B8], 4
0x180016de5  mov     [rsp+290h+var_268], rax
0x180016dea  mov     rcx, r14
0x180016ded  mov     dword ptr [rsp+290h+var_270], 0Bh
0x180016df5  mov     [rbp+140h+var_C8], 4
0x180016dfd  mov     [rbp+140h+var_D8], 8
0x180016e05  call    _tlgWriteTransfer_EventWriteTransfer
0x180016e0a  lea     rcx, [rbp+140h+var_128]
0x180016e0e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016e13  mov     rcx, rsi
0x180016e16  call    ?IgnoreCurrentThread@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180016e1b  mov     rcx, [rbp+140h+var_50]
0x180016e22  xor     rcx, rsp; StackCookie
0x180016e25  call    __security_check_cookie
0x180016e2a  add     rsp, 258h
0x180016e31  pop     r15
0x180016e33  pop     r14
0x180016e35  pop     r13
0x180016e37  pop     r12
0x180016e39  pop     rdi
0x180016e3a  pop     rsi
0x180016e3b  pop     rbx
0x180016e3c  pop     rbp
0x180016e3d  retn
```
