# WiFiTaskPipeClient::Stop(void)

- ea: `0x14000a6b4`
- end: `0x14000a747`
- name: `?Stop@WiFiTaskPipeClient@@QEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(WiFiTaskPipeClient *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000a4a0`
- `0x14000c7b0`

## callees

- `0x14000a6b4`
- `0x14000bef0`
- `0x14000e4cc`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14000a71e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14000a71e`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::Stop(WiFiTaskPipeClient *this)
{
  __int64 v2; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
  }
  Synchronizer::EnqueueEvent(
    *(Synchronizer **)(*((_QWORD *)this + 2) + 8LL),
    *((struct SynchronizedObject **)this + 2),
    3u,
    0,
    0);
  v2 = *((_QWORD *)this + 2);
  CloseThreadpoolCleanupGroupMembers(*(PTP_CLEANUP_GROUP *)(v2 + 1544), 0, 0);
  *(_BYTE *)(v2 + 1552) = 1;
  (*(void (__fastcall **)(WiFiTaskPipeClient *))(*(_QWORD *)this + 32LL))(this);
  return 0;
}

```

## disassembly

```asm
0x14000a6b4  mov     [rsp+arg_0], rbx
0x14000a6b9  push    rdi
0x14000a6ba  sub     rsp, 30h
0x14000a6be  mov     rdi, rcx
0x14000a6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6c8  lea     rax, WPP_GLOBAL_Control
0x14000a6cf  cmp     rcx, rax
0x14000a6d2  jz      short loc_14000A6EE
0x14000a6d4  cmp     byte ptr [rcx+19h], 5
0x14000a6d8  jb      short loc_14000A6EE
0x14000a6da  test    byte ptr [rcx+1Ch], 1
0x14000a6de  jz      short loc_14000A6EE
0x14000a6e0  mov     rcx, [rcx+10h]
0x14000a6e4  mov     edx, 1Bh
0x14000a6e9  call    WPP_SF_
0x14000a6ee  mov     rcx, [rdi+10h]
0x14000a6f2  xor     r9d, r9d; void *
0x14000a6f5  mov     rdx, rcx; struct SynchronizedObject *
0x14000a6f8  mov     [rsp+38h+var_18], 0; void *
0x14000a701  mov     rcx, [rcx+8]; this
0x14000a705  lea     r8d, [r9+3]; int
0x14000a709  call    ?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z; Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)
0x14000a70e  mov     rbx, [rdi+10h]
0x14000a712  xor     r8d, r8d; pvCleanupContext
0x14000a715  xor     edx, edx; fCancelPendingCallbacks
0x14000a717  mov     rcx, [rbx+608h]; ptpcg
0x14000a71e  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x14000a724  mov     byte ptr [rbx+610h], 1
0x14000a72b  mov     rcx, rdi
0x14000a72e  mov     rax, [rdi]
0x14000a731  mov     rax, [rax+20h]
0x14000a735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a73a  mov     rbx, [rsp+38h+arg_0]
0x14000a73f  xor     eax, eax
0x14000a741  add     rsp, 30h
0x14000a745  pop     rdi
0x14000a746  retn
```
