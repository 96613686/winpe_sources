# mkl_serv_snprintf_s

- ea: `0x18000f110`
- end: `0x18000f4f0`
- name: `mkl_serv_snprintf_s`
- size: `992`
- prototype: ``
- caller_count: `34`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000125d`
- `0x1800016f2`
- `0x180001b0b`
- `0x180001f8d`
- `0x1800023cb`
- `0x1800025f0`
- `0x180002a30`
- `0x180002eb0`
- `0x180003460`
- `0x1800037b0`
- `0x180003b60`
- `0x180003e30`
- `0x180004080`
- `0x180004370`
- `0x1800046b0`
- `0x1800048d0`
- `0x180004ae0`
- `0x180004d90`
- `0x1800051d0`
- `0x180005650`
- `0x180005c00`
- `0x180005f50`
- `0x180006300`
- `0x1800065d0`
- `0x180006820`
- `0x180006b10`
- `0x180006e50`
- `0x180007070`
- `0x180007280`
- `0x1800602e0`
- `0x18012b630`
- `0x18012b7b0`
- `0x18012b920`
- `0x18012bb00`

## callees

- `0x18000e560`
- `0x18000e580`
- `0x18000f110`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x18000f23c`
- `KERNEL32!GetModuleHandleA` at `0x18000f3d7`
- `KERNEL32!GetModuleHandleA` at `0x18000f23c`
- `KERNEL32!GetModuleHandleA` at `0x18000f3d7`
- `KERNEL32!GetProcAddress` at `0x18000f282`
- `KERNEL32!GetProcAddress` at `0x18000f2a2`
- `KERNEL32!GetProcAddress` at `0x18000f2be`
- `KERNEL32!GetProcAddress` at `0x18000f2da`
- `KERNEL32!GetProcAddress` at `0x18000f2f6`
- `KERNEL32!GetProcAddress` at `0x18000f312`
- `KERNEL32!GetProcAddress` at `0x18000f41d`
- `KERNEL32!GetProcAddress` at `0x18000f43d`
- `KERNEL32!GetProcAddress` at `0x18000f45d`
- `KERNEL32!GetProcAddress` at `0x18000f47d`
- `KERNEL32!GetProcAddress` at `0x18000f49d`
- `KERNEL32!GetProcAddress` at `0x18000f4bd`
- `KERNEL32!GetProcAddress` at `0x18000f282`
- `KERNEL32!GetProcAddress` at `0x18000f2a2`
- `KERNEL32!GetProcAddress` at `0x18000f2be`
- `KERNEL32!GetProcAddress` at `0x18000f2da`
- `KERNEL32!GetProcAddress` at `0x18000f2f6`
- `KERNEL32!GetProcAddress` at `0x18000f312`
- `KERNEL32!GetProcAddress` at `0x18000f41d`
- `KERNEL32!GetProcAddress` at `0x18000f43d`
- `KERNEL32!GetProcAddress` at `0x18000f45d`
- `KERNEL32!GetProcAddress` at `0x18000f47d`
- `KERNEL32!GetProcAddress` at `0x18000f49d`
- `KERNEL32!GetProcAddress` at `0x18000f4bd`
- `KERNEL32!LoadLibraryA` at `0x18000f258`
- `KERNEL32!LoadLibraryA` at `0x18000f3f3`
- `KERNEL32!LoadLibraryA` at `0x18000f258`
- `KERNEL32!LoadLibraryA` at `0x18000f3f3`

## string_xrefs

- `0x18000f333`: `MSVCR120.DLL`
- `0x18000f33a`: `MSVCR120D.DLL`
- `0x18000f3a3`: `MSVCR110.DLL`
- `0x18000f3aa`: `MSVCR110D.DLL`
- `0x18000f346`: `MSVCR100.DLL`
- `0x18000f352`: `MSVCR100D.DLL`
- `0x18000f35e`: `MSVCR90.DLL`
- `0x18000f36a`: `MSVCR90D.DLL`
- `0x18000f376`: `MSVCR80.DLL`
- `0x18000f385`: `MSVCR80D.DLL`
- `0x18000f394`: `MSVCRT.DLL`
- `0x18000f3b1`: `MSVCRTD.DLL`
- `0x18000f204`: `APPCRT140.DLL`
- `0x18000f20b`: `APPCRT140D.DLL`
- `0x18000f212`: `UCRTBASE.DLL`
- `0x18000f219`: `UCRTBASED.DLL`
- `0x18000f27b`: `__stdio_common_vsscanf`
- `0x18000f29b`: `__stdio_common_vfscanf`
- `0x18000f2b7`: `__stdio_common_vsnprintf_s`
- `0x18000f2d3`: `__stdio_common_vfprintf_s`

