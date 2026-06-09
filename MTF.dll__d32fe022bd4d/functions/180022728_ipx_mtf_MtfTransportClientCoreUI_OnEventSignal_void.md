# ipx::mtf::MtfTransportClientCoreUI::_OnEventSignal(void)

- ea: `0x180022728`
- end: `0x180022abb`
- name: `?_OnEventSignal@MtfTransportClientCoreUI@mtf@ipx@@IEAAJXZ`
- size: `915`
- prototype: `__int64 __fastcall(ipx::mtf::MtfTransportClientCoreUI *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022520`

## callees

- `0x180002de0`
- `0x180002e68`
- `0x180006074`
- `0x18001e1f4`
- `0x18001e89c`
- `0x180022728`
- `0x180022c0c`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180022982`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180022982`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022762`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800227de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022762`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800227de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002278c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002279f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800228f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002278c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002279f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800228f3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180022997`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180022997`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ipx::mtf::MtfTransportClientCoreUI::_OnEventSignal(ipx::mtf::MtfTransportClientCoreUI *this)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 v3; // rbx
  char v4; // r13
  __int64 v5; // r14
  _QWORD *v6; // rax
  struct IUnknown **v7; // r15
  struct IUnknown *v8; // r14
  __int64 *v9; // rcx
  __int64 v10; // rdx
  int v12; // eax
  unsigned int v13; // r14d
  struct IUnknown *v14; // r14
  int v15; // eax
  struct IUnknown *v16; // rcx
  struct IUnknown *v17; // rcx
  struct IUnknown *v19; // rcx
  int v20; // [rsp+20h] [rbp-39h]
  struct IUnknown *v21; // [rsp+30h] [rbp-29h] BYREF
  char v22[8]; // [rsp+38h] [rbp-21h] BYREF
  char Parameter[8]; // [rsp+40h] [rbp-19h] BYREF
  int v24; // [rsp+48h] [rbp-11h]
  HANDLE Timer; // [rsp+50h] [rbp-9h]
  ipx::mtf::MtfTransportClientCoreUI *v26; // [rsp+58h] [rbp-1h]
  __int64 v27; // [rsp+60h] [rbp+7h]
  struct IUnknown *v28; // [rsp+68h] [rbp+Fh]
  struct IUnknown *v29; // [rsp+70h] [rbp+17h] BYREF
  int v30; // [rsp+78h] [rbp+1Fh]
  unsigned int v31; // [rsp+7Ch] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = (RTL_SRWLOCK *)((char *)this + 288);
  AcquireSRWLockExclusive((PSRWLOCK)this + 36);
  if ( (*(unsigned int (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 8LL))(this) == 1 )
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 6);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
  else
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    v26 = this;
    v3 = *((_QWORD *)this + 42);
    v27 = v3;
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    while ( 1 )
    {
      v4 = 0;
      v28 = 0;
      AcquireSRWLockExclusive((PSRWLOCK)this + 35);
      v21 = (struct IUnknown *)((char *)this + 280);
      if ( *((_QWORD *)this + 41) )
      {
        v4 = 1;
        v5 = *((_QWORD *)this + 40);
        if ( this == (ipx::mtf::MtfTransportClientCoreUI *)-296LL )
        {
          std::_Lockit::_Lockit((std::_Lockit *)v22, 3);
          std::_Lockit::~_Lockit((std::_Lockit *)v22);
          v6 = 0;
        }
        else
        {
          v6 = (_QWORD *)*((_QWORD *)this + 37);
        }
        if ( v6 )
          v6 = (_QWORD *)*v6;
        v7 = *(struct IUnknown ***)(v6[1] + 8 * (v5 & (v6[2] - 1LL)));
        v8 = *v7;
        if ( *v7 )
          ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->AddRef)(*v7);
        if ( v28 )
          ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
        v28 = v8;
        v29 = v7[1];
        v30 = *((_DWORD *)v7 + 4);
        v31 = *((_DWORD *)v7 + 5);
        if ( *((_QWORD *)this + 41) )
        {
          v9 = *(__int64 **)(*((_QWORD *)this + 38) + 8 * (*((_QWORD *)this + 40) & (*((_QWORD *)this + 39) - 1LL)));
          v10 = *v9;
          *v9 = 0;
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          if ( (*((_QWORD *)this + 41))-- == 1 )
            *((_QWORD *)this + 40) = 0;
          else
            ++*((_QWORD *)this + 40);
        }
      }
      if ( this != (ipx::mtf::MtfTransportClientCoreUI *)-280LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
      if ( !v4 )
        break;
      if ( v3 )
      {
        v21 = 0;
        v12 = ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(this, v28, &v21);
        v13 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x297,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
            (const char *)(unsigned int)v12,
            v20);
          if ( v21 )
            ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
          v17 = v28;
          v28 = 0;
          if ( v17 )
            ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
          (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
          return v13;
        }
        CRPCTimeout::CRPCTimeout(Parameter);
        v14 = v21;
        v15 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **, _QWORD, struct IUnknown *))(*(_QWORD *)v3 + 24LL))(
                v3,
                &v29,
                v31,
                v21);
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x29B,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
            (const char *)(unsigned int)v15,
            v20);
        if ( v24 >= 0 )
        {
          v24 = -2147467259;
          CoDisableCallCancellation(0);
          if ( Timer )
          {
            DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
            Timer = 0;
          }
        }
        if ( v14 )
          ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
      }
      v16 = v28;
      v28 = 0;
      if ( v16 )
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
    }
    v19 = v28;
    v28 = 0;
    if ( v19 )
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
  }
  return 0;
}

