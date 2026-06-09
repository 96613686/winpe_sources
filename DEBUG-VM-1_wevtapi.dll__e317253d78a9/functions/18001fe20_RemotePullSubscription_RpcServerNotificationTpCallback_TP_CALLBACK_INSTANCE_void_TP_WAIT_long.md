# RemotePullSubscription::RpcServerNotificationTpCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18001fe20`
- end: `0x18001ff0b`
- name: `?RpcServerNotificationTpCallback@RemotePullSubscription@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `235`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000108c`
- `0x18001fe20`
- `0x180023548`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fe63`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fea8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fe63`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ff04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fed1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fe56`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fe56`

## pseudocode

```c
void __fastcall RemotePullSubscription::RpcServerNotificationTpCallback(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _TP_WAIT *Ptr; // rcx
  DWORD LastError; // eax

  AcquireSRWLockExclusive(Context + 7);
  if ( !LOBYTE(Context[34].Ptr) )
  {
    Ptr = (struct _TP_WAIT *)Context[23].Ptr;
    if ( Ptr )
      SetThreadpoolWait(Ptr, Context[22].Ptr, 0);
  }
  SetEvent(Context[25].Ptr);
  if ( !LODWORD(Context[13].Ptr) && !LOBYTE(Context[34].Ptr) )
  {
    if ( (unsigned int)dword_18004B008 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18004B008,
        &unk_180043B05,
        &Context[29]);
    if ( !SetEvent(Context[24].Ptr)
      && WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids, LastError);
    }
  }
  ReleaseSRWLockExclusive(Context + 7);
}

```

## disassembly

```asm
0x18001fe20  mov     [rsp+arg_0], rbx
0x18001fe25  push    rdi
0x18001fe26  sub     rsp, 20h
0x18001fe2a  lea     rcx, [rdx+38h]; SRWLock
0x18001fe2e  mov     rbx, rdx
0x18001fe31  call    cs:__imp_AcquireSRWLockExclusive
0x18001fe37  cmp     byte ptr [rbx+110h], 0
0x18001fe3e  jnz     short loc_18001FE5C
0x18001fe40  mov     rcx, [rbx+0B8h]; pwa
0x18001fe47  test    rcx, rcx
0x18001fe4a  jz      short loc_18001FE5C
0x18001fe4c  mov     rdx, [rbx+0B0h]; h
0x18001fe53  xor     r8d, r8d; pftTimeout
0x18001fe56  call    cs:__imp_SetThreadpoolWait
0x18001fe5c  mov     rcx, [rbx+0C8h]; hEvent
0x18001fe63  call    cs:__imp_SetEvent
0x18001fe69  cmp     dword ptr [rbx+68h], 0
0x18001fe6d  jnz     loc_18001FEF6
0x18001fe73  cmp     byte ptr [rbx+110h], 0
0x18001fe7a  jnz     short loc_18001FEF6
0x18001fe7c  mov     eax, cs:dword_18004B008
0x18001fe82  cmp     eax, 5
0x18001fe85  jbe     short loc_18001FEA1
0x18001fe87  lea     r8, [rbx+0E8h]
0x18001fe8e  lea     rdx, unk_180043B05
0x18001fe95  lea     rcx, dword_18004B008
0x18001fe9c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001fea1  mov     rcx, [rbx+0C0h]; hEvent
0x18001fea8  call    cs:__imp_SetEvent
0x18001feae  test    eax, eax
0x18001feb0  jnz     short loc_18001FEF6
0x18001feb2  mov     rax, cs:WPP_GLOBAL_Control
0x18001feb9  lea     rcx, WPP_GLOBAL_Control
0x18001fec0  cmp     rax, rcx
0x18001fec3  jz      short loc_18001FEF6
0x18001fec5  test    byte ptr [rax+1Ch], 80h
0x18001fec9  jz      short loc_18001FEF6
0x18001fecb  cmp     byte ptr [rax+19h], 2
0x18001fecf  jb      short loc_18001FEF6
0x18001fed1  call    cs:__imp_GetLastError
0x18001fed7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fede  lea     r8, WPP_158a74e732e63b8ecd72ac50aa116150_Traceguids
0x18001fee5  mov     edx, 1Ch
0x18001feea  mov     r9d, eax
0x18001feed  mov     rcx, [rcx+10h]
0x18001fef1  call    WPP_SF_D
0x18001fef6  lea     rcx, [rbx+38h]
0x18001fefa  mov     rbx, [rsp+28h+arg_0]
0x18001feff  add     rsp, 20h
0x18001ff03  pop     rdi
0x18001ff04  jmp     cs:__imp_ReleaseSRWLockExclusive
```
