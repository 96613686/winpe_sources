# Broker::GetMonthlyDelay(_TB_IRREGULAR_SCHEDULE *,_SYSTEMTIME *,_ULARGE_INTEGER,ulong *)

- ea: `0x180018c8c`
- end: `0x180018f93`
- name: `?GetMonthlyDelay@Broker@@YAKPEAU_TB_IRREGULAR_SCHEDULE@@PEAU_SYSTEMTIME@@T_ULARGE_INTEGER@@PEAK@Z`
- size: `775`
- prototype: `__int64 __fastcall(Broker *this, const SYSTEMTIME *, struct _SYSTEMTIME *, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800113dc`

## callees

- `0x180012dd0`
- `0x180018c8c`
- `0x1800193ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f4d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018d4d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018de5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018ef0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018d4d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018de5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018ef0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018d1f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018dfb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018f61`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018d1f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018dfb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018f61`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180018d37`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180018d68`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180018d37`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180018d68`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018e11`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018e11`

## pseudocode

```c
__int64 __fastcall Broker::GetMonthlyDelay(
        Broker *this,
        const SYSTEMTIME *a2,
        struct _SYSTEMTIME *a3,
        union _ULARGE_INTEGER a4)
{
  unsigned int v5; // eax
  FILETIME v9; // rbx
  WORD wYear; // r9
  WORD v11; // r8
  WORD wMonth; // dx
  int v13; // eax
  int v14; // eax
  struct _FILETIME *wDay; // r9
  int v16; // edx
  unsigned __int8 v17; // al
  DWORD LastError; // edi
  FILETIME FileTime2; // [rsp+20h] [rbp-60h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-58h] BYREF
  FILETIME FileTime; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 v22[4]; // [rsp+38h] [rbp-48h] BYREF
  SYSTEMTIME v23; // [rsp+40h] [rbp-40h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+50h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  *(_QWORD *)v22 = 0;
  FileTime1 = 0;
  FileTime2 = 0;
  v5 = *(_DWORD *)this - 3;
  FileTime = 0;
  SystemTime = 0;
  LocalTime = 0;
  v23 = 0;
  if ( v5 > 1 )
    return 0;
  FileTime.dwHighDateTime = HIDWORD(a3);
  *(_DWORD *)a4.QuadPart = 0;
  FileTime.dwLowDateTime = (unsigned int)a3;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    {
      if ( SystemTimeToFileTime(&LocalTime, &FileTime1) )
      {
        v9 = FileTime1;
        if ( SystemTimeToTzSpecificLocalTime(0, a2, &v23) )
        {
          wYear = LocalTime.wYear;
          v11 = LocalTime.wYear;
          wMonth = LocalTime.wMonth;
          v23.wYear = LocalTime.wYear;
          for ( v23.wDay = LocalTime.wDay; ; v23.wDay = 1 )
          {
            v23.wMonth = wMonth;
            if ( v11 - wYear > 4 )
              return 87;
            if ( *(_DWORD *)this == 3 )
            {
              v13 = *((unsigned __int16 *)this + 6);
              if ( _bittest(&v13, (unsigned __int8)(wMonth - 1)) )
                break;
            }
            if ( *(_DWORD *)this == 4 )
            {
              v14 = *((unsigned __int16 *)this + 5);
              if ( _bittest(&v14, (unsigned __int8)(wMonth - 1)) )
                break;
            }
LABEL_29:
            if ( wMonth == 12 )
            {
              ++v11;
              wMonth = 1;
              v23.wYear = v11;
            }
            else
            {
              ++wMonth;
            }
          }
          if ( SystemTimeToFileTime(&v23, &FileTime2) && FileTimeToSystemTime(&FileTime2, &v23) )
          {
            while ( 1 )
            {
              if ( CompareFileTime(&FileTime1, &FileTime2) >= 0 )
                goto LABEL_26;
              if ( *(_DWORD *)this == 3 )
              {
                wDay = (struct _FILETIME *)v23.wDay;
                v16 = *((_DWORD *)this + 2);
                if ( _bittest(&v16, (unsigned __int8)(LOBYTE(v23.wDay) - 1)) )
                  goto LABEL_33;
                if ( v16 >= 0 )
                  goto LABEL_21;
                if ( !Broker::TbSystemTimeToFileTime(
                        (Broker *)&v23,
                        (struct _SYSTEMTIME *)1,
                        (unsigned __int16)v22,
                        (struct _FILETIME *)v23.wDay) )
                  goto LABEL_33;
              }
              wDay = (struct _FILETIME *)v23.wDay;
LABEL_21:
              if ( *(_DWORD *)this == 4 && ((unsigned __int8)(1 << SLOBYTE(v23.wDayOfWeek)) & *((_BYTE *)this + 9)) != 0 )
              {
                v17 = *((_BYTE *)this + 8);
                if ( ((unsigned __int8)(1 << (((unsigned __int16)wDay - 1) / 7)) & v17) != 0 )
                  goto LABEL_33;
                if ( (v17 & 0x10) != 0 )
                {
                  if ( !Broker::TbSystemTimeToFileTime(
                          (Broker *)&v23,
                          (struct _SYSTEMTIME *)7,
                          (unsigned __int16)v22,
                          wDay) )
                  {
LABEL_33:
                    LastError = 0;
                    *(_DWORD *)a4.QuadPart = (*(_QWORD *)&FileTime2 - *(_QWORD *)&v9) / 0x989680uLL;
                    goto LABEL_35;
                  }
LABEL_26:
                  LOWORD(wDay) = v23.wDay;
                }
              }
              v23.wDay = (_WORD)wDay + 1;
              v23.wDayOfWeek = ((unsigned int)v23.wDayOfWeek + 1) % 7;
              if ( !SystemTimeToFileTime(&v23, &FileTime2) )
              {
                wYear = LocalTime.wYear;
                wMonth = v23.wMonth;
                v11 = v23.wYear;
                goto LABEL_29;
              }
            }
          }
        }
      }
    }
  }
  LastError = GetLastError();
  if ( !LastError )
