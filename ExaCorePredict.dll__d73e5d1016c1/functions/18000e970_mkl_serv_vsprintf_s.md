# mkl_serv_vsprintf_s

- ea: `0x18000e970`
- end: `0x18000ed40`
- name: `mkl_serv_vsprintf_s`
- size: `976`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053c30`
- `0x180053cf0`

## callees

- `0x18000e560`
- `0x18000e580`
- `0x18000e970`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18000ea8d`
- `KERNEL32!GetModuleHandleA` at `0x18000ec28`
- `KERNEL32!GetModuleHandleA` at `0x18000ea8d`
- `KERNEL32!GetModuleHandleA` at `0x18000ec28`
- `KERNEL32!GetProcAddress` at `0x18000ead3`
- `KERNEL32!GetProcAddress` at `0x18000eaf3`
- `KERNEL32!GetProcAddress` at `0x18000eb0f`
- `KERNEL32!GetProcAddress` at `0x18000eb2b`
- `KERNEL32!GetProcAddress` at `0x18000eb47`
- `KERNEL32!GetProcAddress` at `0x18000eb63`
- `KERNEL32!GetProcAddress` at `0x18000ec6e`
- `KERNEL32!GetProcAddress` at `0x18000ec8e`
- `KERNEL32!GetProcAddress` at `0x18000ecae`
- `KERNEL32!GetProcAddress` at `0x18000ecce`
- `KERNEL32!GetProcAddress` at `0x18000ecee`
- `KERNEL32!GetProcAddress` at `0x18000ed0e`
- `KERNEL32!GetProcAddress` at `0x18000ead3`
- `KERNEL32!GetProcAddress` at `0x18000eaf3`
- `KERNEL32!GetProcAddress` at `0x18000eb0f`
- `KERNEL32!GetProcAddress` at `0x18000eb2b`
- `KERNEL32!GetProcAddress` at `0x18000eb47`
- `KERNEL32!GetProcAddress` at `0x18000eb63`
- `KERNEL32!GetProcAddress` at `0x18000ec6e`
- `KERNEL32!GetProcAddress` at `0x18000ec8e`
- `KERNEL32!GetProcAddress` at `0x18000ecae`
- `KERNEL32!GetProcAddress` at `0x18000ecce`
- `KERNEL32!GetProcAddress` at `0x18000ecee`
- `KERNEL32!GetProcAddress` at `0x18000ed0e`
- `KERNEL32!LoadLibraryA` at `0x18000eaa9`
- `KERNEL32!LoadLibraryA` at `0x18000ec44`
- `KERNEL32!LoadLibraryA` at `0x18000eaa9`
- `KERNEL32!LoadLibraryA` at `0x18000ec44`

## string_xrefs

- `0x18000eb84`: `MSVCR120.DLL`
- `0x18000eb8b`: `MSVCR120D.DLL`
- `0x18000ebf4`: `MSVCR110.DLL`
- `0x18000ebfb`: `MSVCR110D.DLL`
- `0x18000eb97`: `MSVCR100.DLL`
- `0x18000eba3`: `MSVCR100D.DLL`
- `0x18000ebaf`: `MSVCR90.DLL`
- `0x18000ebbb`: `MSVCR90D.DLL`
- `0x18000ebc7`: `MSVCR80.DLL`
- `0x18000ebd6`: `MSVCR80D.DLL`
- `0x18000ebe5`: `MSVCRT.DLL`
- `0x18000ec02`: `MSVCRTD.DLL`
- `0x18000ea55`: `APPCRT140.DLL`
- `0x18000ea5c`: `APPCRT140D.DLL`
- `0x18000ea63`: `UCRTBASE.DLL`
- `0x18000ea6a`: `UCRTBASED.DLL`
- `0x18000eacc`: `__stdio_common_vsscanf`
- `0x18000eaec`: `__stdio_common_vfscanf`
- `0x18000eb08`: `__stdio_common_vsnprintf_s`
- `0x18000eb24`: `__stdio_common_vfprintf_s`

## pseudocode

