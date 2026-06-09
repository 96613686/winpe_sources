# BdeSvcWorkTracking::CancelAndWaitForOutstandingWorkImpl(void)

- ea: `0x18002f3f4`
- end: `0x18002f4cb`
- name: `?CancelAndWaitForOutstandingWorkImpl@BdeSvcWorkTracking@@AEAAXXZ`
- size: `215`
- prototype: `void __fastcall(PTP_CLEANUP_GROUP *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042f0`
- `0x18002f364`

## callees

- `0x180009f30`
- `0x18002f3f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002f481`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002f481`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002f46e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002f46e`

## pseudocode

```c
void __fastcall BdeSvcWorkTracking::CancelAndWaitForOutstandingWorkImpl(PTP_CLEANUP_GROUP *this)
{
  PVOID *v2; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this[20] )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
      WPP_SF_(v2[2], 30, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    CloseThreadpoolCleanupGroupMembers(this[20], 1, 0);
    CloseThreadpoolCleanupGroup(this[20]);
    this[20] = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 31, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
}

```

## disassembly

```asm
0x18002f3f4  mov     [rsp+arg_0], rbx
0x18002f3f9  push    rsi
0x18002f3fa  sub     rsp, 20h
0x18002f3fe  mov     rbx, rcx
0x18002f401  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f408  lea     rsi, WPP_GLOBAL_Control
0x18002f40f  cmp     rcx, rsi
0x18002f412  jz      short loc_18002F436
0x18002f414  test    byte ptr [rcx+1Ch], 20h
0x18002f418  jz      short loc_18002F436
0x18002f41a  mov     rcx, [rcx+10h]
0x18002f41e  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18002f425  mov     edx, 1Dh
0x18002f42a  call    WPP_SF_
0x18002f42f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f436  cmp     qword ptr [rbx+0A0h], 0
0x18002f43e  jz      short loc_18002F49F
0x18002f440  cmp     rcx, rsi
0x18002f443  jz      short loc_18002F460
0x18002f445  test    byte ptr [rcx+1Ch], 20h
0x18002f449  jz      short loc_18002F460
0x18002f44b  mov     rcx, [rcx+10h]
0x18002f44f  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18002f456  mov     edx, 1Eh
0x18002f45b  call    WPP_SF_
0x18002f460  mov     rcx, [rbx+0A0h]; ptpcg
0x18002f467  xor     r8d, r8d; pvCleanupContext
0x18002f46a  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18002f46e  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002f475  nop     dword ptr [rax+rax+00h]
0x18002f47a  mov     rcx, [rbx+0A0h]; ptpcg
0x18002f481  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002f488  nop     dword ptr [rax+rax+00h]
0x18002f48d  mov     qword ptr [rbx+0A0h], 0
0x18002f498  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f49f  cmp     rcx, rsi
0x18002f4a2  jz      short loc_18002F4BF
0x18002f4a4  test    byte ptr [rcx+1Ch], 20h
0x18002f4a8  jz      short loc_18002F4BF
0x18002f4aa  mov     rcx, [rcx+10h]
0x18002f4ae  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18002f4b5  mov     edx, 1Fh
0x18002f4ba  call    WPP_SF_
0x18002f4bf  mov     rbx, [rsp+28h+arg_0]
0x18002f4c4  add     rsp, 20h
0x18002f4c8  pop     rsi
0x18002f4c9  retn
```
