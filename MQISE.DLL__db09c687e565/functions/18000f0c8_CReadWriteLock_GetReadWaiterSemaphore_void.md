# CReadWriteLock::GetReadWaiterSemaphore(void)

- ea: `0x18000f0c8`
- end: `0x18000f167`
- name: `?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ`
- size: `159`
- prototype: `void *__fastcall(CReadWriteLock *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007988`
- `0x18000f214`

## callees

- `0x180001c0c`
- `0x180003140`
- `0x18000dbb4`
- `0x18000f0c8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000f0fd`
- `KERNEL32!CloseHandle` at `0x18000f0fd`
- `KERNEL32!CreateSemaphoreW` at `0x18000f0e5`
- `KERNEL32!CreateSemaphoreW` at `0x18000f0e5`
- `KERNEL32!GetLastError` at `0x18000f126`
- `KERNEL32!GetLastError` at `0x18000f126`

## pseudocode

```c
void *__fastcall CReadWriteLock::GetReadWaiterSemaphore(CReadWriteLock *this)
{
  HANDLE SemaphoreW; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 1) )
  {
    SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
    if ( !SemaphoreW )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, LastError);
      }
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)SemaphoreW, 0) )
      CloseHandle(SemaphoreW);
  }
  return (void *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x18000f0c8  push    rbx
0x18000f0ca  sub     rsp, 40h
0x18000f0ce  cmp     qword ptr [rcx+8], 0
0x18000f0d3  mov     rbx, rcx
0x18000f0d6  jnz     short loc_18000F103
0x18000f0d8  xor     r9d, r9d; lpName
0x18000f0db  xor     edx, edx; lInitialCount
0x18000f0dd  xor     ecx, ecx; lpSemaphoreAttributes
0x18000f0df  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18000f0e5  call    cs:__imp_CreateSemaphoreW
0x18000f0eb  mov     rcx, rax; hObject
0x18000f0ee  test    rax, rax
0x18000f0f1  jz      short loc_18000F10D
0x18000f0f3  xor     eax, eax
0x18000f0f5  lock cmpxchg [rbx+8], rcx
0x18000f0fb  jz      short loc_18000F103
0x18000f0fd  call    cs:__imp_CloseHandle
0x18000f103  mov     rax, [rbx+8]
0x18000f107  add     rsp, 40h
0x18000f10b  pop     rbx
0x18000f10c  retn
0x18000f10d  mov     rax, cs:WPP_GLOBAL_Control
0x18000f114  lea     rcx, WPP_GLOBAL_Control
0x18000f11b  cmp     rax, rcx
0x18000f11e  jz      short loc_18000F14B
0x18000f120  test    byte ptr [rax+1Ch], 1
0x18000f124  jz      short loc_18000F14B
0x18000f126  call    cs:__imp_GetLastError
0x18000f12c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f133  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x18000f13a  mov     edx, 0Eh
0x18000f13f  mov     r9d, eax
0x18000f142  mov     rcx, [rcx+10h]
0x18000f146  call    WPP_SF_d
0x18000f14b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000f150  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000f155  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f15c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f161  call    _CxxThrowException_0
```
