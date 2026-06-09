# NetpEventlogWriteEx3

- ea: `0x180071ad0`
- end: `0x180071f05`
- name: `NetpEventlogWriteEx3`
- size: `1077`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bcf8`
- `0x18000be4c`
- `0x18000c57c`
- `0x18000c700`
- `0x18000ca04`
- `0x18000e440`
- `0x18006d778`

## callees

- `0x180002ad0`
- `0x1800038d8`
- `0x1800038e4`
- `0x1800038f0`
- `0x180071ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071b43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180071b43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071ed9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071d39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071ddf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071ddf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071bbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071bbd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180071b7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180071e1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180071b7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180071e1b`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180071cdb`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180071cdb`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180071d2f`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180071d2f`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180071d49`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180071d49`

## pseudocode

```c
__int64 __fastcall NetpEventlogWriteEx3(
        struct _RTL_CRITICAL_SECTION *a1,
        int a2,
        int a3,
        DWORD a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        LPCWSTR *lpStrings,
        unsigned int wNumStrings,
        void *lpRawData,
        DWORD Size)
{
  DWORD v11; // ebp
  int v13; // esi
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  struct _RTL_CRITICAL_SECTION *v15; // r14
  struct _RTL_CRITICAL_SECTION_DEBUG *DebugInfo; // rdi
  __int64 OwningThread_low; // rsi
  struct _RTL_CRITICAL_SECTION *v18; // rbp
  struct _LIST_ENTRY *Flink; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *v20; // rcx
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rax
  unsigned int v22; // r8d
  char *v23; // rcx
  LPCWSTR v24; // rdx
  bool v25; // zf
  signed __int64 v26; // rdx
  int v27; // eax
  int v28; // r9d
  struct _RTL_CRITICAL_SECTION *v29; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG **p_DebugInfo; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v31; // rax
  DWORD LastError; // ebp
  HANDLE v33; // rbx
  LPCWSTR *v34; // rdi
  unsigned int v35; // ecx
  signed int v36; // edx
  unsigned int v37; // r9d
  unsigned int v38; // r8d
  LPCWSTR v39; // r10
  __int64 v40; // rax
  unsigned int v41; // edx
  __int64 v42; // r12
  HLOCAL v43; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v44; // rbx
  wchar_t *v45; // rsi
  unsigned int v46; // r15d
  __int64 v47; // rdi
  struct _LIST_ENTRY *v48; // rax
  __int64 v49; // rax
  PRTL_CRITICAL_SECTION_DEBUG v50; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-60h] BYREF
  struct _RTL_CRITICAL_SECTION *v57; // [rsp+80h] [rbp-58h]

  v11 = a4;
  v13 = a2;
  v14 = a1;
  EnterCriticalSection(a1);
  v15 = v14 + 1;
  DebugInfo = v14[1].DebugInfo;
  v57 = v14 + 1;
  if ( DebugInfo != (struct _RTL_CRITICAL_SECTION_DEBUG *)&v14[1] )
  {
    while ( 1 )
    {
      OwningThread_low = LODWORD(v14[1].OwningThread);
      v18 = *(struct _RTL_CRITICAL_SECTION **)&DebugInfo->Type;
      SystemTimeAsFileTime = 0;
      if ( (_DWORD)OwningThread_low == -1
        || (Flink = DebugInfo->ProcessLocksList.Flink,
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
            (__int64)(*(_QWORD *)&SystemTimeAsFileTime - (_QWORD)Flink) >= 0)
        && *(_QWORD *)&SystemTimeAsFileTime - (_QWORD)Flink <= 10000 * OwningThread_low )
      {
        if ( LODWORD(DebugInfo->ProcessLocksList.Blink) == a4 )
        {
          v13 = a2;
          if ( HIDWORD(DebugInfo->ProcessLocksList.Blink) == a2
            && DebugInfo->Flags == a3
            && LODWORD(DebugInfo[1].CriticalSection) == Size
            && LODWORD(DebugInfo[1].ProcessLocksList.Blink) == wNumStrings
            && (!Size || !memcmp_0(*(const void **)&DebugInfo[1].Type, lpRawData, Size))
            && !*(_QWORD *)&DebugInfo->EntryCount )
          {
            v22 = 0;
            if ( wNumStrings )
            {
              while ( 1 )
              {
                v23 = (char *)*((_QWORD *)&DebugInfo[1].ProcessLocksList.Flink->Flink + v22);
                v24 = lpStrings[v22];
                if ( v23 )
                {
                  if ( !v24 )
                    goto LABEL_9;
                  v26 = (char *)v24 - v23;
                  do
                  {
                    v27 = *(unsigned __int16 *)&v23[v26];
                    v28 = *(unsigned __int16 *)v23 - v27;
                    if ( v28 )
                      break;
                    v23 += 2;
                  }
                  while ( v27 );
                  v25 = v28 == 0;
                }
                else
                {
                  v25 = v24 == 0;
                }
                if ( !v25 )
                  break;
                if ( ++v22 >= wNumStrings )
                  goto LABEL_29;
              }
            }
            else
            {
LABEL_29:
              if ( v22 == wNumStrings )
              {
                v29 = *(struct _RTL_CRITICAL_SECTION **)&DebugInfo->Type;
                if ( *(struct _RTL_CRITICAL_SECTION_DEBUG **)(*(_QWORD *)&DebugInfo->Type + 8LL) != DebugInfo )
                  goto LABEL_70;
                p_DebugInfo = &DebugInfo->CriticalSection->DebugInfo;
                if ( *p_DebugInfo != DebugInfo )
                  goto LABEL_70;
                *p_DebugInfo = (struct _RTL_CRITICAL_SECTION_DEBUG *)v29;
                *(_QWORD *)&v29->LockCount = p_DebugInfo;
                v31 = v15->DebugInfo;
                if ( v15->DebugInfo->CriticalSection != v15 )
                  goto LABEL_70;
                *(_QWORD *)&DebugInfo->Type = v31;
                LastError = 183;
                DebugInfo->CriticalSection = v15;
                v31->CriticalSection = (struct _RTL_CRITICAL_SECTION *)DebugInfo;
                v15->DebugInfo = DebugInfo;
                ++HIDWORD(DebugInfo[1].ProcessLocksList.Blink);
                goto LABEL_72;
              }
            }
          }
          goto LABEL_9;
        }
      }
      else
      {
        v20 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type;
        if ( *(struct _RTL_CRITICAL_SECTION_DEBUG **)(*(_QWORD *)&DebugInfo->Type + 8LL) != DebugInfo )
          goto LABEL_70;
        CriticalSection = DebugInfo->CriticalSection;
        if ( CriticalSection->DebugInfo != DebugInfo )
          goto LABEL_70;
        CriticalSection->DebugInfo = v20;
        v20->CriticalSection = CriticalSection;
        LocalFree(DebugInfo);
      }
      v13 = a2;
LABEL_9:
      v14 = a1;
      DebugInfo = (struct _RTL_CRITICAL_SECTION_DEBUG *)v18;
      if ( v18 == v15 )
      {
        v11 = a4;
        break;
      }
    }
  }
  v33 = RegisterEventSourceW(0, (LPCWSTR)v14[1].LockSemaphore);
  if ( v33 )
  {
    v34 = lpStrings;
    if ( ReportEventW(v33, v13, a3, v11, 0, wNumStrings, Size, lpStrings, lpRawData) )
      LastError = 0;
    else
      LastError = GetLastError();
    DeregisterEventSource(v33);
  }
  else
  {
    v34 = lpStrings;
    LastError = GetLastError();
  }
  if ( LastError )
    goto LABEL_72;
  v35 = Size + 80;
  if ( Size >= 0xFFFFFFB0 )
    goto LABEL_72;
  v36 = 0;
  v37 = 0;
  if ( !wNumStrings )
    goto LABEL_57;
  do
  {
    if ( v36 < 0 )
      goto LABEL_72;
    v38 = v35 + 8;
    if ( v35 + 8 < v35 )
    {
      v35 = -1;
LABEL_54:
      v36 = -1073741675;
      goto LABEL_55;
    }
    v35 += 8;
    v36 = 0;
    v39 = v34[v37];
    if ( !v39 )
      goto LABEL_55;
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    v41 = v38 + 2 * v40;
    v35 = -1;
    if ( v41 < v38 )
      goto LABEL_54;
    if ( v41 + 2 >= v41 )
      v35 = v41 + 2;
    v36 = v41 + 2 < v41 ? 0xC0000095 : 0;
LABEL_55:
    ++v37;
  }
  while ( v37 < wNumStrings );
  if ( v36 >= 0 )
  {
LABEL_57:
    v42 = v35;
    v43 = LocalAlloc(0, v35);
    v44 = (struct _RTL_CRITICAL_SECTION_DEBUG *)v43;
    if ( v43 )
    {
      *((_DWORD *)v43 + 6) = a4;
      *((_DWORD *)v43 + 10) = a3;
      *((_DWORD *)v43 + 7) = v13;
      *((_QWORD *)v43 + 4) = 0;
      *((_DWORD *)v43 + 14) = Size;
      *((_DWORD *)v43 + 18) = wNumStrings;
      *((_DWORD *)v43 + 19) = 1;
      GetSystemTimeAsFileTime((LPFILETIME)v43 + 2);
      v44[1].ProcessLocksList.Flink = (struct _LIST_ENTRY *)&v44[1].EntryCount;
      v45 = (wchar_t *)(&v44[1].EntryCount + 2 * wNumStrings);
      v46 = 0;
      if ( wNumStrings )
      {
        v47 = 0;
        do
        {
          v48 = v44[1].ProcessLocksList.Flink;
          if ( lpStrings[v47] )
          {
            *((_QWORD *)&v48->Flink + v47) = v45;
            wcscpy_s(v45, ((unsigned __int64)v44 + v42 - (_QWORD)v45) >> 1, lpStrings[v47]);
            v49 = -1;
            do
              ++v49;
            while ( lpStrings[v47][v49] );
            v45 += v49 + 1;
          }
          else
          {
            *((_QWORD *)&v48->Flink + v47) = 0;
          }
          ++v46;
          ++v47;
        }
        while ( v46 < wNumStrings );
        v15 = v57;
      }
      if ( Size )
      {
        *(_QWORD *)&v44[1].Type = v45;
        memcpy_0(v45, lpRawData, Size);
      }
      v50 = v15->DebugInfo;
      if ( v15->DebugInfo->CriticalSection != v15 )
LABEL_70:
        __fastfail(3u);
      *(_QWORD *)&v44->Type = v50;
      v44->CriticalSection = v15;
      v50->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v44;
      v15->DebugInfo = v44;
    }
  }
