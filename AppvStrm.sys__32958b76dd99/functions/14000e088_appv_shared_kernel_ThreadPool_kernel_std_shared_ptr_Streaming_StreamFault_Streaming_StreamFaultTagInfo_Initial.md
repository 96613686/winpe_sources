# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::InitializeThreadPool(void)

- ea: `0x14000e088`
- end: `0x14000e1d6`
- name: `?InitializeThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(char *StartContext, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d7a0`

## callees

- `0x1400048a8`
- `0x140004ab8`
- `0x14000e088`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e1b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e1b2`
- `ntoskrnl!ZwClose` at `0x14000e142`
- `ntoskrnl!ZwClose` at `0x14000e142`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e12c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e12c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e1a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e1a6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e17f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000e17f`
- `ntoskrnl!PsCreateSystemThread` at `0x14000e102`
- `ntoskrnl!PsCreateSystemThread` at `0x14000e102`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e167`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e167`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::InitializeThreadPool(
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
               appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::WorkingThread,
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
0x14000e088  push    rbx
0x14000e08a  push    rbp
0x14000e08b  push    rsi
0x14000e08c  push    rdi
0x14000e08d  sub     rsp, 48h
0x14000e091  cmp     dword ptr [rcx+0D4h], 0
0x14000e098  mov     rdi, rcx
0x14000e09b  jnz     short loc_14000E0A7
0x14000e09d  mov     eax, 0C000000Dh
0x14000e0a2  jmp     loc_14000E1CC
0x14000e0a7  add     rcx, 78h ; 'x'; this
0x14000e0ab  call    ?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z; appv::shared::kernel::event::create(wchar_t const *,bool)
0x14000e0b0  mov     ebx, eax
0x14000e0b2  test    eax, eax
0x14000e0b4  js      loc_14000E1CC
0x14000e0ba  mov     esi, [rdi+0D4h]
0x14000e0c0  mov     dword ptr [rdi+0D0h], 0
0x14000e0ca  test    esi, esi
0x14000e0cc  jz      loc_14000E1CA
0x14000e0d2  lea     rax, ?WorkingThread@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::WorkingThread(void *)
0x14000e0d9  mov     [rsp+68h+StartContext], rdi; StartContext
0x14000e0de  mov     [rsp+68h+StartRoutine], rax; StartRoutine
0x14000e0e3  lea     rcx, [rsp+68h+ThreadHandle]; ThreadHandle
0x14000e0e8  xor     r9d, r9d; ProcessHandle
0x14000e0eb  mov     [rsp+68h+ClientId], 0; ClientId
0x14000e0f4  xor     r8d, r8d; ObjectAttributes
0x14000e0f7  mov     [rsp+68h+ThreadHandle], 0
0x14000e100  xor     edx, edx; DesiredAccess
0x14000e102  call    cs:__imp_PsCreateSystemThread
0x14000e109  nop     dword ptr [rax+rax+00h]
0x14000e10e  mov     ebx, eax
0x14000e110  test    eax, eax
0x14000e112  js      short loc_14000E138
0x14000e114  lea     rcx, [rdi+0B0h]; Object
0x14000e11b  mov     [rsp+68h+ClientId], 0; Timeout
0x14000e124  xor     r9d, r9d; Alertable
0x14000e127  xor     r8d, r8d; WaitMode
0x14000e12a  xor     edx, edx; WaitReason
0x14000e12c  call    cs:__imp_KeWaitForSingleObject
0x14000e133  nop     dword ptr [rax+rax+00h]
0x14000e138  mov     rcx, [rsp+68h+ThreadHandle]; Handle
0x14000e13d  test    rcx, rcx
0x14000e140  jz      short loc_14000E14E
0x14000e142  call    cs:__imp_ZwClose
0x14000e149  nop     dword ptr [rax+rax+00h]
0x14000e14e  test    ebx, ebx
0x14000e150  js      short loc_14000E15D
0x14000e152  add     esi, 0FFFFFFFFh
0x14000e155  jnz     loc_14000E0D2
0x14000e15b  jmp     short loc_14000E1CA
0x14000e15d  xor     sil, sil
0x14000e160  cmp     qword ptr [rdi+70h], 0
0x14000e165  jz      short loc_14000E195
0x14000e167  call    cs:__imp_KeEnterCriticalRegion
0x14000e16e  nop     dword ptr [rax+rax+00h]
0x14000e173  mov     rcx, [rdi+70h]; Resource
0x14000e177  mov     ebp, 1
0x14000e17c  mov     dl, bpl; Wait
0x14000e17f  call    cs:__imp_ExAcquireResourceSharedLite
0x14000e186  nop     dword ptr [rax+rax+00h]
0x14000e18b  cmp     al, bpl
0x14000e18e  movzx   esi, sil
0x14000e192  cmovz   esi, ebp
0x14000e195  mov     ebp, [rdi+5Ch]
0x14000e198  test    sil, sil
0x14000e19b  jz      short loc_14000E1BE
0x14000e19d  mov     rcx, [rdi+70h]; Resource
0x14000e1a1  test    rcx, rcx
0x14000e1a4  jz      short loc_14000E1BE
0x14000e1a6  call    cs:__imp_ExReleaseResourceLite
0x14000e1ad  nop     dword ptr [rax+rax+00h]
0x14000e1b2  call    cs:__imp_KeLeaveCriticalRegion
0x14000e1b9  nop     dword ptr [rax+rax+00h]
0x14000e1be  test    ebp, ebp
0x14000e1c0  jz      short loc_14000E1CA
0x14000e1c2  mov     rcx, rdi
0x14000e1c5  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x14000e1ca  mov     eax, ebx
0x14000e1cc  add     rsp, 48h
0x14000e1d0  pop     rdi
0x14000e1d1  pop     rsi
0x14000e1d2  pop     rbp
0x14000e1d3  pop     rbx
0x14000e1d4  retn
```
