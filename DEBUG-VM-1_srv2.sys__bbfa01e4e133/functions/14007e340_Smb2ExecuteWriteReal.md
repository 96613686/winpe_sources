# Smb2ExecuteWriteReal

- ea: `0x14007e340`
- end: `0x14007ea49`
- name: `Smb2ExecuteWriteReal`
- size: `1801`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007e280`

## callees

- `0x140005070`
- `0x140006ad0`
- `0x140007090`
- `0x140007400`
- `0x140008190`
- `0x1400125d0`
- `0x140013810`
- `0x140015000`
- `0x1400152a0`
- `0x140017730`
- `0x1400186f0`
- `0x14001f050`
- `0x1400222ec`
- `0x140022958`
- `0x1400384d0`
- `0x140038680`
- `0x14006c4f8`
- `0x140077600`
- `0x14007e340`
- `0x14007f2f0`
- `0x140080364`
- `0x140086110`
- `0x140091888`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14007e738`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007e738`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007e9a2`
- `ntoskrnl!KeDelayExecutionThread` at `0x14007e9a2`
- `ntoskrnl!ExAllocatePool2` at `0x14007e5a6`
- `ntoskrnl!ExAllocatePool2` at `0x14007e5a6`
- `ntoskrnl!IofCallDriver` at `0x14007e976`
- `ntoskrnl!IofCallDriver` at `0x14007e976`
- `ntoskrnl!IoFreeIrp` at `0x14007e405`
- `ntoskrnl!IoFreeIrp` at `0x14007e405`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007e3e9`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007e3e9`
- `srvnet!SrvLibAuditForceAccess` at `0x14007e38d`
- `srvnet!SrvLibAuditForceAccess` at `0x14007e38d`

## string_xrefs

