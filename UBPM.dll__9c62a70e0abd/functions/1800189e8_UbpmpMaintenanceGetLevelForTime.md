# UbpmpMaintenanceGetLevelForTime

- ea: `0x1800189e8`
- end: `0x180018da6`
- name: `UbpmpMaintenanceGetLevelForTime`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016b50`

## callees

- `0x1800189e8`
- `0x180036d44`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018a99`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018ab3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018ad0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018b4f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c36`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c51`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c68`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c96`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018cad`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018cec`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d0b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d22`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d39`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d50`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d6b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018a99`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018ab3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018ad0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018b4f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c36`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c51`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c68`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c96`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018cad`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018cec`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d0b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d22`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d39`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d50`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018d6b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018a7f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018b36`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018bcb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018c0c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018a7f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018b36`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018bcb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018c0c`

## pseudocode

```c
FILETIME *__fastcall UbpmpMaintenanceGetLevelForTime(
        __int64 a1,
        __int64 a2,
        const FILETIME *a3,
        const FILETIME *a4,
        FILETIME *a5,
        FILETIME *lpFileTime2,
        __int64 a7,
        char a8,
        char *a9,
        FILETIME *a10)
{
  FILETIME v14; // rbx
  FILETIME v15; // rbx
  FILETIME v16; // rdi
  char v17; // di
  FILETIME *result; // rax
  FILETIME v19; // rdi
  FILETIME FileTime; // [rsp+20h] [rbp-50h] BYREF
  FILETIME v21; // [rsp+28h] [rbp-48h] BYREF
  FILETIME FileTime1; // [rsp+30h] [rbp-40h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-38h] BYREF
  char *v24; // [rsp+40h] [rbp-30h]
  FILETIME *v25; // [rsp+48h] [rbp-28h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  v24 = a9;
  v25 = a10;
  v21 = *a4;
  FileTime2 = v21;
  v14 = (FILETIME)(*(_QWORD *)&v21 + 864000000000LL);
  SystemTime = 0;
  if ( *(_QWORD *)&v21 + 864000000000LL >= *(unsigned __int64 *)&v21 )
  {
    *(_QWORD *)&v21 += 864000000000LL;
    FileTime = v14;
    if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
      FileTime2 = v14;
  }
  if ( CompareFileTime(a3, lpFileTime2) < 0 )
    *lpFileTime2 = *a3;
  if ( CompareFileTime(lpFileTime2, a4) < 0 )
    *lpFileTime2 = *a4;
  if ( CompareFileTime(lpFileTime2, a5) < 0 )
    *lpFileTime2 = *a5;
  v15 = *a3;
  FileTime1 = *lpFileTime2;
  v21 = FileTime1;
  FileTime = v15;
  SystemTime = 0;
  if ( *(_QWORD *)&FileTime + 864000000000LL >= *(unsigned __int64 *)&FileTime )
  {
    FileTime = (FILETIME)(*(_QWORD *)&v15 + 864000000000LL);
    if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
      *(_QWORD *)&v15 += 864000000000LL;
  }
  if ( CompareFileTime(a3, &FileTime2) < 0 )
  {
    v17 = 0;
    goto LABEL_16;
  }
  SystemTime = 0;
  v16 = (FILETIME)(*(_QWORD *)&FileTime1 + a1);
  if ( *(_QWORD *)&FileTime1 + a1 < *(unsigned __int64 *)&FileTime1
    || (FileTime = (FILETIME)(*(_QWORD *)&FileTime1 + a1), !FileTimeToSystemTime(&FileTime, &SystemTime))
    || (FileTime1 = v16,
        SystemTime = 0,
        v19 = (FILETIME)(*(_QWORD *)&v21 + a2),
        *(_QWORD *)&v21 + a2 < *(unsigned __int64 *)&v21)
    || (FileTime = (FILETIME)(*(_QWORD *)&v21 + a2), !FileTimeToSystemTime(&FileTime, &SystemTime)) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v17 = 2;
LABEL_16:
    v15 = FileTime2;
    goto LABEL_17;
  }
  v21 = v19;
  if ( !a2 )
  {
    if ( !CompareFileTime(&FileTime1, a3) || CompareFileTime(&FileTime1, a3) < 0 )
      goto LABEL_27;
    goto LABEL_31;
  }
  if ( a8 )
  {
    if ( !CompareFileTime(&v21, a3) || CompareFileTime(&v21, a3) < 0 )
    {
      v17 = 4;
      goto LABEL_17;
    }
    if ( (!CompareFileTime(&FileTime1, a3) || CompareFileTime(&FileTime1, a3) < 0) && CompareFileTime(a3, &v21) < 0 )
    {
      v15 = v21;
      v17 = 3;
      goto LABEL_17;
    }
  }
  if ( CompareFileTime(&FileTime1, a3) && CompareFileTime(&FileTime1, a3) >= 0 )
  {
    if ( CompareFileTime(a3, &FileTime1) >= 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_27:
      v17 = 2;
      goto LABEL_17;
    }
LABEL_31:
    v15 = FileTime1;
    v17 = 0;
    goto LABEL_17;
  }
  *(FILETIME *)&SystemTime.wYear = v21;
  v17 = 2;
  FileTime = v15;
  if ( CompareFileTime((const FILETIME *)&SystemTime, &FileTime) > 0 )
    v15 = v21;
LABEL_17:
  *v24 = v17;
  result = v25;
  *v25 = v15;
  return result;
}

```

