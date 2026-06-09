# mkl_serv_sscanf_s

- ea: `0x18000f4f0`
- end: `0x18000fa70`
- name: `mkl_serv_sscanf_s`
- size: `1408`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800779d0`

## callees

- `0x18000e560`
- `0x18000e580`
- `0x18000f4f0`
- `0x1832dbef0`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18000f7a4`
- `KERNEL32!GetModuleHandleA` at `0x18000f95d`
- `KERNEL32!GetModuleHandleA` at `0x18000f7a4`
- `KERNEL32!GetModuleHandleA` at `0x18000f95d`
- `KERNEL32!GetProcAddress` at `0x18000f7ed`
- `KERNEL32!GetProcAddress` at `0x18000f80d`
- `KERNEL32!GetProcAddress` at `0x18000f829`
- `KERNEL32!GetProcAddress` at `0x18000f845`
- `KERNEL32!GetProcAddress` at `0x18000f861`
- `KERNEL32!GetProcAddress` at `0x18000f87d`
- `KERNEL32!GetProcAddress` at `0x18000f9a6`
- `KERNEL32!GetProcAddress` at `0x18000f9c6`
- `KERNEL32!GetProcAddress` at `0x18000f9e6`
- `KERNEL32!GetProcAddress` at `0x18000fa06`
- `KERNEL32!GetProcAddress` at `0x18000fa26`
- `KERNEL32!GetProcAddress` at `0x18000fa46`
- `KERNEL32!GetProcAddress` at `0x18000f7ed`
- `KERNEL32!GetProcAddress` at `0x18000f80d`
- `KERNEL32!GetProcAddress` at `0x18000f829`
- `KERNEL32!GetProcAddress` at `0x18000f845`
- `KERNEL32!GetProcAddress` at `0x18000f861`
- `KERNEL32!GetProcAddress` at `0x18000f87d`
- `KERNEL32!GetProcAddress` at `0x18000f9a6`
- `KERNEL32!GetProcAddress` at `0x18000f9c6`
- `KERNEL32!GetProcAddress` at `0x18000f9e6`
- `KERNEL32!GetProcAddress` at `0x18000fa06`
- `KERNEL32!GetProcAddress` at `0x18000fa26`
- `KERNEL32!GetProcAddress` at `0x18000fa46`
- `KERNEL32!LoadLibraryA` at `0x18000f7c3`
- `KERNEL32!LoadLibraryA` at `0x18000f97c`
- `KERNEL32!LoadLibraryA` at `0x18000f7c3`
- `KERNEL32!LoadLibraryA` at `0x18000f97c`

## string_xrefs

- `0x18000f89e`: `MSVCR120.DLL`
- `0x18000f8a5`: `MSVCR120D.DLL`
- `0x18000f8ff`: `MSVCR110.DLL`
- `0x18000f906`: `MSVCR110D.DLL`
- `0x18000f90d`: `MSVCR100.DLL`
- `0x18000f914`: `MSVCR100D.DLL`
- `0x18000f8b4`: `MSVCR90.DLL`
- `0x18000f8c3`: `MSVCR90D.DLL`
- `0x18000f8d2`: `MSVCR80.DLL`
- `0x18000f8e1`: `MSVCR80D.DLL`
- `0x18000f8f0`: `MSVCRT.DLL`
- `0x18000f91b`: `MSVCRTD.DLL`
- `0x18000f75d`: `APPCRT140.DLL`
- `0x18000f764`: `APPCRT140D.DLL`
- `0x18000f76b`: `UCRTBASE.DLL`
- `0x18000f772`: `UCRTBASED.DLL`
- `0x18000f7e6`: `__stdio_common_vsscanf`
- `0x18000f806`: `__stdio_common_vfscanf`
- `0x18000f822`: `__stdio_common_vsnprintf_s`
- `0x18000f83e`: `__stdio_common_vfprintf_s`

## pseudocode

