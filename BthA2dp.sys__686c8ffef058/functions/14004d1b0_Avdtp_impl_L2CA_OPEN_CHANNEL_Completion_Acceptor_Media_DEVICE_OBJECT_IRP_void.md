# Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Acceptor_Media(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14004d1b0`
- end: `0x14004d787`
- name: `?L2CA_OPEN_CHANNEL_Completion_Acceptor_Media@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `1495`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000700c`
- `0x140008810`
- `0x140012a5c`
- `0x140034b60`
- `0x140036494`
- `0x14003b244`
- `0x140046044`
- `0x140046390`
- `0x140048550`
- `0x14004d1b0`
- `0x1400502f0`
- `0x140055404`
- `0x140055bc4`
- `0x14005903c`
- `0x14005c7d0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004d280`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d280`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d470`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d613`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d709`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d470`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d613`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d709`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d3ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d6d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d3ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d6d9`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Acceptor_Media(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        unsigned int *a3,
        __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  char v8; // si
  int IfrRecorderLog; // eax
  __int64 v10; // r10
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rbx
  __int64 v14; // r12
  int v15; // edx
  int v16; // r8d
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  BOOL v18; // r13d
  __int64 v19; // r14
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned int v28; // ebp
  __int64 *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // eax
  __int64 v34; // r10
  int v35; // edx
  int v36; // r8d
  __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  unsigned __int64 v45; // r8
  int v46; // eax
  __int64 v47; // r10
  int v48; // edx
  int v49; // r8d
  KIRQL v50; // al
  __int64 v51; // rsi
  KIRQL v52; // bp
  int v54; // [rsp+20h] [rbp-B8h]
  int v55; // [rsp+28h] [rbp-B0h]
  int v56; // [rsp+30h] [rbp-A8h]
  int v57; // [rsp+38h] [rbp-A0h]
  KIRQL NewIrql; // [rsp+70h] [rbp-68h]
  int v59; // [rsp+74h] [rbp-64h]
  _BYTE v60[32]; // [rsp+78h] [rbp-60h] BYREF

  v8 = 1;
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4) )
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      IfrRecorderLog = GetIfrRecorderLog(2, v6, v7);
      WPP_RECORDER_AND_TRACE_SF_qi(
        *(_QWORD *)(v10 + 24),
        v11,
        v12,
        IfrRecorderLog,
        4,
        4,
        64,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        (char)a3,
        (char)a2);
    }
  }
  v13 = *(_QWORD *)a3;
  v14 = a3[2];
  ExFreePoolWithTag(a3, 0x41564430u);
  SecurityContext = 0;
  v18 = 0;
  if ( a2 )
  {
    SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
    if ( SecurityContext )
    {
      if ( !a2->IoStatus.Status && !HIDWORD(SecurityContext[1].SecurityQos) )
        v18 = 1;
    }
  }
  LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_ddDqqD(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      v16,
      WPP_GLOBAL_Control->DeviceExtension,
      v54,
      v55,
      v56,
      v57,
      a2->IoStatus.Status,
      HIDWORD(SecurityContext[1].SecurityQos),
      (char)SecurityContext[1].AccessState,
      *(_QWORD *)&SecurityContext[4].DesiredAccess,
      v13,
      v14);
  }
  LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      v16,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      66,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
      SecurityContext[15].FullCreateOptions,
      WORD2(SecurityContext[12].SecurityQos));
  }
  if ( (unsigned int)v14 < 4 )
  {
    NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 1600));
    v59 = *(_DWORD *)(v13 + 144);
    v19 = 200 * v14;
    Feature_60817472__private_IsEnabledDeviceUsageNoInline(v21, v20, v22, v23);
    v28 = *(_DWORD *)(200 * v14 + v13 + 232);
    if ( v28 == 3 )
    {
      if ( v18 )
      {
        _InterlockedExchange64((volatile __int64 *)(v19 + v13 + 240), *(_QWORD *)&SecurityContext[4].DesiredAccess);
        if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v25, v24, v26, v27) )
        {
          LOBYTE(v31) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          if ( (_BYTE)v31 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            v33 = GetIfrRecorderLog(2, v31, v32);
            WPP_RECORDER_AND_TRACE_SF_bth_addrqD(
              *(_QWORD *)(v34 + 24),
              v35,
              v36,
              v33,
              v54,
              v55,
              68,
              v57,
              *(_QWORD *)(v13 + 1128),
              *(_QWORD *)&SecurityContext[4].DesiredAccess,
              v14);
          }
        }
        v37 = 4;
        *(_OWORD *)(v19 + v13 + 248) = *(_OWORD *)&SecurityContext[15].DesiredAccess;
        *(_OWORD *)(v19 + v13 + 264) = *(_OWORD *)&SecurityContext[16].AccessState;
        *(_OWORD *)(v19 + v13 + 280) = *(_OWORD *)&SecurityContext[17].SecurityQos;
        *(_OWORD *)(v19 + v13 + 296) = *(_OWORD *)&SecurityContext[17].DesiredAccess;
        *(_OWORD *)(v19 + v13 + 312) = *(_OWORD *)&SecurityContext[18].AccessState;
        *(_OWORD *)(v19 + v13 + 328) = *(_OWORD *)&SecurityContext[12].SecurityQos;
        *(_OWORD *)(v19 + v13 + 344) = *(_OWORD *)&SecurityContext[12].DesiredAccess;
        *(_OWORD *)(v19 + v13 + 360) = *(_OWORD *)&SecurityContext[13].AccessState;
        *(_OWORD *)(v19 + v13 + 376) = *(_OWORD *)&SecurityContext[14].SecurityQos;
        *(_OWORD *)(v19 + v13 + 392) = *(_OWORD *)&SecurityContext[14].DesiredAccess;
      }
      else
      {
        v37 = 1;
      }
      Avdtp_impl::tagSepInfo::SetState(v19 + v13 + 216, v37);
      Avdtp_impl::CopySepsToLocalInfo(
        (const struct Avdtp_impl::tagSepInfo *)(v13 + 216),
        v38,
        (struct SepInfoCopy *)v60,
        v39);
      KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 1600), NewIrql);
      if ( v59 == 7 )
      {
        if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v41, v40, v42, v43) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v8 = 0;
          }
          LOBYTE(v45) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v46 = GetIfrRecorderLog(2, v44, v45);
            LOBYTE(v48) = v8;
            WPP_RECORDER_AND_TRACE_SF_qD(
              *(_QWORD *)(v47 + 24),
              v48,
              v49,
              v46,
              4,
              4,
              69,
              (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
              v13,
              v14);
          }
        }
        Avdtp_impl::AbortOpenMediaChannelsOrDisconnect((Avdtp_impl *)v13, (const struct SepInfoCopy *)v60, v45);
      }
      else if ( v18 )
      {
        v50 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 1600));
        v51 = *(_QWORD *)(v13 + 1144);
        v52 = v50;
        if ( v51 )
          (*(void (__fastcall **)(_QWORD))(v13 + 1168))(*(_QWORD *)(v13 + 1144));
        KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 1600), v52);
        if ( v51 )
        {
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(v13 + 1336))(
            v13,
            *(_QWORD *)(v13 + 1144),
            *(_QWORD *)&SecurityContext[4].DesiredAccess,
            LOWORD(SecurityContext[15].FullCreateOptions),
            WORD2(SecurityContext[12].SecurityQos));
          (*(void (__fastcall **)(__int64))(v13 + 1176))(v51);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v8 = 0;
      }
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v29 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        LOBYTE(v29) = v8;
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_LL(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v29,
          v26,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          4,
          67,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          v14,
          *(_DWORD *)(v19 + v13 + 232));
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 1600), NewIrql);
      if ( v28 != 7 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(v30, v28, 3, "The state of SEP is unexpected");
      Avdtp_impl::Abort_Req((void *)v13, *(_BYTE *)(v19 + v13 + 236));
    }
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14004d1b0  mov     [rsp+arg_0], rbx
0x14004d1b5  push    rbp
0x14004d1b6  push    rsi
0x14004d1b7  push    rdi
0x14004d1b8  push    r12
0x14004d1ba  push    r13
0x14004d1bc  push    r14
0x14004d1be  push    r15
0x14004d1c0  sub     rsp, 0A0h
0x14004d1c7  mov     rax, cs:__security_cookie
0x14004d1ce  xor     rax, rsp
0x14004d1d1  mov     [rsp+0D8h+var_40], rax
0x14004d1d9  mov     rdi, r8
0x14004d1dc  mov     rbp, rdx
0x14004d1df  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004d1e4  lea     r15, WPP_GLOBAL_Control
0x14004d1eb  mov     esi, 1
0x14004d1f0  lea     rcx, WPP_RECORDER_INITIALIZED
0x14004d1f7  lea     rbx, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004d1fe  lea     r14d, [rsi+3]
0x14004d202  test    eax, eax
0x14004d204  jz      short loc_14004D271
0x14004d206  mov     r10, cs:WPP_GLOBAL_Control
0x14004d20d  cmp     r10, r15
0x14004d210  jz      short loc_14004D225
0x14004d212  mov     eax, [r10+2Ch]
0x14004d216  test    al, 8
0x14004d218  jz      short loc_14004D225
0x14004d21a  cmp     [r10+29h], r14b
0x14004d21e  jb      short loc_14004D225
0x14004d220  mov     dl, sil
0x14004d223  jmp     short loc_14004D227
0x14004d225  xor     dl, dl
0x14004d227  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14004d22e  setnz   r8b
0x14004d232  test    dl, dl
0x14004d234  jnz     short loc_14004D23B
0x14004d236  test    r8b, r8b
0x14004d239  jz      short loc_14004D271
0x14004d23b  mov     ecx, 2
0x14004d240  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004d245  mov     rcx, [r10+18h]
0x14004d249  mov     r9, rax
0x14004d24c  mov     [rsp+0D8h+var_90], rbp
0x14004d251  mov     [rsp+0D8h+var_98], rdi
0x14004d256  mov     [rsp+0D8h+var_A0], rbx
0x14004d25b  mov     [rsp+0D8h+var_A8], 40h ; '@'
0x14004d262  mov     [rsp+0D8h+var_B0], r14d
0x14004d267  mov     byte ptr [rsp+0D8h+var_B8], r14b
0x14004d26c  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14004d271  mov     rbx, [rdi]
0x14004d274  mov     edx, 41564430h; Tag
0x14004d279  mov     r12d, [rdi+8]
0x14004d27d  mov     rcx, rdi; P
0x14004d280  call    cs:__imp_ExFreePoolWithTag
0x14004d287  nop     dword ptr [rax+rax+00h]
0x14004d28c  xor     edi, edi
0x14004d28e  test    rbp, rbp
0x14004d291  jz      short loc_14004D2B4
0x14004d293  mov     rax, [rbp+0B8h]
0x14004d29a  mov     rdi, [rax+8]
0x14004d29e  test    rdi, rdi
0x14004d2a1  jz      short loc_14004D2B4
0x14004d2a3  cmp     dword ptr [rbp+30h], 0
0x14004d2a7  jnz     short loc_14004D2B4
0x14004d2a9  cmp     dword ptr [rdi+1Ch], 0
0x14004d2ad  jnz     short loc_14004D2B4
0x14004d2af  mov     r13d, esi
0x14004d2b2  jmp     short loc_14004D2B7
0x14004d2b4  xor     r13d, r13d
0x14004d2b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d2be  cmp     rcx, r15
0x14004d2c1  jz      short loc_14004D2D5
0x14004d2c3  mov     eax, [rcx+2Ch]
0x14004d2c6  test    al, 8
0x14004d2c8  jz      short loc_14004D2D5
0x14004d2ca  cmp     [rcx+29h], r14b
0x14004d2ce  jb      short loc_14004D2D5
0x14004d2d0  mov     dl, sil
0x14004d2d3  jmp     short loc_14004D2D7
0x14004d2d5  xor     dl, dl
0x14004d2d7  lea     r9, WPP_RECORDER_INITIALIZED
0x14004d2de  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14004d2e5  setnz   r8b
0x14004d2e9  test    dl, dl
0x14004d2eb  jnz     short loc_14004D2F2
0x14004d2ed  test    r8b, r8b
0x14004d2f0  jz      short loc_14004D331
0x14004d2f2  mov     rax, [rdi+70h]
0x14004d2f6  movzx   r9d, byte ptr [rdi+20h]
0x14004d2fb  mov     [rsp+0D8h+var_70], r12d
0x14004d300  mov     [rsp+0D8h+var_78], rbx
0x14004d305  mov     [rsp+0D8h+var_80], rax
0x14004d30a  mov     eax, [rdi+1Ch]
0x14004d30d  mov     [rsp+0D8h+var_88], r9d
0x14004d312  mov     r9, [rcx+40h]
0x14004d316  mov     rcx, [rcx+18h]
0x14004d31a  mov     dword ptr [rsp+0D8h+var_90], eax
0x14004d31e  mov     eax, [rbp+30h]
0x14004d321  mov     dword ptr [rsp+0D8h+var_98], eax
0x14004d325  call    WPP_RECORDER_AND_TRACE_SF_ddDqqD
0x14004d32a  lea     r9, WPP_RECORDER_INITIALIZED
0x14004d331  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d338  cmp     rcx, r15
0x14004d33b  jz      short loc_14004D34F
0x14004d33d  mov     eax, [rcx+2Ch]
0x14004d340  test    al, 8
0x14004d342  jz      short loc_14004D34F
0x14004d344  cmp     [rcx+29h], r14b
0x14004d348  jb      short loc_14004D34F
0x14004d34a  mov     dl, sil
0x14004d34d  jmp     short loc_14004D351
0x14004d34f  xor     dl, dl
0x14004d351  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14004d358  setnz   r8b
0x14004d35c  test    dl, dl
0x14004d35e  jnz     short loc_14004D365
0x14004d360  test    r8b, r8b
0x14004d363  jz      short loc_14004D3A7
0x14004d365  movzx   eax, word ptr [rdi+124h]
0x14004d36c  movzx   r9d, word ptr [rdi+17Ch]
0x14004d374  mov     dword ptr [rsp+0D8h+var_90], eax
0x14004d378  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004d37f  mov     dword ptr [rsp+0D8h+var_98], r9d
0x14004d384  mov     r9, [rcx+40h]
0x14004d388  mov     rcx, [rcx+18h]
0x14004d38c  mov     [rsp+0D8h+var_A0], rax
0x14004d391  mov     [rsp+0D8h+var_A8], 42h ; 'B'
0x14004d398  mov     [rsp+0D8h+var_B0], r14d
0x14004d39d  mov     byte ptr [rsp+0D8h+var_B8], r14b
0x14004d3a2  call    WPP_RECORDER_AND_TRACE_SF_DD
0x14004d3a7  cmp     r12d, r14d
0x14004d3aa  jnb     loc_14004D756
0x14004d3b0  lea     r15, [rbx+640h]
0x14004d3b7  mov     rcx, r15; SpinLock
0x14004d3ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004d3c1  nop     dword ptr [rax+rax+00h]
0x14004d3c6  mov     [rsp+0D8h+NewIrql], al
0x14004d3ca  mov     eax, [rbx+90h]
0x14004d3d0  mov     [rsp+0D8h+var_64], eax
0x14004d3d4  imul    r14, r12, 0C8h
0x14004d3db  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004d3e0  mov     ebp, [r14+rbx+0E8h]
0x14004d3e8  cmp     ebp, 3
0x14004d3eb  jz      loc_14004D4AA
0x14004d3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d3f8  lea     rax, WPP_GLOBAL_Control
0x14004d3ff  cmp     rcx, rax
0x14004d402  jz      short loc_14004D411
0x14004d404  mov     eax, [rcx+2Ch]
0x14004d407  test    al, 8
0x14004d409  jz      short loc_14004D411
0x14004d40b  cmp     byte ptr [rcx+29h], 3
0x14004d40f  jnb     short loc_14004D414
0x14004d411  xor     sil, sil
0x14004d414  lea     rax, WPP_RECORDER_INITIALIZED
0x14004d41b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004d422  setnz   r8b
0x14004d426  test    sil, sil
0x14004d429  jnz     short loc_14004D430
0x14004d42b  test    r8b, r8b
0x14004d42e  jz      short loc_14004D469
0x14004d430  mov     r9, [rcx+40h]
0x14004d434  lea     rdx, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004d43b  mov     rcx, [rcx+18h]
0x14004d43f  mov     dword ptr [rsp+0D8h+var_90], ebp
0x14004d443  mov     dword ptr [rsp+0D8h+var_98], r12d
0x14004d448  mov     [rsp+0D8h+var_A0], rdx
0x14004d44d  mov     dl, sil
0x14004d450  mov     [rsp+0D8h+var_A8], 43h ; 'C'
0x14004d457  mov     [rsp+0D8h+var_B0], 4
0x14004d45f  mov     byte ptr [rsp+0D8h+var_B8], 3
0x14004d464  call    WPP_RECORDER_AND_TRACE_SF_LL
0x14004d469  mov     dl, [rsp+0D8h+NewIrql]; NewIrql
0x14004d46d  mov     rcx, r15; SpinLock
0x14004d470  call    cs:__imp_KeReleaseSpinLock
0x14004d477  nop     dword ptr [rax+rax+00h]
0x14004d47c  cmp     ebp, 7
0x14004d47f  jz      short loc_14004D495
0x14004d481  lea     r9, aTheStateOfSepI; "The state of SEP is unexpected"
0x14004d488  mov     r8d, 3
0x14004d48e  mov     edx, ebp
0x14004d490  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14004d495  mov     dl, [r14+rbx+0ECh]; unsigned __int8
0x14004d49d  mov     rcx, rbx; void *
0x14004d4a0  call    ?Abort_Req@Avdtp_impl@@CAJPEAXE@Z; Avdtp_impl::Abort_Req(void *,uchar)
0x14004d4a5  jmp     loc_14004D756
0x14004d4aa  test    r13d, r13d
0x14004d4ad  jz      loc_14004D5EA
0x14004d4b3  mov     rax, [rdi+70h]
0x14004d4b7  xchg    rax, [r14+rbx+0F0h]
0x14004d4bf  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004d4c4  test    eax, eax
0x14004d4c6  jz      short loc_14004D543
0x14004d4c8  mov     r10, cs:WPP_GLOBAL_Control
0x14004d4cf  lea     rax, WPP_GLOBAL_Control
0x14004d4d6  cmp     r10, rax
0x14004d4d9  jz      short loc_14004D4EF
0x14004d4db  mov     eax, [r10+2Ch]
0x14004d4df  test    al, 8
0x14004d4e1  jz      short loc_14004D4EF
0x14004d4e3  cmp     byte ptr [r10+29h], 4
0x14004d4e8  jb      short loc_14004D4EF
0x14004d4ea  mov     dl, sil
0x14004d4ed  jmp     short loc_14004D4F1
0x14004d4ef  xor     dl, dl
0x14004d4f1  lea     rax, WPP_RECORDER_INITIALIZED
0x14004d4f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004d4ff  setnz   r8b
0x14004d503  test    dl, dl
0x14004d505  jnz     short loc_14004D50C
0x14004d507  test    r8b, r8b
0x14004d50a  jz      short loc_14004D543
0x14004d50c  mov     ecx, 2
0x14004d511  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004d516  mov     rcx, [r10+18h]
0x14004d51a  mov     r9, rax
0x14004d51d  mov     rax, [rdi+70h]
0x14004d521  mov     [rsp+0D8h+var_88], r12d
0x14004d526  mov     [rsp+0D8h+var_90], rax
0x14004d52b  mov     rax, [rbx+468h]
0x14004d532  mov     [rsp+0D8h+var_98], rax
0x14004d537  mov     [rsp+0D8h+var_A8], 44h ; 'D'
0x14004d53e  call    WPP_RECORDER_AND_TRACE_SF_bth_addrqD
0x14004d543  movups  xmm0, xmmword ptr [rdi+178h]
0x14004d54a  mov     edx, 4
0x14004d54f  movups  xmmword ptr [r14+rbx+0F8h], xmm0
0x14004d558  movups  xmm1, xmmword ptr [rdi+188h]
0x14004d55f  movups  xmmword ptr [r14+rbx+108h], xmm1
0x14004d568  movups  xmm0, xmmword ptr [rdi+198h]
0x14004d56f  movups  xmmword ptr [r14+rbx+118h], xmm0
0x14004d578  movups  xmm1, xmmword ptr [rdi+1A8h]
0x14004d57f  movups  xmmword ptr [r14+rbx+128h], xmm1
0x14004d588  movups  xmm0, xmmword ptr [rdi+1B8h]
0x14004d58f  movups  xmmword ptr [r14+rbx+138h], xmm0
0x14004d598  movups  xmm0, xmmword ptr [rdi+120h]
0x14004d59f  movups  xmmword ptr [r14+rbx+148h], xmm0
0x14004d5a8  movups  xmm1, xmmword ptr [rdi+130h]
0x14004d5af  movups  xmmword ptr [r14+rbx+158h], xmm1
0x14004d5b8  movups  xmm0, xmmword ptr [rdi+140h]
0x14004d5bf  movups  xmmword ptr [r14+rbx+168h], xmm0
0x14004d5c8  movups  xmm1, xmmword ptr [rdi+150h]
0x14004d5cf  movups  xmmword ptr [r14+rbx+178h], xmm1
0x14004d5d8  movups  xmm0, xmmword ptr [rdi+160h]
0x14004d5df  movups  xmmword ptr [r14+rbx+188h], xmm0
0x14004d5e8  jmp     short loc_14004D5EC
0x14004d5ea  mov     edx, esi
0x14004d5ec  lea     rcx, [rbx+0D8h]
0x14004d5f3  add     rcx, r14
0x14004d5f6  call    ?SetState@tagSepInfo@Avdtp_impl@@QEAAXW4TAG_AvdtpSepState@@@Z; Avdtp_impl::tagSepInfo::SetState(TAG_AvdtpSepState)
0x14004d5fb  lea     rcx, [rbx+0D8h]; struct Avdtp_impl::tagSepInfo *
0x14004d602  lea     r8, [rsp+0D8h+var_60]; struct SepInfoCopy *
0x14004d607  call    ?CopySepsToLocalInfo@Avdtp_impl@@CAXPEBUtagSepInfo@1@_KPEAUSepInfoCopy@@1@Z; Avdtp_impl::CopySepsToLocalInfo(Avdtp_impl::tagSepInfo const *,unsigned __int64,SepInfoCopy *,unsigned __int64)
0x14004d60c  mov     dl, [rsp+0D8h+NewIrql]; NewIrql
0x14004d610  mov     rcx, r15; SpinLock
0x14004d613  call    cs:__imp_KeReleaseSpinLock
0x14004d61a  nop     dword ptr [rax+rax+00h]
0x14004d61f  cmp     [rsp+0D8h+var_64], 7
0x14004d624  jnz     loc_14004D6CD
0x14004d62a  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004d62f  test    eax, eax
0x14004d631  jz      loc_14004D6BB
0x14004d637  mov     r10, cs:WPP_GLOBAL_Control
0x14004d63e  lea     rax, WPP_GLOBAL_Control
0x14004d645  cmp     r10, rax
0x14004d648  jz      short loc_14004D659
0x14004d64a  mov     eax, [r10+2Ch]
0x14004d64e  test    al, 8
0x14004d650  jz      short loc_14004D659
0x14004d652  cmp     byte ptr [r10+29h], 4
0x14004d657  jnb     short loc_14004D65C
0x14004d659  xor     sil, sil
0x14004d65c  lea     rax, WPP_RECORDER_INITIALIZED
0x14004d663  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004d66a  setnz   r8b
0x14004d66e  test    sil, sil
0x14004d671  jnz     short loc_14004D678
0x14004d673  test    r8b, r8b
0x14004d676  jz      short loc_14004D6BB
0x14004d678  mov     ecx, 2
0x14004d67d  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004d682  mov     rcx, [r10+18h]
0x14004d686  mov     r9, rax
0x14004d689  mov     dword ptr [rsp+0D8h+var_90], r12d
0x14004d68e  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004d695  mov     [rsp+0D8h+var_98], rbx
0x14004d69a  mov     dl, sil
0x14004d69d  mov     [rsp+0D8h+var_A0], rax
0x14004d6a2  mov     [rsp+0D8h+var_A8], 45h ; 'E'
0x14004d6a9  mov     [rsp+0D8h+var_B0], 4
0x14004d6b1  mov     byte ptr [rsp+0D8h+var_B8], 4
0x14004d6b6  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14004d6bb  lea     rdx, [rsp+0D8h+var_60]; struct SepInfoCopy *
0x14004d6c0  mov     rcx, rbx; this
0x14004d6c3  call    ?AbortOpenMediaChannelsOrDisconnect@Avdtp_impl@@AEAAXPEBUSepInfoCopy@@_K@Z; Avdtp_impl::AbortOpenMediaChannelsOrDisconnect(SepInfoCopy const *,unsigned __int64)
0x14004d6c8  jmp     loc_14004D756
0x14004d6cd  test    r13d, r13d
0x14004d6d0  jz      loc_14004D756
0x14004d6d6  mov     rcx, r15; SpinLock
0x14004d6d9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
  ... truncated ...
```
