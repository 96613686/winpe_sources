# AfdTlNotifyAttachProvider

- ea: `0x14005dcb0`
- end: `0x14005dea5`
- name: `AfdTlNotifyAttachProvider`
- size: `501`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400402c4`
- `0x14005dcb0`
- `0x14005eb74`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005de82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005de82`
- `ntoskrnl!ExAllocatePool2` at `0x14005dd82`
- `ntoskrnl!ExAllocatePool2` at `0x14005dd82`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005dd17`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005de19`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005dd17`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005de19`
- `NDIS!NdisReleaseRWLock` at `0x14005dd39`
- `NDIS!NdisReleaseRWLock` at `0x14005dd65`
- `NDIS!NdisReleaseRWLock` at `0x14005de6a`
- `NDIS!NdisReleaseRWLock` at `0x14005dd39`
- `NDIS!NdisReleaseRWLock` at `0x14005dd65`
- `NDIS!NdisReleaseRWLock` at `0x14005de6a`
- `NETIO!NmrClientAttachProvider` at `0x14005ddf8`
- `NETIO!NmrClientAttachProvider` at `0x14005ddf8`

## pseudocode

```c
__int64 __fastcall AfdTlNotifyAttachProvider(HANDLE NmrBindingHandle, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  char v6; // di
  __int64 Pool2; // rax
  _QWORD *v9; // rbx
  NTSTATUS v10; // esi
  _QWORD *v11; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+18h] BYREF

  v3 = *(_QWORD *)(a3 + 32);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( !v3 )
    return 3221226169LL;
  v6 = 0;
  if ( *(_WORD *)v3 && *(_BYTE *)(v3 + 12) == 1 )
  {
    if ( !NmrIsEqualNpiModuleId(*(PNPI_MODULEID *)(a3 + 16), &NPI_MS_FLRDMA_MODULEID) )
      return 3221226169LL;
    NdisAcquireRWLockWrite(AfdTlTransportLock, &LockState, 0);
    if ( AfdNdkTransport )
    {
      NdisReleaseRWLock(AfdTlTransportLock, &LockState);
      return 3221226169LL;
    }
    AfdNdkTransport = 1;
    NdisReleaseRWLock(AfdTlTransportLock, &LockState);
    v6 = 1;
  }
  Pool2 = ExAllocatePool2(64, 80, 1413760609);
  v9 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 64) = NmrBindingHandle;
    *(_DWORD *)(Pool2 + 16) = 2;
    *(_WORD *)(Pool2 + 20) = *(_WORD *)v3;
    *(_WORD *)(Pool2 + 22) = *(_WORD *)(v3 + 4);
    *(_DWORD *)(Pool2 + 24) = *(_DWORD *)(v3 + 8);
    *(_WORD *)(Pool2 + 28) = *(_WORD *)(v3 + 2);
    *(_OWORD *)(Pool2 + 48) = *(_OWORD *)(*(_QWORD *)(a3 + 16) + 8LL);
    v10 = NmrClientAttachProvider(
            NmrBindingHandle,
            (PVOID)Pool2,
            &AfdTlClientDispatch,
            (PVOID *)(Pool2 + 32),
            (const void **)(Pool2 + 40));
    if ( v10 < 0 )
    {
      ExFreePoolWithTag(v9, 0);
      if ( v6 )
        AfdNdkTransport = 0;
    }
    else
    {
      NdisAcquireRWLockWrite(AfdTlTransportLock, &LockState, 0);
      if ( v6 )
      {
        AfdNdkTransport = (__int64)v9;
      }
      else
      {
        v11 = (_QWORD *)qword_140087C58;
        if ( *(__int64 **)qword_140087C58 != &AfdTlTransportListHead )
          __fastfail(3u);
        *v9 = &AfdTlTransportListHead;
        v9[1] = v11;
        *v11 = v9;
        qword_140087C58 = (__int64)v9;
      }
      NdisReleaseRWLock(AfdTlTransportLock, &LockState);
      AfdWskProcessTransportChangeList();
    }
    return (unsigned int)v10;
  }
  else
  {
    if ( v6 )
      AfdNdkTransport = 0;
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14005dcb0  mov     [rsp+arg_0], rbx
0x14005dcb5  mov     [rsp+arg_8], rbp
0x14005dcba  push    rsi
0x14005dcbb  push    rdi
0x14005dcbc  push    r14
0x14005dcbe  sub     rsp, 30h
0x14005dcc2  mov     rsi, [r8+20h]
0x14005dcc6  xor     eax, eax
0x14005dcc8  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14005dccd  mov     rbp, r8
0x14005dcd0  mov     [rsp+48h+LockState.Flags], al
0x14005dcd4  mov     r14, rcx
0x14005dcd7  test    rsi, rsi
0x14005dcda  jz      short loc_14005DD45
0x14005dcdc  xor     dil, dil
0x14005dcdf  lea     ebx, [rax+1]
0x14005dce2  cmp     [rsi], bx
0x14005dce5  jb      loc_14005DD74
0x14005dceb  cmp     [rsi+0Ch], bl
0x14005dcee  jnz     loc_14005DD74
0x14005dcf4  mov     rcx, [r8+10h]; ModuleId1
0x14005dcf8  lea     rdx, NPI_MS_FLRDMA_MODULEID; ModuleId2
0x14005dcff  call    NmrIsEqualNpiModuleId
0x14005dd04  test    al, al
0x14005dd06  jz      short loc_14005DD45
0x14005dd08  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005dd0f  lea     rdx, [rsp+48h+LockState]; LockState
0x14005dd14  xor     r8d, r8d; Flags
0x14005dd17  call    cs:__imp_NdisAcquireRWLockWrite
0x14005dd1e  nop     dword ptr [rax+rax+00h]
0x14005dd23  cmp     cs:AfdNdkTransport, 0
0x14005dd2b  lea     rdx, [rsp+48h+LockState]; LockState
0x14005dd30  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005dd37  jz      short loc_14005DD5E
0x14005dd39  call    cs:__imp_NdisReleaseRWLock
0x14005dd40  nop     dword ptr [rax+rax+00h]
0x14005dd45  mov     eax, 0C00002B9h
0x14005dd4a  mov     rbx, [rsp+48h+arg_0]
0x14005dd4f  mov     rbp, [rsp+48h+arg_8]
0x14005dd54  add     rsp, 30h
0x14005dd58  pop     r14
0x14005dd5a  pop     rdi
0x14005dd5b  pop     rsi
0x14005dd5c  retn
0x14005dd5e  mov     cs:AfdNdkTransport, rbx
0x14005dd65  call    cs:__imp_NdisReleaseRWLock
0x14005dd6c  nop     dword ptr [rax+rax+00h]
0x14005dd71  mov     dil, bl
0x14005dd74  mov     edx, 50h ; 'P'
0x14005dd79  mov     r8d, 54444661h
0x14005dd7f  lea     ecx, [rdx-10h]
0x14005dd82  call    cs:__imp_ExAllocatePool2
0x14005dd89  nop     dword ptr [rax+rax+00h]
0x14005dd8e  mov     rbx, rax
0x14005dd91  test    rax, rax
0x14005dd94  jnz     short loc_14005DDA9
0x14005dd96  test    dil, dil
0x14005dd99  jz      short loc_14005DDA2
0x14005dd9b  mov     cs:AfdNdkTransport, rax
0x14005dda2  mov     eax, 0C000009Ah
0x14005dda7  jmp     short loc_14005DD4A
0x14005dda9  mov     [rax+40h], r14
0x14005ddad  lea     r9, [rbx+20h]; ProviderBindingContext
0x14005ddb1  mov     dword ptr [rax+10h], 2
0x14005ddb8  lea     r8, AfdTlClientDispatch; ClientDispatch
0x14005ddbf  movzx   eax, word ptr [rsi]
0x14005ddc2  mov     rdx, rbx; ClientBindingContext
0x14005ddc5  mov     [rbx+14h], ax
0x14005ddc9  mov     rcx, r14; NmrBindingHandle
0x14005ddcc  movzx   eax, word ptr [rsi+4]
0x14005ddd0  mov     [rbx+16h], ax
0x14005ddd4  mov     eax, [rsi+8]
0x14005ddd7  mov     [rbx+18h], eax
0x14005ddda  movzx   eax, word ptr [rsi+2]
0x14005ddde  mov     [rbx+1Ch], ax
0x14005dde2  mov     rax, [rbp+10h]
0x14005dde6  movups  xmm0, xmmword ptr [rax+8]
0x14005ddea  lea     rax, [rbx+28h]
0x14005ddee  mov     [rsp+48h+ProviderDispatch], rax; ProviderDispatch
0x14005ddf3  movdqu  xmmword ptr [rbx+30h], xmm0
0x14005ddf8  call    cs:__imp_NmrClientAttachProvider
0x14005ddff  nop     dword ptr [rax+rax+00h]
0x14005de04  mov     esi, eax
0x14005de06  test    eax, eax
0x14005de08  js      short loc_14005DE7D
0x14005de0a  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005de11  lea     rdx, [rsp+48h+LockState]; LockState
0x14005de16  xor     r8d, r8d; Flags
0x14005de19  call    cs:__imp_NdisAcquireRWLockWrite
0x14005de20  nop     dword ptr [rax+rax+00h]
0x14005de25  test    dil, dil
0x14005de28  jz      short loc_14005DE33
0x14005de2a  mov     cs:AfdNdkTransport, rbx
0x14005de31  jmp     short loc_14005DE5E
0x14005de33  mov     rax, cs:qword_140087C58
0x14005de3a  lea     rcx, AfdTlTransportListHead
0x14005de41  cmp     [rax], rcx
0x14005de44  jz      short loc_14005DE4D
0x14005de46  mov     ecx, 3
0x14005de4b  int     29h; Win8: RtlFailFast(ecx)
0x14005de4d  mov     [rbx], rcx
0x14005de50  mov     [rbx+8], rax
0x14005de54  mov     [rax], rbx
0x14005de57  mov     cs:qword_140087C58, rbx
0x14005de5e  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005de65  lea     rdx, [rsp+48h+LockState]; LockState
0x14005de6a  call    cs:__imp_NdisReleaseRWLock
0x14005de71  nop     dword ptr [rax+rax+00h]
0x14005de76  call    AfdWskProcessTransportChangeList
0x14005de7b  jmp     short loc_14005DE9E
0x14005de7d  xor     edx, edx; Tag
0x14005de7f  mov     rcx, rbx; P
0x14005de82  call    cs:__imp_ExFreePoolWithTag
0x14005de89  nop     dword ptr [rax+rax+00h]
0x14005de8e  test    dil, dil
0x14005de91  jz      short loc_14005DE9E
0x14005de93  mov     cs:AfdNdkTransport, 0
0x14005de9e  mov     eax, esi
0x14005dea0  jmp     loc_14005DD4A
```