LABEL_72:
  LeaveCriticalSection(a1);
  return LastError;
}

```

## disassembly

```asm
0x180071ad0  push    rbx
0x180071ad2  push    rbp
0x180071ad3  push    rsi
0x180071ad4  push    rdi
0x180071ad5  push    r12
0x180071ad7  push    r13
0x180071ad9  push    r14
0x180071adb  push    r15
0x180071add  sub     rsp, 98h
0x180071ae4  mov     rax, cs:__security_cookie
0x180071aeb  xor     rax, rsp
0x180071aee  mov     [rsp+0D8h+var_50], rax
0x180071af6  mov     rax, [rsp+0D8h+arg_38]
0x180071afe  mov     ebp, r9d
0x180071b01  mov     r15d, dword ptr [rsp+0D8h+Size]
0x180071b09  mov     r12d, r8d
0x180071b0c  mov     r13d, dword ptr [rsp+0D8h+arg_40]
0x180071b14  mov     esi, edx
0x180071b16  mov     [rsp+0D8h+var_80], rax
0x180071b1b  mov     rbx, rcx
0x180071b1e  mov     rax, [rsp+0D8h+arg_48]
0x180071b26  mov     [rsp+0D8h+var_74+4], rax
0x180071b2b  mov     [rsp+0D8h+var_84], r9d
0x180071b30  mov     [rsp+0D8h+var_78], r8d
0x180071b35  mov     [rsp+0D8h+var_88], edx
0x180071b39  mov     [rsp+0D8h+lpCriticalSection], rcx
0x180071b3e  mov     dword ptr [rsp+0D8h+var_74], r15d
0x180071b43  call    cs:__imp_EnterCriticalSection
0x180071b49  lea     r14, [rbx+28h]
0x180071b4d  xor     r11d, r11d
0x180071b50  mov     rdi, [r14]
0x180071b53  mov     [rsp+0D8h+var_58], r14
0x180071b5b  cmp     rdi, r14
0x180071b5e  jz      loc_180071CD5
0x180071b64  mov     esi, [rbx+38h]
0x180071b67  mov     rbp, [rdi]
0x180071b6a  mov     qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime], r11
0x180071b6f  cmp     esi, 0FFFFFFFFh
0x180071b72  jz      short loc_180071BE0
0x180071b74  mov     rbx, [rdi+10h]
0x180071b78  lea     rcx, [rsp+0D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180071b7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180071b83  mov     rdx, qword ptr [rsp+0D8h+SystemTimeAsFileTime.dwLowDateTime]
0x180071b88  sub     rdx, rbx
0x180071b8b  js      short loc_180071B99
0x180071b8d  imul    rcx, rsi, 2710h
0x180071b94  cmp     rdx, rcx
0x180071b97  jle     short loc_180071BDD
0x180071b99  mov     rcx, [rdi]
0x180071b9c  cmp     [rcx+8], rdi
0x180071ba0  jnz     loc_180071EBF
0x180071ba6  mov     rax, [rdi+8]
0x180071baa  cmp     [rax], rdi
0x180071bad  jnz     loc_180071EBF
0x180071bb3  mov     [rax], rcx
0x180071bb6  mov     [rcx+8], rax
0x180071bba  mov     rcx, rdi; hMem
0x180071bbd  call    cs:__imp_LocalFree
0x180071bc3  mov     esi, [rsp+0D8h+var_88]
0x180071bc7  mov     rbx, [rsp+0D8h+lpCriticalSection]
0x180071bcc  mov     rdi, rbp
0x180071bcf  cmp     rbp, r14
0x180071bd2  jz      loc_180071CD1
0x180071bd8  xor     r11d, r11d
0x180071bdb  jmp     short loc_180071B64
0x180071bdd  xor     r11d, r11d
0x180071be0  mov     eax, [rsp+0D8h+var_84]
0x180071be4  cmp     [rdi+18h], eax
0x180071be7  jnz     short loc_180071BC3
0x180071be9  mov     esi, [rsp+0D8h+var_88]
0x180071bed  cmp     [rdi+1Ch], esi
0x180071bf0  jnz     short loc_180071BC7
0x180071bf2  cmp     [rdi+28h], r12d
0x180071bf6  jnz     short loc_180071BC7
0x180071bf8  cmp     [rdi+38h], r15d
0x180071bfc  jnz     short loc_180071BC7
0x180071bfe  cmp     [rdi+48h], r13d
0x180071c02  jnz     short loc_180071BC7
0x180071c04  test    r15d, r15d
0x180071c07  jz      short loc_180071C21
0x180071c09  mov     rdx, [rsp+0D8h+var_74+4]; Buf2
0x180071c0e  mov     r8, r15; Size
0x180071c11  mov     rcx, [rdi+30h]; Buf1
0x180071c15  call    memcmp_0
0x180071c1a  xor     r11d, r11d
0x180071c1d  test    eax, eax
0x180071c1f  jnz     short loc_180071BC7
0x180071c21  cmp     [rdi+20h], r11
0x180071c25  jnz     short loc_180071BC7
0x180071c27  mov     r8d, r11d
0x180071c2a  test    r13d, r13d
0x180071c2d  jz      short loc_180071C7F
0x180071c2f  mov     r10, [rdi+40h]
0x180071c33  mov     rdx, [rsp+0D8h+var_80]
0x180071c38  mov     eax, r8d
0x180071c3b  mov     rcx, [r10+rax*8]
0x180071c3f  mov     rdx, [rdx+rax*8]
0x180071c43  test    rcx, rcx
0x180071c46  jnz     short loc_180071C4D
0x180071c48  test    rdx, rdx
0x180071c4b  jmp     short loc_180071C71
0x180071c4d  test    rdx, rdx
0x180071c50  jz      loc_180071BC7
0x180071c56  sub     rdx, rcx
0x180071c59  movzx   r9d, word ptr [rcx]
0x180071c5d  movzx   eax, word ptr [rcx+rdx]
0x180071c61  sub     r9d, eax
0x180071c64  jnz     short loc_180071C6E
0x180071c66  add     rcx, 2
0x180071c6a  test    eax, eax
0x180071c6c  jnz     short loc_180071C59
0x180071c6e  test    r9d, r9d
0x180071c71  jnz     loc_180071BC7
0x180071c77  inc     r8d
0x180071c7a  cmp     r8d, r13d
0x180071c7d  jb      short loc_180071C33
0x180071c7f  cmp     r8d, r13d
0x180071c82  jnz     loc_180071BC7
0x180071c88  mov     rax, [rdi]
0x180071c8b  cmp     [rax+8], rdi
0x180071c8f  jnz     loc_180071EBF
0x180071c95  mov     rcx, [rdi+8]
0x180071c99  cmp     [rcx], rdi
0x180071c9c  jnz     loc_180071EBF
0x180071ca2  mov     [rcx], rax
0x180071ca5  mov     [rax+8], rcx
0x180071ca9  mov     rax, [r14]
0x180071cac  cmp     [rax+8], r14
0x180071cb0  jnz     loc_180071EBF
0x180071cb6  mov     [rdi], rax
0x180071cb9  mov     ebp, 0B7h
0x180071cbe  mov     [rdi+8], r14
0x180071cc2  mov     [rax+8], rdi
0x180071cc6  mov     [r14], rdi
0x180071cc9  inc     dword ptr [rdi+4Ch]
0x180071ccc  jmp     loc_180071ED4
0x180071cd1  mov     ebp, [rsp+0D8h+var_84]
0x180071cd5  mov     rdx, [rbx+40h]; lpSourceName
0x180071cd9  xor     ecx, ecx; lpUNCServerName
0x180071cdb  call    cs:__imp_RegisterEventSourceW
0x180071ce1  mov     rbx, rax
0x180071ce4  test    rax, rax
0x180071ce7  jnz     short loc_180071CFB
0x180071ce9  call    cs:__imp_GetLastError
0x180071cef  mov     rdi, [rsp+0D8h+var_80]
0x180071cf4  xor     r12d, r12d
0x180071cf7  mov     ebp, eax
0x180071cf9  jmp     short loc_180071D4F
0x180071cfb  mov     rax, [rsp+0D8h+var_74+4]
0x180071d00  movzx   r8d, r12w; wCategory
0x180071d04  mov     rdi, [rsp+0D8h+var_80]
0x180071d09  xor     r12d, r12d
0x180071d0c  mov     [rsp+0D8h+lpRawData], rax; lpRawData
0x180071d11  movzx   edx, si; wType
0x180071d14  mov     [rsp+0D8h+lpStrings], rdi; lpStrings
0x180071d19  mov     r9d, ebp; dwEventID
0x180071d1c  mov     [rsp+0D8h+dwDataSize], r15d; dwDataSize
0x180071d21  mov     rcx, rbx; hEventLog
0x180071d24  mov     [rsp+0D8h+wNumStrings], r13w; wNumStrings
0x180071d2a  mov     [rsp+0D8h+lpUserSid], r12; lpUserSid
0x180071d2f  call    cs:__imp_ReportEventW
0x180071d35  test    eax, eax
0x180071d37  jnz     short loc_180071D43
0x180071d39  call    cs:__imp_GetLastError
0x180071d3f  mov     ebp, eax
0x180071d41  jmp     short loc_180071D46
0x180071d43  mov     ebp, r12d
0x180071d46  mov     rcx, rbx; hEventLog
0x180071d49  call    cs:__imp_DeregisterEventSource
0x180071d4f  test    ebp, ebp
0x180071d51  jnz     loc_180071ED4
0x180071d57  lea     ecx, [r15+50h]
0x180071d5b  cmp     ecx, 50h ; 'P'
0x180071d5e  jb      loc_180071ED4
0x180071d64  mov     edx, r12d
0x180071d67  mov     r9d, r12d
0x180071d6a  test    r13d, r13d
0x180071d6d  jz      short loc_180071DD8
0x180071d6f  mov     r11d, 0C0000095h
0x180071d75  or      ebx, 0FFFFFFFFh
0x180071d78  test    edx, edx
0x180071d7a  js      loc_180071ED4
0x180071d80  lea     r8d, [rcx+8]
0x180071d84  cmp     r8d, ecx
0x180071d87  jb      short loc_180071DC3
0x180071d89  mov     eax, r9d
0x180071d8c  mov     ecx, r8d
0x180071d8f  mov     edx, r12d
0x180071d92  mov     r10, [rdi+rax*8]
0x180071d96  test    r10, r10
0x180071d99  jz      short loc_180071DC8
0x180071d9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180071d9f  inc     rax
0x180071da2  cmp     [r10+rax*2], r12w
0x180071da7  jnz     short loc_180071D9F
0x180071da9  lea     edx, [r8+rax*2]
0x180071dad  mov     ecx, ebx
0x180071daf  cmp     edx, r8d
0x180071db2  jb      short loc_180071DC5
0x180071db4  lea     eax, [rdx+2]
0x180071db7  cmp     eax, edx
0x180071db9  cmovnb  ecx, eax
0x180071dbc  sbb     edx, edx
0x180071dbe  and     edx, r11d
0x180071dc1  jmp     short loc_180071DC8
0x180071dc3  mov     ecx, ebx
0x180071dc5  mov     edx, r11d
0x180071dc8  inc     r9d
0x180071dcb  cmp     r9d, r13d
0x180071dce  jb      short loc_180071D78
0x180071dd0  test    edx, edx
0x180071dd2  js      loc_180071ED4
0x180071dd8  mov     r12d, ecx
0x180071ddb  mov     edx, ecx; uBytes
0x180071ddd  xor     ecx, ecx; uFlags
0x180071ddf  call    cs:__imp_LocalAlloc
0x180071de5  xor     edx, edx
0x180071de7  mov     rbx, rax
0x180071dea  test    rax, rax
0x180071ded  jz      loc_180071ED4
0x180071df3  mov     eax, [rsp+0D8h+var_84]
0x180071df7  lea     rcx, [rbx+10h]; lpSystemTimeAsFileTime
0x180071dfb  mov     [rbx+18h], eax
0x180071dfe  mov     eax, [rsp+0D8h+var_78]
0x180071e02  mov     [rbx+28h], eax
0x180071e05  mov     [rbx+1Ch], esi
0x180071e08  mov     [rbx+20h], rdx
0x180071e0c  mov     [rbx+38h], r15d
0x180071e10  mov     [rbx+48h], r13d
0x180071e14  mov     dword ptr [rbx+4Ch], 1
0x180071e1b  call    cs:__imp_GetSystemTimeAsFileTime
0x180071e21  lea     rcx, [rbx+50h]
0x180071e25  mov     [rbx+40h], rcx
0x180071e29  lea     rsi, [rcx+r13*8]
0x180071e2d  xor     ecx, ecx
0x180071e2f  mov     r15d, ecx
0x180071e32  test    r13d, r13d
0x180071e35  jz      short loc_180071E9A
0x180071e37  mov     r14, [rsp+0D8h+var_80]
0x180071e3c  mov     edi, ecx
0x180071e3e  mov     rax, [rbx+40h]
0x180071e42  cmp     [r14+rdi*8], rcx
0x180071e46  jnz     short loc_180071E4E
0x180071e48  mov     [rax+rdi*8], rcx
0x180071e4c  jmp     short loc_180071E87
0x180071e4e  mov     [rax+rdi*8], rsi
0x180071e52  mov     rdx, r12
0x180071e55  mov     r8, [r14+rdi*8]; Source
0x180071e59  sub     rdx, rsi
0x180071e5c  add     rdx, rbx
0x180071e5f  mov     rcx, rsi; Destination
0x180071e62  shr     rdx, 1; SizeInWords
0x180071e65  call    wcscpy_s
0x180071e6a  mov     rcx, [r14+rdi*8]
0x180071e6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180071e72  xor     edx, edx
0x180071e74  inc     rax
0x180071e77  cmp     [rcx+rax*2], dx
0x180071e7b  jnz     short loc_180071E74
0x180071e7d  lea     rsi, [rsi+rax*2]
0x180071e81  add     rsi, 2
0x180071e85  xor     ecx, ecx
0x180071e87  inc     r15d
0x180071e8a  inc     rdi
0x180071e8d  cmp     r15d, r13d
0x180071e90  jb      short loc_180071E3E
0x180071e92  mov     r14, [rsp+0D8h+var_58]
0x180071e9a  mov     eax, dword ptr [rsp+0D8h+var_74]
0x180071e9e  test    eax, eax
0x180071ea0  jz      short loc_180071EB6
0x180071ea2  mov     rdx, [rsp+0D8h+var_74+4]; Src
0x180071ea7  mov     r8d, eax; Size
0x180071eaa  mov     rcx, rsi; void *
0x180071ead  mov     [rbx+30h], rsi
0x180071eb1  call    memcpy_0
0x180071eb6  mov     rax, [r14]
0x180071eb9  cmp     [rax+8], r14
0x180071ebd  jz      short loc_180071EC6
0x180071ebf  mov     ecx, 3
0x180071ec4  int     29h; Win8: RtlFailFast(ecx)
0x180071ec6  mov     [rbx], rax
0x180071ec9  mov     [rbx+8], r14
0x180071ecd  mov     [rax+8], rbx
0x180071ed1  mov     [r14], rbx
0x180071ed4  mov     rcx, [rsp+0D8h+lpCriticalSection]; lpCriticalSection
0x180071ed9  call    cs:__imp_LeaveCriticalSection
0x180071edf  mov     eax, ebp
0x180071ee1  mov     rcx, [rsp+0D8h+var_50]
0x180071ee9  xor     rcx, rsp; StackCookie
0x180071eec  call    __security_check_cookie
0x180071ef1  add     rsp, 98h
0x180071ef8  pop     r15
0x180071efa  pop     r14
0x180071efc  pop     r13
0x180071efe  pop     r12
0x180071f00  pop     rdi
0x180071f01  pop     rsi
0x180071f02  pop     rbp
0x180071f03  pop     rbx
0x180071f04  retn
  ... truncated ...
```
