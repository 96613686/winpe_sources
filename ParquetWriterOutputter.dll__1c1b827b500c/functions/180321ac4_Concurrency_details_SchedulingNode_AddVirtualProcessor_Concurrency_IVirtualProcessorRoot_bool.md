# Concurrency::details::SchedulingNode::AddVirtualProcessor(Concurrency::IVirtualProcessorRoot *,bool)

- ea: `0x180321ac4`
- end: `0x180321c16`
- name: `?AddVirtualProcessor@SchedulingNode@details@Concurrency@@QEAAPEAVVirtualProcessor@23@PEAUIVirtualProcessorRoot@3@_N@Z`
- size: `338`
- prototype: `struct Concurrency::details::VirtualProcessor *__fastcall(Concurrency::details::SchedulingNode *__hidden this, struct Concurrency::IVirtualProcessorRoot *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180315e14`
- `0x180321020`

## callees

- `0x180083490`
- `0x180316a0c`
- `0x180319d68`
- `0x180320e88`
- `0x180320f24`
- `0x180321944`
- `0x180321ac4`
- `0x180358070`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x180321af4`
- `KERNEL32!InterlockedPopEntrySList` at `0x180321af4`

## pseudocode

```c
struct Concurrency::details::VirtualProcessor *__fastcall Concurrency::details::SchedulingNode::AddVirtualProcessor(
        Concurrency::details::SchedulingNode *this,
        struct Concurrency::IVirtualProcessorRoot *a2,
        char a3)
{
  union _SLIST_HEADER *v6; // rbp
  struct Concurrency::details::ContextBase *v7; // rsi
  PSLIST_ENTRY v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx

  v6 = (union _SLIST_HEADER *)((char *)this + 80);
  v7 = Concurrency::details::SchedulerBase::FastCurrentContext();
  v8 = InterlockedPopEntrySList(v6);
  if ( !v8 || (v9 = (__int64)&v8[-18], v8 == (PSLIST_ENTRY)288) )
    v9 = (*(__int64 (__fastcall **)(_QWORD, Concurrency::details::SchedulingNode *, struct Concurrency::IVirtualProcessorRoot *))(**(_QWORD **)this + 184LL))(
           *(_QWORD *)this,
           this,
           a2);
  else
    (*(void (__fastcall **)(__int64, Concurrency::details::SchedulingNode *, struct Concurrency::IVirtualProcessorRoot *))(*(_QWORD *)v9 + 48LL))(
      v9,
      this,
      a2);
  if ( a3 )
  {
    *(_BYTE *)(v9 + 256) = 1;
    *(_QWORD *)(v9 + 264) = (char *)v7 - 16;
    *((_QWORD *)v7 + 32) = v9;
  }
  _InterlockedIncrement((volatile signed __int32 *)this + 14);
  Concurrency::details::ReferenceCountedQuickBitSet::InterlockedSet(
    (Concurrency::details::ReferenceCountedQuickBitSet *)(*(_QWORD *)this + 72LL),
    *(_DWORD *)(v9 + 212));
  if ( *(_DWORD *)(*(_QWORD *)this + 676LL) == *(_DWORD *)(*(_QWORD *)this + 680LL)
    && *(int *)(*(_QWORD *)this + 28LL) > 0 )
  {
    Concurrency::details::ListArray<Concurrency::details::VirtualProcessor>::Add((char *)this + 80, v9);
    if ( Concurrency::details::SchedulerBase::VirtualProcessorActive(*(Concurrency::details::SchedulerBase **)this, 1) )
    {
      if ( v7 )
        v10 = parquet::TypedStatisticsImpl<parquet::PhysicalType<2>>::num_values(v7);
      else
        v10 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 56LL))(v9, v10, 0);
    }
  }
  else
  {
    Concurrency::details::ListArray<Concurrency::details::VirtualProcessor>::Add((char *)this + 80, v9);
    Concurrency::details::VirtualProcessor::MakeAvailable(v9, 1);
  }
  return (struct Concurrency::details::VirtualProcessor *)v9;
}

