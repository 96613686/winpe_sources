# CommonUtil::UtilGetModuleFileName(wchar_t * *,HINSTANCE__ *,bool)

- ea: `0x14000d93c`
- end: `0x14000db99`
- name: `?UtilGetModuleFileName@CommonUtil@@YAJPEAPEA_WPEAUHINSTANCE__@@_N@Z`
- size: `605`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HMODULE hModule, HINSTANCE, bool)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14000e760`
- `0x140015154`
- `0x140088850`
- `0x14008ab48`
- `0x14008ffb0`

## callees

- `0x14000d93c`
- `0x140013110`
- `0x140015528`
- `0x140017738`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x1400f3610`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x14000da2d`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14000da2d`
- `KERNEL32!CloseHandle` at `0x14000da49`
- `KERNEL32!CloseHandle` at `0x14000daa6`
- `KERNEL32!CloseHandle` at `0x14000dabb`
- `KERNEL32!CloseHandle` at `0x14000dae2`
- `KERNEL32!CloseHandle` at `0x14000daf0`
- `KERNEL32!CloseHandle` at `0x14000da49`
- `KERNEL32!CloseHandle` at `0x14000daa6`
- `KERNEL32!CloseHandle` at `0x14000dabb`
- `KERNEL32!CloseHandle` at `0x14000dae2`
- `KERNEL32!CloseHandle` at `0x14000daf0`
- `KERNEL32!GetModuleFileNameW` at `0x14000d9b3`
- `KERNEL32!GetModuleFileNameW` at `0x14000d9b3`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetModuleFileName(
        CommonUtil *this,
        const struct std::nothrow_t *hModule,
        HINSTANCE a3)
{
  LPWSTR v3; // rbx
  char v4; // r15
  DWORD i; // edi
  const struct std::nothrow_t *v8; // rdx
  int v9; // ebx
  DWORD ModuleFileNameW; // eax
  const wchar_t *v11; // r8
  const struct std::nothrow_t *v12; // rdx
  int File; // esi
  DWORD FinalPathNameByHandleW; // eax
  const struct std::nothrow_t *v15; // rdx
  unsigned int v16; // edi
  int LastFailure; // eax
  LPWSTR lpFilename; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-18h] BYREF

  v3 = 0;
  v4 = (char)a3;
  lpFilename = 0;
  for ( i = 260; ; i = (3 * i) >> 1 )
  {
    if ( v3 )
    {
      operator delete(v3, hModule);
      lpFilename = 0;
    }
    v9 = CommonUtil::MpNewBuffer<wchar_t>(&lpFilename, i);
    if ( v9 < 0 )
      break;
    v3 = lpFilename;
    ModuleFileNameW = GetModuleFileNameW((HMODULE)hModule, lpFilename, i);
    if ( !ModuleFileNameW )
    {
      LastFailure = HrGetLastFailure();
      goto LABEL_39;
    }
    if ( ModuleFileNameW < i )
    {
      if ( !v4 )
        goto LABEL_24;
      hFile = (HANDLE)-1LL;
      File = CommonUtil::UtilCreateFile((CommonUtil *)&hFile, (void **)v3, 0, 7u, 3u, 0, 0, 0, lpFilename);
      if ( File < 0 )
      {
        if ( hFile != (HANDLE)-1LL )
          CloseHandle(hFile);
        if ( v3 )
          operator delete(v3, v12);
        return (unsigned int)File;
      }
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, v3, i, 0);
      if ( !FinalPathNameByHandleW )
      {
        v16 = HrGetLastFailure();
        if ( hFile != (HANDLE)-1LL )
          CloseHandle(hFile);
LABEL_40:
        if ( v3 )
LABEL_41:
          operator delete(v3, v15);
        return v16;
      }
      if ( FinalPathNameByHandleW < i )
      {
        if ( FinalPathNameByHandleW - 4 <= 0x103 && *v3 == 92 && v3[1] == 92 && v3[2] == 63 && v3[3] == 92 )
        {
          v16 = CommonUtil::HrDuplicateStringW(this, (wchar_t **)v3 + 1, v11);
          if ( hFile != (HANDLE)-1LL )
            CloseHandle(hFile);
          goto LABEL_41;
        }
        if ( hFile != (HANDLE)-1LL )
          CloseHandle(hFile);
LABEL_24:
        LastFailure = CommonUtil::HrDuplicateStringW(this, (wchar_t **)v3, v11);
LABEL_39:
        v16 = LastFailure;
        goto LABEL_40;
      }
      if ( hFile != (HANDLE)-1LL )
        CloseHandle(hFile);
    }
    if ( i > 0x7FFF )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_02054f1da1d13c5db2ae787d1a5da12f_Traceguids, i);
      if ( v3 )
        operator delete(v3, hModule);
      return 2147942511LL;
    }
  }
  if ( lpFilename )
    operator delete(lpFilename, v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000d93c  mov     [rsp-28h+arg_10], rbx
0x14000d941  mov     [rsp-28h+arg_18], rsi
0x14000d946  push    rbp
0x14000d947  push    rdi
0x14000d948  push    r12
0x14000d94a  push    r14
0x14000d94c  push    r15
0x14000d94e  mov     rbp, rsp
0x14000d951  sub     rsp, 60h
0x14000d955  mov     rax, cs:__security_cookie
0x14000d95c  xor     rax, rsp
0x14000d95f  mov     [rbp+var_10], rax
0x14000d963  xor     ebx, ebx
0x14000d965  mov     r15b, r8b
0x14000d968  mov     [rbp+lpFilename], rbx
0x14000d96c  mov     r12, rdx
0x14000d96f  mov     r14, rcx
0x14000d972  mov     edi, 104h
0x14000d977  test    rbx, rbx
0x14000d97a  jz      short loc_14000D98C
0x14000d97c  mov     rcx, rbx; void *
0x14000d97f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000d984  mov     [rbp+lpFilename], 0
0x14000d98c  mov     edx, edi
0x14000d98e  lea     rcx, [rbp+lpFilename]
0x14000d992  call    ??$MpNewBuffer@_W@CommonUtil@@YAJPEAPEA_W_K@Z; CommonUtil::MpNewBuffer<wchar_t>(wchar_t * *,unsigned __int64)
0x14000d997  mov     ecx, eax
0x14000d999  mov     ebx, eax
0x14000d99b  shr     ecx, 1Fh
0x14000d99e  test    cl, cl
0x14000d9a0  jnz     loc_14000DB64
0x14000d9a6  mov     rbx, [rbp+lpFilename]
0x14000d9aa  mov     r8d, edi; nSize
0x14000d9ad  mov     rdx, rbx; lpFilename
0x14000d9b0  mov     rcx, r12; hModule
0x14000d9b3  call    cs:__imp_GetModuleFileNameW
0x14000d9b9  test    eax, eax
0x14000d9bb  jz      loc_14000DB4C
0x14000d9c1  cmp     eax, edi
0x14000d9c3  jnb     loc_14000DA4F
0x14000d9c9  test    r15b, r15b
0x14000d9cc  jz      loc_14000DAC1
0x14000d9d2  mov     [rsp+60h+var_28], 0; struct _SECURITY_ATTRIBUTES *
0x14000d9db  lea     rcx, [rbp+hFile]; this
0x14000d9df  mov     qword ptr [rsp+60h+var_30], 0; unsigned int
0x14000d9e8  mov     r9d, 7; unsigned int
0x14000d9ee  mov     [rsp+60h+var_38], 0; unsigned int
0x14000d9f6  xor     r8d, r8d; wchar_t *
0x14000d9f9  mov     rdx, rbx; void **
0x14000d9fc  mov     [rsp+60h+var_40], 3; unsigned int
0x14000da04  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x14000da0c  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x14000da11  mov     ecx, eax
0x14000da13  mov     esi, eax
0x14000da15  shr     ecx, 1Fh
0x14000da18  test    cl, cl
0x14000da1a  mov     rcx, [rbp+hFile]; hObject
0x14000da1e  jnz     loc_14000DAEA
0x14000da24  xor     r9d, r9d; dwFlags
0x14000da27  mov     r8d, edi; cchFilePath
0x14000da2a  mov     rdx, rbx; lpszFilePath
0x14000da2d  call    cs:__imp_GetFinalPathNameByHandleW
0x14000da33  test    eax, eax
0x14000da35  jz      loc_14000DAD1
0x14000da3b  cmp     eax, edi
0x14000da3d  jb      short loc_14000DA65
0x14000da3f  mov     rcx, [rbp+hFile]; hObject
0x14000da43  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000da47  jz      short loc_14000DA4F
0x14000da49  call    cs:__imp_CloseHandle
0x14000da4f  cmp     edi, 7FFFh
0x14000da55  ja      loc_14000DB07
0x14000da5b  lea     edi, [rdi+rdi*2]
0x14000da5e  shr     edi, 1
0x14000da60  jmp     loc_14000D977
0x14000da65  add     eax, 0FFFFFFFCh
0x14000da68  cmp     eax, 103h
0x14000da6d  ja      short loc_14000DAB1
0x14000da6f  cmp     word ptr [rbx], 5Ch ; '\'
0x14000da73  jnz     short loc_14000DAB1
0x14000da75  cmp     word ptr [rbx+2], 5Ch ; '\'
0x14000da7a  jnz     short loc_14000DAB1
0x14000da7c  cmp     word ptr [rbx+4], 3Fh ; '?'
0x14000da81  jnz     short loc_14000DAB1
0x14000da83  cmp     word ptr [rbx+6], 5Ch ; '\'
0x14000da88  jnz     short loc_14000DAB1
0x14000da8a  lea     rdx, [rbx+8]; wchar_t **
0x14000da8e  mov     rcx, r14; this
0x14000da91  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x14000da96  mov     rcx, [rbp+hFile]; hObject
0x14000da9a  mov     edi, eax
0x14000da9c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000daa0  jz      loc_14000DB58
0x14000daa6  call    cs:__imp_CloseHandle
0x14000daac  jmp     loc_14000DB58
0x14000dab1  mov     rcx, [rbp+hFile]; hObject
0x14000dab5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000dab9  jz      short loc_14000DAC1
0x14000dabb  call    cs:__imp_CloseHandle
0x14000dac1  mov     rdx, rbx; wchar_t **
0x14000dac4  mov     rcx, r14; this
0x14000dac7  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x14000dacc  jmp     loc_14000DB51
0x14000dad1  call    HrGetLastFailure
0x14000dad6  mov     rcx, [rbp+hFile]; hObject
0x14000dada  mov     edi, eax
0x14000dadc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000dae0  jz      short loc_14000DB53
0x14000dae2  call    cs:__imp_CloseHandle
0x14000dae8  jmp     short loc_14000DB53
0x14000daea  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000daee  jz      short loc_14000DAF6
0x14000daf0  call    cs:__imp_CloseHandle
0x14000daf6  test    rbx, rbx
0x14000daf9  jz      short loc_14000DB03
0x14000dafb  mov     rcx, rbx; void *
0x14000dafe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000db03  mov     eax, esi
0x14000db05  jmp     short loc_14000DB74
0x14000db07  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db0e  lea     rax, WPP_GLOBAL_Control
0x14000db15  cmp     rcx, rax
0x14000db18  jz      short loc_14000DB38
0x14000db1a  test    byte ptr [rcx+1Ch], 1
0x14000db1e  jz      short loc_14000DB38
0x14000db20  mov     rcx, [rcx+10h]
0x14000db24  lea     r8, WPP_02054f1da1d13c5db2ae787d1a5da12f_Traceguids
0x14000db2b  mov     edx, 14h
0x14000db30  mov     r9d, edi
0x14000db33  call    WPP_SF_d
0x14000db38  test    rbx, rbx
0x14000db3b  jz      short loc_14000DB45
0x14000db3d  mov     rcx, rbx; void *
0x14000db40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000db45  mov     eax, 8007006Fh
0x14000db4a  jmp     short loc_14000DB74
0x14000db4c  call    HrGetLastFailure
0x14000db51  mov     edi, eax
0x14000db53  test    rbx, rbx
0x14000db56  jz      short loc_14000DB60
0x14000db58  mov     rcx, rbx; void *
0x14000db5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000db60  mov     eax, edi
0x14000db62  jmp     short loc_14000DB74
0x14000db64  mov     rcx, [rbp+lpFilename]; void *
0x14000db68  test    rcx, rcx
0x14000db6b  jz      short loc_14000DB72
0x14000db6d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000db72  mov     eax, ebx
0x14000db74  mov     rcx, [rbp+var_10]
0x14000db78  xor     rcx, rsp; StackCookie
0x14000db7b  call    __security_check_cookie
0x14000db80  lea     r11, [rsp+60h+var_s0]
0x14000db85  mov     rbx, [r11+40h]
0x14000db89  mov     rsi, [r11+48h]
0x14000db8d  mov     rsp, r11
0x14000db90  pop     r15
0x14000db92  pop     r14
0x14000db94  pop     r12
0x14000db96  pop     rdi
0x14000db97  pop     rbp
0x14000db98  retn
```