## pseudocode

```c
__int64 mkl_serv_snprintf_s(__int64 a1, __int64 a2, __int64 a3, __int64 a4, ...)
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
  LPCSTR lpModuleName; // [rsp+40h] [rbp-98h]
  const char *v18; // [rsp+48h] [rbp-90h]
  const char *v19; // [rsp+50h] [rbp-88h]
  const char *v20; // [rsp+58h] [rbp-80h]
  const char *v21; // [rsp+60h] [rbp-78h]
  const char *v22; // [rsp+68h] [rbp-70h]
  const char *v23; // [rsp+70h] [rbp-68h]
  const char *v24; // [rsp+78h] [rbp-60h]
  const char *v25; // [rsp+80h] [rbp-58h]
  const char *v26; // [rsp+88h] [rbp-50h]
  const char *v27; // [rsp+90h] [rbp-48h]
  const char *v28; // [rsp+98h] [rbp-40h]
  va_list v29; // [rsp+A0h] [rbp-38h]
  va_list va; // [rsp+100h] [rbp+28h] BYREF

  va_start(va, a4);
  va_copy(v29, va);
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
        && (qword_1836E89D8 = (__int64)GetProcAddress(ModuleHandleA, "__stdio_common_vsscanf")) != 0
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
          qword_1836E89F8 = (__int64)GetProcAddress(LibraryA, "sscanf");
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
    result = qword_1836E89E8(qword_1836E89C8, a1, a2, a3, a4, 0, va);
    if ( (int)result < 0 )
      result = 0xFFFFFFFFLL;
  }
  else if ( dword_1836D0DF0 == 1 )
  {
    result = qword_1836E8A08(a1, a2, a3, a4, va);
  }
  else
  {
    result = 0xFFFFFFFFLL;
  }
  v29 = 0;
  return result;
}

```

## disassembly

