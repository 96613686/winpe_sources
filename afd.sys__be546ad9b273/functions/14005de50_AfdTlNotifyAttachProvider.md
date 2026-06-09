# AfdTlNotifyAttachProvider

- ea: `0x14005de50`
- end: `0x14005e045`
- name: `AfdTlNotifyAttachProvider`
- size: `501`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1400402e4`
- `0x14005de50`
- `0x14005ed14`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005e022`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e022`
- `ntoskrnl!ExAllocatePool2` at `0x14005df22`
- `ntoskrnl!ExAllocatePool2` at `0x14005df22`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005deb7`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005dfb9`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005deb7`
- `NDIS!NdisAcquireRWLockWrite` at `0x14005dfb9`
- `NDIS!NdisReleaseRWLock` at `0x14005ded9`
- `NDIS!NdisReleaseRWLock` at `0x14005df05`
- `NDIS!NdisReleaseRWLock` at `0x14005e00a`
- `NDIS!NdisReleaseRWLock` at `0x14005ded9`
- `NDIS!NdisReleaseRWLock` at `0x14005df05`
- `NDIS!NdisReleaseRWLock` at `0x14005e00a`
- `NETIO!NmrClientAttachProvider` at `0x14005df98`
- `NETIO!NmrClientAttachProvider` at `0x14005df98`

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
0x14005de50  mov     [rsp+arg_0], rbx
0x14005de55  mov     [rsp+arg_8], rbp
0x14005de5a  push    rsi
0x14005de5b  push    rdi
0x14005de5c  push    r14
0x14005de5e  sub     rsp, 30h
0x14005de62  mov     rsi, [r8+20h]
0x14005de66  xor     eax, eax
0x14005de68  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14005de6d  mov     rbp, r8
0x14005de70  mov     [rsp+48h+LockState.Flags], al
0x14005de74  mov     r14, rcx
0x14005de77  test    rsi, rsi
0x14005de7a  jz      short loc_14005DEE5
0x14005de7c  xor     dil, dil
0x14005de7f  lea     ebx, [rax+1]
0x14005de82  cmp     [rsi], bx
0x14005de85  jb      loc_14005DF14
0x14005de8b  cmp     [rsi+0Ch], bl
0x14005de8e  jnz     loc_14005DF14
0x14005de94  mov     rcx, [r8+10h]; ModuleId1
0x14005de98  lea     rdx, NPI_MS_FLRDMA_MODULEID; ModuleId2
0x14005de9f  call    NmrIsEqualNpiModuleId
0x14005dea4  test    al, al
0x14005dea6  jz      short loc_14005DEE5
0x14005dea8  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005deaf  lea     rdx, [rsp+48h+LockState]; LockState
0x14005deb4  xor     r8d, r8d; Flags
0x14005deb7  call    cs:__imp_NdisAcquireRWLockWrite
0x14005debe  nop     dword ptr [rax+rax+00h]
0x14005dec3  cmp     cs:AfdNdkTransport, 0
0x14005decb  lea     rdx, [rsp+48h+LockState]; LockState
0x14005ded0  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005ded7  jz      short loc_14005DEFE
0x14005ded9  call    cs:__imp_NdisReleaseRWLock
0x14005dee0  nop     dword ptr [rax+rax+00h]
0x14005dee5  mov     eax, 0C00002B9h
0x14005deea  mov     rbx, [rsp+48h+arg_0]
0x14005deef  mov     rbp, [rsp+48h+arg_8]
0x14005def4  add     rsp, 30h
0x14005def8  pop     r14
0x14005defa  pop     rdi
0x14005defb  pop     rsi
0x14005defc  retn
0x14005defe  mov     cs:AfdNdkTransport, rbx
0x14005df05  call    cs:__imp_NdisReleaseRWLock
0x14005df0c  nop     dword ptr [rax+rax+00h]
0x14005df11  mov     dil, bl
0x14005df14  mov     edx, 50h ; 'P'
0x14005df19  mov     r8d, 54444661h
0x14005df1f  lea     ecx, [rdx-10h]
0x14005df22  call    cs:__imp_ExAllocatePool2
0x14005df29  nop     dword ptr [rax+rax+00h]
0x14005df2e  mov     rbx, rax
0x14005df31  test    rax, rax
0x14005df34  jnz     short loc_14005DF49
0x14005df36  test    dil, dil
0x14005df39  jz      short loc_14005DF42
0x14005df3b  mov     cs:AfdNdkTransport, rax
0x14005df42  mov     eax, 0C000009Ah
0x14005df47  jmp     short loc_14005DEEA
0x14005df49  mov     [rax+40h], r14
0x14005df4d  lea     r9, [rbx+20h]; ProviderBindingContext
0x14005df51  mov     dword ptr [rax+10h], 2
0x14005df58  lea     r8, AfdTlClientDispatch; ClientDispatch
0x14005df5f  movzx   eax, word ptr [rsi]
0x14005df62  mov     rdx, rbx; ClientBindingContext
0x14005df65  mov     [rbx+14h], ax
0x14005df69  mov     rcx, r14; NmrBindingHandle
0x14005df6c  movzx   eax, word ptr [rsi+4]
0x14005df70  mov     [rbx+16h], ax
0x14005df74  mov     eax, [rsi+8]
0x14005df77  mov     [rbx+18h], eax
0x14005df7a  movzx   eax, word ptr [rsi+2]
0x14005df7e  mov     [rbx+1Ch], ax
0x14005df82  mov     rax, [rbp+10h]
0x14005df86  movups  xmm0, xmmword ptr [rax+8]
0x14005df8a  lea     rax, [rbx+28h]
0x14005df8e  mov     [rsp+48h+ProviderDispatch], rax; ProviderDispatch
0x14005df93  movdqu  xmmword ptr [rbx+30h], xmm0
0x14005df98  call    cs:__imp_NmrClientAttachProvider
0x14005df9f  nop     dword ptr [rax+rax+00h]
0x14005dfa4  mov     esi, eax
0x14005dfa6  test    eax, eax
0x14005dfa8  js      short loc_14005E01D
0x14005dfaa  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005dfb1  lea     rdx, [rsp+48h+LockState]; LockState
0x14005dfb6  xor     r8d, r8d; Flags
0x14005dfb9  call    cs:__imp_NdisAcquireRWLockWrite
0x14005dfc0  nop     dword ptr [rax+rax+00h]
0x14005dfc5  test    dil, dil
0x14005dfc8  jz      short loc_14005DFD3
0x14005dfca  mov     cs:AfdNdkTransport, rbx
0x14005dfd1  jmp     short loc_14005DFFE
0x14005dfd3  mov     rax, cs:qword_140087C58
0x14005dfda  lea     rcx, AfdTlTransportListHead
0x14005dfe1  cmp     [rax], rcx
0x14005dfe4  jz      short loc_14005DFED
0x14005dfe6  mov     ecx, 3
0x14005dfeb  int     29h; Win8: RtlFailFast(ecx)
0x14005dfed  mov     [rbx], rcx
0x14005dff0  mov     [rbx+8], rax
0x14005dff4  mov     [rax], rbx
0x14005dff7  mov     cs:qword_140087C58, rbx
0x14005dffe  mov     rcx, cs:AfdTlTransportLock; Lock
0x14005e005  lea     rdx, [rsp+48h+LockState]; LockState
0x14005e00a  call    cs:__imp_NdisReleaseRWLock
0x14005e011  nop     dword ptr [rax+rax+00h]
0x14005e016  call    AfdWskProcessTransportChangeList
0x14005e01b  jmp     short loc_14005E03E
0x14005e01d  xor     edx, edx; Tag
0x14005e01f  mov     rcx, rbx; P
0x14005e022  call    cs:__imp_ExFreePoolWithTag
0x14005e029  nop     dword ptr [rax+rax+00h]
0x14005e02e  test    dil, dil
0x14005e031  jz      short loc_14005E03E
0x14005e033  mov     cs:AfdNdkTransport, 0
0x14005e03e  mov     eax, esi
0x14005e040  jmp     loc_14005DEEA
```
