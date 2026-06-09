# QueueCancel

- ea: `0x14000785c`
- end: `0x140007cba`
- name: `QueueCancel`
- size: `1118`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400062d0`
- `0x140007f80`
- `0x14000a230`
- `0x14000c2e0`
- `0x14000c368`

## callees

- `0x140002964`
- `0x140002a24`
- `0x14000785c`
- `0x140009504`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400078bb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400078bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000788f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000788f`
- `ntoskrnl!IoCancelIrp` at `0x140007a29`
- `ntoskrnl!IoCancelIrp` at `0x140007ad4`
- `ntoskrnl!IoCancelIrp` at `0x140007b82`
- `ntoskrnl!IoCancelIrp` at `0x140007c30`
- `ntoskrnl!IoCancelIrp` at `0x140007a29`
- `ntoskrnl!IoCancelIrp` at `0x140007ad4`
- `ntoskrnl!IoCancelIrp` at `0x140007b82`
- `ntoskrnl!IoCancelIrp` at `0x140007c30`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400078f8`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000799e`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007a03`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007a55`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007aae`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007b00`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007b5c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007bae`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007c0a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007c5c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400078f8`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000799e`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007a03`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007a55`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007aae`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007b00`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007b5c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007bae`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007c0a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007c5c`

## pseudocode

```c
__int64 __fastcall QueueCancel(__int64 a1)
{
  char v2; // bl
  __int64 Default; // rax
  int v4; // ebp
  __int64 v5; // r13
  __int64 v6; // r12
  __int64 v7; // rbp
  char v8; // di
  char v9; // si
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  IRP *v14; // rbx
  int v15; // edi
  __int64 v16; // rax
  int v17; // eax
  int v18; // edx
  IRP *v19; // rbx
  int v20; // edi
  __int64 v21; // rax
  int v22; // eax
  int v23; // edx
  IRP *v24; // rbx
  int v25; // edi
  __int64 v26; // rax
  int v27; // eax
  int v28; // edx
  IRP *v29; // rbx
  int v30; // edi
  __int64 v31; // rax
  int v32; // eax
  int v33; // edx
  int v35; // [rsp+20h] [rbp-98h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-68h] BYREF
  int i; // [rsp+C8h] [rbp+10h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 1240), &LockHandle);
  if ( *(_DWORD *)(a1 + 1248) == 1 )
  {
    v2 = 1;
  }
  else
  {
    v2 = 0;
    *(_DWORD *)(a1 + 1248) = 1;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v2 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_(Default, 2u, 3u, 0x35u, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
    }
  }
  else
  {
    v4 = 0;
    for ( i = 0; (unsigned __int16)v4 < *(_WORD *)(a1 + 1280); i = v4 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 1224) + 4LL * (unsigned __int16)v4) == 2 )
      {
        v5 = *(_QWORD *)(a1 + 1176);
        v6 = 224LL * (unsigned __int16)v4;
        if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v7 = *(_QWORD *)(v6 + v5 + 32);
          v8 = *(_BYTE *)(v7 + 72);
          v9 = *(_BYTE *)(v7 + 2);
          v10 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          WPP_RECORDER_SF_PDDd(v10, v11, v12, v13, v35, v7, v9, v8, i);
          v4 = i;
        }
        v14 = *(IRP **)(v6 + v5 + 112);
        v15 = *(_DWORD *)(v6 + v5 + 8);
        if ( v14 && v15 == 2 )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v16 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_(v16, 4u, 5u, 0x37u, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
          }
          IoCancelIrp(v14);
        }
        else if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v17 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v18) = 4;
          WPP_RECORDER_SF_d(v17, v18, 5, 56, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v15);
        }
        v19 = *(IRP **)(v6 + v5 + 120);
        v20 = *(_DWORD *)(v6 + v5 + 12);
        if ( v19 && v20 == 2 )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v21 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_(v21, 4u, 5u, 0x39u, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
          }
          IoCancelIrp(v19);
        }
        else if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v22 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v23) = 4;
          WPP_RECORDER_SF_d(v22, v23, 5, 58, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v20);
        }
        v24 = *(IRP **)(v6 + v5 + 128);
        v25 = *(_DWORD *)(v6 + v5 + 16);
        if ( v24 && v25 == 2 )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v26 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_(v26, 4u, 5u, 0x3Bu, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
          }
          IoCancelIrp(v24);
        }
        else if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v27 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v28) = 4;
          WPP_RECORDER_SF_d(v27, v28, 5, 60, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v25);
        }
        v29 = *(IRP **)(v6 + v5 + 136);
        v30 = *(_DWORD *)(v6 + v5 + 20);
        if ( v29 && v30 == 2 )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v31 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_(v31, 4u, 5u, 0x3Du, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
          }
          IoCancelIrp(v29);
        }
        else if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v32 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
          LOBYTE(v33) = 4;
          WPP_RECORDER_SF_d(v32, v33, 5, 62, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v30);
        }
      }
      LOWORD(v4) = v4 + 1;
    }
    *(_DWORD *)(a1 + 1248) = 3;
  }
  return 0;
}

