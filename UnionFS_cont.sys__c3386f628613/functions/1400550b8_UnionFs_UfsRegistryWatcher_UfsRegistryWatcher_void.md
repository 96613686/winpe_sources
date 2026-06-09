# UnionFs::UfsRegistryWatcher::~UfsRegistryWatcher(void)

- ea: `0x1400550b8`
- end: `0x1400551c3`
- name: `??1UfsRegistryWatcher@UnionFs@@QEAA@XZ`
- size: `267`
- prototype: `void __fastcall(UnionFs::UfsRegistryWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14003de50`
- `0x1400551cc`

## callees

- `0x1400550b8`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140055139`
- `ntoskrnl!KeDelayExecutionThread` at `0x140055139`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400550f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005511b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055171`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400550f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005511b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055171`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055196`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400551ab`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400551ab`
- `ntoskrnl!ZwClose` at `0x14005510a`
- `ntoskrnl!ZwClose` at `0x140055185`
- `ntoskrnl!ZwClose` at `0x14005510a`
- `ntoskrnl!ZwClose` at `0x140055185`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400550ce`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400550ce`

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
0x1400550b8  mov     [rsp+arg_8], rbx
0x1400550bd  push    rdi
0x1400550be  sub     rsp, 20h
0x1400550c2  mov     rbx, rcx
0x1400550c5  mov     rcx, [rcx+20h]; RunRef
0x1400550c9  test    rcx, rcx
0x1400550cc  jz      short loc_1400550DA
0x1400550ce  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400550d5  nop     dword ptr [rax+rax+00h]
0x1400550da  mov     rdi, [rbx+28h]
0x1400550de  mov     qword ptr [rbx+28h], 0
0x1400550e6  test    rdi, rdi
0x1400550e9  jz      short loc_140055127
0x1400550eb  mov     rcx, [rdi+8]; P
0x1400550ef  test    rcx, rcx
0x1400550f2  jz      short loc_140055102
0x1400550f4  xor     edx, edx; Tag
0x1400550f6  call    cs:__imp_ExFreePoolWithTag
0x1400550fd  nop     dword ptr [rax+rax+00h]
0x140055102  mov     rcx, [rdi]; Handle
0x140055105  test    rcx, rcx
0x140055108  jz      short loc_140055116
0x14005510a  call    cs:__imp_ZwClose
0x140055111  nop     dword ptr [rax+rax+00h]
0x140055116  xor     edx, edx; Tag
0x140055118  mov     rcx, rdi; P
0x14005511b  call    cs:__imp_ExFreePoolWithTag
0x140055122  nop     dword ptr [rax+rax+00h]
0x140055127  lea     r8, [rsp+28h+Interval]; Interval
0x14005512c  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFF0BDC0h
0x140055135  xor     edx, edx; Alertable
0x140055137  xor     ecx, ecx; WaitMode
0x140055139  call    cs:__imp_KeDelayExecutionThread
0x140055140  nop     dword ptr [rax+rax+00h]
0x140055145  mov     rcx, [rbx+0A0h]
0x14005514c  test    rcx, rcx
0x14005514f  jz      short loc_14005515D
0x140055151  mov     rax, [rcx]
0x140055154  mov     rax, [rax+18h]
0x140055158  call    _guard_dispatch_icall
0x14005515d  mov     rdi, [rbx+28h]
0x140055161  test    rdi, rdi
0x140055164  jz      short loc_1400551A2
0x140055166  mov     rcx, [rdi+8]; P
0x14005516a  test    rcx, rcx
0x14005516d  jz      short loc_14005517D
0x14005516f  xor     edx, edx; Tag
0x140055171  call    cs:__imp_ExFreePoolWithTag
0x140055178  nop     dword ptr [rax+rax+00h]
0x14005517d  mov     rcx, [rdi]; Handle
0x140055180  test    rcx, rcx
0x140055183  jz      short loc_140055191
0x140055185  call    cs:__imp_ZwClose
0x14005518c  nop     dword ptr [rax+rax+00h]
0x140055191  xor     edx, edx; Tag
0x140055193  mov     rcx, rdi; P
0x140055196  call    cs:__imp_ExFreePoolWithTag
0x14005519d  nop     dword ptr [rax+rax+00h]
0x1400551a2  mov     rcx, [rbx+20h]; RunRefCacheAware
0x1400551a6  test    rcx, rcx
0x1400551a9  jz      short loc_1400551B7
0x1400551ab  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400551b2  nop     dword ptr [rax+rax+00h]
0x1400551b7  mov     rbx, [rsp+28h+arg_8]
0x1400551bc  add     rsp, 20h
0x1400551c0  pop     rdi
0x1400551c1  retn
```
