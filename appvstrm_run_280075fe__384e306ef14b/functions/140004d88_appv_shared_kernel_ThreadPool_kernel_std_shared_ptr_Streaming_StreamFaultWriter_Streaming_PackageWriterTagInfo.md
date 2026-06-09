# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>(long,long &,long,long)

- ea: `0x140004d88`
- end: `0x140004ee8`
- name: `??0?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@JAEAJJJ@Z`
- size: `352`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000600c`

## callees

- `0x140004d88`
- `0x140006710`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCount` at `0x140004eb5`
- `ntoskrnl!KeQueryActiveProcessorCount` at `0x140004eb5`
- `ntoskrnl!KeInitializeSemaphore` at `0x140004e76`
- `ntoskrnl!KeInitializeSemaphore` at `0x140004e91`
- `ntoskrnl!KeInitializeSemaphore` at `0x140004e76`
- `ntoskrnl!KeInitializeSemaphore` at `0x140004e91`
- `ntoskrnl!ExInitializeResourceLite` at `0x140004df0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140004e47`
- `ntoskrnl!ExInitializeResourceLite` at `0x140004df0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140004e47`
- `ntoskrnl!ExAllocatePool2` at `0x140004dcf`
- `ntoskrnl!ExAllocatePool2` at `0x140004e2f`
- `ntoskrnl!ExAllocatePool2` at `0x140004dcf`
- `ntoskrnl!ExAllocatePool2` at `0x140004e2f`

## pseudocode

```c
char *__fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>(
        char *StartContext,
        int a2,
        int *a3)
{
  struct _ERESOURCE *Pool2; // rax
  NTSTATUS v7; // esi
  int v8; // edi
  struct _ERESOURCE *v9; // rax
  const wchar_t *v10; // rdx

  *((_DWORD *)StartContext + 10) = 2003854963;
  *((_QWORD *)StartContext + 4) = StartContext + 8;
  *(_DWORD *)StartContext = 0;
  *((_QWORD *)StartContext + 1) = 0;
  *((_QWORD *)StartContext + 2) = 0;
  *((_QWORD *)StartContext + 3) = StartContext + 8;
  *((_QWORD *)StartContext + 6) = 0;
  Pool2 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 2003854963);
  *((_QWORD *)StartContext + 6) = Pool2;
  v7 = -1073741670;
  if ( Pool2 )
    v8 = ExInitializeResourceLite(Pool2);
  else
    v8 = -1073741670;
  *((_QWORD *)StartContext + 7) = 0;
  *((_QWORD *)StartContext + 8) = 0;
  *((_QWORD *)StartContext + 9) = 0;
  *((_QWORD *)StartContext + 10) = 0;
  *((_QWORD *)StartContext + 11) = 0;
  StartContext[96] = 1;
  *((_DWORD *)StartContext + 26) = 2003854963;
  *((_QWORD *)StartContext + 14) = 0;
  v9 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 2003854963);
  *((_QWORD *)StartContext + 14) = v9;
  if ( v9 )
    v7 = ExInitializeResourceLite(v9);
  StartContext[120] = 0;
  *((_QWORD *)StartContext + 16) = 0;
  *((_QWORD *)StartContext + 17) = 0;
  KeInitializeSemaphore((PRKSEMAPHORE)(StartContext + 144), 0, 0xFFFF);
  KeInitializeSemaphore((PRKSEMAPHORE)(StartContext + 176), 0, 0xFFFF);
  *((_DWORD *)StartContext + 53) = a2;
  if ( v8 >= 0 )
  {
    if ( v7 >= 0 )
    {
      if ( !a2 )
        *((_DWORD *)StartContext + 53) = 3 * KeQueryActiveProcessorCount(0);
      v8 = appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::InitializeThreadPool(
             StartContext,
             v10);
    }
    else
    {
      v8 = v7;
    }
  }
  *a3 = v8;
  return StartContext;
}

```

## disassembly

