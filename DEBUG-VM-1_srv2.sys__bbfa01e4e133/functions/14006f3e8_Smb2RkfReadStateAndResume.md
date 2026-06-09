# Smb2RkfReadStateAndResume

- ea: `0x14006f3e8`
- end: `0x14006fb51`
- name: `Smb2RkfReadStateAndResume`
- size: `1897`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14007a84c`

## callees

- `0x140014d60`
- `0x140022958`
- `0x140028dbc`
- `0x140028e58`
- `0x14003420c`
- `0x140034330`
- `0x1400344d0`
- `0x14006cd08`
- `0x14006ea80`
- `0x14006ed0c`
- `0x14006f3e8`
- `0x14006fb58`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14006f8f7`
- `ntoskrnl!ZwClose` at `0x14006fa8f`
- `ntoskrnl!ZwClose` at `0x14006f8f7`
- `ntoskrnl!ZwClose` at `0x14006fa8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f640`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f640`
- `ntoskrnl!ZwCreateEvent` at `0x14006f870`
- `ntoskrnl!ZwCreateEvent` at `0x14006fa0a`
- `ntoskrnl!ZwCreateEvent` at `0x14006f870`
- `ntoskrnl!ZwCreateEvent` at `0x14006fa0a`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006f8e4`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006fa7c`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006f8e4`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14006fa7c`
- `ntoskrnl!ZwFsControlFile` at `0x14006f8c6`
- `ntoskrnl!ZwFsControlFile` at `0x14006fa5e`
- `ntoskrnl!ZwFsControlFile` at `0x14006f8c6`
- `ntoskrnl!ZwFsControlFile` at `0x14006fa5e`

## pseudocode

```c
__int64 __fastcall Smb2RkfReadStateAndResume(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 FileHandle; // rax
  NTSTATUS State; // ebx
  int v8; // r8d
  PDEVICE_OBJECT v9; // rcx
  int v10; // edx
  char v11; // r14
  PVOID v12; // rsi
  unsigned int v13; // r14d
  __int64 v14; // rdx
  PDEVICE_OBJECT v15; // rcx
  int v16; // edx
  PVOID InputBuffer; // r14
  int v18; // r8d
  int v19; // eax
  void *EventHandle; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v21; // [rsp+98h] [rbp-78h] BYREF
  int v22; // [rsp+9Ch] [rbp-74h] BYREF
  unsigned int v23; // [rsp+A0h] [rbp-70h] BYREF
  int v24; // [rsp+A4h] [rbp-6Ch] BYREF
  int v25; // [rsp+A8h] [rbp-68h] BYREF
  PVOID P; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-50h] BYREF
  PVOID v29; // [rsp+C8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-10h] BYREF
  PDEVICE_OBJECT v32; // [rsp+110h] [rbp+0h]
  __int128 v33; // [rsp+118h] [rbp+8h] BYREF
  __int64 v34; // [rsp+128h] [rbp+18h]
  char v35; // [rsp+180h] [rbp+70h] BYREF
  ULONG InputBufferLength; // [rsp+188h] [rbp+78h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  EventHandle = 0;
  P = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v22 = 0;
  v28 = 0;
  v21 = 0;
  v27 = 0;
  v29 = 0;
  InputBufferLength = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v35 = 0;
  if ( !*(_QWORD *)(v2 + 80) )
  {
    FileHandle = Smb2GetFileHandle(a2);
    *(_QWORD *)(v2 + 80) = FileHandle;
    if ( !FileHandle )
      return 3221225768LL;
  }
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZiDDDDDDDDDDD(
      v32->AttachedDevice,
      *(unsigned __int8 *)(a2 + 685),
      *(unsigned __int8 *)(a2 + 684),
      a1,
      v2 + 192,
      *(_QWORD *)(a2 + 80),
      *(_DWORD *)(a2 + 672),
      *(_WORD *)(a2 + 676),
      *(_WORD *)(a2 + 678),
      *(_BYTE *)(a2 + 680),
      *(_BYTE *)(a2 + 681),
      *(_BYTE *)(a2 + 682),
      *(_BYTE *)(a2 + 683),
      *(_BYTE *)(a2 + 684),
      *(_BYTE *)(a2 + 685),
      *(_BYTE *)(a2 + 686),
      *(_BYTE *)(a2 + 687));
  }
  State = Smb2RkfReadState(
            *(_QWORD *)(a1 + 64),
            *(_QWORD *)(*(_QWORD *)(v2 + 80) + 96LL),
            (unsigned int)&v23,
            (unsigned int)&P,
            (__int64)&v22,
            (__int64)&v25,
            (__int64)&v28,
            (__int64)&v21,
            (__int64)&v27,
            (__int64)&v29,
            (__int64)&InputBufferLength,
            (__int64)&v24,
            (__int64)&v35);
  if ( State < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_14;
    }
    v10 = 20;
    goto LABEL_13;
  }
  v12 = P;
  if ( *(_DWORD *)P != 3 )
  {
    State = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        (unsigned int)&WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids,
        a1,
        v2 + 192);
    }
    goto LABEL_14;
  }
  v13 = v21;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZiDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v2 + 192,
      v8,
      a1,
      v2 + 192,
      *(_QWORD *)(a2 + 80),
      v22,
      *((_DWORD *)P + 22),
      v21,
      InputBufferLength);
  }
  v14 = v23;
  *(_BYTE *)(v2 + 380) = 1;
  if ( (unsigned __int8)Smb2RkfResumeAppInstance(a1, v14, v12) )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = 23;