- `0x14007ea1a`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14007e682`: `Smb2ExecuteWriteReal`
- `0x14007e6e2`: `Smb2ExecuteWriteReal`
- `0x14007e95a`: `Smb2ExecuteWriteReal`

## pseudocode

```c
NTSTATUS __fastcall Smb2ExecuteWriteReal(__int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  char v7; // cl
  __int64 v8; // rdx
  __int64 Irp; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  char v14; // al
  NTSTATUS result; // eax
  char v16; // al
  void *v17; // rbp
  unsigned int v18; // edx
  unsigned int v19; // eax
  __int64 Pool2; // rax
  void *v21; // rbx
  __int64 v22; // rbx
  char v23; // al
  __int64 v24; // rcx
  int v25; // r8d
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 (__fastcall *v29)(); // rdx
  int v30; // eax
  __int64 v31; // rdx
  char v32; // al
  char v33; // bl
  int v34; // [rsp+20h] [rbp-68h]
  int v35; // [rsp+20h] [rbp-68h]
  int v36; // [rsp+20h] [rbp-68h]
  int v37; // [rsp+28h] [rbp-60h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 304) + 24LL);
  if ( !*(_BYTE *)(*(_QWORD *)(v2 + 72) + 235LL) && (int)Smb2ImpersonateWorkItem(*(_QWORD *)(a1 + 560)) >= 0 )
  {
    if ( (int)SrvLibAuditForceAccess(*(_QWORD *)(*(_QWORD *)(v2 + 80) + 88LL), 2) >= 0 )
      *(_BYTE *)(*(_QWORD *)(v2 + 72) + 235LL) = 1;
    Smb2Revert();
  }
  Smb2DereferenceHandle(*(PVOID *)(v2 + 80));
  v6 = *(_QWORD *)(v2 + 96);
  *(_QWORD *)(v2 + 80) = 0;
  v7 = *(_BYTE *)(v6 + 76);
  if ( *(char *)(*(_QWORD *)(a1 + 120) + 66LL) < v7 || (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
  {
    v8 = 15;
    if ( v7 > 15 )
      v8 = *(unsigned __int8 *)(v6 + 76);
    Irp = IoAllocateIrpEx(-1, v8, 0);
    if ( !Irp )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          70,
          &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids,
          a1,
          -1073741670);
      }
      v12 = 2635;
      v13 = 3221225626LL;
      goto LABEL_92;
    }
    IoFreeIrp(*(PIRP *)(a1 + 120));
    *(_QWORD *)(a1 + 120) = Irp;
  }
  if ( (*(_BYTE *)(v2 + 280) & 0x18) != 0 )
  {
    LOBYTE(v5) = 1;
    v10 = Smb2PreGoAsync2Ex(a1, 0, v5);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 71, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1, v10);
      }
      v12 = 2653;
      v13 = v11;
      goto LABEL_92;
    }
  }
  if ( *(_QWORD *)(v2 + 216) )
  {
    v14 = *(_BYTE *)(v2 + 280);
    if ( (v14 & 0x40) != 0 || v14 < 0 )
      return Smb2ExecuteDirectPlacementWrite(a1);
    else
      return Smb2ExecuteDirectPlacementMdlWrite(a1);
  }
  if ( *(_DWORD *)(a1 + 404) < *(_DWORD *)(v3 + 68) + (unsigned int)*(unsigned __int16 *)(v3 + 66) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 72, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v12 = 2706;
LABEL_30:
    v13 = 3221225485LL;
LABEL_92:
    Smb2SetError(a1, v13, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", v12);
    return Srv2CompleteWorkItem(a1, 0);
  }
  v16 = *(_BYTE *)(v2 + 280);
  v17 = (void *)(*(unsigned __int16 *)(v3 + 66) + v3);
  if ( (v16 & 0x40) == 0 || (v16 & 8) != 0 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(v2 + 72) + 239LL) )
    {
      v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 96) + 8LL) + 80LL);
      if ( v22 )
      {
        if ( *(_DWORD *)v22 > 0x18u && *(_QWORD *)(v22 + 24) )
        {
          LOBYTE(v4) = 2;
          SRV2_PERF_ENTER_EX(a1 + 584, v4, 2771, "Smb2ExecuteWriteReal", 1);
          v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, void *, __int64, _QWORD))(v22 + 24))(
                  *(_QWORD *)(v2 + 88),
                  v2 + 192,
                  *(unsigned int *)(v2 + 248),
                  0,
                  *(_DWORD *)(v2 + 256),
                  v17,
                  *(_QWORD *)(a1 + 120) + 48LL,
                  *(_QWORD *)(v2 + 96));
          LOBYTE(v35) = 1;
          v24 = a1 + 584;
          if ( v23 )
          {
            SRV2_PERF_ENTER_EX(v24, 0, 2783, "Smb2ExecuteWriteReal", v35);
            *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
            return Smb2ContinueWrite(a1);
          }
          SRV2_PERF_ENTER_EX(v24, 0, 2789, "Smb2ExecuteWriteReal", v35);
        }
      }
    }
  }
  else
  {
    v18 = *(_DWORD *)(*(_QWORD *)(v2 + 96) + 152LL);
    if ( v18 > 1 && ((*(_DWORD *)(*(_QWORD *)(v2 + 96) + 152LL) - 1) & (unsigned int)v17) != 0 )
    {
      v19 = *(_DWORD *)(v2 + 248);
      if ( v19 + v18 < v19 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
        }
        v12 = 2737;
        goto LABEL_30;
      }
      Pool2 = ExAllocatePool2(258, v19 + v18, 1647465292);
      *(_QWORD *)(v2 + 208) = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 74, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
        }
        v12 = 2752;
