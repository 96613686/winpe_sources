# mkl_serv_vsnprintf_s

- ea: `0x18000ed40`
- end: `0x18000f110`
- name: `mkl_serv_vsnprintf_s`
- size: `976`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c060`

## callees

- `0x18000e560`
- `0x18000e580`
- `0x18000ed40`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18000ee66`
- `KERNEL32!GetModuleHandleA` at `0x18000f001`
- `KERNEL32!GetModuleHandleA` at `0x18000ee66`
- `KERNEL32!GetModuleHandleA` at `0x18000f001`
- `KERNEL32!GetProcAddress` at `0x18000eeac`
- `KERNEL32!GetProcAddress` at `0x18000eecc`
- `KERNEL32!GetProcAddress` at `0x18000eee8`
- `KERNEL32!GetProcAddress` at `0x18000ef04`
- `KERNEL32!GetProcAddress` at `0x18000ef20`
- `KERNEL32!GetProcAddress` at `0x18000ef3c`
- `KERNEL32!GetProcAddress` at `0x18000f047`
- `KERNEL32!GetProcAddress` at `0x18000f067`
- `KERNEL32!GetProcAddress` at `0x18000f087`
- `KERNEL32!GetProcAddress` at `0x18000f0a7`
- `KERNEL32!GetProcAddress` at `0x18000f0c7`
- `KERNEL32!GetProcAddress` at `0x18000f0e7`
- `KERNEL32!GetProcAddress` at `0x18000eeac`
- `KERNEL32!GetProcAddress` at `0x18000eecc`
- `KERNEL32!GetProcAddress` at `0x18000eee8`
- `KERNEL32!GetProcAddress` at `0x18000ef04`
- `KERNEL32!GetProcAddress` at `0x18000ef20`
- `KERNEL32!GetProcAddress` at `0x18000ef3c`
- `KERNEL32!GetProcAddress` at `0x18000f047`
- `KERNEL32!GetProcAddress` at `0x18000f067`
- `KERNEL32!GetProcAddress` at `0x18000f087`
- `KERNEL32!GetProcAddress` at `0x18000f0a7`
- `KERNEL32!GetProcAddress` at `0x18000f0c7`
- `KERNEL32!GetProcAddress` at `0x18000f0e7`
- `KERNEL32!LoadLibraryA` at `0x18000ee82`
- `KERNEL32!LoadLibraryA` at `0x18000f01d`
- `KERNEL32!LoadLibraryA` at `0x18000ee82`
- `KERNEL32!LoadLibraryA` at `0x18000f01d`

## string_xrefs

- `0x18000ef5d`: `MSVCR120.DLL`
- `0x18000ef64`: `MSVCR120D.DLL`
- `0x18000efcd`: `MSVCR110.DLL`
- `0x18000efd4`: `MSVCR110D.DLL`
- `0x18000ef70`: `MSVCR100.DLL`
- `0x18000ef7c`: `MSVCR100D.DLL`
- `0x18000ef88`: `MSVCR90.DLL`
- `0x18000ef94`: `MSVCR90D.DLL`
- `0x18000efa0`: `MSVCR80.DLL`
- `0x18000efaf`: `MSVCR80D.DLL`
- `0x18000efbe`: `MSVCRT.DLL`
- `0x18000efdb`: `MSVCRTD.DLL`
- `0x18000ee2e`: `APPCRT140.DLL`
- `0x18000ee35`: `APPCRT140D.DLL`
- `0x18000ee3c`: `UCRTBASE.DLL`
- `0x18000ee43`: `UCRTBASED.DLL`
- `0x18000eea5`: `__stdio_common_vsscanf`
- `0x18000eec5`: `__stdio_common_vfscanf`
- `0x18000eee1`: `__stdio_common_vsnprintf_s`
- `0x18000eefd`: `__stdio_common_vfprintf_s`

## pseudocode

