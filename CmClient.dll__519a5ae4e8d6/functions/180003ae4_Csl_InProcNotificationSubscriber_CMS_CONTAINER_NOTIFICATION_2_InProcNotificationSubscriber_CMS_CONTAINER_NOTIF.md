# Csl::InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::~InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>(void)

- ea: `0x180003ae4`
- end: `0x180003b4e`
- name: `??1?$InProcNotificationSubscriber@U_CMS_CONTAINER_NOTIFICATION@@$01@Csl@@QEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003bc4`
- `0x180005540`

## callees

- `0x180003ae4`
- `0x180006f7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180003b37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180003b37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180003b14`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180003b14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b02`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Csl::InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>::~InProcNotificationSubscriber<_CMS_CONTAINER_NOTIFICATION,2>(
        __int64 a1)
{
  __int64 v2; // rsi
  int v3; // ebx
  utl::_RefCountBase *v4; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v3 = *(_DWORD *)(v2 + 108);
    if ( v3 == GetCurrentThreadId() )
      *(_BYTE *)(v2 + 113) = 1;
    else
      WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)a1, 1);
  }
  v4 = *(utl::_RefCountBase **)(a1 + 16);
  if ( v4 )
    utl::_RefCountBase::_DecStrong(v4);
  if ( *(_QWORD *)a1 )
    CloseThreadpoolWork(*(PTP_WORK *)a1);
}

```

## disassembly

```asm
0x180003ae4  mov     [rsp+arg_0], rbx
0x180003ae9  mov     [rsp+arg_8], rsi
0x180003aee  push    rdi
0x180003aef  sub     rsp, 20h
0x180003af3  mov     rdi, rcx
0x180003af6  mov     rsi, [rcx+8]
0x180003afa  test    rsi, rsi
0x180003afd  jz      short loc_180003B20
0x180003aff  mov     ebx, [rsi+6Ch]
0x180003b02  call    cs:__imp_GetCurrentThreadId
0x180003b08  cmp     ebx, eax
0x180003b0a  jz      short loc_180003B1C
0x180003b0c  mov     edx, 1; fCancelPendingCallbacks
0x180003b11  mov     rcx, [rdi]; pwk
0x180003b14  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180003b1a  jmp     short loc_180003B20
0x180003b1c  mov     byte ptr [rsi+71h], 1
0x180003b20  mov     rcx, [rdi+10h]; this
0x180003b24  test    rcx, rcx
0x180003b27  jz      short loc_180003B2F
0x180003b29  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180003b2e  nop
0x180003b2f  mov     rcx, [rdi]; pwk
0x180003b32  test    rcx, rcx
0x180003b35  jz      short loc_180003B3E
0x180003b37  call    cs:__imp_CloseThreadpoolWork
0x180003b3d  nop
0x180003b3e  mov     rbx, [rsp+28h+arg_0]
0x180003b43  mov     rsi, [rsp+28h+arg_8]
0x180003b48  add     rsp, 20h
0x180003b4c  pop     rdi
0x180003b4d  retn
```
