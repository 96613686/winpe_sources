# UbpmpMaintenanceComputeCompletionPeriod

- ea: `0x180018560`
- end: `0x180018969`
- name: `UbpmpMaintenanceComputeCompletionPeriod`
- size: `1033`
- prototype: `__int64 __usercall@<rax>(FILETIME *lpFileTime2@<rcx>, FILETIME *lpFileTime@<rdx>, struct _UBPM_TIMESPAN *@<r8>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017110`
- `0x18002ee00`

## callees

- `0x180018560`
- `0x180018db0`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001894e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001894e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800187e2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800187e2`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800186a2`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018793`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018935`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800186a2`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018793`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018935`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800186df`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800187ab`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800187c7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018846`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001885e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018907`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800186df`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800187ab`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800187c7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018846`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001885e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018907`

## pseudocode

```c
unsigned int __fastcall UbpmpMaintenanceComputeCompletionPeriod(
        FILETIME *lpFileTime2,
        FILETIME *lpFileTime,
        struct _UBPM_TIMESPAN *a3,
        FILETIME *a4,
        FILETIME *a5)
{
  unsigned __int16 *v7; // rdi
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r8
  unsigned int result; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // rdx
  __int16 v16; // r8
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r8
  int v21; // r9d
  FILETIME v22; // [rsp+20h] [rbp-58h] BYREF
  FILETIME FileTime; // [rsp+28h] [rbp-50h] BYREF
  FILETIME FileTime1; // [rsp+30h] [rbp-48h] BYREF
  FILETIME v25; // [rsp+38h] [rbp-40h]
  SYSTEMTIME v26; // [rsp+40h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-28h] BYREF

  FileTime = 0;
  FileTime1 = 0;
  v7 = (unsigned __int16 *)((char *)a3 + 2);
  SystemTime = 0;
  v26 = 0;
  if ( *(_DWORD *)a3 )
  {
    if ( !FileTimeToSystemTime(lpFileTime, &SystemTime) )
      return GetLastError();
  }
  else
  {
    v22 = *lpFileTime;
    v25 = *lpFileTime2;
    v9 = 6048000000000LL * *((unsigned __int16 *)a3 + 2);
    v10 = v9 + 864000000000LL * *((unsigned __int16 *)a3 + 3);
    if ( v10 < v9 )
      return 534;
    v12 = v10 + 36000000000LL * *((unsigned __int16 *)a3 + 4);
    if ( v12 < v10 )
      return 534;
    v13 = v12 + 600000000LL * *((unsigned __int16 *)a3 + 5);
    if ( v13 < v12 )
      return 534;
    v14 = v13 + 10000000LL * *((unsigned __int16 *)a3 + 6);
    if ( v14 < v13 )
      return 534;
    v15 = (*(_QWORD *)&v25 - *(_QWORD *)&v22) % v14;
    if ( *(_QWORD *)&v25 - v15 < *(_QWORD *)&v22 )
      return 534;
    v22 = (FILETIME)(*(_QWORD *)&v25 - v15);
    FileTime = (FILETIME)(*(_QWORD *)&v25 - v15);
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      return GetLastError();
  }
  v16 = *(_WORD *)a3;
  v22 = 0;
  if ( v16 || (v7 = (unsigned __int16 *)((char *)a3 + 2), *((_WORD *)a3 + 1)) )
  {
    v21 = *v7 + SystemTime.wMonth - 1;
    if ( (unsigned __int16)(SystemTime.wYear + v16 + v21 / 12) < SystemTime.wYear )
      return 534;
    v26.wYear = SystemTime.wYear + v16 + v21 / 12;
    v26.wDay = SystemTime.wDay;
    v26.wHour = SystemTime.wHour;
    v26.wMinute = SystemTime.wMinute;
    v26.wSecond = SystemTime.wSecond;
    v26.wMilliseconds = SystemTime.wMilliseconds;
    v26.wMonth = v21 % 12 + 1;
    while ( !SystemTimeToFileTime(&v26, &v22) )
    {
      if ( v26.wDay <= 0x1Cu )
        return 87;
      --v26.wDay;
    }
LABEL_13:
    v17 = *(_QWORD *)&v22 + 6048000000000LL * *((unsigned __int16 *)a3 + 2);
    if ( v17 >= *(_QWORD *)&v22 )
    {
      v18 = v17 + 864000000000LL * *((unsigned __int16 *)a3 + 3);
      if ( v18 >= v17 )
      {
        v19 = v18 + 36000000000LL * *((unsigned __int16 *)a3 + 4);
        if ( v19 >= v18 )
        {
          v20 = v19 + 600000000LL * *((unsigned __int16 *)a3 + 5);
          if ( v20 >= v19 && v20 + 10000000LL * *((unsigned __int16 *)a3 + 6) >= v20 )
          {
            v22 = (FILETIME)(v20 + 10000000LL * *((unsigned __int16 *)a3 + 6));
            if ( FileTimeToSystemTime(&v22, &v26) )
              goto LABEL_19;
            goto LABEL_23;
          }
        }
      }
    }
    return 534;
  }
  if ( SystemTimeToFileTime(&SystemTime, &v22) )
    goto LABEL_13;
LABEL_23:
  result = GetLastError();
  if ( result )
    return result;
LABEL_19:
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) || !SystemTimeToFileTime(&v26, &FileTime1) )
    return GetLastError();
  while ( CompareFileTime(&FileTime1, lpFileTime2) < 0 )
  {
    SystemTime = v26;
    result = UbpmpUtilsAddPeriodToSystemTime(&SystemTime, a3, &v26);
    if ( result )
      return result;
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) || !SystemTimeToFileTime(&v26, &FileTime1) )
      return GetLastError();
  }
  *a4 = FileTime;
  *a5 = FileTime1;
  return 0;
}

