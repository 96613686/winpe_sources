# mkl_serv_sprintf_s

- ea: `0x18000e590`
- end: `0x18000e970`
- name: `mkl_serv_sprintf_s`
- size: `992`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bb30`
- `0x180053cf0`
- `0x180453fc0`

## callees

- `0x18000e560`
- `0x18000e580`
- `0x18000e590`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18000e6c0`
- `KERNEL32!GetModuleHandleA` at `0x18000e85b`
- `KERNEL32!GetModuleHandleA` at `0x18000e6c0`
- `KERNEL32!GetModuleHandleA` at `0x18000e85b`
- `KERNEL32!GetProcAddress` at `0x18000e706`
- `KERNEL32!GetProcAddress` at `0x18000e726`
- `KERNEL32!GetProcAddress` at `0x18000e742`
- `KERNEL32!GetProcAddress` at `0x18000e75e`
- `KERNEL32!GetProcAddress` at `0x18000e77a`
- `KERNEL32!GetProcAddress` at `0x18000e796`
- `KERNEL32!GetProcAddress` at `0x18000e8a1`
- `KERNEL32!GetProcAddress` at `0x18000e8c1`
- `KERNEL32!GetProcAddress` at `0x18000e8e1`
- `KERNEL32!GetProcAddress` at `0x18000e901`
- `KERNEL32!GetProcAddress` at `0x18000e921`
- `KERNEL32!GetProcAddress` at `0x18000e941`
- `KERNEL32!GetProcAddress` at `0x18000e706`
- `KERNEL32!GetProcAddress` at `0x18000e726`
- `KERNEL32!GetProcAddress` at `0x18000e742`
- `KERNEL32!GetProcAddress` at `0x18000e75e`
- `KERNEL32!GetProcAddress` at `0x18000e77a`
- `KERNEL32!GetProcAddress` at `0x18000e796`
- `KERNEL32!GetProcAddress` at `0x18000e8a1`
- `KERNEL32!GetProcAddress` at `0x18000e8c1`
- `KERNEL32!GetProcAddress` at `0x18000e8e1`
- `KERNEL32!GetProcAddress` at `0x18000e901`
- `KERNEL32!GetProcAddress` at `0x18000e921`
- `KERNEL32!GetProcAddress` at `0x18000e941`
- `KERNEL32!LoadLibraryA` at `0x18000e6dc`
- `KERNEL32!LoadLibraryA` at `0x18000e877`
- `KERNEL32!LoadLibraryA` at `0x18000e6dc`
- `KERNEL32!LoadLibraryA` at `0x18000e877`

## string_xrefs

- `0x18000e7b7`: `MSVCR120.DLL`
- `0x18000e7be`: `MSVCR120D.DLL`
- `0x18000e827`: `MSVCR110.DLL`
- `0x18000e82e`: `MSVCR110D.DLL`
- `0x18000e7ca`: `MSVCR100.DLL`
- `0x18000e7d6`: `MSVCR100D.DLL`
- `0x18000e7e2`: `MSVCR90.DLL`
- `0x18000e7ee`: `MSVCR90D.DLL`
- `0x18000e7fa`: `MSVCR80.DLL`
- `0x18000e809`: `MSVCR80D.DLL`
- `0x18000e818`: `MSVCRT.DLL`
- `0x18000e835`: `MSVCRTD.DLL`
- `0x18000e688`: `APPCRT140.DLL`
- `0x18000e68f`: `APPCRT140D.DLL`
- `0x18000e696`: `UCRTBASE.DLL`
- `0x18000e69d`: `UCRTBASED.DLL`
- `0x18000e6ff`: `__stdio_common_vsscanf`
- `0x18000e71f`: `__stdio_common_vfscanf`
- `0x18000e73b`: `__stdio_common_vsnprintf_s`
- `0x18000e757`: `__stdio_common_vfprintf_s`

## pseudocode