```asm
0x140004d88  push    rbx
0x140004d8a  push    rbp
0x140004d8b  push    rsi
0x140004d8c  push    rdi
0x140004d8d  push    r12
0x140004d8f  push    r14
0x140004d91  sub     rsp, 28h
0x140004d95  lea     rax, [rcx+8]
0x140004d99  mov     dword ptr [rcx+28h], 77706673h
0x140004da0  xor     r12d, r12d
0x140004da3  mov     [rax+18h], rax
0x140004da7  mov     [rcx], r12d
0x140004daa  mov     ebp, edx
0x140004dac  mov     [rax], r12
0x140004daf  mov     r14, r8
0x140004db2  mov     [rax+8], r12
0x140004db6  mov     rbx, rcx
0x140004db9  lea     edx, [r12+68h]
0x140004dbe  mov     [rax+10h], rax
0x140004dc2  mov     [rcx+30h], r12
0x140004dc6  mov     r8d, 77706673h
0x140004dcc  lea     ecx, [rdx-28h]
0x140004dcf  call    cs:__imp_ExAllocatePool2
0x140004dd6  nop     dword ptr [rax+rax+00h]
0x140004ddb  mov     [rbx+30h], rax
0x140004ddf  mov     esi, 0C000009Ah
0x140004de4  test    rax, rax
0x140004de7  jnz     short loc_140004DED
0x140004de9  mov     edi, esi
0x140004deb  jmp     short loc_140004DFE
0x140004ded  mov     rcx, rax; Resource
0x140004df0  call    cs:__imp_ExInitializeResourceLite
0x140004df7  nop     dword ptr [rax+rax+00h]
0x140004dfc  mov     edi, eax
0x140004dfe  mov     edx, 68h ; 'h'
0x140004e03  mov     [rbx+38h], r12
0x140004e07  mov     [rbx+40h], r12
0x140004e0b  mov     r8d, 77706673h
0x140004e11  mov     [rbx+48h], r12
0x140004e15  mov     [rbx+50h], r12
0x140004e19  mov     [rbx+58h], r12
0x140004e1d  lea     ecx, [rdx-28h]
0x140004e20  mov     byte ptr [rbx+60h], 1
0x140004e24  mov     dword ptr [rbx+68h], 77706673h
0x140004e2b  mov     [rbx+70h], r12
0x140004e2f  call    cs:__imp_ExAllocatePool2
0x140004e36  nop     dword ptr [rax+rax+00h]
0x140004e3b  mov     [rbx+70h], rax
0x140004e3f  test    rax, rax
0x140004e42  jz      short loc_140004E55
0x140004e44  mov     rcx, rax; Resource
0x140004e47  call    cs:__imp_ExInitializeResourceLite
0x140004e4e  nop     dword ptr [rax+rax+00h]
0x140004e53  mov     esi, eax
0x140004e55  lea     rcx, [rbx+90h]; Semaphore
0x140004e5c  mov     [rbx+78h], r12b
0x140004e60  xor     edx, edx; Count
0x140004e62  mov     [rbx+80h], r12
0x140004e69  mov     r8d, 0FFFFh; Limit
0x140004e6f  mov     [rbx+88h], r12
0x140004e76  call    cs:__imp_KeInitializeSemaphore
0x140004e7d  nop     dword ptr [rax+rax+00h]
0x140004e82  lea     rcx, [rbx+0B0h]; Semaphore
0x140004e89  xor     edx, edx; Count
0x140004e8b  mov     r8d, 0FFFFh; Limit
0x140004e91  call    cs:__imp_KeInitializeSemaphore
0x140004e98  nop     dword ptr [rax+rax+00h]
0x140004e9d  mov     [rbx+0D4h], ebp
0x140004ea3  test    edi, edi
0x140004ea5  js      short loc_140004ED4
0x140004ea7  test    esi, esi
0x140004ea9  jns     short loc_140004EAF
0x140004eab  mov     edi, esi
0x140004ead  jmp     short loc_140004ED4
0x140004eaf  test    ebp, ebp
0x140004eb1  jnz     short loc_140004ECA
0x140004eb3  xor     ecx, ecx; ActiveProcessors
0x140004eb5  call    cs:__imp_KeQueryActiveProcessorCount
0x140004ebc  nop     dword ptr [rax+rax+00h]
0x140004ec1  lea     ecx, [rax+rax*2]
0x140004ec4  mov     [rbx+0D4h], ecx
0x140004eca  mov     rcx, rbx; StartContext
0x140004ecd  call    ?InitializeThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::InitializeThreadPool(void)
0x140004ed2  mov     edi, eax
0x140004ed4  mov     [r14], edi
0x140004ed7  mov     rax, rbx
0x140004eda  add     rsp, 28h
0x140004ede  pop     r14
0x140004ee0  pop     r12
0x140004ee2  pop     rdi
0x140004ee3  pop     rsi
0x140004ee4  pop     rbp
0x140004ee5  pop     rbx
0x140004ee6  retn
```