```c
__int64 __fastcall mkl_serv_vsnprintf_s(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  __int64 v10; // r15
  HMODULE ModuleHandleA; // rax
  unsigned __int64 i; // r15
  HMODULE v13; // r15
  __int64 v14; // r15
  HMODULE LibraryA; // rax
  unsigned __int64 j; // r15
  HMODULE v17; // r15
  LPCSTR lpModuleName; // [rsp+40h] [rbp-98h]
  const char *v19; // [rsp+48h] [rbp-90h]
  const char *v20; // [rsp+50h] [rbp-88h]
  const char *v21; // [rsp+58h] [rbp-80h]
  const char *v22; // [rsp+60h] [rbp-78h]
  const char *v23; // [rsp+68h] [rbp-70h]
  const char *v24; // [rsp+70h] [rbp-68h]
  const char *v25; // [rsp+78h] [rbp-60h]
  const char *v26; // [rsp+80h] [rbp-58h]
  const char *v27; // [rsp+88h] [rbp-50h]
  const char *v28; // [rsp+90h] [rbp-48h]
  const char *v29; // [rsp+98h] [rbp-40h]

  if ( dword_1836D0DF0 == -1 )
  {
    sub_18000E560();
    if ( dword_1836D0DF0 == -1 )
    {
      lpModuleName = "APPCRT140.DLL";
      v19 = "APPCRT140D.DLL";
      v20 = "UCRTBASE.DLL";
      v21 = "UCRTBASED.DLL";
      v10 = 0;
      while ( 1 )
      {
        ModuleHandleA = GetModuleHandleA((&lpModuleName)[v10]);
        if ( ModuleHandleA )
          break;
        if ( (unsigned __int64)++v10 >= 4 )
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
      v13 = ModuleHandleA;
      if ( ModuleHandleA
        && (qword_1836E89D8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(ModuleHandleA, "__stdio_common_vsscanf")) != 0
        && (qword_1836E89E0 = (__int64)GetProcAddress(v13, "__stdio_common_vfscanf")) != 0
        && (qword_1836E89E8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(v13, "__stdio_common_vsnprintf_s")) != 0
        && (qword_1836E89D0 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                v13,
                                                                                                "__stdio_common_vfprintf_s")) != 0
        && (qword_1836E89F0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v13, "__acrt_iob_func")) != 0
        && (qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v13, "fflush")) != 0 )
      {
        dword_1836D0DF0 = 2;
      }
      else
      {
        lpModuleName = "MSVCR120.DLL";
        v22 = "MSVCR100.DLL";
        v23 = "MSVCR100D.DLL";
        v24 = "MSVCR90.DLL";
        v25 = "MSVCR90D.DLL";
        v26 = "MSVCR80.DLL";
        v27 = "MSVCR80D.DLL";
        v28 = "MSVCRT.DLL";
        v19 = "MSVCR120D.DLL";
        v20 = "MSVCR110.DLL";
        v21 = "MSVCR110D.DLL";
        v14 = 0;
        v29 = "MSVCRTD.DLL";
        while ( 1 )
        {
          LibraryA = GetModuleHandleA((&lpModuleName)[v14]);
          if ( LibraryA )
            break;
          if ( (unsigned __int64)++v14 >= 0xC )
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
        v17 = LibraryA;
        if ( LibraryA )
        {
          qword_1836E89F8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(LibraryA, "sscanf");
          if ( qword_1836E89F8 )
          {
            qword_1836E8A00 = (__int64)GetProcAddress(v17, "fscanf");
            if ( qword_1836E8A00 )
            {
              qword_1836E89B8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(v17, "vfprintf_s");
              if ( qword_1836E89B8 )
              {
                qword_1836E8A08 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                    v17,
                                                                                                    "_vsnprintf_s");
                if ( qword_1836E8A08 )
                {
                  qword_1836E8A10 = GetProcAddress(v17, "__iob_func");
                  if ( qword_1836E8A10 )
                  {
                    qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v17, "fflush");
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
    result = qword_1836E89E8(qword_1836E89C8, a1, a2, a3, a4, 0, a5);
    if ( (int)result < 0 )
      return 0xFFFFFFFFLL;
  }
  else if ( dword_1836D0DF0 == 1 )
  {
    return qword_1836E8A08(a1, a2, a3, a4, a5);
  }
  else
  {
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ed40  push    rdi
0x18000ed41  push    r12
0x18000ed43  push    r13
0x18000ed45  push    r14
0x18000ed47  push    r15
0x18000ed49  push    rbp
0x18000ed4a  sub     rsp, 0A8h
0x18000ed51  mov     rdi, r9
0x18000ed54  mov     eax, cs:dword_1836D0DF0
0x18000ed5a  mov     r14, r8
0x18000ed5d  mov     rbp, [rsp+0D8h+arg_20]
0x18000ed65  mov     r13, rdx
0x18000ed68  mov     r12, rcx
0x18000ed6b  cmp     eax, 0FFFFFFFFh
0x18000ed6e  jz      loc_18000EE14
0x18000ed74  mov     eax, cs:dword_1836D0DF0
0x18000ed7a  cmp     eax, 2
0x18000ed7d  jz      short loc_18000EDCF
0x18000ed7f  mov     eax, cs:dword_1836D0DF0
0x18000ed85  cmp     eax, 1
0x18000ed88  jz      short loc_18000EDA1
0x18000ed8a  mov     eax, 0FFFFFFFFh
0x18000ed8f  add     rsp, 0A8h
0x18000ed96  pop     rbp
0x18000ed97  pop     r15
0x18000ed99  pop     r14
0x18000ed9b  pop     r13
0x18000ed9d  pop     r12
0x18000ed9f  pop     rdi
0x18000eda0  retn
0x18000eda1  mov     rax, cs:qword_1836E8A08
0x18000eda8  mov     rcx, r12
0x18000edab  mov     [rsp+0D8h+arg_20], rbp
0x18000edb3  mov     rdx, r13
0x18000edb6  mov     r8, r14
0x18000edb9  mov     r9, rdi
0x18000edbc  add     rsp, 0A8h
0x18000edc3  pop     rbp
0x18000edc4  pop     r15
0x18000edc6  pop     r14
0x18000edc8  pop     r13
0x18000edca  pop     r12
0x18000edcc  pop     rdi
0x18000edcd  jmp     rax
0x18000edcf  mov     rax, rsp
0x18000edd2  mov     rdx, r12
0x18000edd5  mov     rcx, cs:qword_1836E89C8
0x18000eddc  mov     r8, r13
0x18000eddf  mov     r9, r14
0x18000ede2  mov     [rax+20h], rdi
0x18000ede6  mov     qword ptr [rax+28h], 0
0x18000edee  mov     [rax+30h], rbp
0x18000edf2  call    cs:qword_1836E89E8
0x18000edf8  mov     edx, 0FFFFFFFFh
0x18000edfd  test    eax, eax
0x18000edff  cmovl   eax, edx
0x18000ee02  add     rsp, 0A8h
0x18000ee09  pop     rbp
0x18000ee0a  pop     r15
0x18000ee0c  pop     r14
0x18000ee0e  pop     r13
0x18000ee10  pop     r12
0x18000ee12  pop     rdi
0x18000ee13  retn
0x18000ee14  call    sub_18000E560
0x18000ee19  mov     eax, cs:dword_1836D0DF0
0x18000ee1f  cmp     eax, 0FFFFFFFFh
0x18000ee22  jz      short loc_18000EE2E
0x18000ee24  call    sub_18000E580
0x18000ee29  jmp     loc_18000ED74
0x18000ee2e  lea     rax, aAppcrt140Dll; "APPCRT140.DLL"
0x18000ee35  lea     r10, aAppcrt140dDll; "APPCRT140D.DLL"
0x18000ee3c  lea     r11, aUcrtbaseDll; "UCRTBASE.DLL"
0x18000ee43  lea     r15, aUcrtbasedDll; "UCRTBASED.DLL"
0x18000ee4a  mov     [rsp+0D8h+lpModuleName], rax
0x18000ee4f  mov     [rsp+0D8h+var_90], r10
0x18000ee54  mov     [rsp+0D8h+var_88], r11
0x18000ee59  mov     [rsp+0D8h+var_80], r15
0x18000ee5e  xor     r15d, r15d
0x18000ee61  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpModuleName
0x18000ee66  call    cs:__imp_GetModuleHandleA
0x18000ee6c  test    rax, rax
0x18000ee6f  jnz     short loc_18000EE96
0x18000ee71  inc     r15
0x18000ee74  cmp     r15, 4
0x18000ee78  jb      short loc_18000EE61
0x18000ee7a  xor     r15d, r15d
0x18000ee7d  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpLibFileName
0x18000ee82  call    cs:__imp_LoadLibraryA
0x18000ee88  test    rax, rax
0x18000ee8b  jnz     short loc_18000EE96
0x18000ee8d  inc     r15
0x18000ee90  cmp     r15, 4
0x18000ee94  jb      short loc_18000EE7D
0x18000ee96  mov     r15, rax
0x18000ee99  test    r15, r15
0x18000ee9c  jz      loc_18000EF5D
0x18000eea2  mov     rcx, r15; hModule
0x18000eea5  lea     rdx, aStdioCommonVss; "__stdio_common_vsscanf"
0x18000eeac  call    cs:__imp_GetProcAddress
0x18000eeb2  mov     cs:qword_1836E89D8, rax
0x18000eeb9  test    rax, rax
0x18000eebc  jz      loc_18000EF5D
0x18000eec2  mov     rcx, r15; hModule
0x18000eec5  lea     rdx, aStdioCommonVfs; "__stdio_common_vfscanf"
0x18000eecc  call    cs:__imp_GetProcAddress
0x18000eed2  mov     cs:qword_1836E89E0, rax
0x18000eed9  test    rax, rax
0x18000eedc  jz      short loc_18000EF5D
0x18000eede  mov     rcx, r15; hModule
0x18000eee1  lea     rdx, aStdioCommonVsn; "__stdio_common_vsnprintf_s"
0x18000eee8  call    cs:__imp_GetProcAddress
0x18000eeee  mov     cs:qword_1836E89E8, rax
0x18000eef5  test    rax, rax
0x18000eef8  jz      short loc_18000EF5D
0x18000eefa  mov     rcx, r15; hModule
0x18000eefd  lea     rdx, aStdioCommonVfp; "__stdio_common_vfprintf_s"
0x18000ef04  call    cs:__imp_GetProcAddress
0x18000ef0a  mov     cs:qword_1836E89D0, rax
0x18000ef11  test    rax, rax
0x18000ef14  jz      short loc_18000EF5D
0x18000ef16  mov     rcx, r15; hModule
0x18000ef19  lea     rdx, aAcrtIobFunc; "__acrt_iob_func"
0x18000ef20  call    cs:__imp_GetProcAddress
0x18000ef26  mov     cs:qword_1836E89F0, rax
0x18000ef2d  test    rax, rax
0x18000ef30  jz      short loc_18000EF5D
0x18000ef32  mov     rcx, r15; hModule
0x18000ef35  lea     rdx, aFflush; "fflush"
0x18000ef3c  call    cs:__imp_GetProcAddress
0x18000ef42  mov     cs:qword_1836E89C0, rax
0x18000ef49  test    rax, rax
0x18000ef4c  jz      short loc_18000EF5D
0x18000ef4e  mov     cs:dword_1836D0DF0, 2
0x18000ef58  jmp     loc_18000EE24
0x18000ef5d  lea     rax, aMsvcr120Dll; "MSVCR120.DLL"
0x18000ef64  lea     r10, aMsvcr120dDll; "MSVCR120D.DLL"
0x18000ef6b  mov     [rsp+0D8h+lpModuleName], rax
0x18000ef70  lea     rax, aMsvcr100Dll; "MSVCR100.DLL"
0x18000ef77  mov     [rsp+0D8h+var_78], rax
0x18000ef7c  lea     rax, aMsvcr100dDll; "MSVCR100D.DLL"
0x18000ef83  mov     [rsp+0D8h+var_70], rax
0x18000ef88  lea     rax, aMsvcr90Dll; "MSVCR90.DLL"
0x18000ef8f  mov     [rsp+0D8h+var_68], rax
0x18000ef94  lea     rax, aMsvcr90dDll; "MSVCR90D.DLL"
0x18000ef9b  mov     [rsp+0D8h+var_60], rax
0x18000efa0  lea     rax, aMsvcr80Dll; "MSVCR80.DLL"
0x18000efa7  mov     [rsp+0D8h+var_58], rax
0x18000efaf  lea     rax, aMsvcr80dDll; "MSVCR80D.DLL"
0x18000efb6  mov     [rsp+0D8h+var_50], rax
0x18000efbe  lea     rax, aMsvcrtDll; "MSVCRT.DLL"
0x18000efc5  mov     [rsp+0D8h+var_48], rax
0x18000efcd  lea     r11, aMsvcr110Dll; "MSVCR110.DLL"
0x18000efd4  lea     r15, aMsvcr110dDll; "MSVCR110D.DLL"
0x18000efdb  lea     rax, aMsvcrtdDll; "MSVCRTD.DLL"
0x18000efe2  mov     [rsp+0D8h+var_90], r10
0x18000efe7  mov     [rsp+0D8h+var_88], r11
0x18000efec  mov     [rsp+0D8h+var_80], r15
0x18000eff1  xor     r15d, r15d
0x18000eff4  mov     [rsp+0D8h+var_40], rax
0x18000effc  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpModuleName
0x18000f001  call    cs:__imp_GetModuleHandleA
0x18000f007  test    rax, rax
0x18000f00a  jnz     short loc_18000F031
0x18000f00c  inc     r15
0x18000f00f  cmp     r15, 0Ch
0x18000f013  jb      short loc_18000EFFC
0x18000f015  xor     r15d, r15d
0x18000f018  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpLibFileName
0x18000f01d  call    cs:__imp_LoadLibraryA
0x18000f023  test    rax, rax
0x18000f026  jnz     short loc_18000F031
0x18000f028  inc     r15
0x18000f02b  cmp     r15, 0Ch
0x18000f02f  jb      short loc_18000F018
0x18000f031  mov     r15, rax
0x18000f034  test    r15, r15
0x18000f037  jz      loc_18000EE24
0x18000f03d  mov     rcx, r15; hModule
0x18000f040  lea     rdx, aSscanf; "sscanf"
0x18000f047  call    cs:__imp_GetProcAddress
0x18000f04d  mov     cs:qword_1836E89F8, rax
0x18000f054  test    rax, rax
0x18000f057  jz      loc_18000EE24
0x18000f05d  mov     rcx, r15; hModule
0x18000f060  lea     rdx, aFscanf; "fscanf"
0x18000f067  call    cs:__imp_GetProcAddress
0x18000f06d  mov     cs:qword_1836E8A00, rax
0x18000f074  test    rax, rax
0x18000f077  jz      loc_18000EE24
0x18000f07d  mov     rcx, r15; hModule
0x18000f080  lea     rdx, aVfprintfS; "vfprintf_s"
0x18000f087  call    cs:__imp_GetProcAddress
0x18000f08d  mov     cs:qword_1836E89B8, rax
0x18000f094  test    rax, rax
0x18000f097  jz      loc_18000EE24
0x18000f09d  mov     rcx, r15; hModule
0x18000f0a0  lea     rdx, aVsnprintfS; "_vsnprintf_s"
0x18000f0a7  call    cs:__imp_GetProcAddress
0x18000f0ad  mov     cs:qword_1836E8A08, rax
0x18000f0b4  test    rax, rax
0x18000f0b7  jz      loc_18000EE24
0x18000f0bd  mov     rcx, r15; hModule
0x18000f0c0  lea     rdx, aIobFunc; "__iob_func"
0x18000f0c7  call    cs:__imp_GetProcAddress
0x18000f0cd  mov     cs:qword_1836E8A10, rax
0x18000f0d4  test    rax, rax
0x18000f0d7  jz      loc_18000EE24
0x18000f0dd  mov     rcx, r15; hModule
0x18000f0e0  lea     rdx, aFflush; "fflush"
0x18000f0e7  call    cs:__imp_GetProcAddress
0x18000f0ed  mov     cs:qword_1836E89C0, rax
0x18000f0f4  test    rax, rax
0x18000f0f7  jz      loc_18000EE24
0x18000f0fd  mov     cs:dword_1836D0DF0, 1
0x18000f107  jmp     loc_18000EE24
```
