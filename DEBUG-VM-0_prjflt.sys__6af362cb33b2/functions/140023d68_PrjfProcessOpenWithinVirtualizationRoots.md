# PrjfProcessOpenWithinVirtualizationRoots

- ea: `0x140023d68`
- end: `0x14002417e`
- name: `PrjfProcessOpenWithinVirtualizationRoots`
- size: `1046`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140022320`

## callees

- `0x140002f3c`
- `0x14000b1d0`
- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x140023d68`
- `0x140024758`
- `0x140029214`
- `0x14003a6e4`
- `0x14003df88`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14002402d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400240e3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400240fb`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002402d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400240e3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400240fb`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024018`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400240a8`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400240ce`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024018`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400240a8`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400240ce`
- `FLTMGR!FltReleaseContext` at `0x14002414a`
- `FLTMGR!FltReleaseContext` at `0x14002415e`
- `FLTMGR!FltReleaseContext` at `0x14002414a`
- `FLTMGR!FltReleaseContext` at `0x14002415e`

## string_xrefs

- `0x140023e49`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023ee4`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023fbc`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
__int64 __fastcall PrjfProcessOpenWithinVirtualizationRoots(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a4,
        _WORD *a5)
{
  PVOID FsContext; // r14
  PFLT_IO_PARAMETER_BLOCK Iopb; // r10
  __int16 v9; // r12
  int SetContextFileObject; // eax
  __int64 v11; // rcx
  int v12; // r8d
  char *v13; // rdi
  int v14; // edx
  _DWORD *v15; // rsi
  int v16; // ebx
  char *v17; // rax
  int NotificationMask; // r12d
  _QWORD *v19; // rbx
  int v20; // edx
  int v21; // r8d
  bool v22; // zf
  ULONG_PTR Information; // rax
  int v24; // eax
  char v25; // cl
  struct _FAST_MUTEX *v26; // rcx
  PFLT_CONTEXT v28; // [rsp+60h] [rbp-18h] BYREF
  PFLT_CONTEXT Context[2]; // [rsp+68h] [rbp-10h] BYREF
  int v30; // [rsp+C0h] [rbp+48h] BYREF
  PFLT_INSTANCE Instancea; // [rsp+C8h] [rbp+50h]
  int v32; // [rsp+D0h] [rbp+58h]
  __int64 v33; // [rsp+D8h] [rbp+60h]

  v33 = a4;
  Instancea = Instance;
  FsContext = FileObject->FsContext;
  Context[0] = 0;
  v28 = 0;
  v30 = -1;
  Iopb = CallbackData->Iopb;
  v9 = *a5;
  v32 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  SetContextFileObject = PrjfGetSetContextFileObject(
                           Instance,
                           FileObject,
                           0x80000000,
                           1,
                           (Iopb->Parameters.Create.Options & 0x1000) != 0,
                           a4,
                           (__int64)a5,
                           Context,
                           &v28);
  v13 = (char *)Context[0];
  v14 = 0;
  v15 = v28;
  v16 = SetContextFileObject;
  if ( SetContextFileObject < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        517,
        v14,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        14,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        118,
        SetContextFileObject,
        (__int64)&FileObject->FileName);
    }
    goto LABEL_44;
  }
  if ( Context[0] )
  {
    if ( !v9 && *(_DWORD *)v28 != 1 )
    {
      v16 = -1073689086;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          517,
          v14,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          15,
          (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          143);
      }
      goto LABEL_44;
    }
    v17 = (char *)a5;
    NotificationMask = *((_DWORD *)v28 + 10);
    v19 = a5 + 4;
    if ( !NotificationMask )
    {
      if ( !*v19 )
        v17 = (char *)Context[0] + 120;
      NotificationMask = PrjfGetNotificationMask(v17);
      v17 = (char *)a5;
    }
    if ( !*v19 )
      v17 = v13 + 120;
    v16 = PrjfSendPostCreateNotifications(CallbackData, Instancea, FileObject, v33, v17, NotificationMask, &v30);
    if ( v16 < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v20,
          v21,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          16,
          (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          188,
          v16);
      }
      goto LABEL_44;
    }
    if ( v30 == -1 )
      v30 = NotificationMask;
    ExAcquireFastMutex((PFAST_MUTEX)(v13 + 8));
    v15[10] = v30;
    ExReleaseFastMutex((PFAST_MUTEX)(v13 + 8));
    if ( *v15 == 1 )
    {
      v22 = (v32 & 0x106) == 0;
    }
    else if ( *v15 )
    {
      v22 = (v32 & 0x116) == 0;
    }
    else
    {
      Information = CallbackData->IoStatus.Information;
      if ( Information == 3 || !Information )
      {
        v24 = PrjfExpandAndWait(CallbackData, 3, 1, 19, 0);
        goto LABEL_43;
      }
      if ( (v32 & 6) != 0 )
      {
        v24 = PrjfExpandAndWait(CallbackData, 3, 1, 16, 0);
        goto LABEL_43;
      }
      ExAcquireFastMutex((PFAST_MUTEX)(v13 + 8));
      if ( *((_DWORD *)v13 + 16) != 3 )
      {
        v25 = *((_BYTE *)FsContext + 6);
        if ( (v25 & 4) != 0 )
        {
          if ( (*((_BYTE *)FsContext + 4) & 0x40) != 0 )
          {
            ExAcquireFastMutex(*((PFAST_MUTEX *)FsContext + 6));
            v26 = (struct _FAST_MUTEX *)*((_QWORD *)FsContext + 6);
            *((_BYTE *)FsContext + 6) &= ~4u;
            ExReleaseFastMutex(v26);
          }
          else
          {
            *((_BYTE *)FsContext + 6) = v25 & 0xFB;
          }
        }
      }
      ExReleaseFastMutex((PFAST_MUTEX)(v13 + 8));
      v22 = (v32 & 0x100) == 0;
    }
    if ( v22 )
      goto LABEL_44;
    v24 = PrjfSetPlaceHolderFlagsSynchronized(CallbackData, Instancea, FileObject);
