# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::InitializeThreadPool(void)

- ea: `0x140003ef8`
- end: `0x140004046`
- name: `?InitializeThreadPool@?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(char *StartContext, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003898`

## callees

- `0x140003ef8`
- `0x1400048a8`
- `0x140004ab8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004022`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004022`
- `ntoskrnl!ZwClose` at `0x140003fb2`
- `ntoskrnl!ZwClose` at `0x140003fb2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003f9c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003f9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004016`
- `ntoskrnl!ExReleaseResourceLite` at `0x140004016`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140003fef`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140003fef`
- `ntoskrnl!PsCreateSystemThread` at `0x140003f72`
- `ntoskrnl!PsCreateSystemThread` at `0x140003f72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003fd7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003fd7`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::InitializeThreadPool(
        char *StartContext,
        const wchar_t *a2)
{
  __int64 result; // rax
  NTSTATUS v4; // ebx
  int v5; // esi
  bool v6; // si
  int v7; // ebp
  struct _ERESOURCE *v8; // rcx
  void *ThreadHandle; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_DWORD *)StartContext + 53) )
    return 3221225485LL;
  result = appv::shared::kernel::event::create((appv::shared::kernel::event *)(StartContext + 120), a2);
  v4 = result;
  if ( (int)result >= 0 )
  {
    v5 = *((_DWORD *)StartContext + 53);
    *((_DWORD *)StartContext + 52) = 0;
    if ( v5 )
    {
      while ( 1 )
      {
        ThreadHandle = 0;
        v4 = PsCreateSystemThread(
               &ThreadHandle,
               0,
               0,
               0,
               0,
               appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::WorkingThread,
               StartContext);
        if ( v4 >= 0 )
          KeWaitForSingleObject(StartContext + 176, Executive, 0, 0, 0);
        if ( ThreadHandle )
          ZwClose(ThreadHandle);
        if ( v4 < 0 )
          break;
        if ( !--v5 )
          return (unsigned int)v4;
      }
      v6 = 0;
      if ( *((_QWORD *)StartContext + 14) )
      {
        KeEnterCriticalRegion();
        v6 = ExAcquireResourceSharedLite(*((PERESOURCE *)StartContext + 14), 1u) == 1;
      }
      v7 = *((_DWORD *)StartContext + 23);
      if ( v6 )
      {
        v8 = (struct _ERESOURCE *)*((_QWORD *)StartContext + 14);
        if ( v8 )
        {
          ExReleaseResourceLite(v8);
          KeLeaveCriticalRegion();
        }
      }
      if ( v7 )
        appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(StartContext);
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x140003ef8  push    rbx
0x140003efa  push    rbp
0x140003efb  push    rsi
0x140003efc  push    rdi
0x140003efd  sub     rsp, 48h
0x140003f01  cmp     dword ptr [rcx+0D4h], 0
0x140003f08  mov     rdi, rcx
0x140003f0b  jnz     short loc_140003F17
0x140003f0d  mov     eax, 0C000000Dh
0x140003f12  jmp     loc_14000403C
0x140003f17  add     rcx, 78h ; 'x'; this
0x140003f1b  call    ?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z; appv::shared::kernel::event::create(wchar_t const *,bool)
0x140003f20  mov     ebx, eax
0x140003f22  test    eax, eax
0x140003f24  js      loc_14000403C
0x140003f2a  mov     esi, [rdi+0D4h]
0x140003f30  mov     dword ptr [rdi+0D0h], 0
0x140003f3a  test    esi, esi
0x140003f3c  jz      loc_14000403A
0x140003f42  lea     rax, ?WorkingThread@?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::WorkingThread(void *)
0x140003f49  mov     [rsp+68h+StartContext], rdi; StartContext
0x140003f4e  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x140003f53  lea     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x140003f58  xor     r9d, r9d; ProcessHandle
0x140003f5b  mov     [rsp+68h+ClientId], 0; ClientId
0x140003f64  xor     r8d, r8d; ObjectAttributes
0x140003f67  mov     [rsp+68h+ThreadHandle], 0
0x140003f70  xor     edx, edx; DesiredAccess
0x140003f72  call    cs:__imp_PsCreateSystemThread
0x140003f79  nop     dword ptr [rax+rax+00h]
0x140003f7e  mov     ebx, eax
0x140003f80  test    eax, eax
0x140003f82  js      short loc_140003FA8
0x140003f84  lea     rcx, [rdi+0B0h]; Object
0x140003f8b  mov     [rsp+68h+ClientId], 0; Timeout
0x140003f94  xor     r9d, r9d; Alertable
0x140003f97  xor     r8d, r8d; WaitMode
0x140003f9a  xor     edx, edx; WaitReason
0x140003f9c  call    cs:__imp_KeWaitForSingleObject
0x140003fa3  nop     dword ptr [rax+rax+00h]
0x140003fa8  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x140003fad  test    rcx, rcx
0x140003fb0  jz      short loc_140003FBE
0x140003fb2  call    cs:__imp_ZwClose
0x140003fb9  nop     dword ptr [rax+rax+00h]
0x140003fbe  test    ebx, ebx
0x140003fc0  js      short loc_140003FCD
0x140003fc2  add     esi, 0FFFFFFFFh
0x140003fc5  jnz     loc_140003F42
0x140003fcb  jmp     short loc_14000403A
0x140003fcd  xor     sil, sil
0x140003fd0  cmp     qword ptr [rdi+70h], 0
0x140003fd5  jz      short loc_140004005
0x140003fd7  call    cs:__imp_KeEnterCriticalRegion
0x140003fde  nop     dword ptr [rax+rax+00h]
0x140003fe3  mov     rcx, [rdi+70h]; Resource
0x140003fe7  mov     ebp, 1
0x140003fec  mov     dl, bpl; Wait
0x140003fef  call    cs:__imp_ExAcquireResourceSharedLite
0x140003ff6  nop     dword ptr [rax+rax+00h]
0x140003ffb  cmp     al, bpl
0x140003ffe  movzx   esi, sil
0x140004002  cmovz   esi, ebp
0x140004005  mov     ebp, [rdi+5Ch]
0x140004008  test    sil, sil
0x14000400b  jz      short loc_14000402E
0x14000400d  mov     rcx, [rdi+70h]; Resource
0x140004011  test    rcx, rcx
0x140004014  jz      short loc_14000402E
0x140004016  call    cs:__imp_ExReleaseResourceLite
0x14000401d  nop     dword ptr [rax+rax+00h]
0x140004022  call    cs:__imp_KeLeaveCriticalRegion
0x140004029  nop     dword ptr [rax+rax+00h]
0x14000402e  test    ebp, ebp
0x140004030  jz      short loc_14000403A
0x140004032  mov     rcx, rdi
0x140004035  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x14000403a  mov     eax, ebx
0x14000403c  add     rsp, 48h
0x140004040  pop     rdi
0x140004041  pop     rsi
0x140004042  pop     rbp
0x140004043  pop     rbx
0x140004044  retn
```
