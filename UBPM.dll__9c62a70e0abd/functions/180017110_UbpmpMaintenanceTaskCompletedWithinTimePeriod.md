# UbpmpMaintenanceTaskCompletedWithinTimePeriod

- ea: `0x180017110`
- end: `0x18001757f`
- name: `UbpmpMaintenanceTaskCompletedWithinTimePeriod`
- size: `1135`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e500`

## callees

- `0x180017110`
- `0x1800182a0`
- `0x180018560`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800171ea`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800171ea`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001717f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001717f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017562`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001716c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001716c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001737b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800173dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800173f4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017438`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017454`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017479`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001737b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800173dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800173f4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017438`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017454`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017479`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180017310`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180017310`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017237`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017343`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001735f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017521`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017237`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017343`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001735f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017521`

## pseudocode

```c
__int64 __fastcall UbpmpMaintenanceTaskCompletedWithinTimePeriod(__int64 a1, _BYTE *a2)
{
  __int64 v4; // rax
  _WORD *v5; // rbx
  unsigned __int64 v6; // rdx
  DWORD LastError; // ebx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  int v12; // r8d
  struct _FILETIME FileTime; // [rsp+30h] [rbp-39h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-31h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-29h] BYREF
  FILETIME v16; // [rsp+48h] [rbp-21h] BYREF
  SYSTEMTIME SystemTime; // [rsp+50h] [rbp-19h] BYREF
  SYSTEMTIME v18; // [rsp+60h] [rbp-9h] BYREF
  FILETIME FileTime2[2]; // [rsp+70h] [rbp+7h] BYREF
  FILETIME v20[2]; // [rsp+80h] [rbp+17h] BYREF
  int v21; // [rsp+90h] [rbp+27h]

  FileTime1 = 0;
  v16 = 0;
  SystemTimeAsFileTime = 0;
  v21 = 0;
  SystemTime = 0;
  *a2 = 0;
  v18 = 0;
  *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
  *(_OWORD *)&v20[0].dwLowDateTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  RtlAcquireSRWLockShared(&g_SystemSetup);
  SystemTime = (SYSTEMTIME)xmmword_18004FB52;
  RtlReleaseSRWLockShared(&g_SystemSetup);
  if ( !*(_DWORD *)&SystemTime.wYear && !SystemTime.wDay )
    goto LABEL_18;
  v4 = *(_QWORD *)(a1 + 24);
  FileTime = 0;
  v5 = *(_WORD **)(v4 + 48);
  if ( *v5 || v5[1] )
  {
    if ( (unsigned __int16)(SystemTime.wYear + *v5 + ((unsigned __int16)v5[1] + SystemTime.wMonth - 1) / 12) < SystemTime.wYear )
      return 534;
    v18.wYear = SystemTime.wYear + *v5 + ((unsigned __int16)v5[1] + SystemTime.wMonth - 1) / 12;
    v12 = SystemTime.wMonth - 1 + (unsigned __int16)v5[1];
    v18.wDay = SystemTime.wDay;
    v18.wHour = SystemTime.wHour;
    v18.wMinute = SystemTime.wMinute;
    v18.wSecond = SystemTime.wSecond;
    v18.wMilliseconds = SystemTime.wMilliseconds;
    v18.wMonth = v12 % 12 + 1;
    while ( !SystemTimeToFileTime(&v18, &FileTime) )
    {
      if ( v18.wDay <= 0x1Cu )
        return 87;
      --v18.wDay;
    }
  }
  else if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    goto LABEL_14;
  }
  v6 = *(_QWORD *)&FileTime + 6048000000000LL * (unsigned __int16)v5[2];
  if ( v6 < *(_QWORD *)&FileTime )
    return 534;
  v9 = v6 + 864000000000LL * (unsigned __int16)v5[3];
  if ( v9 < v6 )
    return 534;
  v10 = v9 + 36000000000LL * (unsigned __int16)v5[4];
  if ( v10 < v9 )
    return 534;
  v11 = v10 + 600000000LL * (unsigned __int16)v5[5];
  if ( v11 < v10 || v11 + 10000000LL * (unsigned __int16)v5[6] < v11 )
    return 534;
  FileTime = (struct _FILETIME)(v11 + 10000000LL * (unsigned __int16)v5[6]);
  if ( !FileTimeToSystemTime(&FileTime, &v18) )
  {
LABEL_14:
    LastError = GetLastError();
    if ( LastError )
      return LastError;
    goto LABEL_15;
  }
  LastError = 0;
LABEL_15:
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime1) || !SystemTimeToFileTime(&v18, &v16) )
    return GetLastError();
  if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) < 0 && CompareFileTime(&SystemTimeAsFileTime, &v16) <= 0 )
    goto LABEL_28;
LABEL_18:
  LastError = UbpmStatsOperation(a1, 0, FileTime2);
  if ( !LastError )
  {
    if ( v21 )
    {
      if ( v20[1].dwHighDateTime )
      {
        if ( v20[1].dwLowDateTime != -2147023605
          && v20[1].dwLowDateTime != -2147023829
          && (CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)&FileTime2[0].dwHighDateTime) < 0
           || CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)&v20[1].dwHighDateTime) < 0
           || (LastError = UbpmpMaintenanceComputeCompletionPeriod(
                             &SystemTimeAsFileTime,
                             (FILETIME *)&FileTime2[0].dwHighDateTime,
                             *(struct _UBPM_TIMESPAN **)(*(_QWORD *)(a1 + 24) + 48LL),
                             (__int64)&v16)) == 0
           && CompareFileTime(&FileTime1, (const FILETIME *)&v20[1].dwHighDateTime) < 0
           && CompareFileTime((const FILETIME *)&v20[1].dwHighDateTime, &v16) <= 0) )
        {
LABEL_28:
          *a2 = 1;
        }
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180017110  mov     [rsp-8+arg_10], rbx
0x180017115  push    rbp
0x180017116  push    rsi
0x180017117  push    rdi
0x180017118  push    r14
0x18001711a  push    r15
0x18001711c  lea     rbp, [rsp-37h]
0x180017121  sub     rsp, 0A0h
0x180017128  mov     rax, cs:__security_cookie
0x18001712f  xor     rax, rsp
0x180017132  mov     [rbp+57h+var_28], rax
0x180017136  xorps   xmm0, xmm0
0x180017139  xor     r15d, r15d
0x18001713c  xor     eax, eax
0x18001713e  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r15
0x180017142  mov     rdi, rcx
0x180017145  mov     qword ptr [rbp+57h+var_78.dwLowDateTime], r15
0x180017149  xorps   xmm1, xmm1
0x18001714c  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180017150  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180017154  mov     [rbp+57h+var_30], eax
0x180017157  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001715b  mov     [rdx], al
0x18001715d  mov     r14, rdx
0x180017160  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm1
0x180017164  movups  xmmword ptr [rbp+57h+FileTime2.dwLowDateTime], xmm0
0x180017168  movups  xmmword ptr [rbp+57h+var_40.dwLowDateTime], xmm0
0x18001716c  call    cs:__imp_GetSystemTimeAsFileTime
0x180017173  nop     dword ptr [rax+rax+00h]
0x180017178  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x18001717f  call    cs:__imp_RtlAcquireSRWLockShared
0x180017186  nop     dword ptr [rax+rax+00h]
0x18001718b  movzx   eax, word ptr cs:xmmword_18004FB52
0x180017192  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x180017199  mov     [rbp+57h+SystemTime.wYear], ax
0x18001719d  movzx   eax, word ptr cs:xmmword_18004FB52+2
0x1800171a4  mov     [rbp+57h+SystemTime.wMonth], ax
0x1800171a8  movzx   eax, word ptr cs:xmmword_18004FB52+4
0x1800171af  mov     [rbp+57h+SystemTime.wDayOfWeek], ax
0x1800171b3  movzx   eax, word ptr cs:xmmword_18004FB52+6
0x1800171ba  mov     [rbp+57h+SystemTime.wDay], ax
0x1800171be  movzx   eax, word ptr cs:xmmword_18004FB52+8
0x1800171c5  mov     [rbp+57h+SystemTime.wHour], ax
0x1800171c9  movzx   eax, word ptr cs:xmmword_18004FB52+0Ah
0x1800171d0  mov     [rbp+57h+SystemTime.wMinute], ax
0x1800171d4  movzx   eax, word ptr cs:xmmword_18004FB52+0Ch
0x1800171db  mov     [rbp+57h+SystemTime.wSecond], ax
0x1800171df  movzx   eax, word ptr cs:xmmword_18004FB52+0Eh
0x1800171e6  mov     [rbp+57h+SystemTime.wMilliseconds], ax
0x1800171ea  call    cs:__imp_RtlReleaseSRWLockShared
0x1800171f1  nop     dword ptr [rax+rax+00h]
0x1800171f6  movzx   r10d, [rbp+57h+SystemTime.wYear]
0x1800171fb  movzx   r11d, [rbp+57h+SystemTime.wDay]
0x180017200  test    r10w, r10w
0x180017204  jz      loc_180017548
0x18001720a  mov     rax, [rdi+18h]
0x18001720e  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r15
0x180017212  mov     rbx, [rax+30h]
0x180017216  movzx   r9d, word ptr [rbx]
0x18001721a  test    r9w, r9w
0x18001721e  jnz     loc_18001748F
0x180017224  cmp     [rbx+2], r15w
0x180017229  jnz     loc_18001748F
0x18001722f  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180017233  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180017237  call    cs:__imp_SystemTimeToFileTime
0x18001723e  nop     dword ptr [rax+rax+00h]
0x180017243  test    eax, eax
0x180017245  jz      loc_180017325
0x18001724b  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x18001724e  mov     rdx, 58028E44000h
0x180017258  mov     ecx, [rbp+57h+FileTime.dwHighDateTime]
0x18001725b  shl     rcx, 20h
0x18001725f  or      rcx, rax
0x180017262  movzx   eax, word ptr [rbx+4]
0x180017266  imul    rdx, rax
0x18001726a  add     rdx, rcx
0x18001726d  cmp     rdx, rcx
0x180017270  jnb     short loc_18001729D
0x180017272  mov     ebx, 216h
0x180017277  mov     eax, ebx
0x180017279  mov     rcx, [rbp+57h+var_28]
0x18001727d  xor     rcx, rsp; StackCookie
0x180017280  call    __security_check_cookie
0x180017285  mov     rbx, [rsp+0C0h+arg_10]
0x18001728d  add     rsp, 0A0h
0x180017294  pop     r15
0x180017296  pop     r14
0x180017298  pop     rdi
0x180017299  pop     rsi
0x18001729a  pop     rbp
0x18001729b  retn
0x18001729d  movzx   eax, word ptr [rbx+6]
0x1800172a1  mov     rcx, 0C92A69C000h
0x1800172ab  imul    rcx, rax
0x1800172af  add     rcx, rdx
0x1800172b2  cmp     rcx, rdx
0x1800172b5  jb      short loc_180017272
0x1800172b7  movzx   eax, word ptr [rbx+8]
0x1800172bb  mov     rdx, 861C46800h
0x1800172c5  imul    rdx, rax
0x1800172c9  add     rdx, rcx
0x1800172cc  cmp     rdx, rcx
0x1800172cf  jb      short loc_180017272
0x1800172d1  movzx   eax, word ptr [rbx+0Ah]
0x1800172d5  imul    r8, rax, 23C34600h
0x1800172dc  add     r8, rdx
0x1800172df  cmp     r8, rdx
0x1800172e2  jb      short loc_180017272
0x1800172e4  movzx   eax, word ptr [rbx+0Ch]
0x1800172e8  imul    rax, 989680h
0x1800172ef  add     rax, r8
0x1800172f2  cmp     rax, r8
0x1800172f5  jb      loc_180017272
0x1800172fb  mov     rcx, rax
0x1800172fe  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180017301  shr     rcx, 20h
0x180017305  lea     rdx, [rbp+57h+var_60]; lpSystemTime
0x180017309  mov     [rbp+57h+FileTime.dwHighDateTime], ecx
0x18001730c  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x180017310  call    cs:__imp_FileTimeToSystemTime
0x180017317  nop     dword ptr [rax+rax+00h]
0x18001731c  test    eax, eax
0x18001731e  jz      short loc_180017325
0x180017320  mov     ebx, r15d
0x180017323  jmp     short loc_18001733B
0x180017325  call    cs:__imp_GetLastError
0x18001732c  nop     dword ptr [rax+rax+00h]
0x180017331  mov     ebx, eax
0x180017333  test    eax, eax
0x180017335  jnz     loc_180017277
0x18001733b  lea     rdx, [rbp+57h+FileTime1]; lpFileTime
0x18001733f  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180017343  call    cs:__imp_SystemTimeToFileTime
0x18001734a  nop     dword ptr [rax+rax+00h]
0x18001734f  test    eax, eax
0x180017351  jz      loc_180017562
0x180017357  lea     rdx, [rbp+57h+var_78]; lpFileTime
0x18001735b  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x18001735f  call    cs:__imp_SystemTimeToFileTime
0x180017366  nop     dword ptr [rax+rax+00h]
0x18001736b  test    eax, eax
0x18001736d  jz      loc_180017562
0x180017373  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x180017377  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x18001737b  call    cs:__imp_CompareFileTime
0x180017382  nop     dword ptr [rax+rax+00h]
0x180017387  test    eax, eax
0x180017389  js      loc_180017471
0x18001738f  lea     r8, [rbp+57h+FileTime2]
0x180017393  xor     edx, edx
0x180017395  mov     rcx, rdi
0x180017398  call    UbpmStatsOperation
0x18001739d  mov     ebx, eax
0x18001739f  test    eax, eax
0x1800173a1  jnz     loc_180017277
0x1800173a7  cmp     [rbp+57h+var_30], r15d
0x1800173ab  jz      loc_180017277
0x1800173b1  cmp     [rbp+57h+var_40.dwHighDateTime+8], r15d
0x1800173b5  jz      loc_180017277
0x1800173bb  mov     eax, [rbp+57h+var_40.dwLowDateTime+8]
0x1800173be  cmp     eax, 8007050Bh
0x1800173c3  jz      loc_180017277
0x1800173c9  cmp     eax, 8007042Bh
0x1800173ce  jz      loc_180017277
0x1800173d4  lea     rdx, [rbp+57h+FileTime2.dwHighDateTime]; lpFileTime2
0x1800173d8  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x1800173dc  call    cs:__imp_CompareFileTime
0x1800173e3  nop     dword ptr [rax+rax+00h]
0x1800173e8  test    eax, eax
0x1800173ea  js      short loc_180017468
0x1800173ec  lea     rdx, [rbp+57h+var_40.dwHighDateTime+8]; lpFileTime2
0x1800173f0  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x1800173f4  call    cs:__imp_CompareFileTime
0x1800173fb  nop     dword ptr [rax+rax+00h]
0x180017400  test    eax, eax
0x180017402  js      short loc_180017468
0x180017404  mov     r8, [rdi+18h]
0x180017408  lea     rax, [rbp+57h+var_78]
0x18001740c  lea     r9, [rbp+57h+FileTime1]
0x180017410  mov     [rsp+0C0h+var_A0], rax; __int64
0x180017415  lea     rdx, [rbp+57h+FileTime2.dwHighDateTime]; lpFileTime
0x180017419  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x18001741d  mov     r8, [r8+30h]; struct _UBPM_TIMESPAN *
0x180017421  call    UbpmpMaintenanceComputeCompletionPeriod
0x180017426  mov     ebx, eax
0x180017428  test    eax, eax
0x18001742a  jnz     loc_180017277
0x180017430  lea     rdx, [rbp+57h+var_40.dwHighDateTime+8]; lpFileTime2
0x180017434  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180017438  call    cs:__imp_CompareFileTime
0x18001743f  nop     dword ptr [rax+rax+00h]
0x180017444  test    eax, eax
0x180017446  jns     loc_180017277
0x18001744c  lea     rdx, [rbp+57h+var_78]; lpFileTime2
0x180017450  lea     rcx, [rbp+57h+var_40.dwHighDateTime+8]; lpFileTime1
0x180017454  call    cs:__imp_CompareFileTime
0x18001745b  nop     dword ptr [rax+rax+00h]
0x180017460  test    eax, eax
0x180017462  jg      loc_180017277
0x180017468  mov     byte ptr [r14], 1
0x18001746c  jmp     loc_180017277
0x180017471  lea     rdx, [rbp+57h+var_78]; lpFileTime2
0x180017475  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime1
0x180017479  call    cs:__imp_CompareFileTime
0x180017480  nop     dword ptr [rax+rax+00h]
0x180017485  test    eax, eax
0x180017487  jg      loc_18001738F
0x18001748d  jmp     short loc_180017468
0x18001748f  movzx   eax, word ptr [rbx+2]
0x180017493  movzx   esi, [rbp+57h+SystemTime.wMonth]
0x180017497  lea     ecx, [rsi-1]
0x18001749a  add     ecx, eax
0x18001749c  mov     eax, 2AAAAAABh
0x1800174a1  imul    ecx
0x1800174a3  sar     edx, 1
0x1800174a5  mov     ecx, edx
0x1800174a7  shr     ecx, 1Fh
0x1800174aa  add     edx, ecx
0x1800174ac  add     dx, r9w
0x1800174b0  add     dx, r10w
0x1800174b4  cmp     dx, r10w
0x1800174b8  jb      loc_180017272
0x1800174be  mov     [rbp+57h+var_60.wYear], dx
0x1800174c2  dec     esi
0x1800174c4  movzx   r8d, word ptr [rbx+2]
0x1800174c9  mov     eax, 2AAAAAABh
0x1800174ce  add     r8d, esi
0x1800174d1  mov     [rbp+57h+var_60.wDay], r11w
0x1800174d6  imul    r8d
0x1800174d9  mov     esi, 0FFFFh
0x1800174de  sar     edx, 1
0x1800174e0  mov     eax, edx
0x1800174e2  shr     eax, 1Fh
0x1800174e5  add     edx, eax
0x1800174e7  lea     eax, [rdx+rdx*2]
0x1800174ea  shl     eax, 2
0x1800174ed  sub     r8d, eax
0x1800174f0  movzx   eax, [rbp+57h+SystemTime.wHour]
0x1800174f4  mov     [rbp+57h+var_60.wHour], ax
0x1800174f8  inc     r8w
0x1800174fc  movzx   eax, [rbp+57h+SystemTime.wMinute]
0x180017500  mov     [rbp+57h+var_60.wMinute], ax
0x180017504  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x180017508  mov     [rbp+57h+var_60.wSecond], ax
0x18001750c  movzx   eax, [rbp+57h+SystemTime.wMilliseconds]
0x180017510  mov     [rbp+57h+var_60.wMilliseconds], ax
0x180017514  mov     [rbp+57h+var_60.wMonth], r8w
0x180017519  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001751d  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x180017521  call    cs:__imp_SystemTimeToFileTime
0x180017528  nop     dword ptr [rax+rax+00h]
0x18001752d  test    eax, eax
0x18001752f  jnz     loc_18001724B
0x180017535  movzx   eax, [rbp+57h+var_60.wDay]
0x180017539  cmp     ax, 1Ch
0x18001753d  jbe     short loc_180017575
0x18001753f  add     ax, si
0x180017542  mov     [rbp+57h+var_60.wDay], ax
0x180017546  jmp     short loc_180017519
0x180017548  cmp     [rbp+57h+SystemTime.wMonth], r15w
0x18001754d  jnz     loc_18001720A
0x180017553  test    r11w, r11w
0x180017557  jnz     loc_18001720A
0x18001755d  jmp     loc_18001738F
0x180017562  call    cs:__imp_GetLastError
0x180017569  nop     dword ptr [rax+rax+00h]
0x18001756e  mov     ebx, eax
0x180017570  jmp     loc_180017277
0x180017575  mov     ebx, 57h ; 'W'
0x18001757a  jmp     loc_180017277
```
