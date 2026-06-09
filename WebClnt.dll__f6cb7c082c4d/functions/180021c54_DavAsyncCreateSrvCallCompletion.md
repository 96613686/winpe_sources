# DavAsyncCreateSrvCallCompletion

- ea: `0x180021c54`
- end: `0x180021ef8`
- name: `DavAsyncCreateSrvCallCompletion`
- size: `676`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021f00`

## callees

- `0x18000b7dc`
- `0x180010770`
- `0x180011360`
- `0x180021c54`

## import_xrefs

- `msvcrt!time` at `0x180021e20`
- `msvcrt!time` at `0x180021e20`
- `ntdll!RtlNtStatusToDosError` at `0x180021d82`
- `ntdll!RtlNtStatusToDosError` at `0x180021d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ecc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ecc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021de0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ede`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021de0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021ede`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021d70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021e0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021eb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021d70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021e0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021eb0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021da0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021da0`
- `KERNEL32!LocalFree` at `0x180021ed5`
- `KERNEL32!LocalFree` at `0x180021ed5`
- `WINHTTP!WinHttpCloseHandle` at `0x180021c80`
- `WINHTTP!WinHttpCloseHandle` at `0x180021cc4`
- `WINHTTP!WinHttpCloseHandle` at `0x180021d0a`
- `WINHTTP!WinHttpCloseHandle` at `0x180021c80`
- `WINHTTP!WinHttpCloseHandle` at `0x180021cc4`
- `WINHTTP!WinHttpCloseHandle` at `0x180021d0a`

## pseudocode

```c
void __fastcall DavAsyncCreateSrvCallCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  void *v5; // rcx
  DWORD LastError; // eax
  void *v7; // rcx
  DWORD v8; // eax
  void *v9; // rcx
  DWORD v10; // eax
  NTSTATUS v11; // ecx
  int v12; // ebx
  ULONG v13; // eax
  void *v14; // rcx
  __int64 v15; // rbx
  DWORD v16; // eax
  time_t v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  int v21; // ecx
  __int64 v22; // rcx
  void *v23; // rcx

  v3 = *(_QWORD *)(a1 + 504);
  v5 = *(void **)(a1 + 528);
  if ( v5 )
  {
    if ( !WinHttpCloseHandle(v5) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, LastError);
    }
  }
  v7 = *(void **)(a1 + 520);
  if ( v7 )
  {
    if ( !WinHttpCloseHandle(v7) )
    {
      v8 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v8);
    }
  }
  v9 = *(void **)(a1 + 512);
  if ( v9 )
  {
    if ( !WinHttpCloseHandle(v9) )
    {
      v10 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v10);
    }
  }
  if ( *(_DWORD *)(a1 + 664) )
  {
    if ( *(_QWORD *)(a1 + 496) )
      DavFinalizePerUserEntry((unsigned int **)(a1 + 496), a2, a3);
    if ( v3 )
    {
      EnterCriticalSection(&HashServerEntryTableLock);
      v11 = *(_DWORD *)(a1 + 32);
      if ( v11 )
      {
        v12 = 1;
        v13 = RtlNtStatusToDosError(v11);
      }
      else
      {
        v12 = 2;
        v13 = 0;
      }
      *(_DWORD *)(v3 + 24) = v13;
      *(_DWORD *)(v3 + 12) = v12;
      v14 = *(void **)(v3 + 16);
      if ( v14
        && !SetEvent(v14)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v16 = GetLastError();
        WPP_SF_d(v15, 60, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids, v16);
      }
      LeaveCriticalSection(&HashServerEntryTableLock);
    }
  }
  if ( *(_DWORD *)(a1 + 32) )
  {
    *(_DWORD *)(a1 + 2312) = 0;
    if ( *(_DWORD *)(a1 + 664) )
    {
      if ( v3 )
      {
        EnterCriticalSection(&HashServerEntryTableLock);
        *(_QWORD *)(v3 + 28) = 0;
        *(_QWORD *)(v3 + 36) = 0;
        *(_DWORD *)(v3 + 44) = 0;
        v17 = time(0);
        --*(_DWORD *)(v3 + 104);
        *(_QWORD *)(v3 + 112) = v17;
        v18 = (_QWORD *)(v3 + 88);
        v19 = *(_QWORD *)(v3 + 88);
        if ( *(_QWORD *)(v19 + 8) != v3 + 88 )
          goto LABEL_41;
        v20 = *(_QWORD **)(v3 + 96);
        if ( (_QWORD *)*v20 != v18 )
          goto LABEL_41;
        *v20 = v19;
        *(_QWORD *)(v19 + 8) = v20;
        v21 = *(_DWORD *)(a1 + 32);
        if ( v21 != -1073741790 && v21 != -1073741715 && v21 != -1073741117 && v21 != -1073739515 )
        {
          v22 = ToBeFinalizedServerEntries;
          if ( *(__int64 **)(ToBeFinalizedServerEntries + 8) == &ToBeFinalizedServerEntries )
          {
            *v18 = ToBeFinalizedServerEntries;
            *(_QWORD *)(v3 + 96) = &ToBeFinalizedServerEntries;
            *(_QWORD *)(v22 + 8) = v18;
            ToBeFinalizedServerEntries = v3 + 88;
LABEL_48:
            LeaveCriticalSection(&HashServerEntryTableLock);
            goto LABEL_49;
          }
LABEL_41:
          __fastfail(3u);
        }
        *(_DWORD *)(v3 + 64) = 1;
LABEL_44:
        if ( !*(_DWORD *)(v3 + 104) )
        {
          v23 = *(void **)(v3 + 16);
          if ( v23 )
            CloseHandle(v23);
          LocalFree((HLOCAL)v3);
        }
        goto LABEL_48;
      }
    }
    else if ( *(_DWORD *)(a1 + 668) )
    {
      EnterCriticalSection(&HashServerEntryTableLock);
      --*(_DWORD *)(v3 + 104);
      if ( !*(_DWORD *)(v3 + 64) )
        goto LABEL_48;
      goto LABEL_44;
    }
  }
