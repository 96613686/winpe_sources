# ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)

- ea: `0x1800d3b3c`
- end: `0x1800d3bed`
- name: `??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(ShieldProvider::CRPCTimeoutEx *__hidden this, DWORD DueTime, const unsigned __int16 *)`
- caller_count: `70`
- callee_count: `4`
- tags: ``

## callers

- `0x180015600`
- `0x180018c7c`
- `0x18001a154`
- `0x18001a504`
- `0x1800299ec`
- `0x18002a9f8`
- `0x18002aab4`
- `0x18002b6b8`
- `0x18002b94c`
- `0x18002bfe8`
- `0x18002d9b0`
- `0x18002da74`
- `0x180035e58`
- `0x180036b9c`
- `0x180044018`
- `0x1800451b8`
- `0x180047454`
- `0x18004b544`
- `0x18004bba4`
- `0x18004c2bc`
- `0x18004c384`
- `0x18004e530`
- `0x180050a84`
- `0x180050c2c`
- `0x180050dd4`
- `0x180050f80`
- `0x180052d1c`
- `0x180053670`
- `0x18006768c`
- `0x18006d0f8`
- `0x180071480`
- `0x1800718cc`
- `0x1800753a0`
- `0x180076894`
- `0x1800772f0`
- `0x180078840`
- `0x180078cd0`
- `0x180078ddc`
- `0x180079090`
- `0x18007913c`
- `0x18007963c`
- `0x18007e278`
- `0x180084148`
- `0x180085474`
- `0x180085f08`
- `0x180086210`
- `0x180094db0`
- `0x1800b8320`
- `0x1800bd82c`
- `0x1800be518`

## callees

- `0x18000517c`
- `0x18000af28`
- `0x1800d3b3c`
- `0x1800d3d38`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800d3b4f`
- `KERNEL32!GetCurrentThreadId` at `0x1800d3b4f`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800d3baf`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800d3baf`
- `ole32!CoEnableCallCancellation` at `0x1800d3b7e`
- `ole32!CoEnableCallCancellation` at `0x1800d3b7e`

## pseudocode

```c
ShieldProvider::CRPCTimeoutEx *__fastcall ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
        ShieldProvider::CRPCTimeoutEx *this,
        DWORD DueTime,
        const unsigned __int16 *a3)
{
  DWORD CurrentThreadId; // eax
  DWORD v7; // ebp
  HRESULT v8; // eax

  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)this + 4) = 0;
  *(_DWORD *)this = CurrentThreadId;
  *((_DWORD *)this + 2) = -2147467259;
  *((_QWORD *)this + 2) = 0;
  CBaseRPCTimeout::Disarm(this);
  v7 = 5000;
  if ( DueTime )
    v7 = DueTime;
  v8 = CoEnableCallCancellation(0);
  *((_DWORD *)this + 2) = v8;
  if ( v8 >= 0 )
    CreateTimerQueueTimer((PHANDLE)this + 2, 0, CBaseRPCTimeout::s_Callback, this, v7, 0x3E8u, 0);
  *((_DWORD *)this + 6) = DueTime;
  memset_0((char *)this + 28, 0, 0xC8u);
  if ( a3 )
    StringCchCopyW((unsigned __int16 *)this + 14, 0x64u, a3);
  return this;
}

```

## disassembly

```asm
0x1800d3b3c  push    rbx
0x1800d3b3e  push    rbp
0x1800d3b3f  push    rsi
0x1800d3b40  push    rdi
0x1800d3b41  push    r14
0x1800d3b43  sub     rsp, 40h
0x1800d3b47  mov     rsi, r8
0x1800d3b4a  mov     edi, edx
0x1800d3b4c  mov     rbx, rcx
0x1800d3b4f  call    cs:__imp_GetCurrentThreadId
0x1800d3b55  mov     rcx, rbx; this
0x1800d3b58  mov     byte ptr [rbx+4], 0
0x1800d3b5c  mov     [rbx], eax
0x1800d3b5e  mov     dword ptr [rbx+8], 80004005h
0x1800d3b65  mov     qword ptr [rbx+10h], 0
0x1800d3b6d  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x1800d3b72  test    edi, edi
0x1800d3b74  mov     ebp, 1388h
0x1800d3b79  cmovnz  ebp, edi
0x1800d3b7c  xor     ecx, ecx; pReserved
0x1800d3b7e  call    cs:__imp_CoEnableCallCancellation
0x1800d3b84  mov     [rbx+8], eax
0x1800d3b87  test    eax, eax
0x1800d3b89  js      short loc_1800D3BB5
0x1800d3b8b  mov     [rsp+68h+Flags], 0; Flags
0x1800d3b93  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x1800d3b9a  mov     [rsp+68h+Period], 3E8h; Period
0x1800d3ba2  lea     rcx, [rbx+10h]; phNewTimer
0x1800d3ba6  mov     r9, rbx; Parameter
0x1800d3ba9  mov     [rsp+68h+DueTime], ebp; DueTime
0x1800d3bad  xor     edx, edx; TimerQueue
0x1800d3baf  call    cs:__imp_CreateTimerQueueTimer
0x1800d3bb5  xor     edx, edx; Val
0x1800d3bb7  mov     [rbx+18h], edi
0x1800d3bba  mov     r8d, 0C8h; Size
0x1800d3bc0  lea     rcx, [rbx+1Ch]; void *
0x1800d3bc4  call    memset_0
0x1800d3bc9  test    rsi, rsi
0x1800d3bcc  jz      short loc_1800D3BDF
0x1800d3bce  mov     r8, rsi; unsigned __int16 *
0x1800d3bd1  lea     rcx, [rbx+1Ch]; unsigned __int16 *
0x1800d3bd5  mov     edx, 64h ; 'd'; unsigned __int64
0x1800d3bda  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d3bdf  mov     rax, rbx
0x1800d3be2  add     rsp, 40h
0x1800d3be6  pop     r14
0x1800d3be8  pop     rdi
0x1800d3be9  pop     rsi
0x1800d3bea  pop     rbp
0x1800d3beb  pop     rbx
0x1800d3bec  retn
```
