# CEventNotificationService::KillThread(ushort const *,void * *,void *)

- ea: `0x14001eb38`
- end: `0x14001ed07`
- name: `?KillThread@CEventNotificationService@@IEAAJPEBGPEAPEAXPEAX@Z`
- size: `463`
- prototype: `int(CEventNotificationService *__hidden this, const unsigned __int16 *, void **, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1400229c0`
- `0x140027328`

## callees

- `0x14001eb38`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001ecf1`
- `KERNEL32!CloseHandle` at `0x14001ecf1`
- `KERNEL32!GetThreadId` at `0x14001ec28`
- `KERNEL32!GetThreadId` at `0x14001eccc`
- `KERNEL32!GetThreadId` at `0x14001ec28`
- `KERNEL32!GetThreadId` at `0x14001eccc`
- `KERNEL32!SetEvent` at `0x14001eb59`
- `KERNEL32!SetEvent` at `0x14001eb59`
- `KERNEL32!WaitForSingleObject` at `0x14001ec46`
- `KERNEL32!WaitForSingleObject` at `0x14001ec46`
- `KERNEL32!GetLastError` at `0x14001eb67`
- `KERNEL32!GetLastError` at `0x14001ec50`
- `KERNEL32!GetLastError` at `0x14001eb67`
- `KERNEL32!GetLastError` at `0x14001ec50`
- `KERNEL32!IsDebuggerPresent` at `0x14001ebbe`
- `KERNEL32!IsDebuggerPresent` at `0x14001eca7`
- `KERNEL32!IsDebuggerPresent` at `0x14001ebbe`
- `KERNEL32!IsDebuggerPresent` at `0x14001eca7`

## string_xrefs

- `0x14001eb8a`: `CEventNotificationService::KillThread`
- `0x14001ec73`: `CEventNotificationService::KillThread`
- `0x14001ec31`: `CEventNotificationService::KillThread - waiting for %s thread (id 0x%X) to terminate.\n`
- `0x14001ecd5`: `CEventNotificationService::KillThread - %s thread (id 0x%X) has terminated.\n`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::KillThread(
        CEventNotificationService *this,
        const unsigned __int16 *a2,
        void **a3,
        void *a4)
{
  signed int v6; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v8; // r15
  __int64 v9; // r9
  __int64 v10; // r8
  DWORD ThreadId; // eax
  signed int v12; // eax
  DWORD v13; // eax
  signed int v15; // [rsp+30h] [rbp-38h]
  signed int v16; // [rsp+38h] [rbp-30h]

  if ( !*a3 )
    return 0;
  if ( !SetEvent(a4) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    v8 = L"fSuccess";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x18DDu,
      L"CEventNotificationService::KillThread",
      L"CBRAEx",
      L"fSuccess",
      v6);
    if ( IsDebuggerPresent() )
    {
      v9 = 6365;
LABEL_10:
      v16 = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v9,
        L"CEventNotificationService::KillThread",
        L"CBRAEx",
        v8,
        v16);
      return (unsigned int)v6;
    }
    v10 = 6365;
    goto LABEL_12;
  }
  ThreadId = GetThreadId(*a3);
  DEBUGMSG(L"CEventNotificationService::KillThread - waiting for %s thread (id 0x%X) to terminate.\n", a2, ThreadId);
  if ( WaitForSingleObject(*a3, 0xFFFFFFFF) )
  {
    v12 = GetLastError();
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    v8 = L"0";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      0x18EAu,
      L"CEventNotificationService::KillThread",
      L"CBRAEx",
      L"0",
      v6);
    if ( IsDebuggerPresent() )
    {
      v9 = 6378;
      goto LABEL_10;
    }
    v10 = 6378;
LABEL_12:
    v15 = v6;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
      v10,
      L"CEventNotificationService::KillThread",
      L"CBRAEx",
      v8,
      v15);
    return (unsigned int)v6;
  }
  v6 = 0;
  v13 = GetThreadId(*a3);
  DEBUGMSG(L"CEventNotificationService::KillThread - %s thread (id 0x%X) has terminated.\n", a2, v13);
  if ( (char *)*a3 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*a3);
    *a3 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001eb38  push    rbx
0x14001eb3a  push    rbp
0x14001eb3b  push    rsi
0x14001eb3c  push    rdi
0x14001eb3d  push    r15
0x14001eb3f  sub     rsp, 40h
0x14001eb43  cmp     qword ptr [r8], 0
0x14001eb47  mov     rdi, r8
0x14001eb4a  mov     rsi, rdx
0x14001eb4d  jnz     short loc_14001EB56
0x14001eb4f  xor     ebx, ebx
0x14001eb51  jmp     loc_14001ECFA
0x14001eb56  mov     rcx, r9; hEvent
0x14001eb59  call    cs:__imp_SetEvent
0x14001eb5f  test    eax, eax
0x14001eb61  jnz     loc_14001EC25
0x14001eb67  call    cs:__imp_GetLastError
0x14001eb6d  mov     ebx, eax
0x14001eb6f  test    eax, eax
0x14001eb71  jle     short loc_14001EB7C
0x14001eb73  movzx   ebx, ax
0x14001eb76  or      ebx, 80070000h
0x14001eb7c  mov     eax, 80004005h
0x14001eb81  lea     rbp, aCbraex; "CBRAEx"
0x14001eb88  test    ebx, ebx
0x14001eb8a  lea     rsi, aCeventnotifica_105; "CEventNotificationService::KillThread"
0x14001eb91  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001eb98  mov     r9, rbp; unsigned __int16 *
0x14001eb9b  cmovns  ebx, eax
0x14001eb9e  lea     r15, aFsuccess; "fSuccess"
0x14001eba5  mov     [rsp+68h+var_40], ebx; int
0x14001eba9  mov     r8, rsi; unsigned __int16 *
0x14001ebac  mov     edx, 18DDh; unsigned int
0x14001ebb1  mov     [rsp+68h+var_48], r15; unsigned __int16 *
0x14001ebb6  mov     rcx, rdi; unsigned __int16 *
0x14001ebb9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001ebbe  call    cs:__imp_IsDebuggerPresent
0x14001ebc4  test    eax, eax
0x14001ebc6  jz      short loc_14001EBFA
0x14001ebc8  mov     r9d, 18DDh
0x14001ebce  mov     [rsp+68h+var_30], ebx
0x14001ebd2  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001ebd9  mov     [rsp+68h+var_38], r15
0x14001ebde  mov     r8, rdi
0x14001ebe1  mov     qword ptr [rsp+68h+var_40], rbp
0x14001ebe6  mov     ecx, 2; unsigned __int8
0x14001ebeb  mov     [rsp+68h+var_48], rsi
0x14001ebf0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001ebf5  jmp     loc_14001ECFA
0x14001ebfa  mov     r8d, 18DDh
0x14001ec00  mov     dword ptr [rsp+68h+var_38], ebx
0x14001ec04  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001ec0b  mov     qword ptr [rsp+68h+var_40], r15
0x14001ec10  mov     r9, rsi
0x14001ec13  mov     rdx, rdi
0x14001ec16  mov     [rsp+68h+var_48], rbp
0x14001ec1b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14001ec20  jmp     loc_14001ECFA
0x14001ec25  mov     rcx, [rdi]; Thread
0x14001ec28  call    cs:__imp_GetThreadId
0x14001ec2e  mov     rdx, rsi
0x14001ec31  lea     rcx, aCeventnotifica_111; "CEventNotificationService::KillThread -"...
0x14001ec38  mov     r8d, eax
0x14001ec3b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001ec40  mov     rcx, [rdi]; hHandle
0x14001ec43  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001ec46  call    cs:__imp_WaitForSingleObject
0x14001ec4c  test    eax, eax
0x14001ec4e  jz      short loc_14001ECC7
0x14001ec50  call    cs:__imp_GetLastError
0x14001ec56  mov     ebx, eax
0x14001ec58  test    eax, eax
0x14001ec5a  jle     short loc_14001EC65
0x14001ec5c  movzx   ebx, ax
0x14001ec5f  or      ebx, 80070000h
0x14001ec65  mov     eax, 80004005h
0x14001ec6a  lea     rbp, aCbraex; "CBRAEx"
0x14001ec71  test    ebx, ebx
0x14001ec73  lea     rsi, aCeventnotifica_105; "CEventNotificationService::KillThread"
0x14001ec7a  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001ec81  mov     r9, rbp; unsigned __int16 *
0x14001ec84  cmovns  ebx, eax
0x14001ec87  lea     r15, a0; "0"
0x14001ec8e  mov     [rsp+68h+var_40], ebx; int
0x14001ec92  mov     r8, rsi; unsigned __int16 *
0x14001ec95  mov     edx, 18EAh; unsigned int
0x14001ec9a  mov     [rsp+68h+var_48], r15; unsigned __int16 *
0x14001ec9f  mov     rcx, rdi; unsigned __int16 *
0x14001eca2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001eca7  call    cs:__imp_IsDebuggerPresent
0x14001ecad  test    eax, eax
0x14001ecaf  jz      short loc_14001ECBC
0x14001ecb1  mov     r9d, 18EAh
0x14001ecb7  jmp     loc_14001EBCE
0x14001ecbc  mov     r8d, 18EAh
0x14001ecc2  jmp     loc_14001EC00
0x14001ecc7  mov     rcx, [rdi]; Thread
0x14001ecca  xor     ebx, ebx
0x14001eccc  call    cs:__imp_GetThreadId
0x14001ecd2  mov     rdx, rsi
0x14001ecd5  lea     rcx, aCeventnotifica_60; "CEventNotificationService::KillThread -"...
0x14001ecdc  mov     r8d, eax
0x14001ecdf  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001ece4  mov     rcx, [rdi]; hObject
0x14001ece7  lea     rdx, [rcx-1]
0x14001eceb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14001ecef  ja      short loc_14001ECFA
0x14001ecf1  call    cs:__imp_CloseHandle
0x14001ecf7  mov     [rdi], rbx
0x14001ecfa  mov     eax, ebx
0x14001ecfc  add     rsp, 40h
0x14001ed00  pop     r15
0x14001ed02  pop     rdi
0x14001ed03  pop     rsi
0x14001ed04  pop     rbp
0x14001ed05  pop     rbx
0x14001ed06  retn
```
