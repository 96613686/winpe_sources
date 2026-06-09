# MpAsyncShutdown

- ea: `0x140079540`
- end: `0x140079635`
- name: `MpAsyncShutdown`
- size: `245`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008e000`
- `0x14008f314`

## callees

- `0x14000970c`
- `0x1400794d4`
- `0x140079540`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140079606`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079606`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14007959b`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14007959b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400795ce`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400795e8`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400795ce`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400795e8`
- `ntoskrnl!KeBugCheck` at `0x140079628`
- `ntoskrnl!KeBugCheck` at `0x140079628`
- `ntoskrnl!ObfDereferenceObject` at `0x14007956b`
- `ntoskrnl!ObfDereferenceObject` at `0x14007956b`

## pseudocode

```c
void MpAsyncShutdown()
{
  PVOID v0; // rcx

  if ( MpAsync )
  {
    if ( *((_QWORD *)MpAsync + 5) )
    {
      MpAsyncpShutdownWorkerThreads();
      ObfDereferenceObject(*((PVOID *)MpAsync + 5));
      if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
      {
        if ( KdRefreshDebuggerNotPresent() )
          KeBugCheck(1u);
        __debugbreak();
      }
      *((_QWORD *)MpAsync + 5) = 0;
    }
    MpAsyncCleanupQueue();
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpAsync + 192));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)MpAsync + 3);
    v0 = MpAsync;
    *(_DWORD *)MpAsync = -1162151174;
    ExFreePoolWithTag(v0, 0x6461504Du);
    MpAsync = 0;
  }
}

```

## disassembly

```asm
0x140079540  sub     rsp, 28h
0x140079544  mov     rax, cs:MpAsync
0x14007954b  test    rax, rax
0x14007954e  jz      loc_14007961D
0x140079554  cmp     qword ptr [rax+28h], 0
0x140079559  jz      short loc_1400795BB
0x14007955b  call    MpAsyncpShutdownWorkerThreads
0x140079560  mov     rcx, cs:MpAsync
0x140079567  mov     rcx, [rcx+28h]; Object
0x14007956b  call    cs:__imp_ObfDereferenceObject
0x140079572  nop     dword ptr [rax+rax+00h]
0x140079577  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007957b  lock xadd cs:ObTotalReferences, rax
0x140079584  cmp     rax, 1
0x140079588  jns     short loc_1400795AC
0x14007958a  mov     rax, cs:MpData
0x140079591  mov     ecx, [rax+364h]
0x140079597  test    ecx, ecx
0x140079599  jns     short loc_1400795AC
0x14007959b  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400795a2  nop     dword ptr [rax+rax+00h]
0x1400795a7  test    al, al
0x1400795a9  jnz     short loc_140079623
0x1400795ab  int     3; Trap to Debugger
0x1400795ac  mov     rax, cs:MpAsync
0x1400795b3  mov     qword ptr [rax+28h], 0
0x1400795bb  call    MpAsyncCleanupQueue
0x1400795c0  mov     rcx, cs:MpAsync
0x1400795c7  add     rcx, 0C0h; Lookaside
0x1400795ce  call    cs:__imp_ExDeletePagedLookasideList
0x1400795d5  nop     dword ptr [rax+rax+00h]
0x1400795da  mov     rcx, cs:MpAsync
0x1400795e1  add     rcx, 180h; Lookaside
0x1400795e8  call    cs:__imp_ExDeletePagedLookasideList
0x1400795ef  nop     dword ptr [rax+rax+00h]
0x1400795f4  mov     rcx, cs:MpAsync; P
0x1400795fb  mov     edx, 6461504Dh; Tag
0x140079600  mov     dword ptr [rcx], 0BABAFAFAh
0x140079606  call    cs:__imp_ExFreePoolWithTag
0x14007960d  nop     dword ptr [rax+rax+00h]
0x140079612  mov     cs:MpAsync, 0
0x14007961d  add     rsp, 28h
0x140079621  retn
0x140079623  mov     ecx, 1; BugCheckCode
0x140079628  call    cs:__imp_KeBugCheck
```