LABEL_49:
  DavFsFinalizeTheDavCallBackContext(a1);
}

```

## disassembly

```asm
0x180021c54  push    rbx
0x180021c56  push    rbp
0x180021c57  push    rsi
0x180021c58  push    rdi
0x180021c59  push    r12
0x180021c5b  push    r14
0x180021c5d  sub     rsp, 28h
0x180021c61  mov     rdi, [rcx+1F8h]
0x180021c68  lea     r12, WPP_GLOBAL_Control
0x180021c6f  mov     rsi, rcx
0x180021c72  xor     ebp, ebp
0x180021c74  mov     rcx, [rcx+210h]; hInternet
0x180021c7b  test    rcx, rcx
0x180021c7e  jz      short loc_180021CB8
0x180021c80  call    cs:__imp_WinHttpCloseHandle
0x180021c86  test    eax, eax
0x180021c88  jnz     short loc_180021CB8
0x180021c8a  call    cs:__imp_GetLastError
0x180021c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c97  cmp     rcx, r12
0x180021c9a  jz      short loc_180021CB8
0x180021c9c  test    byte ptr [rcx+1Ch], 1
0x180021ca0  jz      short loc_180021CB8
0x180021ca2  mov     rcx, [rcx+10h]
0x180021ca6  lea     edx, [rbp+39h]
0x180021ca9  mov     r9d, eax
0x180021cac  lea     r8, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids
0x180021cb3  call    WPP_SF_d
0x180021cb8  mov     rcx, [rsi+208h]; hInternet
0x180021cbf  test    rcx, rcx
0x180021cc2  jz      short loc_180021CFE
0x180021cc4  call    cs:__imp_WinHttpCloseHandle
0x180021cca  test    eax, eax
0x180021ccc  jnz     short loc_180021CFE
0x180021cce  call    cs:__imp_GetLastError
0x180021cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cdb  cmp     rcx, r12
0x180021cde  jz      short loc_180021CFE
0x180021ce0  test    byte ptr [rcx+1Ch], 1
0x180021ce4  jz      short loc_180021CFE
0x180021ce6  mov     rcx, [rcx+10h]
0x180021cea  lea     r8, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids
0x180021cf1  mov     edx, 3Ah ; ':'
0x180021cf6  mov     r9d, eax
0x180021cf9  call    WPP_SF_d
0x180021cfe  mov     rcx, [rsi+200h]; hInternet
0x180021d05  test    rcx, rcx
0x180021d08  jz      short loc_180021D44
0x180021d0a  call    cs:__imp_WinHttpCloseHandle
0x180021d10  test    eax, eax
0x180021d12  jnz     short loc_180021D44
0x180021d14  call    cs:__imp_GetLastError
0x180021d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d21  cmp     rcx, r12
0x180021d24  jz      short loc_180021D44
0x180021d26  test    byte ptr [rcx+1Ch], 1
0x180021d2a  jz      short loc_180021D44
0x180021d2c  mov     rcx, [rcx+10h]
0x180021d30  lea     r8, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids
0x180021d37  mov     edx, 3Bh ; ';'
0x180021d3c  mov     r9d, eax
0x180021d3f  call    WPP_SF_d
0x180021d44  lea     r14, HashServerEntryTableLock
0x180021d4b  cmp     [rsi+298h], ebp
0x180021d51  jz      loc_180021DE6
0x180021d57  lea     rcx, [rsi+1F0h]
0x180021d5e  cmp     [rcx], rbp
0x180021d61  jz      short loc_180021D68
0x180021d63  call    DavFinalizePerUserEntry
0x180021d68  test    rdi, rdi
0x180021d6b  jz      short loc_180021DE6
0x180021d6d  mov     rcx, r14; lpCriticalSection
0x180021d70  call    cs:__imp_EnterCriticalSection
0x180021d76  mov     ecx, [rsi+20h]; Status
0x180021d79  test    ecx, ecx
0x180021d7b  jz      short loc_180021D8A
0x180021d7d  mov     ebx, 1
0x180021d82  call    cs:__imp_RtlNtStatusToDosError
0x180021d88  jmp     short loc_180021D91
0x180021d8a  mov     ebx, 2
0x180021d8f  mov     eax, ebp
0x180021d91  mov     [rdi+18h], eax
0x180021d94  mov     [rdi+0Ch], ebx
0x180021d97  mov     rcx, [rdi+10h]; hEvent
0x180021d9b  test    rcx, rcx
0x180021d9e  jz      short loc_180021DDD
0x180021da0  call    cs:__imp_SetEvent
0x180021da6  test    eax, eax
0x180021da8  jnz     short loc_180021DDD
0x180021daa  mov     rbx, cs:WPP_GLOBAL_Control
0x180021db1  cmp     rbx, r12
0x180021db4  jz      short loc_180021DDD
0x180021db6  test    byte ptr [rbx+1Ch], 1
0x180021dba  jz      short loc_180021DDD
0x180021dbc  mov     rbx, [rbx+10h]
0x180021dc0  call    cs:__imp_GetLastError
0x180021dc6  mov     edx, 3Ch ; '<'
0x180021dcb  lea     r8, WPP_63e32ebd36c63df0deb7b2e5434a4f62_Traceguids
0x180021dd2  mov     r9d, eax
0x180021dd5  mov     rcx, rbx
0x180021dd8  call    WPP_SF_d
0x180021ddd  mov     rcx, r14; lpCriticalSection
0x180021de0  call    cs:__imp_LeaveCriticalSection
0x180021de6  cmp     [rsi+20h], ebp
0x180021de9  jz      loc_180021EE4
0x180021def  mov     [rsi+908h], ebp
0x180021df5  cmp     [rsi+298h], ebp
0x180021dfb  jz      loc_180021EA5
0x180021e01  test    rdi, rdi
0x180021e04  jz      loc_180021EE4
0x180021e0a  mov     rcx, r14; lpCriticalSection
0x180021e0d  call    cs:__imp_EnterCriticalSection
0x180021e13  xor     ecx, ecx; Time
0x180021e15  mov     [rdi+1Ch], rbp
0x180021e19  mov     [rdi+24h], rbp
0x180021e1d  mov     [rdi+2Ch], ebp
0x180021e20  call    cs:__imp_time
0x180021e26  dec     dword ptr [rdi+68h]
0x180021e29  mov     [rdi+70h], rax
0x180021e2d  lea     rax, [rdi+58h]
0x180021e31  mov     rdx, [rax]
0x180021e34  cmp     [rdx+8], rax
0x180021e38  jnz     short loc_180021E9E
0x180021e3a  mov     rcx, [rax+8]
0x180021e3e  cmp     [rcx], rax
0x180021e41  jnz     short loc_180021E9E
0x180021e43  mov     [rcx], rdx
0x180021e46  mov     [rdx+8], rcx
0x180021e4a  mov     ecx, [rsi+20h]
0x180021e4d  cmp     ecx, 0C0000022h
0x180021e53  jz      short loc_180021E95
0x180021e55  cmp     ecx, 0C000006Dh
0x180021e5b  jz      short loc_180021E95
0x180021e5d  cmp     ecx, 0C00002C3h
0x180021e63  jz      short loc_180021E95
0x180021e65  cmp     ecx, 0C0000905h
0x180021e6b  jz      short loc_180021E95
0x180021e6d  mov     rcx, cs:ToBeFinalizedServerEntries
0x180021e74  lea     rdx, ToBeFinalizedServerEntries
0x180021e7b  cmp     [rcx+8], rdx
0x180021e7f  jnz     short loc_180021E9E
0x180021e81  mov     [rax], rcx
0x180021e84  mov     [rax+8], rdx
0x180021e88  mov     [rcx+8], rax
0x180021e8c  mov     cs:ToBeFinalizedServerEntries, rax
0x180021e93  jmp     short loc_180021EDB
0x180021e95  mov     dword ptr [rdi+40h], 1
0x180021e9c  jmp     short loc_180021EBE
0x180021e9e  mov     ecx, 3
0x180021ea3  int     29h; Win8: RtlFailFast(ecx)
0x180021ea5  cmp     [rsi+29Ch], ebp
0x180021eab  jz      short loc_180021EE4
0x180021ead  mov     rcx, r14; lpCriticalSection
0x180021eb0  call    cs:__imp_EnterCriticalSection
0x180021eb6  dec     dword ptr [rdi+68h]
0x180021eb9  cmp     [rdi+40h], ebp
0x180021ebc  jz      short loc_180021EDB
0x180021ebe  cmp     [rdi+68h], ebp
0x180021ec1  jnz     short loc_180021EDB
0x180021ec3  mov     rcx, [rdi+10h]; hObject
0x180021ec7  test    rcx, rcx
0x180021eca  jz      short loc_180021ED2
0x180021ecc  call    cs:__imp_CloseHandle
0x180021ed2  mov     rcx, rdi; hMem
0x180021ed5  call    cs:__imp_LocalFree
0x180021edb  mov     rcx, r14; lpCriticalSection
0x180021ede  call    cs:__imp_LeaveCriticalSection
0x180021ee4  mov     rcx, rsi
0x180021ee7  add     rsp, 28h
0x180021eeb  pop     r14
0x180021eed  pop     r12
0x180021eef  pop     rdi
0x180021ef0  pop     rsi
0x180021ef1  pop     rbp
0x180021ef2  pop     rbx
0x180021ef3  jmp     DavFsFinalizeTheDavCallBackContext
```
