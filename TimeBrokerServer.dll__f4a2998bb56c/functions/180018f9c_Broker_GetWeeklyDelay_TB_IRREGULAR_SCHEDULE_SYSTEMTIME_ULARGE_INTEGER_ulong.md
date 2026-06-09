# Broker::GetWeeklyDelay(_TB_IRREGULAR_SCHEDULE *,_SYSTEMTIME *,_ULARGE_INTEGER,ulong *)

- ea: `0x180018f9c`
- end: `0x1800193e5`
- name: `?GetWeeklyDelay@Broker@@YAKPEAU_TB_IRREGULAR_SCHEDULE@@PEAU_SYSTEMTIME@@T_ULARGE_INTEGER@@PEAK@Z`
- size: `1097`
- prototype: `__int64 __fastcall(Broker *this, const SYSTEMTIME *, struct _SYSTEMTIME *, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800113dc`

## callees

- `0x180012dd0`
- `0x180018f9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192bd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019029`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019071`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019029`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019071`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019043`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800192b3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800193bd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019043`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800192b3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800193bd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180019013`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001905b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180019013`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18001905b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019129`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800191c4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019264`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001936b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019129`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800191c4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019264`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001936b`

## pseudocode

```c
__int64 __fastcall Broker::GetWeeklyDelay(
        Broker *this,
        const SYSTEMTIME *a2,
        struct _SYSTEMTIME *a3,
        union _ULARGE_INTEGER a4)
{
  Broker *v4; // r12
  unsigned __int64 v6; // rbx
  unsigned __int8 v7; // r15
  FILETIME v8; // rsi
  unsigned __int8 i; // r14
  bool v10; // zf
  unsigned __int8 v11; // cl
  int v12; // ecx
  unsigned int v13; // eax
  unsigned __int64 v14; // rdi
  unsigned __int8 k; // r15
  unsigned __int8 j; // r12
  unsigned int v17; // r8d
  DWORD dwLowDateTime; // r12d
  DWORD LastError; // edi
  unsigned __int64 v20; // r8
  int v21; // r15d
  unsigned __int8 m; // di
  DWORD dwHighDateTime; // r13d
  struct _FILETIME FileTime; // [rsp+20h] [rbp-69h] BYREF
  struct _FILETIME v25; // [rsp+28h] [rbp-61h]
  FILETIME FileTime1; // [rsp+30h] [rbp-59h] BYREF
  Broker *v27; // [rsp+38h] [rbp-51h]
  unsigned __int64 v28; // [rsp+40h] [rbp-49h]
  _DWORD *QuadPart; // [rsp+48h] [rbp-41h]
  struct _SYSTEMTIME LocalTime; // [rsp+50h] [rbp-39h] BYREF
  struct _SYSTEMTIME v31; // [rsp+60h] [rbp-29h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-19h] BYREF
  SYSTEMTIME v33; // [rsp+80h] [rbp-9h] BYREF

  QuadPart = (_DWORD *)a4.QuadPart;
  v27 = this;
  v10 = *(_DWORD *)this == 2;
  v4 = this;
  LocalTime = 0;
  FileTime = 0;
  v31 = 0;
  SystemTime = 0;
  v33 = 0;
  if ( !v10 )
    return 0;
  FileTime1.dwLowDateTime = (unsigned int)a3;
  *(_DWORD *)a4.QuadPart = 0;
  FileTime1.dwHighDateTime = HIDWORD(a3);
  if ( SystemTimeToTzSpecificLocalTime(0, a2, &LocalTime) )
  {
    if ( SystemTimeToFileTime(&LocalTime, &FileTime) )
    {
      v6 = (unsigned __int64)FileTime;
      if ( FileTimeToSystemTime(&FileTime1, &SystemTime) )
      {
        if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &v33) && SystemTimeToFileTime(&v33, &FileTime1) )
        {
          v7 = -1;
          v8 = FileTime1;
          if ( *((_BYTE *)v4 + 9) )
          {
            for ( i = 0; ; ++i )
            {
              v10 = i == 7;
              if ( i >= 7u )
                break;
              if ( ((unsigned __int8)(1 << i) & *((_BYTE *)v4 + 9)) != 0 )
              {
                v11 = v7;
                if ( v7 >= i )
                  v11 = i;
                v7 = v11;
                if ( i >= (unsigned int)LocalTime.wDayOfWeek )
                {
                  v12 = i - LocalTime.wDayOfWeek;
LABEL_19:
                  v13 = 86400 * v12;
                  goto LABEL_21;
                }
              }
            }
            i = -1;
            if ( v10 )
            {
              v12 = v7 - LocalTime.wDayOfWeek + 7;
              goto LABEL_19;
            }
            v13 = 0;
LABEL_21:
            v6 += 10000000LL * v13;
            v25 = (struct _FILETIME)v6;
            FileTime = (struct _FILETIME)v6;
          }
          else
          {
            i = -1;
          }
          if ( CompareFileTime(&FileTime1, &FileTime) > 0 )
          {
            v14 = v6
                + 6048000000000LL
                * *((unsigned __int8 *)v4 + 8)
                * ((*(_QWORD *)&v8 - v6)
                 / (6048000000000LL
                  * (unsigned __int64)*((unsigned __int8 *)v4 + 8)));
            if ( i == 0xFF )
            {
              if ( v7 != 0xFF )
              {
                for ( j = 1; j < 7u; ++j )
                {
                  v17 = (j + (unsigned int)LocalTime.wDayOfWeek) % 7;
                  if ( ((unsigned __int8)(1 << v17) & *((_BYTE *)v27 + 9)) != 0 && (unsigned __int8)v17 > v7 )
                  {
                    v6 = v14 + 864000000000LL * ((unsigned __int8)v17 - (unsigned __int64)v7);
                    v25 = (struct _FILETIME)v6;
                    FileTime = (struct _FILETIME)v6;
                    if ( CompareFileTime(&FileTime1, &FileTime) < 0 )
                      goto LABEL_50;
                  }
                }
                v4 = v27;
              }
            }
            else
            {
              for ( k = i + 1; k < 7u; ++k )
              {
                if ( ((unsigned __int8)(1 << k) & *((_BYTE *)v4 + 9)) != 0 )
                {
                  v6 = v14 + 864000000000LL * (k - (unsigned __int64)i);
                  v25 = (struct _FILETIME)v6;
                  FileTime = (struct _FILETIME)v6;
                  if ( CompareFileTime(&FileTime1, &FileTime) < 0 )
                    goto LABEL_50;
                }
              }
            }
            v25 = (struct _FILETIME)(v14 + 6048000000000LL * *((unsigned __int8 *)v4 + 8));
            v6 = (unsigned __int64)v25;
            dwLowDateTime = v25.dwLowDateTime;
            FileTime = v25;
            if ( !FileTimeToSystemTime(&FileTime, &v31) )
              goto LABEL_39;
            v20 = v6;
            v28 = v6;
            LOBYTE(v21) = 7;
            for ( m = 0; m < 7u && ((_BYTE)v21 || i == 0xFF); ++m )
            {
              v21 = (v31.wDayOfWeek - m + 7) % 7;
              if ( ((unsigned __int8)(1 << v21) & *((_BYTE *)v27 + 9)) != 0 )
              {
                dwHighDateTime = v25.dwHighDateTime;
                v6 = v20 - 864000000000LL * m;
                v25 = (struct _FILETIME)v6;
                FileTime = (struct _FILETIME)v6;
                if ( CompareFileTime(&FileTime1, &FileTime) > 0 )
                {
                  v25 = (struct _FILETIME)__PAIR64__(dwHighDateTime, dwLowDateTime);
                  v6 = __PAIR64__(dwHighDateTime, dwLowDateTime);
                  FileTime.dwLowDateTime = dwLowDateTime;
                  FileTime.dwHighDateTime = dwHighDateTime;
                  break;
                }
                dwLowDateTime = v25.dwLowDateTime;
                v20 = v28;
              }
            }
          }
LABEL_50:
          LastError = 0;
          *QuadPart = (v6 - *(_QWORD *)&v8) / 0x989680;
LABEL_51:
          FileTimeToSystemTime(&FileTime, &v31);
          return LastError;
        }
      }
    }
  }
LABEL_39:
  LastError = GetLastError();
  if ( !LastError )
    goto LABEL_51;
  return LastError;
}

```