```

## disassembly

```asm
0x14000785c  mov     [rsp+arg_8], rdx
0x140007861  push    rbx
0x140007862  push    rbp
0x140007863  push    rsi
0x140007864  push    rdi
0x140007865  push    r12
0x140007867  push    r13
0x140007869  push    r14
0x14000786b  push    r15
0x14000786d  sub     rsp, 78h
0x140007871  mov     r15, rcx
0x140007874  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x140007879  xorps   xmm0, xmm0
0x14000787c  xor     eax, eax
0x14000787e  add     rcx, 4D8h; SpinLock
0x140007885  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x14000788a  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14000788f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007896  nop     dword ptr [rax+rax+00h]
0x14000789b  mov     eax, 1
0x1400078a0  cmp     [r15+4E0h], eax
0x1400078a7  jnz     short loc_1400078AD
0x1400078a9  mov     bl, al
0x1400078ab  jmp     short loc_1400078B6
0x1400078ad  xor     bl, bl
0x1400078af  mov     [r15+4E0h], eax
0x1400078b6  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x1400078bb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400078c2  nop     dword ptr [rax+rax+00h]
0x1400078c7  test    bl, bl
0x1400078c9  jz      short loc_140007927
0x1400078cb  cmp     cs:gTracingEnabled, 0
0x1400078d2  jz      loc_140007CA6
0x1400078d8  lea     r14, WPP_RECORDER_INITIALIZED
0x1400078df  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400078e6  jz      loc_140007CA6
0x1400078ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078f3  mov     ebx, 35h ; '5'
0x1400078f8  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400078ff  nop     dword ptr [rax+rax+00h]
0x140007904  movzx   r9d, bx
0x140007908  lea     r8d, [rbx-32h]
0x14000790c  mov     rcx, rax
0x14000790f  mov     dl, 2
0x140007911  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140007918  mov     [rsp+0B8h+var_98], rax
0x14000791d  call    WPP_RECORDER_SF_
0x140007922  jmp     loc_140007CA6
0x140007927  xor     ebp, ebp
0x140007929  xor     eax, eax
0x14000792b  mov     dword ptr [rsp+0B8h+arg_8], ebp
0x140007932  cmp     ax, [r15+500h]
0x14000793a  jnb     loc_140007C9B
0x140007940  lea     r14, WPP_RECORDER_INITIALIZED
0x140007947  lea     rsi, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x14000794e  mov     rax, [r15+4C8h]
0x140007955  movzx   ecx, bp
0x140007958  cmp     dword ptr [rax+rcx*4], 2
0x14000795c  jnz     loc_140007C83
0x140007962  mov     r13, [r15+498h]
0x140007969  imul    r12, rcx, 0E0h
0x140007970  cmp     cs:gTracingEnabled, 0
0x140007977  jz      short loc_1400079D1
0x140007979  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007980  jz      short loc_1400079D1
0x140007982  mov     rbp, [r12+r13+20h]
0x140007987  mov     rcx, cs:WPP_GLOBAL_Control
0x14000798e  movzx   ebx, word ptr [rsp+0B8h+arg_8]
0x140007996  movzx   edi, byte ptr [rbp+48h]
0x14000799a  movzx   esi, byte ptr [rbp+2]
0x14000799e  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400079a5  nop     dword ptr [rax+rax+00h]
0x1400079aa  mov     [rsp+0B8h+var_78], ebx
0x1400079ae  mov     rcx, rax
0x1400079b1  mov     [rsp+0B8h+var_80], edi
0x1400079b5  mov     [rsp+0B8h+var_88], esi
0x1400079b9  mov     [rsp+0B8h+var_90], rbp
0x1400079be  call    WPP_RECORDER_SF_PDDd
0x1400079c3  mov     ebp, dword ptr [rsp+0B8h+arg_8]
0x1400079ca  lea     rsi, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x1400079d1  mov     rbx, [r12+r13+70h]
0x1400079d6  mov     edi, [r12+r13+8]
0x1400079db  test    rbx, rbx
0x1400079de  jz      short loc_140007A37
0x1400079e0  cmp     edi, 2
0x1400079e3  jnz     short loc_140007A37
0x1400079e5  cmp     cs:gTracingEnabled, 0
0x1400079ec  jz      short loc_140007A26
0x1400079ee  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400079f5  jz      short loc_140007A26
0x1400079f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079fe  mov     edi, 37h ; '7'
0x140007a03  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007a0a  nop     dword ptr [rax+rax+00h]
0x140007a0f  movzx   r9d, di
0x140007a13  mov     [rsp+0B8h+var_98], rsi
0x140007a18  mov     rcx, rax
0x140007a1b  lea     r8d, [rdi-32h]
0x140007a1f  mov     dl, 4
0x140007a21  call    WPP_RECORDER_SF_
0x140007a26  mov     rcx, rbx; Irp
0x140007a29  call    cs:__imp_IoCancelIrp
0x140007a30  nop     dword ptr [rax+rax+00h]
0x140007a35  jmp     short loc_140007A7C
0x140007a37  cmp     cs:gTracingEnabled, 0
0x140007a3e  jz      short loc_140007A7C
0x140007a40  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007a47  jz      short loc_140007A7C
0x140007a49  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a50  mov     ebx, 38h ; '8'
0x140007a55  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007a5c  nop     dword ptr [rax+rax+00h]
0x140007a61  mov     dword ptr [rsp+0B8h+var_90], edi
0x140007a65  lea     r8d, [rbx-33h]
0x140007a69  mov     rcx, rax
0x140007a6c  mov     [rsp+0B8h+var_98], rsi
0x140007a71  movzx   r9d, bx
0x140007a75  mov     dl, 4
0x140007a77  call    WPP_RECORDER_SF_d
0x140007a7c  mov     rbx, [r12+r13+78h]
0x140007a81  mov     edi, [r12+r13+0Ch]
0x140007a86  test    rbx, rbx
0x140007a89  jz      short loc_140007AE2
0x140007a8b  cmp     edi, 2
0x140007a8e  jnz     short loc_140007AE2
0x140007a90  cmp     cs:gTracingEnabled, 0
0x140007a97  jz      short loc_140007AD1
0x140007a99  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007aa0  jz      short loc_140007AD1
0x140007aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140007aa9  mov     edi, 39h ; '9'
0x140007aae  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007ab5  nop     dword ptr [rax+rax+00h]
0x140007aba  movzx   r9d, di
0x140007abe  mov     [rsp+0B8h+var_98], rsi
0x140007ac3  mov     rcx, rax
0x140007ac6  lea     r8d, [rdi-34h]
0x140007aca  mov     dl, 4
0x140007acc  call    WPP_RECORDER_SF_
0x140007ad1  mov     rcx, rbx; Irp
0x140007ad4  call    cs:__imp_IoCancelIrp
0x140007adb  nop     dword ptr [rax+rax+00h]
0x140007ae0  jmp     short loc_140007B27
0x140007ae2  cmp     cs:gTracingEnabled, 0
0x140007ae9  jz      short loc_140007B27
0x140007aeb  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007af2  jz      short loc_140007B27
0x140007af4  mov     rcx, cs:WPP_GLOBAL_Control
0x140007afb  mov     ebx, 3Ah ; ':'
0x140007b00  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007b07  nop     dword ptr [rax+rax+00h]
0x140007b0c  mov     dword ptr [rsp+0B8h+var_90], edi
0x140007b10  lea     r8d, [rbx-35h]
0x140007b14  mov     rcx, rax
0x140007b17  mov     [rsp+0B8h+var_98], rsi
0x140007b1c  movzx   r9d, bx
0x140007b20  mov     dl, 4
0x140007b22  call    WPP_RECORDER_SF_d
0x140007b27  mov     rbx, [r12+r13+80h]
0x140007b2f  mov     edi, [r12+r13+10h]
0x140007b34  test    rbx, rbx
0x140007b37  jz      short loc_140007B90
0x140007b39  cmp     edi, 2
0x140007b3c  jnz     short loc_140007B90
0x140007b3e  cmp     cs:gTracingEnabled, 0
0x140007b45  jz      short loc_140007B7F
0x140007b47  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007b4e  jz      short loc_140007B7F
0x140007b50  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b57  mov     edi, 3Bh ; ';'
0x140007b5c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007b63  nop     dword ptr [rax+rax+00h]
0x140007b68  movzx   r9d, di
0x140007b6c  mov     [rsp+0B8h+var_98], rsi
0x140007b71  mov     rcx, rax
0x140007b74  lea     r8d, [rdi-36h]
0x140007b78  mov     dl, 4
0x140007b7a  call    WPP_RECORDER_SF_
0x140007b7f  mov     rcx, rbx; Irp
0x140007b82  call    cs:__imp_IoCancelIrp
0x140007b89  nop     dword ptr [rax+rax+00h]
0x140007b8e  jmp     short loc_140007BD5
0x140007b90  cmp     cs:gTracingEnabled, 0
0x140007b97  jz      short loc_140007BD5
0x140007b99  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007ba0  jz      short loc_140007BD5
0x140007ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ba9  mov     ebx, 3Ch ; '<'
0x140007bae  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007bb5  nop     dword ptr [rax+rax+00h]
0x140007bba  mov     dword ptr [rsp+0B8h+var_90], edi
0x140007bbe  lea     r8d, [rbx-37h]
0x140007bc2  mov     rcx, rax
0x140007bc5  mov     [rsp+0B8h+var_98], rsi
0x140007bca  movzx   r9d, bx
0x140007bce  mov     dl, 4
0x140007bd0  call    WPP_RECORDER_SF_d
0x140007bd5  mov     rbx, [r12+r13+88h]
0x140007bdd  mov     edi, [r12+r13+14h]
0x140007be2  test    rbx, rbx
0x140007be5  jz      short loc_140007C3E
0x140007be7  cmp     edi, 2
0x140007bea  jnz     short loc_140007C3E
0x140007bec  cmp     cs:gTracingEnabled, 0
0x140007bf3  jz      short loc_140007C2D
0x140007bf5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007bfc  jz      short loc_140007C2D
0x140007bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c05  mov     edi, 3Dh ; '='
0x140007c0a  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007c11  nop     dword ptr [rax+rax+00h]
0x140007c16  movzx   r9d, di
0x140007c1a  mov     [rsp+0B8h+var_98], rsi
0x140007c1f  mov     rcx, rax
0x140007c22  lea     r8d, [rdi-38h]
0x140007c26  mov     dl, 4
0x140007c28  call    WPP_RECORDER_SF_
0x140007c2d  mov     rcx, rbx; Irp
0x140007c30  call    cs:__imp_IoCancelIrp
0x140007c37  nop     dword ptr [rax+rax+00h]
0x140007c3c  jmp     short loc_140007C83
0x140007c3e  cmp     cs:gTracingEnabled, 0
0x140007c45  jz      short loc_140007C83
0x140007c47  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140007c4e  jz      short loc_140007C83
0x140007c50  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c57  mov     ebx, 3Eh ; '>'
0x140007c5c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007c63  nop     dword ptr [rax+rax+00h]
0x140007c68  mov     dword ptr [rsp+0B8h+var_90], edi
0x140007c6c  lea     r8d, [rbx-39h]
0x140007c70  mov     rcx, rax
0x140007c73  mov     [rsp+0B8h+var_98], rsi
0x140007c78  movzx   r9d, bx
0x140007c7c  mov     dl, 4
0x140007c7e  call    WPP_RECORDER_SF_d
0x140007c83  inc     bp
0x140007c86  mov     dword ptr [rsp+0B8h+arg_8], ebp
0x140007c8d  cmp     bp, [r15+500h]
0x140007c95  jb      loc_14000794E
0x140007c9b  mov     dword ptr [r15+4E0h], 3
0x140007ca6  xor     eax, eax
0x140007ca8  add     rsp, 78h
0x140007cac  pop     r15
0x140007cae  pop     r14
0x140007cb0  pop     r13
0x140007cb2  pop     r12
0x140007cb4  pop     rdi
0x140007cb5  pop     rsi
0x140007cb6  pop     rbp
0x140007cb7  pop     rbx
0x140007cb8  retn
```
