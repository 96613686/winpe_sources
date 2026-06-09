# CPcmPin::UpdateL2capOverflowedCondition(void)

- ea: `0x1400043a0`
- end: `0x140004712`
- name: `?UpdateL2capOverflowedCondition@CPcmPin@@AEAA_KXZ`
- size: `882`
- prototype: `unsigned __int64 __fastcall(CPcmPin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140003cc0`

## callees

- `0x1400043a0`
- `0x140005060`
- `0x14001bed0`
- `0x14003b5ec`
- `0x14003b7fc`
- `0x14005c7d0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004400`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400046fa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004400`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400046fa`
- `ntoskrnl!EtwWriteTransfer` at `0x1400045a9`
- `ntoskrnl!EtwWriteTransfer` at `0x1400045a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004433`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004433`

## pseudocode

```c
ULONGLONG __fastcall CPcmPin::UpdateL2capOverflowedCondition(KSPIN_LOCK *this)
{
  KSPIN_LOCK v2; // rbx
  ULONGLONG v3; // rsi
  KIRQL v4; // al
  int v5; // edx
  KSPIN_LOCK v6; // rax
  __int128 v7; // xmm0
  __int64 v8; // rcx
  _UNKNOWN **v9; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  _UNKNOWN **v13; // r8
  __int64 v14; // [rsp+68h] [rbp-A0h] BYREF
  KIRQL v15; // [rsp+70h] [rbp-98h]
  int v16; // [rsp+71h] [rbp-97h]
  __int16 v17; // [rsp+75h] [rbp-93h]
  char Keyword_high; // [rsp+77h] [rbp-91h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-90h] BYREF
  __int64 v20; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v21; // [rsp+90h] [rbp-78h] BYREF
  __int128 v22; // [rsp+98h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A8h] [rbp-60h] BYREF
  void *v24; // [rsp+B8h] [rbp-50h]
  int v25; // [rsp+C0h] [rbp-48h]
  int v26; // [rsp+C4h] [rbp-44h]
  __int64 *v27; // [rsp+C8h] [rbp-40h]
  __int64 v28; // [rsp+D0h] [rbp-38h]
  __int128 *v29; // [rsp+D8h] [rbp-30h]
  __int64 v30; // [rsp+E0h] [rbp-28h]
  unsigned __int64 *v31; // [rsp+E8h] [rbp-20h]
  __int64 v32; // [rsp+F0h] [rbp-18h]
  __int64 *v33; // [rsp+F8h] [rbp-10h]
  __int64 v34; // [rsp+100h] [rbp-8h]

  if ( this[15] )
  {
    if ( this[9] == this[8] )
    {
      if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 4) != 0 )
        McTemplateK0_EtwWriteTransfer(this, L2capOverflowStop);
      v2 = this[15];
      v3 = KeQueryUnbiasedInterruptTime() - v2;
      this[15] = 0;
      v4 = KeAcquireSpinLockRaiseToDpc(this + 10);
      *((_BYTE *)this + 88) = 1;
      if ( this != (KSPIN_LOCK *)-80LL )
      {
        v15 = v4;
        v16 = *(_DWORD *)((char *)&EventDescriptor.Keyword + 1);
        v17 = *(_WORD *)((char *)&EventDescriptor.Keyword + 5);
        Keyword_high = HIBYTE(EventDescriptor.Keyword);
        v14 = (__int64)(this + 10);
        wil::details::kspin_lock_saved_irql::Release((const struct wil::details::kspin_lock_saved_irql *)&v14);
      }
      if ( (unsigned int)dword_14006F0F8 > 5 )
      {
        v5 = 0;
        if ( (qword_14006F108 & 0x400000000000LL) != 0 && (qword_14006F110 & 0x400000000000LL) == qword_14006F110 )
        {
          v6 = this[4];
          v7 = *((_OWORD *)this + 8);
          EventDescriptor.Keyword = 0x400000000000LL;
          v34 = 8;
          v8 = *(_QWORD *)(v6 + 720);
          v33 = &v20;
          v31 = &v21;
          v29 = &v22;
          v27 = &v14;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_14006F100;
          v20 = v8;
          v21 = v3 / 0x2710;
          v22 = v7;
          v14 = 50333696;
          v32 = 8;
          v30 = 16;
          v28 = 8;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          UserData.Size = (unsigned __int16)*off_14006F100;
          v24 = &unk_140069CA0;
          UserData.Reserved = 2;
          v25 = 94;
          v26 = 1;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
        }
      }
      LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      v9 = &WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_i(
          WPP_GLOBAL_Control->AttachedDevice,
          v5,
          (_DWORD)v9,
          WPP_GLOBAL_Control->DeviceExtension,
          3);
      }
      return v3;
    }
    return 0;
  }
  v11 = 120LL * *((int *)this + 13);
  v12 = this[9] + v11 / 1000;
  if ( (__int64)this[8] <= v12 )
    return 0;
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 4) != 0 )
    McTemplateK0_EtwWriteTransfer(v11, L2capOverflowStart);
  LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
  v13 = &WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_ii(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      (_DWORD)v13,
      WPP_GLOBAL_Control->DeviceExtension,
      3);
  }
  this[15] = KeQueryUnbiasedInterruptTime();
  return 0;
}