```asm
0x18000f110  push    rdi
0x18000f111  push    r12
0x18000f113  push    r13
0x18000f115  push    r14
0x18000f117  push    r15
0x18000f119  push    rbp
0x18000f11a  sub     rsp, 0A8h
0x18000f121  mov     rdi, r8
0x18000f124  mov     [rsp+0D8h+arg_18], r9
0x18000f12c  lea     rax, [rsp+0D8h+arg_20]
0x18000f134  mov     [rsp+0D8h+var_38], rax
0x18000f13c  mov     r14, rdx
0x18000f13f  mov     r13, rcx
0x18000f142  mov     eax, cs:dword_1836D0DF0
0x18000f148  cmp     eax, 0FFFFFFFFh
0x18000f14b  mov     r12, [rsp+0D8h+arg_18]
0x18000f153  mov     rbp, [rsp+0D8h+var_38]
0x18000f15b  jz      loc_18000F1EA
0x18000f161  mov     eax, cs:dword_1836D0DF0
0x18000f167  cmp     eax, 2
0x18000f16a  jz      short loc_18000F1B5
0x18000f16c  mov     eax, cs:dword_1836D0DF0
0x18000f172  cmp     eax, 1
0x18000f175  jz      short loc_18000F19A
0x18000f177  mov     eax, 0FFFFFFFFh
0x18000f17c  mov     [rsp+0D8h+var_38], 0
0x18000f188  add     rsp, 0A8h
0x18000f18f  pop     rbp
0x18000f190  pop     r15
0x18000f192  pop     r14
0x18000f194  pop     r13
0x18000f196  pop     r12
0x18000f198  pop     rdi
0x18000f199  retn
0x18000f19a  mov     rax, rsp
0x18000f19d  mov     rcx, r13
0x18000f1a0  mov     rdx, r14
0x18000f1a3  mov     r8, rdi
0x18000f1a6  mov     r9, r12
0x18000f1a9  mov     [rax+20h], rbp
0x18000f1ad  call    cs:qword_1836E8A08
0x18000f1b3  jmp     short loc_18000F17C
0x18000f1b5  mov     rax, rsp
0x18000f1b8  mov     rdx, r13
0x18000f1bb  mov     rcx, cs:qword_1836E89C8
0x18000f1c2  mov     r8, r14
0x18000f1c5  mov     r9, rdi
0x18000f1c8  mov     [rax+20h], r12
0x18000f1cc  mov     qword ptr [rax+28h], 0
0x18000f1d4  mov     [rax+30h], rbp
0x18000f1d8  call    cs:qword_1836E89E8
0x18000f1de  mov     edx, 0FFFFFFFFh
0x18000f1e3  test    eax, eax
0x18000f1e5  cmovl   eax, edx
0x18000f1e8  jmp     short loc_18000F17C
0x18000f1ea  call    sub_18000E560
0x18000f1ef  mov     eax, cs:dword_1836D0DF0
0x18000f1f5  cmp     eax, 0FFFFFFFFh
0x18000f1f8  jz      short loc_18000F204
0x18000f1fa  call    sub_18000E580
0x18000f1ff  jmp     loc_18000F161
0x18000f204  lea     rax, aAppcrt140Dll; "APPCRT140.DLL"
0x18000f20b  lea     r10, aAppcrt140dDll; "APPCRT140D.DLL"
0x18000f212  lea     r11, aUcrtbaseDll; "UCRTBASE.DLL"
0x18000f219  lea     r15, aUcrtbasedDll; "UCRTBASED.DLL"
0x18000f220  mov     [rsp+0D8h+lpModuleName], rax
0x18000f225  mov     [rsp+0D8h+var_90], r10
0x18000f22a  mov     [rsp+0D8h+var_88], r11
0x18000f22f  mov     [rsp+0D8h+var_80], r15
0x18000f234  xor     r15d, r15d
0x18000f237  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpModuleName
0x18000f23c  call    cs:__imp_GetModuleHandleA
0x18000f242  test    rax, rax
0x18000f245  jnz     short loc_18000F26C
0x18000f247  inc     r15
0x18000f24a  cmp     r15, 4
0x18000f24e  jb      short loc_18000F237
0x18000f250  xor     r15d, r15d
0x18000f253  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpLibFileName
0x18000f258  call    cs:__imp_LoadLibraryA
0x18000f25e  test    rax, rax
0x18000f261  jnz     short loc_18000F26C
0x18000f263  inc     r15
0x18000f266  cmp     r15, 4
0x18000f26a  jb      short loc_18000F253
0x18000f26c  mov     r15, rax
0x18000f26f  test    r15, r15
0x18000f272  jz      loc_18000F333
0x18000f278  mov     rcx, r15; hModule
0x18000f27b  lea     rdx, aStdioCommonVss; "__stdio_common_vsscanf"
0x18000f282  call    cs:__imp_GetProcAddress
0x18000f288  mov     cs:qword_1836E89D8, rax
0x18000f28f  test    rax, rax
0x18000f292  jz      loc_18000F333
0x18000f298  mov     rcx, r15; hModule
0x18000f29b  lea     rdx, aStdioCommonVfs; "__stdio_common_vfscanf"
0x18000f2a2  call    cs:__imp_GetProcAddress
0x18000f2a8  mov     cs:qword_1836E89E0, rax
0x18000f2af  test    rax, rax
0x18000f2b2  jz      short loc_18000F333
0x18000f2b4  mov     rcx, r15; hModule
0x18000f2b7  lea     rdx, aStdioCommonVsn; "__stdio_common_vsnprintf_s"
0x18000f2be  call    cs:__imp_GetProcAddress
0x18000f2c4  mov     cs:qword_1836E89E8, rax
0x18000f2cb  test    rax, rax
0x18000f2ce  jz      short loc_18000F333
0x18000f2d0  mov     rcx, r15; hModule
0x18000f2d3  lea     rdx, aStdioCommonVfp; "__stdio_common_vfprintf_s"
0x18000f2da  call    cs:__imp_GetProcAddress
0x18000f2e0  mov     cs:qword_1836E89D0, rax
0x18000f2e7  test    rax, rax
0x18000f2ea  jz      short loc_18000F333
0x18000f2ec  mov     rcx, r15; hModule
0x18000f2ef  lea     rdx, aAcrtIobFunc; "__acrt_iob_func"
0x18000f2f6  call    cs:__imp_GetProcAddress
0x18000f2fc  mov     cs:qword_1836E89F0, rax
0x18000f303  test    rax, rax
0x18000f306  jz      short loc_18000F333
0x18000f308  mov     rcx, r15; hModule
0x18000f30b  lea     rdx, aFflush; "fflush"
0x18000f312  call    cs:__imp_GetProcAddress
0x18000f318  mov     cs:qword_1836E89C0, rax
0x18000f31f  test    rax, rax
0x18000f322  jz      short loc_18000F333
0x18000f324  mov     cs:dword_1836D0DF0, 2
0x18000f32e  jmp     loc_18000F1FA
0x18000f333  lea     rax, aMsvcr120Dll; "MSVCR120.DLL"
0x18000f33a  lea     r10, aMsvcr120dDll; "MSVCR120D.DLL"
0x18000f341  mov     [rsp+0D8h+lpModuleName], rax
0x18000f346  lea     rax, aMsvcr100Dll; "MSVCR100.DLL"
0x18000f34d  mov     [rsp+0D8h+var_78], rax
0x18000f352  lea     rax, aMsvcr100dDll; "MSVCR100D.DLL"
0x18000f359  mov     [rsp+0D8h+var_70], rax
0x18000f35e  lea     rax, aMsvcr90Dll; "MSVCR90.DLL"
0x18000f365  mov     [rsp+0D8h+var_68], rax
0x18000f36a  lea     rax, aMsvcr90dDll; "MSVCR90D.DLL"
0x18000f371  mov     [rsp+0D8h+var_60], rax
0x18000f376  lea     rax, aMsvcr80Dll; "MSVCR80.DLL"
0x18000f37d  mov     [rsp+0D8h+var_58], rax
0x18000f385  lea     rax, aMsvcr80dDll; "MSVCR80D.DLL"
0x18000f38c  mov     [rsp+0D8h+var_50], rax
0x18000f394  lea     rax, aMsvcrtDll; "MSVCRT.DLL"
0x18000f39b  mov     [rsp+0D8h+var_48], rax
0x18000f3a3  lea     r11, aMsvcr110Dll; "MSVCR110.DLL"
0x18000f3aa  lea     r15, aMsvcr110dDll; "MSVCR110D.DLL"
0x18000f3b1  lea     rax, aMsvcrtdDll; "MSVCRTD.DLL"
0x18000f3b8  mov     [rsp+0D8h+var_90], r10
0x18000f3bd  mov     [rsp+0D8h+var_88], r11
0x18000f3c2  mov     [rsp+0D8h+var_80], r15
0x18000f3c7  xor     r15d, r15d
0x18000f3ca  mov     [rsp+0D8h+var_40], rax
0x18000f3d2  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpModuleName
0x18000f3d7  call    cs:__imp_GetModuleHandleA
0x18000f3dd  test    rax, rax
0x18000f3e0  jnz     short loc_18000F407
0x18000f3e2  inc     r15
0x18000f3e5  cmp     r15, 0Ch
0x18000f3e9  jb      short loc_18000F3D2
0x18000f3eb  xor     r15d, r15d
0x18000f3ee  mov     rcx, [rsp+r15*8+0D8h+lpModuleName]; lpLibFileName
0x18000f3f3  call    cs:__imp_LoadLibraryA
0x18000f3f9  test    rax, rax
0x18000f3fc  jnz     short loc_18000F407
0x18000f3fe  inc     r15
0x18000f401  cmp     r15, 0Ch
0x18000f405  jb      short loc_18000F3EE
0x18000f407  mov     r15, rax
0x18000f40a  test    r15, r15
0x18000f40d  jz      loc_18000F1FA
0x18000f413  mov     rcx, r15; hModule
0x18000f416  lea     rdx, aSscanf; "sscanf"
0x18000f41d  call    cs:__imp_GetProcAddress
0x18000f423  mov     cs:qword_1836E89F8, rax
0x18000f42a  test    rax, rax
0x18000f42d  jz      loc_18000F1FA
0x18000f433  mov     rcx, r15; hModule
0x18000f436  lea     rdx, aFscanf; "fscanf"
0x18000f43d  call    cs:__imp_GetProcAddress
0x18000f443  mov     cs:qword_1836E8A00, rax
0x18000f44a  test    rax, rax
0x18000f44d  jz      loc_18000F1FA
0x18000f453  mov     rcx, r15; hModule
0x18000f456  lea     rdx, aVfprintfS; "vfprintf_s"
0x18000f45d  call    cs:__imp_GetProcAddress
0x18000f463  mov     cs:qword_1836E89B8, rax
0x18000f46a  test    rax, rax
0x18000f46d  jz      loc_18000F1FA
0x18000f473  mov     rcx, r15; hModule
0x18000f476  lea     rdx, aVsnprintfS; "_vsnprintf_s"
0x18000f47d  call    cs:__imp_GetProcAddress
0x18000f483  mov     cs:qword_1836E8A08, rax
0x18000f48a  test    rax, rax
0x18000f48d  jz      loc_18000F1FA
0x18000f493  mov     rcx, r15; hModule
0x18000f496  lea     rdx, aIobFunc; "__iob_func"
0x18000f49d  call    cs:__imp_GetProcAddress
0x18000f4a3  mov     cs:qword_1836E8A10, rax
0x18000f4aa  test    rax, rax
0x18000f4ad  jz      loc_18000F1FA
0x18000f4b3  mov     rcx, r15; hModule
0x18000f4b6  lea     rdx, aFflush; "fflush"
0x18000f4bd  call    cs:__imp_GetProcAddress
0x18000f4c3  mov     cs:qword_1836E89C0, rax
0x18000f4ca  test    rax, rax
0x18000f4cd  jz      loc_18000F1FA
0x18000f4d3  mov     cs:dword_1836D0DF0, 1
0x18000f4dd  jmp     loc_18000F1FA
```