```

## disassembly

```asm
0x180321ac4  mov     [rsp+arg_0], rbx
0x180321ac9  mov     [rsp+arg_8], rbp
0x180321ace  mov     [rsp+arg_10], rsi
0x180321ad3  push    rdi
0x180321ad4  push    r14
0x180321ad6  push    r15
0x180321ad8  sub     rsp, 20h
0x180321adc  mov     r15b, r8b
0x180321adf  mov     r14, rdx
0x180321ae2  mov     rdi, rcx
0x180321ae5  call    ?FastCurrentContext@SchedulerBase@details@Concurrency@@SAPEAVContextBase@23@XZ
0x180321aea  lea     rbp, [rdi+50h]
0x180321aee  mov     rsi, rax
0x180321af1  mov     rcx, rbp; ListHead
0x180321af4  call    cs:__imp_InterlockedPopEntrySList
0x180321afa  test    rax, rax
0x180321afd  jz      short loc_180321B23
0x180321aff  lea     rbx, [rax-120h]
0x180321b06  test    rbx, rbx
0x180321b09  jz      short loc_180321B23
0x180321b0b  mov     rcx, [rbx]
0x180321b0e  mov     r8, r14
0x180321b11  mov     rdx, rdi
0x180321b14  mov     rax, [rcx+30h]
0x180321b18  mov     rcx, rbx
0x180321b1b  call    cs:__guard_dispatch_icall_fptr
0x180321b21  jmp     short loc_180321B3F
0x180321b23  mov     rcx, [rdi]
0x180321b26  mov     r8, r14
0x180321b29  mov     rdx, rdi
0x180321b2c  mov     rax, [rcx]
0x180321b2f  mov     rax, [rax+0B8h]
0x180321b36  call    cs:__guard_dispatch_icall_fptr
0x180321b3c  mov     rbx, rax
0x180321b3f  test    r15b, r15b
0x180321b42  jz      short loc_180321B5D
0x180321b44  lea     rcx, [rsi-10h]
0x180321b48  mov     byte ptr [rbx+100h], 1
0x180321b4f  mov     [rbx+108h], rcx
0x180321b56  mov     [rsi+100h], rbx
0x180321b5d  lock inc dword ptr [rdi+38h]
0x180321b61  mov     rcx, [rdi]
0x180321b64  mov     edx, [rbx+0D4h]; unsigned int
0x180321b6a  add     rcx, 48h ; 'H'; this
0x180321b6e  call    ?InterlockedSet@ReferenceCountedQuickBitSet@details@Concurrency@@QEAAII@Z
0x180321b73  mov     rax, [rdi]
0x180321b76  mov     r9d, [rax+2A8h]
0x180321b7d  mov     rax, [rdi]
0x180321b80  mov     r8d, [rax+2A4h]
0x180321b87  cmp     r8d, r9d
0x180321b8a  jnz     short loc_180321BE0
0x180321b8c  mov     rax, [rdi]
0x180321b8f  mov     r8d, [rax+1Ch]
0x180321b93  test    r8d, r8d
0x180321b96  jle     short loc_180321BE0
0x180321b98  mov     rdx, rbx
0x180321b9b  mov     rcx, rbp
0x180321b9e  call    ?Add@?$ListArray@VVirtualProcessor@details@Concurrency@@@details@Concurrency@@QEAAHPEAVVirtualProcessor@23@@Z
0x180321ba3  mov     rcx, [rdi]; this
0x180321ba6  mov     dl, 1; bool
0x180321ba8  call    ?VirtualProcessorActive@SchedulerBase@details@Concurrency@@QEAA_N_N@Z
0x180321bad  test    al, al
0x180321baf  jz      short loc_180321BFA
0x180321bb1  test    rsi, rsi
0x180321bb4  jz      short loc_180321BC3
0x180321bb6  mov     rcx, rsi
0x180321bb9  call    ?num_values@?$TypedStatisticsImpl@U?$PhysicalType@$01@parquet@@@parquet@@UEBA_JXZ
0x180321bbe  mov     rdx, rax
0x180321bc1  jmp     short loc_180321BCB
0x180321bc3  mov     rax, [rdi+8]
0x180321bc7  mov     rdx, [rax+10h]
0x180321bcb  mov     rax, [rbx]
0x180321bce  xor     r8d, r8d
0x180321bd1  mov     rcx, rbx
0x180321bd4  mov     rax, [rax+38h]
0x180321bd8  call    cs:__guard_dispatch_icall_fptr
0x180321bde  jmp     short loc_180321BFA
0x180321be0  mov     rdx, rbx
0x180321be3  mov     rcx, rbp
0x180321be6  call    ?Add@?$ListArray@VVirtualProcessor@details@Concurrency@@@details@Concurrency@@QEAAHPEAVVirtualProcessor@23@@Z
0x180321beb  xor     r8d, r8d
0x180321bee  mov     rcx, rbx
0x180321bf1  lea     edx, [r8+1]
0x180321bf5  call    ?MakeAvailable@VirtualProcessor@details@Concurrency@@IEAAXW4AvailabilityType@123@_N@Z
0x180321bfa  mov     rbp, [rsp+38h+arg_8]
0x180321bff  mov     rax, rbx
0x180321c02  mov     rbx, [rsp+38h+arg_0]
0x180321c07  mov     rsi, [rsp+38h+arg_10]
0x180321c0c  add     rsp, 20h
0x180321c10  pop     r15
0x180321c12  pop     r14
0x180321c14  pop     rdi
0x180321c15  retn
```
