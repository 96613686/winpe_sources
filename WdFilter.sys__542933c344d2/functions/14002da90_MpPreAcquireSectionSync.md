# MpPreAcquireSectionSync

- ea: `0x14002da90`
- end: `0x14002de5f`
- name: `MpPreAcquireSectionSync`
- size: `975`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140003d20`
- `0x140005e78`
- `0x140009bf0`
- `0x1400118d0`
- `0x14002d520`
- `0x14002da90`
- `0x14002de60`
- `0x14003f700`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14002db38`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14002db38`
- `ntoskrnl!IoThreadToProcess` at `0x14002dbe6`
- `ntoskrnl!IoThreadToProcess` at `0x14002dc0e`
- `ntoskrnl!IoThreadToProcess` at `0x14002dbe6`
- `ntoskrnl!IoThreadToProcess` at `0x14002dc0e`
- `FLTMGR!FltReleaseContext` at `0x14002dc49`
- `FLTMGR!FltReleaseContext` at `0x14002dcbc`
- `FLTMGR!FltReleaseContext` at `0x14002dd64`
- `FLTMGR!FltReleaseContext` at `0x14002de4e`
- `FLTMGR!FltReleaseContext` at `0x14002dc49`
- `FLTMGR!FltReleaseContext` at `0x14002dcbc`
- `FLTMGR!FltReleaseContext` at `0x14002dd64`
- `FLTMGR!FltReleaseContext` at `0x14002de4e`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002dd40`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002dd40`
- `FLTMGR!FltGetStreamContext` at `0x14002db8f`
- `FLTMGR!FltGetStreamContext` at `0x14002db8f`
- `FLTMGR!FltSupportsStreamContexts` at `0x14002dacc`
- `FLTMGR!FltSupportsStreamContexts` at `0x14002dacc`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14002dae4`
- `FLTMGR!FltSupportsStreamHandleContexts` at `0x14002dae4`

## pseudocode

```c
__int64 __fastcall MpPreAcquireSectionSync(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PIRP TopLevelIrp; // rcx
  struct _KPROCESS *v6; // rdi
  struct _KPROCESS *v7; // rdi
  PFLT_CONTEXT v8; // rcx
  struct _FILE_OBJECT *v10; // rdx
  struct _FLT_INSTANCE *v11; // rcx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-38h] BYREF
  PFLT_CONTEXT v13; // [rsp+38h] [rbp-30h] BYREF

  Iopb = CallbackData->Iopb;
  Context = 0;
  if ( Iopb->Parameters.Read.Length != 1 || !FltSupportsStreamContexts(*(PFILE_OBJECT *)(a2 + 32)) )
    return 1;
  if ( FltSupportsStreamHandleContexts(*(PFILE_OBJECT *)(a2 + 32))
    && (!*(_BYTE *)(MpData + 3632) || _InterlockedCompareExchange64((volatile signed __int64 *)(MpData + 3640), 0, 0)) )
  {
    v10 = *(struct _FILE_OBJECT **)(a2 + 32);
    v11 = *(struct _FLT_INSTANCE **)(a2 + 24);
    v13 = 0;
    if ( FltGetStreamHandleContext(v11, v10, &v13) >= 0 )
    {
      v8 = v13;
      if ( (*((_DWORD *)v13 + 10) & 4) != 0 )
        goto LABEL_18;
      FltReleaseContext(v13);
    }
  }
  if ( (unsigned int)MpPreSectionSyncPPLReduxCallback(CallbackData, (_QWORD *)a2) != 1835009 )
  {
    TopLevelIrp = IoGetTopLevelIrp();
    if ( TopLevelIrp )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          (unsigned int)WPP_a67f6715d69b338c18208b3d25efa3ca_Traceguids,
          CallbackData->Thread,
          (__int64)TopLevelIrp);
    }
    else if ( (unsigned int)MpScanOnPreUserModeReadCopySourceFile(CallbackData, a2, &Context, 0, 1) == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_a67f6715d69b338c18208b3d25efa3ca_Traceguids,
          CallbackData->Thread);
      if ( Context )
        FltReleaseContext(Context);
      return 4;
    }
    if ( !Context )
    {
      FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
      if ( !Context )
        return 1;
    }
    if ( *((_BYTE *)MpDlpData + 32)
      && (*((_DWORD *)Context + 12) & 0x10000) != 0
      && (*((_BYTE *)MpDlpData + 268) || (*((_DWORD *)Context + 12) & 0x600000) != 0)
      && (unsigned int)MpDlpPreAcquireSectionSync(CallbackData, a2, (__int64)Context) == 2 )
    {
      if ( Context )
        FltReleaseContext(Context);
      if ( CallbackData->IoStatus.Status >= 0 )
        CallbackData->IoStatus.Status = dword_140026538;
      return 4;
    }
    v6 = *(struct _KPROCESS **)(MpData + 232);
    if ( IoThreadToProcess(KeGetCurrentThread()) != v6 )
    {
      v7 = *(struct _KPROCESS **)(MpData + 256);
      if ( IoThreadToProcess(KeGetCurrentThread()) != v7 )
        _InterlockedOr((volatile signed __int32 *)Context + 12, 0x800u);
    }
    if ( (CallbackData->Iopb->Parameters.AcquireForSectionSynchronization.PageProtection & 0x44) != 0 )
    {
      _InterlockedOr((volatile signed __int32 *)Context + 12, 0x20u);
      if ( (*(_DWORD *)(MpData + 864) & 0x40) != 0 && (*(_BYTE *)(*((_QWORD *)Context + 1) + 88LL) & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_a67f6715d69b338c18208b3d25efa3ca_Traceguids,
            *(_QWORD *)(a2 + 32) + 88LL);
        _InterlockedOr((volatile signed __int32 *)Context + 12, 0x100000u);
        *((_DWORD *)Context + 8) = 0;
        _InterlockedAnd((volatile signed __int32 *)Context + 12, 0xFFFFBFFF);
        _InterlockedOr((volatile signed __int32 *)Context + 12, 0x108u);
      }
    }
    v8 = Context;
LABEL_18:
    FltReleaseContext(v8);
    return 1;
  }
  return 4;
}

```