## disassembly

```asm
0x1800189e8  mov     [rsp-38h+arg_0], rbx
0x1800189ed  push    rbp
0x1800189ee  push    rsi
0x1800189ef  push    rdi
0x1800189f0  push    r12
0x1800189f2  push    r13
0x1800189f4  push    r14
0x1800189f6  push    r15
0x1800189f8  mov     rbp, rsp
0x1800189fb  sub     rsp, 70h
0x1800189ff  mov     rax, cs:__security_cookie
0x180018a06  xor     rax, rsp
0x180018a09  mov     [rbp+var_10], rax
0x180018a0d  mov     rax, [rbp+arg_40]
0x180018a14  mov     rbx, 0C92A69C000h
0x180018a1e  mov     r13, [rbp+arg_20]
0x180018a22  xorps   xmm0, xmm0
0x180018a25  mov     rdi, [rbp+lpFileTime2]
0x180018a29  mov     r12, r9
0x180018a2c  mov     [rbp+var_30], rax
0x180018a30  mov     r15, r8
0x180018a33  mov     rax, [rbp+arg_48]
0x180018a3a  mov     rsi, rdx
0x180018a3d  mov     [rbp+var_28], rax
0x180018a41  mov     r14, rcx
0x180018a44  mov     rax, [r9]
0x180018a47  mov     [rbp+var_48.dwLowDateTime], eax
0x180018a4a  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180018a4e  shr     rax, 20h
0x180018a52  mov     [rbp+var_48.dwHighDateTime], eax
0x180018a55  add     rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x180018a59  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018a5d  cmp     rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x180018a61  jb      short loc_180018A93
0x180018a63  mov     qword ptr [rbp+var_48.dwLowDateTime], rbx
0x180018a67  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180018a6b  mov     eax, [rbp+var_48.dwLowDateTime]
0x180018a6e  lea     rcx, [rbp+FileTime]; lpFileTime
0x180018a72  mov     [rbp+FileTime.dwLowDateTime], eax
0x180018a75  mov     rax, rbx
0x180018a78  shr     rax, 20h
0x180018a7c  mov     [rbp+FileTime.dwHighDateTime], eax
0x180018a7f  call    cs:__imp_FileTimeToSystemTime
0x180018a86  nop     dword ptr [rax+rax+00h]
0x180018a8b  test    eax, eax
0x180018a8d  jz      short loc_180018A93
0x180018a8f  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rbx
0x180018a93  mov     rdx, rdi; lpFileTime2
0x180018a96  mov     rcx, r15; lpFileTime1
0x180018a99  call    cs:__imp_CompareFileTime
0x180018aa0  nop     dword ptr [rax+rax+00h]
0x180018aa5  test    eax, eax
0x180018aa7  js      loc_180018D93
0x180018aad  mov     rdx, r12; lpFileTime2
0x180018ab0  mov     rcx, rdi; lpFileTime1
0x180018ab3  call    cs:__imp_CompareFileTime
0x180018aba  nop     dword ptr [rax+rax+00h]
0x180018abf  test    eax, eax
0x180018ac1  jns     short loc_180018ACA
0x180018ac3  mov     rax, [r12]
0x180018ac7  mov     [rdi], rax
0x180018aca  mov     rdx, r13; lpFileTime2
0x180018acd  mov     rcx, rdi; lpFileTime1
0x180018ad0  call    cs:__imp_CompareFileTime
0x180018ad7  nop     dword ptr [rax+rax+00h]
0x180018adc  test    eax, eax
0x180018ade  js      loc_180018CC9
0x180018ae4  mov     rax, [rdi]
0x180018ae7  xorps   xmm0, xmm0
0x180018aea  mov     rbx, [r15]
0x180018aed  mov     rdi, 0C92A69C000h
0x180018af7  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180018afb  mov     qword ptr [rbp+var_48.dwLowDateTime], rax
0x180018aff  mov     rax, rbx
0x180018b02  shr     rax, 20h
0x180018b06  mov     [rbp+FileTime.dwHighDateTime], eax
0x180018b09  mov     [rbp+FileTime.dwLowDateTime], ebx
0x180018b0c  add     rdi, qword ptr [rbp+FileTime.dwLowDateTime]
0x180018b10  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018b14  cmp     rdi, qword ptr [rbp+FileTime.dwLowDateTime]
0x180018b18  jb      short loc_180018B48
0x180018b1a  mov     qword ptr [rbp+FileTime.dwLowDateTime], rdi
0x180018b1e  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180018b22  mov     eax, [rbp+FileTime.dwLowDateTime]
0x180018b25  lea     rcx, [rbp+FileTime]; lpFileTime
0x180018b29  mov     [rbp+FileTime.dwLowDateTime], eax
0x180018b2c  mov     rax, rdi
0x180018b2f  shr     rax, 20h
0x180018b33  mov     [rbp+FileTime.dwHighDateTime], eax
0x180018b36  call    cs:__imp_FileTimeToSystemTime
0x180018b3d  nop     dword ptr [rax+rax+00h]
0x180018b42  test    eax, eax
0x180018b44  cmovnz  rbx, rdi
0x180018b48  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180018b4c  mov     rcx, r15; lpFileTime1
0x180018b4f  call    cs:__imp_CompareFileTime
0x180018b56  nop     dword ptr [rax+rax+00h]
0x180018b5b  test    eax, eax
0x180018b5d  js      loc_180018D9E
0x180018b63  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180018b67  xorps   xmm0, xmm0
0x180018b6a  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018b6e  lea     rdi, [rax+r14]
0x180018b72  cmp     rdi, rax
0x180018b75  jnb     short loc_180018BB6
0x180018b77  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018b7c  mov     dil, 2
0x180018b7f  mov     rbx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180018b83  mov     rax, [rbp+var_30]
0x180018b87  mov     [rax], dil
0x180018b8a  mov     rax, [rbp+var_28]
0x180018b8e  mov     [rax], rbx
0x180018b91  mov     rcx, [rbp+var_10]
0x180018b95  xor     rcx, rsp; StackCookie
0x180018b98  call    __security_check_cookie
0x180018b9d  mov     rbx, [rsp+70h+arg_0]
0x180018ba5  add     rsp, 70h
0x180018ba9  pop     r15
0x180018bab  pop     r14
0x180018bad  pop     r13
0x180018baf  pop     r12
0x180018bb1  pop     rdi
0x180018bb2  pop     rsi
0x180018bb3  pop     rbp
0x180018bb4  retn
0x180018bb6  mov     rax, rdi
0x180018bb9  mov     [rbp+FileTime.dwLowDateTime], edi
0x180018bbc  shr     rax, 20h
0x180018bc0  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180018bc4  lea     rcx, [rbp+FileTime]; lpFileTime
0x180018bc8  mov     [rbp+FileTime.dwHighDateTime], eax
0x180018bcb  call    cs:__imp_FileTimeToSystemTime
0x180018bd2  nop     dword ptr [rax+rax+00h]
0x180018bd7  test    eax, eax
0x180018bd9  jz      short loc_180018B77
0x180018bdb  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rdi
0x180018bdf  mov     rax, qword ptr [rbp+var_48.dwLowDateTime]
0x180018be3  xorps   xmm0, xmm0
0x180018be6  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018bea  lea     rdi, [rax+rsi]
0x180018bee  cmp     rdi, rax
0x180018bf1  jb      loc_180018C85
0x180018bf7  mov     rax, rdi
0x180018bfa  mov     [rbp+FileTime.dwLowDateTime], edi
0x180018bfd  shr     rax, 20h
0x180018c01  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180018c05  lea     rcx, [rbp+FileTime]; lpFileTime
0x180018c09  mov     [rbp+FileTime.dwHighDateTime], eax
0x180018c0c  call    cs:__imp_FileTimeToSystemTime
0x180018c13  nop     dword ptr [rax+rax+00h]
0x180018c18  test    eax, eax
0x180018c1a  jz      short loc_180018C85
0x180018c1c  mov     qword ptr [rbp+var_48.dwLowDateTime], rdi
0x180018c20  test    rsi, rsi
0x180018c23  jz      short loc_180018C8F
0x180018c25  cmp     [rbp+arg_38], 0
0x180018c29  jnz     loc_180018D04
0x180018c2f  mov     rdx, r15; lpFileTime2
0x180018c32  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180018c36  call    cs:__imp_CompareFileTime
0x180018c3d  nop     dword ptr [rax+rax+00h]
0x180018c42  test    eax, eax
0x180018c44  jz      loc_180018CD5
0x180018c4a  mov     rdx, r15; lpFileTime2
0x180018c4d  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180018c51  call    cs:__imp_CompareFileTime
0x180018c58  nop     dword ptr [rax+rax+00h]
0x180018c5d  test    eax, eax
0x180018c5f  js      short loc_180018CD5
0x180018c61  lea     rdx, [rbp+FileTime1]; lpFileTime2
0x180018c65  mov     rcx, r15; lpFileTime1
0x180018c68  call    cs:__imp_CompareFileTime
0x180018c6f  nop     dword ptr [rax+rax+00h]
0x180018c74  test    eax, eax
0x180018c76  js      short loc_180018CBD
0x180018c78  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018c7d  mov     dil, 2
0x180018c80  jmp     loc_180018B83
0x180018c85  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018c8a  jmp     loc_180018B7C
0x180018c8f  mov     rdx, r15; lpFileTime2
0x180018c92  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180018c96  call    cs:__imp_CompareFileTime
0x180018c9d  nop     dword ptr [rax+rax+00h]
0x180018ca2  test    eax, eax
0x180018ca4  jz      short loc_180018C7D
0x180018ca6  mov     rdx, r15; lpFileTime2
0x180018ca9  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180018cad  call    cs:__imp_CompareFileTime
0x180018cb4  nop     dword ptr [rax+rax+00h]
0x180018cb9  test    eax, eax
0x180018cbb  js      short loc_180018C7D
0x180018cbd  mov     rbx, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180018cc1  xor     dil, dil
0x180018cc4  jmp     loc_180018B83
0x180018cc9  mov     rax, [r13+0]
0x180018ccd  mov     [rdi], rax
0x180018cd0  jmp     loc_180018AE4
0x180018cd5  mov     rax, qword ptr [rbp+var_48.dwLowDateTime]
0x180018cd9  lea     rdx, [rbp+FileTime]; lpFileTime2
0x180018cdd  lea     rcx, [rbp+SystemTime]; lpFileTime1
0x180018ce1  mov     qword ptr [rbp+SystemTime.wYear], rax
0x180018ce5  mov     dil, 2
0x180018ce8  mov     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x180018cec  call    cs:__imp_CompareFileTime
0x180018cf3  nop     dword ptr [rax+rax+00h]
0x180018cf8  test    eax, eax
0x180018cfa  cmovg   rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x180018cff  jmp     loc_180018B83
0x180018d04  mov     rdx, r15; lpFileTime2
0x180018d07  lea     rcx, [rbp+var_48]; lpFileTime1
0x180018d0b  call    cs:__imp_CompareFileTime
0x180018d12  nop     dword ptr [rax+rax+00h]
0x180018d17  test    eax, eax
0x180018d19  jz      short loc_180018D8B
0x180018d1b  mov     rdx, r15; lpFileTime2
0x180018d1e  lea     rcx, [rbp+var_48]; lpFileTime1
0x180018d22  call    cs:__imp_CompareFileTime
0x180018d29  nop     dword ptr [rax+rax+00h]
0x180018d2e  test    eax, eax
0x180018d30  js      short loc_180018D8B
0x180018d32  mov     rdx, r15; lpFileTime2
0x180018d35  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180018d39  call    cs:__imp_CompareFileTime
0x180018d40  nop     dword ptr [rax+rax+00h]
0x180018d45  test    eax, eax
0x180018d47  jz      short loc_180018D64
0x180018d49  mov     rdx, r15; lpFileTime2
0x180018d4c  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180018d50  call    cs:__imp_CompareFileTime
0x180018d57  nop     dword ptr [rax+rax+00h]
0x180018d5c  test    eax, eax
0x180018d5e  jns     loc_180018C2F
0x180018d64  lea     rdx, [rbp+var_48]; lpFileTime2
0x180018d68  mov     rcx, r15; lpFileTime1
0x180018d6b  call    cs:__imp_CompareFileTime
0x180018d72  nop     dword ptr [rax+rax+00h]
0x180018d77  test    eax, eax
0x180018d79  jns     loc_180018C2F
0x180018d7f  mov     rbx, qword ptr [rbp+var_48.dwLowDateTime]
0x180018d83  mov     dil, 3
0x180018d86  jmp     loc_180018B83
0x180018d8b  mov     dil, 4
0x180018d8e  jmp     loc_180018B83
0x180018d93  mov     rax, [r15]
0x180018d96  mov     [rdi], rax
0x180018d99  jmp     loc_180018AAD
0x180018d9e  xor     dil, dil
0x180018da1  jmp     loc_180018B7F
```