LABEL_47:
        v13 = 3221225989LL;
        goto LABEL_92;
      }
      v21 = (void *)(~(unsigned __int64)*(unsigned int *)(*(_QWORD *)(v2 + 96) + 152LL)
                   & (*(unsigned int *)(*(_QWORD *)(v2 + 96) + 152LL) + Pool2));
      memmove(v21, v17, *(unsigned int *)(v2 + 248));
      v17 = v21;
    }
  }
  IoBuildPartialMdl(
    *(PMDL *)(*(_QWORD *)(a1 + 304) + 56LL),
    *(PMDL *)(*(_QWORD *)(a1 + 304) + 80LL),
    v17,
    *(_DWORD *)(v2 + 248));
  LOBYTE(v25) = *(_BYTE *)(v2 + 280);
  if ( (v25 & 8) != 0 )
  {
    LOBYTE(v25) = 4;
    v26 = Smb2BuildPipeReadOrWriteRequest(a1, *(_QWORD *)(v2 + 88), v25, (_DWORD)v17, *(_DWORD *)(v2 + 248));
  }
  else
  {
    v29 = Srv2PostOnCompletionAndClearCancel;
    if ( Smb2EnableInlineSendIOCompletion )
      v29 = Srv2ClearCancelAndCallCallback;
    LOBYTE(v37) = 0;
    LOBYTE(v34) = 4;
    v26 = Smb2BuildReadOrWriteRequest(
            a1,
            0,
            *(_QWORD *)(v2 + 88),
            *(_QWORD *)(v2 + 96),
            v34,
            v37,
            v17,
            *(_DWORD *)(v2 + 248),
            *(_QWORD *)(*(_QWORD *)(a1 + 304) + 80LL),
            *(_QWORD *)(v2 + 192),
            *(_DWORD *)(v2 + 256),
            v29,
            (v25 & 0x40) != 0,
            (v25 & 0x20) != 0);
  }
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 75, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v12 = 2837;
    goto LABEL_47;
  }
  *(_BYTE *)(*(_QWORD *)(v2 + 72) + 239LL) = 1;
  if ( (*(_BYTE *)(v2 + 280) & 8) == 0
    && *(_BYTE *)(*(_QWORD *)(v2 + 56) + 88LL)
    && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 88) + 24LL) + 40LL) + 0x2000000LL < *(_QWORD *)(v2 + 192) )
  {
    if ( *(_QWORD *)(v2 + 168) != -1 || (LOBYTE(v28) = 1, v30 = Smb2PreGoAsync2Ex(a1, 0, v28), v30 >= 0) )
    {
      *(_DWORD *)(a1 + 72) = 1;
      *(_QWORD *)(a1 + 48) = Smb2ExecuteVdlWriteReal;
      return Smb2GoAsyncForSyncCall(a1);
    }
    v12 = 2858;
    v13 = (unsigned int)v30;
    goto LABEL_92;
  }
  *(_QWORD *)(a1 + 48) = Smb2ContinueWrite;
  LOBYTE(v27) = (*(_BYTE *)(v2 + 280) & 8) != 0;
  if ( (int)Srv2MarkWorkItemCancellable(a1, v27) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 76, &WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids, a1);
    }
    v12 = 2884;
    v13 = 3221225760LL;
    goto LABEL_92;
  }
  v32 = *(_BYTE *)(v2 + 280);
  if ( (v32 & 8) != 0 || (v33 = 0, (v32 & 0x10) != 0) )
  {
    v33 = 1;
    Srv2ReferenceConnection(a1);
  }
  LOBYTE(v36) = 1;
  LOBYTE(v31) = 3;
  SRV2_PERF_ENTER_EX(a1 + 584, v31, 2895, "Smb2ExecuteWriteReal", v36);
  result = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 96), *(PIRP *)(a1 + 120));
  if ( v33 )
  {
    Interval.QuadPart = -5000;
    KeDelayExecutionThread(0, 0, &Interval);
    if ( (unsigned int)Srv2MarkWorkItemPending(a1) )
      return Srv2DereferenceWorkItem(a1);
    else
      return Smb2GoAsync2(a1);
  }
  return result;
}

