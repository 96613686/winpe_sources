# appv::shared::kernel::device_io_call<vemgr::vemgr_pool_info>::~device_io_call<vemgr::vemgr_pool_info>(void)

- ea: `0x1800050a0`
- end: `0x180005171`
- name: `??1?$device_io_call@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000456c`

## callees

- `0x1800050a0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18000511c`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000511c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005154`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005154`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005128`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005128`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800050d4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800050d4`
- `ntoskrnl!ObfDereferenceObject` at `0x1800050f3`
- `ntoskrnl!ObfDereferenceObject` at `0x1800050f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800050bc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800050bc`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000513d`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000513d`

## pseudocode

```c
void __fastcall appv::shared::kernel::device_io_call<vemgr::vemgr_pool_info>::~device_io_call<vemgr::vemgr_pool_info>(
        __int64 a1)
{
  bool v1; // di
  void *v3; // rcx
  struct _ERESOURCE *v4; // rcx
  struct _ERESOURCE *v5; // rcx
  void *v6; // rcx

  v1 = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    KeEnterCriticalRegion();
    v1 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 24), 1u) == 1;
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    ObfDereferenceObject(v3);
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)a1 = 0;
  }
  if ( v1 )
  {
    v4 = *(struct _ERESOURCE **)(a1 + 24);
    if ( v4 )
    {
      ExReleaseResourceLite(v4);
      KeLeaveCriticalRegion();
    }
  }
  v5 = *(struct _ERESOURCE **)(a1 + 24);
  if ( v5 )
  {
    ExDeleteResourceLite(v5);
    v6 = *(void **)(a1 + 24);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
}

```

## disassembly

```asm
0x1800050a0  mov     [rsp+arg_0], rbx
0x1800050a5  mov     [rsp+arg_8], rsi
0x1800050aa  push    rdi
0x1800050ab  sub     rsp, 20h
0x1800050af  xor     dil, dil
0x1800050b2  mov     rbx, rcx
0x1800050b5  cmp     qword ptr [rcx+18h], 0
0x1800050ba  jz      short loc_1800050EA
0x1800050bc  call    cs:__imp_KeEnterCriticalRegion
0x1800050c3  nop     dword ptr [rax+rax+00h]
0x1800050c8  mov     rcx, [rbx+18h]; Resource
0x1800050cc  mov     esi, 1
0x1800050d1  mov     dl, sil; Wait
0x1800050d4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800050db  nop     dword ptr [rax+rax+00h]
0x1800050e0  cmp     al, sil
0x1800050e3  movzx   edi, dil
0x1800050e7  cmovz   edi, esi
0x1800050ea  mov     rcx, [rbx+8]; Object
0x1800050ee  test    rcx, rcx
0x1800050f1  jz      short loc_18000510E
0x1800050f3  call    cs:__imp_ObfDereferenceObject
0x1800050fa  nop     dword ptr [rax+rax+00h]
0x1800050ff  mov     qword ptr [rbx+8], 0
0x180005107  mov     qword ptr [rbx], 0
0x18000510e  test    dil, dil
0x180005111  jz      short loc_180005134
0x180005113  mov     rcx, [rbx+18h]; Resource
0x180005117  test    rcx, rcx
0x18000511a  jz      short loc_180005134
0x18000511c  call    cs:__imp_ExReleaseResourceLite
0x180005123  nop     dword ptr [rax+rax+00h]
0x180005128  call    cs:__imp_KeLeaveCriticalRegion
0x18000512f  nop     dword ptr [rax+rax+00h]
0x180005134  mov     rcx, [rbx+18h]; Resource
0x180005138  test    rcx, rcx
0x18000513b  jz      short loc_180005160
0x18000513d  call    cs:__imp_ExDeleteResourceLite
0x180005144  nop     dword ptr [rax+rax+00h]
0x180005149  mov     rcx, [rbx+18h]; P
0x18000514d  test    rcx, rcx
0x180005150  jz      short loc_180005160
0x180005152  xor     edx, edx; Tag
0x180005154  call    cs:__imp_ExFreePoolWithTag
0x18000515b  nop     dword ptr [rax+rax+00h]
0x180005160  mov     rbx, [rsp+28h+arg_0]
0x180005165  mov     rsi, [rsp+28h+arg_8]
0x18000516a  add     rsp, 20h
0x18000516e  pop     rdi
0x18000516f  retn
```
