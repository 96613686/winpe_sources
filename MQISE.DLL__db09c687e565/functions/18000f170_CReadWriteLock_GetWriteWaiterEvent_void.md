# CReadWriteLock::GetWriteWaiterEvent(void)

- ea: `0x18000f170`
- end: `0x18000f20c`
- name: `?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ`
- size: `156`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002df0`
- `0x180003938`
- `0x18000f214`

## callees

- `0x180001c0c`
- `0x180003140`
- `0x18000dbb4`
- `0x18000f170`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000f1a2`
- `KERNEL32!CloseHandle` at `0x18000f1a2`
- `KERNEL32!CreateEventW` at `0x18000f18a`
- `KERNEL32!CreateEventW` at `0x18000f18a`
- `KERNEL32!GetLastError` at `0x18000f1cb`
- `KERNEL32!GetLastError` at `0x18000f1cb`

## pseudocode

```c
void *__fastcall CReadWriteLock::GetWriteWaiterEvent(CReadWriteLock *this)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, LastError);
      }
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 2, (signed __int64)EventW, 0) )
      CloseHandle(EventW);
  }
  return (void *)*((_QWORD *)this + 2);
}

```

## disassembly

```asm
0x18000f170  push    rbx
0x18000f172  sub     rsp, 40h
0x18000f176  cmp     qword ptr [rcx+10h], 0
0x18000f17b  mov     rbx, rcx
0x18000f17e  jnz     short loc_18000F1A8
0x18000f180  xor     r9d, r9d; lpName
0x18000f183  xor     r8d, r8d; bInitialState
0x18000f186  xor     edx, edx; bManualReset
0x18000f188  xor     ecx, ecx; lpEventAttributes
0x18000f18a  call    cs:__imp_CreateEventW
0x18000f190  mov     rcx, rax; hObject
0x18000f193  test    rax, rax
0x18000f196  jz      short loc_18000F1B2
0x18000f198  xor     eax, eax
0x18000f19a  lock cmpxchg [rbx+10h], rcx
0x18000f1a0  jz      short loc_18000F1A8
0x18000f1a2  call    cs:__imp_CloseHandle
0x18000f1a8  mov     rax, [rbx+10h]
0x18000f1ac  add     rsp, 40h
0x18000f1b0  pop     rbx
0x18000f1b1  retn
0x18000f1b2  mov     rax, cs:WPP_GLOBAL_Control
0x18000f1b9  lea     rcx, WPP_GLOBAL_Control
0x18000f1c0  cmp     rax, rcx
0x18000f1c3  jz      short loc_18000F1F0
0x18000f1c5  test    byte ptr [rax+1Ch], 1
0x18000f1c9  jz      short loc_18000F1F0
0x18000f1cb  call    cs:__imp_GetLastError
0x18000f1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1d8  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x18000f1df  mov     edx, 0Fh
0x18000f1e4  mov     r9d, eax
0x18000f1e7  mov     rcx, [rcx+10h]
0x18000f1eb  call    WPP_SF_d
0x18000f1f0  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000f1f5  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000f1fa  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f201  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f206  call    _CxxThrowException_0
```
