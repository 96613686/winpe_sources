# PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::Set(void *,_TASK_TRIGGER *,_TASK_RUNTIME_DATA *,TimeValue const &,TimeValue const &,uchar,ulong)

- ea: `0x1800068b0`
- end: `0x180006da9`
- name: `?Set@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXPEAU_TASK_TRIGGER@@PEAU_TASK_RUNTIME_DATA@@AEBVTimeValue@@3EK@Z`
- size: `1273`
- prototype: `__int64 __fastcall(CScheduleMgr *pv, void *, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, unsigned __int8, char)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800068b0`
- `0x180006db0`
- `0x18000e970`
- `0x18000e9c8`
- `0x18000ea40`
- `0x180010276`
- `0x180020a64`
- `0x180020c30`

## import_xrefs

- `msvcrt!malloc` at `0x180006994`
- `msvcrt!malloc` at `0x180006994`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180006d18`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180006d18`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180006cbe`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180006cbe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006c2f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006c2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006be5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006be5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006bf7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006bf7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006c04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b0c`
- `ntdll!NtCreateWnfStateName` at `0x180006d03`
- `ntdll!NtCreateWnfStateName` at `0x180006d03`
- `ntdll!NtDeleteWnfStateName` at `0x180006ba8`
- `ntdll!NtDeleteWnfStateName` at `0x180006ba8`
- `ntdll!RtlQueryWnfStateData` at `0x180006c77`
- `ntdll!RtlQueryWnfStateData` at `0x180006c77`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180006b5d`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180006b5d`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x180006d9b`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x180006d9b`

## string_xrefs