LABEL_39:
      WPP_SF_qZ(v15->AttachedDevice, v16, (unsigned int)&WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, a1, v2 + 192);
    }
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = 24;
      goto LABEL_39;
    }
  }
  if ( v27 && (State = Smb2RestoreFileLockState(a2, v28, v13), State < 0) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_14;
    }
    v10 = 25;
  }
  else
  {
    InputBuffer = v29;
    if ( v29 )
    {
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      State = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
      if ( State < 0 )
        goto LABEL_14;
      State = ZwFsControlFile(
                *(HANDLE *)(*(_QWORD *)(v2 + 80) + 88LL),
                EventHandle,
                0,
                0,
                &IoStatusBlock,
                0x90308u,
                InputBuffer,
                InputBufferLength,
                0,
                0);
      if ( State == 259 )
      {
        ZwWaitForSingleObject(EventHandle, 0, 0);
        State = IoStatusBlock.Status;
      }
      ZwClose(EventHandle);
      v11 = 0;
      if ( State < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qZd(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            (unsigned int)&WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids,
            a1,
            v2 + 192,
            State);
        }
        goto LABEL_15;
      }
      *(_WORD *)(a2 + 196) = 512;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdZ(WPP_GLOBAL_Control->AttachedDevice, 512, v18, a1, 0, v2 + 192);
      }
    }
    if ( !v35 )
      goto LABEL_69;
    ObjectAttributes.Attributes = 512;
    v33 = 0;
    LODWORD(v33) = v24;
    v34 = 128;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    State = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
    if ( State < 0 )
      goto LABEL_14;
    State = ZwFsControlFile(
              *(HANDLE *)(*(_QWORD *)(v2 + 80) + 88LL),
              EventHandle,
              0,
              0,
              &IoStatusBlock,
              0x900FCu,
              &v33,
              0x18u,
              0,
              0);
    if ( State == 259 )
    {
      ZwWaitForSingleObject(EventHandle, 0, 0);
      State = IoStatusBlock.Status;
    }
    ZwClose(EventHandle);
    if ( State >= 0 )
    {
LABEL_69:
      if ( !*(_BYTE *)(v2 + 306) && !*(_BYTE *)(v2 + 302) )
      {
        v19 = Smb2RkfNotifyComplete(*(_QWORD *)(a1 + 64), *(_QWORD *)(*(_QWORD *)(v2 + 80) + 96LL));
        *(_BYTE *)(v2 + 381) = 0;
        v11 = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids, a1, v19);
        }
        goto LABEL_15;
      }
      *(_BYTE *)(v2 + 381) = 1;
      goto LABEL_14;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_14;
    }
    v10 = 28;
  }
LABEL_13:
  WPP_SF_qZd(
    v9->AttachedDevice,
    v10,
    (unsigned int)&WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids,
    a1,
    v2 + 192,
    State);
LABEL_14:
  v11 = 0;
LABEL_15:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( State < 0 && !v11 )
  {
    Smb2RkfNotifyComplete(*(_QWORD *)(a1 + 64), *(_QWORD *)(*(_QWORD *)(v2 + 80) + 96LL));
    *(_BYTE *)(v2 + 381) = 0;
  }
  return (unsigned int)State;
}