```c
__int64 mkl_serv_sprintf_s(__int64 a1, __int64 a2, __int64 a3, ...)
{
  __int64 result; // rax
  __int64 v7; // r15
  HMODULE ModuleHandleA; // rax
  unsigned __int64 i; // r15
  HMODULE v10; // r15
  __int64 v11; // r15
  HMODULE LibraryA; // rax
  unsigned __int64 j; // r15
  HMODULE v14; // r15
  LPCSTR lpModuleName; // [rsp+40h] [rbp-98h]
  const char *v16; // [rsp+48h] [rbp-90h]
  const char *v17; // [rsp+50h] [rbp-88h]
  const char *v18; // [rsp+58h] [rbp-80h]
  const char *v19; // [rsp+60h] [rbp-78h]
  const char *v20; // [rsp+68h] [rbp-70h]
  const char *v21; // [rsp+70h] [rbp-68h]
  const char *v22; // [rsp+78h] [rbp-60h]
  const char *v23; // [rsp+80h] [rbp-58h]
  const char *v24; // [rsp+88h] [rbp-50h]
  const char *v25; // [rsp+90h] [rbp-48h]
  const char *v26; // [rsp+98h] [rbp-40h]
  va_list v27; // [rsp+A0h] [rbp-38h]
  va_list va; // [rsp+F8h] [rbp+20h] BYREF

  va_start(va, a3);
  va_copy(v27, va);
  if ( dword_1836D0DF0 == -1 )
  {
    sub_18000E560();
    if ( dword_1836D0DF0 == -1 )
    {
      lpModuleName = "APPCRT140.DLL";
      v16 = "APPCRT140D.DLL";
      v17 = "UCRTBASE.DLL";
      v18 = "UCRTBASED.DLL";
      v7 = 0;
      while ( 1 )
      {
        ModuleHandleA = GetModuleHandleA((&lpModuleName)[v7]);
        if ( ModuleHandleA )
          break;
        if ( (unsigned __int64)++v7 >= 4 )
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
      v10 = ModuleHandleA;
      if ( ModuleHandleA
        && (qword_1836E89D8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(ModuleHandleA, "__stdio_common_vsscanf")) != 0
        && (qword_1836E89E0 = (__int64)GetProcAddress(v10, "__stdio_common_vfscanf")) != 0
        && (qword_1836E89E8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(v10, "__stdio_common_vsnprintf_s")) != 0
        && (qword_1836E89D0 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                v10,
                                                                                                "__stdio_common_vfprintf_s")) != 0
        && (qword_1836E89F0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v10, "__acrt_iob_func")) != 0
        && (qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v10, "fflush")) != 0 )
      {
        dword_1836D0DF0 = 2;
      }
      else
      {
        lpModuleName = "MSVCR120.DLL";
        v19 = "MSVCR100.DLL";
        v20 = "MSVCR100D.DLL";
        v21 = "MSVCR90.DLL";
        v22 = "MSVCR90D.DLL";
        v23 = "MSVCR80.DLL";
        v24 = "MSVCR80D.DLL";
        v25 = "MSVCRT.DLL";
        v16 = "MSVCR120D.DLL";
        v17 = "MSVCR110.DLL";
        v18 = "MSVCR110D.DLL";
        v11 = 0;
        v26 = "MSVCRTD.DLL";
        while ( 1 )
        {
          LibraryA = GetModuleHandleA((&lpModuleName)[v11]);
          if ( LibraryA )
            break;
          if ( (unsigned __int64)++v11 >= 0xC )
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
        v14 = LibraryA;
        if ( LibraryA )
        {
          qword_1836E89F8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(LibraryA, "sscanf");
          if ( qword_1836E89F8 )
          {
            qword_1836E8A00 = (__int64)GetProcAddress(v14, "fscanf");
            if ( qword_1836E8A00 )
            {
              qword_1836E89B8 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(v14, "vfprintf_s");
              if ( qword_1836E89B8 )
              {
                qword_1836E8A08 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                                    v14,
                                                                                                    "_vsnprintf_s");
                if ( qword_1836E8A08 )
                {
                  qword_1836E8A10 = GetProcAddress(v14, "__iob_func");
                  if ( qword_1836E8A10 )
                  {
                    qword_1836E89C0 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(v14, "fflush");
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
    result = qword_1836E89E8(qword_1836E89C8, a1, a2, 0x7FFFFFFF, a3, 0, va);
    if ( (int)result < 0 )
      result = 0xFFFFFFFFLL;
  }
  else if ( dword_1836D0DF0 == 1 )
  {
    result = qword_1836E8A08(a1, a2, 0x7FFFFFFF, a3, va);
  }
  else
  {
    result = 0xFFFFFFFFLL;
  }
  v27 = 0;
  return result;
}

```