- `0x180006cb2`: `TaskSchedulerWNFEventAccess`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::Set(
        CScheduleMgr *pv,
        void *a2,
        struct _TASK_TRIGGER *a3,
        struct _TASK_RUNTIME_DATA *a4,
        const struct TimeValue *a5,
        const struct TimeValue *a6,
        unsigned __int8 a7,
        char a8)
{
  CScheduleMgr *v9; // rbx
  __int64 v10; // rdi
  int v11; // eax
  signed int v12; // r14d
  const void *v13; // r12
  unsigned int v14; // esi
  void *v15; // rax
  void *v16; // r15
  __int64 v17; // r8
  unsigned int v18; // r9d
  bool v19; // zf
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  signed int LastError; // eax
  int v25; // eax
  struct _TP_TIMER *v26; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int v28; // eax
  int v29; // eax
  int WnfStateName; // eax
  __int64 v31; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B8h] BYREF
  int v33; // [rsp+58h] [rbp-B0h] BYREF
  int v34; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+68h] [rbp-A0h]
  _BYTE v36[36]; // [rsp+78h] [rbp-90h] BYREF
  int v37; // [rsp+9Ch] [rbp-6Ch]
  __int128 v38; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-50h]
  __int128 v40; // [rsp+C8h] [rbp-40h]
  __int64 *v41; // [rsp+D8h] [rbp-30h]
  __int64 v42; // [rsp+E0h] [rbp-28h]

  v9 = pv;
  if ( !a3 || !a2 )
    return 2147500035LL;
  v10 = *(_QWORD *)&a3->wBeginDay;
  if ( v10 )
  {
    v11 = *(_DWORD *)(v10 + 8);
    if ( v11 >= 7 )
      return (unsigned int)-2100362986;
    if ( v11 >= 3 )
    {
      pv = (CScheduleMgr *)*(unsigned int *)(v10 + 12);
      if ( (((_DWORD)pv - 1) & 0xFFFFFFFC) != 0 || (_DWORD)pv == 3 )
        return (unsigned int)-2100362986;
    }
    if ( (*(_DWORD *)(v10 + 28) & 0xFFFFFFF8) != 0 )
    {
      return (unsigned int)-2100362986;
    }
    else
    {
      v12 = 0;
      if ( *((_QWORD *)v9 + 35) )
      {
        v25 = CSebDeleteEvent(*((_QWORD *)v9 + 35));
        v12 = v25;
        if ( v25 < 0 && (byte_180030D06 & 8) != 0 )
          McTemplateU0qqq_EventWriteTransfer(
            *((_DWORD *)v9 + 71),
            (unsigned int)ErrorDeleteCSebEvent,
            v25,
            *((_DWORD *)v9 + 70),
            *((_DWORD *)v9 + 71));
        *((_QWORD *)v9 + 35) = 0;
      }
      if ( *((_QWORD *)v9 + 34) )
      {
        NtDeleteWnfStateName((char *)v9 + 272);
        *((_QWORD *)v9 + 34) = 0;
      }
      *((_QWORD *)v9 + 22) = a2;
      *((_OWORD *)v9 + 13) = *(_OWORD *)v10;
      *((_OWORD *)v9 + 14) = *(_OWORD *)(v10 + 16);
      v13 = *(const void **)(v10 + 16);
      if ( v13 && (v14 = *(_DWORD *)(v10 + 12)) != 0 && (v15 = malloc(v14), (v16 = v15) != 0) )
        memcpy_0(v15, v13, v14);
      else
        v16 = 0;
      *((_QWORD *)v9 + 28) = v16;
      *((_OWORD *)v9 + 15) = 0;
      v17 = *((unsigned int *)v9 + 58);
      if ( (_DWORD)v17 )
      {
        if ( (byte_180030D04 & 0x10) != 0 )
          McTemplateU0q_EventWriteTransfer(pv, DelayedWNFTrigger, v17);
        v26 = (struct _TP_TIMER *)*((_QWORD *)v9 + 32);
        if ( v26 )
        {
          SetThreadpoolTimer(v26, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)v9 + 32), 1);
          CloseThreadpoolTimer(*((PTP_TIMER *)v9 + 32));
          *((_QWORD *)v9 + 32) = 0;
        }
        _InterlockedExchange64((volatile __int64 *)v9 + 33, 0);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::WNFDelayTimerCallback,
                            v9,
                            &ThreadpoolCallBackEnvironment);
        *((_QWORD *)v9 + 32) = ThreadpoolTimer;
        if ( !ThreadpoolTimer )
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      if ( v12 < 0 )
        return (unsigned int)v12;
      if ( !*(_QWORD *)(v10 + 16) || *((_QWORD *)v9 + 28) )
      {
        v18 = 0;
        v19 = (*((_BYTE *)v9 + 236) & 1) == 0;
        LODWORD(v31) = 0;
        if ( v19 && (a8 & 2) != 0 )
        {
          if ( (unsigned int)RtlQueryWnfStateData(&v31, *((_QWORD *)v9 + 26), Trigger::GetBrokeredEventId, 0, 0) )
          {
            v18 = 0;
            LODWORD(v31) = 0;
          }
          else
          {
            v18 = v31;
          }
        }
        v20 = CScheduleMgr::SubscribeWnfStateChangeNotify(
                pv,
                (struct _WNF_USER_SUBSCRIPTION **)v9 + 25,
                *(struct _WNF_STATE_NAME *)((char *)v9 + 208),
                v18,
                *((struct CSchedule **)v9 + 22));
        if ( v20 < 0 )
        {
          v28 = HRESULTFromNTSTATUS(v20);
        }
        else
        {
          if ( (a8 & 1) == 0 )
            goto LABEL_21;
          v32 = 0;
          v29 = QueryTransientObjectSecurityDescriptor(10, L"TaskSchedulerWNFEventAccess", &v32);
          v12 = HRESULTFromNTSTATUS(v29);
          if ( v12 < 0 )
            goto LABEL_21;
          WnfStateName = NtCreateWnfStateName((char *)v9 + 272, 3, 0);
          v12 = HRESULTFromNTSTATUS(WnfStateName);
          FreeTransientObjectSecurityDescriptor(v32);
          if ( v12 < 0 )
            goto LABEL_21;
          *(_QWORD *)&v35 = *((_QWORD *)v9 + 34);
          memset(&v36[12], 0, 24);
          *((_QWORD *)&v35 + 1) = 0x10000101CLL;
          *(_DWORD *)v36 = 1;
          *(_QWORD *)&v36[4] = 1;
          v37 = 0;
          v38 = v35;
          v39 = *(_OWORD *)v36;
          v40 = *(_OWORD *)&v36[16];
          v41 = 0;
          v28 = CSebCreatePrivateEvent(&v38, (char *)v9 + 280);
        }
        v12 = v28;
LABEL_21:
        if ( (byte_180030D04 & 0x10) != 0 )
        {
          LODWORD(v32) = v31;
          v34 = *((_DWORD *)v9 + 53);
          v33 = *((_DWORD *)v9 + 52);
          *(_QWORD *)&v39 = &v33;
          *(_QWORD *)&v40 = &v34;
          v41 = &v32;
          *((_QWORD *)&v39 + 1) = 4;
          *((_QWORD *)&v40 + 1) = 4;
          v42 = 4;
          McGenEventWrite_EventWriteTransfer(v21, L"a", v22, 4, &v38);
        }
        return (unsigned int)v12;
      }
      return (unsigned int)-2147024882;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800068b0  mov     r11, rsp
