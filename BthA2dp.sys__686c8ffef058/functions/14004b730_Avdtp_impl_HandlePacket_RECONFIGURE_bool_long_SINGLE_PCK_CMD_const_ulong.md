# Avdtp_impl::HandlePacket_RECONFIGURE(bool,long,_SINGLE_PCK_CMD const *,ulong)

- ea: `0x14004b730`
- end: `0x14004baf9`
- name: `?HandlePacket_RECONFIGURE@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@K@Z`
- size: `969`
- prototype: `void __fastcall(KSPIN_LOCK *this, __int64, __int64, const struct _SINGLE_PCK_CMD *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x14004e5fc`

## callees

- `0x140003530`
- `0x14000f570`
- `0x14002d890`
- `0x140036494`
- `0x14003b244`
- `0x140049870`
- `0x14004b730`
- `0x14004f510`
- `0x140056048`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004ba02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004baaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004ba02`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004baaf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b9d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004ba7f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b9d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004ba7f`

## pseudocode

```c
void __fastcall Avdtp_impl::HandlePacket_RECONFIGURE(
        KSPIN_LOCK *this,
        __int64 a2,
        __int64 a3,
        const struct _SINGLE_PCK_CMD *a4,
        unsigned int a5)
{
  char v6; // r14
  unsigned int v7; // ebp
  PDEVICE_OBJECT v9; // rcx
  char v10; // di
  __int64 *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int IfrRecorderLog; // eax
  __int64 v17; // r11
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // r13d
  int v21; // r8d
  __int64 *v22; // rdx
  __int64 *v23; // rdx
  unsigned __int8 v24; // r9
  unsigned __int8 v25; // dl
  KIRQL v26; // al
  KSPIN_LOCK v27; // rdi
  KIRQL v28; // r15
  __int64 v29; // r9
  char v30; // bp
  char v31; // si
  KIRQL v32; // al
  KIRQL v33; // r15
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // [rsp+30h] [rbp-88h]
  unsigned int EndpointIndexByLocalSeid_AndReturnState; // [rsp+60h] [rbp-58h]
  int v38; // [rsp+C8h] [rbp+10h] BYREF

  v6 = a2;
  v7 = a3;
  v9 = WPP_GLOBAL_Control;
  v10 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v11 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      190,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
      (char)this);
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v9, a2, a3, v11) )
  {
    LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      IfrRecorderLog = GetIfrRecorderLog(1, v12, v14);
      LOWORD(v36) = 191;
      WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq(*(_QWORD *)(v17 + 24), v18, v19, IfrRecorderLog);
    }
  }
  if ( v6 )
  {
    v20 = a5;
    if ( a5 < 5 )
    {
      if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v13, v12, v14, v15) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v10 = 0;
        }
        if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v22 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
          LOBYTE(v22) = v10;
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v22,
            v21,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            192,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
            (char)this);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v10 = 0;
        }
        if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
          LOBYTE(v23) = v10;
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v23,
            v21,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            193,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
        }
      }
      v24 = 17;
      goto LABEL_36;
    }
    v25 = *((_BYTE *)a4 + 2) >> 2;
    v38 = 0;
    EndpointIndexByLocalSeid_AndReturnState = Avdtp_impl::FindEndpointIndexByLocalSeid_AndReturnState(
                                                (Avdtp_impl *)this,
                                                v25,
                                                (enum TAG_AvdtpSepState *)&v38);
    if ( EndpointIndexByLocalSeid_AndReturnState == 4 )
    {
      v24 = 18;
LABEL_36:
      Avdtp_impl::Reconfigure_Rsp(v7, (Avdtp_impl *)this, 0, v24);
      return;
    }
    if ( *((_BYTE *)a4 + 3) != 1 && *((_BYTE *)a4 + 3) != 2 && *((_BYTE *)a4 + 3) != 3 )
    {
      if ( *((_BYTE *)a4 + 3) == 4 )
        goto LABEL_47;
      if ( *((_BYTE *)a4 + 3) != 5 && *((_BYTE *)a4 + 3) != 6 )
      {
        if ( *((_BYTE *)a4 + 3) != 7 )
        {
          v24 = 23;
          goto LABEL_36;
        }
LABEL_47:
        if ( (unsigned int)(v38 - 2) > 2 )
        {
          v24 = 49;
          goto LABEL_36;
        }
        v26 = KeAcquireSpinLockRaiseToDpc(this + 200);
        v27 = this[143];
        v28 = v26;
        if ( v27 )
          ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
        KeReleaseSpinLock(this + 200, v28);
        if ( v27 )
        {
          LOBYTE(v29) = *((_BYTE *)a4 + 2) >> 2;
          ((void (__fastcall *)(_QWORD, KSPIN_LOCK *, KSPIN_LOCK, __int64, char *, unsigned int, int))this[163])(
            v7,
            this,
            this[25 * EndpointIndexByLocalSeid_AndReturnState + 27],
            v29,
            (char *)a4 + 3,
            v20 - 3,
            v36);
LABEL_61:
          ((void (__fastcall *)(KSPIN_LOCK))this[147])(v27);
          return;
        }
        return;
      }
    }
    v24 = 26;
    goto LABEL_36;
  }
  if ( (*(_BYTE *)a4 & 3) == 2 )
  {
    v30 = 0;
    v31 = 0;
  }
  else
  {
    v30 = *((_BYTE *)a4 + 3);
    v31 = *((_BYTE *)a4 + 2);
  }
  v32 = KeAcquireSpinLockRaiseToDpc(this + 200);
  v27 = this[143];
  v33 = v32;
  if ( v27 )
    ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
  KeReleaseSpinLock(this + 200, v33);
  if ( v27 )
  {
    LOBYTE(v35) = v31;
    LOBYTE(v34) = v30;
    ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK, __int64, __int64))this[164])(this, v27, v34, v35);
    goto LABEL_61;
  }
}

```