## disassembly

```asm
0x14002da90  mov     [rsp+arg_18], rbx
0x14002da95  push    rbp
0x14002da96  push    rsi
0x14002da97  push    r14
0x14002da99  sub     rsp, 50h
0x14002da9d  mov     rax, cs:__security_cookie
0x14002daa4  xor     rax, rsp
0x14002daa7  mov     [rsp+68h+var_28], rax
0x14002daac  mov     rax, [rcx+10h]
0x14002dab0  xor     r14d, r14d
0x14002dab3  mov     [rsp+68h+Context], r14
0x14002dab8  mov     rsi, rdx
0x14002dabb  mov     rbx, rcx
0x14002dabe  cmp     dword ptr [rax+18h], 1
0x14002dac2  jnz     loc_14002DC55
0x14002dac8  mov     rcx, [rdx+20h]; FileObject
0x14002dacc  call    cs:__imp_FltSupportsStreamContexts
0x14002dad3  nop     dword ptr [rax+rax+00h]
0x14002dad8  test    al, al
0x14002dada  jz      loc_14002DC55
0x14002dae0  mov     rcx, [rsi+20h]; FileObject
0x14002dae4  call    cs:__imp_FltSupportsStreamHandleContexts
0x14002daeb  nop     dword ptr [rax+rax+00h]
0x14002daf0  test    al, al
0x14002daf2  jz      short loc_14002DB22
0x14002daf4  mov     rax, cs:MpData
0x14002dafb  movzx   ecx, byte ptr [rax+0E30h]
0x14002db02  test    cl, cl
0x14002db04  jz      loc_14002DD2E
0x14002db0a  mov     rcx, cs:MpData
0x14002db11  xor     eax, eax
0x14002db13  lock cmpxchg [rcx+0E38h], r14
0x14002db1c  jnz     loc_14002DD2E
0x14002db22  mov     rdx, rsi
0x14002db25  mov     rcx, rbx; CallbackData
0x14002db28  call    MpPreSectionSyncPPLReduxCallback
0x14002db2d  cmp     eax, 1C0001h
0x14002db32  jz      loc_14002DCD7
0x14002db38  call    cs:__imp_IoGetTopLevelIrp
0x14002db3f  nop     dword ptr [rax+rax+00h]
0x14002db44  lea     rbp, WPP_GLOBAL_Control
0x14002db4b  mov     rcx, rax
0x14002db4e  test    rax, rax
0x14002db51  jnz     loc_14002DCE1
0x14002db57  xor     r9d, r9d
0x14002db5a  mov     dword ptr [rsp+68h+var_48], 1
0x14002db62  lea     r8, [rsp+68h+Context]
0x14002db67  mov     rdx, rsi
0x14002db6a  mov     rcx, rbx
0x14002db6d  call    MpScanOnPreUserModeReadCopySourceFile
0x14002db72  cmp     eax, 1
0x14002db75  jz      loc_14002DE0D
0x14002db7b  cmp     [rsp+68h+Context], r14
0x14002db80  jnz     short loc_14002DBA6
0x14002db82  mov     rdx, [rsi+20h]; FileObject
0x14002db86  lea     r8, [rsp+68h+Context]; Context
0x14002db8b  mov     rcx, [rsi+18h]; Instance
0x14002db8f  call    cs:__imp_FltGetStreamContext
0x14002db96  nop     dword ptr [rax+rax+00h]
0x14002db9b  cmp     [rsp+68h+Context], r14
0x14002dba0  jz      loc_14002DC55
0x14002dba6  mov     rax, cs:MpDlpData
0x14002dbad  movzx   ecx, byte ptr [rax+20h]
0x14002dbb1  test    cl, cl
0x14002dbb3  jz      short loc_14002DBC7
0x14002dbb5  mov     rax, [rsp+68h+Context]
0x14002dbba  test    dword ptr [rax+30h], 10000h
0x14002dbc1  jnz     loc_14002DC79
0x14002dbc7  mov     rcx, gs:188h; Thread
0x14002dbd0  mov     rax, cs:MpData
0x14002dbd7  mov     [rsp+68h+arg_10], rdi
0x14002dbdf  mov     rdi, [rax+0E8h]
0x14002dbe6  call    cs:__imp_IoThreadToProcess
0x14002dbed  nop     dword ptr [rax+rax+00h]
0x14002dbf2  cmp     rax, rdi
0x14002dbf5  jz      short loc_14002DC2C
0x14002dbf7  mov     rcx, gs:188h; Thread
0x14002dc00  mov     rax, cs:MpData
0x14002dc07  mov     rdi, [rax+100h]
0x14002dc0e  call    cs:__imp_IoThreadToProcess
0x14002dc15  nop     dword ptr [rax+rax+00h]
0x14002dc1a  cmp     rax, rdi
0x14002dc1d  jz      short loc_14002DC2C
0x14002dc1f  mov     rcx, [rsp+68h+Context]
0x14002dc24  lock or dword ptr [rcx+30h], 800h
0x14002dc2c  mov     rcx, [rbx+10h]
0x14002dc30  mov     rdi, [rsp+68h+arg_10]
0x14002dc38  mov     edx, [rcx+1Ch]
0x14002dc3b  test    dl, 44h
0x14002dc3e  jnz     loc_14002DD75
0x14002dc44  mov     rcx, [rsp+68h+Context]; Context
0x14002dc49  call    cs:__imp_FltReleaseContext
0x14002dc50  nop     dword ptr [rax+rax+00h]
0x14002dc55  mov     eax, 1
0x14002dc5a  mov     rcx, [rsp+68h+var_28]
0x14002dc5f  xor     rcx, rsp; StackCookie
0x14002dc62  call    __security_check_cookie
0x14002dc67  mov     rbx, [rsp+68h+arg_18]
0x14002dc6f  add     rsp, 50h
0x14002dc73  pop     r14
0x14002dc75  pop     rsi
0x14002dc76  pop     rbp
0x14002dc77  retn
0x14002dc79  mov     rax, cs:MpDlpData
0x14002dc80  movzx   ecx, byte ptr [rax+10Ch]
0x14002dc87  mov     r8, [rsp+68h+Context]
0x14002dc8c  test    cl, cl
0x14002dc8e  jnz     short loc_14002DC9E
0x14002dc90  test    dword ptr [r8+30h], 600000h
0x14002dc98  jz      loc_14002DBC7
0x14002dc9e  mov     rdx, rsi
0x14002dca1  mov     rcx, rbx; CallbackData
0x14002dca4  call    MpDlpPreAcquireSectionSync
0x14002dca9  cmp     eax, 2
0x14002dcac  jnz     loc_14002DBC7
0x14002dcb2  mov     rcx, [rsp+68h+Context]; Context
0x14002dcb7  test    rcx, rcx
0x14002dcba  jz      short loc_14002DCC8
0x14002dcbc  call    cs:__imp_FltReleaseContext
0x14002dcc3  nop     dword ptr [rax+rax+00h]
0x14002dcc8  cmp     [rbx+18h], r14d
0x14002dccc  jl      short loc_14002DCD7
0x14002dcce  mov     eax, cs:dword_140026538
0x14002dcd4  mov     [rbx+18h], eax
0x14002dcd7  mov     eax, 4
0x14002dcdc  jmp     loc_14002DC5A
0x14002dce1  mov     r10, cs:WPP_GLOBAL_Control
0x14002dce8  cmp     r10, rbp
0x14002dceb  jz      loc_14002DB7B
0x14002dcf1  mov     eax, [r10+2Ch]
0x14002dcf5  test    al, 4
0x14002dcf7  jz      loc_14002DB7B
0x14002dcfd  mov     rax, [rbx+10h]
0x14002dd01  mov     edx, 0Bh
0x14002dd06  mov     r9, [rbx+8]
0x14002dd0a  movzx   r8d, byte ptr [rax+4]
0x14002dd0f  mov     [rsp+68h+var_40], r8d
0x14002dd14  lea     r8, WPP_a67f6715d69b338c18208b3d25efa3ca_Traceguids
0x14002dd1b  mov     [rsp+68h+var_48], rcx
0x14002dd20  mov     rcx, [r10+18h]
0x14002dd24  call    WPP_SF_qqD
0x14002dd29  jmp     loc_14002DB7B
0x14002dd2e  mov     rdx, [rsi+20h]; FileObject
0x14002dd32  lea     r8, [rsp+68h+var_30]; Context
0x14002dd37  mov     rcx, [rsi+18h]; Instance
0x14002dd3b  mov     [rsp+68h+var_30], r14
0x14002dd40  call    cs:__imp_FltGetStreamHandleContext
0x14002dd47  nop     dword ptr [rax+rax+00h]
0x14002dd4c  test    eax, eax
0x14002dd4e  js      loc_14002DB22
0x14002dd54  mov     rcx, [rsp+68h+var_30]; Context
0x14002dd59  mov     eax, [rcx+28h]
0x14002dd5c  test    al, 4
0x14002dd5e  jnz     loc_14002DC49
0x14002dd64  call    cs:__imp_FltReleaseContext
0x14002dd6b  nop     dword ptr [rax+rax+00h]
0x14002dd70  jmp     loc_14002DB22
0x14002dd75  mov     rax, [rsp+68h+Context]
0x14002dd7a  lock or dword ptr [rax+30h], 20h
0x14002dd7f  mov     rax, cs:MpData
0x14002dd86  mov     ecx, [rax+360h]
0x14002dd8c  test    cl, 40h
0x14002dd8f  jz      loc_14002DC44
0x14002dd95  mov     rax, [rsp+68h+Context]
0x14002dd9a  mov     rcx, [rax+8]
0x14002dd9e  test    byte ptr [rcx+58h], 1
0x14002dda2  jz      loc_14002DC44
0x14002dda8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ddaf  cmp     rcx, rbp
0x14002ddb2  jz      short loc_14002DDD8
0x14002ddb4  mov     eax, [rcx+2Ch]
0x14002ddb7  test    al, 4
0x14002ddb9  jz      short loc_14002DDD8
0x14002ddbb  mov     r9, [rsi+20h]
0x14002ddbf  lea     r8, WPP_a67f6715d69b338c18208b3d25efa3ca_Traceguids
0x14002ddc6  mov     rcx, [rcx+18h]
0x14002ddca  add     r9, 58h ; 'X'
0x14002ddce  mov     edx, 0Ch
0x14002ddd3  call    WPP_SF_Z
0x14002ddd8  mov     rax, [rsp+68h+Context]
0x14002dddd  lock or dword ptr [rax+30h], 100000h
0x14002dde5  mov     rax, [rsp+68h+Context]
0x14002ddea  mov     [rax+20h], r14d
0x14002ddee  mov     rax, [rsp+68h+Context]
0x14002ddf3  lock and dword ptr [rax+30h], 0FFFFBFFFh
0x14002ddfb  mov     rax, [rsp+68h+Context]
0x14002de00  lock or dword ptr [rax+30h], 108h
0x14002de08  jmp     loc_14002DC44
0x14002de0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002de14  lea     rbp, WPP_GLOBAL_Control
0x14002de1b  cmp     rcx, rbp
0x14002de1e  jz      short loc_14002DE40
0x14002de20  mov     eax, [rcx+2Ch]
0x14002de23  test    al, 2
0x14002de25  jz      short loc_14002DE40
0x14002de27  mov     r9, [rbx+8]
0x14002de2b  lea     r8, WPP_a67f6715d69b338c18208b3d25efa3ca_Traceguids
0x14002de32  mov     rcx, [rcx+18h]
0x14002de36  mov     edx, 0Ah
0x14002de3b  call    WPP_SF_q
0x14002de40  mov     rcx, [rsp+68h+Context]; Context
0x14002de45  test    rcx, rcx
0x14002de48  jz      loc_14002DCD7
0x14002de4e  call    cs:__imp_FltReleaseContext
0x14002de55  nop     dword ptr [rax+rax+00h]
0x14002de5a  jmp     loc_14002DCD7
```