```

## disassembly

```asm
0x180018560  push    rbp
0x180018562  push    rbx
0x180018563  push    rsi
0x180018564  push    rdi
0x180018565  push    r12
0x180018567  push    r13
0x180018569  push    r14
0x18001856b  push    r15
0x18001856d  mov     rbp, rsp
0x180018570  sub     rsp, 78h
0x180018574  mov     rax, cs:__security_cookie
0x18001857b  xor     rax, rsp
0x18001857e  mov     [rbp+var_18], rax
0x180018582  mov     r15, [rbp+arg_20]
0x180018586  mov     rbx, r8
0x180018589  xor     r12d, r12d
0x18001858c  xorps   xmm0, xmm0
0x18001858f  xorps   xmm1, xmm1
0x180018592  mov     qword ptr [rbp+FileTime.dwLowDateTime], r12
0x180018596  mov     r14, r9
0x180018599  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x18001859d  lea     rdi, [rbx+2]
0x1800185a1  mov     r8, rdx
0x1800185a4  mov     rsi, rcx
0x1800185a7  mov     r13, 861C46800h
0x1800185b1  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800185b5  movups  xmmword ptr [rbp+var_38.wYear], xmm1
0x1800185b9  cmp     [rbx], r12w
0x1800185bd  jnz     loc_18001892E
0x1800185c3  cmp     [rdi], r12w
0x1800185c7  jnz     loc_18001892E
0x1800185cd  mov     eax, [rdx+4]
0x1800185d0  mov     [rbp+var_58.dwHighDateTime], eax
0x1800185d3  mov     eax, [rdx]
0x1800185d5  mov     [rbp+var_58.dwLowDateTime], eax
0x1800185d8  mov     eax, [rcx+4]
0x1800185db  mov     dword ptr [rbp+var_40+4], eax
0x1800185de  mov     eax, [rcx]
0x1800185e0  mov     dword ptr [rbp+var_40], eax
0x1800185e3  movzx   eax, word ptr [rbx+4]
0x1800185e7  imul    eax, 93A80h
0x1800185ed  cdqe
0x1800185ef  imul    rdx, rax, 989680h
0x1800185f6  movzx   eax, word ptr [rbx+6]
0x1800185fa  imul    eax, 15180h
0x180018600  cdqe
0x180018602  imul    r8, rax, 989680h
0x180018609  add     r8, rdx
0x18001860c  cmp     r8, rdx
0x18001860f  jnb     short loc_180018634
0x180018611  mov     eax, 216h
0x180018616  mov     rcx, [rbp+var_18]
0x18001861a  xor     rcx, rsp; StackCookie
0x18001861d  call    __security_check_cookie
0x180018622  add     rsp, 78h
0x180018626  pop     r15
0x180018628  pop     r14
0x18001862a  pop     r13
0x18001862c  pop     r12
0x18001862e  pop     rdi
0x18001862f  pop     rsi
0x180018630  pop     rbx
0x180018631  pop     rbp
0x180018632  retn
0x180018634  movzx   edx, word ptr [rbx+8]
0x180018638  imul    rdx, r13
0x18001863c  add     rdx, r8
0x18001863f  cmp     rdx, r8
0x180018642  jb      short loc_180018611
0x180018644  movzx   eax, word ptr [rbx+0Ah]
0x180018648  imul    r8, rax, 23C34600h
0x18001864f  add     r8, rdx
0x180018652  cmp     r8, rdx
0x180018655  jb      short loc_180018611
0x180018657  movzx   eax, word ptr [rbx+0Ch]
0x18001865b  imul    r9, rax, 989680h
0x180018662  add     r9, r8
0x180018665  cmp     r9, r8
0x180018668  jb      short loc_180018611
0x18001866a  mov     rcx, qword ptr [rbp+var_58.dwLowDateTime]
0x18001866e  xor     edx, edx
0x180018670  mov     r8, [rbp+var_40]
0x180018674  sub     r8, rcx
0x180018677  mov     rax, r8
0x18001867a  div     r9
0x18001867d  sub     r8, rdx
0x180018680  lea     rax, [r8+rcx]
0x180018684  cmp     rax, rcx
0x180018687  jb      short loc_180018611
0x180018689  mov     qword ptr [rbp+var_58.dwLowDateTime], rax
0x18001868d  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180018691  shr     rax, 20h
0x180018695  lea     rcx, [rbp+FileTime]; lpFileTime
0x180018699  mov     [rbp+FileTime.dwHighDateTime], eax
0x18001869c  mov     eax, [rbp+var_58.dwLowDateTime]
0x18001869f  mov     [rbp+FileTime.dwLowDateTime], eax
0x1800186a2  call    cs:__imp_FileTimeToSystemTime
0x1800186a9  nop     dword ptr [rax+rax+00h]
0x1800186ae  test    eax, eax
0x1800186b0  jz      loc_18001894E
0x1800186b6  movzx   r8d, word ptr [rbx]
0x1800186ba  mov     qword ptr [rbp+var_58.dwLowDateTime], r12
0x1800186be  test    r8w, r8w
0x1800186c2  jnz     loc_180018883
0x1800186c8  cmp     [rbx+2], r12w
0x1800186cd  lea     rdi, [rbx+2]
0x1800186d1  jnz     loc_180018883
0x1800186d7  lea     rdx, [rbp+var_58]; lpFileTime
0x1800186db  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800186df  call    cs:__imp_SystemTimeToFileTime
0x1800186e6  nop     dword ptr [rax+rax+00h]
0x1800186eb  test    eax, eax
0x1800186ed  jz      loc_180018808
0x1800186f3  mov     eax, [rbp+var_58.dwLowDateTime]
0x1800186f6  mov     rdx, 58028E44000h
0x180018700  mov     ecx, [rbp+var_58.dwHighDateTime]
0x180018703  shl     rcx, 20h
0x180018707  or      rcx, rax
0x18001870a  movzx   eax, word ptr [rbx+4]
0x18001870e  imul    rdx, rax
0x180018712  add     rdx, rcx
0x180018715  cmp     rdx, rcx
0x180018718  jb      loc_180018611
0x18001871e  movzx   eax, word ptr [rbx+6]
0x180018722  mov     rcx, 0C92A69C000h
0x18001872c  imul    rcx, rax
0x180018730  add     rcx, rdx
0x180018733  cmp     rcx, rdx
0x180018736  jb      loc_180018611
0x18001873c  movzx   edx, word ptr [rbx+8]
0x180018740  imul    rdx, r13
0x180018744  add     rdx, rcx
0x180018747  cmp     rdx, rcx
0x18001874a  jb      loc_180018611
0x180018750  movzx   eax, word ptr [rbx+0Ah]
0x180018754  imul    r8, rax, 23C34600h
0x18001875b  add     r8, rdx
0x18001875e  cmp     r8, rdx
0x180018761  jb      loc_180018611
0x180018767  movzx   eax, word ptr [rbx+0Ch]
0x18001876b  imul    rax, 989680h
0x180018772  add     rax, r8
0x180018775  cmp     rax, r8
0x180018778  jb      loc_180018611
0x18001877e  mov     rcx, rax
0x180018781  mov     [rbp+var_58.dwLowDateTime], eax
0x180018784  shr     rcx, 20h
0x180018788  lea     rdx, [rbp+var_38]; lpSystemTime
0x18001878c  mov     [rbp+var_58.dwHighDateTime], ecx
0x18001878f  lea     rcx, [rbp+var_58]; lpFileTime
0x180018793  call    cs:__imp_FileTimeToSystemTime
0x18001879a  nop     dword ptr [rax+rax+00h]
0x18001879f  test    eax, eax
0x1800187a1  jz      short loc_180018808
0x1800187a3  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800187a7  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800187ab  call    cs:__imp_SystemTimeToFileTime
0x1800187b2  nop     dword ptr [rax+rax+00h]
0x1800187b7  test    eax, eax
0x1800187b9  jz      loc_180018872
0x1800187bf  lea     rdx, [rbp+FileTime1]; lpFileTime
0x1800187c3  lea     rcx, [rbp+var_38]; lpSystemTime
0x1800187c7  call    cs:__imp_SystemTimeToFileTime
0x1800187ce  nop     dword ptr [rax+rax+00h]
0x1800187d3  test    eax, eax
0x1800187d5  jz      loc_180018872
0x1800187db  mov     rdx, rsi; lpFileTime2
0x1800187de  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800187e2  call    cs:__imp_CompareFileTime
0x1800187e9  nop     dword ptr [rax+rax+00h]
0x1800187ee  test    eax, eax
0x1800187f0  js      short loc_18001881D
0x1800187f2  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x1800187f6  mov     [r14], rax
0x1800187f9  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x1800187fd  mov     [r15], rax
0x180018800  mov     eax, r12d
0x180018803  jmp     loc_180018616
0x180018808  call    cs:__imp_GetLastError
0x18001880f  nop     dword ptr [rax+rax+00h]
0x180018814  test    eax, eax
0x180018816  jz      short loc_1800187A3
0x180018818  jmp     loc_180018616
0x18001881d  movaps  xmm0, xmmword ptr [rbp+var_38.wYear]
0x180018821  lea     r8, [rbp+var_38]; struct _SYSTEMTIME *
0x180018825  mov     rdx, rbx; struct _UBPM_TIMESPAN *
0x180018828  movdqa  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001882d  lea     rcx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x180018831  call    ?UbpmpUtilsAddPeriodToSystemTime@@YAKPEAU_SYSTEMTIME@@PEAU_UBPM_TIMESPAN@@0@Z; UbpmpUtilsAddPeriodToSystemTime(_SYSTEMTIME *,_UBPM_TIMESPAN *,_SYSTEMTIME *)
0x180018836  test    eax, eax
0x180018838  jnz     loc_180018616
0x18001883e  lea     rdx, [rbp+FileTime]; lpFileTime
0x180018842  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180018846  call    cs:__imp_SystemTimeToFileTime
0x18001884d  nop     dword ptr [rax+rax+00h]
0x180018852  test    eax, eax
0x180018854  jz      short loc_180018872
0x180018856  lea     rdx, [rbp+FileTime1]; lpFileTime
0x18001885a  lea     rcx, [rbp+var_38]; lpSystemTime
0x18001885e  call    cs:__imp_SystemTimeToFileTime
0x180018865  nop     dword ptr [rax+rax+00h]
0x18001886a  test    eax, eax
0x18001886c  jnz     loc_1800187DB
0x180018872  call    cs:__imp_GetLastError
0x180018879  nop     dword ptr [rax+rax+00h]
0x18001887e  jmp     loc_180018616
0x180018883  movzx   r9d, [rbp+SystemTime.wMonth]
0x180018888  mov     eax, 2AAAAAABh
0x18001888d  movzx   ecx, word ptr [rdi]
0x180018890  dec     r9d
0x180018893  add     r9d, ecx
0x180018896  imul    r9d
0x180018899  sar     edx, 1
0x18001889b  mov     eax, edx
0x18001889d  shr     eax, 1Fh
0x1800188a0  add     edx, eax
0x1800188a2  lea     eax, [r8+rdx]
0x1800188a6  add     ax, [rbp+SystemTime.wYear]
0x1800188aa  cmp     ax, [rbp+SystemTime.wYear]
0x1800188ae  jb      loc_180018611
0x1800188b4  mov     [rbp+var_38.wYear], ax
0x1800188b8  mov     edi, 0FFFFh
0x1800188bd  movzx   eax, dx
0x1800188c0  add     dx, dx
0x1800188c3  add     ax, dx
0x1800188c6  shl     ax, 2
0x1800188ca  sub     r9w, ax
0x1800188ce  movzx   eax, [rbp+SystemTime.wDay]
0x1800188d2  mov     [rbp+var_38.wDay], ax
0x1800188d6  inc     r9w
0x1800188da  movzx   eax, [rbp+SystemTime.wHour]
0x1800188de  mov     [rbp+var_38.wHour], ax
0x1800188e2  movzx   eax, [rbp+SystemTime.wMinute]
0x1800188e6  mov     [rbp+var_38.wMinute], ax
0x1800188ea  movzx   eax, [rbp+SystemTime.wSecond]
0x1800188ee  mov     [rbp+var_38.wSecond], ax
0x1800188f2  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x1800188f6  mov     [rbp+var_38.wMilliseconds], ax
0x1800188fa  mov     [rbp+var_38.wMonth], r9w
0x1800188ff  lea     rdx, [rbp+var_58]; lpFileTime
0x180018903  lea     rcx, [rbp+var_38]; lpSystemTime
0x180018907  call    cs:__imp_SystemTimeToFileTime
0x18001890e  nop     dword ptr [rax+rax+00h]
0x180018913  test    eax, eax
0x180018915  jnz     loc_1800186F3
0x18001891b  movzx   eax, [rbp+var_38.wDay]
0x18001891f  cmp     ax, 1Ch
0x180018923  jbe     short loc_18001895F
0x180018925  add     ax, di
0x180018928  mov     [rbp+var_38.wDay], ax
0x18001892c  jmp     short loc_1800188FF
0x18001892e  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180018932  mov     rcx, r8; lpFileTime
0x180018935  call    cs:__imp_FileTimeToSystemTime
0x18001893c  nop     dword ptr [rax+rax+00h]
0x180018941  test    eax, eax
0x180018943  jnz     loc_1800186B6
0x180018949  jmp     loc_180018872
0x18001894e  call    cs:__imp_GetLastError
0x180018955  nop     dword ptr [rax+rax+00h]
0x18001895a  jmp     loc_180018616
0x18001895f  mov     eax, 57h ; 'W'
0x180018964  jmp     loc_180018616
```
