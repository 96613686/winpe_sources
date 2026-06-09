# EnterpriseWorkerThread::AddLicenseForPreinstalledApp(_GUID,_GUID)

- ea: `0x180014268`
- end: `0x180014504`
- name: `?AddLicenseForPreinstalledApp@EnterpriseWorkerThread@@AEAAJU_GUID@@0@Z`
- size: `668`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x1800165b8`

## callees

- `0x180002f64`
- `0x180014268`
- `0x180018518`
- `0x18001b210`
- `0x18001b2bc`
- `0x18006a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800143f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800144e7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800143f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800144e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001431f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001431f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143e3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001438a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001438a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014307`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180014307`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180014345`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180014345`

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
  int updated; // r14d
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
0x180014268  mov     [rsp-8+arg_10], r8
0x18001426d  mov     [rsp-8+arg_0], rcx
0x180014272  push    rbp
0x180014273  push    rbx
0x180014274  push    rsi
0x180014275  push    rdi
0x180014276  push    r12
0x180014278  push    r13
0x18001427a  push    r14
0x18001427c  push    r15
0x18001427e  lea     rbp, [rsp-1Fh]
0x180014283  sub     rsp, 88h
0x18001428a  mov     r12, rdx
0x18001428d  mov     r15, rcx
0x180014290  xor     ebx, ebx
0x180014292  mov     edi, ebx
0x180014294  mov     [rbp+57h+var_68], rbx
0x180014298  mov     [rbp+57h+lpFileName], rbx
0x18001429c  mov     [rbp+57h+var_60], rbx
0x1800142a0  mov     [rbp+57h+bstrString], rbx
0x1800142a4  mov     [rbp+57h+var_58], rbx
0x1800142a8  mov     [rbp+57h+arg_18], ebx
0x1800142ab  movaps  xmm0, xmmword ptr [rdx]
0x1800142ae  movdqa  [rbp+57h+var_50], xmm0
0x1800142b3  lea     r8d, [rbx+14h]
0x1800142b7  lea     r9, [rbp+57h+lpFileName]
0x1800142bb  lea     rdx, [rbp+57h+var_50]
0x1800142bf  lea     ecx, [rbx+1]
0x1800142c2  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x1800142c7  mov     r14d, eax
0x1800142ca  test    eax, eax
0x1800142cc  js      loc_1800144C0
0x1800142d2  mov     r13d, ebx
0x1800142d5  mov     [rbp+57h+nNumberOfBytesToRead], ebx
0x1800142d8  mov     esi, ebx
0x1800142da  mov     qword ptr [rbp+57h+var_50], rbx
0x1800142de  mov     [rbp+57h+var_70], rbx
0x1800142e2  mov     [rsp+0C0h+hTemplateFile], rbx; hTemplateFile
0x1800142e7  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800142ef  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800142f7  xor     r9d, r9d; lpSecurityAttributes
0x1800142fa  mov     edx, 80000000h; dwDesiredAccess
0x1800142ff  lea     r8d, [rbx+1]; dwShareMode
0x180014303  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180014307  call    cs:__imp_CreateFileW
0x18001430d  test    rax, rax
0x180014310  jz      short loc_180014340
0x180014312  mov     rbx, rax
0x180014315  mov     [rbp+57h+var_70], rax
0x180014319  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001431d  jnz     short loc_180014340
0x18001431f  call    cs:__imp_GetLastError
0x180014325  mov     r14d, eax
0x180014328  test    eax, eax
0x18001432a  jle     loc_1800143DB
0x180014330  movzx   r14d, ax
0x180014334  or      r14d, 80070000h
0x18001433b  jmp     loc_1800143DB
0x180014340  xor     edx, edx; lpFileSizeHigh
0x180014342  mov     rcx, rbx; hFile
0x180014345  call    cs:__imp_GetFileSize
0x18001434b  mov     [rbp+57h+nNumberOfBytesToRead], eax
0x18001434e  lea     ecx, [rax+1]
0x180014351  test    ecx, 0FFFFFFFEh
0x180014357  jnz     short loc_180014361
0x180014359  mov     r14d, 8007000Dh
0x18001435f  jmp     short loc_1800143DB
0x180014361  mov     ecx, eax; unsigned __int64
0x180014363  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014368  mov     r15, rax
0x18001436b  test    rax, rax
0x18001436e  jz      short loc_1800143D1
0x180014370  mov     rsi, rax
0x180014373  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x18001437c  lea     r9, [rbp+57h+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x180014380  mov     r8d, [rbp+57h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180014384  mov     rdx, rax; lpBuffer
0x180014387  mov     rcx, rbx; hFile
0x18001438a  call    cs:__imp_ReadFile
0x180014390  test    eax, eax
0x180014392  jnz     short loc_1800143AE
0x180014394  call    cs:__imp_GetLastError
0x18001439a  mov     r14d, eax
0x18001439d  test    eax, eax
0x18001439f  jle     short loc_1800143D7
0x1800143a1  movzx   r14d, ax
0x1800143a5  or      r14d, 80070000h
0x1800143ac  jmp     short loc_1800143D7
0x1800143ae  mov     eax, [rbp+57h+nNumberOfBytesToRead]
0x1800143b1  test    eax, eax
0x1800143b3  jnz     short loc_1800143BD
0x1800143b5  mov     r14d, 8007000Dh
0x1800143bb  jmp     short loc_1800143D7
0x1800143bd  xor     r14d, r14d
0x1800143c0  xor     esi, esi
0x1800143c2  mov     rdi, r15
0x1800143c5  mov     [rbp+57h+var_68], r15
0x1800143c9  mov     r13d, eax
0x1800143cc  mov     [rbp+57h+nNumberOfBytesToRead], esi
0x1800143cf  jmp     short loc_1800143D7
0x1800143d1  mov     r14d, 8007000Eh
0x1800143d7  mov     r15, [rbp+57h+arg_0]
0x1800143db  test    rbx, rbx
0x1800143de  jz      short loc_1800143EA
0x1800143e0  mov     rcx, rbx; hObject
0x1800143e3  call    cs:__imp_CloseHandle
0x1800143e9  nop
0x1800143ea  xor     ebx, ebx
0x1800143ec  test    rsi, rsi
0x1800143ef  jz      short loc_1800143FA
0x1800143f1  mov     rcx, rsi
0x1800143f4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800143fa  test    r14d, r14d
0x1800143fd  js      loc_1800144C0
0x180014403  movaps  xmm0, xmmword ptr [r12]
0x180014408  movdqa  [rbp+57h+var_50], xmm0
0x18001440d  mov     r8d, 6
0x180014413  lea     r9, [rbp+57h+bstrString]
0x180014417  lea     rdx, [rbp+57h+var_50]
0x18001441b  lea     ecx, [r8-5]
0x18001441f  call    ?RetrieveBSTR@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAPEAG@Z; EnrollmentManager::RetrieveBSTR(TABLEID,_GUID,ushort,ushort * *)
0x180014424  mov     r14d, eax
0x180014427  test    eax, eax
0x180014429  js      loc_1800144C0
0x18001442f  movaps  xmm0, xmmword ptr [r12]
0x180014434  movdqa  [rbp+57h+var_50], xmm0
0x180014439  mov     r8d, 16h
0x18001443f  lea     r9, [rbp+57h+arg_18]
0x180014443  lea     rdx, [rbp+57h+var_50]
0x180014447  call    ?RetrieveByte@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAE@Z; EnrollmentManager::RetrieveByte(TABLEID,_GUID,ushort,uchar *)
0x18001444c  mov     r14d, eax
0x18001444f  test    eax, eax
0x180014451  js      short loc_1800144C0
0x180014453  movaps  xmm0, xmmword ptr [r12]
0x180014458  movdqa  [rbp+57h+var_50], xmm0
0x18001445d  mov     byte ptr [rsp+0C0h+dwFlagsAndAttributes], 37h ; '7'
0x180014462  lea     rax, Src
0x180014469  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x18001446e  xor     r9d, r9d
0x180014471  lea     r8d, [r9+4]
0x180014475  lea     rdx, [rbp+57h+var_50]
0x180014479  mov     rcx, r15
0x18001447c  call    ?UpdateXAPRequestStatus@EnterpriseWorkerThread@@AEAAJU_GUID@@W4_ENTERPRISE_APP_INSTALL_STATE@@JPEBGE@Z; EnterpriseWorkerThread::UpdateXAPRequestStatus(_GUID,_ENTERPRISE_APP_INSTALL_STATE,long,ushort const *,uchar)
0x180014481  mov     r14d, eax
0x180014484  test    eax, eax
0x180014486  js      short loc_1800144C0
0x180014488  mov     rcx, [r15+130h]
0x18001448f  mov     rax, [rbp+57h+arg_10]
0x180014493  movaps  xmm0, xmmword ptr [rax]
0x180014496  movdqa  [rbp+57h+var_50], xmm0
0x18001449b  mov     rax, [rcx]
0x18001449e  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx
0x1800144a2  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rbx
0x1800144a7  mov     r9d, r13d
0x1800144aa  mov     r8, rdi
0x1800144ad  lea     rdx, [rbp+57h+var_50]
0x1800144b1  mov     rax, [rax+120h]
0x1800144b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144bd  mov     r14d, eax
0x1800144c0  xor     ecx, ecx; bstrString
0x1800144c2  call    cs:__imp_SysFreeString
0x1800144c8  nop
0x1800144c9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800144cd  call    cs:__imp_SysFreeString
0x1800144d3  nop
0x1800144d4  mov     rcx, [rbp+57h+lpFileName]; bstrString
0x1800144d8  call    cs:__imp_SysFreeString
0x1800144de  nop
0x1800144df  test    rdi, rdi
0x1800144e2  jz      short loc_1800144ED
0x1800144e4  mov     rcx, rdi
0x1800144e7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800144ed  mov     eax, r14d
0x1800144f0  add     rsp, 88h
0x1800144f7  pop     r15
0x1800144f9  pop     r14
0x1800144fb  pop     r13
0x1800144fd  pop     r12
0x1800144ff  pop     rdi
0x180014500  pop     rsi
0x180014501  pop     rbx
0x180014502  pop     rbp
0x180014503  retn
```
