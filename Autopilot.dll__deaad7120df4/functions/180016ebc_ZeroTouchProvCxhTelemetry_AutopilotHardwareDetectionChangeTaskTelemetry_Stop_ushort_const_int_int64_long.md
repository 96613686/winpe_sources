# ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::Stop(ushort const *,int,__int64,long)

- ea: `0x180016ebc`
- end: `0x18001734d`
- name: `?Stop@AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBGH_JJ@Z`
- size: `1169`
- prototype: `void __fastcall(ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *__hidden this, const unsigned __int16 *, int, __int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180015054`

## callees

- `0x180001640`
- `0x1800018cc`
- `0x1800045d0`
- `0x180015cd4`
- `0x180015e10`
- `0x180015e94`
- `0x18001670c`
- `0x180016ebc`
- `0x1800179b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016f3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001715e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016f3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001715e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800171e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800171e4`

## string_xrefs

- `0x180016f98`: `taskArgument null`
- `0x1800171b7`: `taskArgument null`

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
  __int64 v14; // r14
  __int64 v15; // rax
  __int64 AutopilotCorrelationVector; // rax
  __int64 v17; // r9
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
  const unsigned __int16 *v39; // [rsp+100h] [rbp-50h] BYREF
  __int64 v40; // [rsp+108h] [rbp-48h] BYREF
  __int64 v41; // [rsp+110h] [rbp-40h] BYREF
  __int64 v42; // [rsp+118h] [rbp-38h] BYREF
  int *v43; // [rsp+120h] [rbp-30h] BYREF
  const unsigned __int16 *v44; // [rsp+128h] [rbp-28h] BYREF
  int *v45; // [rsp+130h] [rbp-20h] BYREF
  const unsigned __int16 *v46; // [rsp+138h] [rbp-18h] BYREF
  int *v47; // [rsp+140h] [rbp-10h] BYREF
  const unsigned __int16 *v48; // [rsp+148h] [rbp-8h] BYREF
  const unsigned __int16 *v49; // [rsp+150h] [rbp+0h] BYREF
  int *v50; // [rsp+158h] [rbp+8h] BYREF
  const unsigned __int16 *v51; // [rsp+160h] [rbp+10h] BYREF
  char *v52[5]; // [rsp+168h] [rbp+18h] BYREF
  char v53[32]; // [rsp+190h] [rbp+40h] BYREF
  const unsigned __int16 **v54; // [rsp+1B0h] [rbp+60h]
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
    v14 = (__int64)v13;
    if ( *(_DWORD *)v13 > 5u )
    {
      v15 = *((_QWORD *)v13 + 3);
      if ( (*(_QWORD *)(v14 + 16) & 0x800000000000LL) != 0 && (v15 & 0x800000000000LL) == v15 )
      {
        v35 = a5;
        v41 = 0x2000000;
        if ( !a2 )
          a2 = L"taskArgument null";
        v42 = a4;
        v43 = (int *)a2;
        v36 = a3;
        AutopilotCorrelationVector = ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector((__int64)v52);
        if ( *(_QWORD *)(AutopilotCorrelationVector + 24) > 0xFu )
          AutopilotCorrelationVector = *(_QWORD *)AutopilotCorrelationVector;
        v44 = (const unsigned __int16 *)AutopilotCorrelationVector;
        v45 = *(int **)(v11 + 120);
        v46 = *(const unsigned __int16 **)(v11 + 112);
        v37 = *(_DWORD *)(v11 + 104);
        v47 = *(int **)(v11 + 96);
        v48 = *(const unsigned __int16 **)(v11 + 88);
        v18 = *((_QWORD *)this + 34);
        v38 = *(_DWORD *)(v11 + 80);
        v49 = *(const unsigned __int16 **)(v11 + 72);
        v30 = *(_DWORD *)(v11 + 32);
        v50 = *(int **)(v11 + 24);
        v31 = *(_DWORD *)v11;
        v51 = *(const unsigned __int16 **)(v11 + 128);
        v32 = *(_DWORD *)(v11 + 64);
        v39 = *(const unsigned __int16 **)(v11 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v11 + 8);
        v40 = 0x1000000;
        v34 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v14,
          (__int64)&dword_18003B65C,
          v18 + 8,
          v17,
          (__int64)&v34,
          (__int64)&v40,
          (__int64)&SRWLock,
          &v39,
          (__int64)&v32,
          &v51,
          (__int64)&v31,
          &v50,
          (__int64)&v30,
          &v49,
          (__int64)&v38,
          &v48,
          &v47,
          (__int64)&v37,
          &v46,
          &v45,
          &v44,
          &v43,
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
        v23 = ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector((__int64)v52);
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
          v24 = &byte_180037110;
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
        tlgWriteTransfer_EventWriteTransfer(v21, byte_18003BB1D, v26 + 8, 0, 11, v53);
        goto LABEL_30;
      }
    }
  }
  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180016ebc  push    rbp
