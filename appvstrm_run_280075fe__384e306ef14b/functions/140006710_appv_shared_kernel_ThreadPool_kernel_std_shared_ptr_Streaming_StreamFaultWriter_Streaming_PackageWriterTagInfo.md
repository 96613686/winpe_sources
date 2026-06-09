# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::InitializeThreadPool(void)

- ea: `0x140006710`
- end: `0x14000685e`
- name: `?InitializeThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004d88`

## callees

- `0x140004ab8`
- `0x140006710`
- `0x1400073b8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000683a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000683a`
- `ntoskrnl!ZwClose` at `0x1400067ca`
- `ntoskrnl!ZwClose` at `0x1400067ca`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400067b4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400067b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000682e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000682e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140006807`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140006807`
- `ntoskrnl!PsCreateSystemThread` at `0x14000678a`
- `ntoskrnl!PsCreateSystemThread` at `0x14000678a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400067ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400067ef`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::InitializeThreadPool(
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
               appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::WorkingThread,
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
        appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(StartContext);
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x140006710  push    rbx
0x140006712  push    rbp
0x140006713  push    rsi
0x140006714  push    rdi
0x140006715  sub     rsp, 48h
0x140006719  cmp     dword ptr [rcx+0D4h], 0
0x140006720  mov     rdi, rcx
0x140006723  jnz     short loc_14000672F
0x140006725  mov     eax, 0C000000Dh
0x14000672a  jmp     loc_140006854
0x14000672f  add     rcx, 78h ; 'x'; this
0x140006733  call    ?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z; appv::shared::kernel::event::create(wchar_t const *,bool)
0x140006738  mov     ebx, eax
0x14000673a  test    eax, eax
0x14000673c  js      loc_140006854
0x140006742  mov     esi, [rdi+0D4h]
0x140006748  mov     dword ptr [rdi+0D0h], 0
0x140006752  test    esi, esi
0x140006754  jz      loc_140006852
0x14000675a  lea     rax, ?WorkingThread@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::WorkingThread(void *)
0x140006761  mov     [rsp+68h+StartContext], rdi; StartContext
0x140006766  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x14000676b  lea     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x140006770  xor     r9d, r9d; ProcessHandle
0x140006773  mov     [rsp+68h+ClientId], 0; ClientId
0x14000677c  xor     r8d, r8d; ObjectAttributes
0x14000677f  mov     [rsp+68h+ThreadHandle], 0
0x140006788  xor     edx, edx; DesiredAccess
0x14000678a  call    cs:__imp_PsCreateSystemThread
0x140006791  nop     dword ptr [rax+rax+00h]
0x140006796  mov     ebx, eax
0x140006798  test    eax, eax
0x14000679a  js      short loc_1400067C0
0x14000679c  lea     rcx, [rdi+0B0h]; Object
0x1400067a3  mov     [rsp+68h+ClientId], 0; Timeout
0x1400067ac  xor     r9d, r9d; Alertable
0x1400067af  xor     r8d, r8d; WaitMode
0x1400067b2  xor     edx, edx; WaitReason
0x1400067b4  call    cs:__imp_KeWaitForSingleObject
0x1400067bb  nop     dword ptr [rax+rax+00h]
0x1400067c0  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x1400067c5  test    rcx, rcx
0x1400067c8  jz      short loc_1400067D6
0x1400067ca  call    cs:__imp_ZwClose
0x1400067d1  nop     dword ptr [rax+rax+00h]
0x1400067d6  test    ebx, ebx
0x1400067d8  js      short loc_1400067E5
0x1400067da  add     esi, 0FFFFFFFFh
0x1400067dd  jnz     loc_14000675A
0x1400067e3  jmp     short loc_140006852
0x1400067e5  xor     sil, sil
0x1400067e8  cmp     qword ptr [rdi+70h], 0
0x1400067ed  jz      short loc_14000681D
0x1400067ef  call    cs:__imp_KeEnterCriticalRegion
0x1400067f6  nop     dword ptr [rax+rax+00h]
0x1400067fb  mov     rcx, [rdi+70h]; Resource
0x1400067ff  mov     ebp, 1
0x140006804  mov     dl, bpl; Wait
0x140006807  call    cs:__imp_ExAcquireResourceSharedLite
0x14000680e  nop     dword ptr [rax+rax+00h]
0x140006813  cmp     al, bpl
0x140006816  movzx   esi, sil
0x14000681a  cmovz   esi, ebp
0x14000681d  mov     ebp, [rdi+5Ch]
0x140006820  test    sil, sil
0x140006823  jz      short loc_140006846
0x140006825  mov     rcx, [rdi+70h]; Resource
0x140006829  test    rcx, rcx
0x14000682c  jz      short loc_140006846
0x14000682e  call    cs:__imp_ExReleaseResourceLite
0x140006835  nop     dword ptr [rax+rax+00h]
0x14000683a  call    cs:__imp_KeLeaveCriticalRegion
0x140006841  nop     dword ptr [rax+rax+00h]
0x140006846  test    ebp, ebp
0x140006848  jz      short loc_140006852
0x14000684a  mov     rcx, rdi
0x14000684d  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x140006852  mov     eax, ebx
0x140006854  add     rsp, 48h
0x140006858  pop     rdi
0x140006859  pop     rsi
0x14000685a  pop     rbp
0x14000685b  pop     rbx
0x14000685c  retn
```