```

## disassembly

```asm
0x14007e340  mov     [rsp+arg_8], rbx
0x14007e345  mov     [rsp+arg_10], rbp
0x14007e34a  push    rsi
0x14007e34b  push    rdi
0x14007e34c  push    r14
0x14007e34e  sub     rsp, 70h
0x14007e352  mov     rax, [rcx+130h]
0x14007e359  mov     rdi, rcx
0x14007e35c  mov     rsi, [rcx+230h]
0x14007e363  mov     rbp, [rax+18h]
0x14007e367  mov     rax, [rsi+48h]
0x14007e36b  cmp     byte ptr [rax+0EBh], 0
0x14007e372  jnz     short loc_14007E3AD
0x14007e374  mov     rcx, rsi
0x14007e377  call    Smb2ImpersonateWorkItem
0x14007e37c  test    eax, eax
0x14007e37e  js      short loc_14007E3AD
0x14007e380  mov     rcx, [rsi+50h]
0x14007e384  mov     edx, 2
0x14007e389  mov     rcx, [rcx+58h]
0x14007e38d  call    cs:__imp_SrvLibAuditForceAccess
0x14007e394  nop     dword ptr [rax+rax+00h]
0x14007e399  test    eax, eax
0x14007e39b  js      short loc_14007E3A8
0x14007e39d  mov     rax, [rsi+48h]
0x14007e3a1  mov     byte ptr [rax+0EBh], 1
0x14007e3a8  call    Smb2Revert
0x14007e3ad  mov     rcx, [rsi+50h]; P
0x14007e3b1  call    Smb2DereferenceHandle
0x14007e3b6  mov     rax, [rsi+60h]
0x14007e3ba  mov     qword ptr [rsi+50h], 0
0x14007e3c2  movzx   ecx, byte ptr [rax+4Ch]
0x14007e3c6  mov     rax, [rdi+78h]
0x14007e3ca  cmp     [rax+42h], cl
0x14007e3cd  jl      short loc_14007E3D8
0x14007e3cf  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x14007e3d6  jz      short loc_14007E415
0x14007e3d8  mov     edx, 0Fh
0x14007e3dd  cmp     cl, dl
0x14007e3df  cmovg   edx, ecx
0x14007e3e2  xor     r8d, r8d
0x14007e3e5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14007e3e9  call    cs:__imp_IoAllocateIrpEx
0x14007e3f0  nop     dword ptr [rax+rax+00h]
0x14007e3f5  mov     rbx, rax
0x14007e3f8  test    rax, rax
0x14007e3fb  jz      loc_14007E9CB
0x14007e401  mov     rcx, [rdi+78h]; Irp
0x14007e405  call    cs:__imp_IoFreeIrp
0x14007e40c  nop     dword ptr [rax+rax+00h]
0x14007e411  mov     [rdi+78h], rbx
0x14007e415  test    byte ptr [rsi+118h], 18h
0x14007e41c  jz      short loc_14007E47E
0x14007e41e  mov     r8b, 1
0x14007e421  xor     edx, edx
0x14007e423  mov     rcx, rdi
0x14007e426  call    Smb2PreGoAsync2Ex
0x14007e42b  mov     ebx, eax
0x14007e42d  test    eax, eax
0x14007e42f  jns     short loc_14007E47E
0x14007e431  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e438  lea     rcx, WPP_GLOBAL_Control
0x14007e43f  cmp     r10, rcx
0x14007e442  jz      short loc_14007E471
0x14007e444  test    dword ptr [r10+2Ch], 800000h
0x14007e44c  jz      short loc_14007E471
0x14007e44e  cmp     byte ptr [r10+29h], 1
0x14007e453  jb      short loc_14007E471
0x14007e455  mov     rcx, [r10+18h]
0x14007e459  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e460  mov     edx, 47h ; 'G'
0x14007e465  mov     [rsp+88h+var_68], eax
0x14007e469  mov     r9, rdi
0x14007e46c  call    WPP_SF_qD
0x14007e471  mov     r9d, 0A5Dh
0x14007e477  mov     edx, ebx
0x14007e479  jmp     loc_14007EA1A
0x14007e47e  cmp     qword ptr [rsi+0D8h], 0
0x14007e486  jz      short loc_14007E4B0
0x14007e488  mov     al, [rsi+118h]
0x14007e48e  test    al, 40h
0x14007e490  jnz     short loc_14007E4A3
0x14007e492  test    al, al
0x14007e494  js      short loc_14007E4A3
0x14007e496  mov     rcx, rdi
0x14007e499  call    Smb2ExecuteDirectPlacementMdlWrite
0x14007e49e  jmp     loc_14007EA33
0x14007e4a3  mov     rcx, rdi
0x14007e4a6  call    Smb2ExecuteDirectPlacementWrite
0x14007e4ab  jmp     loc_14007EA33
0x14007e4b0  movzx   ecx, word ptr [rbp+42h]
0x14007e4b4  mov     eax, ecx
0x14007e4b6  add     eax, [rbp+44h]
0x14007e4b9  cmp     [rdi+194h], eax
0x14007e4bf  jnb     short loc_14007E50D
0x14007e4c1  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e4c8  lea     rcx, WPP_GLOBAL_Control
0x14007e4cf  cmp     r10, rcx
0x14007e4d2  jz      short loc_14007E4FD
0x14007e4d4  test    dword ptr [r10+2Ch], 800000h
0x14007e4dc  jz      short loc_14007E4FD
0x14007e4de  cmp     byte ptr [r10+29h], 1
0x14007e4e3  jb      short loc_14007E4FD
0x14007e4e5  mov     rcx, [r10+18h]
0x14007e4e9  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e4f0  mov     edx, 48h ; 'H'
0x14007e4f5  mov     r9, rdi
0x14007e4f8  call    WPP_SF_q
0x14007e4fd  mov     r9d, 0A92h
0x14007e503  mov     edx, 0C000000Dh
0x14007e508  jmp     loc_14007EA1A
0x14007e50d  mov     al, [rsi+118h]
0x14007e513  add     rbp, rcx
0x14007e516  test    al, 40h
0x14007e518  jz      loc_14007E639
0x14007e51e  test    al, 8
0x14007e520  jnz     loc_14007E639
0x14007e526  mov     rax, [rsi+60h]
0x14007e52a  mov     edx, [rax+98h]
0x14007e530  cmp     edx, 1
0x14007e533  jbe     loc_14007E71F
0x14007e539  lea     ecx, [rdx-1]
0x14007e53c  test    rbp, rcx
0x14007e53f  jz      loc_14007E71F
0x14007e545  mov     eax, [rsi+0F8h]
0x14007e54b  lea     ecx, [rax+rdx]
0x14007e54e  cmp     ecx, eax
0x14007e550  jnb     short loc_14007E599
0x14007e552  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e559  lea     rcx, WPP_GLOBAL_Control
0x14007e560  cmp     r10, rcx
0x14007e563  jz      short loc_14007E58E
0x14007e565  test    dword ptr [r10+2Ch], 800000h
0x14007e56d  jz      short loc_14007E58E
0x14007e56f  cmp     byte ptr [r10+29h], 1
0x14007e574  jb      short loc_14007E58E
0x14007e576  mov     rcx, [r10+18h]
0x14007e57a  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e581  mov     edx, 49h ; 'I'
0x14007e586  mov     r9, rdi
0x14007e589  call    WPP_SF_q
0x14007e58e  mov     r9d, 0AB1h
0x14007e594  jmp     loc_14007E503
0x14007e599  mov     edx, ecx
0x14007e59b  mov     r8d, 6232534Ch
0x14007e5a1  mov     ecx, 102h
0x14007e5a6  call    cs:__imp_ExAllocatePool2
0x14007e5ad  nop     dword ptr [rax+rax+00h]
0x14007e5b2  mov     [rsi+0D0h], rax
0x14007e5b9  mov     rdx, rax
0x14007e5bc  test    rax, rax
0x14007e5bf  jnz     short loc_14007E60B
0x14007e5c1  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e5c8  lea     rcx, WPP_GLOBAL_Control
0x14007e5cf  cmp     r10, rcx
0x14007e5d2  jz      short loc_14007E5FB
0x14007e5d4  test    dword ptr [r10+2Ch], 800000h
0x14007e5dc  jz      short loc_14007E5FB
0x14007e5de  cmp     byte ptr [r10+29h], 1
0x14007e5e3  jb      short loc_14007E5FB
0x14007e5e5  mov     rcx, [r10+18h]
0x14007e5e9  lea     edx, [rax+4Ah]
0x14007e5ec  mov     r9, rdi
0x14007e5ef  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e5f6  call    WPP_SF_q
0x14007e5fb  mov     r9d, 0AC0h
0x14007e601  mov     edx, 0C0000205h
0x14007e606  jmp     loc_14007EA1A
0x14007e60b  mov     rax, [rsi+60h]
0x14007e60f  mov     r8d, [rsi+0F8h]; Size
0x14007e616  mov     ecx, [rax+98h]
0x14007e61c  lea     rbx, [rcx+rdx]
0x14007e620  not     rcx
0x14007e623  and     rbx, rcx
0x14007e626  mov     rdx, rbp; Src
0x14007e629  mov     rcx, rbx; void *
0x14007e62c  call    memmove
0x14007e631  mov     rbp, rbx
0x14007e634  jmp     loc_14007E71F
0x14007e639  mov     rax, [rsi+48h]
0x14007e63d  cmp     byte ptr [rax+0EFh], 0
0x14007e644  jz      loc_14007E71F
0x14007e64a  mov     rax, [rsi+60h]
0x14007e64e  mov     rcx, [rax+8]
0x14007e652  mov     rbx, [rcx+50h]
0x14007e656  test    rbx, rbx
0x14007e659  jz      loc_14007E71F
0x14007e65f  cmp     dword ptr [rbx], 18h
0x14007e662  jbe     loc_14007E71F
0x14007e668  cmp     qword ptr [rbx+18h], 0
0x14007e66d  jz      loc_14007E71F
0x14007e673  lea     r14, [rdi+248h]
0x14007e67a  mov     byte ptr [rsp+88h+var_68], 1
0x14007e67f  mov     rcx, r14
0x14007e682  lea     r9, aSmb2executewri; "Smb2ExecuteWriteReal"
0x14007e689  mov     r8d, 0AD3h
0x14007e68f  mov     dl, 2
0x14007e691  call    SRV2_PERF_ENTER_EX
0x14007e696  mov     rcx, [rsi+60h]
0x14007e69a  lea     rdx, [rsi+0C0h]
0x14007e6a1  mov     r8, [rdi+78h]
0x14007e6a5  xor     r9d, r9d
0x14007e6a8  mov     rax, [rbx+18h]
0x14007e6ac  add     r8, 30h ; '0'
0x14007e6b0  mov     [rsp+88h+var_50], rcx
0x14007e6b5  mov     rcx, [rsi+58h]
0x14007e6b9  mov     [rsp+88h+var_58], r8
0x14007e6be  mov     r8d, [rsi+100h]
0x14007e6c5  mov     [rsp+88h+var_60], rbp
0x14007e6ca  mov     [rsp+88h+var_68], r8d
0x14007e6cf  mov     r8d, [rsi+0F8h]
0x14007e6d6  call    _guard_dispatch_icall
0x14007e6db  xor     edx, edx
0x14007e6dd  mov     byte ptr [rsp+88h+var_68], 1
0x14007e6e2  lea     r9, aSmb2executewri; "Smb2ExecuteWriteReal"
0x14007e6e9  mov     rcx, r14
0x14007e6ec  test    al, al
0x14007e6ee  jz      short loc_14007E714
0x14007e6f0  mov     r8d, 0ADFh
0x14007e6f6  call    SRV2_PERF_ENTER_EX
0x14007e6fb  mov     rax, [rdi+78h]
0x14007e6ff  mov     rcx, rdi
0x14007e702  mov     qword ptr [rax+8], 0
0x14007e70a  call    Smb2ContinueWrite
0x14007e70f  jmp     loc_14007EA33
0x14007e714  mov     r8d, 0AE5h
0x14007e71a  call    SRV2_PERF_ENTER_EX
0x14007e71f  mov     rcx, [rdi+130h]
0x14007e726  mov     r8, rbp; VirtualAddress
0x14007e729  mov     r9d, [rsi+0F8h]; Length
0x14007e730  mov     rdx, [rcx+50h]; TargetMdl
0x14007e734  mov     rcx, [rcx+38h]; SourceMdl
0x14007e738  call    cs:__imp_IoBuildPartialMdl
0x14007e73f  nop     dword ptr [rax+rax+00h]
0x14007e744  mov     r8b, [rsi+118h]
0x14007e74b  test    r8b, 8
0x14007e74f  jz      short loc_14007E772
0x14007e751  mov     eax, [rsi+0F8h]
0x14007e757  mov     r9, rbp
0x14007e75a  mov     rdx, [rsi+58h]
0x14007e75e  mov     r8b, 4
0x14007e761  mov     rcx, rdi
0x14007e764  mov     [rsp+88h+var_68], eax
0x14007e768  call    Smb2BuildPipeReadOrWriteRequest
0x14007e76d  jmp     loc_14007E7FA
0x14007e772  mov     rcx, [rdi+130h]
0x14007e779  lea     rax, Srv2ClearCancelAndCallCallback
0x14007e780  cmp     cs:Smb2EnableInlineSendIOCompletion, 0
0x14007e787  lea     rdx, Srv2PostOnCompletionAndClearCancel
0x14007e78e  mov     r9, [rsi+60h]
0x14007e792  cmovnz  rdx, rax
0x14007e796  mov     al, r8b
0x14007e799  shr     al, 5
0x14007e79c  and     al, 1
0x14007e79e  shr     r8b, 6
0x14007e7a2  mov     [rsp+88h+var_20], al
0x14007e7a6  and     r8b, 1
0x14007e7aa  mov     eax, [rsi+100h]
0x14007e7b0  mov     [rsp+88h+var_28], r8b
0x14007e7b5  mov     r8, [rsi+58h]
0x14007e7b9  mov     [rsp+88h+var_30], rdx
0x14007e7be  xor     edx, edx
0x14007e7c0  mov     [rsp+88h+var_38], eax
0x14007e7c4  mov     rax, [rsi+0C0h]
0x14007e7cb  mov     [rsp+88h+var_40], rax
0x14007e7d0  mov     rax, [rcx+50h]
0x14007e7d4  mov     rcx, rdi
0x14007e7d7  mov     [rsp+88h+var_48], rax
0x14007e7dc  mov     eax, [rsi+0F8h]
0x14007e7e2  mov     dword ptr [rsp+88h+var_50], eax
0x14007e7e6  mov     [rsp+88h+var_58], rbp
0x14007e7eb  mov     byte ptr [rsp+88h+var_60], 0
0x14007e7f0  mov     byte ptr [rsp+88h+var_68], 4
0x14007e7f5  call    Smb2BuildReadOrWriteRequest
0x14007e7fa  test    eax, eax
0x14007e7fc  jns     short loc_14007E845
0x14007e7fe  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007e805  lea     rcx, WPP_GLOBAL_Control
0x14007e80c  cmp     r10, rcx
0x14007e80f  jz      short loc_14007E83A
0x14007e811  test    dword ptr [r10+2Ch], 800000h
0x14007e819  jz      short loc_14007E83A
0x14007e81b  cmp     byte ptr [r10+29h], 1
0x14007e820  jb      short loc_14007E83A
0x14007e822  mov     rcx, [r10+18h]
0x14007e826  lea     r8, WPP_9e7d39b7ca7e3e56e327b0a14923adf2_Traceguids
0x14007e82d  mov     edx, 4Bh ; 'K'
0x14007e832  mov     r9, rdi
0x14007e835  call    WPP_SF_q
0x14007e83a  mov     r9d, 0B15h
0x14007e840  jmp     loc_14007E601
0x14007e845  mov     rax, [rsi+48h]
0x14007e849  mov     byte ptr [rax+0EFh], 1
0x14007e850  test    byte ptr [rsi+118h], 8
0x14007e857  jnz     short loc_14007E8C5
0x14007e859  mov     rax, [rsi+38h]
0x14007e85d  cmp     byte ptr [rax+58h], 0
0x14007e861  jz      short loc_14007E8C5
0x14007e863  mov     rax, [rsi+58h]
0x14007e867  mov     rcx, [rax+18h]
  ... truncated ...
```