## disassembly

```asm
0x14004b730  push    rbx
0x14004b732  push    rbp
0x14004b733  push    rsi
0x14004b734  push    rdi
0x14004b735  push    r12
0x14004b737  push    r13
0x14004b739  push    r14
0x14004b73b  push    r15
0x14004b73d  sub     rsp, 78h
0x14004b741  mov     rsi, r9
0x14004b744  movzx   r14d, dl
0x14004b748  mov     ebp, r8d
0x14004b74b  mov     rbx, rcx
0x14004b74e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b755  lea     r15, WPP_GLOBAL_Control
0x14004b75c  mov     edi, 1
0x14004b761  lea     r12d, [rdi+3]
0x14004b765  cmp     rcx, r15
0x14004b768  jz      short loc_14004B77C
0x14004b76a  mov     eax, [rcx+2Ch]
0x14004b76d  test    al, 8
0x14004b76f  jz      short loc_14004B77C
0x14004b771  cmp     [rcx+29h], r12b
0x14004b775  jb      short loc_14004B77C
0x14004b777  mov     dl, dil
0x14004b77a  jmp     short loc_14004B77E
0x14004b77c  xor     dl, dl
0x14004b77e  lea     r13, WPP_RECORDER_INITIALIZED
0x14004b785  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004b78c  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b793  setnz   r8b
0x14004b797  test    dl, dl
0x14004b799  jnz     short loc_14004B7A0
0x14004b79b  test    r8b, r8b
0x14004b79e  jz      short loc_14004B7C8
0x14004b7a0  mov     [rsp+0B8h+var_78], rbx
0x14004b7a5  mov     [rsp+0B8h+var_80], r9
0x14004b7aa  mov     r9, [rcx+40h]
0x14004b7ae  mov     rcx, [rcx+18h]
0x14004b7b2  mov     [rsp+0B8h+var_88], 0BEh
0x14004b7b9  mov     [rsp+0B8h+var_90], r12d
0x14004b7be  mov     byte ptr [rsp+0B8h+var_98], r12b
0x14004b7c3  call    WPP_RECORDER_AND_TRACE_SF_q
0x14004b7c8  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004b7cd  test    eax, eax
0x14004b7cf  jz      short loc_14004B836
0x14004b7d1  mov     r11, cs:WPP_GLOBAL_Control
0x14004b7d8  cmp     r11, r15
0x14004b7db  jz      short loc_14004B7F0
0x14004b7dd  mov     eax, [r11+2Ch]
0x14004b7e1  test    al, 8
0x14004b7e3  jz      short loc_14004B7F0
0x14004b7e5  cmp     [r11+29h], r12b
0x14004b7e9  jb      short loc_14004B7F0
0x14004b7eb  mov     dl, dil
0x14004b7ee  jmp     short loc_14004B7F2
0x14004b7f0  xor     dl, dl
0x14004b7f2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14004b7f9  setnz   r8b
0x14004b7fd  test    dl, dl
0x14004b7ff  jnz     short loc_14004B806
0x14004b801  test    r8b, r8b
0x14004b804  jz      short loc_14004B836
0x14004b806  mov     rcx, rdi
0x14004b809  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004b80e  mov     rcx, [r11+18h]
0x14004b812  mov     r9, rax
0x14004b815  mov     [rsp+0B8h+var_68], rbx
0x14004b81a  mov     [rsp+0B8h+var_70], ebp
0x14004b81e  mov     dword ptr [rsp+0B8h+var_78], r14d
0x14004b823  mov     [rsp+0B8h+var_88], 0BFh
0x14004b82a  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq
0x14004b82f  lea     r15, WPP_GLOBAL_Control
0x14004b836  test    r14b, r14b
0x14004b839  jz      loc_14004BA5D
0x14004b83f  mov     r13d, [rsp+0B8h+arg_20]
0x14004b847  cmp     r13d, 5
0x14004b84b  jnb     loc_14004B944
0x14004b851  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004b856  test    eax, eax
0x14004b858  jz      short loc_14004B8CA
0x14004b85a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b861  cmp     rcx, r15
0x14004b864  jz      short loc_14004B873
0x14004b866  mov     eax, [rcx+2Ch]
0x14004b869  test    al, 8
0x14004b86b  jz      short loc_14004B873
0x14004b86d  cmp     byte ptr [rcx+29h], 2
0x14004b871  jnb     short loc_14004B876
0x14004b873  xor     dil, dil
0x14004b876  lea     rax, WPP_RECORDER_INITIALIZED
0x14004b87d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004b884  setnz   r8b
0x14004b888  test    dil, dil
0x14004b88b  jnz     short loc_14004B896
0x14004b88d  test    r8b, r8b
0x14004b890  jz      loc_14004B92F
0x14004b896  mov     r9, [rcx+40h]
0x14004b89a  lea     rdx, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b8a1  mov     rcx, [rcx+18h]
0x14004b8a5  mov     [rsp+0B8h+var_78], rbx
0x14004b8aa  mov     [rsp+0B8h+var_80], rdx
0x14004b8af  mov     dl, dil
0x14004b8b2  mov     [rsp+0B8h+var_88], 0C0h
0x14004b8b9  mov     [rsp+0B8h+var_90], r12d
0x14004b8be  mov     byte ptr [rsp+0B8h+var_98], 2
0x14004b8c3  call    WPP_RECORDER_AND_TRACE_SF_q
0x14004b8c8  jmp     short loc_14004B92F
0x14004b8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b8d1  cmp     rcx, r15
0x14004b8d4  jz      short loc_14004B8E3
0x14004b8d6  mov     eax, [rcx+2Ch]
0x14004b8d9  test    al, 8
0x14004b8db  jz      short loc_14004B8E3
0x14004b8dd  cmp     byte ptr [rcx+29h], 2
0x14004b8e1  jnb     short loc_14004B8E6
0x14004b8e3  xor     dil, dil
0x14004b8e6  lea     rax, WPP_RECORDER_INITIALIZED
0x14004b8ed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004b8f4  setnz   r8b
0x14004b8f8  test    dil, dil
0x14004b8fb  jnz     short loc_14004B902
0x14004b8fd  test    r8b, r8b
0x14004b900  jz      short loc_14004B92F
0x14004b902  mov     r9, [rcx+40h]
0x14004b906  lea     rdx, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b90d  mov     rcx, [rcx+18h]
0x14004b911  mov     [rsp+0B8h+var_80], rdx
0x14004b916  mov     dl, dil
0x14004b919  mov     [rsp+0B8h+var_88], 0C1h
0x14004b920  mov     [rsp+0B8h+var_90], r12d
0x14004b925  mov     byte ptr [rsp+0B8h+var_98], 2
0x14004b92a  call    WPP_RECORDER_AND_TRACE_SF_
0x14004b92f  mov     r9b, 11h; unsigned __int8
0x14004b932  xor     r8d, r8d; unsigned __int8
0x14004b935  mov     rdx, rbx; this
0x14004b938  mov     ecx, ebp; int
0x14004b93a  call    ?Reconfigure_Rsp@Avdtp_impl@@CAJJPEAXEE@Z; Avdtp_impl::Reconfigure_Rsp(long,void *,uchar,uchar)
0x14004b93f  jmp     loc_14004BAE7
0x14004b944  mov     dl, [rsi+2]
0x14004b947  lea     r8, [rsp+0B8h+arg_8]; enum TAG_AvdtpSepState *
0x14004b94f  shr     dl, 2; unsigned __int8
0x14004b952  mov     rcx, rbx; this
0x14004b955  mov     [rsp+0B8h+arg_8], 0
0x14004b960  call    ?FindEndpointIndexByLocalSeid_AndReturnState@Avdtp_impl@@AEAAKEAEAW4TAG_AvdtpSepState@@@Z; Avdtp_impl::FindEndpointIndexByLocalSeid_AndReturnState(uchar,TAG_AvdtpSepState &)
0x14004b965  mov     [rsp+0B8h+var_58], eax
0x14004b969  cmp     eax, r12d
0x14004b96c  jnz     short loc_14004B973
0x14004b96e  mov     r9b, 12h
0x14004b971  jmp     short loc_14004B932
0x14004b973  lea     r12, [rsi+3]
0x14004b977  movzx   ecx, byte ptr [r12]
0x14004b97c  sub     ecx, edi
0x14004b97e  jz      loc_14004BA55
0x14004b984  sub     ecx, edi
0x14004b986  jz      loc_14004BA55
0x14004b98c  sub     ecx, edi
0x14004b98e  jz      loc_14004BA55
0x14004b994  sub     ecx, edi
0x14004b996  jz      short loc_14004B9B1
0x14004b998  sub     ecx, edi
0x14004b99a  jz      loc_14004BA55
0x14004b9a0  sub     ecx, edi
0x14004b9a2  jz      loc_14004BA55
0x14004b9a8  cmp     ecx, edi
0x14004b9aa  jz      short loc_14004B9B1
0x14004b9ac  mov     r9b, 17h
0x14004b9af  jmp     short loc_14004B932
0x14004b9b1  mov     eax, [rsp+0B8h+arg_8]
0x14004b9b8  add     eax, 0FFFFFFFEh
0x14004b9bb  cmp     eax, 2
0x14004b9be  jbe     short loc_14004B9C8
0x14004b9c0  mov     r9b, 31h ; '1'
0x14004b9c3  jmp     loc_14004B932
0x14004b9c8  lea     r14, [rbx+640h]
0x14004b9cf  mov     rcx, r14; SpinLock
0x14004b9d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b9d9  nop     dword ptr [rax+rax+00h]
0x14004b9de  mov     rdi, [rbx+478h]
0x14004b9e5  mov     r15b, al
0x14004b9e8  test    rdi, rdi
0x14004b9eb  jz      short loc_14004B9FC
0x14004b9ed  mov     rax, [rbx+490h]
0x14004b9f4  mov     rcx, rdi
0x14004b9f7  call    _guard_dispatch_icall
0x14004b9fc  mov     dl, r15b; NewIrql
0x14004b9ff  mov     rcx, r14; SpinLock
0x14004ba02  call    cs:__imp_KeReleaseSpinLock
0x14004ba09  nop     dword ptr [rax+rax+00h]
0x14004ba0e  test    rdi, rdi
0x14004ba11  jz      loc_14004BAE7
0x14004ba17  mov     eax, [rsp+0B8h+var_58]
0x14004ba1b  lea     edx, [r13-3]
0x14004ba1f  mov     r9b, [rsi+2]
0x14004ba23  mov     ecx, ebp
0x14004ba25  imul    r8, rax, 0C8h
0x14004ba2c  mov     rax, [rbx+518h]
0x14004ba33  mov     [rsp+0B8h+var_90], edx
0x14004ba37  mov     rdx, rbx
0x14004ba3a  shr     r9b, 2
0x14004ba3e  mov     [rsp+0B8h+var_98], r12
0x14004ba43  mov     r8, [r8+rbx+0D8h]
0x14004ba4b  call    _guard_dispatch_icall
0x14004ba50  jmp     loc_14004BAD8
0x14004ba55  mov     r9b, 1Ah
0x14004ba58  jmp     loc_14004B932
0x14004ba5d  mov     al, [rsi]
0x14004ba5f  and     al, 3
0x14004ba61  cmp     al, 2
0x14004ba63  jnz     short loc_14004BA6D
0x14004ba65  xor     bpl, bpl
0x14004ba68  xor     sil, sil
0x14004ba6b  jmp     short loc_14004BA75
0x14004ba6d  mov     bpl, [rsi+3]
0x14004ba71  mov     sil, [rsi+2]
0x14004ba75  lea     r14, [rbx+640h]
0x14004ba7c  mov     rcx, r14; SpinLock
0x14004ba7f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004ba86  nop     dword ptr [rax+rax+00h]
0x14004ba8b  mov     rdi, [rbx+478h]
0x14004ba92  mov     r15b, al
0x14004ba95  test    rdi, rdi
0x14004ba98  jz      short loc_14004BAA9
0x14004ba9a  mov     rax, [rbx+490h]
0x14004baa1  mov     rcx, rdi
0x14004baa4  call    _guard_dispatch_icall
0x14004baa9  mov     dl, r15b; NewIrql
0x14004baac  mov     rcx, r14; SpinLock
0x14004baaf  call    cs:__imp_KeReleaseSpinLock
0x14004bab6  nop     dword ptr [rax+rax+00h]
0x14004babb  test    rdi, rdi
0x14004babe  jz      short loc_14004BAE7
0x14004bac0  mov     rax, [rbx+520h]
0x14004bac7  mov     r9b, sil
0x14004baca  mov     r8b, bpl
0x14004bacd  mov     rdx, rdi
0x14004bad0  mov     rcx, rbx
0x14004bad3  call    _guard_dispatch_icall
0x14004bad8  mov     rax, [rbx+498h]
0x14004badf  mov     rcx, rdi
0x14004bae2  call    _guard_dispatch_icall
0x14004bae7  add     rsp, 78h
0x14004baeb  pop     r15
0x14004baed  pop     r14
0x14004baef  pop     r13
0x14004baf1  pop     r12
0x14004baf3  pop     rdi
0x14004baf4  pop     rsi
0x14004baf5  pop     rbp
0x14004baf6  pop     rbx
0x14004baf7  retn
```