0x1800068b3  push    rbp
0x1800068b4  push    rbx
0x1800068b5  push    rsi
0x1800068b6  lea     rbp, [r11-28h]
0x1800068ba  sub     rsp, 110h
0x1800068c1  mov     rax, cs:__security_cookie
0x1800068c8  xor     rax, rsp
0x1800068cb  mov     [rbp+20h+var_40], rax
0x1800068cf  mov     rsi, rdx
0x1800068d2  mov     rbx, rcx
0x1800068d5  test    r8, r8
0x1800068d8  jz      loc_180006AFA
0x1800068de  test    rdx, rdx
0x1800068e1  jz      loc_180006AFA
0x1800068e7  mov     [r11+10h], rdi
0x1800068eb  mov     rdi, [r8+8]
0x1800068ef  test    rdi, rdi
0x1800068f2  jz      loc_180006B2D
0x1800068f8  mov     eax, [rdi+8]
0x1800068fb  mov     [r11-30h], r14
0x1800068ff  cmp     eax, 7
0x180006902  jge     loc_180006A83
0x180006908  cmp     eax, 3
0x18000690b  jge     loc_180006B37
0x180006911  test    dword ptr [rdi+1Ch], 0FFFFFFF8h
0x180006918  jnz     loc_180006A83
0x18000691e  mov     eax, [rbx+11Ch]
0x180006924  xor     r14d, r14d
0x180006927  or      eax, [rbx+118h]
0x18000692d  mov     [rsp+108h], r12
0x180006935  mov     [rsp+120h+var_20], r13
0x18000693d  mov     [rsp+120h+var_30], r15
0x180006945  jnz     loc_180006B56
0x18000694b  mov     eax, [rbx+114h]
0x180006951  or      eax, [rbx+110h]
0x180006957  jnz     loc_180006BA1
0x18000695d  mov     [rbx+0B0h], rsi
0x180006964  movups  xmm0, xmmword ptr [rdi]
0x180006967  movups  xmmword ptr [rbx+0D0h], xmm0
0x18000696e  movups  xmm1, xmmword ptr [rdi+10h]
0x180006972  movups  xmmword ptr [rbx+0E0h], xmm1
0x180006979  mov     r12, [rdi+10h]
0x18000697d  test    r12, r12
0x180006980  jz      loc_180006B04
0x180006986  mov     esi, [rdi+0Ch]
0x180006989  test    rsi, rsi
0x18000698c  jz      loc_180006B04
0x180006992  mov     ecx, esi; Size
0x180006994  call    cs:__imp_malloc
0x18000699a  mov     r15, rax
0x18000699d  test    rax, rax
0x1800069a0  jz      loc_180006B04
0x1800069a6  mov     r8d, esi; Size
0x1800069a9  mov     rdx, r12; Src
0x1800069ac  mov     rcx, rax; void *
0x1800069af  call    memcpy_0
0x1800069b4  mov     r12, [rsp+108h]
0x1800069bc  xorps   xmm0, xmm0
0x1800069bf  mov     [rbx+0E0h], r15
0x1800069c6  mov     r15, [rsp+120h+var_30]
0x1800069ce  movups  xmmword ptr [rbx+0F0h], xmm0
0x1800069d5  mov     r8d, [rbx+0E8h]
0x1800069dc  test    r8d, r8d
0x1800069df  jnz     loc_180006BBC
0x1800069e5  test    r14d, r14d
0x1800069e8  js      short loc_180006A51
0x1800069ea  cmp     qword ptr [rdi+10h], 0
0x1800069ef  jz      short loc_1800069FF
0x1800069f1  cmp     qword ptr [rbx+0E0h], 0
0x1800069f9  jz      loc_180006C4A
0x1800069ff  mov     edi, [rbp+20h+arg_38]
0x180006a02  xor     r9d, r9d; unsigned int
0x180006a05  test    byte ptr [rbx+0ECh], 1
0x180006a0c  mov     dword ptr [rsp+120h+var_E0], r9d
0x180006a11  jz      loc_180006C55
0x180006a17  mov     rax, [rbx+0B0h]
0x180006a1e  lea     rdx, [rbx+0C8h]; struct _WNF_USER_SUBSCRIPTION **
0x180006a25  mov     r8, [rbx+0D0h]; struct _WNF_STATE_NAME
0x180006a2c  mov     [rsp+120h+var_100], rax; struct CSchedule *
0x180006a31  call    ?SubscribeWnfStateChangeNotify@CScheduleMgr@@QEAAJPEAPEAU_WNF_USER_SUBSCRIPTION@@U_WNF_STATE_NAME@@KPEAVCSchedule@@@Z; CScheduleMgr::SubscribeWnfStateChangeNotify(_WNF_USER_SUBSCRIPTION * *,_WNF_STATE_NAME,ulong,CSchedule *)
0x180006a36  test    eax, eax
0x180006a38  js      loc_180006C98
0x180006a3e  test    dil, 1
0x180006a42  jnz     loc_180006CA4
0x180006a48  test    cs:byte_180030D04, 10h
0x180006a4f  jnz     short loc_180006A8B
0x180006a51  mov     r13, [rsp+120h+var_20]
0x180006a59  mov     eax, r14d
0x180006a5c  mov     r14, [rsp+120h+var_28]
0x180006a64  mov     rdi, [rsp+120h+arg_8]
0x180006a6c  mov     rcx, [rbp+20h+var_40]
0x180006a70  xor     rcx, rsp; StackCookie
0x180006a73  call    __security_check_cookie
0x180006a78  add     rsp, 110h
0x180006a7f  pop     rsi
0x180006a80  pop     rbx
0x180006a81  pop     rbp
0x180006a82  retn
0x180006a83  mov     r14d, 82CF0116h
0x180006a89  jmp     short loc_180006A59
0x180006a8b  mov     eax, dword ptr [rsp+120h+var_E0]
0x180006a8f  lea     rdx, WNFTriggerEvent; "a"
0x180006a96  mov     dword ptr [rsp+120h+var_D8], eax
0x180006a9a  mov     r9d, 4
0x180006aa0  mov     eax, [rbx+0D4h]
0x180006aa6  mov     dword ptr [rsp+120h+var_C8], eax
0x180006aaa  mov     eax, [rbx+0D0h]
0x180006ab0  mov     [rsp+120h+var_D0], eax
0x180006ab4  lea     rax, [rsp+120h+var_D0]
0x180006ab9  mov     qword ptr [rbp+20h+var_70], rax
0x180006abd  lea     rax, [rsp+120h+var_C8]
0x180006ac2  mov     qword ptr [rbp+20h+var_60], rax
0x180006ac6  lea     rax, [rsp+120h+var_D8]
0x180006acb  mov     [rbp+20h+var_50], rax
0x180006acf  lea     rax, [rbp+20h+var_80]
0x180006ad3  mov     [rsp+120h+var_100], rax
0x180006ad8  mov     qword ptr [rbp+20h+var_70+8], 4
0x180006ae0  mov     qword ptr [rbp+20h+var_60+8], 4
0x180006ae8  mov     [rbp+20h+var_48], 4
0x180006af0  call    McGenEventWrite_EventWriteTransfer
0x180006af5  jmp     loc_180006A51
0x180006afa  mov     eax, 80004003h
0x180006aff  jmp     loc_180006A6C
0x180006b04  xor     r15d, r15d
0x180006b07  jmp     loc_1800069B4
0x180006b0c  call    cs:__imp_GetLastError
0x180006b12  mov     r14d, eax
0x180006b15  test    eax, eax
0x180006b17  jle     loc_1800069E5
0x180006b1d  movzx   r14d, ax
0x180006b21  or      r14d, 80070000h
0x180006b28  jmp     loc_1800069E5
0x180006b2d  mov     eax, 80070057h
0x180006b32  jmp     loc_180006A64
0x180006b37  mov     ecx, [rdi+0Ch]
0x180006b3a  lea     eax, [rcx-1]
0x180006b3d  test    eax, 0FFFFFFFCh
0x180006b42  jnz     loc_180006A83
0x180006b48  cmp     ecx, 3
0x180006b4b  jz      loc_180006A83
0x180006b51  jmp     loc_180006911
0x180006b56  mov     rcx, [rbx+118h]
0x180006b5d  call    cs:__imp_CSebDeleteEvent
0x180006b63  mov     r14d, eax
0x180006b66  test    eax, eax
0x180006b68  jns     short loc_180006B93
0x180006b6a  test    cs:byte_180030D06, 8
0x180006b71  jz      short loc_180006B93
0x180006b73  mov     ecx, [rbx+11Ch]
0x180006b79  lea     rdx, ErrorDeleteCSebEvent
0x180006b80  mov     r9d, [rbx+118h]
0x180006b87  mov     r8d, eax
0x180006b8a  mov     dword ptr [rsp+120h+var_100], ecx
0x180006b8e  call    McTemplateU0qqq_EventWriteTransfer
0x180006b93  xor     eax, eax
0x180006b95  mov     [rbx+118h], rax
0x180006b9c  jmp     loc_18000694B
0x180006ba1  lea     rcx, [rbx+110h]
0x180006ba8  call    cs:__imp_NtDeleteWnfStateName
0x180006bae  xor     eax, eax
0x180006bb0  mov     [rbx+110h], rax
0x180006bb7  jmp     loc_18000695D
0x180006bbc  test    cs:byte_180030D04, 10h
0x180006bc3  jz      short loc_180006BD1
0x180006bc5  lea     rdx, DelayedWNFTrigger
0x180006bcc  call    McTemplateU0q_EventWriteTransfer
0x180006bd1  mov     rcx, [rbx+100h]; pti
0x180006bd8  test    rcx, rcx
0x180006bdb  jz      short loc_180006C15
0x180006bdd  xor     r9d, r9d; msWindowLength
0x180006be0  xor     r8d, r8d; msPeriod
0x180006be3  xor     edx, edx; pftDueTime
0x180006be5  call    cs:__imp_SetThreadpoolTimer
0x180006beb  mov     rcx, [rbx+100h]; pti
0x180006bf2  mov     edx, 1; fCancelPendingCallbacks
0x180006bf7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006bfd  mov     rcx, [rbx+100h]; pti
0x180006c04  call    cs:__imp_CloseThreadpoolTimer
0x180006c0a  mov     qword ptr [rbx+100h], 0
0x180006c15  xor     eax, eax
0x180006c17  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180006c1e  xchg    rax, [rbx+108h]
0x180006c25  mov     rdx, rbx; pv
0x180006c28  lea     rcx, ?WNFDelayTimerCallback@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006c2f  call    cs:__imp_CreateThreadpoolTimer
0x180006c35  mov     [rbx+100h], rax
0x180006c3c  test    rax, rax
0x180006c3f  jnz     loc_1800069E5
0x180006c45  jmp     loc_180006B0C
0x180006c4a  mov     r14d, 8007000Eh
0x180006c50  jmp     loc_180006A51
0x180006c55  test    dil, 2
0x180006c59  jz      loc_180006A17
0x180006c5f  mov     rdx, [rbx+0D0h]
0x180006c66  lea     r8, ?GetBrokeredEventId@Trigger@@UEAAHPEAU_CBROKERED_EVENT_ID@@@Z; Trigger::GetBrokeredEventId(_CBROKERED_EVENT_ID *)
0x180006c6d  lea     rcx, [rsp+120h+var_E0]
0x180006c72  mov     [rsp+120h+var_100], r9
0x180006c77  call    cs:__imp_RtlQueryWnfStateData
0x180006c7d  test    eax, eax
0x180006c7f  jz      short loc_180006C8E
0x180006c81  xor     r9d, r9d
0x180006c84  mov     dword ptr [rsp+120h+var_E0], r9d
0x180006c89  jmp     loc_180006A17
0x180006c8e  mov     r9d, dword ptr [rsp+120h+var_E0]
0x180006c93  jmp     loc_180006A17
0x180006c98  mov     ecx, eax; int
0x180006c9a  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x180006c9f  jmp     loc_180006DA1
0x180006ca4  lea     r8, [rsp+120h+var_D8]
0x180006ca9  mov     [rsp+120h+var_D8], 0
0x180006cb2  lea     rdx, aTaskschedulerw; "TaskSchedulerWNFEventAccess"
0x180006cb9  mov     ecx, 0Ah
0x180006cbe  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180006cc4  mov     ecx, eax; int
0x180006cc6  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x180006ccb  mov     r14d, eax
0x180006cce  test    eax, eax
0x180006cd0  js      loc_180006A48
0x180006cd6  mov     rax, [rsp+120h+var_D8]
0x180006cdb  lea     rcx, [rbx+110h]
0x180006ce2  mov     [rsp+30h], rax
0x180006ce7  xor     r9d, r9d
0x180006cea  mov     dword ptr [rsp+120h+var_F8], 8
0x180006cf2  xor     r8d, r8d
0x180006cf5  mov     edx, 3
0x180006cfa  mov     [rsp+120h+var_100], 0
0x180006d03  call    cs:__imp_NtCreateWnfStateName
0x180006d09  mov     ecx, eax; int
0x180006d0b  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x180006d10  mov     rcx, [rsp+120h+var_D8]
0x180006d15  mov     r14d, eax
0x180006d18  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180006d1e  test    r14d, r14d
0x180006d21  js      loc_180006A48
0x180006d27  mov     rax, [rbx+110h]
0x180006d2e  lea     rdx, [rbx+118h]
0x180006d35  xorps   xmm0, xmm0
0x180006d38  mov     qword ptr [rsp+120h+var_C8+8], rax
0x180006d3d  movdqu  xmmword ptr [rsp+7Ch], xmm0
0x180006d43  mov     [rbp+20h+var_94], 0
0x180006d4b  lea     rcx, [rbp+20h+var_80]
0x180006d4f  mov     dword ptr [rsp+120h+var_B8], 101Ch
0x180006d57  mov     dword ptr [rsp+120h+var_B8+4], 1
0x180006d5f  movups  xmm0, [rsp+120h+var_C8+8]
0x180006d64  mov     dword ptr [rsp+120h+var_B8+8], 1
0x180006d6c  mov     qword ptr [rsp+120h+var_B8+0Ch], 1
0x180006d75  movups  xmm1, [rsp+120h+var_B8+8]
0x180006d7a  mov     [rbp+20h+var_8C], 0
0x180006d81  movaps  [rbp+20h+var_80], xmm0
0x180006d85  movups  xmm0, xmmword ptr [rbp-80h]
0x180006d89  movaps  [rbp+20h+var_70], xmm1
0x180006d8d  movsd   xmm1, [rbp+20h+var_94+4]
0x180006d92  movaps  [rbp+20h+var_60], xmm0
0x180006d96  movsd   [rbp+20h+var_50], xmm1
0x180006d9b  call    cs:__imp_CSebCreatePrivateEvent
0x180006da1  mov     r14d, eax
0x180006da4  jmp     loc_180006A48
```