```

## disassembly

```asm
0x180022728  mov     [rsp-8+arg_8], rbx
0x18002272d  mov     [rsp-8+arg_10], rsi
0x180022732  push    rbp
0x180022733  push    r12
0x180022735  push    r13
0x180022737  push    r14
0x180022739  push    r15
0x18002273b  lea     rbp, [rsp-37h]
0x180022740  sub     rsp, 90h
0x180022747  mov     rax, cs:__security_cookie
0x18002274e  xor     rax, rsp
0x180022751  mov     [rbp+57h+var_30], rax
0x180022755  mov     rsi, rcx
0x180022758  lea     rbx, [rcx+120h]
0x18002275f  mov     rcx, rbx; SRWLock
0x180022762  call    cs:__imp_AcquireSRWLockExclusive
0x180022768  mov     rax, [rsi]
0x18002276b  mov     rcx, rsi
0x18002276e  mov     rax, [rax+8]
0x180022772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022777  cmp     eax, 1
0x18002277a  jnz     short loc_180022797
0x18002277c  lock dec dword ptr [rsi+18h]
0x180022780  test    rbx, rbx
0x180022783  jz      loc_180022A90
0x180022789  mov     rcx, rbx; SRWLock
0x18002278c  call    cs:__imp_ReleaseSRWLockExclusive
0x180022792  jmp     loc_180022A90
0x180022797  test    rbx, rbx
0x18002279a  jz      short loc_1800227A5
0x18002279c  mov     rcx, rbx; SRWLock
0x18002279f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800227a5  mov     [rbp+57h+var_58], rsi
0x1800227a9  mov     rbx, [rsi+150h]
0x1800227b0  mov     [rbp+57h+var_50], rbx
0x1800227b4  test    rbx, rbx
0x1800227b7  jz      short loc_1800227C9
0x1800227b9  mov     rax, [rbx]
0x1800227bc  mov     rcx, rbx
0x1800227bf  mov     rax, [rax+8]
0x1800227c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227c8  nop
0x1800227c9  lea     r12, [rsi+118h]
0x1800227d0  xor     r13b, r13b
0x1800227d3  mov     [rbp+57h+var_48], 0
0x1800227db  mov     rcx, r12; SRWLock
0x1800227de  call    cs:__imp_AcquireSRWLockExclusive
0x1800227e4  mov     [rbp+57h+var_80], r12
0x1800227e8  cmp     qword ptr [rsi+148h], 0
0x1800227f0  jbe     loc_1800228EB
0x1800227f6  mov     r13b, 1
0x1800227f9  lea     rax, [rsi+128h]
0x180022800  mov     r14, [rax+18h]
0x180022804  test    rax, rax
0x180022807  jnz     short loc_180022822
0x180022809  lea     edx, [rax+3]; int
0x18002280c  lea     rcx, [rbp+57h+var_78]; this
0x180022810  call    ??0_Lockit@std@@QEAA@H@Z; std::_Lockit::_Lockit(int)
0x180022815  lea     rcx, [rbp+57h+var_78]; this
0x180022819  call    ??1_Lockit@std@@QEAA@XZ; std::_Lockit::~_Lockit(void)
0x18002281e  xor     eax, eax
0x180022820  jmp     short loc_180022825
0x180022822  mov     rax, [rax]
0x180022825  test    rax, rax
0x180022828  jz      short loc_18002282D
0x18002282a  mov     rax, [rax]
0x18002282d  mov     rcx, [rax+10h]
0x180022831  dec     rcx
0x180022834  and     rcx, r14
0x180022837  mov     rax, [rax+8]
0x18002283b  mov     r15, [rax+rcx*8]
0x18002283f  mov     r14, [r15]
0x180022842  test    r14, r14
0x180022845  jz      short loc_180022856
0x180022847  mov     rax, [r14]
0x18002284a  mov     rcx, r14
0x18002284d  mov     rax, [rax+8]
0x180022851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022856  mov     rcx, [rbp+57h+var_48]
0x18002285a  test    rcx, rcx
0x18002285d  jz      short loc_18002286B
0x18002285f  mov     rax, [rcx]
0x180022862  mov     rax, [rax+10h]
0x180022866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002286b  mov     [rbp+57h+var_48], r14
0x18002286f  movsd   xmm0, qword ptr [r15+8]
0x180022875  movsd   [rbp+57h+var_40], xmm0
0x18002287a  mov     eax, [r15+10h]
0x18002287e  mov     [rbp+57h+var_38], eax
0x180022881  mov     eax, [r15+14h]
0x180022885  mov     [rbp+57h+var_34], eax
0x180022888  cmp     qword ptr [rsi+148h], 0
0x180022890  jz      short loc_1800228EB
0x180022892  mov     rcx, [rsi+138h]
0x180022899  dec     rcx
0x18002289c  and     rcx, [rsi+140h]
0x1800228a3  mov     rax, [rsi+130h]
0x1800228aa  mov     rcx, [rax+rcx*8]
0x1800228ae  mov     rdx, [rcx]
0x1800228b1  mov     qword ptr [rcx], 0
0x1800228b8  test    rdx, rdx
0x1800228bb  jz      short loc_1800228CD
0x1800228bd  mov     rax, [rdx]
0x1800228c0  mov     rcx, rdx
0x1800228c3  mov     rax, [rax+10h]
0x1800228c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228cc  nop
0x1800228cd  sub     qword ptr [rsi+148h], 1
0x1800228d5  jnz     short loc_1800228E4
0x1800228d7  mov     qword ptr [rsi+140h], 0
0x1800228e2  jmp     short loc_1800228EB
0x1800228e4  inc     qword ptr [rsi+140h]
0x1800228eb  test    r12, r12
0x1800228ee  jz      short loc_1800228F9
0x1800228f0  mov     rcx, r12; SRWLock
0x1800228f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800228f9  test    r13b, r13b
0x1800228fc  jz      loc_180022A4E
0x180022902  test    rbx, rbx
0x180022905  jz      loc_1800229BA
0x18002290b  mov     [rbp+57h+var_80], 0
0x180022913  lea     r8, [rbp+57h+var_80]; struct IUnknown **
0x180022917  mov     rdx, [rbp+57h+var_48]; struct IUnknown *
0x18002291b  mov     rcx, rsi; this
0x18002291e  call    ?_SerializeDeserializeData@MtfTransportClientCoreUI@mtf@ipx@@IEAAJPEAUIUnknown@@PEAPEAU4@@Z; ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(IUnknown *,IUnknown * *)
0x180022923  mov     r14d, eax
0x180022926  test    eax, eax
0x180022928  js      loc_1800229DD
0x18002292e  lea     rcx, [rbp+57h+Parameter]; Parameter
0x180022932  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x180022937  nop
0x180022938  mov     rax, [rbx]
0x18002293b  mov     r14, [rbp+57h+var_80]
0x18002293f  mov     r9, r14
0x180022942  mov     r8d, [rbp+57h+var_34]
0x180022946  lea     rdx, [rbp+57h+var_40]
0x18002294a  mov     rcx, rbx
0x18002294d  mov     rax, [rax+18h]
0x180022951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022956  mov     rcx, [rbp+5Fh]; this
0x18002295a  test    eax, eax
0x18002295c  jns     short loc_180022973
0x18002295e  mov     r9d, eax; char *
0x180022961  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180022968  mov     edx, 29Bh; void *
0x18002296d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022972  nop
0x180022973  cmp     [rbp+57h+var_68], 0
0x180022977  jl      short loc_1800229A5
0x180022979  mov     [rbp+57h+var_68], 80004005h
0x180022980  xor     ecx, ecx; pReserved
0x180022982  call    cs:__imp_CoDisableCallCancellation
0x180022988  mov     rdx, [rbp+57h+Timer]; Timer
0x18002298c  test    rdx, rdx
0x18002298f  jz      short loc_1800229A5
0x180022991  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180022995  xor     ecx, ecx; TimerQueue
0x180022997  call    cs:__imp_DeleteTimerQueueTimer
0x18002299d  mov     [rbp+57h+Timer], 0
0x1800229a5  test    r14, r14
0x1800229a8  jz      short loc_1800229BA
0x1800229aa  mov     rax, [r14]
0x1800229ad  mov     rcx, r14
0x1800229b0  mov     rax, [rax+10h]
0x1800229b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229b9  nop
0x1800229ba  mov     rcx, [rbp+57h+var_48]
0x1800229be  mov     [rbp+57h+var_48], 0
0x1800229c6  test    rcx, rcx
0x1800229c9  jz      short loc_1800229D8
0x1800229cb  mov     rax, [rcx]
0x1800229ce  mov     rax, [rax+10h]
0x1800229d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229d7  nop
0x1800229d8  jmp     loc_1800227D0
0x1800229dd  mov     rcx, [rbp+5Fh]; this
0x1800229e1  mov     r9d, r14d; char *
0x1800229e4  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800229eb  mov     edx, 297h; void *
0x1800229f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800229f5  nop
0x1800229f6  mov     rcx, [rbp+57h+var_80]
0x1800229fa  test    rcx, rcx
0x1800229fd  jz      short loc_180022A0C
0x1800229ff  mov     rax, [rcx]
0x180022a02  mov     rax, [rax+10h]
0x180022a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a0b  nop
0x180022a0c  mov     rcx, [rbp+57h+var_48]
0x180022a10  mov     [rbp+57h+var_48], 0
0x180022a18  test    rcx, rcx
0x180022a1b  jz      short loc_180022A2A
0x180022a1d  mov     rax, [rcx]
0x180022a20  mov     rax, [rax+10h]
0x180022a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a29  nop
0x180022a2a  mov     rax, [rbx]
0x180022a2d  mov     rcx, rbx
0x180022a30  mov     rax, [rax+10h]
0x180022a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a39  nop
0x180022a3a  mov     rax, [rsi]
0x180022a3d  mov     rcx, rsi
0x180022a40  mov     rax, [rax+10h]
0x180022a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a49  mov     eax, r14d
0x180022a4c  jmp     short loc_180022A92
0x180022a4e  mov     rcx, [rbp+57h+var_48]
0x180022a52  mov     [rbp+57h+var_48], 0
0x180022a5a  test    rcx, rcx
0x180022a5d  jz      short loc_180022A6C
0x180022a5f  mov     rax, [rcx]
0x180022a62  mov     rax, [rax+10h]
0x180022a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a6b  nop
0x180022a6c  test    rbx, rbx
0x180022a6f  jz      short loc_180022A81
0x180022a71  mov     rax, [rbx]
0x180022a74  mov     rcx, rbx
0x180022a77  mov     rax, [rax+10h]
0x180022a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a80  nop
0x180022a81  mov     rax, [rsi]
0x180022a84  mov     rcx, rsi
0x180022a87  mov     rax, [rax+10h]
0x180022a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a90  xor     eax, eax
0x180022a92  mov     rcx, [rbp+57h+var_30]
0x180022a96  xor     rcx, rsp; StackCookie
0x180022a99  call    __security_check_cookie
0x180022a9e  lea     r11, [rsp+0B0h+var_20]
0x180022aa6  mov     rbx, [r11+38h]
0x180022aaa  mov     rsi, [r11+40h]
0x180022aae  mov     rsp, r11
0x180022ab1  pop     r15
0x180022ab3  pop     r14
0x180022ab5  pop     r13
0x180022ab7  pop     r12
0x180022ab9  pop     rbp
0x180022aba  retn
```
