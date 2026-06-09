# NetpEventlogWriteEx3

- ea: `0x180042c94`
- end: `0x180043210`
- name: `NetpEventlogWriteEx3`
- size: `1404`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, PSID pSid1, LPCWSTR *, WORD, __int64, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180041810`

## callees

- `0x180042c94`
- `0x1800434ae`
- `0x1800434ba`
- `0x180043510`

## import_xrefs

- `msvcrt!_ultow` at `0x180042db6`
- `msvcrt!_ultow` at `0x180042db6`
- `msvcrt!wcscpy_s` at `0x180042da0`
- `msvcrt!wcscpy_s` at `0x180043197`
- `msvcrt!wcscpy_s` at `0x180042da0`
- `msvcrt!wcscpy_s` at `0x180043197`
- `ntdll!RtlNtStatusToDosError` at `0x180042d79`
- `ntdll!RtlNtStatusToDosError` at `0x180042d79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042d3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042d3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042d11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042d11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180042e02`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043115`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180042e02`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800430d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800430d9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043041`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043135`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004314c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043041`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043135`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004314c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180042ec4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180042ec4`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180043005`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180043005`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180042f9f`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180042f9f`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180042feb`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180042feb`

## pseudocode

```c
__int64 __fastcall NetpEventlogWriteEx3(
        struct _RTL_CRITICAL_SECTION *a1,
        int a2,
        int a3,
        DWORD a4,
        int a5,
        int a6,
        PSID pSid1,
        LPCWSTR *a8,
        unsigned int wNumStrings,
        void *lpRawData,
        size_t Size)
{
  WORD v11; // r15
  PSID v12; // rbx
  int v13; // esi
  LPCWSTR *lpStrings; // rdi
  struct _RTL_CRITICAL_SECTION *v15; // rbp
  unsigned int v16; // r13d
  DWORD LastError; // ebp
  struct _RTL_CRITICAL_SECTION *v18; // rdx
  int v20; // r14d
  struct _RTL_CRITICAL_SECTION *v21; // rsi
  struct _RTL_CRITICAL_SECTION_DEBUG *DebugInfo; // rdi
  __int64 OwningThread_low; // rbp
  struct _RTL_CRITICAL_SECTION_DEBUG *v24; // r15
  struct _LIST_ENTRY *Flink; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *v26; // rcx
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rax
  __int64 v28; // rax
  unsigned int v29; // r8d
  char *v30; // rcx
  LPCWSTR v31; // rdx
  bool v32; // zf
  signed __int64 v33; // rdx
  int v34; // eax
  int v35; // r9d
  struct _RTL_CRITICAL_SECTION_DEBUG *v36; // rax
  struct _RTL_CRITICAL_SECTION *v37; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v38; // rax
  HANDLE v39; // rbx
  unsigned int v40; // ebx
  signed int v41; // r8d
  SIZE_T v42; // rdx
  DWORD LengthSid; // eax
  unsigned int v44; // ecx
  unsigned int v45; // r9d
  unsigned int v46; // ecx
  LPCWSTR v47; // r10
  __int64 v48; // rax
  unsigned int v49; // r8d
  unsigned int v50; // eax
  __int64 v51; // r15
  HLOCAL v52; // rax
  struct _RTL_CRITICAL_SECTION *v53; // rbx
  __int64 v54; // rsi
  DWORD v55; // eax
  wchar_t *v56; // rdi
  unsigned int v57; // r14d
  __int64 v58; // rsi
  _QWORD *LockSemaphore; // rax
  __int64 v60; // rax
  struct _RTL_CRITICAL_SECTION *v61; // rax
  PRTL_CRITICAL_SECTION_DEBUG v62; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-98h] BYREF
  wchar_t Destination[2]; // [rsp+88h] [rbp-90h] BYREF
  wchar_t Buffer[26]; // [rsp+8Ch] [rbp-8Ch] BYREF

  v11 = a3;
  v12 = pSid1;
  v13 = a2;
  lpStrings = a8;
  v15 = a1;
  v16 = Size;
  EnterCriticalSection(a1);
  if ( ((a5 & 0x40000000) != 0 || a5 < 0) && !wNumStrings )
  {
    LastError = 87;
LABEL_5:
    v18 = a1;
    goto LABEL_6;
  }
  v20 = a5 & 0x20000000;
  if ( a5 < 0 )
  {
    *a8 = (LPCWSTR)RtlNtStatusToDosError(*(_DWORD *)a8);
LABEL_10:
    wcscpy_s(Destination, 0x19u, L"%%");
    _ultow(*(_DWORD *)a8, Buffer, 10);
    *a8 = Destination;
    goto LABEL_11;
  }
  if ( (a5 & 0x40000000) != 0 )
    goto LABEL_10;
LABEL_11:
  if ( !v20 )
  {
    v21 = v15 + 1;
    DebugInfo = v15[1].DebugInfo;
    while ( 1 )
    {
      if ( DebugInfo == (struct _RTL_CRITICAL_SECTION_DEBUG *)v21 )
      {
        lpStrings = a8;
        v13 = a2;
        v11 = a3;
        break;
      }
      OwningThread_low = LODWORD(v15[1].OwningThread);
      v24 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
      SystemTimeAsFileTime = 0;
      if ( (_DWORD)OwningThread_low != -1 )
      {
        Flink = DebugInfo->ProcessLocksList.Flink;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( (__int64)(*(_QWORD *)&SystemTimeAsFileTime - (_QWORD)Flink) < 0
          || *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)Flink > 10000 * OwningThread_low )
        {
          v26 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
          if ( *(struct _RTL_CRITICAL_SECTION_DEBUG **)(*(_QWORD *)&DebugInfo->Type + 8LL) != DebugInfo )
            goto LABEL_92;
          CriticalSection = DebugInfo->CriticalSection;
          if ( CriticalSection->DebugInfo != DebugInfo )
            goto LABEL_92;
          CriticalSection->DebugInfo = v26;
          v26->CriticalSection = CriticalSection;
          LocalFree(DebugInfo);
          goto LABEL_44;
        }
        v12 = pSid1;
      }
      if ( LODWORD(DebugInfo->ProcessLocksList.Blink) == a4
        && HIDWORD(DebugInfo->ProcessLocksList.Blink) == a2
        && DebugInfo->Flags == a3
        && LODWORD(DebugInfo[1].CriticalSection) == (_DWORD)Size
        && LODWORD(DebugInfo[1].ProcessLocksList.Blink) == wNumStrings
        && (!(_DWORD)Size || !memcmp_0(*(const void **)&DebugInfo[1].Type, lpRawData, (unsigned int)Size)) )
      {
        v28 = *(_QWORD *)&DebugInfo->EntryCount;
        if ( v12 )
        {
          if ( !v28 || !EqualSid(v12, *(PSID *)&DebugInfo->EntryCount) )
            goto LABEL_44;
        }
        else if ( v28 )
        {
          goto LABEL_44;
        }
        v29 = 0;
        if ( wNumStrings )
        {
          while ( 1 )
          {
            v30 = (char *)*((_QWORD *)&DebugInfo[1].ProcessLocksList.Flink->Flink + v29);
            v31 = a8[v29];
            if ( v30 )
            {
              if ( !v31 )
                break;
              v33 = (char *)v31 - v30;
              do
              {
                v34 = *(unsigned __int16 *)&v30[v33];
                v35 = *(unsigned __int16 *)v30 - v34;
                if ( v35 )
                  break;
                v30 += 2;
              }
              while ( v34 );
              v32 = v35 == 0;
            }
            else
            {
              v32 = v31 == 0;
            }
            if ( !v32 )
              break;
            if ( ++v29 >= wNumStrings )
              goto LABEL_43;
          }
        }
        else
        {
LABEL_43:
          if ( v29 == wNumStrings )
          {
            v36 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
            if ( *(struct _RTL_CRITICAL_SECTION_DEBUG **)(*(_QWORD *)&DebugInfo->Type + 8LL) != DebugInfo )
              goto LABEL_92;
            v37 = DebugInfo->CriticalSection;
            if ( v37->DebugInfo != DebugInfo )
              goto LABEL_92;
            v37->DebugInfo = v36;
            v36->CriticalSection = v37;
            v38 = v21->DebugInfo;
            if ( v21->DebugInfo->CriticalSection != v21 )
              goto LABEL_92;
            *(_QWORD *)&DebugInfo->Type = v38;
            LastError = 183;
            DebugInfo->CriticalSection = v21;
            v38->CriticalSection = (struct _RTL_CRITICAL_SECTION *)DebugInfo;
            v21->DebugInfo = DebugInfo;
            ++HIDWORD(DebugInfo[1].ProcessLocksList.Blink);
            goto LABEL_5;
          }
        }
      }
LABEL_44:
      v12 = pSid1;
      DebugInfo = v24;
      v15 = a1;
    }
  }
  v39 = RegisterEventSourceW(0, (LPCWSTR)v15[1].LockSemaphore);
  if ( v39 )
  {
    if ( ReportEventW(v39, v13, v11, a4, 0, wNumStrings, Size, lpStrings, lpRawData) )
      LastError = 0;
    else
      LastError = GetLastError();
    DeregisterEventSource(v39);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError )
    goto LABEL_5;
  if ( v20 )
    goto LABEL_5;
  v40 = Size + 80;
  if ( (unsigned int)Size >= 0xFFFFFFB0 )
    goto LABEL_5;
  v41 = 0;
  v42 = v40;
  if ( pSid1 )
  {
    LengthSid = GetLengthSid(pSid1);
    v42 = 0xFFFFFFFFLL;
    v44 = LengthSid + v40;
    if ( LengthSid + v40 >= v40 )
      v42 = v44;
    v41 = v44 < v40 ? 0xC0000095 : 0;
    if ( v44 < v40 )
      goto LABEL_5;
  }
  v45 = 0;
  if ( !wNumStrings )
    goto LABEL_76;
  do
  {
    if ( v41 < 0 )
      goto LABEL_5;
    v46 = v42 + 8;
    if ( (int)v42 + 8 < (unsigned int)v42 )
      goto LABEL_73;
    v41 = 0;
    v42 = v46;
    v47 = lpStrings[v45];
    if ( !v47 )
      goto LABEL_74;
    v48 = -1;
    do
      ++v48;
    while ( v47[v48] );
    v49 = v46 + 2 * v48;
    if ( v49 < v46 )
    {
LABEL_73:
      v41 = -1073741675;
      v42 = 0xFFFFFFFFLL;
    }
    else
    {
      v50 = v49 + 2;
      v42 = 0xFFFFFFFFLL;
      if ( v49 + 2 >= v49 )
        v42 = v50;
      v41 = v50 < v49 ? 0xC0000095 : 0;
    }
LABEL_74:
    ++v45;
  }
  while ( v45 < wNumStrings );
  if ( v41 < 0 )
    goto LABEL_5;
LABEL_76:
  v51 = (unsigned int)v42;
  v52 = LocalAlloc(0, v42);
  v53 = (struct _RTL_CRITICAL_SECTION *)v52;
  if ( !v52 )
    goto LABEL_5;
  *((_DWORD *)v52 + 6) = a4;
  *((_DWORD *)v52 + 10) = a3;
  *((_DWORD *)v52 + 7) = v13;
  *((_QWORD *)v52 + 4) = 0;
  *((_DWORD *)v52 + 14) = Size;
  *((_DWORD *)v52 + 18) = wNumStrings;
  *((_DWORD *)v52 + 19) = 1;
  GetSystemTimeAsFileTime((LPFILETIME)v52 + 2);
  v53[1].LockSemaphore = &v53[2];
  v54 = (__int64)&v53[2] + 8 * wNumStrings;
  if ( pSid1 )
  {
    v53->SpinCount = v54;
    v55 = GetLengthSid(pSid1);
    memcpy_0(&v53[2].DebugInfo + wNumStrings, pSid1, v55);
    v56 = (wchar_t *)(v54 + GetLengthSid(pSid1));
  }
  else
  {
    v56 = (wchar_t *)(&v53[2].DebugInfo + wNumStrings);
  }
  v57 = 0;
  if ( wNumStrings )
  {
    v58 = 0;
    do
    {
      LockSemaphore = v53[1].LockSemaphore;
      if ( a8[v58] )
      {
        LockSemaphore[v58] = v56;
        wcscpy_s(v56, ((unsigned __int64)v53 + v51 - (_QWORD)v56) >> 1, a8[v58]);
        v60 = -1;
        do
          ++v60;
        while ( a8[v58][v60] );
        v56 += v60 + 1;
      }
      else
      {
        LockSemaphore[v58] = 0;
      }
      ++v57;
      ++v58;
    }
    while ( v57 < wNumStrings );
    v16 = Size;
  }
  if ( v16 )
  {
    *(_QWORD *)&v53[1].LockCount = v56;
    memcpy_0(v56, lpRawData, v16);
  }
  v18 = a1;
  v61 = a1 + 1;
  v62 = a1[1].DebugInfo;
  if ( v62->CriticalSection != &a1[1] )
LABEL_92:
    __fastfail(3u);
  v53->DebugInfo = v62;
  *(_QWORD *)&v53->LockCount = v61;
  v62->CriticalSection = v53;
  v61->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v53;
LABEL_6:
  LeaveCriticalSection(v18);
  return LastError;
}

```