## disassembly

```asm
0x18000e590  push    r12
0x18000e592  push    r13
0x18000e594  push    r14
0x18000e596  push    r15
0x18000e598  push    rbp
0x18000e599  sub     rsp, 0B0h
0x18000e5a0  mov     r14, rdx
0x18000e5a3  mov     [rsp+0D8h+arg_10], r8
0x18000e5ab  lea     rax, [rsp+0D8h+arg_18]
0x18000e5b3  mov     [rax], r9
0x18000e5b6  mov     r13, rcx
0x18000e5b9  mov     [rsp+0D8h+var_38], rax
0x18000e5c1  mov     eax, cs:dword_1836D0DF0
0x18000e5c7  cmp     eax, 0FFFFFFFFh
0x18000e5ca  mov     r12, [rsp+0D8h+arg_10]
0x18000e5d2  mov     rbp, [rsp+0D8h+var_38]
0x18000e5da  jz      loc_18000E66E
0x18000e5e0  mov     eax, cs:dword_1836D0DF0
0x18000e5e6  cmp     eax, 2
0x18000e5e9  jz      short loc_18000E636
0x18000e5eb  mov     eax, cs:dword_1836D0DF0
0x18000e5f1  cmp     eax, 1
0x18000e5f4  jz      short loc_18000E618
0x18000e5f6  mov     eax, 0FFFFFFFFh
0x18000e5fb  mov     [rsp+0D8h+var_38], 0
0x18000e607  add     rsp, 0B0h
0x18000e60e  pop     rbp
0x18000e60f  pop     r15
0x18000e611  pop     r14
0x18000e613  pop     r13
0x18000e615  pop     r12
0x18000e617  retn
0x18000e618  mov     rax, rsp
0x18000e61b  mov     rcx, r13
0x18000e61e  mov     rdx, r14
0x18000e621  mov     r8d, 7FFFFFFFh
0x18000e627  mov     r9, r12
0x18000e62a  mov     [rax+20h], rbp
0x18000e62e  call    cs:qword_1836E8A08
0x18000e634  jmp     short loc_18000E5FB
0x18000e636  mov     rax, rsp
0x18000e639  mov     rdx, r13
0x18000e63c  mov     rcx, cs:qword_1836E89C8
0x18000e643  mov     r8, r14
0x18000e646  mov     r9d, 7FFFFFFFh
0x18000e64c  mov     [rax+20h], r12
0x18000e650  mov     qword ptr [rax+28h], 0
0x18000e658  mov     [rax+30h], rbp
0x18000e65c  call    cs:qword_1836E89E8
0x18000e662  mov     edx, 0FFFFFFFFh
0x18000e667  test    eax, eax
0x18000e669  cmovl   eax, edx
0x18000e66c  jmp     short loc_18000E5FB
0x18000e66e  call    sub_18000E560
0x18000e673  mov     eax, cs:dword_1836D0DF0
0x18000e679  cmp     eax, 0FFFFFFFFh
0x18000e67c  jz      short loc_18000E688
0x18000e67e  call    sub_18000E580
0x18000e683  jmp     loc_18000E5E0
0x18000e688  lea     rax, aAppcrt140Dll; "APPCRT140.DLL"
0x18000e68f  lea     r10, aAppcrt140dDll; "APPCRT140D.DLL"
0x18000e696  lea     r11, aUcrtbaseDll; "UCRTBASE.DLL"
0x18000e69d  lea     r15, aUcrtbasedDll; "UCRTBASED.DLL"
0x18000e6a4  mov     [rsp+0D8h+lpModuleName], rax
0x18000e6a9  mov     [rsp+0D8h+var_90], r10
0x18000e6ae  mov     [rsp+0D8h+var_88], r11
0x18000e6b3  mov     [rsp+0D8h+var_80], r15
0x18000e6b8  xor     r15d, r15d
0x18000e6bb  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpModuleName
0x18000e6c0  call    cs:__imp_GetModuleHandleA
0x18000e6c6  test    rax, rax
0x18000e6c9  jnz     short loc_18000E6F0
0x18000e6cb  inc     r15
0x18000e6ce  cmp     r15, 4
0x18000e6d2  jb      short loc_18000E6BB
0x18000e6d4  xor     r15d, r15d
0x18000e6d7  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpLibFileName
0x18000e6dc  call    cs:__imp_LoadLibraryA
0x18000e6e2  test    rax, rax
0x18000e6e5  jnz     short loc_18000E6F0
0x18000e6e7  inc     r15
0x18000e6ea  cmp     r15, 4
0x18000e6ee  jb      short loc_18000E6D7
0x18000e6f0  mov     r15, rax
0x18000e6f3  test    r15, r15
0x18000e6f6  jz      loc_18000E7B7
0x18000e6fc  mov     rcx, r15; hModule
0x18000e6ff  lea     rdx, aStdioCommonVss; "__stdio_common_vsscanf"
0x18000e706  call    cs:__imp_GetProcAddress
0x18000e70c  mov     cs:qword_1836E89D8, rax
0x18000e713  test    rax, rax
0x18000e716  jz      loc_18000E7B7
0x18000e71c  mov     rcx, r15; hModule
0x18000e71f  lea     rdx, aStdioCommonVfs; "__stdio_common_vfscanf"
0x18000e726  call    cs:__imp_GetProcAddress
0x18000e72c  mov     cs:qword_1836E89E0, rax
0x18000e733  test    rax, rax
0x18000e736  jz      short loc_18000E7B7
0x18000e738  mov     rcx, r15; hModule
0x18000e73b  lea     rdx, aStdioCommonVsn; "__stdio_common_vsnprintf_s"
0x18000e742  call    cs:__imp_GetProcAddress
0x18000e748  mov     cs:qword_1836E89E8, rax
0x18000e74f  test    rax, rax
0x18000e752  jz      short loc_18000E7B7
0x18000e754  mov     rcx, r15; hModule
0x18000e757  lea     rdx, aStdioCommonVfp; "__stdio_common_vfprintf_s"
0x18000e75e  call    cs:__imp_GetProcAddress
0x18000e764  mov     cs:qword_1836E89D0, rax
0x18000e76b  test    rax, rax
0x18000e76e  jz      short loc_18000E7B7
0x18000e770  mov     rcx, r15; hModule
0x18000e773  lea     rdx, aAcrtIobFunc; "__acrt_iob_func"
0x18000e77a  call    cs:__imp_GetProcAddress
0x18000e780  mov     cs:qword_1836E89F0, rax
0x18000e787  test    rax, rax
0x18000e78a  jz      short loc_18000E7B7
0x18000e78c  mov     rcx, r15; hModule
0x18000e78f  lea     rdx, aFflush; "fflush"
0x18000e796  call    cs:__imp_GetProcAddress
0x18000e79c  mov     cs:qword_1836E89C0, rax
0x18000e7a3  test    rax, rax
0x18000e7a6  jz      short loc_18000E7B7
0x18000e7a8  mov     cs:dword_1836D0DF0, 2
0x18000e7b2  jmp     loc_18000E67E
0x18000e7b7  lea     rax, aMsvcr120Dll; "MSVCR120.DLL"
0x18000e7be  lea     r10, aMsvcr120dDll; "MSVCR120D.DLL"
0x18000e7c5  mov     [rsp+0D8h+lpModuleName], rax
0x18000e7ca  lea     rax, aMsvcr100Dll; "MSVCR100.DLL"
0x18000e7d1  mov     [rsp+0D8h+var_78], rax
0x18000e7d6  lea     rax, aMsvcr100dDll; "MSVCR100D.DLL"
0x18000e7dd  mov     [rsp+0D8h+var_70], rax
0x18000e7e2  lea     rax, aMsvcr90Dll; "MSVCR90.DLL"
0x18000e7e9  mov     [rsp+0D8h+var_68], rax
0x18000e7ee  lea     rax, aMsvcr90dDll; "MSVCR90D.DLL"
0x18000e7f5  mov     [rsp+0D8h+var_60], rax
0x18000e7fa  lea     rax, aMsvcr80Dll; "MSVCR80.DLL"
0x18000e801  mov     [rsp+0D8h+var_58], rax
0x18000e809  lea     rax, aMsvcr80dDll; "MSVCR80D.DLL"
0x18000e810  mov     [rsp+0D8h+var_50], rax
0x18000e818  lea     rax, aMsvcrtDll; "MSVCRT.DLL"
0x18000e81f  mov     [rsp+0D8h+var_48], rax
0x18000e827  lea     r11, aMsvcr110Dll; "MSVCR110.DLL"
0x18000e82e  lea     r15, aMsvcr110dDll; "MSVCR110D.DLL"
0x18000e835  lea     rax, aMsvcrtdDll; "MSVCRTD.DLL"
0x18000e83c  mov     [rsp+0D8h+var_90], r10
0x18000e841  mov     [rsp+0D8h+var_88], r11
0x18000e846  mov     [rsp+0D8h+var_80], r15
0x18000e84b  xor     r15d, r15d
0x18000e84e  mov     [rsp+0D8h+var_40], rax
0x18000e856  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpModuleName
0x18000e85b  call    cs:__imp_GetModuleHandleA
0x18000e861  test    rax, rax
0x18000e864  jnz     short loc_18000E88B
0x18000e866  inc     r15
0x18000e869  cmp     r15, 0Ch
0x18000e86d  jb      short loc_18000E856
0x18000e86f  xor     r15d, r15d
0x18000e872  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpLibFileName
0x18000e877  call    cs:__imp_LoadLibraryA
0x18000e87d  test    rax, rax
0x18000e880  jnz     short loc_18000E88B
0x18000e882  inc     r15
0x18000e885  cmp     r15, 0Ch
0x18000e889  jb      short loc_18000E872
0x18000e88b  mov     r15, rax
0x18000e88e  test    r15, r15
0x18000e891  jz      loc_18000E67E
0x18000e897  mov     rcx, r15; hModule
0x18000e89a  lea     rdx, aSscanf; "sscanf"
0x18000e8a1  call    cs:__imp_GetProcAddress
0x18000e8a7  mov     cs:qword_1836E89F8, rax
0x18000e8ae  test    rax, rax
0x18000e8b1  jz      loc_18000E67E
0x18000e8b7  mov     rcx, r15; hModule
0x18000e8ba  lea     rdx, aFscanf; "fscanf"
0x18000e8c1  call    cs:__imp_GetProcAddress
0x18000e8c7  mov     cs:qword_1836E8A00, rax
0x18000e8ce  test    rax, rax
0x18000e8d1  jz      loc_18000E67E
0x18000e8d7  mov     rcx, r15; hModule
0x18000e8da  lea     rdx, aVfprintfS; "vfprintf_s"
0x18000e8e1  call    cs:__imp_GetProcAddress
0x18000e8e7  mov     cs:qword_1836E89B8, rax
0x18000e8ee  test    rax, rax
0x18000e8f1  jz      loc_18000E67E
0x18000e8f7  mov     rcx, r15; hModule
0x18000e8fa  lea     rdx, aVsnprintfS; "_vsnprintf_s"
0x18000e901  call    cs:__imp_GetProcAddress
0x18000e907  mov     cs:qword_1836E8A08, rax
0x18000e90e  test    rax, rax
0x18000e911  jz      loc_18000E67E
0x18000e917  mov     rcx, r15; hModule
0x18000e91a  lea     rdx, aIobFunc; "__iob_func"
0x18000e921  call    cs:__imp_GetProcAddress
0x18000e927  mov     cs:qword_1836E8A10, rax
0x18000e92e  test    rax, rax
0x18000e931  jz      loc_18000E67E
0x18000e937  mov     rcx, r15; hModule
0x18000e93a  lea     rdx, aFflush; "fflush"
0x18000e941  call    cs:__imp_GetProcAddress
0x18000e947  mov     cs:qword_1836E89C0, rax
0x18000e94e  test    rax, rax
0x18000e951  jz      loc_18000E67E
0x18000e957  mov     cs:dword_1836D0DF0, 1
0x18000e961  jmp     loc_18000E67E
```
