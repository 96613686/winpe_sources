# SCardReconnect

- ea: `0x180023640`
- end: `0x18002372c`
- name: `SCardReconnect`
- size: `236`
- prototype: `LONG __stdcall(SCARDHANDLE hCard, DWORD dwShareMode, DWORD dwPreferredProtocols, DWORD dwInitialization, LPDWORD pdwActiveProtocol)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180028ed8`

## callees

- `0x1800126f0`
- `0x180023640`
- `0x180024704`
- `0x18002d8b8`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023671`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023671`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800236a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800236a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LONG __stdcall SCardReconnect(
        SCARDHANDLE hCard,
        DWORD dwShareMode,
        DWORD dwPreferredProtocols,
        DWORD dwInitialization,
        LPDWORD pdwActiveProtocol)
{
  LONG v9; // edi
  CHandleList *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // rsi
  struct CHandleList::HandlePtr *HandlePtr; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  ulong pExceptionObject; // [rsp+34h] [rbp-54h] BYREF
  ulong v20; // [rsp+38h] [rbp-50h] BYREF
  LONG v21; // [rsp+3Ch] [rbp-4Ch] BYREF
  char *v22; // [rsp+40h] [rbp-48h]

  v9 = 0;
  try
  {
    v10 = g_phlReaders;
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlReaders + 32);
    v22 = (char *)g_phlReaders + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlReaders + 32));
    HandlePtr = CHandleList::GetHandlePtr(v10, hCard);
    if ( !HandlePtr )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v13 = *(_QWORD *)HandlePtr;
    LeaveCriticalSection(v11);
    if ( *(_DWORD *)(v13 + 16) )
    {
      v20 = -2146435042;
      throw &v20;
    }
    v14 = *(_QWORD *)(v13 + 40);
    if ( v14 )
    {
      v9 = RedirectedSCardReconnect(v14, dwShareMode, dwPreferredProtocols, dwInitialization, pdwActiveProtocol);
    }
    else
    {
      CReaderContext::Reconnect((CReaderContext *)v13, dwShareMode, dwPreferredProtocols, dwInitialization);
      if ( pdwActiveProtocol )
        *pdwActiveProtocol = *(_DWORD *)(v13 + 36);
    }
  }
  catch ( ulong v21 )
  {
    return v21;
  }
  catch ( ... )
  {
    return -2146435068;
  }
  return v9;
}

```

## disassembly

```asm
0x180023640  push    rbx
0x180023642  push    rsi
0x180023643  push    rdi
0x180023644  push    r12
0x180023646  push    r13
0x180023648  push    r14
0x18002364a  push    r15
0x18002364c  sub     rsp, 50h
0x180023650  mov     r14d, r9d
0x180023653  mov     r15d, r8d
0x180023656  mov     r12d, edx
0x180023659  mov     r13, rcx
0x18002365c  xor     edi, edi
0x18002365e  mov     rbx, cs:?g_phlReaders@@3PEAVCHandleList@@EA; CHandleList * g_phlReaders
0x180023665  lea     rsi, [rbx+20h]
0x180023669  mov     [rsp+88h+var_48], rsi
0x18002366e  mov     rcx, rsi; lpCriticalSection
0x180023671  call    cs:__imp_EnterCriticalSection
0x180023677  nop
0x180023678  mov     rdx, r13; unsigned __int64
0x18002367b  mov     rcx, rbx; this
0x18002367e  call    ?GetHandlePtr@CHandleList@@IEBAPEAUHandlePtr@1@_K@Z; CHandleList::GetHandlePtr(unsigned __int64)
0x180023683  test    rax, rax
0x180023686  jnz     short loc_1800236A1
0x180023688  mov     [rsp+88h+pExceptionObject], 6
0x180023690  lea     rdx, _TI1K; pThrowInfo
0x180023697  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002369c  call    _CxxThrowException_0
0x1800236a1  mov     rbx, [rax]
0x1800236a4  mov     rcx, rsi; lpCriticalSection
0x1800236a7  call    cs:__imp_LeaveCriticalSection
0x1800236ad  cmp     dword ptr [rbx+10h], 0
0x1800236b1  jz      short loc_1800236CC
0x1800236b3  mov     [rsp+88h+var_50], 8010001Eh
0x1800236bb  lea     rdx, _TI1K; pThrowInfo
0x1800236c2  lea     rcx, [rsp+88h+var_50]; pExceptionObject
0x1800236c7  call    _CxxThrowException_0
0x1800236cc  mov     rcx, [rbx+28h]; unsigned __int64
0x1800236d0  mov     r9d, r14d; unsigned int
0x1800236d3  mov     r8d, r15d; unsigned int
0x1800236d6  mov     edx, r12d; unsigned int
0x1800236d9  test    rcx, rcx
0x1800236dc  jz      short loc_1800236F8
0x1800236de  mov     rax, [rsp+88h+pdwActiveProtocol]
0x1800236e6  mov     [rsp+88h+var_68], rax; unsigned int *
0x1800236eb  call    ?RedirectedSCardReconnect@@YAJ_KKKKPEAK@Z; RedirectedSCardReconnect(unsigned __int64,ulong,ulong,ulong,ulong *)
0x1800236f0  mov     edi, eax
0x1800236f2  mov     [rsp+88h+var_58], eax
0x1800236f6  jmp     short loc_180023712
0x1800236f8  mov     rcx, rbx; this
0x1800236fb  call    ?Reconnect@CReaderContext@@QEAAXKKK@Z; CReaderContext::Reconnect(ulong,ulong,ulong)
0x180023700  mov     rcx, [rsp+88h+pdwActiveProtocol]
0x180023708  test    rcx, rcx
0x18002370b  jz      short loc_180023712
0x18002370d  mov     eax, [rbx+24h]
0x180023710  mov     [rcx], eax
0x180023712  jmp     short loc_18002371A
0x180023714  jmp     short $+2
0x180023716  mov     edi, [rsp+88h+var_58]
0x18002371a  mov     eax, edi
0x18002371c  add     rsp, 50h
0x180023720  pop     r15
0x180023722  pop     r14
0x180023724  pop     r13
0x180023726  pop     r12
0x180023728  pop     rdi
0x180023729  pop     rsi
0x18002372a  pop     rbx
0x18002372b  retn
```
