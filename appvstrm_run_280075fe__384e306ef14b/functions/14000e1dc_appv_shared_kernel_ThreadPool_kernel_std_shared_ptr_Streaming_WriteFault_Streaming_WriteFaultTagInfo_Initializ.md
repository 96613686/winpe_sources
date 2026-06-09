# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::InitializeThreadPool(void)

- ea: `0x14000e1dc`
- end: `0x14000e32a`
- name: `?InitializeThreadPool@?$ThreadPool@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d7a0`

## callees

- `0x1400048a8`
- `0x140004ab8`
- `0x14000e1dc`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e306`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e306`
- `ntoskrnl!ZwClose` at `0x14000e296`
- `ntoskrnl!ZwClose` at `0x14000e296`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e280`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e280`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e2fa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e2fa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e2d3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e2d3`
- `ntoskrnl!PsCreateSystemThread` at `0x14000e256`
- `ntoskrnl!PsCreateSystemThread` at `0x14000e256`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e2bb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e2bb`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::InitializeThreadPool(
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
               appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::WorkingThread,
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
0x14000e1dc  push    rbx
0x14000e1de  push    rbp
0x14000e1df  push    rsi
0x14000e1e0  push    rdi
0x14000e1e1  sub     rsp, 48h
0x14000e1e5  cmp     dword ptr [rcx+0D4h], 0
0x14000e1ec  mov     rdi, rcx
0x14000e1ef  jnz     short loc_14000E1FB
0x14000e1f1  mov     eax, 0C000000Dh
0x14000e1f6  jmp     loc_14000E320
0x14000e1fb  add     rcx, 78h ; 'x'; this
0x14000e1ff  call    ?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z; appv::shared::kernel::event::create(wchar_t const *,bool)
0x14000e204  mov     ebx, eax
0x14000e206  test    eax, eax
0x14000e208  js      loc_14000E320
0x14000e20e  mov     esi, [rdi+0D4h]
0x14000e214  mov     dword ptr [rdi+0D0h], 0
0x14000e21e  test    esi, esi
0x14000e220  jz      loc_14000E31E
0x14000e226  lea     rax, ?WorkingThread@?$ThreadPool@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::WorkingThread(void *)
0x14000e22d  mov     [rsp+68h+StartContext], rdi; StartContext
0x14000e232  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x14000e237  lea     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x14000e23c  xor     r9d, r9d; ProcessHandle
0x14000e23f  mov     [rsp+68h+ClientId], 0; ClientId
0x14000e248  xor     r8d, r8d; ObjectAttributes
0x14000e24b  mov     [rsp+68h+ThreadHandle], 0
0x14000e254  xor     edx, edx; DesiredAccess
0x14000e256  call    cs:__imp_PsCreateSystemThread
0x14000e25d  nop     dword ptr [rax+rax+00h]
0x14000e262  mov     ebx, eax
0x14000e264  test    eax, eax
0x14000e266  js      short loc_14000E28C
0x14000e268  lea     rcx, [rdi+0B0h]; Object
0x14000e26f  mov     [rsp+68h+ClientId], 0; Timeout
0x14000e278  xor     r9d, r9d; Alertable
0x14000e27b  xor     r8d, r8d; WaitMode
0x14000e27e  xor     edx, edx; WaitReason
0x14000e280  call    cs:__imp_KeWaitForSingleObject
0x14000e287  nop     dword ptr [rax+rax+00h]
0x14000e28c  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x14000e291  test    rcx, rcx
0x14000e294  jz      short loc_14000E2A2
0x14000e296  call    cs:__imp_ZwClose
0x14000e29d  nop     dword ptr [rax+rax+00h]
0x14000e2a2  test    ebx, ebx
0x14000e2a4  js      short loc_14000E2B1
0x14000e2a6  add     esi, 0FFFFFFFFh
0x14000e2a9  jnz     loc_14000E226
0x14000e2af  jmp     short loc_14000E31E
0x14000e2b1  xor     sil, sil
0x14000e2b4  cmp     qword ptr [rdi+70h], 0
0x14000e2b9  jz      short loc_14000E2E9
0x14000e2bb  call    cs:__imp_KeEnterCriticalRegion
0x14000e2c2  nop     dword ptr [rax+rax+00h]
0x14000e2c7  mov     rcx, [rdi+70h]; Resource
0x14000e2cb  mov     ebp, 1
0x14000e2d0  mov     dl, bpl; Wait
0x14000e2d3  call    cs:__imp_ExAcquireResourceSharedLite
0x14000e2da  nop     dword ptr [rax+rax+00h]
0x14000e2df  cmp     al, bpl
0x14000e2e2  movzx   esi, sil
0x14000e2e6  cmovz   esi, ebp
0x14000e2e9  mov     ebp, [rdi+5Ch]
0x14000e2ec  test    sil, sil
0x14000e2ef  jz      short loc_14000E312
0x14000e2f1  mov     rcx, [rdi+70h]; Resource
0x14000e2f5  test    rcx, rcx
0x14000e2f8  jz      short loc_14000E312
0x14000e2fa  call    cs:__imp_ExReleaseResourceLite
0x14000e301  nop     dword ptr [rax+rax+00h]
0x14000e306  call    cs:__imp_KeLeaveCriticalRegion
0x14000e30d  nop     dword ptr [rax+rax+00h]
0x14000e312  test    ebp, ebp
0x14000e314  jz      short loc_14000E31E
0x14000e316  mov     rcx, rdi
0x14000e319  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x14000e31e  mov     eax, ebx
0x14000e320  add     rsp, 48h
0x14000e324  pop     rdi
0x14000e325  pop     rsi
0x14000e326  pop     rbp
0x14000e327  pop     rbx
0x14000e328  retn
```
