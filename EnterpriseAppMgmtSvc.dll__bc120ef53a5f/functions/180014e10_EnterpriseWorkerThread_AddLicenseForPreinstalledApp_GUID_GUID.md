# EnterpriseWorkerThread::AddLicenseForPreinstalledApp(_GUID,_GUID)

- ea: `0x180014e10`
- end: `0x1800150f2`
- name: `?AddLicenseForPreinstalledApp@EnterpriseWorkerThread@@AEAAJU_GUID@@0@Z`
- size: `738`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x18001735c`

## callees

- `0x180002fb4`
- `0x180014e10`
- `0x180019384`
- `0x18001c550`
- `0x18001c5fc`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180014fc3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800150ce`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014fc3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800150ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180015097`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150b9`
- `OLEAUT32!__imp_SysFreeString` at `0x180015097`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800150b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014fac`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014f47`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014f47`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014eaf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014eaf`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180014ef9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180014ef9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EnterpriseWorkerThread::AddLicenseForPreinstalledApp(
        EnterpriseWorkerThread *this,
        struct _GUID *a2,
        struct _GUID *a3)
{
  EnterpriseWorkerThread *v4; // r15
  void *v5; // rbx
  void *v6; // rdi
  signed int updated; // r14d
  DWORD v8; // r13d
  void *v9; // rsi
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD FileSize; // eax
  void *v13; // rax
  void *v14; // r15
  signed int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  LPCWSTR lpFileName; // [rsp+40h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-21h] BYREF
  HANDLE v21; // [rsp+50h] [rbp-19h]
  void *v22; // [rsp+58h] [rbp-11h]
  __int64 v23; // [rsp+60h] [rbp-9h]
  __int64 v24; // [rsp+68h] [rbp-1h]
  _OWORD v25[5]; // [rsp+70h] [rbp+7h] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+D8h] [rbp+6Fh] BYREF
  struct _GUID *v28; // [rsp+E0h] [rbp+77h]
  int v29; // [rsp+E8h] [rbp+7Fh] BYREF

