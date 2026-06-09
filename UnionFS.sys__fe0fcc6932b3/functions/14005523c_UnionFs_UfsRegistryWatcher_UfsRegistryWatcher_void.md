# UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)

- ea: `0x14005523c`
- end: `0x140055347`
- name: `??1UfsRegistryWatcher@UnionFs@@QEAA@XZ`
- size: `267`
- prototype: `void __fastcall(UnionFs::UfsRegistryWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14003df70`
- `0x140055350`

## callees

- `0x14005523c`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400552bd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400552bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005527a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005529f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400552f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005531a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005527a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005529f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400552f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005531a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005532f`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005532f`
- `ntoskrnl!ZwClose` at `0x14005528e`
- `ntoskrnl!ZwClose` at `0x140055309`
- `ntoskrnl!ZwClose` at `0x14005528e`
- `ntoskrnl!ZwClose` at `0x140055309`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140055252`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140055252`

## pseudocode

```c
void __fastcall UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(UnionFs::UfsRegistryWatcher *this)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v2; // rcx
  __int64 v3; // rdi
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rdi
  void *v7; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v8; // rcx
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)this + 4);
  if ( v2 )
    ExWaitForRundownProtectionReleaseCacheAware(v2);
  v3 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v3 )
  {
    v4 = *(void **)(v3 + 8);
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    if ( *(_QWORD *)v3 )
      ZwClose(*(HANDLE *)v3);
    ExFreePoolWithTag((PVOID)v3, 0);
  }
  Interval.QuadPart = -1000000;
  KeDelayExecutionThread(0, 0, &Interval);
  v5 = *((_QWORD *)this + 20);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v6 = *((_QWORD *)this + 5);
  if ( v6 )
  {
    v7 = *(void **)(v6 + 8);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    if ( *(_QWORD *)v6 )
      ZwClose(*(HANDLE *)v6);
    ExFreePoolWithTag((PVOID)v6, 0);
  }
  v8 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)this + 4);
  if ( v8 )
    ExFreeCacheAwareRundownProtection(v8);
}

```

## disassembly

```asm
0x14005523c  mov     [rsp+arg_8], rbx
0x140055241  push    rdi
0x140055242  sub     rsp, 20h
0x140055246  mov     rbx, rcx
0x140055249  mov     rcx, [rcx+20h]; RunRef
0x14005524d  test    rcx, rcx
0x140055250  jz      short loc_14005525E
0x140055252  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140055259  nop     dword ptr [rax+rax+00h]
0x14005525e  mov     rdi, [rbx+28h]
0x140055262  mov     qword ptr [rbx+28h], 0
0x14005526a  test    rdi, rdi
0x14005526d  jz      short loc_1400552AB
0x14005526f  mov     rcx, [rdi+8]; P
0x140055273  test    rcx, rcx
0x140055276  jz      short loc_140055286
0x140055278  xor     edx, edx; Tag
0x14005527a  call    cs:__imp_ExFreePoolWithTag
0x140055281  nop     dword ptr [rax+rax+00h]
0x140055286  mov     rcx, [rdi]; Handle
0x140055289  test    rcx, rcx
0x14005528c  jz      short loc_14005529A
0x14005528e  call    cs:__imp_ZwClose
0x140055295  nop     dword ptr [rax+rax+00h]
0x14005529a  xor     edx, edx; Tag
0x14005529c  mov     rcx, rdi; P
0x14005529f  call    cs:__imp_ExFreePoolWithTag
0x1400552a6  nop     dword ptr [rax+rax+00h]
0x1400552ab  lea     r8, [rsp+28h+Interval]; Interval
0x1400552b0  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFF0BDC0h
0x1400552b9  xor     edx, edx; Alertable
0x1400552bb  xor     ecx, ecx; WaitMode
0x1400552bd  call    cs:__imp_KeDelayExecutionThread
0x1400552c4  nop     dword ptr [rax+rax+00h]
0x1400552c9  mov     rcx, [rbx+0A0h]
0x1400552d0  test    rcx, rcx
0x1400552d3  jz      short loc_1400552E1
0x1400552d5  mov     rax, [rcx]
0x1400552d8  mov     rax, [rax+18h]
0x1400552dc  call    _guard_dispatch_icall
0x1400552e1  mov     rdi, [rbx+28h]
0x1400552e5  test    rdi, rdi
0x1400552e8  jz      short loc_140055326
0x1400552ea  mov     rcx, [rdi+8]; P
0x1400552ee  test    rcx, rcx
0x1400552f1  jz      short loc_140055301
0x1400552f3  xor     edx, edx; Tag
0x1400552f5  call    cs:__imp_ExFreePoolWithTag
0x1400552fc  nop     dword ptr [rax+rax+00h]
0x140055301  mov     rcx, [rdi]; Handle
0x140055304  test    rcx, rcx
0x140055307  jz      short loc_140055315
0x140055309  call    cs:__imp_ZwClose
0x140055310  nop     dword ptr [rax+rax+00h]
0x140055315  xor     edx, edx; Tag
0x140055317  mov     rcx, rdi; P
0x14005531a  call    cs:__imp_ExFreePoolWithTag
0x140055321  nop     dword ptr [rax+rax+00h]
0x140055326  mov     rcx, [rbx+20h]; RunRefCacheAware
0x14005532a  test    rcx, rcx
0x14005532d  jz      short loc_14005533B
0x14005532f  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140055336  nop     dword ptr [rax+rax+00h]
0x14005533b  mov     rbx, [rsp+28h+arg_8]
0x140055340  add     rsp, 20h
0x140055344  pop     rdi
0x140055345  retn
```
