# EvtWdfRequestCompletionRoutine

- ea: `0x1400188c0`
- end: `0x140018c0c`
- name: `EvtWdfRequestCompletionRoutine`
- size: `844`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x1400156d0`
- `0x1400188c0`
- `0x140018c14`
- `0x14001eed0`
- `0x14002a924`
- `0x1400cf130`
- `0x1400dfd40`

## import_xrefs

- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140018a59`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140018a59`

## string_xrefs

- `0x1400189bd`: `onecoreuap\net\wlan\sys\wificx\extension\src\wxdevice.cpp`

## pseudocode

```c
void __fastcall EvtWdfRequestCompletionRoutine(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int v8; // ecx
  int v9; // edi
  _QWORD *v10; // r14
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rsi
  unsigned int v14; // ebp
  Event *v15; // rbx
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  int v19; // r13d
  int v20; // r15d
  __int64 v21; // r12
  Event *v22; // rax
  char v23; // r14
  EventQueue *v24; // rcx
  const char *v25; // [rsp+20h] [rbp-78h]
  __int64 v26; // [rsp+28h] [rbp-70h]
  WxDevice *v27; // [rsp+40h] [rbp-58h]
  int v28; // [rsp+B0h] [rbp+18h]

  v3 = a2;
  v5 = (unsigned int *)(a3 + 8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      104,
      (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
      a1,
      *v5);
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 1392))(WdfDriverGlobals, v3);
  v27 = (WxDevice *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                      WdfDriverGlobals,
                      v6,
                      off_14010E308);
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14010E330);
  v8 = *v5;
  v9 = -1073741436;
  v10 = (_QWORD *)v7;
  if ( *v5 != -1073741536 && v8 != -1073741436 )
  {
    if ( v8 && v8 != -1073741823 )
      __int2c();
    goto LABEL_34;
  }
  v25 = "onecoreuap\\net\\wlan\\sys\\wificx\\extension\\src\\wxdevice.cpp";
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01031 + 1640))(
    WdfDriverGlobals,
    a1,
    1380350039,
    1558);
  *((_BYTE *)v10 + 16) = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      v12,
      105,
      (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
      a1,
      *v5);
  }
  v13 = *v10;
  v14 = *v5;
  v15 = (Event *)(*v10 + 208LL);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 32LL))(*v10);
  v19 = *(_DWORD *)(v13 + 16);
  v28 = *(_DWORD *)(v13 + 60);
  if ( v14 == -1073741536 )
    v20 = -1073676276;
  else
    v20 = NdisConvertNtStatusToNdisStatus(v14);
  v21 = v10[1];
  if ( v15 )
  {
    v23 = 0;
  }
  else
  {
    v22 = (Event *)operator new(0x48u);
    if ( !v22 || (v15 = Event::Event(v22, 0, 0)) == 0 )
    {
      v9 = -1073741670;
LABEL_30:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v26) = v9;
        LOBYTE(v16) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          1,
          100,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
          v26);
      }
      goto LABEL_34;
    }
    v23 = 1;
  }
  v24 = (WxDevice *)((char *)v27 + 792);
  if ( v27 == (WxDevice *)-792LL )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v17,
        10,
        (__int64)WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids,
        (char)v15,
        *(_DWORD *)v15);
    }
    v9 = -1073741811;
  }
  else if ( *((_BYTE *)v15 + 45) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v17,
        11,
        (__int64)WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids,
        (char)v15,
        *(_DWORD *)v15);
    }
  }
  else
  {
    *((_DWORD *)v15 + 4) = 1;
    *((_QWORD *)v15 + 1) = v24;
    *((_QWORD *)v15 + 4) = v21;
    *((_QWORD *)v15 + 3) = v13;
    *((_DWORD *)v15 + 10) = v20;
    v9 = EventQueue::QueueEvent(v24, v15, 0);
  }
  if ( v9 )
  {
    if ( v23 )
      operator delete(v15);
    goto LABEL_30;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DLd(WPP_GLOBAL_Control->DeviceExtension, v16, v17, v18, (_DWORD)v25, v19, v28, v14);
LABEL_34:
  WxDevice::DumpPowerQueueStatusToTraceLog(v27);
}