0x180016ebe  push    rbx
0x180016ebf  push    rsi
0x180016ec0  push    rdi
0x180016ec1  push    r12
0x180016ec3  push    r13
0x180016ec5  push    r14
0x180016ec7  push    r15
0x180016ec9  lea     rbp, [rsp-108h]
0x180016ed1  sub     rsp, 258h
0x180016ed8  mov     rax, cs:__security_cookie
0x180016edf  xor     rax, rsp
0x180016ee2  mov     [rbp+140h+var_50], rax
0x180016ee9  mov     rdi, [rcx+110h]
0x180016ef0  xor     r13d, r13d
0x180016ef3  mov     r15, r9
0x180016ef6  mov     r12d, r8d
0x180016ef9  mov     rbx, rdx
0x180016efc  mov     rsi, rcx
0x180016eff  mov     eax, [rdi+48h]
0x180016f02  test    eax, eax
0x180016f04  jns     loc_18001713F
0x180016f0a  add     rdi, 50h ; 'P'
0x180016f0e  cmp     eax, [rdi+8]
0x180016f11  jnz     loc_18001713F
0x180016f17  test    rdi, rdi
0x180016f1a  jz      loc_18001713F
0x180016f20  lea     rdx, [rbp+140h+SRWLock]
0x180016f24  call    ?LockExclusive@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016f29  mov     rax, [rsi+110h]
0x180016f30  mov     rcx, [rbp+140h+SRWLock]; SRWLock
0x180016f34  mov     dword ptr [rax], 2
0x180016f3a  test    rcx, rcx
0x180016f3d  jz      short loc_180016F4B
0x180016f3f  call    cs:__imp_ReleaseSRWLockExclusive
0x180016f46  nop     dword ptr [rax+rax+00h]
0x180016f4b  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180016f50  mov     r14, rax
0x180016f53  mov     ecx, [rax]
0x180016f55  cmp     ecx, 5
0x180016f58  jbe     loc_180017321
0x180016f5e  mov     rax, [rax+18h]
0x180016f62  mov     rdx, 800000000000h
0x180016f6c  mov     rcx, [r14+10h]
0x180016f70  test    rdx, rcx
0x180016f73  jz      loc_180017321
0x180016f79  mov     rcx, rax
0x180016f7c  and     rcx, rdx
0x180016f7f  cmp     rcx, rax
0x180016f82  jnz     loc_180017321
0x180016f88  mov     eax, [rbp+140h+arg_20]
0x180016f8e  lea     rcx, [rbp+140h+var_128]
0x180016f92  mov     [rbp+140h+var_1A0], eax
0x180016f95  test    rbx, rbx
0x180016f98  lea     rax, aTaskargumentNu; "taskArgument null"
0x180016f9f  mov     [rbp+140h+var_180], 2000000h
0x180016fa7  cmovz   rbx, rax
0x180016fab  mov     [rbp+140h+var_178], r15
0x180016faf  mov     [rbp+140h+var_170], rbx
0x180016fb3  mov     [rbp+140h+var_19C], r12d
0x180016fb7  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180016fbc  cmp     qword ptr [rax+18h], 0Fh
0x180016fc1  jbe     short loc_180016FC6
0x180016fc3  mov     rax, [rax]
0x180016fc6  mov     [rbp+140h+var_168], rax
0x180016fca  lea     rdx, dword_18003B65C
0x180016fd1  mov     rax, [rdi+78h]
0x180016fd5  mov     rcx, r14
0x180016fd8  mov     [rbp+140h+var_160], rax
0x180016fdc  mov     rax, [rdi+70h]
0x180016fe0  mov     [rbp+140h+var_158], rax
0x180016fe4  mov     eax, [rdi+68h]
0x180016fe7  mov     [rbp+140h+var_198], eax
0x180016fea  mov     rax, [rdi+60h]
0x180016fee  mov     [rbp+140h+var_150], rax
0x180016ff2  mov     rax, [rdi+58h]
0x180016ff6  mov     [rbp+140h+var_148], rax
0x180016ffa  mov     eax, [rdi+50h]
0x180016ffd  mov     r8, [rsi+110h]
0x180017004  mov     [rbp+140h+var_194], eax
0x180017007  add     r8, 8
0x18001700b  mov     rax, [rdi+48h]
0x18001700f  mov     [rbp+140h+var_140], rax
0x180017013  mov     eax, [rdi+20h]
0x180017016  mov     [rbp+140h+var_1C0], eax
0x180017019  mov     rax, [rdi+18h]
0x18001701d  mov     [rbp+140h+var_138], rax
0x180017021  mov     eax, [rdi]
0x180017023  mov     [rbp+140h+var_1BC], eax
0x180017026  mov     rax, [rdi+80h]
0x18001702d  mov     [rbp+140h+var_130], rax
0x180017031  mov     eax, [rdi+40h]
0x180017034  mov     [rbp+140h+var_1B8], eax
0x180017037  mov     rax, [rdi+38h]
0x18001703b  mov     [rbp+140h+var_190], rax
0x18001703f  mov     eax, [rdi+8]
0x180017042  mov     dword ptr [rbp+140h+SRWLock], eax
0x180017045  lea     rax, [rbp+140h+var_180]
0x180017049  mov     [rsp+290h+var_1C8], rax
0x180017051  lea     rax, [rbp+140h+var_1A0]
0x180017055  mov     [rsp+290h+var_1D0], rax
0x18001705d  lea     rax, [rbp+140h+var_178]
0x180017061  mov     [rsp+290h+var_1D8], rax
0x180017069  lea     rax, [rbp+140h+var_19C]
0x18001706d  mov     [rsp+290h+var_1E0], rax
0x180017075  lea     rax, [rbp+140h+var_170]
0x180017079  mov     [rsp+290h+var_1E8], rax
0x180017081  lea     rax, [rbp+140h+var_168]
0x180017085  mov     [rsp+290h+var_1F0], rax
0x18001708d  lea     rax, [rbp+140h+var_160]
0x180017091  mov     [rsp+290h+var_1F8], rax
0x180017099  lea     rax, [rbp+140h+var_158]
0x18001709d  mov     [rsp+290h+var_200], rax
0x1800170a5  lea     rax, [rbp+140h+var_198]
0x1800170a9  mov     [rsp+290h+var_208], rax
0x1800170b1  lea     rax, [rbp+140h+var_150]
0x1800170b5  mov     [rsp+290h+var_210], rax
0x1800170bd  lea     rax, [rbp+140h+var_148]
0x1800170c1  mov     [rsp+290h+var_218], rax
0x1800170c6  lea     rax, [rbp+140h+var_194]
0x1800170ca  mov     [rsp+290h+var_220], rax
0x1800170cf  lea     rax, [rbp+140h+var_140]
0x1800170d3  mov     [rsp+290h+var_228], rax
0x1800170d8  lea     rax, [rbp+140h+var_1C0]
0x1800170dc  mov     [rsp+290h+var_230], rax
0x1800170e1  lea     rax, [rbp+140h+var_138]
0x1800170e5  mov     [rsp+290h+var_238], rax
0x1800170ea  lea     rax, [rbp+140h+var_1BC]
0x1800170ee  mov     [rsp+290h+var_240], rax
0x1800170f3  lea     rax, [rbp+140h+var_130]
0x1800170f7  mov     [rsp+290h+var_248], rax
0x1800170fc  lea     rax, [rbp+140h+var_1B8]
0x180017100  mov     [rsp+290h+var_250], rax
0x180017105  lea     rax, [rbp+140h+var_190]
0x180017109  mov     [rsp+290h+var_258], rax
0x18001710e  lea     rax, [rbp+140h+SRWLock]
0x180017112  mov     [rsp+290h+var_260], rax
0x180017117  lea     rax, [rbp+140h+var_188]
0x18001711b  mov     [rsp+290h+var_268], rax
0x180017120  lea     rax, [rbp+140h+var_1A8]
0x180017124  mov     [rsp+290h+var_270], rax
0x180017129  mov     [rbp+140h+var_188], 1000000h
0x180017131  mov     [rbp+140h+var_1A8], r13
0x180017135  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U3@U4@U2@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456564343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001713a  jmp     loc_180017318
0x18001713f  lea     rdx, [rbp+140h+var_1A8]
0x180017143  call    ?LockExclusive@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017148  mov     rax, [rsi+110h]
0x18001714f  mov     rcx, [rbp+140h+var_1A8]; SRWLock
0x180017153  mov     dword ptr [rax], 2
0x180017159  test    rcx, rcx
0x18001715c  jz      short loc_18001716A
0x18001715e  call    cs:__imp_ReleaseSRWLockExclusive
0x180017165  nop     dword ptr [rax+rax+00h]
0x18001716a  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x18001716f  mov     r14, rax
0x180017172  mov     ecx, [rax]
0x180017174  cmp     ecx, 5
0x180017177  jbe     loc_180017321
0x18001717d  mov     rax, [rax+18h]
0x180017181  mov     rdx, 800000000000h
0x18001718b  mov     rcx, [r14+10h]
0x18001718f  test    rdx, rcx
0x180017192  jz      loc_180017321
0x180017198  mov     rcx, rax
0x18001719b  and     rcx, rdx
0x18001719e  cmp     rcx, rax
0x1800171a1  jnz     loc_180017321
0x1800171a7  mov     eax, [rbp+140h+arg_20]
0x1800171ad  lea     rcx, [rbp+140h+var_128]
0x1800171b1  mov     dword ptr [rbp+140h+SRWLock], eax
0x1800171b4  test    rbx, rbx
0x1800171b7  lea     rax, aTaskargumentNu; "taskArgument null"
0x1800171be  mov     [rbp+140h+var_1A8], 2000000h
0x1800171c6  cmovz   rbx, rax
0x1800171ca  mov     [rbp+140h+var_188], r15
0x1800171ce  mov     [rbp+140h+var_1B8], r12d
0x1800171d2  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x1800171d7  mov     rdi, rax
0x1800171da  cmp     qword ptr [rax+18h], 0Fh
0x1800171df  jbe     short loc_1800171E4
0x1800171e1  mov     rdi, [rax]
0x1800171e4  call    cs:__imp_GetCurrentThreadId
0x1800171eb  nop     dword ptr [rax+rax+00h]
0x1800171f0  mov     r8, [rsi+110h]
0x1800171f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800171fb  mov     [rbp+140h+var_1BC], eax
0x1800171fe  mov     [rbp+140h+var_58], 8
0x180017209  mov     [rbp+140h+var_68], 4
0x180017214  mov     eax, [r8+48h]
0x180017218  mov     [rbp+140h+var_1C0], eax
0x18001721b  lea     rax, [rbp+140h+var_1A8]
0x18001721f  mov     [rbp+140h+var_60], rax
0x180017226  lea     rax, [rbp+140h+SRWLock]
0x18001722a  mov     [rbp+140h+var_70], rax
0x180017231  lea     rax, [rbp+140h+var_188]
0x180017235  mov     [rbp+140h+var_80], rax
0x18001723c  lea     rax, [rbp+140h+var_1B8]
0x180017240  mov     [rbp+140h+var_90], rax
0x180017247  mov     rax, rcx
0x18001724a  mov     [rbp+140h+var_190], r13
0x18001724e  mov     [rbp+140h+var_78], 8
0x180017259  mov     [rbp+140h+var_88], 4
0x180017264  inc     rax
0x180017267  cmp     [rbx+rax*2], r13w
0x18001726c  jnz     short loc_180017264
0x18001726e  mov     [rbp+140h+var_A0], rbx
0x180017275  lea     eax, ds:2[rax*2]
0x18001727c  mov     [rbp+140h+var_98], eax
0x180017282  mov     [rbp+140h+var_94], r13d
0x180017289  test    rdi, rdi
0x18001728c  jz      short loc_18001729B
0x18001728e  inc     rcx
0x180017291  cmp     [rdi+rcx], r13b
0x180017295  jnz     short loc_18001728E
0x180017297  inc     ecx
0x180017299  jmp     short loc_1800172A7
0x18001729b  lea     rdi, byte_180037110
0x1800172a2  mov     ecx, 1
0x1800172a7  lea     rax, [rbp+140h+var_1BC]
0x1800172ab  mov     [rbp+140h+var_A8], ecx
0x1800172b1  mov     [rbp+140h+var_C0], rax
0x1800172b8  lea     rdx, byte_18003BB1D
0x1800172bf  lea     rax, [rbp+140h+var_1C0]
0x1800172c3  mov     [rbp+140h+var_B0], rdi
0x1800172ca  mov     [rbp+140h+var_D0], rax
0x1800172ce  add     r8, 8
0x1800172d2  lea     rax, [rbp+140h+var_190]
0x1800172d6  mov     [rbp+140h+var_A4], r13d
0x1800172dd  mov     [rbp+140h+var_E0], rax
0x1800172e1  xor     r9d, r9d
0x1800172e4  lea     rax, [rbp+140h+var_100]
0x1800172e8  mov     [rbp+140h+var_B8], 4
0x1800172f3  mov     [rsp+290h+var_268], rax
0x1800172f8  mov     rcx, r14
0x1800172fb  mov     dword ptr [rsp+290h+var_270], 0Bh
0x180017303  mov     [rbp+140h+var_C8], 4
0x18001730b  mov     [rbp+140h+var_D8], 8
0x180017313  call    _tlgWriteTransfer_EventWriteTransfer
0x180017318  lea     rcx, [rbp+140h+var_128]
0x18001731c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180017321  mov     rcx, rsi
0x180017324  call    ?IgnoreCurrentThread@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180017329  mov     rcx, [rbp+140h+var_50]
0x180017330  xor     rcx, rsp; StackCookie
0x180017333  call    __security_check_cookie
0x180017338  add     rsp, 258h
0x18001733f  pop     r15
0x180017341  pop     r14
0x180017343  pop     r13
0x180017345  pop     r12
0x180017347  pop     rdi
0x180017348  pop     rsi
0x180017349  pop     rbx
0x18001734a  pop     rbp
0x18001734b  retn
```
