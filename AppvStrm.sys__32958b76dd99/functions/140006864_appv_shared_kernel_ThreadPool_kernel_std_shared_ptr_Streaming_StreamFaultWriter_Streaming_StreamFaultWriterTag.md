# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::InitializeThreadPool(void)

- ea: `0x140006864`
- end: `0x1400069b2`
- name: `?InitializeThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(char *StartContext, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004fec`

## callees

- `0x140004ab8`
- `0x140006864`
- `0x1400073b8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000698e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000698e`
- `ntoskrnl!ZwClose` at `0x14000691e`
- `ntoskrnl!ZwClose` at `0x14000691e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006908`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006908`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006982`
- `ntoskrnl!ExReleaseResourceLite` at `0x140006982`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000695b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000695b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400068de`
- `ntoskrnl!PsCreateSystemThread` at `0x1400068de`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006943`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006943`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::InitializeThreadPool(
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
               appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::WorkingThread,
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
0x140006864  push    rbx
0x140006866  push    rbp
0x140006867  push    rsi
0x140006868  push    rdi
0x140006869  sub     rsp, 48h
0x14000686d  cmp     dword ptr [rcx+0D4h], 0
0x140006874  mov     rdi, rcx
0x140006877  jnz     short loc_140006883
0x140006879  mov     eax, 0C000000Dh
0x14000687e  jmp     loc_1400069A8
0x140006883  add     rcx, 78h ; 'x'; this
0x140006887  call    ?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z; appv::shared::kernel::event::create(wchar_t const *,bool)
0x14000688c  mov     ebx, eax
0x14000688e  test    eax, eax
0x140006890  js      loc_1400069A8
0x140006896  mov     esi, [rdi+0D4h]
0x14000689c  mov     dword ptr [rdi+0D0h], 0
0x1400068a6  test    esi, esi
0x1400068a8  jz      loc_1400069A6
0x1400068ae  lea     rax, ?WorkingThread@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::WorkingThread(void *)
0x1400068b5  mov     [rsp+68h+StartContext], rdi; StartContext
0x1400068ba  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x1400068bf  lea     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x1400068c4  xor     r9d, r9d; ProcessHandle
0x1400068c7  mov     [rsp+68h+ClientId], 0; ClientId
0x1400068d0  xor     r8d, r8d; ObjectAttributes
0x1400068d3  mov     [rsp+68h+ThreadHandle], 0
0x1400068dc  xor     edx, edx; DesiredAccess
0x1400068de  call    cs:__imp_PsCreateSystemThread
0x1400068e5  nop     dword ptr [rax+rax+00h]
0x1400068ea  mov     ebx, eax
0x1400068ec  test    eax, eax
0x1400068ee  js      short loc_140006914
0x1400068f0  lea     rcx, [rdi+0B0h]; Object
0x1400068f7  mov     [rsp+68h+ClientId], 0; Timeout
0x140006900  xor     r9d, r9d; Alertable
0x140006903  xor     r8d, r8d; WaitMode
0x140006906  xor     edx, edx; WaitReason
0x140006908  call    cs:__imp_KeWaitForSingleObject
0x14000690f  nop     dword ptr [rax+rax+00h]
0x140006914  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x140006919  test    rcx, rcx
0x14000691c  jz      short loc_14000692A
0x14000691e  call    cs:__imp_ZwClose
0x140006925  nop     dword ptr [rax+rax+00h]
0x14000692a  test    ebx, ebx
0x14000692c  js      short loc_140006939
0x14000692e  add     esi, 0FFFFFFFFh
0x140006931  jnz     loc_1400068AE
0x140006937  jmp     short loc_1400069A6
0x140006939  xor     sil, sil
0x14000693c  cmp     qword ptr [rdi+70h], 0
0x140006941  jz      short loc_140006971
0x140006943  call    cs:__imp_KeEnterCriticalRegion
0x14000694a  nop     dword ptr [rax+rax+00h]
0x14000694f  mov     rcx, [rdi+70h]; Resource
0x140006953  mov     ebp, 1
0x140006958  mov     dl, bpl; Wait
0x14000695b  call    cs:__imp_ExAcquireResourceSharedLite
0x140006962  nop     dword ptr [rax+rax+00h]
0x140006967  cmp     al, bpl
0x14000696a  movzx   esi, sil
0x14000696e  cmovz   esi, ebp
0x140006971  mov     ebp, [rdi+5Ch]
0x140006974  test    sil, sil
0x140006977  jz      short loc_14000699A
0x140006979  mov     rcx, [rdi+70h]; Resource
0x14000697d  test    rcx, rcx
0x140006980  jz      short loc_14000699A
0x140006982  call    cs:__imp_ExReleaseResourceLite
0x140006989  nop     dword ptr [rax+rax+00h]
0x14000698e  call    cs:__imp_KeLeaveCriticalRegion
0x140006995  nop     dword ptr [rax+rax+00h]
0x14000699a  test    ebp, ebp
0x14000699c  jz      short loc_1400069A6
0x14000699e  mov     rcx, rdi
0x1400069a1  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x1400069a6  mov     eax, ebx
0x1400069a8  add     rsp, 48h
0x1400069ac  pop     rdi
0x1400069ad  pop     rsi
0x1400069ae  pop     rbp
0x1400069af  pop     rbx
0x1400069b0  retn
```
