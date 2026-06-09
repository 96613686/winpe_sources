# FsDepRegisterUnregisterForBugchecks

- ea: `0x18000a32c`
- end: `0x18000a3f6`
- name: `FsDepRegisterUnregisterForBugchecks`
- size: `202`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008010`
- `0x18000db70`
- `0x180013078`

## callees

- `0x18000a32c`

## import_xrefs

- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x18000a390`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x18000a390`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x18000a3b4`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x18000a3b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a3de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a3de`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a3d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a3d2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a354`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a354`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a33f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a33f`

## pseudocode

```c
void __fastcall FsDepRegisterUnregisterForBugchecks(char a1, char a2)
{
  if ( !a2 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
  }
  if ( a1 )
  {
    if ( !byte_1800051CC )
    {
      CallbackRecord.State = 0;
      byte_1800051CC = KeRegisterBugCheckReasonCallback(
                         &CallbackRecord,
                         FsDepHandleBugcheck,
                         KbCallbackReserved1,
                         FsDependsBugcheckIdentifier);
    }
  }
  else if ( byte_1800051CC == 1 )
  {
    KeDeregisterBugCheckReasonCallback(&CallbackRecord);
    byte_1800051CC = 0;
  }
  if ( !a2 )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x18000a32c  mov     [rsp+arg_0], rbx
0x18000a331  push    rdi
0x18000a332  sub     rsp, 20h
0x18000a336  mov     bl, dl
0x18000a338  mov     dil, cl
0x18000a33b  test    dl, dl
0x18000a33d  jnz     short loc_18000A360
0x18000a33f  call    cs:__imp_KeEnterCriticalRegion
0x18000a346  nop     dword ptr [rax+rax+00h]
0x18000a34b  mov     dl, 1; Wait
0x18000a34d  lea     rcx, Resource; Resource
0x18000a354  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000a35b  nop     dword ptr [rax+rax+00h]
0x18000a360  test    dil, dil
0x18000a363  jz      short loc_18000A3A4
0x18000a365  cmp     cs:byte_1800051CC, 0
0x18000a36c  jnz     short loc_18000A3C7
0x18000a36e  lea     r9, FsDependsBugcheckIdentifier; "FsDepends.sys"
0x18000a375  mov     cs:CallbackRecord.State, 0
0x18000a37c  mov     r8d, 1; Reason
0x18000a382  lea     rdx, FsDepHandleBugcheck; CallbackRoutine
0x18000a389  lea     rcx, CallbackRecord; CallbackRecord
0x18000a390  call    cs:__imp_KeRegisterBugCheckReasonCallback
0x18000a397  nop     dword ptr [rax+rax+00h]
0x18000a39c  mov     cs:byte_1800051CC, al
0x18000a3a2  jmp     short loc_18000A3C7
0x18000a3a4  cmp     cs:byte_1800051CC, 1
0x18000a3ab  jnz     short loc_18000A3C7
0x18000a3ad  lea     rcx, CallbackRecord; CallbackRecord
0x18000a3b4  call    cs:__imp_KeDeregisterBugCheckReasonCallback
0x18000a3bb  nop     dword ptr [rax+rax+00h]
0x18000a3c0  mov     cs:byte_1800051CC, 0
0x18000a3c7  test    bl, bl
0x18000a3c9  jnz     short loc_18000A3EA
0x18000a3cb  lea     rcx, Resource; Resource
0x18000a3d2  call    cs:__imp_ExReleaseResourceLite
0x18000a3d9  nop     dword ptr [rax+rax+00h]
0x18000a3de  call    cs:__imp_KeLeaveCriticalRegion
0x18000a3e5  nop     dword ptr [rax+rax+00h]
0x18000a3ea  mov     rbx, [rsp+28h+arg_0]
0x18000a3ef  add     rsp, 20h
0x18000a3f3  pop     rdi
0x18000a3f4  retn
```