## disassembly

```asm
0x180042c94  push    rbx
0x180042c96  push    rbp
0x180042c97  push    rsi
0x180042c98  push    rdi
0x180042c99  push    r12
0x180042c9b  push    r13
0x180042c9d  push    r14
0x180042c9f  push    r15
0x180042ca1  sub     rsp, 0D8h
0x180042ca8  mov     rax, cs:__security_cookie
0x180042caf  xor     rax, rsp
0x180042cb2  mov     [rsp+118h+var_58], rax
0x180042cba  mov     rax, [rsp+118h+arg_48]
0x180042cc2  mov     r15d, r8d
0x180042cc5  mov     rbx, [rsp+118h+pSid1]
0x180042ccd  mov     esi, edx
0x180042ccf  mov     rdi, [rsp+118h+arg_38]
0x180042cd7  mov     rbp, rcx
0x180042cda  mov     r13d, dword ptr [rsp+118h+Size]
0x180042ce2  mov     r12d, dword ptr [rsp+118h+arg_40]
0x180042cea  mov     [rsp+118h+pSid], rbx
0x180042cef  mov     [rsp+118h+var_A8], rdi
0x180042cf4  mov     [rsp+118h+Buf2], rax
0x180042cf9  mov     [rsp+118h+var_B4], r13d
0x180042cfe  mov     [rsp+118h+dwEventID], r9d
0x180042d03  mov     [rsp+118h+var_BC], r8d
0x180042d08  mov     [rsp+118h+var_B8], edx
0x180042d0c  mov     [rsp+118h+lpCriticalSection], rcx
0x180042d11  call    cs:__imp_EnterCriticalSection
0x180042d17  mov     eax, [rsp+118h+arg_20]
0x180042d1e  xor     r11d, r11d
0x180042d21  bt      eax, 1Eh
0x180042d25  jb      short loc_180042D2B
0x180042d27  test    eax, eax
0x180042d29  jns     short loc_180042D69
0x180042d2b  test    r12d, r12d
0x180042d2e  jnz     short loc_180042D69
0x180042d30  lea     ebp, [r12+57h]
0x180042d35  mov     rdx, [rsp+118h+lpCriticalSection]
0x180042d3a  mov     rcx, rdx; lpCriticalSection
0x180042d3d  call    cs:__imp_LeaveCriticalSection
0x180042d43  mov     eax, ebp
0x180042d45  mov     rcx, [rsp+118h+var_58]
0x180042d4d  xor     rcx, rsp; StackCookie
0x180042d50  call    __security_check_cookie
0x180042d55  add     rsp, 0D8h
0x180042d5c  pop     r15
0x180042d5e  pop     r14
0x180042d60  pop     r13
0x180042d62  pop     r12
0x180042d64  pop     rdi
0x180042d65  pop     rsi
0x180042d66  pop     rbp
0x180042d67  pop     rbx
0x180042d68  retn
0x180042d69  mov     r14d, eax
0x180042d6c  and     r14d, 20000000h
0x180042d73  test    eax, eax
0x180042d75  jns     short loc_180042D86
0x180042d77  mov     ecx, [rdi]; Status
0x180042d79  call    cs:__imp_RtlNtStatusToDosError
0x180042d7f  mov     eax, eax
0x180042d81  mov     [rdi], rax
0x180042d84  jmp     short loc_180042D8C
0x180042d86  bt      eax, 1Eh
0x180042d8a  jnb     short loc_180042DCA
0x180042d8c  lea     r8, Source; "%%"
0x180042d93  mov     edx, 19h; SizeInWords
0x180042d98  lea     rcx, [rsp+118h+Destination]; Destination
0x180042da0  call    cs:__imp_wcscpy_s
0x180042da6  mov     ecx, [rdi]; Value
0x180042da8  lea     rdx, [rsp+118h+Buffer]; Buffer
0x180042db0  mov     r8d, 0Ah; Radix
0x180042db6  call    cs:__imp__ultow
0x180042dbc  lea     rax, [rsp+118h+Destination]
0x180042dc4  xor     r11d, r11d
0x180042dc7  mov     [rdi], rax
0x180042dca  test    r14d, r14d
0x180042dcd  jnz     loc_180042F99
0x180042dd3  lea     rsi, [rbp+28h]
0x180042dd7  mov     rdi, [rsi]
0x180042dda  cmp     rdi, rsi
0x180042ddd  jz      loc_180042F8B
0x180042de3  mov     ebp, [rbp+38h]
0x180042de6  mov     r15, [rdi]
0x180042de9  mov     qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime], r11
0x180042df1  cmp     ebp, 0FFFFFFFFh
0x180042df4  jz      short loc_180042E58
0x180042df6  mov     rbx, [rdi+10h]
0x180042dfa  lea     rcx, [rsp+118h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180042e02  call    cs:__imp_GetSystemTimeAsFileTime
0x180042e08  mov     rdx, qword ptr [rsp+118h+SystemTimeAsFileTime.dwLowDateTime]
0x180042e10  sub     rdx, rbx
0x180042e13  js      short loc_180042E21
0x180042e15  imul    rcx, rbp, 2710h
0x180042e1c  cmp     rdx, rcx
0x180042e1f  jle     short loc_180042E50
0x180042e21  mov     rcx, [rdi]
0x180042e24  cmp     [rcx+8], rdi
0x180042e28  jnz     loc_1800431F6
0x180042e2e  mov     rax, [rdi+8]
0x180042e32  cmp     [rax], rdi
0x180042e35  jnz     loc_1800431F6
0x180042e3b  mov     [rax], rcx
0x180042e3e  mov     [rcx+8], rax
0x180042e42  mov     rcx, rdi; hMem
0x180042e45  call    cs:__imp_LocalFree
0x180042e4b  jmp     loc_180042F2D
0x180042e50  mov     rbx, [rsp+118h+pSid]
0x180042e55  xor     r11d, r11d
0x180042e58  mov     eax, [rsp+118h+dwEventID]
0x180042e5c  cmp     [rdi+18h], eax
0x180042e5f  jnz     loc_180042F2D
0x180042e65  mov     eax, [rsp+118h+var_B8]
0x180042e69  cmp     [rdi+1Ch], eax
0x180042e6c  jnz     loc_180042F2D
0x180042e72  mov     eax, [rsp+118h+var_BC]
0x180042e76  cmp     [rdi+28h], eax
0x180042e79  jnz     loc_180042F2D
0x180042e7f  cmp     [rdi+38h], r13d
0x180042e83  jnz     loc_180042F2D
0x180042e89  cmp     [rdi+48h], r12d
0x180042e8d  jnz     loc_180042F2D
0x180042e93  test    r13d, r13d
0x180042e96  jz      short loc_180042EB0
0x180042e98  mov     rdx, [rsp+118h+Buf2]; Buf2
0x180042e9d  mov     r8, r13; Size
0x180042ea0  mov     rcx, [rdi+30h]; Buf1
0x180042ea4  call    memcmp_0
0x180042ea9  xor     r11d, r11d
0x180042eac  test    eax, eax
0x180042eae  jnz     short loc_180042F2D
0x180042eb0  mov     rax, [rdi+20h]
0x180042eb4  test    rbx, rbx
0x180042eb7  jz      short loc_180042ED3
0x180042eb9  test    rax, rax
0x180042ebc  jz      short loc_180042F2D
0x180042ebe  mov     rdx, rax; pSid2
0x180042ec1  mov     rcx, rbx; pSid1
0x180042ec4  call    cs:__imp_EqualSid
0x180042eca  xor     r11d, r11d
0x180042ecd  test    eax, eax
0x180042ecf  jz      short loc_180042F2D
0x180042ed1  jmp     short loc_180042ED8
0x180042ed3  test    rax, rax
0x180042ed6  jnz     short loc_180042F2D
0x180042ed8  mov     r8d, r11d
0x180042edb  test    r12d, r12d
0x180042ede  jz      short loc_180042F28
0x180042ee0  mov     r10, [rdi+40h]
0x180042ee4  mov     rdx, [rsp+118h+var_A8]
0x180042ee9  mov     eax, r8d
0x180042eec  mov     rcx, [r10+rax*8]
0x180042ef0  mov     rdx, [rdx+rax*8]
0x180042ef4  test    rcx, rcx
0x180042ef7  jnz     short loc_180042EFE
0x180042ef9  test    rdx, rdx
0x180042efc  jmp     short loc_180042F1E
0x180042efe  test    rdx, rdx
0x180042f01  jz      short loc_180042F2D
0x180042f03  sub     rdx, rcx
0x180042f06  movzx   r9d, word ptr [rcx]
0x180042f0a  movzx   eax, word ptr [rcx+rdx]
0x180042f0e  sub     r9d, eax
0x180042f11  jnz     short loc_180042F1B
0x180042f13  add     rcx, 2
0x180042f17  test    eax, eax
0x180042f19  jnz     short loc_180042F06
0x180042f1b  test    r9d, r9d
0x180042f1e  jnz     short loc_180042F2D
0x180042f20  inc     r8d
0x180042f23  cmp     r8d, r12d
0x180042f26  jb      short loc_180042EE4
0x180042f28  cmp     r8d, r12d
0x180042f2b  jz      short loc_180042F42
0x180042f2d  mov     rbx, [rsp+118h+pSid]
0x180042f32  mov     rdi, r15
0x180042f35  mov     rbp, [rsp+118h+lpCriticalSection]
0x180042f3a  xor     r11d, r11d
0x180042f3d  jmp     loc_180042DDA
0x180042f42  mov     rax, [rdi]
0x180042f45  cmp     [rax+8], rdi
0x180042f49  jnz     loc_1800431F6
0x180042f4f  mov     rcx, [rdi+8]
0x180042f53  cmp     [rcx], rdi
0x180042f56  jnz     loc_1800431F6
0x180042f5c  mov     [rcx], rax
0x180042f5f  mov     [rax+8], rcx
0x180042f63  mov     rax, [rsi]
0x180042f66  cmp     [rax+8], rsi
0x180042f6a  jnz     loc_1800431F6
0x180042f70  mov     [rdi], rax
0x180042f73  mov     ebp, 0B7h
0x180042f78  mov     [rdi+8], rsi
0x180042f7c  mov     [rax+8], rdi
0x180042f80  mov     [rsi], rdi
0x180042f83  inc     dword ptr [rdi+4Ch]
0x180042f86  jmp     loc_180042D35
0x180042f8b  mov     rdi, [rsp+118h+var_A8]
0x180042f90  mov     esi, [rsp+118h+var_B8]
0x180042f94  mov     r15d, [rsp+118h+var_BC]
0x180042f99  mov     rdx, [rbp+40h]; lpSourceName
0x180042f9d  xor     ecx, ecx; lpUNCServerName
0x180042f9f  call    cs:__imp_RegisterEventSourceW
0x180042fa5  mov     rbx, rax
0x180042fa8  test    rax, rax
0x180042fab  jnz     short loc_180042FBA
0x180042fad  call    cs:__imp_GetLastError
0x180042fb3  mov     ebp, eax
0x180042fb5  xor     r15d, r15d
0x180042fb8  jmp     short loc_18004300B
0x180042fba  mov     rax, [rsp+118h+Buf2]
0x180042fbf  movzx   r8d, r15w; wCategory
0x180042fc3  mov     r9d, [rsp+118h+dwEventID]; dwEventID
0x180042fc8  xor     r15d, r15d
0x180042fcb  mov     [rsp+118h+lpRawData], rax; lpRawData
0x180042fd0  movzx   edx, si; wType
0x180042fd3  mov     [rsp+118h+lpStrings], rdi; lpStrings
0x180042fd8  mov     rcx, rbx; hEventLog
0x180042fdb  mov     [rsp+118h+dwDataSize], r13d; dwDataSize
0x180042fe0  mov     [rsp+118h+wNumStrings], r12w; wNumStrings
0x180042fe6  mov     [rsp+118h+lpUserSid], r15; lpUserSid
0x180042feb  call    cs:__imp_ReportEventW
0x180042ff1  test    eax, eax
0x180042ff3  jnz     short loc_180042FFF
0x180042ff5  call    cs:__imp_GetLastError
0x180042ffb  mov     ebp, eax
0x180042ffd  jmp     short loc_180043002
0x180042fff  mov     ebp, r15d
0x180043002  mov     rcx, rbx; hEventLog
0x180043005  call    cs:__imp_DeregisterEventSource
0x18004300b  test    ebp, ebp
0x18004300d  jnz     loc_180042D35
0x180043013  test    r14d, r14d
0x180043016  jnz     loc_180042D35
0x18004301c  lea     ebx, [r13+50h]
0x180043020  cmp     ebx, 50h ; 'P'
0x180043023  jb      loc_180042D35
0x180043029  mov     r14, [rsp+118h+pSid]
0x18004302e  mov     r8d, r15d
0x180043031  mov     edx, ebx
0x180043033  mov     r11d, 0C0000095h
0x180043039  test    r14, r14
0x18004303c  jz      short loc_180043066
0x18004303e  mov     rcx, r14; pSid
0x180043041  call    cs:__imp_GetLengthSid
0x180043047  or      edx, 0FFFFFFFFh
0x18004304a  mov     r11d, 0C0000095h
0x180043050  lea     ecx, [rax+rbx]
0x180043053  cmp     ecx, ebx
0x180043055  cmovnb  edx, ecx
0x180043058  sbb     r8d, r8d
0x18004305b  and     r8d, r11d
0x18004305e  cmp     ecx, ebx
0x180043060  jb      loc_180042D35
0x180043066  mov     r9d, r15d
0x180043069  test    r12d, r12d
0x18004306c  jz      short loc_1800430D4
0x18004306e  test    r8d, r8d
0x180043071  js      loc_180042D35
0x180043077  lea     ecx, [rdx+8]
0x18004307a  cmp     ecx, edx
0x18004307c  jb      short loc_1800430BB
0x18004307e  mov     eax, r9d
0x180043081  mov     r8d, r15d
0x180043084  mov     edx, ecx
0x180043086  mov     r10, [rdi+rax*8]
0x18004308a  test    r10, r10
0x18004308d  jz      short loc_1800430C3
0x18004308f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043093  inc     rax
0x180043096  cmp     [r10+rax*2], r15w
0x18004309b  jnz     short loc_180043093
0x18004309d  lea     r8d, [rcx+rax*2]
0x1800430a1  cmp     r8d, ecx
0x1800430a4  jb      short loc_1800430BB
0x1800430a6  lea     eax, [r8+2]
0x1800430aa  or      edx, 0FFFFFFFFh
0x1800430ad  cmp     eax, r8d
0x1800430b0  cmovnb  edx, eax
0x1800430b3  sbb     r8d, r8d
0x1800430b6  and     r8d, r11d
0x1800430b9  jmp     short loc_1800430C3
0x1800430bb  mov     r8d, r11d
0x1800430be  mov     edx, 0FFFFFFFFh; uBytes
0x1800430c3  inc     r9d
0x1800430c6  cmp     r9d, r12d
0x1800430c9  jb      short loc_18004306E
0x1800430cb  test    r8d, r8d
0x1800430ce  js      loc_180042D35
0x1800430d4  xor     ecx, ecx; uFlags
0x1800430d6  mov     r15d, edx
0x1800430d9  call    cs:__imp_LocalAlloc
0x1800430df  xor     edx, edx
0x1800430e1  mov     rbx, rax
0x1800430e4  test    rax, rax
0x1800430e7  jz      loc_180042D35
0x1800430ed  mov     eax, [rsp+118h+dwEventID]
0x1800430f1  lea     rcx, [rbx+10h]; lpSystemTimeAsFileTime
0x1800430f5  mov     [rbx+18h], eax
  ... truncated ...
```