LABEL_35:
    FileTimeToSystemTime(&FileTime2, &v23);
  return LastError;
}

```

## disassembly

```asm
0x180018c8c  mov     [rsp-28h+arg_0], rbx
0x180018c91  push    rbp
0x180018c92  push    rsi
0x180018c93  push    rdi
0x180018c94  push    r12
0x180018c96  push    r14
0x180018c98  mov     rbp, rsp
0x180018c9b  sub     rsp, 80h
0x180018ca2  mov     rax, cs:__security_cookie
0x180018ca9  xor     rax, rsp
0x180018cac  mov     [rbp+var_10], rax
0x180018cb0  mov     rdi, rcx
0x180018cb3  mov     qword ptr [rbp+var_48], 0
0x180018cbb  xorps   xmm0, xmm0
0x180018cbe  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180018cc6  mov     rcx, r8
0x180018cc9  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x180018cd1  shr     rcx, 20h
0x180018cd5  mov     r12d, 1
0x180018cdb  mov     eax, [rdi]
0x180018cdd  xorps   xmm1, xmm1
0x180018ce0  sub     eax, 3
0x180018ce3  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180018ceb  mov     r14, r9
0x180018cee  mov     rsi, rdx
0x180018cf1  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018cf5  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x180018cf9  movups  xmmword ptr [rbp+var_40.wYear], xmm0
0x180018cfd  cmp     eax, r12d
0x180018d00  jbe     short loc_180018D09
0x180018d02  xor     eax, eax
0x180018d04  jmp     loc_180018F70
0x180018d09  mov     [rbp+FileTime.dwHighDateTime], ecx
0x180018d0c  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180018d10  lea     rcx, [rbp+FileTime]; lpFileTime
0x180018d14  mov     dword ptr [r9], 0
0x180018d1b  mov     [rbp+FileTime.dwLowDateTime], r8d
0x180018d1f  call    cs:__imp_FileTimeToSystemTime
0x180018d25  test    eax, eax
0x180018d27  jz      loc_180018F4D
0x180018d2d  lea     r8, [rbp+LocalTime]; lpLocalTime
0x180018d31  xor     ecx, ecx; lpTimeZoneInformation
0x180018d33  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x180018d37  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180018d3d  test    eax, eax
0x180018d3f  jz      loc_180018F4D
0x180018d45  lea     rdx, [rbp+FileTime1]; lpFileTime
0x180018d49  lea     rcx, [rbp+LocalTime]; lpSystemTime
0x180018d4d  call    cs:__imp_SystemTimeToFileTime
0x180018d53  test    eax, eax
0x180018d55  jz      loc_180018F4D
0x180018d5b  mov     rbx, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180018d5f  lea     r8, [rbp+var_40]; lpLocalTime
0x180018d63  mov     rdx, rsi; lpUniversalTime
0x180018d66  xor     ecx, ecx; lpTimeZoneInformation
0x180018d68  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180018d6e  test    eax, eax
0x180018d70  jz      loc_180018F4D
0x180018d76  movzx   r9d, [rbp+LocalTime.wYear]
0x180018d7b  movzx   eax, [rbp+LocalTime.wDay]
0x180018d7f  movzx   r8d, r9w
0x180018d83  movzx   edx, [rbp+LocalTime.wMonth]
0x180018d87  mov     [rbp+var_40.wYear], r9w
0x180018d8c  mov     [rbp+var_40.wDay], ax
0x180018d90  movzx   ecx, r8w
0x180018d94  movzx   eax, r9w
0x180018d98  sub     ecx, eax
0x180018d9a  mov     [rbp+var_40.wMonth], dx
0x180018d9e  cmp     ecx, 4
0x180018da1  jg      loc_180018F69
0x180018da7  cmp     dword ptr [rdi], 3
0x180018daa  jnz     short loc_180018DBE
0x180018dac  movzx   eax, dx
0x180018daf  sub     eax, r12d
0x180018db2  movzx   ecx, al
0x180018db5  movzx   eax, word ptr [rdi+0Ch]
0x180018db9  bt      eax, ecx
0x180018dbc  jb      short loc_180018DDD
0x180018dbe  cmp     dword ptr [rdi], 4
0x180018dc1  jnz     loc_180018F0C
0x180018dc7  movzx   eax, dx
0x180018dca  sub     eax, r12d
0x180018dcd  movzx   ecx, al
0x180018dd0  movzx   eax, word ptr [rdi+0Ah]
0x180018dd4  bt      eax, ecx
0x180018dd7  jnb     loc_180018F0C
0x180018ddd  lea     rdx, [rbp+FileTime2]; lpFileTime
0x180018de1  lea     rcx, [rbp+var_40]; lpSystemTime
0x180018de5  call    cs:__imp_SystemTimeToFileTime
0x180018deb  test    eax, eax
0x180018ded  jz      loc_180018F4D
0x180018df3  lea     rdx, [rbp+var_40]; lpSystemTime
0x180018df7  lea     rcx, [rbp+FileTime2]; lpFileTime
0x180018dfb  call    cs:__imp_FileTimeToSystemTime
0x180018e01  test    eax, eax
0x180018e03  jz      loc_180018F4D
0x180018e09  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180018e0d  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180018e11  call    cs:__imp_CompareFileTime
0x180018e17  test    eax, eax
0x180018e19  jns     loc_180018EB8
0x180018e1f  cmp     dword ptr [rdi], 3
0x180018e22  jnz     short loc_180018E5A
0x180018e24  movzx   r9d, [rbp+var_40.wDay]; struct _FILETIME *
0x180018e29  mov     edx, [rdi+8]
0x180018e2c  mov     eax, r9d
0x180018e2f  sub     eax, r12d
0x180018e32  movzx   ecx, al
0x180018e35  bt      edx, ecx
0x180018e38  jb      loc_180018F2E
0x180018e3e  test    edx, edx
0x180018e40  jns     short loc_180018E5F
0x180018e42  mov     edx, r12d; struct _SYSTEMTIME *
0x180018e45  lea     r8, [rbp+var_48]; unsigned __int16
0x180018e49  lea     rcx, [rbp+var_40]; this
0x180018e4d  call    ?TbSystemTimeToFileTime@Broker@@YAHPEAU_SYSTEMTIME@@GPEAU_FILETIME@@@Z; Broker::TbSystemTimeToFileTime(_SYSTEMTIME *,ushort,_FILETIME *)
0x180018e52  test    eax, eax
0x180018e54  jz      loc_180018F2E
0x180018e5a  movzx   r9d, [rbp+var_40.wDay]; struct _FILETIME *
0x180018e5f  cmp     dword ptr [rdi], 4
0x180018e62  jnz     short loc_180018EBD
0x180018e64  mov     ecx, dword ptr [rbp+var_40.wDayOfWeek]
0x180018e67  mov     edx, r12d
0x180018e6a  shl     edx, cl
0x180018e6c  test    [rdi+9], dl
0x180018e6f  jz      short loc_180018EBD
0x180018e71  movzx   r8d, r9w
0x180018e75  mov     eax, 92492493h
0x180018e7a  sub     r8d, r12d
0x180018e7d  imul    r8d
0x180018e80  lea     ecx, [r8+rdx]
0x180018e84  mov     edx, r12d
0x180018e87  sar     ecx, 2
0x180018e8a  mov     eax, ecx
0x180018e8c  shr     eax, 1Fh
0x180018e8f  add     ecx, eax
0x180018e91  mov     al, [rdi+8]
0x180018e94  shl     edx, cl
0x180018e96  test    al, dl
0x180018e98  jnz     loc_180018F2E
0x180018e9e  test    al, 10h
0x180018ea0  jz      short loc_180018EBD
0x180018ea2  mov     edx, 7; struct _SYSTEMTIME *
0x180018ea7  lea     r8, [rbp+var_48]; unsigned __int16
0x180018eab  lea     rcx, [rbp+var_40]; this
0x180018eaf  call    ?TbSystemTimeToFileTime@Broker@@YAHPEAU_SYSTEMTIME@@GPEAU_FILETIME@@@Z; Broker::TbSystemTimeToFileTime(_SYSTEMTIME *,ushort,_FILETIME *)
0x180018eb4  test    eax, eax
0x180018eb6  jz      short loc_180018F2E
0x180018eb8  movzx   r9d, [rbp+var_40.wDay]
0x180018ebd  movzx   ecx, [rbp+var_40.wDayOfWeek]
0x180018ec1  mov     eax, 24924925h
0x180018ec6  add     ecx, r12d
0x180018ec9  add     r9w, r12w
0x180018ecd  mul     ecx
0x180018ecf  mov     eax, ecx
0x180018ed1  mov     [rbp+var_40.wDay], r9w
0x180018ed6  sub     eax, edx
0x180018ed8  shr     eax, 1
0x180018eda  add     eax, edx
0x180018edc  lea     rdx, [rbp+FileTime2]; lpFileTime
0x180018ee0  shr     eax, 2
0x180018ee3  imul    eax, 7
0x180018ee6  sub     ecx, eax
0x180018ee8  mov     [rbp+var_40.wDayOfWeek], cx
0x180018eec  lea     rcx, [rbp+var_40]; lpSystemTime
0x180018ef0  call    cs:__imp_SystemTimeToFileTime
0x180018ef6  test    eax, eax
0x180018ef8  jnz     loc_180018E09
0x180018efe  movzx   r9d, [rbp+LocalTime.wYear]
0x180018f03  movzx   edx, [rbp+var_40.wMonth]
0x180018f07  movzx   r8d, [rbp+var_40.wYear]
0x180018f0c  cmp     dx, 0Ch
0x180018f10  jnz     short loc_180018F20
0x180018f12  add     r8w, r12w
0x180018f16  mov     edx, r12d
0x180018f19  mov     [rbp+var_40.wYear], r8w
0x180018f1e  jmp     short loc_180018F24
0x180018f20  add     dx, r12w
0x180018f24  mov     [rbp+var_40.wDay], r12w
0x180018f29  jmp     loc_180018D90
0x180018f2e  mov     rcx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180018f32  mov     rax, 0D6BF94D5E57A42BDh
0x180018f3c  sub     rcx, rbx
0x180018f3f  xor     edi, edi
0x180018f41  mul     rcx
0x180018f44  shr     rdx, 17h
0x180018f48  mov     [r14], edx
0x180018f4b  jmp     short loc_180018F59
0x180018f4d  call    cs:__imp_GetLastError
0x180018f53  mov     edi, eax
0x180018f55  test    eax, eax
0x180018f57  jnz     short loc_180018F6E
0x180018f59  lea     rdx, [rbp+var_40]; lpSystemTime
0x180018f5d  lea     rcx, [rbp+FileTime2]; lpFileTime
0x180018f61  call    cs:__imp_FileTimeToSystemTime
0x180018f67  jmp     short loc_180018F6E
0x180018f69  mov     edi, 57h ; 'W'
0x180018f6e  mov     eax, edi
0x180018f70  mov     rcx, [rbp+var_10]
0x180018f74  xor     rcx, rsp; StackCookie
0x180018f77  call    __security_check_cookie
0x180018f7c  mov     rbx, [rsp+80h+arg_0]
0x180018f84  add     rsp, 80h
0x180018f8b  pop     r14
0x180018f8d  pop     r12
0x180018f8f  pop     rdi
0x180018f90  pop     rsi
0x180018f91  pop     rbp
0x180018f92  retn
```