```

## disassembly

```asm
0x1400188c0  push    rbx
0x1400188c2  push    rbp
0x1400188c3  push    rsi
0x1400188c4  push    rdi
0x1400188c5  push    r12
0x1400188c7  push    r13
0x1400188c9  push    r14
0x1400188cb  push    r15
0x1400188cd  sub     rsp, 58h
0x1400188d1  mov     rdi, rdx
0x1400188d4  mov     rsi, rcx
0x1400188d7  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400188de  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400188e5  lea     rbx, [r8+8]
0x1400188e9  lea     r15, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400188f0  jz      short loc_14001891A
0x1400188f2  mov     eax, [rbx]
0x1400188f4  mov     r9d, 68h ; 'h'
0x1400188fa  mov     [rsp+98h+var_68], eax
0x1400188fe  mov     dl, 4
0x140018900  mov     [rsp+98h+var_70], rcx
0x140018905  mov     rcx, cs:WPP_GLOBAL_Control
0x14001890c  mov     [rsp+98h+var_78], r15
0x140018911  mov     rcx, [rcx+40h]
0x140018915  call    WPP_RECORDER_SF_qD
0x14001891a  mov     rax, cs:WdfFunctions_01031
0x140018921  mov     rdx, rdi
0x140018924  mov     rcx, cs:WdfDriverGlobals
0x14001892b  mov     rax, [rax+570h]
0x140018932  call    _guard_dispatch_icall
0x140018937  mov     rcx, cs:WdfFunctions_01031
0x14001893e  mov     rdx, rax
0x140018941  mov     r8, cs:off_14010E308
0x140018948  mov     rax, [rcx+650h]
0x14001894f  mov     rcx, cs:WdfDriverGlobals
0x140018956  call    _guard_dispatch_icall
0x14001895b  mov     rcx, cs:WdfFunctions_01031
0x140018962  mov     rdx, rsi
0x140018965  mov     r8, cs:off_14010E330
0x14001896c  mov     [rsp+98h+var_58], rax
0x140018971  mov     rax, [rcx+650h]
0x140018978  mov     rcx, cs:WdfDriverGlobals
0x14001897f  call    _guard_dispatch_icall
0x140018984  mov     ecx, [rbx]
0x140018986  mov     edi, 0C0000184h
0x14001898b  mov     r14, rax
0x14001898e  lea     r12d, [rdi-64h]
0x140018992  cmp     ecx, r12d
0x140018995  jz      short loc_1400189B6
0x140018997  cmp     ecx, edi
0x140018999  jz      short loc_1400189B6
0x14001899b  test    ecx, ecx
0x14001899d  jz      loc_140018BF0
0x1400189a3  cmp     ecx, 0C0000001h
0x1400189a9  jz      loc_140018BF0
0x1400189af  int     2Ch; Windows NT - assertion failure
0x1400189b1  jmp     loc_140018BF0
0x1400189b6  mov     rax, cs:WdfFunctions_01031
0x1400189bd  lea     rcx, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\sys\\wificx\\ext"...
0x1400189c4  mov     [rsp+98h+var_78], rcx
0x1400189c9  mov     r9d, 616h
0x1400189cf  mov     rcx, cs:WdfDriverGlobals
0x1400189d6  mov     r8d, 52467857h
0x1400189dc  mov     rdx, rsi
0x1400189df  mov     rax, [rax+668h]
0x1400189e6  call    _guard_dispatch_icall
0x1400189eb  mov     byte ptr [r14+10h], 1
0x1400189f0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400189f7  jz      short loc_140018A21
0x1400189f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140018a00  mov     r9d, 69h ; 'i'
0x140018a06  mov     eax, [rbx]
0x140018a08  mov     dl, 4
0x140018a0a  mov     [rsp+98h+var_68], eax
0x140018a0e  mov     [rsp+98h+var_70], rsi
0x140018a13  mov     rcx, [rcx+40h]
0x140018a17  mov     [rsp+98h+var_78], r15
0x140018a1c  call    WPP_RECORDER_SF_qD
0x140018a21  mov     rsi, [r14]
0x140018a24  mov     ebp, [rbx]
0x140018a26  lea     rbx, [rsi+0D0h]
0x140018a2d  mov     rax, [rsi]
0x140018a30  mov     rcx, rsi
0x140018a33  mov     rax, [rax+20h]
0x140018a37  call    _guard_dispatch_icall
0x140018a3c  mov     eax, [rsi+3Ch]
0x140018a3f  mov     r13d, [rsi+10h]
0x140018a43  mov     [rsp+98h+arg_10], eax
0x140018a4a  cmp     ebp, r12d
0x140018a4d  jnz     short loc_140018A57
0x140018a4f  mov     r15d, 0C001000Ch
0x140018a55  jmp     short loc_140018A68
0x140018a57  mov     ecx, ebp
0x140018a59  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x140018a60  nop     dword ptr [rax+rax+00h]
0x140018a65  mov     r15d, eax
0x140018a68  mov     r12, [r14+8]
0x140018a6c  test    rbx, rbx
0x140018a6f  jnz     short loc_140018AA9
0x140018a71  lea     ecx, [rbx+48h]; unsigned __int64
0x140018a74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018a79  test    rax, rax
0x140018a7c  jz      short loc_140018A98
0x140018a7e  xor     r8d, r8d; unsigned int
0x140018a81  xor     edx, edx; bool
0x140018a83  mov     rcx, rax; this
0x140018a86  call    ??0Event@@QEAA@_NK@Z; Event::Event(bool,ulong)
0x140018a8b  mov     rbx, rax
0x140018a8e  test    rax, rax
0x140018a91  jz      short loc_140018A98
0x140018a93  mov     r14b, 1
0x140018a96  jmp     short loc_140018AAC
0x140018a98  mov     edi, 0C000009Ah
0x140018a9d  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018aa4  jmp     loc_140018B8C
0x140018aa9  xor     r14b, r14b
0x140018aac  mov     rcx, [rsp+98h+var_58]
0x140018ab1  add     rcx, 318h; this
0x140018ab8  jz      short loc_140018B32
0x140018aba  cmp     byte ptr [rbx+2Dh], 0
0x140018abe  jz      short loc_140018B05
0x140018ac0  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018ac7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018ace  jz      loc_140018B76
0x140018ad4  mov     eax, [rbx]
0x140018ad6  mov     r9d, 0Bh
0x140018adc  mov     rcx, cs:WPP_GLOBAL_Control
0x140018ae3  mov     dl, 2
0x140018ae5  mov     [rsp+98h+var_68], eax
0x140018ae9  lea     rax, WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids
0x140018af0  mov     [rsp+98h+var_70], rbx
0x140018af5  mov     [rsp+98h+var_78], rax
0x140018afa  mov     rcx, [rcx+40h]
0x140018afe  call    WPP_RECORDER_SF_qD
0x140018b03  jmp     short loc_140018B76
0x140018b05  xor     r8d, r8d; bool
0x140018b08  mov     dword ptr [rbx+10h], 1
0x140018b0f  mov     rdx, rbx; struct Event *
0x140018b12  mov     [rbx+8], rcx
0x140018b16  mov     [rbx+20h], r12
0x140018b1a  mov     [rbx+18h], rsi
0x140018b1e  mov     [rbx+28h], r15d
0x140018b22  call    ?QueueEvent@EventQueue@@QEAAHPEAVEvent@@_N@Z; EventQueue::QueueEvent(Event *,bool)
0x140018b27  mov     edi, eax
0x140018b29  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018b30  jmp     short loc_140018B76
0x140018b32  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018b39  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018b40  jz      short loc_140018B71
0x140018b42  mov     eax, [rbx]
0x140018b44  mov     r9d, 0Ah
0x140018b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b51  mov     dl, 2
0x140018b53  mov     [rsp+98h+var_68], eax
0x140018b57  lea     rax, WPP_36ec87e851083ecb6deb1777feb2ecc6_Traceguids
0x140018b5e  mov     [rsp+98h+var_70], rbx
0x140018b63  mov     [rsp+98h+var_78], rax
0x140018b68  mov     rcx, [rcx+40h]
0x140018b6c  call    WPP_RECORDER_SF_qD
0x140018b71  mov     edi, 0C000000Dh
0x140018b76  test    edi, edi
0x140018b78  jz      short loc_140018BC3
0x140018b7a  test    rbx, rbx
0x140018b7d  jz      short loc_140018B8C
0x140018b7f  test    r14b, r14b
0x140018b82  jz      short loc_140018B8C
0x140018b84  mov     rcx, rbx; void *
0x140018b87  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140018b8c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018b93  jz      short loc_140018BF0
0x140018b95  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b9c  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x140018ba3  mov     r9d, 64h ; 'd'
0x140018ba9  mov     dword ptr [rsp+98h+var_70], edi
0x140018bad  mov     dl, 2
0x140018baf  mov     [rsp+98h+var_78], rax
0x140018bb4  mov     rcx, [rcx+40h]
0x140018bb8  lea     r8d, [r9-63h]
0x140018bbc  call    WPP_RECORDER_SF_d
0x140018bc1  jmp     short loc_140018BF0
0x140018bc3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018bca  jz      short loc_140018BF0
0x140018bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140018bd3  mov     eax, [rsp+98h+arg_10]
0x140018bda  mov     [rsp+98h+var_60], ebp
0x140018bde  mov     [rsp+98h+var_68], eax
0x140018be2  mov     rcx, [rcx+40h]
0x140018be6  mov     dword ptr [rsp+98h+var_70], r13d
0x140018beb  call    WPP_RECORDER_SF_DLd
0x140018bf0  mov     rcx, [rsp+98h+var_58]; this
0x140018bf5  call    ?DumpPowerQueueStatusToTraceLog@WxDevice@@QEAAXXZ; WxDevice::DumpPowerQueueStatusToTraceLog(void)
0x140018bfa  add     rsp, 58h
0x140018bfe  pop     r15
0x140018c00  pop     r14
0x140018c02  pop     r13
0x140018c04  pop     r12
0x140018c06  pop     rdi
0x140018c07  pop     rsi
0x140018c08  pop     rbp
0x140018c09  pop     rbx
0x140018c0a  retn
```