```

## disassembly

```asm
0x14006f3e8  mov     [rsp-8+arg_8], rbx
0x14006f3ed  push    rbp
0x14006f3ee  push    rsi
0x14006f3ef  push    rdi
0x14006f3f0  push    r12
0x14006f3f2  push    r13
0x14006f3f4  push    r14
0x14006f3f6  push    r15
0x14006f3f8  lea     rbp, [rsp-20h]
0x14006f3fd  sub     rsp, 130h
0x14006f404  mov     r15, [rcx+230h]
0x14006f40b  xor     r14d, r14d
0x14006f40e  xorps   xmm0, xmm0
0x14006f411  mov     [rbp+50h+EventHandle], r14
0x14006f415  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x14006f419  xor     eax, eax
0x14006f41b  mov     [rbp+50h+P], r14
0x14006f41f  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x14006f423  mov     r12, rdx
0x14006f426  mov     r13, rcx
0x14006f429  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x14006f42d  mov     [rbp+50h+var_C4], r14d
0x14006f431  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x14006f435  mov     [rbp+50h+var_A0], r14
0x14006f439  mov     [rbp+50h+var_C8], r14d
0x14006f43d  mov     [rbp+50h+var_A8], r14
0x14006f441  mov     [rbp+50h+var_98], r14
0x14006f445  mov     [rbp+50h+arg_18], r14d
0x14006f449  mov     [rbp+50h+var_C0], r14d
0x14006f44d  mov     [rbp+50h+var_B8], r14d
0x14006f451  mov     [rbp+50h+var_BC], r14d
0x14006f455  mov     [rbp+50h+arg_10], r14b
0x14006f459  cmp     [r15+50h], r14
0x14006f45d  jnz     short loc_14006F47A
0x14006f45f  mov     rcx, rdx
0x14006f462  call    Smb2GetFileHandle
0x14006f467  mov     [r15+50h], rax
0x14006f46b  test    rax, rax
0x14006f46e  jnz     short loc_14006F47A
0x14006f470  mov     eax, 0C0000128h
0x14006f475  jmp     loc_14006F66F
0x14006f47a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f481  lea     rsi, WPP_GLOBAL_Control
0x14006f488  mov     [rbp+50h+arg_0], r14b
0x14006f48c  mov     edi, 100000h
0x14006f491  mov     [rbp+50h+var_50], rcx
0x14006f495  cmp     rcx, rsi
0x14006f498  jz      loc_14006F57B
0x14006f49e  test    [rcx+2Ch], edi
0x14006f4a1  jz      loc_14006F57B
0x14006f4a7  cmp     byte ptr [rcx+29h], 2
0x14006f4ab  jb      loc_14006F57B
0x14006f4b1  movzx   eax, byte ptr [r12+2AFh]
0x14006f4ba  lea     r14, [r15+0C0h]
0x14006f4c1  movzx   ecx, byte ptr [r12+2AEh]
0x14006f4ca  movzx   r9d, byte ptr [r12+2ABh]
0x14006f4d3  movzx   edx, byte ptr [r12+2ADh]
0x14006f4dc  movzx   r8d, byte ptr [r12+2ACh]
0x14006f4e5  movzx   r10d, byte ptr [r12+2AAh]
0x14006f4ee  movzx   r11d, byte ptr [r12+2A9h]
0x14006f4f7  movzx   ebx, byte ptr [r12+2A8h]
0x14006f500  movzx   edi, word ptr [r12+2A6h]
0x14006f509  movzx   esi, word ptr [r12+2A4h]
0x14006f512  mov     [rsp+160h+var_E0], eax
0x14006f519  mov     eax, [r12+2A0h]
0x14006f521  mov     [rsp+160h+var_E8], ecx
0x14006f525  mov     rcx, [rbp+50h+var_50]
0x14006f529  mov     [rsp+160h+var_F0], edx
0x14006f52d  mov     [rsp+160h+var_F8], r8d
0x14006f532  mov     dword ptr [rsp+160h+var_100], r9d
0x14006f537  mov     r9, r13
0x14006f53a  mov     rcx, [rcx+18h]
0x14006f53e  mov     dword ptr [rsp+160h+var_108], r10d
0x14006f543  mov     dword ptr [rsp+160h+var_110], r11d
0x14006f548  mov     [rsp+160h+OutputBufferLength], ebx
0x14006f54c  mov     dword ptr [rsp+160h+OutputBuffer], edi
0x14006f550  mov     [rsp+160h+InputBufferLength], esi
0x14006f554  mov     dword ptr [rsp+160h+InputBuffer], eax
0x14006f558  mov     rax, [r12+50h]
0x14006f55d  mov     qword ptr [rsp+160h+FsControlCode], rax
0x14006f562  mov     qword ptr [rsp+160h+InitialState], r14
0x14006f567  call    WPP_SF_qZiDDDDDDDDDDD
0x14006f56c  xor     r14d, r14d
0x14006f56f  lea     rsi, WPP_GLOBAL_Control
0x14006f576  mov     edi, 100000h
0x14006f57b  mov     rdx, [r15+50h]
0x14006f57f  lea     rax, [rbp+50h+arg_10]
0x14006f583  mov     rcx, [r13+40h]
0x14006f587  lea     r9, [rbp+50h+P]
0x14006f58b  mov     [rsp+160h+var_100], rax
0x14006f590  lea     r8, [rbp+50h+var_C0]
0x14006f594  lea     rax, [rbp+50h+var_BC]
0x14006f598  mov     rdx, [rdx+60h]
0x14006f59c  mov     [rsp+160h+var_108], rax
0x14006f5a1  lea     rax, [rbp+50h+arg_18]
0x14006f5a5  mov     [rsp+160h+var_110], rax
0x14006f5aa  lea     rax, [rbp+50h+var_98]
0x14006f5ae  mov     qword ptr [rsp+160h+OutputBufferLength], rax
0x14006f5b3  lea     rax, [rbp+50h+var_A8]
0x14006f5b7  mov     [rsp+160h+OutputBuffer], rax
0x14006f5bc  lea     rax, [rbp+50h+var_C8]
0x14006f5c0  mov     qword ptr [rsp+160h+InputBufferLength], rax
0x14006f5c5  lea     rax, [rbp+50h+var_A0]
0x14006f5c9  mov     [rsp+160h+InputBuffer], rax
0x14006f5ce  lea     rax, [rbp+50h+var_B8]
0x14006f5d2  mov     qword ptr [rsp+160h+FsControlCode], rax
0x14006f5d7  lea     rax, [rbp+50h+var_C4]
0x14006f5db  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f5e0  call    Smb2RkfReadState
0x14006f5e5  mov     ebx, eax
0x14006f5e7  test    eax, eax
0x14006f5e9  jns     loc_14006F68B
0x14006f5ef  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f5f6  cmp     rcx, rsi
0x14006f5f9  jz      short loc_14006F631
0x14006f5fb  test    [rcx+2Ch], edi
0x14006f5fe  jz      short loc_14006F631
0x14006f600  mov     dil, 1
0x14006f603  cmp     [rcx+29h], dil
0x14006f607  jb      short loc_14006F631
0x14006f609  mov     edx, 14h
0x14006f60e  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f615  mov     rcx, [rcx+18h]
0x14006f619  lea     rax, [r15+0C0h]
0x14006f620  mov     [rsp+160h+FsControlCode], ebx
0x14006f624  mov     r9, r13
0x14006f627  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f62c  call    WPP_SF_qZd
0x14006f631  mov     r14b, [rbp+50h+arg_0]
0x14006f635  mov     rcx, [rbp+50h+P]; P
0x14006f639  test    rcx, rcx
0x14006f63c  jz      short loc_14006F64C
0x14006f63e  xor     edx, edx; Tag
0x14006f640  call    cs:__imp_ExFreePoolWithTag
0x14006f647  nop     dword ptr [rax+rax+00h]
0x14006f64c  test    ebx, ebx
0x14006f64e  jns     short loc_14006F66D
0x14006f650  test    r14b, r14b
0x14006f653  jnz     short loc_14006F66D
0x14006f655  mov     rdx, [r15+50h]
0x14006f659  mov     rcx, [r13+40h]
0x14006f65d  mov     rdx, [rdx+60h]
0x14006f661  call    Smb2RkfNotifyComplete
0x14006f666  mov     [r15+17Dh], r14b
0x14006f66d  mov     eax, ebx
0x14006f66f  mov     rbx, [rsp+160h+arg_8]
0x14006f677  add     rsp, 130h
0x14006f67e  pop     r15
0x14006f680  pop     r14
0x14006f682  pop     r13
0x14006f684  pop     r12
0x14006f686  pop     rdi
0x14006f687  pop     rsi
0x14006f688  pop     rbp
0x14006f689  retn
0x14006f68b  mov     rsi, [rbp+50h+P]
0x14006f68f  cmp     dword ptr [rsi], 3
0x14006f692  jz      short loc_14006F6E2
0x14006f694  mov     ebx, r14d
0x14006f697  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f69e  lea     rax, WPP_GLOBAL_Control
0x14006f6a5  cmp     rcx, rax
0x14006f6a8  jz      short loc_14006F631
0x14006f6aa  test    [rcx+2Ch], edi
0x14006f6ad  jz      short loc_14006F631
0x14006f6af  cmp     byte ptr [rcx+29h], 2
0x14006f6b3  jb      loc_14006F631
0x14006f6b9  mov     rcx, [rcx+18h]
0x14006f6bd  lea     rax, [r15+0C0h]
0x14006f6c4  mov     edx, 15h
0x14006f6c9  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f6ce  mov     r9, r13
0x14006f6d1  lea     r8, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f6d8  call    WPP_SF_qZ
0x14006f6dd  jmp     loc_14006F631
0x14006f6e2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f6e9  lea     rax, WPP_GLOBAL_Control
0x14006f6f0  mov     r14d, [rbp+50h+var_C8]
0x14006f6f4  cmp     rcx, rax
0x14006f6f7  jz      short loc_14006F740
0x14006f6f9  test    [rcx+2Ch], edi
0x14006f6fc  jz      short loc_14006F740
0x14006f6fe  cmp     byte ptr [rcx+29h], 2
0x14006f702  jb      short loc_14006F740
0x14006f704  mov     eax, [rbp+50h+arg_18]
0x14006f707  lea     rdx, [r15+0C0h]
0x14006f70e  mov     rcx, [rcx+18h]
0x14006f712  mov     r9, r13
0x14006f715  mov     [rsp+160h+OutputBufferLength], eax
0x14006f719  mov     eax, [rsi+58h]
0x14006f71c  mov     dword ptr [rsp+160h+OutputBuffer], r14d
0x14006f721  mov     [rsp+160h+InputBufferLength], eax
0x14006f725  mov     eax, [rbp+50h+var_C4]
0x14006f728  mov     dword ptr [rsp+160h+InputBuffer], eax
0x14006f72c  mov     rax, [r12+50h]
0x14006f731  mov     qword ptr [rsp+160h+FsControlCode], rax
0x14006f736  mov     qword ptr [rsp+160h+InitialState], rdx
0x14006f73b  call    WPP_SF_qZiDDDD
0x14006f740  mov     edx, [rbp+50h+var_C0]
0x14006f743  mov     dil, 1
0x14006f746  mov     r8, rsi
0x14006f749  mov     [r15+17Ch], dil
0x14006f750  mov     rcx, r13
0x14006f753  call    Smb2RkfResumeAppInstance
0x14006f758  lea     rsi, WPP_857f2cc8c50b3da0e48609e9ae4069db_Traceguids
0x14006f75f  test    al, al
0x14006f761  jz      short loc_14006F78C
0x14006f763  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f76a  lea     rax, WPP_GLOBAL_Control
0x14006f771  cmp     rcx, rax
0x14006f774  jz      short loc_14006F7CE
0x14006f776  test    dword ptr [rcx+2Ch], 100000h
0x14006f77d  jz      short loc_14006F7CE
0x14006f77f  cmp     byte ptr [rcx+29h], 2
0x14006f783  jb      short loc_14006F7CE
0x14006f785  mov     edx, 17h
0x14006f78a  jmp     short loc_14006F7B3
0x14006f78c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f793  lea     rax, WPP_GLOBAL_Control
0x14006f79a  cmp     rcx, rax
0x14006f79d  jz      short loc_14006F7CE
0x14006f79f  test    dword ptr [rcx+2Ch], 100000h
0x14006f7a6  jz      short loc_14006F7CE
0x14006f7a8  cmp     byte ptr [rcx+29h], 2
0x14006f7ac  jb      short loc_14006F7CE
0x14006f7ae  mov     edx, 18h
0x14006f7b3  mov     rcx, [rcx+18h]
0x14006f7b7  lea     rax, [r15+0C0h]
0x14006f7be  mov     r9, r13
0x14006f7c1  mov     qword ptr [rsp+160h+InitialState], rax
0x14006f7c6  mov     r8, rsi
0x14006f7c9  call    WPP_SF_qZ
0x14006f7ce  mov     r9, [rbp+50h+var_A8]
0x14006f7d2  test    r9, r9
0x14006f7d5  jz      short loc_14006F827
0x14006f7d7  mov     rdx, [rbp+50h+var_A0]
0x14006f7db  mov     r8d, r14d
0x14006f7de  mov     rcx, r12
0x14006f7e1  call    Smb2RestoreFileLockState
0x14006f7e6  mov     ebx, eax
0x14006f7e8  test    eax, eax
0x14006f7ea  jns     short loc_14006F827
0x14006f7ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006f7f3  lea     rax, WPP_GLOBAL_Control
0x14006f7fa  cmp     rcx, rax
0x14006f7fd  jz      loc_14006F631
0x14006f803  test    dword ptr [rcx+2Ch], 100000h
0x14006f80a  jz      loc_14006F631
0x14006f810  cmp     [rcx+29h], dil
0x14006f814  jb      loc_14006F631
0x14006f81a  mov     edx, 19h
0x14006f81f  mov     r8, rsi
0x14006f822  jmp     loc_14006F615
0x14006f827  mov     r14, [rbp+50h+var_98]
0x14006f82b  mov     edx, 200h
0x14006f830  test    r14, r14
0x14006f833  jz      loc_14006F9B3
0x14006f839  mov     [rbp+50h+ObjectAttributes.Attributes], edx
0x14006f83c  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x14006f840  xorps   xmm0, xmm0
0x14006f843  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x14006f84a  mov     edx, 1F0003h; DesiredAccess
0x14006f84f  mov     [rbp+50h+ObjectAttributes.RootDirectory], 0
0x14006f857  xor     r9d, r9d; EventType
0x14006f85a  mov     [rbp+50h+ObjectAttributes.ObjectName], 0
0x14006f862  lea     rcx, [rbp+50h+EventHandle]; EventHandle
0x14006f866  mov     [rsp+160h+InitialState], 0; InitialState
0x14006f86b  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006f870  call    cs:__imp_ZwCreateEvent
0x14006f877  nop     dword ptr [rax+rax+00h]
0x14006f87c  mov     ebx, eax
0x14006f87e  test    eax, eax
0x14006f880  js      loc_14006F631
0x14006f886  mov     rcx, [r15+50h]
0x14006f88a  xor     r9d, r9d; ApcContext
0x14006f88d  mov     eax, [rbp+50h+arg_18]
0x14006f890  xor     r8d, r8d; ApcRoutine
0x14006f893  mov     rdx, [rbp+50h+EventHandle]; Event
0x14006f897  mov     [rsp+160h+OutputBufferLength], 0; OutputBufferLength
0x14006f89f  mov     rcx, [rcx+58h]; FileHandle
0x14006f8a3  mov     [rsp+160h+OutputBuffer], 0; OutputBuffer
0x14006f8ac  mov     [rsp+160h+InputBufferLength], eax; InputBufferLength
0x14006f8b0  lea     rax, [rbp+50h+IoStatusBlock]
0x14006f8b4  mov     [rsp+160h+InputBuffer], r14; InputBuffer
0x14006f8b9  mov     [rsp+160h+FsControlCode], 90308h; FsControlCode
0x14006f8c1  mov     qword ptr [rsp+160h+InitialState], rax; IoStatusBlock
0x14006f8c6  call    cs:__imp_ZwFsControlFile
0x14006f8cd  nop     dword ptr [rax+rax+00h]
0x14006f8d2  mov     ebx, eax
0x14006f8d4  cmp     eax, 103h
0x14006f8d9  jnz     short loc_14006F8F3
0x14006f8db  mov     rcx, [rbp+50h+EventHandle]; Handle
0x14006f8df  xor     r8d, r8d; Timeout
0x14006f8e2  xor     edx, edx; Alertable
0x14006f8e4  call    cs:__imp_ZwWaitForSingleObject
0x14006f8eb  nop     dword ptr [rax+rax+00h]
0x14006f8f0  mov     ebx, dword ptr [rbp+50h+IoStatusBlock]
0x14006f8f3  mov     rcx, [rbp+50h+EventHandle]; Handle
0x14006f8f7  call    cs:__imp_ZwClose
0x14006f8fe  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