LABEL_43:
    v16 = v24;
LABEL_44:
    if ( v13 )
      FltReleaseContext(v13);
    goto LABEL_46;
  }
  v15 = v28;
  if ( !v28 )
    return (unsigned int)v16;
  MicrosoftTelemetryAssertTriggeredNoArgsKM(v11);
LABEL_46:
  if ( v15 )
    FltReleaseContext(v15);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140023d68  mov     [rsp-40h+arg_18], r9
0x140023d6d  mov     [rsp-40h+Instance], rdx
0x140023d72  push    rbp
0x140023d73  push    rbx
0x140023d74  push    rsi
0x140023d75  push    rdi
0x140023d76  push    r12
0x140023d78  push    r13
0x140023d7a  push    r14
0x140023d7c  push    r15
0x140023d7e  mov     rbp, rsp
0x140023d81  sub     rsp, 78h
0x140023d85  mov     r14, [r8+18h]
0x140023d89  xor     eax, eax
0x140023d8b  mov     [rbp+Context], rax
0x140023d8f  mov     r11, rdx
0x140023d92  mov     [rbp+var_18], rax
0x140023d96  lea     rdx, [rbp+var_18]
0x140023d9a  mov     [rsp+78h+var_38], rdx; __int64
0x140023d9f  mov     r15, rcx
0x140023da2  mov     rcx, [rbp+arg_20]
0x140023da6  lea     rdx, [rbp+Context]
0x140023daa  mov     qword ptr [rsp+78h+var_40], rdx; __int64
0x140023daf  mov     r13, r8
0x140023db2  mov     [rbp+arg_0], 0FFFFFFFFh
0x140023db9  mov     r8d, 80000000h
0x140023dbf  mov     r10, [r15+10h]
0x140023dc3  mov     rdx, r13; FileObject
0x140023dc6  movzx   r12d, word ptr [rcx]
0x140023dca  mov     [rsp+78h+var_48], rcx; __int64
0x140023dcf  mov     rcx, r11; Instance
0x140023dd2  mov     [rsp+78h+var_50], r9; __int64
0x140023dd7  mov     r9b, 1
0x140023dda  mov     rax, [r10+18h]
0x140023dde  mov     eax, [rax+10h]
0x140023de1  mov     [rbp+arg_10], eax
0x140023de4  mov     eax, [r10+20h]
0x140023de8  shr     eax, 0Ch
0x140023deb  and     al, 1
0x140023ded  mov     [rsp+78h+var_58], al; char
0x140023df1  call    PrjfGetSetContextFileObject
0x140023df6  mov     rdi, [rbp+Context]
0x140023dfa  xor     edx, edx
0x140023dfc  mov     rsi, [rbp+var_18]
0x140023e00  mov     ebx, eax
0x140023e02  test    eax, eax
0x140023e04  jns     loc_140023E8B
0x140023e0a  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140023e10  lea     rax, WPP_RECORDER_INITIALIZED
0x140023e17  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023e1e  setnz   r8b
0x140023e22  and     dl, 20h
0x140023e25  jnz     short loc_140023E30
0x140023e27  test    r8b, r8b
0x140023e2a  jz      loc_140024142
0x140023e30  mov     r9, cs:WPP_GLOBAL_Control
0x140023e37  lea     rax, [r13+58h]
0x140023e3b  mov     [rsp+78h+var_20], rax
0x140023e40  mov     ecx, 205h
0x140023e45  mov     [rsp+78h+var_28], ebx
0x140023e49  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023e50  mov     [rsp+78h+var_30], 176h
0x140023e58  mov     r9, [r9+40h]
0x140023e5c  mov     [rsp+78h+var_38], rax
0x140023e61  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023e68  mov     qword ptr [rsp+78h+var_40], rax
0x140023e6d  mov     word ptr [rsp+78h+var_48], 0Eh
0x140023e74  mov     dword ptr [rsp+78h+var_50], 5
0x140023e7c  mov     [rsp+78h+var_58], 2
0x140023e81  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140023e86  jmp     loc_140024142
0x140023e8b  test    rdi, rdi
0x140023e8e  jnz     short loc_140023EA7
0x140023e90  mov     rsi, [rbp+var_18]
0x140023e94  test    rsi, rsi
0x140023e97  jz      loc_14002416A
0x140023e9d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140023ea2  jmp     loc_140024156
0x140023ea7  test    r12w, r12w
0x140023eab  jnz     short loc_140023F2B
0x140023ead  cmp     dword ptr [rsi], 1
0x140023eb0  jz      short loc_140023F2B
0x140023eb2  mov     ebx, 0C000CE02h
0x140023eb7  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140023ebd  lea     rax, WPP_RECORDER_INITIALIZED
0x140023ec4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023ecb  setnz   r8b
0x140023ecf  and     dl, 20h
0x140023ed2  jnz     short loc_140023EDD
0x140023ed4  test    r8b, r8b
0x140023ed7  jz      loc_140024142
0x140023edd  mov     r9, cs:WPP_GLOBAL_Control
0x140023ee4  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023eeb  mov     [rsp+78h+var_30], 18Fh
0x140023ef3  mov     ecx, 205h
0x140023ef8  mov     [rsp+78h+var_38], rax
0x140023efd  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023f04  mov     qword ptr [rsp+78h+var_40], rax
0x140023f09  mov     r9, [r9+40h]
0x140023f0d  mov     word ptr [rsp+78h+var_48], 0Fh
0x140023f14  mov     dword ptr [rsp+78h+var_50], 5
0x140023f1c  mov     [rsp+78h+var_58], 2
0x140023f21  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140023f26  jmp     loc_140024142
0x140023f2b  mov     rax, [rbp+arg_20]
0x140023f2f  mov     r12d, [rsi+28h]
0x140023f33  lea     rbx, [rax+8]
0x140023f37  test    r12d, r12d
0x140023f3a  jnz     short loc_140023F5A
0x140023f3c  cmp     [rbx], rdx
0x140023f3f  jnz     short loc_140023F45
0x140023f41  lea     rax, [rdi+78h]
0x140023f45  mov     rdx, [rbp+arg_18]
0x140023f49  mov     rcx, rax
0x140023f4c  call    PrjfGetNotificationMask
0x140023f51  mov     r12d, eax
0x140023f54  xor     edx, edx
0x140023f56  mov     rax, [rbp+arg_20]
0x140023f5a  cmp     [rbx], rdx
0x140023f5d  jnz     short loc_140023F63
0x140023f5f  lea     rax, [rdi+78h]
0x140023f63  mov     r9, [rbp+arg_18]
0x140023f67  lea     rcx, [rbp+arg_0]
0x140023f6b  mov     rdx, [rbp+Instance]
0x140023f6f  mov     r8, r13
0x140023f72  mov     [rsp+78h+var_48], rcx
0x140023f77  mov     rcx, r15
0x140023f7a  mov     dword ptr [rsp+78h+var_50], r12d
0x140023f7f  mov     qword ptr [rsp+78h+var_58], rax
0x140023f84  call    PrjfSendPostCreateNotifications
0x140023f89  mov     ebx, eax
0x140023f8b  test    eax, eax
0x140023f8d  jns     short loc_140024007
0x140023f8f  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140023f95  lea     rax, WPP_RECORDER_INITIALIZED
0x140023f9c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023fa3  setnz   r8b
0x140023fa7  and     dl, 20h
0x140023faa  jnz     short loc_140023FB5
0x140023fac  test    r8b, r8b
0x140023faf  jz      loc_140024142
0x140023fb5  mov     r9, cs:WPP_GLOBAL_Control
0x140023fbc  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023fc3  mov     [rsp+78h+var_28], ebx
0x140023fc7  mov     ecx, 205h
0x140023fcc  mov     [rsp+78h+var_30], 1BCh
0x140023fd4  mov     [rsp+78h+var_38], rax
0x140023fd9  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023fe0  mov     r9, [r9+40h]
0x140023fe4  mov     qword ptr [rsp+78h+var_40], rax
0x140023fe9  mov     word ptr [rsp+78h+var_48], 10h
0x140023ff0  mov     dword ptr [rsp+78h+var_50], 5
0x140023ff8  mov     [rsp+78h+var_58], 2
0x140023ffd  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140024002  jmp     loc_140024142
0x140024007  cmp     [rbp+arg_0], 0FFFFFFFFh
0x14002400b  jnz     short loc_140024011
0x14002400d  mov     [rbp+arg_0], r12d
0x140024011  lea     r12, [rdi+8]
0x140024015  mov     rcx, r12; FastMutex
0x140024018  call    cs:__imp_ExAcquireFastMutex
0x14002401f  nop     dword ptr [rax+rax+00h]
0x140024024  mov     eax, [rbp+arg_0]
0x140024027  mov     rcx, r12; FastMutex
0x14002402a  mov     [rsi+28h], eax
0x14002402d  call    cs:__imp_ExReleaseFastMutex
0x140024034  nop     dword ptr [rax+rax+00h]
0x140024039  mov     eax, [rsi]
0x14002403b  mov     ecx, 1
0x140024040  cmp     eax, ecx
0x140024042  jnz     short loc_140024050
0x140024044  test    [rbp+arg_10], 106h
0x14002404b  jmp     loc_140024129
0x140024050  test    eax, eax
0x140024052  jnz     loc_140024122
0x140024058  mov     rax, [r15+20h]
0x14002405c  cmp     rax, 3
0x140024060  jz      loc_140024110
0x140024066  test    rax, rax
0x140024069  jz      loc_140024110
0x14002406f  test    byte ptr [rbp+arg_10], 6
0x140024073  jz      short loc_1400240A5
0x140024075  mov     [rsp+78h+var_40], 0; char
0x14002407a  mov     dword ptr [rsp+78h+var_48], 10h; int
0x140024082  mov     rdx, [rbp+Instance]
0x140024086  mov     r9, rdi
0x140024089  mov     dword ptr [rsp+78h+var_50], ecx; int
0x14002408d  mov     r8, r13
0x140024090  mov     rcx, r15; CallbackData
0x140024093  mov     dword ptr [rsp+78h+var_58], 3; int
0x14002409b  call    PrjfExpandAndWait
0x1400240a0  jmp     loc_140024140
0x1400240a5  mov     rcx, r12; FastMutex
0x1400240a8  call    cs:__imp_ExAcquireFastMutex
0x1400240af  nop     dword ptr [rax+rax+00h]
0x1400240b4  cmp     dword ptr [rdi+40h], 3
0x1400240b8  jz      short loc_1400240F8
0x1400240ba  mov     cl, [r14+6]
0x1400240be  test    cl, 4
0x1400240c1  jz      short loc_1400240F8
0x1400240c3  test    byte ptr [r14+4], 40h
0x1400240c8  jz      short loc_1400240F1
0x1400240ca  mov     rcx, [r14+30h]; FastMutex
0x1400240ce  call    cs:__imp_ExAcquireFastMutex
0x1400240d5  nop     dword ptr [rax+rax+00h]
0x1400240da  mov     rcx, [r14+30h]; FastMutex
0x1400240de  and     byte ptr [r14+6], 0FBh
0x1400240e3  call    cs:__imp_ExReleaseFastMutex
0x1400240ea  nop     dword ptr [rax+rax+00h]
0x1400240ef  jmp     short loc_1400240F8
0x1400240f1  and     cl, 0FBh
0x1400240f4  mov     [r14+6], cl
0x1400240f8  mov     rcx, r12; FastMutex
0x1400240fb  call    cs:__imp_ExReleaseFastMutex
0x140024102  nop     dword ptr [rax+rax+00h]
0x140024107  test    [rbp+arg_10], 100h
0x14002410e  jmp     short loc_140024129
0x140024110  mov     [rsp+78h+var_40], 0
0x140024115  mov     dword ptr [rsp+78h+var_48], 13h
0x14002411d  jmp     loc_140024082
0x140024122  test    [rbp+arg_10], 116h
0x140024129  jz      short loc_140024142
0x14002412b  mov     rdx, [rbp+Instance]; Instance
0x14002412f  mov     r9d, 2
0x140024135  mov     r8, r13; FileObject
0x140024138  mov     rcx, r15; CallbackData
0x14002413b  call    PrjfSetPlaceHolderFlagsSynchronized
0x140024140  mov     ebx, eax
0x140024142  test    rdi, rdi
0x140024145  jz      short loc_140024156
0x140024147  mov     rcx, rdi; Context
0x14002414a  call    cs:__imp_FltReleaseContext
0x140024151  nop     dword ptr [rax+rax+00h]
0x140024156  test    rsi, rsi
0x140024159  jz      short loc_14002416A
0x14002415b  mov     rcx, rsi; Context
0x14002415e  call    cs:__imp_FltReleaseContext
0x140024165  nop     dword ptr [rax+rax+00h]
0x14002416a  mov     eax, ebx
0x14002416c  add     rsp, 78h
0x140024170  pop     r15
0x140024172  pop     r14
0x140024174  pop     r13
0x140024176  pop     r12
0x140024178  pop     rdi
0x140024179  pop     rsi
0x14002417a  pop     rbx
0x14002417b  pop     rbp
0x14002417c  retn
```