## disassembly

```asm
0x180018f9c  push    rbp
0x180018f9e  push    rbx
0x180018f9f  push    rsi
0x180018fa0  push    rdi
0x180018fa1  push    r12
0x180018fa3  push    r13
0x180018fa5  push    r14
0x180018fa7  push    r15
0x180018fa9  lea     rbp, [rsp-1Fh]
0x180018fae  sub     rsp, 0A8h
0x180018fb5  mov     rax, cs:__security_cookie
0x180018fbc  xor     rax, rsp
0x180018fbf  mov     [rbp+57h+var_50], rax
0x180018fc3  xorps   xmm0, xmm0
0x180018fc6  mov     [rbp+57h+var_98], r9
0x180018fca  mov     rax, r8
0x180018fcd  mov     [rbp+57h+var_A8], rcx
0x180018fd1  shr     rax, 20h
0x180018fd5  xorps   xmm1, xmm1
0x180018fd8  cmp     dword ptr [rcx], 2
0x180018fdb  mov     r12, rcx
0x180018fde  movups  xmmword ptr [rbp+57h+LocalTime.wYear], xmm0
0x180018fe2  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x180018fea  movups  xmmword ptr [rbp+57h+var_80.wYear], xmm0
0x180018fee  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm1
0x180018ff2  movups  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x180018ff6  jz      short loc_180018FFF
0x180018ff8  xor     eax, eax
0x180018ffa  jmp     loc_1800193C5
0x180018fff  mov     [rbp+57h+FileTime1.dwLowDateTime], r8d
0x180019003  xor     ecx, ecx; lpTimeZoneInformation
0x180019005  lea     r8, [rbp+57h+LocalTime]; lpLocalTime
0x180019009  mov     dword ptr [r9], 0
0x180019010  mov     [rbp+57h+FileTime1.dwHighDateTime], eax
0x180019013  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180019019  test    eax, eax
0x18001901b  jz      loc_1800192BD
0x180019021  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180019025  lea     rcx, [rbp+57h+LocalTime]; lpSystemTime
0x180019029  call    cs:__imp_SystemTimeToFileTime
0x18001902f  test    eax, eax
0x180019031  jz      loc_1800192BD
0x180019037  mov     rbx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18001903b  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x18001903f  lea     rcx, [rbp+57h+FileTime1]; lpFileTime
0x180019043  call    cs:__imp_FileTimeToSystemTime
0x180019049  test    eax, eax
0x18001904b  jz      loc_1800192BD
0x180019051  lea     r8, [rbp+57h+var_60]; lpLocalTime
0x180019055  xor     ecx, ecx; lpTimeZoneInformation
0x180019057  lea     rdx, [rbp+57h+SystemTime]; lpUniversalTime
0x18001905b  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180019061  test    eax, eax
0x180019063  jz      loc_1800192BD
0x180019069  lea     rdx, [rbp+57h+FileTime1]; lpFileTime
0x18001906d  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x180019071  call    cs:__imp_SystemTimeToFileTime
0x180019077  test    eax, eax
0x180019079  jz      loc_1800192BD
0x18001907f  cmp     byte ptr [r12+9], 0
0x180019085  mov     r15b, 0FFh
0x180019088  mov     rsi, qword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x18001908c  jz      loc_18001911E
0x180019092  mov     r8, qword ptr [rbp+57h+LocalTime.wDayOfWeek]
0x180019096  xor     r14b, r14b
0x180019099  cmp     r14b, 7
0x18001909d  jnb     short loc_1800190DD
0x18001909f  mov     cl, r14b
0x1800190a2  mov     edx, 1
0x1800190a7  shl     edx, cl
0x1800190a9  test    [r12+9], dl
0x1800190ae  jz      short loc_1800190CB
0x1800190b0  cmp     r15b, r14b
0x1800190b3  movzx   ecx, r15b
0x1800190b7  movzx   eax, r14b
0x1800190bb  cmovnb  ecx, eax
0x1800190be  movzx   eax, r14b
0x1800190c2  mov     r15b, cl
0x1800190c5  cmp     ax, r8w
0x1800190c9  jnb     short loc_1800190D0
0x1800190cb  inc     r14b
0x1800190ce  jmp     short loc_180019099
0x1800190d0  movzx   eax, r8w
0x1800190d4  movzx   ecx, r14b
0x1800190d8  sub     rcx, rax
0x1800190db  jmp     short loc_1800190F1
0x1800190dd  mov     r14b, 0FFh
0x1800190e0  jnz     short loc_1800190FA
0x1800190e2  movzx   ecx, r15b
0x1800190e6  movzx   eax, r8w
0x1800190ea  sub     rcx, rax
0x1800190ed  add     rcx, 7
0x1800190f1  imul    rax, rcx, 15180h
0x1800190f8  jmp     short loc_1800190FC
0x1800190fa  xor     eax, eax
0x1800190fc  mov     eax, eax
0x1800190fe  imul    rcx, rax, 989680h
0x180019105  add     rbx, rcx
0x180019108  mov     [rbp+57h+var_B8], rbx
0x18001910c  mov     eax, dword ptr [rbp+57h+var_B8]
0x18001910f  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180019112  mov     rax, rbx
0x180019115  shr     rax, 20h
0x180019119  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x18001911c  jmp     short loc_180019121
0x18001911e  mov     r14b, r15b
0x180019121  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x180019125  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180019129  call    cs:__imp_CompareFileTime
0x18001912f  test    eax, eax
0x180019131  jle     loc_180019399
0x180019137  movzx   r8d, byte ptr [r12+8]
0x18001913d  mov     r9, 58028E44000h
0x180019147  xor     edx, edx
0x180019149  mov     ecx, r8d
0x18001914c  imul    rcx, r9
0x180019150  mov     rax, rsi
0x180019153  sub     rax, rbx
0x180019156  div     rcx
0x180019159  mov     rdi, rax
0x18001915c  imul    rdi, r8
0x180019160  imul    rdi, r9
0x180019164  add     rdi, rbx
0x180019167  cmp     r14b, 0FFh
0x18001916b  jz      short loc_1800191D7
0x18001916d  lea     r15d, [r14+1]
0x180019171  mov     r13, 0C92A69C000h
0x18001917b  cmp     r15b, 7
0x18001917f  jnb     loc_18001927E
0x180019185  mov     cl, r15b
0x180019188  mov     edx, 1
0x18001918d  shl     edx, cl
0x18001918f  test    [r12+9], dl
0x180019194  jz      short loc_1800191D2
0x180019196  movzx   eax, r14b
0x18001919a  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x18001919e  movzx   ebx, r15b
0x1800191a2  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x1800191a6  sub     rbx, rax
0x1800191a9  imul    rbx, r13
0x1800191ad  add     rbx, rdi
0x1800191b0  mov     [rbp+57h+var_B8], rbx
0x1800191b4  mov     eax, dword ptr [rbp+57h+var_B8]
0x1800191b7  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x1800191ba  mov     rax, rbx
0x1800191bd  shr     rax, 20h
0x1800191c1  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x1800191c4  call    cs:__imp_CompareFileTime
0x1800191ca  test    eax, eax
0x1800191cc  js      loc_180019399
0x1800191d2  inc     r15b
0x1800191d5  jmp     short loc_18001917B
0x1800191d7  cmp     r15b, 0FFh
0x1800191db  jz      loc_180019288
0x1800191e1  mov     r12b, 1
0x1800191e4  mov     r13, 0C92A69C000h
0x1800191ee  cmp     r12b, 7
0x1800191f2  jnb     loc_18001927A
0x1800191f8  movzx   r8d, [rbp+57h+LocalTime.wDayOfWeek]
0x1800191fd  movzx   eax, r12b
0x180019201  add     r8d, eax
0x180019204  mov     eax, 24924925h
0x180019209  mul     r8d
0x18001920c  mov     eax, r8d
0x18001920f  sub     eax, edx
0x180019211  shr     eax, 1
0x180019213  add     eax, edx
0x180019215  mov     edx, 1
0x18001921a  shr     eax, 2
0x18001921d  imul    eax, 7
0x180019220  sub     r8d, eax
0x180019223  mov     rax, [rbp+57h+var_A8]
0x180019227  mov     cl, r8b
0x18001922a  shl     edx, cl
0x18001922c  test    [rax+9], dl
0x18001922f  jz      short loc_180019272
0x180019231  cmp     r8b, r15b
0x180019234  jbe     short loc_180019272
0x180019236  movzx   eax, r15b
0x18001923a  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x18001923e  movzx   ebx, r8b
0x180019242  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180019246  sub     rbx, rax
0x180019249  imul    rbx, r13
0x18001924d  add     rbx, rdi
0x180019250  mov     [rbp+57h+var_B8], rbx
0x180019254  mov     eax, dword ptr [rbp+57h+var_B8]
0x180019257  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x18001925a  mov     rax, rbx
0x18001925d  shr     rax, 20h
0x180019261  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x180019264  call    cs:__imp_CompareFileTime
0x18001926a  test    eax, eax
0x18001926c  js      loc_180019399
0x180019272  inc     r12b
0x180019275  jmp     loc_1800191EE
0x18001927a  mov     r12, [rbp+57h+var_A8]
0x18001927e  mov     r9, 58028E44000h
0x180019288  movzx   ebx, byte ptr [r12+8]
0x18001928e  lea     rdx, [rbp+57h+var_80]; lpSystemTime
0x180019292  imul    rbx, r9
0x180019296  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x18001929a  add     rbx, rdi
0x18001929d  mov     rax, rbx
0x1800192a0  mov     [rbp+57h+var_B8], rbx
0x1800192a4  mov     r12d, dword ptr [rbp+57h+var_B8]
0x1800192a8  shr     rax, 20h
0x1800192ac  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x1800192af  mov     [rbp+57h+FileTime.dwLowDateTime], r12d
0x1800192b3  call    cs:__imp_FileTimeToSystemTime
0x1800192b9  test    eax, eax
0x1800192bb  jnz     short loc_1800192D2
0x1800192bd  call    cs:__imp_GetLastError
0x1800192c3  mov     edi, eax
0x1800192c5  test    eax, eax
0x1800192c7  jnz     loc_1800193C3
0x1800192cd  jmp     loc_1800193B5
0x1800192d2  mov     r8, rbx
0x1800192d5  mov     [rbp+57h+var_A0], rbx
0x1800192d9  mov     r15b, 7
0x1800192dc  xor     dil, dil
0x1800192df  cmp     dil, 7
0x1800192e3  jnb     loc_180019399
0x1800192e9  test    r15b, r15b
0x1800192ec  jnz     short loc_1800192F8
0x1800192ee  cmp     r14b, 0FFh
0x1800192f2  jnz     loc_180019399
0x1800192f8  movzx   r15d, [rbp+57h+var_80.wDayOfWeek]
0x1800192fd  movzx   eax, dil
0x180019301  sub     r15d, eax
0x180019304  mov     eax, 92492493h
0x180019309  add     r15d, 7
0x18001930d  imul    r15d
0x180019310  add     edx, r15d
0x180019313  sar     edx, 2
0x180019316  mov     eax, edx
0x180019318  shr     eax, 1Fh
0x18001931b  add     edx, eax
0x18001931d  imul    eax, edx, 7
0x180019320  mov     edx, 1
0x180019325  sub     r15d, eax
0x180019328  mov     rax, [rbp+57h+var_A8]
0x18001932c  mov     cl, r15b
0x18001932f  shl     edx, cl
0x180019331  test    [rax+9], dl
0x180019334  jz      short loc_18001937D
0x180019336  mov     r13d, dword ptr [rbp+57h+var_B8+4]
0x18001933a  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x18001933e  mov     rcx, 0FFFFFF36D5964000h
0x180019348  movzx   ebx, dil
0x18001934c  imul    rbx, rcx
0x180019350  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180019354  add     rbx, r8
0x180019357  mov     [rbp+57h+var_B8], rbx
0x18001935b  mov     eax, dword ptr [rbp+57h+var_B8]
0x18001935e  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180019361  mov     rax, rbx
0x180019364  shr     rax, 20h
0x180019368  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x18001936b  call    cs:__imp_CompareFileTime
0x180019371  test    eax, eax
0x180019373  jg      short loc_180019385
0x180019375  mov     r12d, dword ptr [rbp+57h+var_B8]
0x180019379  mov     r8, [rbp+57h+var_A0]
0x18001937d  inc     dil
0x180019380  jmp     loc_1800192DF
0x180019385  mov     dword ptr [rbp+57h+var_B8], r12d
0x180019389  mov     dword ptr [rbp+57h+var_B8+4], r13d
0x18001938d  mov     rbx, [rbp+57h+var_B8]
0x180019391  mov     [rbp+57h+FileTime.dwLowDateTime], r12d
0x180019395  mov     [rbp+57h+FileTime.dwHighDateTime], r13d
0x180019399  sub     rbx, rsi
0x18001939c  mov     rax, 0D6BF94D5E57A42BDh
0x1800193a6  mul     rbx
0x1800193a9  mov     rax, [rbp+57h+var_98]
0x1800193ad  xor     edi, edi
0x1800193af  shr     rdx, 17h
0x1800193b3  mov     [rax], edx
0x1800193b5  lea     rdx, [rbp+57h+var_80]; lpSystemTime
0x1800193b9  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1800193bd  call    cs:__imp_FileTimeToSystemTime
0x1800193c3  mov     eax, edi
0x1800193c5  mov     rcx, [rbp+57h+var_50]
0x1800193c9  xor     rcx, rsp; StackCookie
0x1800193cc  call    __security_check_cookie
0x1800193d1  add     rsp, 0A8h
0x1800193d8  pop     r15
0x1800193da  pop     r14
0x1800193dc  pop     r13
0x1800193de  pop     r12
0x1800193e0  pop     rdi
0x1800193e1  pop     rsi
0x1800193e2  pop     rbx
0x1800193e3  pop     rbp
0x1800193e4  retn
```
