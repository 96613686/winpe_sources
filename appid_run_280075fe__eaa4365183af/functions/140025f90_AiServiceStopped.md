# AiServiceStopped

- ea: `0x140025f90`
- end: `0x14002607f`
- name: `AiServiceStopped`
- size: `239`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140021d30`
- `0x1400328e0`
- `0x140033f50`

## callees

- `0x140025f90`
- `0x14002b330`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140026016`
- `ntoskrnl!ObfDereferenceObject` at `0x140026016`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026065`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026065`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025fab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025fab`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025fc0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140025fc0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140026059`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140026059`
- `ntoskrnl!ZwClose` at `0x140026039`
- `ntoskrnl!ZwClose` at `0x140026039`

## pseudocode

```c
__int64 __fastcall AiServiceStopped(HANDLE a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  if ( AipServiceContextInitialized )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&AipServiceContext, 0);
    if ( !a1 || a1 == *(&TargetProcessHandle + 1) )
    {
      *(&TargetProcessHandle + 1) = 0;
      if ( Binding )
      {
        v1 = AiRpcDisconnect(&Binding);
        Binding = 0;
      }
      if ( *(&Binding + 1) )
      {
        ObfDereferenceObject(*(&Binding + 1));
        *(&Binding + 1) = 0;
      }
      if ( TargetProcessHandle )
      {
        ZwClose(TargetProcessHandle);
        TargetProcessHandle = 0;
      }
    }
    else
    {
      v1 = -1073741811;
    }
    ExReleasePushLockExclusiveEx(&AipServiceContext, 0);
    KeLeaveCriticalRegion();
  }
  return v1;
}

```

## disassembly

```asm
0x140025f90  mov     [rsp+arg_0], rbx
0x140025f95  push    rdi
0x140025f96  sub     rsp, 20h
0x140025f9a  xor     ebx, ebx
0x140025f9c  mov     rdi, rcx
0x140025f9f  cmp     cs:AipServiceContextInitialized, ebx
0x140025fa5  jz      loc_140026071
0x140025fab  call    cs:__imp_KeEnterCriticalRegion
0x140025fb2  nop     dword ptr [rax+rax+00h]
0x140025fb7  xor     edx, edx
0x140025fb9  lea     rcx, AipServiceContext
0x140025fc0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140025fc7  nop     dword ptr [rax+rax+00h]
0x140025fcc  test    rdi, rdi
0x140025fcf  jz      short loc_140025FE1
0x140025fd1  cmp     rdi, qword ptr cs:TargetProcessHandle+8
0x140025fd8  jz      short loc_140025FE1
0x140025fda  mov     ebx, 0C000000Dh
0x140025fdf  jmp     short loc_140026050
0x140025fe1  cmp     qword ptr cs:Binding, rbx
0x140025fe8  mov     qword ptr cs:TargetProcessHandle+8, rbx
0x140025fef  jz      short loc_14002600A
0x140025ff1  lea     rcx, Binding; Binding
0x140025ff8  call    AiRpcDisconnect
0x140025ffd  mov     ebx, eax
0x140025fff  mov     qword ptr cs:Binding, 0
0x14002600a  mov     rcx, qword ptr cs:Binding+8; Object
0x140026011  test    rcx, rcx
0x140026014  jz      short loc_14002602D
0x140026016  call    cs:__imp_ObfDereferenceObject
0x14002601d  nop     dword ptr [rax+rax+00h]
0x140026022  mov     qword ptr cs:Binding+8, 0
0x14002602d  mov     rcx, qword ptr cs:TargetProcessHandle; Handle
0x140026034  test    rcx, rcx
0x140026037  jz      short loc_140026050
0x140026039  call    cs:__imp_ZwClose
0x140026040  nop     dword ptr [rax+rax+00h]
0x140026045  mov     qword ptr cs:TargetProcessHandle, 0
0x140026050  xor     edx, edx
0x140026052  lea     rcx, AipServiceContext
0x140026059  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140026060  nop     dword ptr [rax+rax+00h]
0x140026065  call    cs:__imp_KeLeaveCriticalRegion
0x14002606c  nop     dword ptr [rax+rax+00h]
0x140026071  mov     eax, ebx
0x140026073  mov     rbx, [rsp+28h+arg_0]
0x140026078  add     rsp, 20h
0x14002607c  pop     rdi
0x14002607d  retn
```