```

## disassembly

```asm
0x1400043a0  mov     r11, rsp
0x1400043a3  push    rbp
0x1400043a4  push    rbx
0x1400043a5  push    rdi
0x1400043a6  lea     rbp, [r11-28h]
0x1400043aa  sub     rsp, 110h
0x1400043b1  mov     rax, cs:__security_cookie
0x1400043b8  xor     rax, rsp
0x1400043bb  mov     [rbp+20h+var_20], rax
0x1400043bf  cmp     qword ptr [rcx+78h], 0
0x1400043c4  mov     rdi, rcx
0x1400043c7  jz      loc_140004648
0x1400043cd  mov     rax, [rcx+40h]
0x1400043d1  cmp     [rcx+48h], rax
0x1400043d5  jnz     loc_140004641
0x1400043db  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 4
0x1400043e2  mov     [r11+10h], rsi
0x1400043e6  mov     [r11+18h], r14
0x1400043ea  mov     [r11+20h], r15
0x1400043ee  jz      short loc_1400043FC
0x1400043f0  lea     rdx, _L2capOverflowStop
0x1400043f7  call    McTemplateK0_EtwWriteTransfer
0x1400043fc  mov     rbx, [rdi+78h]
0x140004400  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140004407  nop     dword ptr [rax+rax+00h]
0x14000440c  mov     rsi, rax
0x14000440f  lea     r14, [rdi+50h]
0x140004413  sub     rsi, rbx
0x140004416  mov     rax, 346DC5D63886594Bh
0x140004420  mul     rsi
0x140004423  xor     ebx, ebx
0x140004425  mov     rcx, r14; SpinLock
0x140004428  mov     r15, rdx
0x14000442b  mov     [rdi+78h], rbx
0x14000442f  shr     r15, 0Bh
0x140004433  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000443a  nop     dword ptr [rax+rax+00h]
0x14000443f  mov     byte ptr [rdi+58h], 1
0x140004443  test    r14, r14
0x140004446  jz      short loc_140004476
0x140004448  mov     byte ptr [rsp+120h+var_B8], al
0x14000444c  lea     rcx, [rsp+120h+var_C0]; struct wil::details::kspin_lock_saved_irql *
0x140004451  mov     eax, dword ptr [rsp+120h+EventDescriptor.Keyword+1]
0x140004455  mov     [rsp+120h+var_B8+1], eax
0x140004459  movzx   eax, word ptr [rsp+120h+EventDescriptor.Keyword+5]
0x14000445e  mov     word ptr [rsp+120h+var_B4+1], ax
0x140004463  movzx   eax, byte ptr [rsp+120h+EventDescriptor.Keyword+7]
0x140004468  mov     byte ptr [rsp+120h+var_B4+3], al
0x14000446c  mov     qword ptr [rsp+120h+var_C0], r14
0x140004471  call    ?Release@kspin_lock_saved_irql@details@wil@@SAXAEBU123@@Z; wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &)
0x140004476  mov     eax, cs:dword_14006F0F8
0x14000447c  mov     r14, [rsp+120h+arg_10]
0x140004484  cmp     eax, 5
0x140004487  jbe     loc_1400045B5
0x14000448d  mov     rcx, cs:qword_14006F110
0x140004494  mov     rdx, 400000000000h
0x14000449e  mov     rax, cs:qword_14006F108
0x1400044a5  test    rdx, rax
0x1400044a8  jz      loc_1400045B5
0x1400044ae  mov     rax, rcx
0x1400044b1  and     rax, rdx
0x1400044b4  cmp     rax, rcx
0x1400044b7  jnz     loc_1400045B5
0x1400044bd  mov     rax, [rdi+20h]
0x1400044c1  xor     r9d, r9d; RelatedActivityId
0x1400044c4  movups  xmm0, xmmword ptr [rdi+80h]
0x1400044cb  mov     [rsp+120h+EventDescriptor.Keyword], rdx
0x1400044d0  xor     r8d, r8d; ActivityId
0x1400044d3  mov     [rbp+20h+var_28], 8
0x1400044db  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1400044e0  mov     rcx, [rax+2D0h]
0x1400044e7  lea     rax, [rbp+20h+var_A0]
0x1400044eb  mov     [rbp+20h+var_30], rax
0x1400044ef  lea     rax, [rbp+20h+var_98]
0x1400044f3  mov     [rbp+20h+var_40], rax
0x1400044f7  lea     rax, [rbp+20h+var_90]
0x1400044fb  mov     [rbp+20h+var_50], rax
0x1400044ff  lea     rax, [rsp+120h+var_C0]
0x140004504  mov     [rbp+20h+var_60], rax
0x140004508  movzx   eax, cs:word_140069C96
0x14000450f  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x140004513  mov     rax, cs:off_14006F100
0x14000451a  mov     [rbp+20h+var_80.Ptr], rax
0x14000451e  mov     [rbp+20h+var_A0], rcx
0x140004522  lea     rcx, _TraceLoggingMetadata
0x140004529  mov     [rbp+20h+var_98], r15
0x14000452d  movups  [rbp+20h+var_90], xmm0
0x140004531  mov     qword ptr [rsp+120h+var_C0], 3000800h
0x14000453a  mov     [rbp+20h+var_38], 8
0x140004542  mov     [rbp+20h+var_48], 10h
0x14000454a  mov     [rbp+20h+var_58], 8
0x140004552  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x14000455a  movzx   eax, word ptr [rax]
0x14000455d  mov     [rbp+20h+var_80.Size], eax
0x140004560  lea     rax, unk_140069CA0
0x140004567  mov     [rbp+20h+var_70], rax
0x14000456b  lea     rax, _TraceLoggingMetadataEnd
0x140004572  sub     eax, ecx
0x140004574  mov     dword ptr [rbp+20h+var_80.0Ch], 2
0x14000457b  mov     [rbp+20h+var_68], 5Eh ; '^'
0x140004582  mov     [rbp+20h+var_64], 1
0x140004589  mov     [rsp+50h], eax
0x14000458d  mov     eax, [rsp+50h]
0x140004591  mov     rcx, cs:RegHandle; RegHandle
0x140004598  lea     rax, [rbp+20h+var_80]
0x14000459c  mov     [rsp+120h+UserData], rax; UserData
0x1400045a1  mov     [rsp+120h+UserDataCount], 6; UserDataCount
0x1400045a9  call    cs:__imp_EtwWriteTransfer
0x1400045b0  nop     dword ptr [rax+rax+00h]
0x1400045b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045bc  lea     rax, WPP_GLOBAL_Control
0x1400045c3  cmp     rcx, rax
0x1400045c6  jz      short loc_1400045DB
0x1400045c8  test    dword ptr [rcx+2Ch], 2000h
0x1400045cf  jz      short loc_1400045DB
0x1400045d1  cmp     byte ptr [rcx+29h], 3
0x1400045d5  jb      short loc_1400045DB
0x1400045d7  mov     dl, 1
0x1400045d9  jmp     short loc_1400045DD
0x1400045db  xor     dl, dl
0x1400045dd  lea     r8, WPP_RECORDER_INITIALIZED
0x1400045e4  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400045eb  setnz   r8b
0x1400045ef  test    dl, dl
0x1400045f1  jnz     short loc_1400045F8
0x1400045f3  test    r8b, r8b
0x1400045f6  jz      short loc_140004616
0x1400045f8  mov     r9, [rcx+40h]
0x1400045fc  mov     rcx, [rcx+18h]
0x140004600  mov     [rsp+120h+var_E0], r15
0x140004605  mov     word ptr [rsp+30h], 35h ; '5'
0x14000460c  mov     byte ptr [rsp+120h+UserDataCount], 3
0x140004611  call    WPP_RECORDER_AND_TRACE_SF_i
0x140004616  mov     r15, [rsp+120h+arg_18]
0x14000461e  mov     rax, rsi
0x140004621  mov     rsi, [rsp+120h+arg_8]
0x140004629  mov     rcx, [rbp+20h+var_20]
0x14000462d  xor     rcx, rsp; StackCookie
0x140004630  call    __security_check_cookie
0x140004635  add     rsp, 110h
0x14000463c  pop     rdi
0x14000463d  pop     rbx
0x14000463e  pop     rbp
0x14000463f  retn
0x140004641  xor     ebx, ebx
0x140004643  mov     rax, rbx
0x140004646  jmp     short loc_140004629
0x140004648  movsxd  rax, dword ptr [rcx+34h]
0x14000464c  xor     ebx, ebx
0x14000464e  imul    rcx, rax, 78h ; 'x'
0x140004652  mov     rax, 20C49BA5E353F7CFh
0x14000465c  imul    rcx
0x14000465f  sar     rdx, 7
0x140004663  mov     rax, rdx
0x140004666  shr     rax, 3Fh
0x14000466a  add     rdx, rax
0x14000466d  add     rdx, [rdi+48h]
0x140004671  cmp     [rdi+40h], rdx
0x140004675  jle     short loc_140004643
0x140004677  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 4
0x14000467e  jz      short loc_14000468C
0x140004680  lea     rdx, _L2capOverflowStart
0x140004687  call    McTemplateK0_EtwWriteTransfer
0x14000468c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004693  lea     rax, WPP_GLOBAL_Control
0x14000469a  cmp     rcx, rax
0x14000469d  jz      short loc_1400046B2
0x14000469f  test    dword ptr [rcx+2Ch], 2000h
0x1400046a6  jz      short loc_1400046B2
0x1400046a8  cmp     byte ptr [rcx+29h], 3
0x1400046ac  jb      short loc_1400046B2
0x1400046ae  mov     dl, 1
0x1400046b0  jmp     short loc_1400046B4
0x1400046b2  xor     dl, dl
0x1400046b4  lea     r8, WPP_RECORDER_INITIALIZED
0x1400046bb  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400046c2  setnz   r8b
0x1400046c6  test    dl, dl
0x1400046c8  jnz     short loc_1400046CF
0x1400046ca  test    r8b, r8b
0x1400046cd  jz      short loc_1400046FA
0x1400046cf  mov     rax, [rdi+40h]
0x1400046d3  mov     r9, [rcx+40h]
0x1400046d7  mov     rcx, [rcx+18h]
0x1400046db  mov     qword ptr [rsp+120h+var_D8], rax
0x1400046e0  mov     rax, [rdi+48h]
0x1400046e4  mov     [rsp+120h+var_E0], rax
0x1400046e9  mov     word ptr [rsp+30h], 36h ; '6'
0x1400046f0  mov     byte ptr [rsp+120h+UserDataCount], 3
0x1400046f5  call    WPP_RECORDER_AND_TRACE_SF_ii
0x1400046fa  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140004701  nop     dword ptr [rax+rax+00h]
0x140004706  mov     [rdi+78h], rax
0x14000470a  mov     rax, rbx
0x14000470d  jmp     loc_140004629
```