```c
__int64 __fastcall mkl_serv_vsprintf_s(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v9; // r15
  HMODULE ModuleHandleA; // rax
  unsigned __int64 i; // r15
  HMODULE v12; // r15
  __int64 v13; // r15
  HMODULE LibraryA; // rax
  unsigned __int64 j; // r15
  HMODULE v16; // r15
  LPCSTR lpModuleName; // [rsp+40h] [rbp-88h]
  const char *v18; // [rsp+48h] [rbp-80h]
  const char *v19; // [rsp+50h] [rbp-78h]
  const char *v20; // [rsp+58h] [rbp-70h]
  const char *v21; // [rsp+60h] [rbp-68h]
  const char *v22; // [rsp+68h] [rbp-60h]
  const char *v23; // [rsp+70h] [rbp-58h]
  const char *v24; // [rsp+78h] [rbp-50h]
  const char *v25; // [rsp+80h] [rbp-48h]
  const char *v26; // [rsp+88h] [rbp-40h]
  const char *v27; // [rsp+90h] [rbp-38h]
  const char *v28; // [rsp+98h] [rbp-30h]

  if ( dword_1836D0DF0 == -1 )
  {
    sub_18000E560();
    if ( dword_1836D0DF0 == -1 )
    {
      lpModuleName = "APPCRT140.DLL";
      v18 = "APPCRT140D.DLL";
      v19 = "UCRTBASE.DLL";
      v20 = "UCRTBASED.DLL";
      v9 = 0;
      while ( 1 )
      {
        ModuleHandleA = GetModuleHandleA((&lpModuleName)[v9]);
        if ( ModuleHandleA )
          break;
        if ( (unsigned __int64)++v9 >= 4 )
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
      v12 = ModuleHandleA;
      if ( ModuleHandleA
        && (qword_1836E89D8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(ModuleHandleA, "__stdio_common_vsscanf")) != 0
        && (qword_1836E89E0 = (__int64)GetProcAddress(v12, "__stdio_common_vfscanf")) != 0
        && (qword_1836E89E8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(v12, "__stdio_common_vsnprintf_s")) != 0
        && (qword_1836E89D0 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                v12,
                                                                                                "__stdio_common_vfprintf_s")) != 0
        && (qword_1836E89F0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v12, "__acrt_iob_func")) != 0
        && (qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v12, "fflush")) != 0 )
      {
        dword_1836D0DF0 = 2;
      }
      else
      {
        lpModuleName = "MSVCR120.DLL";
        v21 = "MSVCR100.DLL";
        v22 = "MSVCR100D.DLL";
        v23 = "MSVCR90.DLL";
        v24 = "MSVCR90D.DLL";
        v25 = "MSVCR80.DLL";
        v26 = "MSVCR80D.DLL";
        v27 = "MSVCRT.DLL";
        v18 = "MSVCR120D.DLL";
        v19 = "MSVCR110.DLL";
        v20 = "MSVCR110D.DLL";
        v13 = 0;
        v28 = "MSVCRTD.DLL";
        while ( 1 )
        {
          LibraryA = GetModuleHandleA((&lpModuleName)[v13]);
          if ( LibraryA )
            break;
          if ( (unsigned __int64)++v13 >= 0xC )
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
        v16 = LibraryA;
        if ( LibraryA )
        {
          qword_1836E89F8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(LibraryA, "sscanf");
          if ( qword_1836E89F8 )
          {
            qword_1836E8A00 = (__int64)GetProcAddress(v16, "fscanf");
            if ( qword_1836E8A00 )
            {
              qword_1836E89B8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(v16, "vfprintf_s");
              if ( qword_1836E89B8 )
              {
                qword_1836E8A08 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                    v16,
                                                                                                    "_vsnprintf_s");
                if ( qword_1836E8A08 )
                {
                  qword_1836E8A10 = GetProcAddress(v16, "__iob_func");
                  if ( qword_1836E8A10 )
                  {
                    qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v16, "fflush");
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
    result = qword_1836E89E8(qword_1836E89C8, a1, a2, 0x7FFFFFFF, a3, 0, a4);
    if ( (int)result < 0 )
      return 0xFFFFFFFFLL;
  }
  else if ( dword_1836D0DF0 == 1 )
  {
    return qword_1836E8A08(a1, a2, 0x7FFFFFFF, a3, a4);
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
0x18000e970  push    r12
0x18000e972  push    r13
0x18000e974  push    r14
0x18000e976  push    r15
0x18000e978  push    rbp
0x18000e979  sub     rsp, 0A0h
0x18000e980  mov     r14, r9
0x18000e983  mov     eax, cs:dword_1836D0DF0
0x18000e989  mov     r13, r8
0x18000e98c  mov     r12, rdx
0x18000e98f  mov     rbp, rcx
0x18000e992  cmp     eax, 0FFFFFFFFh
0x18000e995  jz      loc_18000EA3B
0x18000e99b  mov     eax, cs:dword_1836D0DF0
0x18000e9a1  cmp     eax, 2
0x18000e9a4  jz      short loc_18000E9F4
0x18000e9a6  mov     eax, cs:dword_1836D0DF0
0x18000e9ac  cmp     eax, 1
0x18000e9af  jz      short loc_18000E9C7
0x18000e9b1  mov     eax, 0FFFFFFFFh
0x18000e9b6  add     rsp, 0A0h
0x18000e9bd  pop     rbp
0x18000e9be  pop     r15
0x18000e9c0  pop     r14
0x18000e9c2  pop     r13
0x18000e9c4  pop     r12
0x18000e9c6  retn
0x18000e9c7  mov     rax, rsp
0x18000e9ca  mov     rcx, rbp
0x18000e9cd  mov     rdx, r12
0x18000e9d0  mov     r8d, 7FFFFFFFh
0x18000e9d6  mov     r9, r13
0x18000e9d9  mov     [rax+20h], r14
0x18000e9dd  call    cs:qword_1836E8A08
0x18000e9e3  add     rsp, 0A0h
0x18000e9ea  pop     rbp
0x18000e9eb  pop     r15
0x18000e9ed  pop     r14
0x18000e9ef  pop     r13
0x18000e9f1  pop     r12
0x18000e9f3  retn
0x18000e9f4  mov     rax, rsp
0x18000e9f7  mov     rdx, rbp
0x18000e9fa  mov     rcx, cs:qword_1836E89C8
0x18000ea01  mov     r8, r12
0x18000ea04  mov     r9d, 7FFFFFFFh
0x18000ea0a  mov     [rax+20h], r13
0x18000ea0e  mov     qword ptr [rax+28h], 0
0x18000ea16  mov     [rax+30h], r14
0x18000ea1a  call    cs:qword_1836E89E8
0x18000ea20  mov     edx, 0FFFFFFFFh
0x18000ea25  test    eax, eax
0x18000ea27  cmovl   eax, edx
0x18000ea2a  add     rsp, 0A0h
0x18000ea31  pop     rbp
0x18000ea32  pop     r15
0x18000ea34  pop     r14
0x18000ea36  pop     r13
0x18000ea38  pop     r12
0x18000ea3a  retn
0x18000ea3b  call    sub_18000E560
0x18000ea40  mov     eax, cs:dword_1836D0DF0
0x18000ea46  cmp     eax, 0FFFFFFFFh
0x18000ea49  jz      short loc_18000EA55
0x18000ea4b  call    sub_18000E580
0x18000ea50  jmp     loc_18000E99B
0x18000ea55  lea     rax, aAppcrt140Dll; "APPCRT140.DLL"
0x18000ea5c  lea     r10, aAppcrt140dDll; "APPCRT140D.DLL"
0x18000ea63  lea     r11, aUcrtbaseDll; "UCRTBASE.DLL"
0x18000ea6a  lea     r15, aUcrtbasedDll; "UCRTBASED.DLL"
0x18000ea71  mov     [rsp+0C8h+lpModuleName], rax
0x18000ea76  mov     [rsp+0C8h+var_80], r10
0x18000ea7b  mov     [rsp+0C8h+var_78], r11
0x18000ea80  mov     [rsp+0C8h+var_70], r15
0x18000ea85  xor     r15d, r15d
0x18000ea88  mov     rcx, [rsp+r15*8+0C8h+lpModuleName]; lpModuleName
0x18000ea8d  call    cs:__imp_GetModuleHandleA
0x18000ea93  test    rax, rax
0x18000ea96  jnz     short loc_18000EABD
0x18000ea98  inc     r15
0x18000ea9b  cmp     r15, 4
0x18000ea9f  jb      short loc_18000EA88
0x18000eaa1  xor     r15d, r15d
0x18000eaa4  mov     rcx, [rsp+r15*8+0C8h+lpModuleName]; lpLibFileName
0x18000eaa9  call    cs:__imp_LoadLibraryA
0x18000eaaf  test    rax, rax
0x18000eab2  jnz     short loc_18000EABD
0x18000eab4  inc     r15
0x18000eab7  cmp     r15, 4
0x18000eabb  jb      short loc_18000EAA4
0x18000eabd  mov     r15, rax
0x18000eac0  test    r15, r15
0x18000eac3  jz      loc_18000EB84
0x18000eac9  mov     rcx, r15; hModule
0x18000eacc  lea     rdx, aStdioCommonVss; "__stdio_common_vsscanf"
0x18000ead3  call    cs:__imp_GetProcAddress
0x18000ead9  mov     cs:qword_1836E89D8, rax
0x18000eae0  test    rax, rax
0x18000eae3  jz      loc_18000EB84
0x18000eae9  mov     rcx, r15; hModule
0x18000eaec  lea     rdx, aStdioCommonVfs; "__stdio_common_vfscanf"
0x18000eaf3  call    cs:__imp_GetProcAddress
0x18000eaf9  mov     cs:qword_1836E89E0, rax
0x18000eb00  test    rax, rax
0x18000eb03  jz      short loc_18000EB84
0x18000eb05  mov     rcx, r15; hModule
0x18000eb08  lea     rdx, aStdioCommonVsn; "__stdio_common_vsnprintf_s"
0x18000eb0f  call    cs:__imp_GetProcAddress
0x18000eb15  mov     cs:qword_1836E89E8, rax
0x18000eb1c  test    rax, rax
0x18000eb1f  jz      short loc_18000EB84
0x18000eb21  mov     rcx, r15; hModule
0x18000eb24  lea     rdx, aStdioCommonVfp; "__stdio_common_vfprintf_s"
0x18000eb2b  call    cs:__imp_GetProcAddress
0x18000eb31  mov     cs:qword_1836E89D0, rax
0x18000eb38  test    rax, rax
0x18000eb3b  jz      short loc_18000EB84
0x18000eb3d  mov     rcx, r15; hModule
0x18000eb40  lea     rdx, aAcrtIobFunc; "__acrt_iob_func"
0x18000eb47  call    cs:__imp_GetProcAddress
0x18000eb4d  mov     cs:qword_1836E89F0, rax
0x18000eb54  test    rax, rax
0x18000eb57  jz      short loc_18000EB84
0x18000eb59  mov     rcx, r15; hModule
0x18000eb5c  lea     rdx, aFflush; "fflush"
0x18000eb63  call    cs:__imp_GetProcAddress
0x18000eb69  mov     cs:qword_1836E89C0, rax
0x18000eb70  test    rax, rax
0x18000eb73  jz      short loc_18000EB84
0x18000eb75  mov     cs:dword_1836D0DF0, 2
0x18000eb7f  jmp     loc_18000EA4B
0x18000eb84  lea     rax, aMsvcr120Dll; "MSVCR120.DLL"
0x18000eb8b  lea     r10, aMsvcr120dDll; "MSVCR120D.DLL"
0x18000eb92  mov     [rsp+0C8h+lpModuleName], rax
0x18000eb97  lea     rax, aMsvcr100Dll; "MSVCR100.DLL"
0x18000eb9e  mov     [rsp+0C8h+var_68], rax
0x18000eba3  lea     rax, aMsvcr100dDll; "MSVCR100D.DLL"
0x18000ebaa  mov     [rsp+0C8h+var_60], rax
0x18000ebaf  lea     rax, aMsvcr90Dll; "MSVCR90.DLL"
0x18000ebb6  mov     [rsp+0C8h+var_58], rax
0x18000ebbb  lea     rax, aMsvcr90dDll; "MSVCR90D.DLL"
0x18000ebc2  mov     [rsp+0C8h+var_50], rax
0x18000ebc7  lea     rax, aMsvcr80Dll; "MSVCR80.DLL"
0x18000ebce  mov     [rsp+0C8h+var_48], rax
0x18000ebd6  lea     rax, aMsvcr80dDll; "MSVCR80D.DLL"
0x18000ebdd  mov     [rsp+0C8h+var_40], rax
0x18000ebe5  lea     rax, aMsvcrtDll; "MSVCRT.DLL"
0x18000ebec  mov     [rsp+0C8h+var_38], rax
0x18000ebf4  lea     r11, aMsvcr110Dll; "MSVCR110.DLL"
0x18000ebfb  lea     r15, aMsvcr110dDll; "MSVCR110D.DLL"
0x18000ec02  lea     rax, aMsvcrtdDll; "MSVCRTD.DLL"
0x18000ec09  mov     [rsp+0C8h+var_80], r10
0x18000ec0e  mov     [rsp+0C8h+var_78], r11
0x18000ec13  mov     [rsp+0C8h+var_70], r15
0x18000ec18  xor     r15d, r15d
0x18000ec1b  mov     [rsp+0C8h+var_30], rax
0x18000ec23  mov     rcx, [rsp+r15*8+0C8h+lpModuleName]; lpModuleName
0x18000ec28  call    cs:__imp_GetModuleHandleA
0x18000ec2e  test    rax, rax
0x18000ec31  jnz     short loc_18000EC58
0x18000ec33  inc     r15
0x18000ec36  cmp     r15, 0Ch
0x18000ec3a  jb      short loc_18000EC23
0x18000ec3c  xor     r15d, r15d
0x18000ec3f  mov     rcx, [rsp+r15*8+0C8h+lpModuleName]; lpLibFileName
0x18000ec44  call    cs:__imp_LoadLibraryA
0x18000ec4a  test    rax, rax
0x18000ec4d  jnz     short loc_18000EC58
0x18000ec4f  inc     r15
0x18000ec52  cmp     r15, 0Ch
0x18000ec56  jb      short loc_18000EC3F
0x18000ec58  mov     r15, rax
0x18000ec5b  test    r15, r15
0x18000ec5e  jz      loc_18000EA4B
0x18000ec64  mov     rcx, r15; hModule
0x18000ec67  lea     rdx, aSscanf; "sscanf"
0x18000ec6e  call    cs:__imp_GetProcAddress
0x18000ec74  mov     cs:qword_1836E89F8, rax
0x18000ec7b  test    rax, rax
0x18000ec7e  jz      loc_18000EA4B
0x18000ec84  mov     rcx, r15; hModule
0x18000ec87  lea     rdx, aFscanf; "fscanf"
0x18000ec8e  call    cs:__imp_GetProcAddress
0x18000ec94  mov     cs:qword_1836E8A00, rax
0x18000ec9b  test    rax, rax
0x18000ec9e  jz      loc_18000EA4B
0x18000eca4  mov     rcx, r15; hModule
0x18000eca7  lea     rdx, aVfprintfS; "vfprintf_s"
0x18000ecae  call    cs:__imp_GetProcAddress
0x18000ecb4  mov     cs:qword_1836E89B8, rax
0x18000ecbb  test    rax, rax
0x18000ecbe  jz      loc_18000EA4B
0x18000ecc4  mov     rcx, r15; hModule
0x18000ecc7  lea     rdx, aVsnprintfS; "_vsnprintf_s"
0x18000ecce  call    cs:__imp_GetProcAddress
0x18000ecd4  mov     cs:qword_1836E8A08, rax
0x18000ecdb  test    rax, rax
0x18000ecde  jz      loc_18000EA4B
0x18000ece4  mov     rcx, r15; hModule
0x18000ece7  lea     rdx, aIobFunc; "__iob_func"
0x18000ecee  call    cs:__imp_GetProcAddress
0x18000ecf4  mov     cs:qword_1836E8A10, rax
0x18000ecfb  test    rax, rax
0x18000ecfe  jz      loc_18000EA4B
0x18000ed04  mov     rcx, r15; hModule
0x18000ed07  lea     rdx, aFflush; "fflush"
0x18000ed0e  call    cs:__imp_GetProcAddress
0x18000ed14  mov     cs:qword_1836E89C0, rax
0x18000ed1b  test    rax, rax
0x18000ed1e  jz      loc_18000EA4B
0x18000ed24  mov     cs:dword_1836D0DF0, 1
0x18000ed2e  jmp     loc_18000EA4B
```