```c
__int64 mkl_serv_sscanf_s(__int64 a1, const char *a2, ...)
{
  __int64 v3; // rax
  __int64 v4; // r13
  __int64 result; // rax
  char *v6; // rax
  char v7; // r8
  const char *v8; // rcx
  const char *v9; // rax
  __int64 v10; // r8
  va_list v11; // rax
  __int64 v12; // r15
  HMODULE ModuleHandleA; // rax
  unsigned __int64 i; // r15
  HMODULE v15; // r15
  __int64 v16; // r15
  HMODULE LibraryA; // rax
  unsigned __int64 j; // r15
  HMODULE v19; // r15
  LPCSTR lpModuleName; // [rsp+90h] [rbp-108h]
  const char *v21; // [rsp+98h] [rbp-100h]
  const char *v22; // [rsp+A0h] [rbp-F8h]
  const char *v23; // [rsp+A8h] [rbp-F0h]
  const char *v24; // [rsp+B0h] [rbp-E8h]
  const char *v25; // [rsp+B8h] [rbp-E0h]
  const char *v26; // [rsp+C0h] [rbp-D8h]
  const char *v27; // [rsp+C8h] [rbp-D0h]
  const char *v28; // [rsp+D0h] [rbp-C8h]
  const char *v29; // [rsp+D8h] [rbp-C0h]
  const char *v30; // [rsp+E0h] [rbp-B8h]
  const char *v31; // [rsp+E8h] [rbp-B0h]
  _QWORD v32[16]; // [rsp+F0h] [rbp-A8h]
  va_list v33; // [rsp+170h] [rbp-28h]
  va_list va; // [rsp+1B0h] [rbp+18h] BYREF

  va_start(va, a2);
  v3 = 16;
  do
  {
    *(_OWORD *)&(&v30)[v3] = 0;
    *(_OWORD *)&(&v28)[v3] = 0;
    *(_OWORD *)&(&v26)[v3] = 0;
    *(_OWORD *)&(&v24)[v3] = 0;
    v3 -= 8;
  }
  while ( v3 * 8 );
  v4 = 0;
  va_copy(v33, va);
  if ( dword_1836D0DF0 == -1 )
  {
    sub_18000E560();
    if ( dword_1836D0DF0 == -1 )
    {
      lpModuleName = "APPCRT140.DLL";
      v12 = 0;
      v21 = "APPCRT140D.DLL";
      v22 = "UCRTBASE.DLL";
      v23 = "UCRTBASED.DLL";
      while ( 1 )
      {
        ModuleHandleA = GetModuleHandleA((&lpModuleName)[v12]);
        if ( ModuleHandleA )
          break;
        if ( (unsigned __int64)++v12 >= 4 )
        {
          for ( i = 0; i < 4; ++i )
          {
            ModuleHandleA = LoadLibraryA((&lpModuleName)[i]);
            if ( ModuleHandleA )
              break;
          }
          break;
        }
      }
      v15 = ModuleHandleA;
      if ( ModuleHandleA
        && (qword_1836E89D8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(ModuleHandleA, "__stdio_common_vsscanf")) != 0
        && (qword_1836E89E0 = (__int64)GetProcAddress(v15, "__stdio_common_vfscanf")) != 0
        && (qword_1836E89E8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(v15, "__stdio_common_vsnprintf_s")) != 0
        && (qword_1836E89D0 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                v15,
                                                                                                "__stdio_common_vfprintf_s")) != 0
        && (qword_1836E89F0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v15, "__acrt_iob_func")) != 0
        && (qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v15, "fflush")) != 0 )
      {
        dword_1836D0DF0 = 2;
      }
      else
      {
        lpModuleName = "MSVCR120.DLL";
        v26 = "MSVCR90.DLL";
        v27 = "MSVCR90D.DLL";
        v28 = "MSVCR80.DLL";
        v29 = "MSVCR80D.DLL";
        v30 = "MSVCRT.DLL";
        v21 = "MSVCR120D.DLL";
        v22 = "MSVCR110.DLL";
        v23 = "MSVCR110D.DLL";
        v24 = "MSVCR100.DLL";
        v25 = "MSVCR100D.DLL";
        v16 = 0;
        v31 = "MSVCRTD.DLL";
        while ( 1 )
        {
          LibraryA = GetModuleHandleA((&lpModuleName)[v16]);
          if ( LibraryA )
            break;
          if ( (unsigned __int64)++v16 >= 0xC )
          {
            for ( j = 0; j < 0xC; ++j )
            {
              LibraryA = LoadLibraryA((&lpModuleName)[j]);
              if ( LibraryA )
                break;
            }
            break;
          }
        }
        v19 = LibraryA;
        if ( LibraryA )
        {
          qword_1836E89F8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(LibraryA, "sscanf");
          if ( qword_1836E89F8 )
          {
            qword_1836E8A00 = (__int64)GetProcAddress(v19, "fscanf");
            if ( qword_1836E8A00 )
            {
              qword_1836E89B8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(v19, "vfprintf_s");
              if ( qword_1836E89B8 )
              {
                qword_1836E8A08 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                    v19,
                                                                                                    "_vsnprintf_s");
                if ( qword_1836E8A08 )
                {
                  qword_1836E8A10 = GetProcAddress(v19, "__iob_func");
                  if ( qword_1836E8A10 )
                  {
                    qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v19, "fflush");
                    if ( qword_1836E89C0 )
                      dword_1836D0DF0 = 1;
                  }
                }
              }
            }
          }
        }
      }
    }
    sub_18000E580();
  }
  if ( dword_1836D0DF0 == 2 )
  {
    result = qword_1836E89D8(qword_1836E8A18, a1, 0x7FFFFFFF, a2, 0, v33);
    goto LABEL_7;
  }
  if ( dword_1836D0DF0 != 1 )
  {
    result = 0xFFFFFFFFLL;
LABEL_7:
    v33 = 0;
    return result;
  }
  v6 = strchr_0(a2, 37);
  if ( v6 )
  {
    do
    {
      v7 = v6[1];
      v8 = v6 + 1;
      v9 = v6 + 2;
      if ( v7 == 37 )
        v8 = v9;
      else
        ++v4;
      v6 = strchr_0(v8, 37);
    }
    while ( v6 );
    if ( v4 <= 16 )
    {
      v10 = 0;
      if ( v4 > 0 )
      {
        v11 = v33;
        do
        {
          v11 += 8;
          v33 = v11;
          v32[v10++] = *((_QWORD *)v11 - 1);
        }
        while ( v10 < v4 );
      }
      result = qword_1836E89F8(
                 a1,
                 a2,
                 v32[0],
                 v32[1],
                 v32[2],
                 v32[3],
                 v32[4],
                 v32[5],
                 v32[6],
                 v32[7],
                 v32[8],
                 v32[9],
                 v32[10],
                 v32[11],
                 v32[12],
                 v32[13],
                 v32[14],
                 v32[15],
                 lpModuleName,
                 v21,
                 v22,
                 v23,
                 v24,
                 v25,
                 v26,
                 v27,
                 v28,
                 v29,
                 v30,
                 v31);
      goto LABEL_7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f4f0  push    r13
0x18000f4f2  push    r14
0x18000f4f4  push    r15
0x18000f4f6  sub     rsp, 180h
0x18000f4fd  mov     r14, rcx
0x18000f500  mov     [rsp+198h+Str], rdx
0x18000f508  mov     eax, 80h
0x18000f50d  mov     [rsp+198h+arg_10], r8
0x18000f515  pxor    xmm0, xmm0
0x18000f519  mov     [rsp+198h+arg_18], r9
0x18000f521  movaps  [rsp+rax+198h+var_B8], xmm0
0x18000f529  movaps  [rsp+rax+198h+var_C8], xmm0
0x18000f531  movaps  [rsp+rax+198h+var_D8], xmm0
0x18000f539  movaps  [rsp+rax+198h+var_E8], xmm0
0x18000f541  sub     rax, 40h ; '@'
0x18000f545  jnz     short loc_18000F521
0x18000f547  xor     r13d, r13d
0x18000f54a  lea     rax, [rsp+198h+arg_10]
0x18000f552  mov     [rsp+198h+var_28], rax
0x18000f55a  mov     eax, cs:dword_1836D0DF0
0x18000f560  cmp     eax, 0FFFFFFFFh
0x18000f563  jz      loc_18000F743
0x18000f569  mov     eax, cs:dword_1836D0DF0
0x18000f56f  cmp     eax, 2
0x18000f572  jz      loc_18000F709
0x18000f578  mov     eax, cs:dword_1836D0DF0
0x18000f57e  cmp     eax, 1
0x18000f581  jz      short loc_18000F5A2
0x18000f583  mov     eax, 0FFFFFFFFh
0x18000f588  mov     [rsp+198h+var_28], 0
0x18000f594  add     rsp, 180h
0x18000f59b  pop     r15
0x18000f59d  pop     r14
0x18000f59f  pop     r13
0x18000f5a1  retn
0x18000f5a2  mov     edx, 25h ; '%'; Val
0x18000f5a7  mov     rcx, [rsp+198h+Str]; Str
0x18000f5af  call    strchr_0
0x18000f5b4  test    rax, rax
0x18000f5b7  jz      loc_18000F6F9
0x18000f5bd  mov     r8b, [rax+1]
0x18000f5c1  lea     rcx, [rax+1]
0x18000f5c5  add     rax, 2
0x18000f5c9  cmp     r8b, 25h ; '%'
0x18000f5cd  cmovz   rcx, rax; Str
0x18000f5d1  lea     rax, [r13+1]
0x18000f5d5  cmovnz  r13, rax
0x18000f5d9  mov     edx, 25h ; '%'; Val
0x18000f5de  call    strchr_0
0x18000f5e3  test    rax, rax
0x18000f5e6  jnz     short loc_18000F5BD
0x18000f5e8  cmp     r13, 10h
0x18000f5ec  jg      loc_18000F6F9
0x18000f5f2  xor     r8d, r8d
0x18000f5f5  test    r13, r13
0x18000f5f8  jle     short loc_18000F622
0x18000f5fa  mov     rax, [rsp+198h+var_28]
0x18000f602  add     rax, 8
0x18000f606  mov     [rsp+198h+var_28], rax
0x18000f60e  mov     r9, [rax-8]
0x18000f612  mov     [rsp+r8*8+198h+var_A8], r9
0x18000f61a  inc     r8
0x18000f61d  cmp     r8, r13
0x18000f620  jl      short loc_18000F602
0x18000f622  mov     rax, rsp
0x18000f625  mov     rcx, r14
0x18000f628  mov     r10, [rsp+198h+var_98]
0x18000f630  mov     r11, [rsp+198h+var_90]
0x18000f638  mov     r13, [rsp+198h+var_88]
0x18000f640  mov     [rax+20h], r10
0x18000f644  mov     r10, [rsp+198h+var_78]
0x18000f64c  mov     [rax+40h], r10
0x18000f650  mov     r10, [rsp+198h+var_58]
0x18000f658  mov     [rax+60h], r10
0x18000f65c  mov     r10, [rsp+198h+var_50]
0x18000f664  mov     [rax+68h], r10
0x18000f668  mov     r10, [rsp+198h+var_48]
0x18000f670  mov     [rax+70h], r10
0x18000f674  mov     r10, [rsp+198h+var_40]
0x18000f67c  mov     [rax+78h], r10
0x18000f680  mov     r15, [rsp+198h+var_80]
0x18000f688  mov     r10, [rsp+198h+var_38]
0x18000f690  mov     [rax+28h], r11
0x18000f694  mov     [rax+30h], r13
0x18000f698  mov     [rax+38h], r15
0x18000f69c  mov     [rax+80h], r10
0x18000f6a3  mov     r11, [rsp+198h+var_70]
0x18000f6ab  mov     r13, [rsp+198h+var_68]
0x18000f6b3  mov     r15, [rsp+198h+var_60]
0x18000f6bb  mov     r10, [rsp+198h+var_30]
0x18000f6c3  mov     rdx, [rsp+198h+Str]
0x18000f6cb  mov     r8, [rsp+198h+var_A8]
0x18000f6d3  mov     r9, [rsp+198h+var_A0]
0x18000f6db  mov     [rax+48h], r11
0x18000f6df  mov     [rax+50h], r13
0x18000f6e3  mov     [rax+58h], r15
0x18000f6e7  mov     [rax+88h], r10
0x18000f6ee  call    cs:qword_1836E89F8
0x18000f6f4  jmp     loc_18000F588
0x18000f6f9  xor     eax, eax
0x18000f6fb  add     rsp, 180h
0x18000f702  pop     r15
0x18000f704  pop     r14
0x18000f706  pop     r13
0x18000f708  retn
0x18000f709  mov     r10, rsp
0x18000f70c  mov     rdx, r14
0x18000f70f  mov     rax, [rsp+198h+var_28]
0x18000f717  mov     r8d, 7FFFFFFFh
0x18000f71d  mov     rcx, cs:qword_1836E8A18
0x18000f724  mov     r9, [rsp+198h+Str]
0x18000f72c  mov     qword ptr [r10+20h], 0
0x18000f734  mov     [r10+28h], rax
0x18000f738  call    cs:qword_1836E89D8
0x18000f73e  jmp     loc_18000F588
0x18000f743  call    sub_18000E560
0x18000f748  mov     eax, cs:dword_1836D0DF0
0x18000f74e  cmp     eax, 0FFFFFFFFh
0x18000f751  jz      short loc_18000F75D
0x18000f753  call    sub_18000E580
0x18000f758  jmp     loc_18000F569
0x18000f75d  lea     rax, aAppcrt140Dll; "APPCRT140.DLL"
0x18000f764  lea     r8, aAppcrt140dDll; "APPCRT140D.DLL"
0x18000f76b  lea     r9, aUcrtbaseDll; "UCRTBASE.DLL"
0x18000f772  lea     r10, aUcrtbasedDll; "UCRTBASED.DLL"
0x18000f779  mov     [rsp+198h+lpModuleName], rax
0x18000f781  xor     r15d, r15d
0x18000f784  mov     [rsp+198h+var_100], r8
0x18000f78c  mov     [rsp+198h+var_F8], r9
0x18000f794  mov     [rsp+198h+var_F0], r10
0x18000f79c  mov     rcx, [rsp+r15*8+198h+lpModuleName]; lpModuleName
0x18000f7a4  call    cs:__imp_GetModuleHandleA
0x18000f7aa  test    rax, rax
0x18000f7ad  jnz     short loc_18000F7D7
0x18000f7af  inc     r15
0x18000f7b2  cmp     r15, 4
0x18000f7b6  jb      short loc_18000F79C
0x18000f7b8  xor     r15d, r15d
0x18000f7bb  mov     rcx, [rsp+r15*8+198h+lpModuleName]; lpLibFileName
0x18000f7c3  call    cs:__imp_LoadLibraryA
0x18000f7c9  test    rax, rax
0x18000f7cc  jnz     short loc_18000F7D7
0x18000f7ce  inc     r15
0x18000f7d1  cmp     r15, 4
0x18000f7d5  jb      short loc_18000F7BB
0x18000f7d7  mov     r15, rax
0x18000f7da  test    r15, r15
0x18000f7dd  jz      loc_18000F89E
0x18000f7e3  mov     rcx, r15; hModule
0x18000f7e6  lea     rdx, aStdioCommonVss; "__stdio_common_vsscanf"
0x18000f7ed  call    cs:__imp_GetProcAddress
0x18000f7f3  mov     cs:qword_1836E89D8, rax
0x18000f7fa  test    rax, rax
0x18000f7fd  jz      loc_18000F89E
0x18000f803  mov     rcx, r15; hModule
0x18000f806  lea     rdx, aStdioCommonVfs; "__stdio_common_vfscanf"
0x18000f80d  call    cs:__imp_GetProcAddress
0x18000f813  mov     cs:qword_1836E89E0, rax
0x18000f81a  test    rax, rax
0x18000f81d  jz      short loc_18000F89E
0x18000f81f  mov     rcx, r15; hModule
0x18000f822  lea     rdx, aStdioCommonVsn; "__stdio_common_vsnprintf_s"
0x18000f829  call    cs:__imp_GetProcAddress
0x18000f82f  mov     cs:qword_1836E89E8, rax
0x18000f836  test    rax, rax
0x18000f839  jz      short loc_18000F89E
0x18000f83b  mov     rcx, r15; hModule
0x18000f83e  lea     rdx, aStdioCommonVfp; "__stdio_common_vfprintf_s"
0x18000f845  call    cs:__imp_GetProcAddress
0x18000f84b  mov     cs:qword_1836E89D0, rax
0x18000f852  test    rax, rax
0x18000f855  jz      short loc_18000F89E
0x18000f857  mov     rcx, r15; hModule
0x18000f85a  lea     rdx, aAcrtIobFunc; "__acrt_iob_func"
0x18000f861  call    cs:__imp_GetProcAddress
0x18000f867  mov     cs:qword_1836E89F0, rax
0x18000f86e  test    rax, rax
0x18000f871  jz      short loc_18000F89E
0x18000f873  mov     rcx, r15; hModule
0x18000f876  lea     rdx, aFflush; "fflush"
0x18000f87d  call    cs:__imp_GetProcAddress
0x18000f883  mov     cs:qword_1836E89C0, rax
0x18000f88a  test    rax, rax
0x18000f88d  jz      short loc_18000F89E
0x18000f88f  mov     cs:dword_1836D0DF0, 2
0x18000f899  jmp     loc_18000F753
0x18000f89e  lea     rax, aMsvcr120Dll; "MSVCR120.DLL"
0x18000f8a5  lea     r8, aMsvcr120dDll; "MSVCR120D.DLL"
0x18000f8ac  mov     [rsp+198h+lpModuleName], rax
0x18000f8b4  lea     rax, aMsvcr90Dll; "MSVCR90.DLL"
0x18000f8bb  mov     qword ptr [rsp+198h+var_D8], rax
0x18000f8c3  lea     rax, aMsvcr90dDll; "MSVCR90D.DLL"
0x18000f8ca  mov     qword ptr [rsp+198h+var_D8+8], rax
0x18000f8d2  lea     rax, aMsvcr80Dll; "MSVCR80.DLL"
0x18000f8d9  mov     qword ptr [rsp+198h+var_C8], rax
0x18000f8e1  lea     rax, aMsvcr80dDll; "MSVCR80D.DLL"
0x18000f8e8  mov     qword ptr [rsp+198h+var_C8+8], rax
0x18000f8f0  lea     rax, aMsvcrtDll; "MSVCRT.DLL"
0x18000f8f7  mov     qword ptr [rsp+198h+var_B8], rax
0x18000f8ff  lea     r9, aMsvcr110Dll; "MSVCR110.DLL"
0x18000f906  lea     r10, aMsvcr110dDll; "MSVCR110D.DLL"
0x18000f90d  lea     r11, aMsvcr100Dll; "MSVCR100.DLL"
0x18000f914  lea     r15, aMsvcr100dDll; "MSVCR100D.DLL"
0x18000f91b  lea     rax, aMsvcrtdDll; "MSVCRTD.DLL"
0x18000f922  mov     [rsp+198h+var_100], r8
0x18000f92a  mov     [rsp+198h+var_F8], r9
0x18000f932  mov     [rsp+198h+var_F0], r10
0x18000f93a  mov     qword ptr [rsp+198h+var_E8], r11
0x18000f942  mov     qword ptr [rsp+198h+var_E8+8], r15
0x18000f94a  xor     r15d, r15d
0x18000f94d  mov     qword ptr [rsp+198h+var_B8+8], rax
0x18000f955  mov     rcx, [rsp+r15*8+198h+lpModuleName]; lpModuleName
0x18000f95d  call    cs:__imp_GetModuleHandleA
0x18000f963  test    rax, rax
0x18000f966  jnz     short loc_18000F990
0x18000f968  inc     r15
0x18000f96b  cmp     r15, 0Ch
0x18000f96f  jb      short loc_18000F955
0x18000f971  xor     r15d, r15d
0x18000f974  mov     rcx, [rsp+r15*8+198h+lpModuleName]; lpLibFileName
0x18000f97c  call    cs:__imp_LoadLibraryA
0x18000f982  test    rax, rax
0x18000f985  jnz     short loc_18000F990
0x18000f987  inc     r15
0x18000f98a  cmp     r15, 0Ch
0x18000f98e  jb      short loc_18000F974
0x18000f990  mov     r15, rax
0x18000f993  test    r15, r15
0x18000f996  jz      loc_18000F753
0x18000f99c  mov     rcx, r15; hModule
0x18000f99f  lea     rdx, aSscanf; "sscanf"
0x18000f9a6  call    cs:__imp_GetProcAddress
0x18000f9ac  mov     cs:qword_1836E89F8, rax
0x18000f9b3  test    rax, rax
0x18000f9b6  jz      loc_18000F753
0x18000f9bc  mov     rcx, r15; hModule
0x18000f9bf  lea     rdx, aFscanf; "fscanf"
0x18000f9c6  call    cs:__imp_GetProcAddress
0x18000f9cc  mov     cs:qword_1836E8A00, rax
0x18000f9d3  test    rax, rax
0x18000f9d6  jz      loc_18000F753
0x18000f9dc  mov     rcx, r15; hModule
0x18000f9df  lea     rdx, aVfprintfS; "vfprintf_s"
0x18000f9e6  call    cs:__imp_GetProcAddress
0x18000f9ec  mov     cs:qword_1836E89B8, rax
0x18000f9f3  test    rax, rax
0x18000f9f6  jz      loc_18000F753
0x18000f9fc  mov     rcx, r15; hModule
0x18000f9ff  lea     rdx, aVsnprintfS; "_vsnprintf_s"
0x18000fa06  call    cs:__imp_GetProcAddress
0x18000fa0c  mov     cs:qword_1836E8A08, rax
0x18000fa13  test    rax, rax
0x18000fa16  jz      loc_18000F753
0x18000fa1c  mov     rcx, r15; hModule
0x18000fa1f  lea     rdx, aIobFunc; "__iob_func"
0x18000fa26  call    cs:__imp_GetProcAddress
0x18000fa2c  mov     cs:qword_1836E8A10, rax
0x18000fa33  test    rax, rax
0x18000fa36  jz      loc_18000F753
0x18000fa3c  mov     rcx, r15; hModule
0x18000fa3f  lea     rdx, aFflush; "fflush"
0x18000fa46  call    cs:__imp_GetProcAddress
0x18000fa4c  mov     cs:qword_1836E89C0, rax
0x18000fa53  test    rax, rax
0x18000fa56  jz      loc_18000F753
0x18000fa5c  mov     cs:dword_1836D0DF0, 1
0x18000fa66  jmp     loc_18000F753
```
