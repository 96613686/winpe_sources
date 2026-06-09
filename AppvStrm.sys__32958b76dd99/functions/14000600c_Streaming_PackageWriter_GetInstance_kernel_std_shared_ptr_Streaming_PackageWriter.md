# Streaming::PackageWriter::GetInstance(kernel_std::shared_ptr<Streaming::PackageWriter> &)

- ea: `0x14000600c`
- end: `0x140006150`
- name: `?GetInstance@PackageWriter@Streaming@@SAJAEAV?$shared_ptr@VPackageWriter@Streaming@@@kernel_std@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000571c`

## callees

- `0x140004d88`
- `0x14000528c`
- `0x14000600c`
- `0x1400073b8`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400060de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400060de`
- `ntoskrnl!ExAllocatePool2` at `0x14000602e`
- `ntoskrnl!ExAllocatePool2` at `0x14000607b`
- `ntoskrnl!ExAllocatePool2` at `0x14000602e`
- `ntoskrnl!ExAllocatePool2` at `0x14000607b`

## pseudocode

```c
__int64 __fastcall Streaming::PackageWriter::GetInstance(char **a1)
{
  char *Pool2; // rax
  char *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // edx
  volatile signed __int32 *v7; // rbx
  char *v8; // rax
  NTSTATUS v10; // [rsp+48h] [rbp+10h] BYREF

  Pool2 = (char *)ExAllocatePool2(64, 432, 2003854963);
  v3 = Pool2;
  if ( Pool2 )
  {
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>(
      Pool2,
      0,
      &v10);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>(
      v3 + 216,
      2,
      &v10);
  }
  else
  {
    v3 = 0;
  }
  v4 = ExAllocatePool2(256, 24, 1715758931);
  v5 = v4;
  if ( v4 )
  {
    *(_QWORD *)(v4 + 16) = v3;
    *(_DWORD *)(v4 + 8) = 1;
    *(_DWORD *)(v4 + 12) = 1;
    *(_QWORD *)v4 = &kernel_std::detail::sp_counted_impl_p<Streaming::PackageWriter>::`vftable';
    v6 = *(_DWORD *)(v4 + 8);
  }
  else
  {
    if ( v3 )
    {
      appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(v3);
      appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(v3 + 216);
      appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)(v3 + 216));
      appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)v3);
      ExFreePoolWithTag(v3, 0);
    }
    v6 = 0;
    v5 = 0;
  }
  v7 = (volatile signed __int32 *)a1[1];
  v8 = 0;
  a1[1] = (char *)v5;
  if ( v6 )
    v8 = v3;
  *a1 = v8;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000600c  mov     [rsp+arg_0], rbx
0x140006011  mov     [rsp+arg_10], rsi
0x140006016  push    rdi
0x140006017  sub     rsp, 30h
0x14000601b  mov     rsi, rcx
0x14000601e  mov     edx, 1B0h
0x140006023  mov     ecx, 40h ; '@'
0x140006028  mov     r8d, 77706673h
0x14000602e  call    cs:__imp_ExAllocatePool2
0x140006035  nop     dword ptr [rax+rax+00h]
0x14000603a  mov     rdi, rax
0x14000603d  test    rax, rax
0x140006040  jz      short loc_140006069
0x140006042  lea     r8, [rsp+38h+arg_8]
0x140006047  xor     edx, edx
0x140006049  mov     rcx, rax; StartContext
0x14000604c  call    ??0?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@JAEAJJJ@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>(long,long &,long,long)
0x140006051  lea     rcx, [rdi+0D8h]; StartContext
0x140006058  mov     edx, 2
0x14000605d  lea     r8, [rsp+38h+arg_8]
0x140006062  call    ??0?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@JAEAJJJ@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>(long,long &,long,long)
0x140006067  jmp     short loc_14000606B
0x140006069  xor     edi, edi
0x14000606b  mov     edx, 18h
0x140006070  mov     ecx, 100h
0x140006075  mov     r8d, 66446753h
0x14000607b  call    cs:__imp_ExAllocatePool2
0x140006082  nop     dword ptr [rax+rax+00h]
0x140006087  mov     rcx, rax
0x14000608a  test    rax, rax
0x14000608d  jz      short loc_1400060AD
0x14000608f  mov     eax, 1
0x140006094  mov     [rcx+10h], rdi
0x140006098  mov     [rcx+8], eax
0x14000609b  mov     [rcx+0Ch], eax
0x14000609e  lea     rax, ??_7?$sp_counted_impl_p@VPackageWriter@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::PackageWriter>::`vftable'
0x1400060a5  mov     [rcx], rax
0x1400060a8  mov     edx, [rcx+8]
0x1400060ab  jmp     short loc_1400060EE
0x1400060ad  test    rdi, rdi
0x1400060b0  jz      short loc_1400060EA
0x1400060b2  mov     rcx, rdi
0x1400060b5  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x1400060ba  lea     rbx, [rdi+0D8h]
0x1400060c1  mov     rcx, rbx
0x1400060c4  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x1400060c9  mov     rcx, rbx
0x1400060cc  call    ??1?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x1400060d1  mov     rcx, rdi
0x1400060d4  call    ??1?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x1400060d9  xor     edx, edx; Tag
0x1400060db  mov     rcx, rdi; P
0x1400060de  call    cs:__imp_ExFreePoolWithTag
0x1400060e5  nop     dword ptr [rax+rax+00h]
0x1400060ea  xor     edx, edx
0x1400060ec  xor     ecx, ecx
0x1400060ee  mov     rbx, [rsi+8]
0x1400060f2  xor     eax, eax
0x1400060f4  test    edx, edx
0x1400060f6  mov     [rsi+8], rcx
0x1400060fa  cmovnz  rax, rdi
0x1400060fe  mov     [rsi], rax
0x140006101  test    rbx, rbx
0x140006104  jz      short loc_14000613D
0x140006106  or      edi, 0FFFFFFFFh
0x140006109  mov     eax, edi
0x14000610b  lock xadd [rbx+8], eax
0x140006110  add     eax, edi
0x140006112  jnz     short loc_14000613D
0x140006114  mov     rax, [rbx]
0x140006117  mov     rcx, rbx
0x14000611a  mov     rax, [rax+8]
0x14000611e  call    _guard_dispatch_icall
0x140006123  mov     eax, edi
0x140006125  lock xadd [rbx+0Ch], eax
0x14000612a  add     eax, edi
0x14000612c  jnz     short loc_14000613D
0x14000612e  mov     rax, [rbx]
0x140006131  mov     rcx, rbx
0x140006134  mov     rax, [rax+10h]
0x140006138  call    _guard_dispatch_icall
0x14000613d  mov     rbx, [rsp+38h+arg_0]
0x140006142  xor     eax, eax
0x140006144  mov     rsi, [rsp+38h+arg_10]
0x140006149  add     rsp, 30h
0x14000614d  pop     rdi
0x14000614e  retn
```