  v28 = a3;
  v4 = this;
  v5 = 0;
  v6 = 0;
  v22 = 0;
  lpFileName = 0;
  v23 = 0;
  bstrString = 0;
  v24 = 0;
  v29 = 0;
  v25[0] = *a2;
  updated = EnrollmentManager::RetrieveBSTR(1, v25, 20, &lpFileName);
  if ( updated >= 0 )
  {
    v8 = 0;
    nNumberOfBytesToRead = 0;
    v9 = 0;
    *(_QWORD *)&v25[0] = 0;
    v21 = 0;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW && (v5 = FileW, v21 = FileW, FileW == (HANDLE)-1LL) )
    {
      LastError = GetLastError();
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      FileSize = GetFileSize(v5, 0);
      nNumberOfBytesToRead = FileSize;
      if ( ((FileSize + 1) & 0xFFFFFFFE) != 0 )
      {
        v13 = operator new[](FileSize);
        v14 = v13;
        if ( v13 )
        {
          v9 = v13;
          if ( ReadFile(v5, v13, nNumberOfBytesToRead, &nNumberOfBytesToRead, 0) )
          {
            if ( nNumberOfBytesToRead )
            {
              updated = 0;
              v9 = 0;
              v6 = v14;
              v22 = v14;
              v8 = nNumberOfBytesToRead;
              nNumberOfBytesToRead = 0;
            }
            else
            {
              updated = -2147024883;
            }
          }
          else
          {
            v15 = GetLastError();
            updated = v15;
            if ( v15 > 0 )
              updated = (unsigned __int16)v15 | 0x80070000;
          }
        }
        else
        {
          updated = -2147024882;
        }
        v4 = this;
      }
      else
      {
        updated = -2147024883;
      }
    }
    if ( v5 )
      CloseHandle(v5);
    if ( v9 )
      operator delete[](v9);
    if ( updated >= 0 )
    {
      v25[0] = *a2;
      updated = EnrollmentManager::RetrieveBSTR(1, v25, 6, &bstrString);
      if ( updated >= 0 )
      {
        v25[0] = *a2;
        updated = EnrollmentManager::RetrieveByte(v16, v25, 22, &v29);
        if ( updated >= 0 )
        {
          v25[0] = *a2;
          updated = EnterpriseWorkerThread::UpdateXAPRequestStatus(v4, v25, 4);
          if ( updated >= 0 )
          {
            v17 = *((_QWORD *)v4 + 38);
            v25[0] = *v28;
            updated = (*(__int64 (__fastcall **)(__int64, _OWORD *, void *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v17 + 288LL))(
                        v17,
                        v25,
                        v6,
                        v8,
                        0,
                        0);
          }
        }
      }
    }
  }
  SysFreeString(0);
  SysFreeString(bstrString);
  SysFreeString((BSTR)lpFileName);
  if ( v6 )
    operator delete[](v6);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180014e10  mov     [rsp-8+arg_10], r8
0x180014e15  mov     [rsp-8+arg_0], rcx
0x180014e1a  push    rbp
0x180014e1b  push    rbx
0x180014e1c  push    rsi
0x180014e1d  push    rdi
0x180014e1e  push    r12
0x180014e20  push    r13
0x180014e22  push    r14
0x180014e24  push    r15
0x180014e26  lea     rbp, [rsp-1Fh]
0x180014e2b  sub     rsp, 88h
0x180014e32  mov     r12, rdx
0x180014e35  mov     r15, rcx
0x180014e38  xor     ebx, ebx
0x180014e3a  mov     edi, ebx
0x180014e3c  mov     [rbp+57h+var_68], rbx
0x180014e40  mov     [rbp+57h+lpFileName], rbx
0x180014e44  mov     [rbp+57h+var_60], rbx
0x180014e48  mov     [rbp+57h+bstrString], rbx
0x180014e4c  mov     [rbp+57h+var_58], rbx
0x180014e50  mov     [rbp+57h+arg_18], ebx
0x180014e53  movaps  xmm0, xmmword ptr [rdx]
0x180014e56  movdqa  [rbp+57h+var_50], xmm0
0x180014e5b  lea     r8d, [rbx+14h]
0x180014e5f  lea     r9, [rbp+57h+lpFileName]
0x180014e63  lea     rdx, [rbp+57h+var_50]
0x180014e67  lea     ecx, [rbx+1]
0x180014e6a  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x180014e6f  mov     r14d, eax
0x180014e72  test    eax, eax
0x180014e74  js      loc_180015095
0x180014e7a  mov     r13d, ebx
0x180014e7d  mov     [rbp+57h+nNumberOfBytesToRead], ebx
0x180014e80  mov     esi, ebx
0x180014e82  mov     qword ptr [rbp+57h+var_50], rbx
0x180014e86  mov     [rbp+57h+var_70], rbx
0x180014e8a  mov     [rsp+0C0h+hTemplateFile], rbx; hTemplateFile
0x180014e8f  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180014e97  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180014e9f  xor     r9d, r9d; lpSecurityAttributes
0x180014ea2  mov     edx, 80000000h; dwDesiredAccess
0x180014ea7  lea     r8d, [rbx+1]; dwShareMode
0x180014eab  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180014eaf  call    cs:__imp_CreateFileW
0x180014eb6  nop     dword ptr [rax+rax+00h]
0x180014ebb  test    rax, rax
0x180014ebe  jz      short loc_180014EF4
0x180014ec0  mov     rbx, rax
0x180014ec3  mov     [rbp+57h+var_70], rax
0x180014ec7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014ecb  jnz     short loc_180014EF4
0x180014ecd  call    cs:__imp_GetLastError
0x180014ed4  nop     dword ptr [rax+rax+00h]
0x180014ed9  mov     r14d, eax
0x180014edc  test    eax, eax
0x180014ede  jle     loc_180014FA4
0x180014ee4  movzx   r14d, ax
0x180014ee8  or      r14d, 80070000h
0x180014eef  jmp     loc_180014FA4
0x180014ef4  xor     edx, edx; lpFileSizeHigh
0x180014ef6  mov     rcx, rbx; hFile
0x180014ef9  call    cs:__imp_GetFileSize
0x180014f00  nop     dword ptr [rax+rax+00h]
0x180014f05  mov     [rbp+57h+nNumberOfBytesToRead], eax
0x180014f08  lea     ecx, [rax+1]
0x180014f0b  test    ecx, 0FFFFFFFEh
0x180014f11  jnz     short loc_180014F1E
0x180014f13  mov     r14d, 8007000Dh
0x180014f19  jmp     loc_180014FA4
0x180014f1e  mov     ecx, eax; unsigned __int64
0x180014f20  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014f25  mov     r15, rax
0x180014f28  test    rax, rax
0x180014f2b  jz      short loc_180014F9A
0x180014f2d  mov     rsi, rax
0x180014f30  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x180014f39  lea     r9, [rbp+57h+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x180014f3d  mov     r8d, [rbp+57h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180014f41  mov     rdx, rax; lpBuffer
0x180014f44  mov     rcx, rbx; hFile
0x180014f47  call    cs:__imp_ReadFile
0x180014f4e  nop     dword ptr [rax+rax+00h]
0x180014f53  test    eax, eax
0x180014f55  jnz     short loc_180014F77
0x180014f57  call    cs:__imp_GetLastError
0x180014f5e  nop     dword ptr [rax+rax+00h]
0x180014f63  mov     r14d, eax
0x180014f66  test    eax, eax
0x180014f68  jle     short loc_180014FA0
0x180014f6a  movzx   r14d, ax
0x180014f6e  or      r14d, 80070000h
0x180014f75  jmp     short loc_180014FA0
0x180014f77  mov     eax, [rbp+57h+nNumberOfBytesToRead]
0x180014f7a  test    eax, eax
0x180014f7c  jnz     short loc_180014F86
0x180014f7e  mov     r14d, 8007000Dh
0x180014f84  jmp     short loc_180014FA0
0x180014f86  xor     r14d, r14d
0x180014f89  xor     esi, esi
0x180014f8b  mov     rdi, r15
0x180014f8e  mov     [rbp+57h+var_68], r15
0x180014f92  mov     r13d, eax
0x180014f95  mov     [rbp+57h+nNumberOfBytesToRead], esi
0x180014f98  jmp     short loc_180014FA0
0x180014f9a  mov     r14d, 8007000Eh
0x180014fa0  mov     r15, [rbp+57h+arg_0]
0x180014fa4  test    rbx, rbx
0x180014fa7  jz      short loc_180014FB9
0x180014fa9  mov     rcx, rbx; hObject
0x180014fac  call    cs:__imp_CloseHandle
0x180014fb3  nop     dword ptr [rax+rax+00h]
0x180014fb8  nop
0x180014fb9  xor     ebx, ebx
0x180014fbb  test    rsi, rsi
0x180014fbe  jz      short loc_180014FCF
0x180014fc0  mov     rcx, rsi
0x180014fc3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014fca  nop     dword ptr [rax+rax+00h]
0x180014fcf  test    r14d, r14d
0x180014fd2  js      loc_180015095
0x180014fd8  movaps  xmm0, xmmword ptr [r12]
0x180014fdd  movdqa  [rbp+57h+var_50], xmm0
0x180014fe2  mov     r8d, 6
0x180014fe8  lea     r9, [rbp+57h+bstrString]
0x180014fec  lea     rdx, [rbp+57h+var_50]
0x180014ff0  lea     ecx, [r8-5]
0x180014ff4  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x180014ff9  mov     r14d, eax
0x180014ffc  test    eax, eax
0x180014ffe  js      loc_180015095
0x180015004  movaps  xmm0, xmmword ptr [r12]
0x180015009  movdqa  [rbp+57h+var_50], xmm0
0x18001500e  mov     r8d, 16h
0x180015014  lea     r9, [rbp+57h+arg_18]
0x180015018  lea     rdx, [rbp+57h+var_50]
0x18001501c  call    ?RetrieveByte@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAE@Z; EnrollmentManager::RetrieveByte(TABLEID,_GUID,ushort,uchar *)
0x180015021  mov     r14d, eax
0x180015024  test    eax, eax
0x180015026  js      short loc_180015095
0x180015028  movaps  xmm0, xmmword ptr [r12]
0x18001502d  movdqa  [rbp+57h+var_50], xmm0
0x180015032  mov     byte ptr [rsp+0C0h+dwFlagsAndAttributes], 37h ; '7'
0x180015037  lea     rax, Src
0x18001503e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x180015043  xor     r9d, r9d
0x180015046  lea     r8d, [r9+4]
0x18001504a  lea     rdx, [rbp+57h+var_50]
0x18001504e  mov     rcx, r15
0x180015051  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180015056  mov     r14d, eax
0x180015059  test    eax, eax
0x18001505b  js      short loc_180015095
0x18001505d  mov     rcx, [r15+130h]
0x180015064  mov     rax, [rbp+57h+arg_10]
0x180015068  movaps  xmm0, xmmword ptr [rax]
0x18001506b  movdqa  [rbp+57h+var_50], xmm0
0x180015070  mov     rax, [rcx]
0x180015073  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx
0x180015077  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rbx
0x18001507c  mov     r9d, r13d
0x18001507f  mov     r8, rdi
0x180015082  lea     rdx, [rbp+57h+var_50]
0x180015086  mov     rax, [rax+120h]
0x18001508d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015092  mov     r14d, eax
0x180015095  xor     ecx, ecx; bstrString
0x180015097  call    cs:__imp_SysFreeString
0x18001509e  nop     dword ptr [rax+rax+00h]
0x1800150a3  nop
0x1800150a4  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800150a8  call    cs:__imp_SysFreeString
0x1800150af  nop     dword ptr [rax+rax+00h]
0x1800150b4  nop
0x1800150b5  mov     rcx, [rbp+57h+lpFileName]; bstrString
0x1800150b9  call    cs:__imp_SysFreeString
0x1800150c0  nop     dword ptr [rax+rax+00h]
0x1800150c5  nop
0x1800150c6  test    rdi, rdi
0x1800150c9  jz      short loc_1800150DA
0x1800150cb  mov     rcx, rdi
0x1800150ce  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800150d5  nop     dword ptr [rax+rax+00h]
0x1800150da  mov     eax, r14d
0x1800150dd  add     rsp, 88h
0x1800150e4  pop     r15
0x1800150e6  pop     r14
0x1800150e8  pop     r13
0x1800150ea  pop     r12
0x1800150ec  pop     rdi
0x1800150ed  pop     rsi
0x1800150ee  pop     rbx
0x1800150ef  pop     rbp
0x1800150f0  retn
```
